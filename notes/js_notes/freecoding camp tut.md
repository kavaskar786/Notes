1. syntaxes
	1. print statement
		1. console.log("hello world!..")
	2. comments
		1. `// - is the inline comment`
		2. `/**/ - this the multiline comment the text inside the * will be commented out`
	3. data types
		1. undefined - special data type in js
			1. which sets the variable to undefined yet condition soo by this it will not throw any errors
			2. this value will defaultly assigned to every variable if we didn't assign any values to the variable
		2. null - special data type in js
		3. boolean
		4. string
		5. symbol - primitive variable and that is unique
		6. number - 
			1. there no int or floating everything will be treated as the numbers
		7. and object - this is data type like a key value pair
	4. variable
		1. declarations keywords
			1. var 
				1. var will declare the variable for the whole code
			2. let 
				1.  will declare the variable within the particular functional scope
			3. const 
				1. this will declare the constant variable that cannot be change again and is scope i don't know yet 
		2. actual declaration
			1. var a; this will only declare a variable and will not assign or initialized the variable(it is undefined)
				1. <mark style="background: #FFF3A3A6;">if we didn't assign a value to the variable it will be considered as uninitialized only because it is in the undefined state</mark>
			2. var b = 2; this will declare a variable and also assigns a value(initialize)
		3. the variables are case sensitive
	5. operations on numbers and operators
		1. + - plus for addition
			1. var product = 8 + 0;
		2. - - minus for subtracting
			1. var product = 8 - 0;
		3. * -  asterix for multiplication
			1. var product = 8 * 0;
		4. / - forward slash for dividing
			1.  var product = 8 / 0;
		5. % - modulus symbol for the remainder operator
			1. mostly used to determine whether the number is odd or even by using 2 in it.
		6. ++ - increment operator
			1. product++;
		7. -- - decrement operator
			1. product--;
		8. decimal multiplication, decimal division will give number as the result not a decimal
		9. compound operators
			1.  +=
				1. a=2
				2. a += 2 // a = a + 2
			2. -=
			3. `*=`
			4. /=
	6. string
		1. string literals
			1. single quote
				1. var eg = 'hello'
			2. double quote
				1. var eg = "hello"
			3. backticks
				1. var eg = `hello`  // back tic is not visible in the obsidian editor
			4. 