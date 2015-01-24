---
layout: post
title: "Curring in JavaScript"
date: "2015-01-24"
---

I have been recently reading over JavaScript the good parts and came across the
chapter on currying. I have never worked with currying in my day to day work and the
examples in the book are a little abstract. So I thought I would look into this
a little more.  

### What is Currying

_Currying_ allows you to produce a new **function** by combining a function and
an argument. The example given by _JavaScript the good parts_ is shown below:

```javascript
var add1 = add.curry(1);
document.writeLn(add1(6));
```

This really doesn't mean much to me, what does the add function look like and do
I have to use the ```.curry() ``` function. So I decided to take a look
around for better examples of currying in JavaScript.

After looking at a [Medium article on currying](https://medium.com/@kbrainwave/currying-in-javascript-ce6da2d324fe)
its clear that using a curry function is not needed as shown in the below example.

```javascript
var iLove = function(a) {
  return function(b) {
    console.log('I love '.concat(a).concat(' with ').concat(b));
  };
};

var iLoveCurry = iLove('curry');
iLoveCurry('rice'); //I love curry and rice
iLoveCurry('chips'); //I love curry and chips
```

So we know that we can create a ```function``` that takes a paramater
and returns a function that also returns a paramater. But what are the real world
applications for curryed function.  

### Currying in the Real World

One example that I found of a real world use of currying invloved a conversion
function. Which could convert multiple units, the aim is to only have one function
for every unit type.

##### The functional closure way:

```javascript
function makeConverter(toUnit, factor, offset) {
  offset = offset || 0;
  return function(input) {
    console.log([((offset+input)*factor).toFixed(2), toUnit].join(" "));  
  }
}

var milesToKm = makeConverter('km',1.60936);
var poundsToKg = makeConverter('kg',0.45460);
var farenheitToCelsius = makeConverter('degrees C',0.5556, -32);

milesToKm(10); //"16.09 km"
poundsToKg(2.5); //"1.14 kg"
farenheitToCelsius(98); //"36.67 degrees C"
```

#### The curry Prototype way:

```javascript
Function.prototype.curry = function() {
  var __method = this;
  var slice = Array.prototype.slice;
  var args = slice.apply(arguments);
  return function() {
    return __method.apply(null, args.concat(slice.apply(arguments)));
  }
}

function converter(toUnit, factor, offset, input) {
  offset = offset || 0;
  console.log([((offset+input)*factor).toFixed(2), toUnit].join(" "));  
}

var milesToKm = converter.curry('km',1.60936,undefined);
var poundsToKg = converter.curry('kg',0.45460,undefined);
var farenheitToCelsius = converter.curry('degrees C',0.5556, -32);

milesToKm(10); //"16.09 km"
poundsToKg(2.5); //"1.14 kg"
farenheitToCelsius(98); //"36.67 degrees C"
```

We can see from the curry example that we can extend the ```Function``` prototype
to have a curry function that will apply the arguments coming in to the convert
function. This does save some code in the fact that if we need another unit converter
we just curry the converter and we are done. 
