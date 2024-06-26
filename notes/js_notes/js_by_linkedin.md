1. Versions of the JS
	1. ECMAScript 5(ES5) is the most commonly used version in all the browsers
	2. ES6 2015 provides more features
	3. ES5 and ES6 were mostly used in all the browsers
2. transpilers
	1. want to enjoy the features of the newer versions of the JS without loosing its compatability the tranpilers comes into play
	2.  which takes the newer version of the js and converts it to the standard version like ES5 or any previous standard version
	3. eg
		1. Babel available in babeljs.io 
3. ways to 
	1. JS console
		1. will execute only one line at a time
	2. Node JS
		1. if we only enter the node in terminal without any options it will leads to the repl(read,evaluate and print loop) 
	3. github
4. references
	1. eloquent js book
	2. exploring JS by dr axel aruschmayer
	3. you don't know js(github repo)
	4. MDN
	5. can i use website
	6. quirksmode.org
5. declaring and assigning variables
	1. always use var
	2. use equals to assign
	3. always use semicolon
	4. camelcase is the mostly used convention for the JS
		1. first word's first letter is small and other word's first letter need to be in capital
	5. reserved name or keywords cannot be used as the name of the variable
	6. strings
		1. anything between quotes or backticks is considered as the strings
		2. try to begin and end the strings with the same characters like single quotes or double quotes. don't swap with in the lines
		3. strings had properties and methods explore it in browser
		4. bacticks we can use also use js code by using ${} and code inside the curly braces
	7. js had infinity Infinity and -Infinity and also NaN
	8. explore Math in browser
	9. Boolean
		1. had only two values true and false
		2. boolean is also called flag
	10. constant
		1. the keyword const will do this
		2. this makes the variable constant that cannot be changed
	11. let
		1. along with war let is also one more keyword to declare the variables
	12. objects
		1. complex data type
		2. {};
		3. this stores the values in the key value pairs form
		4. 
6. object arrays and more
	1. object
		1. assume the scenario that we create one object and assigning to the other variable using the assignment operator(=)
			1. this will create only reference not a copy that means changing the values in the second variable will also affect the actual abjects value
			2. we had certain methods to do it
				1. Object.assign() method
				2. ... using spread operator
				3. using JSON method
		2. ... is called spread operator
		3. JSON stands for java script object notation
		4. we can able to use different data types
	2. array
		1. this data struct will preserve their order
		2. [] is used to create a array
		3. no key value pairs
		4. under the hood the array is object only in that keys will be automatically assigned
		5. array knows how much items in it
		6. manipulating arrays
			1. only square [] braces will work in array unlike object 
			2. the indexing will start from zero
			3. index done using [] the square braces
			4. assigning the values is also possilbe
			5. we have push methods to add the values at last
			6. and we have pop method to pop the last value from the list
			7. and also we shift and unshift methods to add and remove the values from the front
			8. delete method will not work on array unlike object instead we need to use the splice method
	3. comments
		1. // this is a single line comment
		2. `/* comment goes here*/` block level comment
	4. regex
		1. // the content inside this slases will be considered as the regex
		2. //i - this will makes the regex as case insensitive
		3. ^// - this will searches only in the beginning
		4. /hello $/ - this will searches in the end of the sentence
		5. /./  is representing 
7. simple comparisions
	1. === - strictly equality operator
		1. this checks whether the value in the left is identical to the right
	2. !== - strictly inequality operator
		1. this will checks whether the value in the left and the value in the right are in equal
	3. == - not strictly equal operator
		1. this will give the 1 == '1' true 😂
	4. != - not strictly inequal operator
		1. this will give 1 != '1' as false 😂
	5. < - less than operator
	6. > - greater than operator
	7. <= less than or equal to operator
	8. >= greater than or equal to operator
8. arithmetic operators
	1. + - addition operator
	2. - - subtractive operator
	3. `*`- multiplicative operator
	4. / - divisive operator
	5. % - remainder operator
	6. ++ - increment operator
	7. -- decrement operator
	8. += 
		1. eg : a = a +1 or a += 1
	9. -=
	10. `*=`
	11. /=
	12. concatenation works on strings
9. logical operators
	1. && - and operator
		1. returns true if both the conditions true
	2. || - or operator
		1. returns true if any one is true
	3. ! - operator
	4. && has more precedence than ||
10. conditions
	1.  window.confirm will raise the pop that will ask for conformation
	2. window.prompt will ask for the input
	3. if-else conditions
		1. if () {}
		2. else if () {}
		3. else {}
	4. switch statements
		1. switch () {}
		2. case "":     ; \nbreak;
		3. break is must in each case
	5. one line if statements
		1. if (condition) one line satatements
		2. else one line statements
	6. truthy
		1. if variable has something then it will be considered as truthy and vice versa
	7. ternary operator
		1. (condition)? statement 1 : statement2
11. data types in js
	1. numbers
	2. strings
	3. booleans
	4. objects
	5. arrays
	6. typeof var - method will give the type of the actual variable
	7. type of not a number (NaN) is number
	8. type of null is object(or empty object)
	9. type of unassigned variable will be undefined
12. Loops
	1. for loop
		1. for (let i = 0; i<10 ; i+= 1) (//statments)
	2. enumerative for loop
		1. for (var p in list1) {p's value is the key numbers}
		2. for (var v of list1) {v rep the values of the list instead of the key}
		3. 