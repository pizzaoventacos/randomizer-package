# Randomizer Package:
## A new package that allows you to easily call random elements of an array, or from a string, AND also functions as a full wrapper for ez-math.js


### run in the shell: 
```
npm install ez-math.js randomizer-package --save
```
# __how to use__
1st Way
```
//better for using several packages or using a lot of different functions from this one
const Random = require('randomizer-package');
console.log(Random.random('first possibility, 'second possibility')) //returns one of the possibilities that are split by commas, randomly chosen
console.log(Random.random(['first possibility', 'second possibility'])) // does the same as above

console.log(Random.add('1, 2, 3, 4')); //returns 10
console.log(Random.add([1, 2, 3 , 4])); //same thing as above
console.log(Random.subtr([1, 2, 3, 4])) //same as: ((1 - 2) - 3) - 4; returns 8
console.log(Random.div([1, 2, 3])) //divides the first 2 parameters(1 and 2), and gets 0.5; divides that by next param and returns what it has when there are no more params to loop through. this returns 0.1666.
console.log(Random.multi('1, 2, 3, 4, 5')) //The same as 1(2)(3)(4)(5)
console.log(Random.pow('10, 2, 4')) //The same as (10^2)^4
console.log(Random.randomInt(10, 100)) //returns a random number between 10 and 100.
```

2nd Way
```
//easier if you are using few packages or only using a couple functions from this package.
const { random, randomInt, pow, subtr, add, multi, div } = require('randomizer-package');
console.log(random('1st option, 2nd option, 3rd option, has to be all in one string, etc.')); //returns one of the possibilities pseudo-randomly.
var poss = '1st option, 2nd option, 3rd option, has to be all in one string, etc.'
console.log(random(poss)) //The same as above
console.log(randomInt(1, 300)) //returns a pseudo-randomly generated number between 1 and 300.
/*

**Important**
 1. Calling the random function on the same set of possibilities twice returns two **different** elements.
 2.This still may return the same, but that is due to a the same number being randomly generated twice, and therefore, will not happen as often as the elements being different.
 
*/
```

# Methods: 
> ## __random__ - _returns a random response from an array or string_
>>Parameters - array(required)
>>>type: string or array

>example: math.random(['hi', 'hello', 'ok']) - returns a pseudo-randomly chosen response; other ways to do the same thing: var responses = ['hi', 'hello', 'ok'] math.random(responses); or: math.random('hi, hello, ok') //all in ONE string

> ## __randomInt__ - _returns a random integer within the min and max_
>>Parameters - min,max(both default to 0, so without any params, you will get 0, and with only min, you will get min)
>>>type: string or number

>example: math.randomInt(1, 100) - returns a random Integer between 1 and 100
> ## __add__ _- adds all of the numbers specified_
>>Parameters - array(required)
>>>type: string or array

>example: math.add([1, 2, 3, 4]) OR math.add('1, 2, 3 ,4') 1 STRING, the commas are inside the string, not representing new strings.

> ## __subtr__ - _subtracts all of the numbers specified in the same order_
>>Parameters - array(required)
>>>type: string or array

>example: math.subtr([1, 2, 3, 4]) - returns -8 (executes [(1-2)-3]-4)

> ## __multi__ - _multiplies all numbers specified_
>>Parameters - array(required)
>>>type: string or array

>example: math.multi([1, 2, 3, 4]) returns 24 (executes [(1 * 2) * 3] * 4)

> ## __div__ - _divides all numbers specified in the same order_
>>Parameters - array(required)
>>>type: string or array

>example: math.div([1, 2, 3, 4]) - returns 0.041666666666666664 (executes [(1 / 2) / 3] / 4)

> ## __pow__ - _raises array[0] to array[1] and raises that to the next parameter. - continues until there is nothing else to loop through(see example for better understanding)_
>>Parameters - array(required)
>>>type: string or array

>example: math.pow([5, 2, 3]) - returns 15625 (executes [5 ^ 2] ^ 3)(the same as: math.pow([5, math.multi([2, 3])])), which multiplies 2 and 3, getting 6, and raises 5 to that(5^6)

[Example](https://replit.com/@PizzaOvenTacos/Randomizer-Package)
