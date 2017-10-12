preImmersive-self-assessment-0-ssp7
Instructions:
Create the functions as described in each exercise. Our tests will check your functions only if they adhere to the exact function name described — so double check what you implement.

For these exercises, please do not worry about arguments outside what’s described. For example, if a function should accept a number argument, do not worry about the possibility that its input is anything but a number. If it should expect different types of arguments, you can then assume so.

This is an open book assessment – we encourage you to use MDN if you need a reference.

You will see passing tests as you go if you implemented your functions correctly. However, there’s 1 test that will always fail – this is by design.

Happy Hacking!

Exercise 1:
Write function helloPerson which takes in a name input and logs a greeting to the console. Note, this function should not have a return value.

For example, if someone calls your function 
helloPerson(‘Petra’);

It should log exactly:
“Hello, Petra”

Similarly, if your function were called with the argument “Juan”, it should log exactly:
“Hello, Juan”

And so on..

## function helloPerson (name) {
  console.log("Hello, " + name);
}


Exercise 2:
Write a function oppositeDay, which takes in a boolean value, and returns the opposite of that value.

For example, oppositeDay(false) should return the boolean value true.

Exercise 3:
Write a function get10thLetter which returns, you guessed it, the 10th letter of an input string. Assume all input strings will have at least 10 characters

Hint: Be sure it’s the 10th LETTER ;-)

Exercise 4:
Write a function indexesOnly which takes in an array, and replaces each element with their corresponding index values.

For example, if indexesOnly is called with the argument [“a”, “b”, “c”, 10, true], the return value should be [0,1,2,3,4];

Note: Your function should not create a new array, but replace the values of the original input array.

Exercise 5:
Write a function myLaptopInfo which takes in no input values, and returns an object with the properties “type”, “color”, and “yearPurchased”. The values of each property is up to you, but these three properties should exist within the object you return.

For example, if myLaptopInfo were called, it would return:

{ type : 'Macbook Air', color : 'Burgundy', yearPurchased : 2016 }
Exercise 6:
Write a function sayFavoriteFood which takes in an object with a name and favoriteFood property. The function will return a string stating the person’s name and favorite food. You can assume that the input object will always have these two properties.

For example:

var person = { name : "Kevin", favoriteFood : "tacos" };
sayFavoriteFood(person);
Will return:
"Kevin's favorite food is tacos"

******************
describe("helloPerson", function() {
  it("should log proper string", function() {
    var originalCL = console.log;
    var trappedMsg;
    
    console.log = function(msg) {
      trappedMsg = msg;
    }
    
    helloPerson('Jonathan');
    expect(trappedMsg).toBe('Hello, Jonathan');
    
    helloPerson('Bea');
    expect(trappedMsg).toBe('Hello, Bea');
    
    console.log = originalCL;
  });
});

describe("oppositeDay", function() {
  it("should return false if input true", function() {
    expect(oppositeDay(true)).toBe(false);
  });
  it("should return true if input false", function() {
    expect(oppositeDay(false)).toBe(true);
  });
});

describe("get10thLetter", function() {
  it("should get the 10th letter of the input string", function() {
    expect(get10thLetter('California Dreamin')).toBe('a');
    expect(get10thLetter('Onomatopoeia')).toBe('e');
    expect(typeof get10thLetter('Onomatopoeia')).toBe('string');
  });
});

describe("indexesOnly", function() {
  it("should return an array", function() {
    expect(Array.isArray(indexesOnly([10,20]))).toBe(true);
  });
  it("should return an array of only index values", function() {
    expect(indexesOnly([10,20,30,40])).toEqual([0,1,2,3]);
    expect(indexesOnly([])).toEqual([]);
    expect(indexesOnly([true, false])).toEqual([0,1]);
  });
  it("should replace the values of the input array", function() {
    var arr = ['a','b','c'];
    indexesOnly(arr);
    expect(arr).toEqual([0,1,2]);
  });
});

describe("myLaptopInfo", function() {
  it("should return an object", function() {
    expect(typeof myLaptopInfo()).toBe("object");
  });
  it("should contain correct properties", function() {
    var result = myLaptopInfo();
    expect(result.hasOwnProperty('type')).toBe(true);
    expect(result.hasOwnProperty('color')).toBe(true);
    expect(result.hasOwnProperty('yearPurchased')).toBe(true);
  });
});

describe("sayFavoriteFood", function() {
  it("should return person and favorite food", function() {
    expect(sayFavoriteFood({name : "Kyle", favoriteFood: "bananas"})).toBe("Kyle's favorite food is bananas");
  });
});

describe("This test", function() {
  it("will fail. If it's the only failing test, you're done! Make sure you 'submit' your code with the most up-to-date version for submission.", function() {
    expect(0).toBe(1);
  })
})

/*
 * Exercise 1:
*Write function helloPerson which takes in a name 
*input and logs a greeting to the console. Note, this 
*function should not have a return value.
*/

function helloPerson (name) {
  console.log("Hello, " + name);
}

/*
*Exercise 2:
*Write a function oppositeDay, which takes in a 
boolean value, and returns the opposite of that value.

For example, oppositeDay(false) should return 
the boolean value true.
*/

function oppositeDay (bool) {
  return !bool;
}

/* 
*Exercise 3:
Write a function get10thLetter which returns, you guessed it, 
the 10th letter of an input string. Assume all input strings 
will have at least 10 characters

Hint: Be sure it’s the 10th LETTER ;-)
*/

function get10thLetter (str) {
  return str[9];
}

/*
Exercise 4:
Write a function indexesOnly which takes in an array, 
and replaces each element with their corresponding 
index values.

For example, if indexesOnly is called with the argument 
["a", "b", "c", 10, true], the return value should be [0,1,2,3,4];

Note: Your function should not create a new array, 
but replace the values of the original input array.
*/

function indexesOnly (myArr) {
  for(var i = 0; i < myArr.length; i++) {
    /* each element in myArr replace it with current ith number*/
    myArr[i] = i;
  }
  return myArr;
}

/*
Exercise 5:
Write a function myLaptopInfo which takes in no input values,
and returns an object with the properties “type”, “color”,
and “yearPurchased”. The values of each property is up to you,
but these three properties should exist within the object
you return.

For example, if myLaptopInfo were called, it would return:

{ type : 'Macbook Air',
  color : 'Burgundy',
  yearPurchased : 2016 }

*/

function myLaptopInfo () {
  return {
    type: 'MBP',
    color: 'silver',
    yearPurchased: 2016
  };
}

/*
Exercise 6:
Write a function sayFavoriteFood which takes in an object
with a name and favoriteFood property.
The function will return a string stating the person’s name
and favorite food. You can assume that the input object
will always have these two properties.

For example:

var person = { name : "Kevin", favoriteFood : "tacos" };
sayFavoriteFood(person);
Will return:
"Kevin's favorite food is tacos"
*/

function sayFavoriteFood (person) {
  return person.name + "'s favorite food is " + person.favoriteFood;
}

- https://repl.it/M4fE/2
