# udacityJSIntro
https://classroom.udacity.com/courses/ud803

https://github.com/ryo-capricorn92/rp-41-solutions

## special characters
Code	Character
\	   \ (backslash)
\"	'' (double quote)
\'	' (single quote)
\n	newline
\t	tab

ex) console.log("the man said \"I am neat\" and moved.")
output: the man said "I am neat" and moved.

* newline \n and tab \t
- newline \n and tab \t, are unique because they add additional whitespace to your Strings. A newline character will add a line break and a tab character will advance your line to the next tab stop.

ex) "Up up\n\tdown down"
output: "Up up
	down down"
  
Quiz: 
Q) "The file located at "C:\\Desktop\My Documents\Roster\names.txt" contains the names on the roster."
fix: add backslsah infront of each quote, each backslash add extra so it won't think it is expecting
     a special character.
     
Answer: "The file located at \"C:\\\\Desktop\\My Documents\\Roster\\names.txt\" contains the names on the roster."

* interesting fact
Lowercase letters have higher numerical values in the ASCII table than uppercase letters. For example, the string "green" is greater than the string "Green".

 == and != when you compared numbers/string for equality. You can also use them with strings! For example, let’s compare the string "Yes" to "yes". 
 output: false due to Case-sensitive

 Q) green > Green 
 output: true 
 - Explanation: Lowercase letters have higher numerical values in the ASCII table than uppercase letters. For example, the string "green" is greater than the string "Green".

"green" > "blue"
- Nice! When checking if a string is "greater than" or "less than" another string, JavaScript compares individual characters using a numerical value. Each character is assigned a numerical value that essentially corresponds to the character's location in an ASCII table: http://www.ascii-code.com/

* Why couldn't the shoes go out and play?
  They were all "tied" up!

- Take the format of a question and answer.

* 
joke = /* write your joke here */
console.log(joke);

Answer: var joke = "Why couldn't the shoes go out and play?\nThey were all \"tied\" up!";

* - Your code should have a variable haiku
- Your code should use string concatenation
- Your poem matches the famous haiku poem

var haiku = "Blowing from the west" + "\n" + "Fallen leaves gather" + "\n" + "In the east.";
console.log(haiku);

## null data type: "vlaue of nothing, while undefined refers to "absence of value"

* ex of null: var x = null;
* ex of undefined: var x; // declared but nothing is assigned
                   console.log(x); // undefined

## What is NaN?
NaN stands for "Not-A-Number" and it's often returned indicating an error with number operations. For instance, if you wrote some code that performed a math calculation, and the calculation failed to produce a valid number, NaN might be returned.

// calculating the square root of a negative number will return NaN
Math.sqrt(-10)

// trying to divide a string by 5 will return NaN
"hello"/5

What will be printed out?

var signedIn;
console.log(signedIn); 

output: undefined

- note: The variable signedIn was never assigned a value, so it will print out undefined. It's worth noting that signedIn could explicitly be assigned the value of null.
 - var signedIn = null;

* Q: "Hello" % 10
The answer is NaN or "Not a Number"

To perform the modulus operation, both "Hello" and 10 are coerced into the Number data type. When "Hello" is converted into a number, the result is NaN (Not a Number). You can see this by typing Number("Hello") in the console.

Therefore, the result of the operation is also NaN.

## DEFINITION: A strongly typed language is a programming language that is more likely to generate errors if data does not closely match an expected type. Because JavaScript is loosely typed, you don’t need to specify data types; however, this can lead to errors that are hard to diagnose due to implicit type coercion.

- ex of strongly typed programming language:
  int count = 1;
  string name = "Julia";
  double num = 1.2932;
  float price = 2.99;

- Equivalent code in JavaScript
  // equivalent code in JavaScript
  var count = 1; 
  var name = "Julia";
  var num = 1.2932;
  var price = 2.99;

## Definition: Type Coercion: using == or != operators, JavaScript first converts each value to the same type (if they’re not already the same type); 

- ex: "1" === 1 
output: false, This returns false because the string "1" is not the same type and value as the number 1. 

- ex: 0 === false
output: false, number 0 is not the same type and value as the boolean false.

- "3" > 1 is true because 3 is greater than 1 (implicit type coercion)
- true >= 0 is true because 1 greater than or equal to 0 (implicit type coercion)
- 1 !== false is true because 1 does not equal false (strict equality)
- 3 === 3 is true because 3 equals 3 (strict equality)

