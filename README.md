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

