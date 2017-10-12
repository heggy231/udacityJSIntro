
// Part 1

function abbreviate(name){
  var firstName = name.first;
  var lastName = name.last;
  var lastStringed = JSON.stringify(lastName);
  var lastInitial = lastStringed.charAt(1);
  return firstName + ' ' + lastInitial + '.';
}


// Part 2 
function getEmployeesFrom(array, city){
  var arr = [];
  for (var i = 0; i < array.length; i++){
    if ((array[i].branch).indexOf(city) !== -1){
      nameAbbreviated = abbreviate(array[i].name);
      arr.push(nameAbbreviated);
    }
  }
    return arr;
}



// Part3 
var salesTeam = [
    {"name": {"first": "Aleen", "last" :"Atkins"}, "sales" : "$2314", "branch": "Austin, TX"},
    {"name": {"first": "Alvaro", "last" :"Angelos"}, "sales" : "$1668", "branch": "New York City, NY"},
    {"name": {"first": "Denese", "last" :"Dossett"}, "sales" : "$9248", "branch": "Austin, TX"},
    {"name": {"first": "Douglas", "last" :"Denney"}, "sales" : "$5058", "branch": "New York City, NY"},
    {"name": {"first": "Earline", "last" :"Erickson"}, "sales" : "$18876", "branch": "New York City, NY"},
    {"name": {"first": "Herman", "last" :"Hazell"}, "sales" : "$2746", "branch": "New York City, NY"},
    {"name": {"first": "Homer", "last" :"Hirth"}, "sales" : "$474", "branch": "Orlando, FL"},
    {"name": {"first": "Hwa", "last" :"Heidt"}, "sales" : "$9607", "branch": "San Francisco, CA"},
    {"name": {"first": "Hyon", "last" :"Hampshire"}, "sales" : "$13598", "branch": "New York City, NY"},
    {"name": {"first": "Issac", "last" :"Ingerson"}, "sales" : "$5225", "branch": "Austin, TX"},
    {"name": {"first": "Jeraldine", "last" :"Joplin"}, "sales" : "$2891", "branch": "New York City, NY"},
    {"name": {"first": "Jin", "last" :"Jeffrey"}, "sales" : "$14402", "branch": "Austin, TX"},
    {"name": {"first": "Joleen", "last" :"Jolin"}, "sales" : "$15736", "branch": "Austin, TX"},
    {"name": {"first": "Jude", "last" :"Jarrett"}, "sales" : "$7557", "branch": "San Francisco, CA"},
    {"name": {"first": "Magda", "last" :"Mireles"}, "sales" : "$1498", "branch": "Austin, TX"},
    {"name": {"first": "Mistie", "last" :"Montealegre"}, "sales" : "$6920", "branch": "New York City, NY"},
    {"name": {"first": "Nancy", "last" :"Napoli"}, "sales" : "$5255", "branch": "New York City, NY"},
    {"name": {"first": "Regine", "last" :"Rohrbaugh"}, "sales" : "$7881", "branch": "Orlando, FL"},
    {"name": {"first": "Rolando", "last" :"Riebel"}, "sales" : "$8573", "branch": "San Francisco, CA"},
    {"name": {"first": "Scarlett", "last" :"Stagg"}, "sales" : "$7126", "branch": "Orlando, FL"},
    {"name": {"first": "Sherron", "last" :"Strawn"}, "sales" : "$8848", "branch": "New York City, NY"},
    {"name": {"first": "Susan", "last" :"Shilling"}, "sales" : "$8542", "branch": "Seattle, WA"},
    {"name": {"first": "Tama", "last" :"Tworek"}, "sales" : "$9200", "branch": "Seattle, WA"},
    {"name": {"first": "Tonisha", "last" :"Taunton"}, "sales" : "$5219", "branch": "Orlando, FL"},
    {"name": {"first": "Vergie", "last" :"Villescas"}, "sales" : "$8712", "branch": "New York City, NY"}
];

function assertObjectsEqual(actual, expected, testName) {
  if (JSON.stringify(actual) === JSON.stringify(expected)) {
    console.log('Test passed');
  } else {
    console.log('Test ['+testName+'] failed: expected ', expected, ' but got, ', actual );
    }
} 
assertObjectsEqual(getEmployeesFrom(salesTeam, 'San Francisco'), ['Hwa H.', 'Jude J.', 'Rolando R.'], "Should return a list of all staff on the Sales Team from San Francisco");

// part 4 
function salesPerBranch(array){
  var obj = {};
  if (array.length === 0){
    return obj;
  } else {
    for (var i = 0; i < array.length; i++){
      if (obj[array[i].branch] === obj[array[i].branch]){
      obj[array[i]]++;
    } else {
      obj[array[i]] = 1;
  }
  return obj;
  }
}
}
/*
function salesPerBranch(){
  var array = str.split('');
  var obj = {};
  if (str.length === 0){
    return obj;
  } else { 
    for(var i = 0; i < array.length; i++){
    if(obj[array[i]]) obj[array[i]]++;
    else obj[array[i]] = 1;
  }
  return obj;
  }
}
*/

function wonkyCoins(num){
  num = Math.floor(num);
  if (num === 0){
    return 1;
  } else {
    return wonkyCoins(num/2) + wonkyCoins(num/3) + wonkyCoins(num/4);
  }
}
wonkyCoins(5);

function wordUnscramb(word, dictionary){
  var result =  dictionary.filter(function(item, i){
      return isAnagram(item, word);
  });
    return result;
}
function isAnagram(word1, word2){
  word1 = word1.split('').sort().join('').toLowerCase().trim();
  word2 = word2.split('').sort().join('').toLowerCase().trim();
  console.log(word1);
  console.log(word2);
  if ((word1.length === word2.length) && (word1 === word2)){
    return true;
  } else {
    return false;
  }
}

wordUnscramb("turn", ["numb", "turn", "runt", "nurt"]);

isAnagram('Punishment', 'Nine thumps');

var morse = {
	a: ".-",
	b: "-...",
	c: "-.-.",
	d: "-..",
	e: ".",
	f: "..-.",
	g: "--.",
	h: "....",
	i: "..",
	j: ".---",
	k: "-.-",
	l: ".-..",
	m: "--",
	n: "-.",
	o: "---",
	p: ".--.",
	q: "--.-",
	r: ".-.",
	s: "...",
	t: "-",
	u: "..-",
	v: "...-",
	w: ".--",
	x: "-..-",
	y: "-.--",
	z: "--.."
};

function morse_encode(str){
  var arr = [];
  for (var i = 0; i < str.length; i++){
    if(morse[str[i]]){
      arr.push(morse[str[i]]);
    }
  }
    return arr.join(' ');
}
morse_encode('Hi who are you');

function letterCount(str){
  var lettersCounted = {};
  str = str.toLowerCase().split('');
  for (var i = 0; i < str.length; i++){
    var letters = str[i];
    if (lettersCounted[letters] === undefined){
        lettersCounted[letters] = 1
    } else {
      lettersCounted[letters]++;
    }
  }
    return lettersCounted;
}

letterCount('Hi who are you there');

function nearestLarger(arr, i){
  var largest = arr[i];
  for(var j = 0; j < arr.length; j++){
    if(arr[j] > largest){
      largest = j;
    } else {
      return 'nil';
    }
  } 
      return largest;
}

nearestLarger([2, 6, 4, 8], 3);

function containsDuplicates(a) {
  a = a.sort();
  console.log(a);
  var arr = [];
  if (a.length === 0){
    return false;
  }for (var i = 0; i < a.length; i++){
            if (a[i] === a[i+1]){
              arr.push(a[i]);
            }
            if (arr.length > 0){
              return true;
            } if (arr.length === 0){
              return false;
            } else {
              return 'null';
            }
}
}
containsDuplicates([0, 1, 0, -1]);

function NorepeatsInRange(year1, year2){
  var rangeofYears = range(year1, year2);
  var result = [];
    console.log(rangeofYears);
    for (var i = 0; i < rangeofYears.length; i++){
      if (Norepeats(rangeofYears[i])){
        result.push(rangeofYears[i]);
      }
    }
          return result;
}
function range(year1, year2){
  var arr = [];
  var start = year1;
  for (var i = start ; i <= year2; i++){
      arr.push(i);
  }
  return arr;
}
function Norepeats(year){
  var arr = [];
  var yearArrayed = year.toString().split('').sort();
  for (var i = 0; i < yearArrayed.length; i++){
    if (yearArrayed[i] === yearArrayed[i+1]){
      arr.push(yearArrayed[i]);
    }
  }
    if(arr.length > 0){
      return false;
    } else {
      return true;
    }
}

Norepeats(2001);
NorepeatsInRange(1832, 2010);

function mostFrequentElement(array){
  var count = {};
  var mostFrequent = array[0];
  for (var i = 0; i < array.length; i++){
    var element = array[i];
    if (count[element] === undefined){
      count[element] = 1;
    } else {
      count[element]++;
    }
  }
    if (count[element] > mostFrequent){
      mostFrequent = element;
    }
      return mostFrequent;
}

mostFrequentElement([1,2,3,4,5,5,5,5,5,5]);

function longestBigram(str1){
  str1 = str1.split(' ');
  var longestBi = '';
  var longest = str1[0].length;
  for (var i = 0; i <str1.length-1; i++){
    var firstWord = str1[i];
    var secondWord = str1[i+1];
    var stringLengths = (firstWord + '' +secondWord).length;
      if (stringLengths > longest){
        longest = stringLengths;
      longestBi = firstWord + ' ' +secondWord;
    }
  }
      return longestBi;
}

longestBigram("One must have a mind of winter");

function nearestLargest(arr, i){
  var largest = arr[i];
  var largestIndex = 'nil';
  for (var j = 0; j < i; j++){
    if (arr[j] > largest){
      largest = arr[j];
      largestIndex = j;
    } for (var j2 = arr.length; j > i; j--){
      if (arr[j2] > largest){
        largest = arr[j2];
        largestIndex  = j2;
      }
    }
  }
    return largestIndex;
}

nearestLargest([2, 6, 4, 8], 3);

function mostFrequentElement(array){
  var count = {};
  var mostFrequent = array[0];
  for (var i = 0; i < array.length; i++){
    var element = array[i];
    if (count[element] === undefined){
      count[element] = 1;
    } else {
      count[element]++;
    }
  }
    if (count[element] > mostFrequent){
      mostFrequent = element;
    }
      return mostFrequent;
}