* QZ: Define two variables called thingOne and thingTwo and assign them values. Print the values of both variables in one console.log statement using concatenation. For example,

red blue
where "red" is the value of thingOne and "blue" is the value of thingTwo. Don't forget to use semicolons!

/*
 * Programming Quiz: Semicolons! (2-8)
 */

var thingOne = "red";
var thingTwo = "blue";

console.log(thingOne + " " + thingTwo);

- Q: Create a variable called bill and assign it the result of 10.25 + 3.99 + 7.15 (don't perform the calculation yourself, let JavaScript do it!). Next, create a variable called tip and assign it the result of multiplying bill by a 15% tip rate. Finally, add the bill and tip together and store it into a variable called total.
Hint: 15% in decimal form is written as 0.15.

- TIP: To print out the total with a dollar sign ( $ ) use string concatenation. To round total up by two decimal points use the toFixed() method. To use toFixed() pass it the number of decimal points you want to use. For example, if total equals 3.9860, then total.toFixed(2) would return 3.99.

* /*
 * Programming Quiz: Out to Dinner (2-10)
 */

 var bill = 10.25 + 3.99 + 7.15;
 var tip = bill * .15;
 var total = bill + tip;
 total.toFixed(2);  // round total up by two decimal points
 console.log("$"+ total.toFixed(2));

 - Your code should have a variable bill
- Your code should have a variable tip
- Your code should have a variable total
- Your variable bill should be declared using the var keyword
- Your variable bill should be a number
- Your variable bill should equal the result of 10.25 + 3.99 + 7.15
- Your variable tip should be declared using the var keyword
- Your variable tip should be a number
- Your variable tip should equal 15% of the bill
- Your variable total should be declared using the var keyword
- Your variable total should be a number
- Your variable total should equal the bill and tip added together
- Your code should print the total to the console

# Mad Libs is a word game where players have fun substituting words for blanks in a story. For this exercise, use the adjective variables below to fill in the blanks and complete the following message.

/*
 * Programming Quiz: MadLibs (2-11)
 * 
 * 1. Declare a madLib variable
 * 2. Use the adjective1, adjective2, and adjective3 variables to set the madLib variable to the message:
 * 
 * 'The Intro to JavaScript course is amazing. James and Julia are so fun. I cannot wait to work through the rest of this entertaining content!'
 */

- Q) var adjective1 = 'amazing';
var adjective2 = 'fun';
var adjective3 = 'entertaining';

- A) var madLib = "The Intro to JavaScript course is " + adjective1 + ". " + "James and Julia are so " + adjective2 + ". I cannot wait to work through the rest of this " + adjective3 + " content!";
console.log(madLib);

## modulo
/*
 * Programming Quiz: Even or Odd (3-2)
 *
 * Write an if...else statement that prints `even` if the 
 * number is even and prints `odd` if the number is odd.
 *
 * Note - make sure to print only the string "even" or the string "odd"
 */

// change the value of `number` to test your if...else statement
var number = 2;

if (number%2 === 0) {
   console.log("even"); 
} else {
   console.log("odd");
}


## Else if statements
In JavaScript, you can represent this secondary check by using an extra if statement called an else if statement.

var weather = "sunny";

if (weather === "snow") {
  console.log("Bring a coat.");
} else if (weather === "rain") {
  console.log("Bring a rain jacket.");
} else {
  console.log("Wear what you have on.");
}

Output: Wear what you have on.

* ex) Directions:
Write a series of conditional statements that:

prints "not a group" if musicians is less than or equal to 0
prints "solo" if musicians is equal to 1
prints "duet" if musicians is equal to 2
prints "trio" if musicians is equal to 3
prints "quartet" if musicians is equal to 4
prints "this is a large group" if musicians is greater than 4
TIP: Make sure to test your code with different values. For example,

If musicians equals 3, then trio should be printed to the console.
If musicians equals 20, then this is a large group should be printed to the console.
If musicians equals -1, then not a group should be printed to the console.


/*
 * Programming Quiz: Musical Groups (3-3)
 */

// change the value of `musicians` to test your conditional statements
var musicians = 1;

// your code goes here
if ( musicians <= 0 ){
    console.log("not a group");
} else if ( musicians === 1 ) {
    console.log("solo");
} else if ( musicians === 2 ) {
    console.log("duet");
} else if ( musicians === 3 ) {
    console.log("trio");
} else if ( musicians === 4 ) {
    console.log("quartet");
} else {
    console.log("this is a large group");
} 

