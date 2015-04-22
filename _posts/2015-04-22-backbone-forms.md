---
layout: post
title: Backbone Forms
status: published
type: post
published: true
comments: true
---

I was thinking out loud today about Backbone views and how to manage user inputted data. When I has searched for
how to manage forms and handle user data the few examples I saw all used jQuery to pull the values out of the DOM. Which
we all know can cause issues with performance and adds a level of complexity when it comes to maintaining the code, as
the form grows the code used to pull the values out of the text boxes etc will grow.

I was thinking about this for a while until I came up with a pattern that would allow the code to update the model linked
to the view and handle new inputs added to the html without any code changes need in the view or the model. The pattern
(if you could call it that) uses [data attributes](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_data_attributes)
on the html to decide if the model needs updating and does this in a dynamic way.

{% highlight javascript %}
<input type="text" class="listen-to" data-model="input1"/>
{% endhighlight %}

The input is decorated with a data-model attribute which will map to an attribute on the model, it also has a "listen-to"
class which will be picked up by the views events.

{% highlight javascript %}
events: {
            "change .listen-to": "updateModel"
        }
{% endhighlight %}

The event will trigger once input has lost focus, this then calls the update model function. The event will fire when any
of the inputs have changed e.g allowing for as many inputs as needed. The event will be passed into the function and this
will be used to find out which attribute of the model to update and what value to update with.

{% highlight javascript %}
updateModel: function(evt){
            this.model.set(evt.currentTarget.attributes["data-model"].value,
            evt.currentTarget.value);
            //optional: update another view with the latest value in the model
            this.outputView = new OutputView({
                model: this.model,
                el: $("#output_container")
            });

        }
{% endhighlight %}

As you can see in the example (hacked together) the evt will hold target that triggered the event. The data-model attribute
is used to get the model attribute to update and the value is taken from the currentTarget. For demo purposes another
is update to show that the changes are made to the model in real time. This could be extended so that a submit button will
call a function that only needs to get the model and do what ever it wants with the values as the model attributes have been
updated as the user has been filling them in.

This takes away the need to use jQuery for getting the values from the inputs and allows more inputs to be added to the
template which out any view code changes.

You can see the full [demo here](http://jsfiddle.net/chrislaughlin/hbsw0kfo/).