mostFrequentElement([1,2,3,4,5,5,5,5,5,5]);

function longestBigram(str1){
  str1 = str1.split(' ');
  var longestBi = '';
  var longest = str1[0].length;
  for (var i = 0; i <str1.length-1; i++){
    var firstWord = str1[i];
    var secondWord = str1[i+1];
    var stringLengths = (firstWord + '' +secondWord).length;
      if (stringLengths > longest){
        longest = stringLengths;
      longestBi = firstWord + ' ' +secondWord;
    }
  }
      return longestBi;
}

longestBigram("One must have a mind of winter");

function nearestLargest(arr, i){
  var largest = arr[i];
  var largestIndex = 'nil';
  for (var j = 0; j < i; j++){
    if (arr[j] > largest){
      largest = arr[j];
      largestIndex = j;
    } for (var j2 = arr.length; j > i; j--){
      if (arr[j2] > largest){
        largest = arr[j2];
        largestIndex  = j2;
      }
    }
  }
    return largestIndex;
}

nearestLargest([2, 6, 4, 8], 3);

function numConsecutiveElements(array){
  var arr = array.sort();
  console.log(arr);
  var count = 0; 
  for (i = 0; i < arr.length; i++){
    if(arr[i] === arr[i+1]){
      count++;
    }
  }
      return count;
}

numConsecutiveElements([1,1,2,2,2,3,4]);

function anagrams(str1, str2){
  str1 = str1.toLowerCase().split('').sort().join('').trim().split('');
  console.log(str1);
  str2 = str2.toLowerCase().split('').sort().join('').trim().split('');
  console.log(str2);
  for (var i = 0; i < str1.length; i++){
    if (str1[i] === str2[i]){
      return true;
    } else {
      return false;
  }
  }
}

anagrams('silent', "listen");

function removeNth(str, n){
  var arr = str.split('');
  var arr1 = [];
 for (var i = 0; i < str.length; i++){
   if (i !== n-1){
     arr1.push(arr[i]);
   }
 }
    return arr1.join('');
}

removeNth('ruby', 4);

function highCardPoints(array){
  var count = 0;
  for (var i = 0; i < array.length; i++){
    if (array[i] === 'J'){
      count +=1;
    } if (array[i] === 'Q'){
      count +=2;
  }if (array[i] === 'K'){
      count +=3;
}if (array[i] === 'A'){
      count +=4;
}
}
      return count;
}

highCardPoints(["2","3","4","5","6","7","8","9","10","J","Q","K","A"]);

var morse = {
	a: ".-",
	b: "-...",
	c: "-.-.",
	d: "-..",
	e: ".",
	f: "..-.",
	g: "--.",
	h: "....",
	i: "..",
	j: ".---",
	k: "-.-",
	l: ".-..",
	m: "--",
	n: "-.",
	o: "---",
	p: ".--.",
	q: "--.-",
	r: ".-.",
	s: "...",
	t: "-",
	u: "..-",
	v: "...-",
	w: ".--",
	x: "-..-",
	y: "-.--",
	z: "--.."
};

function morse_encode(str){
  var arr = [];
  for (var i = 0; i < str.length; i++){
    if(morse[str[i]]){
      arr.push(morse[str[i]]);
    }
  }
    return arr.join(' ');
}
morse_encode('Hi who are you');

function letterCount(str){
  var lettersCounted = {};
  str = str.toLowerCase().split('');
  for (var i = 0; i < str.length; i++){
    var letters = str[i];
    if (lettersCounted[letters] === undefined){
        lettersCounted[letters] = 1
    } else {
      lettersCounted[letters]++;
    }
  }
    return lettersCounted;
}

letterCount('Hi who are you there');

/*
function solution(number){
  var arr = [];
  for (var i = 0; i <= number; i++){
    count += i;
  if (( arr[i] % 3 === 0) || (arr[i] % 5 === 0)){
    arr.push(arr[i]);
  }
  return arr;
}
}
*/ 
function solution(number){
  var sum = 0;
  for (var i = 0; i < number; i++){
    if ((i % 3 === 0) || (i % 5 === 0)){
    sum += i;
  }
  }
    return sum;
}
solution(10);

/*
Exercise 1:
Write function helloPerson which takes in a name input and logs a greeting to the console. Note, this function should not have a return value.

For example, if someone calls your function 
helloPerson(‘Petra’);

It should log exactly:
“Hello, Petra”

Similarly, if your function were called with the argument “Juan”, it should log exactly:
“Hello, Juan”

And so on..

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
*/
/*
function helloPerson(name){
  console.log('Hello '+ name +'');
}
var output = helloPerson('kenny');
console.log(output);

function oppositeDay(boolean){
  if (boolean === true){
    return false;
  } else {
    return true;
  }
}

function get10thLetter(string){
 var arr = string.split('');
  return arr[9];
}
var output = get10thLetter('abcdefghijk');
console.log(output);

function indexesOnly(array){
  for (var i = 0; i < array.length; i++){
    array[i] = i;
}
  return i;
}
var arr = ['a','b','c'];
indexesOnly(arr);

function myLaptopInfo(){
  var laptopObject = {
    type: 'Macbook',
    color: 'black',
    yearPurchased: '2016'
  };
  return laptopObject;
}

myLaptopInfo();


function sayFavoriteFood(object){
  return ''+ object.name +'s favorite food is '+ object.favoriteFood +'';
}
var person = { name : "Kevin", favoriteFood : "tacos" };
sayFavoriteFood(person);
*/ 


/*
Exercise 1:
Write function helloPerson which takes in a name input and logs a greeting to the console. Note, this function should not have a return value.

For example, if someone calls your function 
helloPerson(‘Petra’);

It should log exactly:
“Hello, Petra”

Similarly, if your function were called with the argument “Juan”, it should log exactly:
“Hello, Juan”

And so on..

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
*/
/*
function helloPerson(name){
  console.log('Hello '+ name +'');
}
var output = helloPerson('kenny');
console.log(output);

function oppositeDay(boolean){
  if (boolean === true){
    return false;
  } else {
    return true;
  }
}

function get10thLetter(string){
 var arr = string.split('');
  return arr[9];
}
var output = get10thLetter('abcdefghijk');
console.log(output);

function indexesOnly(array){
  for (var i = 0; i < array.length; i++){
    array[i] = i;
}
  return i;
}
var arr = ['a','b','c'];
indexesOnly(arr);

function myLaptopInfo(){
  var laptopObject = {
    type: 'Macbook',
    color: 'black',
    yearPurchased: '2016'
  };
  return laptopObject;
}

myLaptopInfo();


function sayFavoriteFood(object){
  return ''+ object.name +'s favorite food is '+ object.favoriteFood +'';
}
var person = { name : "Kevin", favoriteFood : "tacos" };
sayFavoriteFood(person);
*/ 


/* 
function lesserNum(num1, num2) {
  if (num1 > num2){
    return num2;
  } else {
    return num1;
  }
}

//lesserNum(19, 4); //4
//lesserNum(3, 26); //3
//lesserNum(-10, -10); //-10


function countBy (factor, count) {
  var arr = [];
  for (var i = 0; i < count + 1; i++){
    arr[i] = factor * i;
  }
  return arr;
}

countBy(4, 3); //[0, 4, 8, 12]
countBy(5, 2); //[0, 5, 10]
countBy(7, 7); //[0, 7, 14, 21, 28, 35, 42, 49]
//countBy(10, 0); //[0]


function titleCase(str) {
 str = str.split(' ');
  for (var i = 0; i < str.length; i++){
    str[i] = str[i].charAt(0).toUpperCase() + str[i].slice(1);
  }
    return str.join(' ');
}
titleCase('california dreamin dreamin dreamin');

4) Given an object with this structure:

var person = {
  name: {
    first: "Richard",
    last: "Loeb"
  },
  birthDay: {
    month: "July",
    day: 12,
    year: 1957
  }
}
Write a function getNameAndBirthday  which returns the name and birthday in one line:

getNameAndBirthday(person); //"Richard Loeb: July 12, 1957"
Hint: Pay attention to the extra characters in the sample output.


function getNameAndBirthday(object){
  var name = Object.values(object.name);
   name = name.join(' ');
  var birthday = Object.values(object.birthDay);
  birthday[1] = birthday[1] + ',';
    birthday = birthday.join(' ');
  return ''+ name + ': ' + birthday +'';
}
var person = {
  name: {
    first: "Richard",
    last: "Loeb"
  },
  birthDay: {
    month: "July",
    day: 12,
    year: 1957
  }
}
getNameAndBirthday(person);
5) Someone who recorded these people’s names and birthdays wasn’t meticulous with their data entry, and input information with inconsistent capitalizations.

var anotherPerson = {
  name: {
    first: "kylA",
    last: "liVingSton"
  },
  birthDay: {
    month: "octobeR",
    day: 20,
    year: 1961
  }
}
Write a function ‘renderInfoNeatly’ which takes in a person object similar to the previous example, and returns the person’s name and birthday with proper casing.

renderInfoNeatly(anotherPerson); //"Kyla Livingston: October 20, 1961"

function titleCase(str) {
 str = str.split(' ');
  for (var i = 0; i < str.length; i++){
    str[i] = str[i].charAt(0).toUpperCase() + str[i].slice(1);
  }
    return str.join(' ');
}
function renderInfoNeatly(object){
  var name = Object.values(object.name);
  name = name.join(' ').toLowerCase();
  var birthday = Object.values(object.birthDay);
  birthday[1] = birthday[1] + ',';
  birthday = birthday.join(' ').toLowerCase();
  return titleCase(''+ name + ': '+ birthday +'');
}
var anotherPerson = {
  name: {
    first: "kylA",
    last: "liVingSton"
  },
  birthDay: {
    month: "octobeR",
    day: 20,
    year: 1961
  }
}
renderInfoNeatly(anotherPerson);
6) Write a function getPeopleBornIn which takes in a string month and an array, and returns a new array of people and their birthday information who were all born in the given month.

A sample input array would look like:

var staff = [
  {name: {first: "Alyssa", last: "Hacker"}, birthday: {month: "June", day: 5, year: 1987}},
  {name: {first: "Ben", last: "Bitdiddle"}, birthday: {month: "August", day: 19, year: 1984}},
  {name: {first: "Eva", last: "Ator"}, birthday: {month: "March", day: 29, year: 1980}},
  {name: {first: "Lem", last: "Tweakit"}, birthday: {month: "August", day: 11, year: 1989}},
  {name: {first: "Louis", last: "Reasoner"}, birthday: {month: "November", day: 17, year: 1992}}
];
A call to your function getPeopleBornIn(staff, 'August');

Would return:

["Ben Bitdiddle: August 19, 1984", "Lem Tweakit: August 11, 1989"]
*/
function titleCase(str) {
 str = str.split(' ');
  for (var i = 0; i < str.length; i++){
    str[i] = str[i].charAt(0).toUpperCase() + str[i].slice(1);
  }
    return str.join(' ');
}
function renderInfoNeatly(object){
  var name = Object.values(object.name);
  name = name.join(' ').toLowerCase();
  var birthday = Object.values(object.birthDay);
  birthday[1] = birthday[1] + ',';
  birthday = birthday.join(' ').toLowerCase();
  return titleCase(''+ name + ': '+ birthday +'');
}
var staff = [
  {name: {first: "Alyssa", last: "Hacker"}, birthday: {month: "June", day: 5, year: 1987}},
  {name: {first: "Ben", last: "Bitdiddle"}, birthday: {month: "August", day: 19, year: 1984}},
  {name: {first: "Eva", last: "Ator"}, birthday: {month: "March", day: 29, year: 1980}},
  {name: {first: "Lem", last: "Tweakit"}, birthday: {month: "August", day: 11, year: 1989}},
  {name: {first: "Louis", last: "Reasoner"}, birthday: {month: "November", day: 17, year: 1992}}
];
function getPeopleBornIn(staff, month){
  var bornIn = [];
  for (var i = 0; i < staff.length; i++){
    if (staff[i].birthday.month === month){
      bornIn.push(staff[i].name.first + " " + staff[i].name.last + ": "+ staff[i].birthday.month + " " + staff[i].birthday.day + ", " + staff[i].birthday.year);
    }
  }
    return bornIn;
}
getPeopleBornIn(staff, 'June');