* Directions:
For this quiz, you're going to help solve a fictitious murder mystery that happened here at Udacity! A murder mystery is a game typically played at parties wherein one of the partygoers is secretly, and unknowingly, playing a murderer, and the other attendees must determine who among them is the criminal. It's a classic case of whodunnit.

Since this might be your first time playing a murder mystery, we've simplified things quite a bit to make it easier. Here's what we know! In this murder mystery there are:

four rooms: the ballroom, gallery, billiards room, and dining room,
four weapons: poison, a trophy, a pool stick, and a knife,
and four suspects: Mr. Parkes, Ms. Van Cleve, Mrs. Sparr, and Mr. Kalehoff.
We also know that each weapon corresponds to a particular room, so...

the poison belongs to the ballroom,
the trophy belongs to the gallery,
the pool stick belongs to the billiards room,
and the knife belongs to the dining room.
And we know that each suspect was located in a specific room at the time of the murder.

Mr. Parkes was located in the dining room.
Ms. Van Cleve was located in the gallery.
Mrs. Sparr was located in the billiards room.
Mr. Kalehoff was located in the ballroom.
To help solve this mystery, write a combination of conditional statements that:

sets the value of weapon based on the room and
sets the value of solved to true if the value of room matches the suspect's room
Afterwards, print the following to the console if the mystery was solved:

__________ did it in the __________ with the __________!
Fill in the blanks with the name of the suspect, the room, and the weapon. For example,

Mr. Parkes did it in the dining room with the knife!
TIP: Make sure to test your code with different values. For example,

If room equals gallery and suspect equals Ms. Van Cleve, then Ms. Van Cleve did it in the gallery with the trophy! should be printed to the console.

- /*
 * Programming Quiz: Murder Mystery (3-4)
 */

// change the value of `room` and `suspect` to test your code
var room = "dining room";
var suspect = "Mr. Parkes";

var weapon = "";
var solved = false;

if (suspect === "Ms. Van Cleve" && room === "gallery") {
	weapon = "trophy";
    solved = true;
} else if (suspect === "Mr. Parkes" && room === "dining room") {
    weapon = "knife";
    solved = true; 
} else if (suspect === "Mrs. Sparr" && room === "billiards room") {
	weapon = "pool stick";
	solved = true;    
} else if (suspect === "Mr. Kalehoff" && room === "ballroom") {
    weapon = "poison";
	solved = true;
} else {
	console.log("try again");
}

if (solved) {
	console.log(suspect + " did it in the " + room + " with the " + weapon + "!");
}

## Logical operators
Logical operators can be used in conjunction with boolean values (true and false) to create complex logical expressions.

By combining two boolean values together with a logical operator, you create a logical expression that returns another boolean value. Here’s a table describing the different logical operators:

Operator	Meaning	Example	How it works
&&	Logical AND	value1 && value2	Returns true if both value1 and value2 evaluate to true.
||	Logical OR	value1 || value2	Returns true if either value1 or value2 (or even both!) evaluates to true.
!	Logical NOT	!value1	Returns the opposite of value1. If value1 is true, then !value1 is false.
By using logical operators, you can create more complex conditionals

- Evaluate the following logical expressions. Check the ones that evaluate to true.
* true || false => true
false && false => false
!true => false
(13 > -7) || (false == 0) => true, true
(3 != 6 % 3) && !(24 > 45) && (!false) => true

- In some scenarios, the value of B in logical AND and OR doesn't matter.
In both tables, there are specific scenarios where regardless of the value of B, the value of A is enough to satisfy the condition.

For example, if you look at A AND B, if A is false, then regardless of the value B, the total expression will always evaluate to false because both A and B must be true in order for the entire expression to be true.

- short-circuiting behavior: describes the event when later arguments in a logical expression are not considered because the first argument already satisfies the condition.

- bank teller quiz
https://classroom.udacity.com/courses/ud803/lessons/3ace947b-b5f6-40c1-bc11-3ec98fd1d936/concepts/03d8062f-6e1f-4f79-86e5-f49cde75e36d

Flowchart 
https://classroom.udacity.com/courses/ud803/lessons/3ace947b-b5f6-40c1-bc11-3ec98fd1d936/concepts/03d8062f-6e1f-4f79-86e5-f49cde75e36d

- Your code should have a variable balance
- Your code should have a variable checkBalance
- Your code should have a variable isActive
- Your code should include an if...else statement
- Your code should produce the expected output

