---
layout: post
title: "UnderscoreJS Compose"
date: "2015-05-31"
---

After watching a [video](https://www.youtube.com/watch?v=m3svKOdZijA&app=desktop&utm_content=buffer13c68&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer) about [UnderscoreJS](http://underscorejs.org/)
I saw the use of the compose function, I have never noticed this when skimming through the underscore docs. The compose function:
> Returns the composition of a list of functions, where each function consumes the return value of the function that follows. In math terms, composing the functions f(), g(), and h() produces f(g(h())).

So to add some context to this; the compose function will take in multiple functions as its params and execute each of these passing the result in to the next function. One thing to note is that the functions are run in reverse order to which they were passed in. ***Why does this matter?*** Well if you have used underscore at any length you will have most likely used the chain function to try and clean up the use of multiple underscore functions:

``` javascript
_.chain(people)
	.sortBy(function(person) { return person.age; })
	.map(function(person) { return person.name + " is " + person.age})
	.first()
	.value();
//"mark is 14"
```
This code is taking an array of people and sorting them by age then returning a string for the person and getting the first string in the array. This works and is "functional" however this could be cleaner. This is where the compose function comes in we can use compose to link the functions together and not only provide cleaner code but also make the code reusable by default.

```javascript
var people = [{name: "john", age: 21}, {name: "mark", age: 14}, {name: "harry", age: 40}, {name: "Mary", age: 70}];
var mapNameAndAge = function(people) {
    return _.map(people, function(person) {
        return person.name + " is " + person.age;
    });
}
var sortByAge = function(people) {
    return _.sortBy(people, 'age');
}

var comp = _.compose(_.first, mapNameAndAge, sortByAge);
comp(people);
//"mark is 14"
```
So you can see there is some set up as you need to define the functions before you call compose however the final composed function is much cleaner and clearer to understand. This is also reuseable by defualt. This does not stop at underscore this can be used in other places such as API calls and data calls e.g:

```javascript
var updateUser = _.compose(save, update, find);
updateUser({id: 1, location: london});
```