function factorial(n){
  // Calculate the factorial here
  var factorial = 1;
  if (n === 0){
    return factorial;
  } if ((n > 12) || (n < 0)){
    throw new RangeError('should be between 0 to 12'); 
  } else {
    for (var i = n; i > 0; i--){
      factorial *= i;
    }
       return factorial;
  }
}

factorial(13);

/*
function accum(s) {
	s1 = s.toLowerCase().split('');
  for (var i = 0; i < s1.length; i++){
    i += s.repeat(i);
}
  return s1.join('-');
}
accum("abcd");    // "A-Bb-Ccc-Dddd"
accum("RqaEzty"); // "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
accum("cwAt");    // "C-Ww-Aaa-Tttt"
*/
function titleCase(str) {
 str = str.split(' ');
  for (var i = 0; i < str.length; i++){
    str[i] = str[i].charAt(0).toUpperCase() + str[i].slice(1);
  }
    return str.join('-');
}
function accum(s) {
	s1 = s.toLowerCase().split('');
  var s2 = s1.map(function(letter, i){
    return letter.repeat(i+1); 
});
   return titleCase(s2.join(' '));
}
accum("abcd");    // "A-Bb-Ccc-Dddd"
accum("RqaEzty"); // "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
accum("cwAt");    // "C-Ww-Aaa-Tttt"
//   str[i] = str[i].charAt(0).toUpperCase() + str[i].slice(1);
//  str[i] = str[i].charAt(0).toUpperCase() + str[i].slice(1);

/* 
Sales Team
You are managing a sales team and you are interested is analyzing some data related to their age and total sales. Take a moment to review the following data structure you will be analyzing:

var salesTeam = [
    {"name": {"first": "Aleen", "last" :"Atkins"}, "sales" : "$2314", "branch": "Austin, TX"},
    {"name": {"first": "Alvaro", "last" :"Angelos"}, "sales" : "$1668", "branch": "New York City, NY"},
    {"name": {"first": "Denese", "last" :"Dossett"}, "sales" : "$9248", "branch": "Austin, TX"},
    {"name": {"first": "Douglas", "last" :"Denney"}, "sales" : "$5058", "branch": "New York City, NY"},
    {"name": {"first": "Earline", "last" :"Erickson"}, "sales" : "$18876", "branch": "New York City, NY"},
    {"name": {"first": "Herman", "last" :"Hazell"}, "sales" : "$2746", "branch": "New York City, NY"},
    {"name": {"first": "Homer", "last" :"Hirth"}, "sales" : "$474", "branch": "Orlando, FL"},
    {"name": {"first": "Hwa", "last" :"Heidt"}, "sales" : "$9607", "branch": "San Francisco, CA"},
    {"name": {"first": "Hyon", "last" :"Hampshire"}, "sales" : "$13598", "branch": "New York City, NY"},
    {"name": {"first": "Issac", "last" :"Ingerson"}, "sales" : "$5225", "branch": "Austin, TX"},
    {"name": {"first": "Jeraldine", "last" :"Joplin"}, "sales" : "$2891", "branch": "New York City, NY"},
    {"name": {"first": "Jin", "last" :"Jeffrey"}, "sales" : "$14402", "branch": "Austin, TX"},
    {"name": {"first": "Joleen", "last" :"Jolin"}, "sales" : "$15736", "branch": "Austin, TX"},
    {"name": {"first": "Jude", "last" :"Jarrett"}, "sales" : "$7557", "branch": "San Francisco, CA"},
    {"name": {"first": "Magda", "last" :"Mireles"}, "sales" : "$1498", "branch": "Austin, TX"},
    {"name": {"first": "Mistie", "last" :"Montealegre"}, "sales" : "$6920", "branch": "New York City, NY"},
    {"name": {"first": "Nancy", "last" :"Napoli"}, "sales" : "$5255", "branch": "New York City, NY"},
    {"name": {"first": "Regine", "last" :"Rohrbaugh"}, "sales" : "$7881", "branch": "Orlando, FL"},
    {"name": {"first": "Rolando", "last" :"Riebel"}, "sales" : "$8573", "branch": "San Francisco, CA"},
    {"name": {"first": "Scarlett", "last" :"Stagg"}, "sales" : "$7126", "branch": "Orlando, FL"},
    {"name": {"first": "Sherron", "last" :"Strawn"}, "sales" : "$8848", "branch": "New York City, NY"},
    {"name": {"first": "Susan", "last" :"Shilling"}, "sales" : "$8542", "branch": "Seattle, WA"},
    {"name": {"first": "Tama", "last" :"Tworek"}, "sales" : "$9200", "branch": "Seattle, WA"},
    {"name": {"first": "Tonisha", "last" :"Taunton"}, "sales" : "$5219", "branch": "Orlando, FL"},
    {"name": {"first": "Vergie", "last" :"Villescas"}, "sales" : "$8712", "branch": "New York City, NY"}
];
Part 1
Write a function abbreviate, which takes in a name object and returns the first name and last initial.

Example:

abbreviate({first: 'Ricky', last: 'Pangelina'}); //'Ricky P.'
abbreviate({first: 'Samantha', last: 'Ward'}); //'Samantha W.'
Part 2
Write a function getEmployeesFrom, that takes in an array like salesTeam and a city, and returns an array that lists the first name and last initial of each person from that city. Note that the input value will only contain the city, and not the state.

Example:

getEmployeesFrom(salesTeam, 'San Francisco'); // ['Hwa H.', 'Jude J.', 'Rolando R.']
Part 3
Copy/paste in the following assertObjectsEqual function and its invocation. If you confirm that getEmployeesFrom passes the test, move to the next part. If you are receiving an error message, correct your getEmployeesFrom function.

function assertObjectsEqual(actual, expected, testName) {
  if (JSON.stringify(actual) === JSON.stringify(expected)) {
    console.log('Test passed');
  } else {
    console.log('Test ['+testName+'] failed: expected ', expected, ' but got, ', actual );
    }
}

assertObjectsEqual(getEmployeesFrom(salesTeam, 'San Francisco'), ['Hwa H.', 'Jude J.', 'Rolando R.'], "Should return a list of all staff on the Sales Team from San Francisco");
Part 4
Write a function salesPerBranch which returns an object with cities and the total amount of their respective employees’ sales as key-value pairs.

The result should appear as:

{
    'Austin, TX': 48423,
    'New York City, NY': 74572,
    'Orlando, FL': 20700,
    'San Francisco, CA': 25737,
    'Seattle, WA': 17742
}

var salesTeam = [
    {"name": {"first": "Aleen", "last" :"Atkins"}, "sales" : "$2314", "branch": "Austin, TX"},
    {"name": {"first": "Alvaro", "last" :"Angelos"}, "sales" : "$1668", "branch": "New York City, NY"},
    {"name": {"first": "Denese", "last" :"Dossett"}, "sales" : "$9248", "branch": "Austin, TX"},
    {"name": {"first": "Douglas", "last" :"Denney"}, "sales" : "$5058", "branch": "New York City, NY"},
    {"name": {"first": "Earline", "last" :"Erickson"}, "sales" : "$18876", "branch": "New York City, NY"},
    {"name": {"first": "Herman", "last" :"Hazell"}, "sales" : "$2746", "branch": "New York City, NY"},
    {"name": {"first": "Homer", "last" :"Hirth"}, "sales" : "$474", "branch": "Orlando, FL"},
    {"name": {"first": "Hwa", "last" :"Heidt"}, "sales" : "$9607", "branch": "San Francisco, CA"},
    {"name": {"first": "Hyon", "last" :"Hampshire"}, "sales" : "$13598", "branch": "New York City, NY"},
    {"name": {"first": "Issac", "last" :"Ingerson"}, "sales" : "$5225", "branch": "Austin, TX"},
    {"name": {"first": "Jeraldine", "last" :"Joplin"}, "sales" : "$2891", "branch": "New York City, NY"},
    {"name": {"first": "Jin", "last" :"Jeffrey"}, "sales" : "$14402", "branch": "Austin, TX"},
    {"name": {"first": "Joleen", "last" :"Jolin"}, "sales" : "$15736", "branch": "Austin, TX"},
    {"name": {"first": "Jude", "last" :"Jarrett"}, "sales" : "$7557", "branch": "San Francisco, CA"},
    {"name": {"first": "Magda", "last" :"Mireles"}, "sales" : "$1498", "branch": "Austin, TX"},
    {"name": {"first": "Mistie", "last" :"Montealegre"}, "sales" : "$6920", "branch": "New York City, NY"},
    {"name": {"first": "Nancy", "last" :"Napoli"}, "sales" : "$5255", "branch": "New York City, NY"},
    {"name": {"first": "Regine", "last" :"Rohrbaugh"}, "sales" : "$7881", "branch": "Orlando, FL"},
    {"name": {"first": "Rolando", "last" :"Riebel"}, "sales" : "$8573", "branch": "San Francisco, CA"},
    {"name": {"first": "Scarlett", "last" :"Stagg"}, "sales" : "$7126", "branch": "Orlando, FL"},
    {"name": {"first": "Sherron", "last" :"Strawn"}, "sales" : "$8848", "branch": "New York City, NY"},
    {"name": {"first": "Susan", "last" :"Shilling"}, "sales" : "$8542", "branch": "Seattle, WA"},
    {"name": {"first": "Tama", "last" :"Tworek"}, "sales" : "$9200", "branch": "Seattle, WA"},
    {"name": {"first": "Tonisha", "last" :"Taunton"}, "sales" : "$5219", "branch": "Orlando, FL"},
    {"name": {"first": "Vergie", "last" :"Villescas"}, "sales" : "$8712", "branch": "New York City, NY"}
];
*/
function abbreviate(name){
  var firstName = name.first;
  var lastName = name.last;
  var lastStringed = JSON.stringify(lastName);
  var lastInitial = lastStringed.charAt(1);
  return firstName + ' ' + lastInitial + '.';
}
// abbreviate({first: 'Ricky', last: 'Pangelina'});