Flowchart for checking your balance at the ATM (Click the image to enlarge the flowchart).
Use the following variables in your solution:

balance - the account balance
isActive - if account is active
checkBalance - if you want to check balance
Hint: The variable balance could be a value less than, greater than, or equal to 0. The variables isActive and checkBalance are booleans that can be set to true or false.

TIP: To print out the account balance with decimal points (i.e. 325.00), use the .toFixed() method and pass it the number of decimal points you want to use. For example, balance.toFixed(2) returns 325.00.
TIP: Make sure to test your code with different values. For example,

If checkBalance equals true and isActive equals false, then Your account is no longer active. should be printed to the console.

/*
 * Programming Quiz - Checking Your Balance (3-5)
 */

// change the values of `balance`, `checkBalance`, and `isActive` to test your code
var balance = 325.00;
var checkBalance = false;
var isActive = false;

// your code goes here
if (checkBalance === false) {
  console.log("Thank you. Have a nice day!");
} else {
	if (isActive === true && balance > 0) {
		console.log("Your balance is $" + balance.toFixed(2) + ".");
	} else if (isActive === false) {
		console.log("Your account is no longer active.");
	} else if (balance === 0) {
		console.log("Your account is empty.");
	} else {
		console.log("Your balance is negative. Please contact bank.");
	}
}

* Note: I missed else if instead wrote if else **

another approach no else early on
// change the values of `balance`, `checkBalance`, and `isActive` to test your code
var balance = 325.00;
var checkBalance = true;
var isActive = false;

- /*
 * Programming Quiz: Ice Cream (3-6)
 *
 * Write a single if statement that logs out the message:
 *
 * "I'd like two scoops of __________ ice cream in a __________ with __________."
 *
 * ...only if:
 *   - flavor is "vanilla" or "chocolate"
 *   - vessel is "cone" or "bowl"
 *   - toppings is "sprinkles" or "peanuts"
 *
 * We're only testing the if statement and your boolean operators.
 * It's okay if the output string doesn't match exactly.
 */

// change the values of `flavor`, `vessel`, and `toppings` to test your code
var flavor = "vanilla";
var vessel = "cone";
var toppings = "sprinkles";

// Add your code here

if(
(flavor === "vanilla" || flavor === "chocolate")
&&
(vessel === "cone" || vessel === "bowl")
&&
(toppings === "sprinkles" || toppings === "peanuts")
) 
{
  console.log("I'd like two scoops of " + flavor + " ice cream in a " + vessel + " with " + toppings + ".");
}

* Your code should have a variable flavor
- Your code should have a variable vessel
- Your code should have a variable toppings
- Your code should have an if statement
- Your code should use logical expressions
- Your code should work with flavor=vanilla, vessel=cone, and toppings=sprinkles
- Your code should work with flavor=vanilla, vessel=cone, and toppings=peanuts
- Your code should work with flavor=vanilla, vessel=bowl, and toppings=sprinkles
- Your code should work with flavor=vanilla, vessel=bowl, and toppings=peanuts
- Your code should work with flavor=chocolate, vessel=cone, and toppings=sprinkles
- Your code should work with flavor=chocolate, vessel=cone, and toppings=peanuts
- Your code should work with flavor=chocolate, vessel=bowl, and toppings=sprinkles
- Your code should work with flavor=chocolate, vessel=bowl, and toppings=peanuts
- Your code should not log anything when the flavor is something other than "vanilla" or "chocolate"
- Your code should not log anything when the vessel is something other than "cone" or "bowl"
- Your code should not log anything when toppings is something other than "sprinkles" or "peanuts"

https://www.youtube.com/watch?v=7AXpUbeUIK0



// your code goes here
if (!checkBalance) {
	console.log("Thank you. Have a nice day!");
} else if (isActive && balance > 0) {
	console.log("Your balance is $" + balance + ".");
} else if (!isActive) {
	console.log("Your account is no longer active.");
} else if (balance === 0) {
	console.log("Your account is empty.");
} else if (balance < 0){
	console.log("Your balance is negative. Please contact bank.");
}

resources: http://www.jsrepl.com/@emg

# Lesson 3: flowchar to code
https://classroom.udacity.com/courses/ud803/lessons/3ace947b-b5f6-40c1-bc11-3ec98fd1d936/concepts/a9ef2a0f-b68f-4c96-8528-5556927aba63

<script>
var price = 15.00;
var money = 20.00;

if (money >= price) {
    
}

</script>