function getEmployeesFrom(array){
  var arr = [];
  for (var i = 0; i < array.length; i++){
    if ((array[i].branch).indexOf("") !== -1){
      arr.push(array[i]);
    }
  }
    return arr;
}
var salesTeam = [
    {"name": {"first": "Aleen", "last" :"Atkins"}, "sales" : "$2314", "branch": "Austin, TX"},
    {"name": {"first": "Alvaro", "last" :"Angelos"}, "sales" : "$1668", "branch": "New York City, NY"},
    {"name": {"first": "Denese", "last" :"Dossett"}, "sales" : "$9248", "branch": "Austin, TX"},
    {"name": {"first": "Douglas", "last" :"Denney"}, "sales" : "$5058", "branch": "New York City, NY"},
    {"name": {"first": "Earline", "last" :"Erickson"}, "sales" : "$18876", "branch": "New York City, NY"},
    {"name": {"first": "Herman", "last" :"Hazell"}, "sales" : "$2746", "branch": "New York City, NY"},
    {"name": {"first": "Homer", "last" :"Hirth"}, "sales" : "$474", "branch": "Orlando, FL"},
    {"name": {"first": "Hwa", "last" :"Heidt"}, "sales" : "$9607", "branch": "San Francisco, CA"},
    {"name": {"first": "Hyon", "last" :"Hampshire"}, "sales" : "$13598", "branch": "New York City, NY"},
    {"name": {"first": "Issac", "last" :"Ingerson"}, "sales" : "$5225", "branch": "Austin, TX"},
    {"name": {"first": "Jeraldine", "last" :"Joplin"}, "sales" : "$2891", "branch": "New York City, NY"},
    {"name": {"first": "Jin", "last" :"Jeffrey"}, "sales" : "$14402", "branch": "Austin, TX"},
    {"name": {"first": "Joleen", "last" :"Jolin"}, "sales" : "$15736", "branch": "Austin, TX"},
    {"name": {"first": "Jude", "last" :"Jarrett"}, "sales" : "$7557", "branch": "San Francisco, CA"},
    {"name": {"first": "Magda", "last" :"Mireles"}, "sales" : "$1498", "branch": "Austin, TX"},
    {"name": {"first": "Mistie", "last" :"Montealegre"}, "sales" : "$6920", "branch": "New York City, NY"},
    {"name": {"first": "Nancy", "last" :"Napoli"}, "sales" : "$5255", "branch": "New York City, NY"},
    {"name": {"first": "Regine", "last" :"Rohrbaugh"}, "sales" : "$7881", "branch": "Orlando, FL"},
    {"name": {"first": "Rolando", "last" :"Riebel"}, "sales" : "$8573", "branch": "San Francisco, CA"},
    {"name": {"first": "Scarlett", "last" :"Stagg"}, "sales" : "$7126", "branch": "Orlando, FL"},
    {"name": {"first": "Sherron", "last" :"Strawn"}, "sales" : "$8848", "branch": "New York City, NY"},
    {"name": {"first": "Susan", "last" :"Shilling"}, "sales" : "$8542", "branch": "Seattle, WA"},
    {"name": {"first": "Tama", "last" :"Tworek"}, "sales" : "$9200", "branch": "Seattle, WA"},
    {"name": {"first": "Tonisha", "last" :"Taunton"}, "sales" : "$5219", "branch": "Orlando, FL"},
    {"name": {"first": "Vergie", "last" :"Villescas"}, "sales" : "$8712", "branch": "New York City, NY"}
];
getEmployeesFrom(salesTeam, 'San Francisco'); // ['Hwa H.', 'Jude J.', 'Rolando R.']

/*
function assertObjectsEqual(actual, expected, testName) {
  if (JSON.stringify(actual) === JSON.stringify(expected)) {
    console.log('Test passed');
  } else {
    console.log('Test ['+testName+'] failed: expected ', expected, ' but got, ', actual );
    }
} 
assertObjectsEqual(getEmployeesFrom(salesTeam, 'San Francisco'), ['Hwa H.', 'Jude J.', 'Rolando R.'], "Should return a list of all staff on the Sales Team from San Francisco");
*/


function titleCase(title, minorWords) {
  var arr = title.toLowerCase().split(' ');
  var array = minorWords.toLowerCase().split(' ');
  for (var i = 0; i < arr.length; i++){
    for (var j = 0; j < array.length; j++){
      if ( arr[i] !== array[j]){
    arr[i] = arr[i].charAt(0).toUpperCase() + arr[i].slice(1);
      } else {
        arr[i];
      }
  }
    }
    return arr.join(' ');
}


titleCase('a clash of KINGS', 'a an the of');

function findOdd(A) {
  //happy coding!
  if (A.length === 0){
  return 0;
} else {
  for (var i = 0; i < A.length; i++){
    if (A[i] % 2 !== 0){
       console.log(A[i]);
    }
  }
}
}
    
 findOdd([20,1,-1,2,-2,3,3,5,5,1,2,4,20,4,-1,-2,5]);

 function findOdd(A) {
  //happy coding!
  if (A.length === 0){
  return 0;
} else {
  for (var i = 0; i < A.length; i++){
    if (A[i] % 2 !== 0){
       console.log(A[i]);
    }
  }
}
}
    
 findOdd([20,1,-1,2,-2,3,3,5,5,1,2,4,20,4,-1,-2,5]);

 repl.it
@kenny_laprelle/untitled
javascript
No description
Log in
side-by-side	
light	
normal	
spaces	
2	
default	
soft wrap	
enabled	
enabled	
share
Run this repl and look for results in the console
run
fork
Share Link:
http://www.replit.info/LYnh/0
Share on:
Embed:
<script src="//www.replit.info/embed/LYnh/0.js"></script>

  
1
2
3
4
5
6
7
8
9
10
  function oddToEven(array) {
    for (var i = 0; i < array.length; i++){
      if (array[i] % 2 !== 0){
        array[i] * 2;
  }
  }
      return array;
  }
  
  oddToEven([1, 2, 3, 4, 5, 6]);

    

function square1(x) {
  return x * x;
}

function square2(x){
  return x * x;
}

function square3(x){
  return x * x;
}

function square(x){
    return x * x;
}

function square(x){ 
  return x * x;
}

function square(x){
  return x * x;
}

function cube(x) {
  return Math.pow(x, 3);
  // your code here
}

cube(3);

function fullName(firstName, lastName){
    return firstName + ' ' + lastName;
}
fullName("John", "Doe");

function average(num1, num2){
  return (num1 + num2) / 2;
}
average(10, 12);

function greeter(name){
  return 'Hello '+ name +'!';
}
greeter('Kenny');

function getRandomIntegerInclusive(min, max){
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
function addRandomAgeInclusive(argument, num1, num2){
  if (typeof argument === 'string'){
    var obj = {};
    obj.name = argument;
    obj.age = getRandomIntegerInclusive(num1, num2);
      return obj;
 } else if (typeof argument === 'object'){
  if ((argument.name === undefined) || (num1 > num2)){
    return argument;
  } else {
    var newObj = argument;
    newObj.age = getRandomIntegerInclusive(num1, num2);
    return newObj;
}
}
}

addRandomAgeInclusive({ name: 'Sean', id: 10330293 }, 30, 40); // { name: 'Sean', id: 10330293, age: 39 }
addRandomAgeInclusive('Kenny', 1, 10);


function getRandomIntegerInclusive(min, max){
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
function addRandomAgeInclusive(argument, num1, num2){
  if (typeof argument === 'string'){
    var obj = {};
    obj.name = argument;
    obj.age = getRandomIntegerInclusive(num1, num2);
      return obj;
 } else if (typeof argument === 'object'){
  if ((argument.name === undefined) || (num1 > num2)){
    return argument;
  } else {
    var newObj = argument;
    newObj.age = getRandomIntegerInclusive(num1, num2);
    return newObj;
}
}
}

addRandomAgeInclusive({ name: 'Sean', id: 10330293 }, 30, 40); // { name: 'Sean', id: 10330293, age: 39 }
addRandomAgeInclusive('Kenny', 1, 10);

function getRandomIntegerInclusive(min, max){
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
function addRandomAgeInclusive(argument, num1, num2){
  if (typeof argument === 'string'){
    var obj = {};
    obj.name = argument;
    obj.age = getRandomIntegerInclusive(num1, num2);
      return obj;
 } else if (typeof argument === 'object'){
  if ((argument.name === undefined) || (num1 > num2)){
    return argument;
  } else {
    var newObj = argument;
    newObj.age = getRandomIntegerInclusive(num1, num2);
    return newObj;
}
}
}
function addAges(array, num1, num2){
  return array.forEach(function(name){
    var nameObj = { name : name };
    nameObj['age'] = getRandomIntegerInclusive(num1, num2);
    return nameObj;
  });
}
var students = ["Lula", "Marla", "Isa", "Geoff", "Cassie", "Ana", "Kayla", "Mark", "Katja", "Kelly", "John", "Megan", "Omar", "Oren", "Pauli", "Rick", "Rita", "Ryan", "Tony", "Tyler", "Viktor"];
addAges(students, 12, 15);

function keep(array, condition) {
  return array.filter(function(element){
    return element === condition;
  });
  // your code here
  // start solution

  // end solution
}

keep([1, 2, 3, 4, 5, 6, 2], 2);

function keep(array, condition) {
  return array.filter(function(element){
    return element === condition;
  });
  // your code here
  // start solution

  // end solution
}

keep([1, 2, 3, 4, 5, 6, 2], 2);

/*

Look up your favorite movie on IMDB, and make an object named "favoriteMovie" that represents some aspects of that movie, e.g.:

Title
Director
Year released
Rating
Actors

HINT: Most movies have multiple actors. What data-structure do we use to represent a collection of similar things?

*/
var favoriteMovie = {
  title: 'Interstellar',
  Director: 'Christopher Nolan',
  yearReleased: 2014,
  Actors: ['Matthew McConaughey', 'Anne Hathaway', 'Jessica Chastain'],
  Rating: 8.6
};
console.log(favoriteMovie.Actors.length);

var you = {
  firstName: 'Kenny',
  lastName: 'Laprelle',
  dateOfBirth: '10/30/1993',
  age: 23,
  hometown: 'Napa, Ca',
  TVshow : 'Fresh Prince',
  Pets: 'Phoebe'
 };

console.log(you.age);

var alyssa = {
  name: {
    first: "Alyssa",
    middle: "P.",
    last: "Hacker"
  },
  age: 26
};
var Kenneth = {
  name: {
    first: "Kenneth",
    last: "Lap"
  },
  age: 23
};


function fullName(person) {
  var fullName = '';
  if (typeof person.name.middle !== 'undefined'){
      fullName = person.name.first + ' '+ person.name.middle + ' ' + person.name.last;
  } else {
    fullName = person.name.first + ' ' + person.name.last;
   
}
  return fullName;
}
fullName(Kenneth); 

/* 
function square(num){
  return num * num;
}
square(10) + 2;
// square(100) + square(77);
//square(8 / 2);
//square(2 + 17);
// square(square(15));
// 2. It is evaluated from the inside out. Meaning 15 is squared. Then that returning number is squared again. 
// 3. 
*/
function countCharacters(s) {
  var arr = s.split('');
    var obj = {};
  if (s.length === 0){
    return obj;
  } else {
    for (var i = 0; i < arr.length; i++){
      if (obj[arr[i]]){
      obj[arr[i]]++;
     } else {
        obj[arr[i]] = 1;
      }
    }
            return obj;
}
}
countCharacters("hello");


function twoSum(array, target){
  var arr1 = [];
  for (var i = 0; i < array.length; i++){
  for (var j = array.length; j > 0; j--){
    if (array[i] + array[j] === target){
      arr1.push(array[i]);
    }
  }
  }
    return arr1;
}

twoSum([3, 34, 4, 12, 5, 2], 9);

function clean(object) {
  if (object.hasOwnProperty('_fht')){
    delete object['_'];
  }
    return object;
}
var dirtyObject = {
  _fht: 192492,
  name: "Alyssa P. Hacker",
  age: 26,
  _byz: 939205,
  _ttrs: 510852
};

clean(dirtyObject);

function narcissistic( value ) {
  var valueStringed = value.toString();
  var arrayed = valueStringed.split('');
  var mapped = arrayed.map(function(element){
      return Math.pow(element, arrayed.length);
    });
      console.log(mapped);
    var mapAdded = mapped.reduce(function(a, b){
    return a + b;
    });
    if (mapAdded === value){
    return true;
    } else {
      return false;
    }
}
narcissistic(1634);

function getLongestWordOfMixedElements(arr) {
  var longest = arr.map(function(a, b){
    if (a.length > b.length){
      return arr[a];
    } else {
      return arr[b];
    }
  });
    return longest.length;
}
var output = getLongestWordOfMixedElements([3, 'word', 5, 'up', 3, 1]);
console.log(output);
// Write a function that will take a string as input, and return a new
// string with the same letters in reverse order.
//
//
// Difficulty: easy.

function reverse(string) {
  return string.split('').reverse().join('');
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for reverse")
console.log("===============================================")
    console.log(
      'reverse("abc") == "cba": ' + (reverse("abc") == "cba")
    )
    console.log(
      'reverse("a") == "a": ' + (reverse("a") == "a")
    )
    console.log(
      'reverse("") == "": ' + (reverse("") == "")
    )
console.log("===============================================")
// Write a function that takes an integer `n` in; it should return
// n*(n-1)*(n-2)*...*2*1. Assume n >= 0.
//
// As a special case, `factorial(0) == 1`.
//
// Difficulty: easy.

function factorial(n) {
  var product = 1;
  for (var i = n; i > 0; i--){
    product *= i;
  }
    return product;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //factorial")
console.log("===============================================")
    console.log(
      'factorial(0) == 1: ' + (factorial(0) == 1)
    )
    console.log(
      'factorial(1) == 1: ' + (factorial(1) == 1)
    )
    console.log(
      'factorial(2) == 2: ' + (factorial(2) == 2)
    )
    console.log(
      'factorial(3) == 6: ' + (factorial(3) == 6)
    )
    console.log(
      'factorial(4) == 24: ' + (factorial(4) == 24)
    )
console.log("===============================================")
// Write a method that takes in a string. Return the longest word in
// the string. You may assume that the string contains only letters and
// spaces.
//
// You may use the String `split` method to aid you in your quest.
//
// Difficulty: easy.

function longest_word(sentence) {
  var longest = sentence.split(' ').reduce(function(a, b){
    if (a.length >= b.length){
      return a;
    } else {
      return b;
    }
  });
      return longest;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //longest_word")
console.log("===============================================")
    console.log(
      'longest_word("short longest") == "longest": ' +
      (longest_word('short longest') == 'longest')
    )
    console.log(
      'longest_word("one") == "one": ' +
      (longest_word('one') == 'one')
    )
    console.log(
      'longest_word("abc function abcde") == "abcde": ' +
      (longest_word('abc function abcde') == 'abcde')
    )
console.log("===============================================")
// Write a function that takes in an integer `num` and returns the sum of
// all integers between zero and num, up to and including `num`.
//
// Difficulty: easy.

function sum_nums(num) {
  var sum = 0;
  for (var i = num; i > 0; i--){
    sum += i;
  }
    return sum;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //sum_nums")
console.log("===============================================")
    console.log('sum_nums(1) == 1: ' + (sum_nums(1) == 1))
    console.log('sum_nums(2) == 3: ' + (sum_nums(2) == 3))
    console.log('sum_nums(3) == 6: ' + (sum_nums(3) == 6))
    console.log('sum_nums(4) == 10: ' + (sum_nums(4) == 10))
    console.log('sum_nums(5) == 15: ' + (sum_nums(5) == 15))
console.log("===============================================")
// Write a function that will take in a number of minutes, and returns a
// string that formats the number into `hours:minutes`.
//
// Difficulty: easy.

function time_conversion(minutes) {
    var hours = Math.floor(minutes / 60);
     minutes = minutes % 60;
     return ''+ hours +':'+ minutes+'';
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //time_conversion")
console.log("===============================================")
    console.log('time_conversion(15) == "0:15": ' + (time_conversion(15) == '0:15'))
    console.log('time_conversion(150) == "2:30": ' + (time_conversion(150) == '2:30'))
    console.log('time_conversion(360) == "6:00": ' + (time_conversion(360) == '6:00'))
console.log("===============================================")
// Write a function that takes a string and returns the number of vowels
// in the string. You may assume that all the letters are lower cased.
// You can treat "y" as a consonant.
//
// Difficulty: easy.

function count_vowels(string){
  var arr = string.split('');
  var count = 0;
  for (var i = 0; i < arr.length; i++){
    if ((arr[i] === 'a') || (arr[i] === 'e') || (arr[i] === 'i') || (arr[i] === 'o') || (arr[i] === 'u')){
      count += 1;
    }
  }
                return count;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //count_vowels")
console.log("===============================================")
    console.log('count_vowels("abcd") == 1: ' + (count_vowels('abcd') == 1))
    console.log('count_vowels("color") == 2: ' + (count_vowels('color') == 2))
    console.log('count_vowels("colour") == 3: ' + (count_vowels('colour') == 3))
    console.log('count_vowels("cecilia") == 4: ' + (count_vowels('cecilia') == 4))
console.log("===============================================")
// Write a function that takes a string and returns true if it is a
// palindrome. A palindrome is a string that is the same whether written
// backward or forward. Assume that there are no spaces; only lowercase
// letters will be given.
//
// Difficulty: easy.

function is_palindrome(string) {
  var reversed = string.split('').reverse().join('');
  console.log(reversed);
  for (var i = 0; i < reversed.length; i++){
  if (reversed[i] === string[i]){
    return true;
  } else {
    return false;
  }
}
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //palindrome?")
console.log("===============================================")
    console.log('is_palindrome("abc") == false: ' + (is_palindrome('abc') === false));
    console.log('is_palindrome("abcba") == true: ' + (is_palindrome('abcba') === true));
    console.log('is_palindrome("z") == true: ' + (is_palindrome('z') === true));
console.log("===============================================")

is_palindrome('hannah');
// Write a function that takes a string in and returns true if the letter
// "z" appears within three letters **after** an "a". You may assume
// that the string contains only lowercase letters.
//
// Difficulty: medium.

function nearby_az(string) {
  var arr = string.split('');
  for (var i = 0; i < arr.length; i++){
    if ((arr[i] === 'a') && (arr[i +1] === 'z') || (arr[i + 2] === 'z') || (arr[i +3] === 'z')){
      return true;
    } else {
      return false;
    }
  }
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //nearby_az")
console.log("===============================================")
    console.log('nearby_az("baz") === true: ' + (nearby_az('baz') === true))
    console.log('nearby_az("abz") === true: ' + (nearby_az('abz') === true))
    console.log('nearby_az("abcz") === true: ' + (nearby_az('abcz') === true))
    console.log('nearby_az("a") === false: ' + (nearby_az('a') === false))
    console.log('nearby_az("z") === false: ' + (nearby_az('z') === false))
    console.log('nearby_az("za") === false: ' + (nearby_az('za') === false))
console.log("===============================================")

nearby_az('baz');
// Write a function that takes an array of numbers. If a pair of numbers
// in the array sums to zero, return the positions of those two numbers.
// If no pair of numbers sums to zero, return `null`.
//
// Difficulty: medium.

function two_sum(nums) {
  for (var i = 0; i < nums.length; i++){
  for (var j = i +1; j < nums.length; j++){
    if (nums[i] + nums[j] === 0){
      return ''+ nums.indexOf(nums[i])+','+ nums.indexOf(nums[j])+'';
  }
  }
}
    return false;
}


two_sum([1, 3, 5, -3]);
// Write a function that takes in a number and returns true if it is a
// power of 2. Otherwise, return false.
//
// You may want to use the `%` modulo operation. `5 % 2` returns the
// remainder when dividing 5 by 2; therefore, `5 % 2 == 1`. In the case
// of `6 % 2`, since 2 evenly divides 6 with no remainder, `6 % 2 == 0`.
//
// Difficulty: medium.

  function is_power_of_two(x) {
    return Math.log2(x) % 1 === 0;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //is_power_of_two")
console.log("===============================================")
    console.log('is_power_of_two(1) === true: ' + (is_power_of_two(1) === true))
    console.log('is_power_of_two(16) === true: ' + (is_power_of_two(16) === true))
    console.log('is_power_of_two(64) === true: ' + (is_power_of_two(64) === true))
    console.log('is_power_of_two(78) === false: ' + (is_power_of_two(78) === false))
    console.log('is_power_of_two(0) === false: ' + (is_power_of_two(0) === false))
console.log("===============================================")

is_power_of_two(1);
// Write a function that takes an array of numbers in. Your function should
// return the third greatest number in the array. You may assume that
// the array has at least three numbers in it.
//
// Difficulty: medium.

function third_greatest(nums) {
  var numsSorted = nums.sort(function(a, b){
    return b-a;
  });
  return numsSorted[2];
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //third_greatest")
console.log("===============================================")
    console.log(
      'third_greatest([5, 3, 7]) == 3: ' +
      (third_greatest([5, 3, 7]) == 3)
    )
    console.log(
      'third_greatest([5, 3, 7, 4]) == 4: ' +
      (third_greatest([5, 3, 7, 4]) == 4)
    )
    console.log(
      'third_greatest([2, 3, 7, 4]) == 3: ' +
      (third_greatest([2, 3, 7, 4]) == 3)
    )
console.log("===============================================")

third_greatest([1, 10, 4, 6, 7]);
// Write a function that takes in a number and returns a string, placing
// a single dash before and after each odd digit. There is one
// exception: don't start or } the string with a dash.
//
// You may wish to use the `%` modulo operation; you can see if a number
// is even if it has zero remainder when divided by two.
//
// Difficulty: medium.

function dasherize_number(num) {
  var numSplit = num.toString().split('');
  var result = '';
  for (var i = 0; i < numSplit.length; i++){
    if(numSplit[i] % 2 !== 0){
          if (i === 0){
        result += numSplit[i] + '-';
          } else if (i === numSplit.length -1){
            result += '-' + numSplit[i];
      } else {
          result += '-' + numSplit[i]+ '-';
      }
  } else {
    result += numSplit[i];
  }
}
        return result;
}
// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //dasherize_number")
console.log("===============================================")
    console.log(
      'dasherize_number(203) == "20-3": ' +
      (dasherize_number(203) == '20-3')
    )
    console.log(
      'dasherize_number(303) == "3-0-3": ' +
      (dasherize_number(303) == '3-0-3')
    )
    console.log(
      'dasherize_number(333) == "3-3-3": ' +
      (dasherize_number(333) == '3-3-3')
    )
    console.log(
      'dasherize_number(3223) == "3-22-3": ' +
      (dasherize_number(3223) == '3-22-3')
    )
console.log("===============================================")
dasherize_number(3032);
// Write a function that takes in a string of lowercase letters and
// spaces, producing a new string that capitalizes the first letter of
// each word.
//
// Difficulty: medium.

function capitalize_words(string) {
  var arr = string.toLowerCase().split(' ');
  for (var i = 0; i < arr.length; i++){
     arr[i] = arr[i].charAt(0).toUpperCase() + arr[i].slice(1);
  }
    return arr.join(' ');
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //capitalize_words")
console.log("===============================================")
    console.log(
      'capitalize_words("this is a sentence") == "This Is A Sentence": ' +
      (capitalize_words("this is a sentence") == "This Is A Sentence")
    )
    console.log(
      'capitalize_words("mike bloomfield") == "Mike Bloomfield": ' +
      (capitalize_words("mike bloomfield") == "Mike Bloomfield")
    )
console.log("===============================================")

capitalize_words('hi there who are you');

function getLongestWordOfMixedElements(arr) {
  var longest = arr.map(function(a, b){
    if (a.length > b.length){
      return arr[a];
    } else {
      return arr[b];
    }
  });
    return longest.length;
}
var output = getLongestWordOfMixedElements([3, 'word', 5, 'up', 3, 1]);
console.log(output);

// Write a function that will take a string as input, and return a new
// string with the same letters in reverse order.
//
//
// Difficulty: easy.

function reverse(string) {
  return string.split('').reverse().join('');
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for reverse")
console.log("===============================================")
    console.log(
      'reverse("abc") == "cba": ' + (reverse("abc") == "cba")
    )
    console.log(
      'reverse("a") == "a": ' + (reverse("a") == "a")
    )
    console.log(
      'reverse("") == "": ' + (reverse("") == "")
    )
console.log("===============================================")
// Write a function that takes an integer `n` in; it should return
// n*(n-1)*(n-2)*...*2*1. Assume n >= 0.
//
// As a special case, `factorial(0) == 1`.
//
// Difficulty: easy.

function factorial(n) {
  var product = 1;
  for (var i = n; i > 0; i--){
    product *= i;
  }
    return product;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //factorial")
console.log("===============================================")
    console.log(
      'factorial(0) == 1: ' + (factorial(0) == 1)
    )
    console.log(
      'factorial(1) == 1: ' + (factorial(1) == 1)
    )
    console.log(
      'factorial(2) == 2: ' + (factorial(2) == 2)
    )
    console.log(
      'factorial(3) == 6: ' + (factorial(3) == 6)
    )
    console.log(
      'factorial(4) == 24: ' + (factorial(4) == 24)
    )
console.log("===============================================")
// Write a method that takes in a string. Return the longest word in
// the string. You may assume that the string contains only letters and
// spaces.
//
// You may use the String `split` method to aid you in your quest.
//
// Difficulty: easy.

function longest_word(sentence) {
  var longest = sentence.split(' ').reduce(function(a, b){
    if (a.length >= b.length){
      return a;
    } else {
      return b;
    }
  });
      return longest;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //longest_word")
console.log("===============================================")
    console.log(
      'longest_word("short longest") == "longest": ' +
      (longest_word('short longest') == 'longest')
    )
    console.log(
      'longest_word("one") == "one": ' +
      (longest_word('one') == 'one')
    )
    console.log(
      'longest_word("abc function abcde") == "abcde": ' +
      (longest_word('abc function abcde') == 'abcde')
    )
console.log("===============================================")
// Write a function that takes in an integer `num` and returns the sum of
// all integers between zero and num, up to and including `num`.
//
// Difficulty: easy.

function sum_nums(num) {
  var sum = 0;
  for (var i = num; i > 0; i--){
    sum += i;
  }
    return sum;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //sum_nums")
console.log("===============================================")
    console.log('sum_nums(1) == 1: ' + (sum_nums(1) == 1))
    console.log('sum_nums(2) == 3: ' + (sum_nums(2) == 3))
    console.log('sum_nums(3) == 6: ' + (sum_nums(3) == 6))
    console.log('sum_nums(4) == 10: ' + (sum_nums(4) == 10))
    console.log('sum_nums(5) == 15: ' + (sum_nums(5) == 15))
console.log("===============================================")
// Write a function that will take in a number of minutes, and returns a
// string that formats the number into `hours:minutes`.
//
// Difficulty: easy.

function time_conversion(minutes) {
    var hours = Math.floor(minutes / 60);
     minutes = minutes % 60;
     return ''+ hours +':'+ minutes+'';
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //time_conversion")
console.log("===============================================")
    console.log('time_conversion(15) == "0:15": ' + (time_conversion(15) == '0:15'))
    console.log('time_conversion(150) == "2:30": ' + (time_conversion(150) == '2:30'))
    console.log('time_conversion(360) == "6:00": ' + (time_conversion(360) == '6:00'))
console.log("===============================================")
// Write a function that takes a string and returns the number of vowels
// in the string. You may assume that all the letters are lower cased.
// You can treat "y" as a consonant.
//
// Difficulty: easy.

function count_vowels(string){
  var arr = string.split('');
  var count = 0;
  for (var i = 0; i < arr.length; i++){
    if ((arr[i] === 'a') || (arr[i] === 'e') || (arr[i] === 'i') || (arr[i] === 'o') || (arr[i] === 'u')){
      count += 1;
    }
  }
                return count;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //count_vowels")
console.log("===============================================")
    console.log('count_vowels("abcd") == 1: ' + (count_vowels('abcd') == 1))
    console.log('count_vowels("color") == 2: ' + (count_vowels('color') == 2))
    console.log('count_vowels("colour") == 3: ' + (count_vowels('colour') == 3))
    console.log('count_vowels("cecilia") == 4: ' + (count_vowels('cecilia') == 4))
console.log("===============================================")
// Write a function that takes a string and returns true if it is a
// palindrome. A palindrome is a string that is the same whether written
// backward or forward. Assume that there are no spaces; only lowercase
// letters will be given.
//
// Difficulty: easy.

function is_palindrome(string) {
  var reversed = string.split('').reverse().join('');
  console.log(reversed);
  for (var i = 0; i < reversed.length; i++){
  if (reversed[i] === string[i]){
    return true;
  } else {
    return false;
  }
}
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //palindrome?")
console.log("===============================================")
    console.log('is_palindrome("abc") == false: ' + (is_palindrome('abc') === false));
    console.log('is_palindrome("abcba") == true: ' + (is_palindrome('abcba') === true));
    console.log('is_palindrome("z") == true: ' + (is_palindrome('z') === true));
console.log("===============================================")

is_palindrome('hannah');
// Write a function that takes a string in and returns true if the letter
// "z" appears within three letters **after** an "a". You may assume
// that the string contains only lowercase letters.
//
// Difficulty: medium.

function nearby_az(string) {
  var arr = string.split('');
  for (var i = 0; i < arr.length; i++){
    if ((arr[i] === 'a') && (arr[i +1] === 'z') || (arr[i + 2] === 'z') || (arr[i +3] === 'z')){
      return true;
    } else {
      return false;
    }
  }
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //nearby_az")
console.log("===============================================")
    console.log('nearby_az("baz") === true: ' + (nearby_az('baz') === true))
    console.log('nearby_az("abz") === true: ' + (nearby_az('abz') === true))
    console.log('nearby_az("abcz") === true: ' + (nearby_az('abcz') === true))
    console.log('nearby_az("a") === false: ' + (nearby_az('a') === false))
    console.log('nearby_az("z") === false: ' + (nearby_az('z') === false))
    console.log('nearby_az("za") === false: ' + (nearby_az('za') === false))
console.log("===============================================")

nearby_az('baz');
// Write a function that takes an array of numbers. If a pair of numbers
// in the array sums to zero, return the positions of those two numbers.
// If no pair of numbers sums to zero, return `null`.
//
// Difficulty: medium.

function two_sum(nums) {
  for (var i = 0; i < nums.length; i++){
  for (var j = i +1; j < nums.length; j++){
    if (nums[i] + nums[j] === 0){
      return ''+ nums.indexOf(nums[i])+','+ nums.indexOf(nums[j])+'';
  }
  }
}
    return false;
}


two_sum([1, 3, 5, -3]);
// Write a function that takes in a number and returns true if it is a
// power of 2. Otherwise, return false.
//
// You may want to use the `%` modulo operation. `5 % 2` returns the
// remainder when dividing 5 by 2; therefore, `5 % 2 == 1`. In the case
// of `6 % 2`, since 2 evenly divides 6 with no remainder, `6 % 2 == 0`.
//
// Difficulty: medium.

  function is_power_of_two(x) {
    return Math.log2(x) % 1 === 0;
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //is_power_of_two")
console.log("===============================================")
    console.log('is_power_of_two(1) === true: ' + (is_power_of_two(1) === true))
    console.log('is_power_of_two(16) === true: ' + (is_power_of_two(16) === true))
    console.log('is_power_of_two(64) === true: ' + (is_power_of_two(64) === true))
    console.log('is_power_of_two(78) === false: ' + (is_power_of_two(78) === false))
    console.log('is_power_of_two(0) === false: ' + (is_power_of_two(0) === false))
console.log("===============================================")

is_power_of_two(1);
// Write a function that takes an array of numbers in. Your function should
// return the third greatest number in the array. You may assume that
// the array has at least three numbers in it.
//
// Difficulty: medium.

function third_greatest(nums) {
  var numsSorted = nums.sort(function(a, b){
    return b-a;
  });
  return numsSorted[2];
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //third_greatest")
console.log("===============================================")
    console.log(
      'third_greatest([5, 3, 7]) == 3: ' +
      (third_greatest([5, 3, 7]) == 3)
    )
    console.log(
      'third_greatest([5, 3, 7, 4]) == 4: ' +
      (third_greatest([5, 3, 7, 4]) == 4)
    )
    console.log(
      'third_greatest([2, 3, 7, 4]) == 3: ' +
      (third_greatest([2, 3, 7, 4]) == 3)
    )
console.log("===============================================")

third_greatest([1, 10, 4, 6, 7]);
// Write a function that takes in a number and returns a string, placing
// a single dash before and after each odd digit. There is one
// exception: don't start or } the string with a dash.
//
// You may wish to use the `%` modulo operation; you can see if a number
// is even if it has zero remainder when divided by two.
//
// Difficulty: medium.

function dasherize_number(num) {
  var numSplit = num.toString().split('');
  var result = '';
  for (var i = 0; i < numSplit.length; i++){
    if(numSplit[i] % 2 !== 0){
          if (i === 0){
        result += numSplit[i] + '-';
          } else if (i === numSplit.length -1){
            result += '-' + numSplit[i];
      } else {
          result += '-' + numSplit[i]+ '-';
      }
  } else {
    result += numSplit[i];
  }
}
        return result;
}
// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //dasherize_number")
console.log("===============================================")
    console.log(
      'dasherize_number(203) == "20-3": ' +
      (dasherize_number(203) == '20-3')
    )
    console.log(
      'dasherize_number(303) == "3-0-3": ' +
      (dasherize_number(303) == '3-0-3')
    )
    console.log(
      'dasherize_number(333) == "3-3-3": ' +
      (dasherize_number(333) == '3-3-3')
    )
    console.log(
      'dasherize_number(3223) == "3-22-3": ' +
      (dasherize_number(3223) == '3-22-3')
    )
console.log("===============================================")
dasherize_number(3032);
// Write a function that takes in a string of lowercase letters and
// spaces, producing a new string that capitalizes the first letter of
// each word.
//
// Difficulty: medium.

function capitalize_words(string) {
  var arr = string.toLowerCase().split(' ');
  for (var i = 0; i < arr.length; i++){
     arr[i] = arr[i].charAt(0).toUpperCase() + arr[i].slice(1);
  }
    return arr.join(' ');
}

// These are tests to check that your code is working. After writing
// your solution, they should all print true.

console.log("\nTests for //capitalize_words")
console.log("===============================================")
    console.log(
      'capitalize_words("this is a sentence") == "This Is A Sentence": ' +
      (capitalize_words("this is a sentence") == "This Is A Sentence")
    )
    console.log(
      'capitalize_words("mike bloomfield") == "Mike Bloomfield": ' +
      (capitalize_words("mike bloomfield") == "Mike Bloomfield")
    )
console.log("===============================================")

capitalize_words('hi there who are you');

/*
A bigram is a pair of consecutive words. Given a string, return the longest bigram in that string. Include the space between the words. Assume there will be no punctuation. In the case of a tie, return the earlier bigram.
E.g., longest_bigram("One must have a mind of winter") => "must have"

*/

function longest_bigram(str){
  var arr1 = str.split(' ');
  var longest = 0;
   for (var i = 0; i < arr1.length-1; i++){
     var firstInLine = arr1[i];
     var nextInLine = arr1[i+1];
     var bigramLength = (firstInLine + ''+ nextInLine).length;
      if(bigramLength > longest){
        longest = bigramLength;
        var bigram = firstInLine + ' ' + nextInLine;
      }
   }
    return bigram; 
}
var string = "One must have a mind of winter";
longest_bigram(string);


function longest_bigram(str){
  var longestbigram = '';
  var longLength = 0;
  var strArr = str.split(" ");
  for(var i = 0; i < strArr.length-1; i++){
    var thisWord = strArr[i];
    var nextWord = strArr[i+1];
    var thisLength = (thisWord+' '+nextWord).length;
    console.log(thisLength);
    if(thisLength > longLength){
      longLength = thisLength;
      longestbigram = thisWord+' '+nextWord;
    }
  }
  return longestbigram;
}

console.log(longest_bigram("One must have a mind of winter")); // => "must have"
console.log(longest_bigram("To regard the frost and the boughs"));

/* 
Given a string, remove every vowel if its index is odd.
Hint: Rather than deleting characters (which would shift which characters are even and odd each time), construct a new string without the unwelcome vowels.

*/

function removeOddVowels (str){
  var arr = str.split('');
  var vowels = ['a', 'e', 'o', 'u', 'i'];
  var arr1 = arr.filter(function(element, i){
          if (i % 2 !== 0){
     return vowels.indexOf(element) === -1;
    } else {
      return arr.indexOf(element) > -1;
    }
    //return ((i % 2 === 0) && (vowels.indexOf(x) === -1))
  });
    return arr1.join('');
}
removeOddVowels("The cat in the hat"); // "The ct in th hat")
/*
var arr1 = ['a', 'e', 'o', 'u', 'i'];
  for (var i = 0; i < arr.length; i++){
    if((arr1.indexOf(arr[i]) === -1) && (i % 2 === 0)); 
    arr.push(arr[i]);
  }
    return arr2.join('');
}
*/

function fibonanci(n){
  // length = n;
  // return array of fibonanci of length n;
  var fibonanciArr = [];
  for (var i = 2; i < n; i++){
    fibonanciArr[0] = 0;
    fibonanciArr[1] = 1
    fibonanciArr[i] = fibonanciArr[i-1] + fibonanciArr[i-2];
  }
    return fibonanciArr;
}
fibonanci(10);

/*
Write a method that, when given a number, returns the number of factors of that number (including the number itself) that are prime. You may wish to write two helper methods: prime?(n) and factors(n).
*/ 
function numberOfPrimeFactors(n){
  return primeFactors(n).length;
}
function primeFactors(n){
  var arr1 = factors(n).filter(function(element){
    return prime(element);
  });
    return arr1;
}

function prime(n){
 var arr = [];
  for (var count = n; count > 0; count--) {
    if (n % count === 0){
    arr.push(count); 
} else {
    arr.push();
  }
  }
  if(arr.length <= 2){
    return true;
  } else {
    return false;
  }
}

function factors (n){
  var arr = [];
  for (var count = n; count > 0; count--) {
    if (n % count === 0){
    arr.push(count);
  } else {
    arr.push();
  }
  }
  return arr;
}
factors(20);
prime(2);
factors(1);
numberOfPrimeFactors(5);
primeFactors();

/*
Write a method that, when given a number, returns the number of factors of that number (including the number itself) that are prime. You may wish to write two helper methods: prime?(n) and factors(n).
*/ 
function numberOfPrimeFactors(n){
  return primeFactors(n).length;
}
function primeFactors(n){
  var arr1 = factors(n).filter(function(element){
    return prime(element);
  });
    return arr1;
}

function prime(n){
 var arr = [];
  for (var count = n; count > 0; count--) {
    if (n % count === 0){
    arr.push(count); 
} else {
    arr.push();
  }
  }
  if(arr.length <= 2){
    return true;
  } else {
    return false;
  }
}

function factors (n){
  var arr = [];
  for (var count = n; count > 0; count--) {
    if (n % count === 0){
    arr.push(count);
  } else {
    arr.push();
  }
  }
  return arr;
}
factors(20);
prime(2);
factors(1);
numberOfPrimeFactors(5);
primeFactors();

function twoSum(nums, target) {
    var arr = [];
    for (var i = 0; i < nums.length; i++){
        for (var j = i+1; j < nums.length; j++){
        if (nums[i] + nums[j] === target){
            arr[0] = i;
            arr[1] = j;
        }
    }
    }
         return arr;
}


twoSum([1, 2, 4, 5, 8, 7, 6], 3);

function stringLength(string){
  count = 0;
  var arr = string.slice(0, string.length);
  for (var i =0; i < arr.length; i++){
    count++;
  }
    return count;
}
stringLength('hello');

function clean(object) {
  for(var key in object){
    if (key[0] !== '_'){
      delete object[key];
    }
  }
  return object;
}
var dirtyObject = {
  _fht: 192492,
  name: "Alyssa P. Hacker",
  age: 26,
  _byz: 939205,
  _ttrs: 510852
};
clean(dirtyObject);

function select(object, array) {
  var obj = {};
  for (var key in object){
    for(var i = 0; i < array.length; i++){
    if (key === array[i]){
      obj[array[i]] = object[key];
    }
    }
}
       return obj;
}
select({a: 1, b: 2, c: 3}, ["a", "c", "d"]); // => {a: 1, c: 3}

function isAnagram(str1, str2){
  str1 = str1.split('').sort();
  str2 = str2.split('').sort();
  for (var i = 0; i < str1.length; i++){
      if (str1.length === str2.length){
        if (str1[i] === str2[i]){
        return true;
    } else {
  }
      }
         return false;
}
}

isAnagram("stone age", "stage one" );

//Define a method that accepts two arguments, a string and an integer. The method should return a copy of the string with the nth letter removed.

function removeN(str, n){
  str = str.split('');
  var str1 = str.splice(n, 1);
  return str;
}
removeN('Hi there who are you', 5);
/*
In the card game bridge, four cards are given point values: Jack: 1, Queen: 2, King: 3, Ace: 4. Given an array of strings corresponding to a hand of cards (the cards are represented like so: ["2","3","4","5","6","7","8","9","10","J","Q","K","A"]), return the total number of high card points for that hand.
E.g., high_card_points(["2","3","4","5","6","7","8","9","10","J","Q","K","A"]) => 10 high_card_points(["2", "A", "A"]) => 8
*/ 
function highCardPoints(array){
  var points = 0;
  for (var i = 0; i < array.length; i++){
    if (array[i] === 'J'){
      points += 1;
    } if (array[i] === 'Q'){
      points +=2;
    } if (array[i] === 'K'){
      points += 3;
    } if (array[i] === 'A'){
      points += 4;
    } else {
      points;
    }
  }
        return points;
}

var arrayed = ["2","3","4","5","6","7","8","9","10","J","Q","K","A", "Q"];
highCardPoints(arrayed);

//Primer (Most Frequent Element)

function mostFrequentElement(array){
  var mostFrequent = array[0];
  var counter = 0;
  array = array.sort();
  console.log(array);
  for (var i = 0; i < array.length; i++){
    if (array[i] === array[i+1]){
      counter+=1;
    }
    if (mostFrequent > counter){
      return mostFrequent;
    } else {
      return counter;
    }
  }
}

var arr = ["2","3", "2", "2", "3", "3","4","5","6","7","8","9","10","J","Q","K","A", "Q"];
mostFrequentElement(arr);

function repeatingElements(array){
  var count = 0;
  for (var i = 0; i < array.length; i++){
    if(array[i] === array[i+1]){
      count++;
    }
  }
    return count;
}

repeatingElements([1,1,2,3,4,5,5,6]);

function areAnagrams(str1,str2){
  str1 = str1.split('').sort();
  str2 = str2.split('').sort();
  for (var i = 0; i < str1.length; i++){
      if (str1.length === str2.length){
      if (str1[i] === str2[i]){
        return true;
      } else {
        return false;
      }
      }
    }
}

areAnagrams('dirty room', 'dormitory');

function firstDuplicate(a) {
  var index = a.length;
    for (var i = 0; i < index ; i++){
       for (var j = index-1; j >= i+1; j--){
         if (a[i] === a[j]){
          index = j;
        }
        }
    }
         return a[index] ? a[index] :-1;
}
firstDuplicate([1, 5, 2, 3, 6 , 5, 6]);

function firstNotRepeatingCharacter(s) {
    s = s.split('').sort();
    console.log(s);
    var holder = {};
    for (var i = 0; i < s.length; i++){
        if ((s[i] != s[i+1]) && (s[i+1] != s[i])){
          holder = s[i];
          break;
        }
    } 
      return holder;
}

firstNotRepeatingCharacter('abcabdefg');


function rotateImage(a) {
  let current, next;

  for (let j = 0; j < a.length / 2; j++) {
    for (let i = j; i < a.length - 1 - j; i++) {
      next = a[i][a.length - 1 - j];
      a[i][a.length - 1 - j] = a[j][i];
      current = next;

      next = a[a.length - 1 - j][a.length - 1 - i];
      a[a.length - 1 - j][a.length - 1 - i] = current;
      current = next;

      next = a[a.length - 1 - i][j];
      a[a.length - 1 - i][j] = current;
      current = next;

      next = a[j][i];
      a[j][i] = current;
      current = next;
    }
  }

  return a;
}
var input =[[1, 2, 3],
     [4, 5, 6],
     [7, 8, 9]];
     
rotateImage(input);

function containsDuplicates(a) {
    for (var i = 0; i < a.length; i++){
        for (var j = a.length; j >= 0; j--){
            if (a[i] === a[j]){
                return true;
            } else {
                return false;
            }
        }
    }
}

containsDuplicates([1,2, 2, 3,4]);




function getEveryOtherNumber(start, end) {
    var arr = []; 
        for (i = 0; i >0; i ++);
        if (i % 2 !== 0){
            return [];
        } else {
            if (i % 2 === 0);
            return i;
        }
}
var output = getEvenNumbersBetween(0, 10);


Example:
var input = 'check out how interesting this problem is, it\'s insanely interesting!';
var output = flipPairs(input);
console.log(output); // --> hcce kuo toh wnietertsni ghtsip orlbmei ,si 't sniasenyli tnreseitgn!

function flipPairs(str1) {
    var matchthem = str1.match(/.{1,2}/g);
    
    var flipthem = matchthem.map(function(i){
      return i.split("").reverse().join("");
    });
        return flipthem.join("");
}
  
  function assertEqual(actual, expected, testName){
      if(atual === expected){
          console.log(passed);
      } else {
        console.log('Failed "'+ testName +'" Expected "'+ expected + '", but got "'+ actual + '"');
      }
  }
  
  // ("").reverse().join("").split(" ").reverse().join(" ");
   //  return strreverse;

- liveCode
Example:
var input = 'check out how interesting this problem is, it\'s insanely interesting!';
var output = flipPairs(input);
console.log(output); // --> hcce kuo toh wnietertsni ghtsip orlbmei ,si 't sniasenyli tnreseitgn!

function flipPairs(str1) {
  var matched = str1.match(/.{1,2}/g);
      
      var flipped = matched.map(function(i){
      return i.split("").reverse().join("");
      });
      return flipped.join("");
  }
  
  function assertequal(actual, expected, testName){
    if ( actual === expected){
      console.log('Passed');
    } else {
      console.log('Failed ' + testName +' Expected '+ expected + ', but got ' + actual + '');
    }
  }
  
  function assertequal(abcdef, abcdef, did_flip);
  function assertequal(abcdef, badcfe , did_flip);




function flipeveryNchars(str1, N){ 
      var result = '';
      for (var i = 0; i < str1.length; i+=N){
    result += str1.substr(i,N).split("").reverse().join("");
  }
      return result;
  }
  
  function assertequal( actual, expected, testName){
      if ( actual === expected){
          console.log('passed');
      } else {
        console.log('FAILED '+ testName +' Expected '+ expected +' , but got '+ actual +'');
      }
  }
  
var input = 'a short example'; 
var output = flipeveryNchars(input, 5);
console.log(output);

- live code 


function getoutliervalue(str){
    var arr = str.split(' ');
    
    
    var odd = [];
    var even = [];
    
    for ( var i = 0; i < arr.length; i++ ){
      if ( arr[i] % 2 === 0 ){
        even.push(i);
    } else {
        odd.push(i);
    }
    }
      var removethis = [];
      if (odd.length > even.length){
        removethis = even;
      } else {
        removethis = odd;
      }
    return parseInt(removethis) +1;
    }
    
    function assertequal(actual, expected, testName){
      if (actual === expected){
        console.log('Passed');
      } else {
        console.log('Failed '+ testName +' Expected '+ expected + ', but got '+ actual +'')
      }
      }

var output1 = getoutliervalue("2 4 7 8 10");
var output2 = getoutliervalue("1 10 1 1");
console.log(output1);
console.log(output2);

function transposeTwoStrings(arr) {
  var size = 0;
  if(arr[0].length > arr[1].length)
    size = arr[0].length
  else
    size = arr[1].length

  result = [];
  for (var i = 0; i < size; i++) {
    var element1 = ' ';
    var element2 = ' ';

    if (typeof arr[0][i] !== 'undefined') element1 = arr[0][i];
    if (typeof arr[1][i] !== 'undefined') element2 = arr[1][i];

    console.log(element1 + ' ' + element2);
  }
}

transposeTwoStrings(['Hello','World']);

function findPairForSum(arr, sum) {
  var result;
  var seen = new Set();

  for (var i = 0; i < arr.length; i++) {
      var deff = sum - arr[i];

      if (seen.has(arr[i])){
        result = [deff, arr[i]];
      }

    seen.add(deff);
  }

  return result;
}
var pair = findPairForSum([3, 34, 4, 12, 5, 2], 9);
console.log(pair); // --> [4, 5]
