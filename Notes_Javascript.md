
**************************************************************************************
Notes on Javascript
**************************************************************************************

--------------------------------------------------------------------------------------
 History of Javascript
--------------------------------------------------------------------------------------

"Brendan Eich" created Javascript, He developed the language in 10 days (May 1995) while working at Netscape Communication which later collaborated with Sun Microsystems (even before Brendan start working on the it.)

Although it was developed under the name "Mocha", the language was officially called "LiveScript" when it first shipped in beta releases of Netscape Navigator 2.0 in September 1995, but it was renamed JavaScript when it was deployed in the Netscape Navigator 2.0 beta 3 in December 1995.

Javascript was largely influenced by Java, Self and Scheme programming language.

Soon after release Javascript for Browser, it also introduced an implementation of the language for Server Side Scripting in Netscape Enterprise Server.

Since 1996, Microsoft IIS Server has supported microsofts server side javascript (JScript) in ASP and ASP.Net

Node.js was introduced in 2009 by "Ryan Dahl"

--------------------------------------------------------------------------------------
 Javascript Versions and Release Cycle
--------------------------------------------------------------------------------------

ES1	-	June 1997
ES2	-	June 1998
ES3	-	June 1999
ES4	-	Abandoned 	

Till this time it has Annual Release Cycle

ES5	-	June 2009 , It took 10 years to release this version

ES6 (ES2015)	- June 2015, It took 6 years to release this versions 
				This is where the naming changes along with reintroduction of Annual Release cycle.
				
ES7 (ES2016)	- June 2016.
ES8 (ES2017)	- June 2017.
ES9 (ES2018)	- June 2018.
ES10 (ES2019)	- June 2019. 10th Edition.

ES.Next 		- It is a dynamic name that ressemble the next version. 

--------------------------------------------------------------------------------------
 Javascript Specification 
--------------------------------------------------------------------------------------

Javascript is also known as ECMAScript. Javascript version is often refered as ES5, ES6, ES7, or ESNext. 
ECMA Stands for European Computer Manufacturers Association. They are the one who manages the javascript specification / ECMA Specification.

ECMA Specification is how the javascript language should work, but doesnot gurantee its implementation. Its upto the browsers vendors to implement the same. or rather say the individual Javascript Engine.

Current ECMAScript Specification is ECMA - 262 URL below:

https://www.ecma-international.org/ecma-262/10.0/index.html

Actually there is a committee who looks after the Spec and adds any change. The committe is TC39.

TC39 committee meets 6 times every year to discuss on proposed changes in the spec.

--------------------------------------------------------------------------------------
 Javascript Feature Addition
--------------------------------------------------------------------------------------

There are 5 Stages after which any new feature is added to the Specification.

Stage - 0	StrawPerson		

	This is freeform way of Submitting Idea to TC39 Committee.

Stage - 1	Proposal

	A formalized Porposal for new feature. Champion must be identified who will be responsible for the proposal.
	Proposal must include examples, API, and demos.
	By accepting the proposal for stage 1 , TC39 shows its willingness to discussion.	

Stage - 2	Draft

	If a feature makes it to Stage 2 it will likely endup getting added in the spec. 
	It is the first version of what will be in the spec.

Stage - 3	Candidate

	Proposal is ready at this stage, and its now time for feedback. 
	TC39 designates reviewer who must sign on the spec.	

Stage - 4	Finalized

	Proposal in this stage is ready to be added to the Standard.
	Acceptance Test is done for Implementation.
	ECMA editor must sign off the spec.

To see the various feature requests in different stage the below github repo can be seen. under the proposal repository.

https://github.com/tc39

--------------------------------------------------------------------------------------
 Browser Support
--------------------------------------------------------------------------------------

https://kangax.github.io/compat-table/es6/


--------------------------------------------------------------------------------------
 Javascript Engine
--------------------------------------------------------------------------------------

There are various javascript engines some are given below:

1. V8               -       Used by Chrome
2. Chakra           -       Used by Edge
3. SpiderMonkey    	-       Used by Firefox
4. JavascriptCore   -       Used by Safari

NodeJs by default runs on V8 Engine, but it also has compiled versions for Chakra and SpiderMonkey

Some Javascript Engines for IOT - such as DuckTape.


--------------------------------------------------------------------------------------
 Javascript Engine (How it Works)
--------------------------------------------------------------------------------------

Source Code -> 
            Parser ->
                AST (Abstract Syntax Tree) ->
                                    Baseline Complier ->
                                                    Machine Code
                                    Optimizing Complier ->
                                                    Optimized Machine Code ->
                                                                Machine Code


--------------------------------------------------------------------------------------
 Script Declaration Inline or External File
--------------------------------------------------------------------------------------

Scripts can be writen directly in the html page under the <script></script> tag

  	<html>
     <head>
         <script>
             console.log('hello world!');
         </script>
     </head>
     <body>
         This is the body
     </body>
 	</html> 

The recomended method is to put the javascript in a seperate file and link usihg the script tag at the end of body.

  	<html>
     <head>
     </head>
     <body>
         This is the body
         <script scr="script.js"></script> 
     </body>
 	</html> 

This way the scripts are downloaded and executed at the end and hence doesnot interfer in HTML parsing. There is a better way using the defer keyword.

	<head>
		<script scr="script.js" defer></script>
	</head>

now with defer the same thing happens, but the file is downloaded along with parsing of the HTML. but the script is executed at the end.

defer 	- keyword helps defer the execution, multiple scripts with defer is executed one after the other as listed in the code.
async	- keyowrd works the same as defer but the execution aslo happens after download, 
		the are download parallel to each other the download order is random.


--------------------------------------------------------------------------------------
 Type of Datatypes
--------------------------------------------------------------------------------------

6 type of primitive data types in javascript

Number  - Values are actually floating number
String  - set of characters
Boolean - stores true or false
undefined   - variable declared but undefined
null    - variable not declared
symbol  -  it can be used to define unique value , like a unique property or key.

Javascript is a Dynamically Typed and Weakly Typed language. There is no static typing in javascript

typeof NaN is number

typeof null is object        this is due to a bug in javascript which is not fixed due to legacy codes

const x = +'123' // this will convert it to number.

const x = '' + 123 // this will convert it to string.

--------------------------------------------------------------------------------------
 Comments in Javascripts
--------------------------------------------------------------------------------------

// This is a single line comment

Comment using /* */. Anything between this is a multi line comment.

--------------------------------------------------------------------------------------
 Variable Declaration and Syntax
--------------------------------------------------------------------------------------

var firstName = 'John'; // declare a variable

console.log(firstName ); // display in console

var job ;  // decalre a variable without initializing with value

console.log(job); // undefined means not defined.

console.log(anotherjob) // this would give a compilation error not defined

--------------------------------------------------------------------------------------
 Invalid Variable Names
--------------------------------------------------------------------------------------

var 3somevar = 3; // this is not a valid variable name (variable name cannot start with number)

var &somevar = 'something'; // this is also invalid. (variable name cannot start with a special characters)

var _somevar = 'valid'; // this is valid (_ and $ sign can be used to start a varaible name)

var $somevar = 'valid with $ sign'; //this is valid

var somevar&more = 'invlaid again'; // this is invalid (variable name cannot contain special characters)

var some var = 'no space is invalid'; // this is invalid


SyntaxError			- when syntax error in script, file containing syntax error no code executes.
ReferenceError   	- when something is not defined. code till that line is run.
TypeError        	- when variable is accessed as function, code till that line is run.

var someVar = 'recomended way to name a variable, '

The above is the way of nameing a variable, it should be camelCase.

var function = 'this'; // this is invalid variable name, as the name is a reserved word.

var if = 'this is invalid';

var number = 'this is valid';

var string = 'this is valid';

var javascript = 'this is valid';

var $ = 'this is valid';

var undefined = 'this is valid';

--------------------------------------------------------------------------------------
 Recomendated Variable Name case is camelCase
--------------------------------------------------------------------------------------

camelCase - 	first letter small and then all starting letter as capitals
            	firstName, firstAndLastName, eBay, iPhone.

PascalCase - 	similar to camelCase but the first letter should be caps.
             	FirstName, FirstAndLastName.

snake_Case -	similar to camelCase but the word seperator is _. 
				starting letter is generally starts with lowercase,
            	but all letter can be either lower or upper case.
            	foo_bar, Hello_world, first_Name.


--------------------------------------------------------------------------------------
 Declare multiple variables in same line
--------------------------------------------------------------------------------------

	var firstName, job, isMarried ;

	firstName= 'John';
	job = 'teacher';
	isMarried=false;

	console.log(firstName + ' is a '+ job + ' and is he married?'+ isMarried);

--------------------------------------------------------------------------------------
 var, let & const
--------------------------------------------------------------------------------------

var , let & const are all used to declare a variable

var		-	has either a global scope or function scope

let		-	In same scope cannot be redeclared. variable in child scope can have the same name which is then shadowed.
			It has block level scope. means variable declared in {} is available within that code block.

const	-	In same scope cannot be redeclared.
			It cannot be reinitialized.
			In case of an array/object the child elements can be added, deleted or updated.

While declaring constant, The Variable names should be in uppercase. It is rather a reccomendation than a need. constant name can be any valid variable named seen earlier.

Shadow variable / variable shadowing is when the local scope has variable with same name as in the parent scope. In such case the local scoped variables shadows the parent scoped varaible and only the local scoped variable is used.

Hoisting happens for variable/object, where they are hoisted to the the top of the code block. 

	In case of var the value is hoisted and initialized with undefined.

	In case of let/const the value is hoisted but not initialized. hence variable declared with let/const cannot be accessed before declaration.

	In case of functions they are hoisted and initialized with the function body.

--------------------------------------------------------------------------------------
 Truthy and Falsy Values
--------------------------------------------------------------------------------------

undefined , null, 0, '', NaN  are the only values that are Falsy, rest all values are Truthy.

	var height;

	if(height){console.log('true');}    // height is undefined and hence no output

	height = 23;

	if(height){console.log('true');}    // height is 23 and hence output is true

	height = 0;

	if(height){console.log('true');}    // height is 0 and hence output is false, as 0 is falsy

	if(undefined){console.log('true');}     // undefined is falsy
	if(null){console.log('true');}     // null is falsy
	if(0){console.log('true');}     // 0 is falsy
	if(''){console.log('true');}     // '' is falsy
	if(NaN){console.log('true');}     // NaN is falsy

	if("somedata"){console.log('true');} // its true

	if(true) {console.log('true');}

	height = 0;
	if (height||height ===0){
		console.log('true');
	}

=== is the equality operator which checks for value as well as type

typeof can be used to check the type of variable.


--------------------------------------------------------------------------------------
 Arrays
--------------------------------------------------------------------------------------

Arrays are collections of variables , they can contain different datatypes.

initialized new array

	var names = ['John','Mark','Sara'];
	var years = new Array(1999, 2018, 2011);

Javascript array starts at index 0

	console.log(names[0]);      // gives item at index of 0
	console.log(names.length);  // length of an array

mutate array data

	names[1] = 'Krtika';
	names[names.length] = 'Aparna';
	console.log(names);

Array with different datatype

	var john = ['John', 'Smith', 1999, 'designer1', false];

	john.push('blue');  	// add element to the end of the array
	john.unshift('Mr.');    // add element to the start of the array    

	console.log(john);

	john.pop(); // removes element from end of an array
	john.shift(); // removes element from start of an array

	console.log(john);

Find element in an array

	console.log(john.indexOf('blue'));  // indexOf finds the element in the array

if found it returns the index of the first occurence of the element else it returns the value as -1

	var isDesigner = john.indexOf('designer') === -1? 'Not a Desinger':'Is a Designer';
	console.log('John '+ isDesigner);

--------------------------------------------------------------------------------------
 Arrays Key things to Note
--------------------------------------------------------------------------------------

Array .length gives the item with highest index + 1 . This doesnot actually give the no of items.

In arrays keys can aslo be added ,like the objects, but they dont show when we console it. because array only shows indexed properties, 

since keys are non indexed properties, they are ignored.

using [] with var will create an array

using {} with var will create an object

Array is indexed, while objects are unordered collection and hence cannot be sorted.

	var a = ['sd','sdf','sdsd'];
	console.log(typeof a);

As can be seen above typeof Array is actually an object.

Sparse Array

	var b = [];
	b[2] = 2;
	console.log(b);

Sparse Arrays are those which do not have contigious set of arrays starting from index 0, they have holes in between.

Dense Array

	var a = [undefined, undefined , 2];
	console.log(a);

When Array/Objects are checked for equality they return false. even if the data for both the variable are same.

	const arr1 = [1,2,3];
	const arr2 = [1,2,3];	
	console.log(arr1 === arr2);  // this return false
	console.log(arr1 == arr2);	// this also returns false

Now if they are copied as below and then compared will return true.

	const arr1 = [1,2,3];
	const arr2 = arr1;
	console.log(arr1 === arr2);  // this return true
	console.log(arr1 == arr2);	// this also returns true

--------------------------------------------------------------------------------------
 Objects and Properties
--------------------------------------------------------------------------------------

Object Literal

	var john = {
		firstName : 'John',
		lastName : 'Smith',
		age : 28,
		family : ['bob', 'sandy', 'mark'],
		isMarried : false
	};

	console.log(john);

	console.log(john.firstName);

	console.log(john['lastName']);

	var x = 'age';

	console.log(john[x]);

new Object syntax

	var john = new Object();
	john.firstName = 'John';
	john.age = 29;
	john['lastName'] = 'Smith';

	console.log(john);

--------------------------------------------------------------------------------------
 Objects and Methods
--------------------------------------------------------------------------------------

	var john = {
		firstName : 'John',
		lastName : 'Smith',
		birthYear : 1999,
		family : ['bob', 'sandy', 'mark'],
		isMarried : false,
		calcAge: function(){
			this.age = 2019-this.birthYear;
		}
	};

	john.calcAge();
	console.log(john.firstName + ' age is '+ john.age);

this is a special keyword, that resembles current object

--------------------------------------------------------------------------------------
 Template Literals
--------------------------------------------------------------------------------------

Back-ticks(`) can be used instead of Single Quotes(') or Double Quotes(") for string containation as below

	let name = 'Sanjeev'
	let age = 29;
	let someValue = 'My Name is ' + name + " and my age is " + age;

same can written with back-ticks, the advantage is it can be written with newline (output will appear with newline)

	let someValue = `My Name is 
		`+name+` and my age is ` + age;

using Template Literals. its even more easier.

	let someValue = `My Name is ${name} and my age is ${age}`;

\n is used to put linebreaks. where (\) is called a escape character.

--------------------------------------------------------------------------------------
 Operators
--------------------------------------------------------------------------------------

Assignment Operators

	var a, b;
	a= 10;  // = is an assignment operator
	b= 20;

Math Operator

	console.log(a-b);  // This will output -10

	console.log(a+b); // This will output 30

	console.log(a*b); // this will output 200

	console.log(a/b); // this will output 0.5

Logical Operators

	console.log(a>b); // this would return false

	console.log(a<=b); // this would return false

typeof operator
 
	console.log(typeof a); // this returns number

	console.log(typeof (a<=b)); // this returns boolean

	var x;
	console.log(typeof x); // this will return undefined

	var x = [];
	console.log(typeof x); // this returns object

Boolean Logic (&&, || , !)  Operator

	var firstName = 'John';
	var age = 10;

	if (age < 13) {
	    console.log(firstName + ' is a boy.');
	}
	else if (age >= 13 && age < 20) {
	    console.log(firstName + ' is a teenager');
	}
	else if (age == 30 || age >=20 && age <30 ) {
	    console.log(firstName + ' is a young men');
	}
	else if (age > 30 && !(age > 100)) {
	    console.log(firstName + ' is a man');
	}
	else {
	    console.log('invalid age');
	}

Ternary Operator

	Similar to if else statement but can be written in a single line.

	var firstName = 'John';
	var age = 15;

	age >= 18 ? console.log(firstName + ' can drink bear'): console.log(firstName + ' can drink juice.');

	var drink = age >= 18 ? 'bear':'juice';
	console.log(firstName + ' can drink ' + drink);


--------------------------------------------------------------------------------------
 Operators - Associativity & Precedence
--------------------------------------------------------------------------------------

 Operator Precedence decides which operator will be parsed first in which Order.
 Operator with higher precedence becomes operands for lower precedence operator.

 If operator precedence is same the associativity determines which will be parsed first.
 it can be either left-to-right or right-to-left.

 console.log(3+4*5);  here * operator has higher prcedence over + hence it is parsed first. so the results 
                      becomes 3 + 20 = 23.

 console.log(a=b=5);  here = is used twice, since same prcedence associativity is used, = has right to left associativity,
                      so b=5 is parsed first and it is assigned to a, which is then output to console log.
 console.log('all ok');

--------------------------------------------------------------------------------------
 Operators - Tricks
--------------------------------------------------------------------------------------

So if the left hand operand is true its value is used else right side operand will be used.

	const userInput = '';
	const name = userInput||'Sanjeev';
	console.log(name); // this will log 'Sanjeev'

	const userInput = 'Aparna';
	const name = userInput||'Sanjeev';
	console.log(name); // this will log 'Aparna'

So if the left hand operand is true then right hand operand value is used, else left side operand is used.

	const userInput = '';
	const name = userInput && 'Sanjeev';
	console.log(name); // this will log ''

	const userInput = 'Aparna';
	const name = userInput && 'Sanjeev';
	console.log(name); // this will log 'Sanjeev'

!! is used as Double Bang operator, to get the actual truthy/falsy value.

	const userInput = 'Sanjeev';
	const isValidInput = !!userInput;
	console.log(isValidInput); // this will log true

--------------------------------------------------------------------------------------
 Statements and Expressions
--------------------------------------------------------------------------------------

Anything that returns something that can be assigned to variable then its an expression.

	var whatDoYouDo = function(job, firstName){
		switch (job) {
			case 'teacher':
				return firstName + ' teaches kids';
			case 'driver':
				return firstName + ' drives a car';
			case 'designer':
				return firstName + ' designes websites';
			default:
				return firstName + ' does something else';
		}
	}

	console.log(whatDoYouDo('driver','Mark'));
	console.log(whatDoYouDo('dovtor','Jane'));
	console.log(whatDoYouDo('designer','John'));

Statements that perform actions that doesnot immediately produce result is a statement.
like a if else statment. rather it consoles undefined.

	if(true){console.log(23);}

--------------------------------------------------------------------------------------
 Loops
--------------------------------------------------------------------------------------

There are below loops:

for loop		-	Used with counter variable to run a fixed number of time.
for-of loop		-	Used with Arrays to loop through all array elements.
for-in loop		-	Used with Objects to loop through key value pair.
while loop		-	runs based on loop condition , loops runs until the loop condition is true. 
do while loop	-	runs atleast once, the loop condition is checked at the end.

break;		-	It stops a loop, steps out of the loop and process next line;

	const arrData = [1,2,3,4,5];
	for(let i=0;i<arrData.length;i++){
		if(arrData[i]>3){
			break;
		}
		console.log(arrData[i]);
	}

the above code will break once the item value is greater than 3.

continue;	-	It is used when there is need to skip somepart of code for some specfic index of a loop.

	const arrData = [1,2,3,4,5];
	for(let i=0;i<arrData.length;i++){
		if(arrData[i] === 3){
			continue;
		}
		console.log(arrData[i]);
	}

the above code will skip the item where value is 3, it will continue any next iteration.


Labeled Statement -	It helps break the parent loop from child look.

--------------------------------------------------------------------------------------
 Try, Catch, Finally and Throw
--------------------------------------------------------------------------------------

we can throw a custom error using throw.

	const inputValue = '23443sdfs';
	const parsedInput = parseInt(inputValue);

	if(!parsedInput){
		throw {message:'Input is invalid.'};
	}

we can use try catch and finally to capture any error and handle it to show better error message. and avoid code to stop execution abruptly.

	function getValue() {
		const inputValue = '23443sdfs';
		const parsedInput = parseInt(inputValue);

		if(!parsedInput){
			throw {message:'Input is invalid.'};
		}

		return parsedInput;
	}

	const getValueData = 0;

	try {
		getValueData = getValue();
	}
	catch(error){
		console.log(error);
		getValueData = 100;
	}

the above code will log an error message, the custom error message passed, and then set the value as default 100.

	try {
		getValueData = getValue();
	}
	catch(error){
		console.log(error);
		getValueData = 100;
	}
	finally {
		console.log('calculated user input and parsed it.');
	}

the finally block is executed no matter if error occured or not.

--------------------------------------------------------------------------------------
 Strict Mode
--------------------------------------------------------------------------------------

use with a string "use strict"; at the top of the code. 

	put this at the top of function to enable strict mode for that function.

	put at the top of script to enable strict mode for all the code in that script at once.

	javascript modules are in strict mode by default.

With strict mode variable must be declared with either a var, let or const keyword.

	userName = 'sanjeev';	// this will give an error not defined.

Varibale cannot be redclared in case var is used. let/const already restrict this in normal mode.

	var userName = 'sanjeev';
	var userName = 'rohit';		// this will give an error. reclared variable.

--------------------------------------------------------------------------------------
 Primitive vs Reference Types
--------------------------------------------------------------------------------------

There are the below primitive data in javascript

	String, Number, Boolean, null, undefined, Symbol

The value for primitive data is copied/passed by value. 

	let name = 'sanjeev';
	let newName = name;

	name = 'Rohit';
	console.log(name);			// this will output Rohit
	console.log(newName);		// this will output   sanjeev

As we can see in the above example thats intuitive that both have different value.

The object and arrays are the reference types.

In reference type the values are copied/passed by reference. when we create an array/object the value is actually created in the heap and the variable actually holds the pointer to memory address. and hence when we copy/pass the variable, the address is actually copied/passed.

	let arrData = [1,3,4,5];
	let newArray = arrData;

	arrData.push(2);
	console.log(arrData);		// this output [1,3,4,5,2]
	console.log(newArray);		// this output [1,3,4,5,2]

So in the above case both array value changes as both are pointing to the same memory address.

This also helps explain the below use cases where both variable with same object/array value created with different variable name doesnot match.

1. Comparision of arrays/objects

	let var1 = [1,2,3];
	let var2 = [1,2,3];

	console.log(var1===var2); 	// this output false
	console.log(var1==var2);	// this output false

	The above code returns false as both the variable actually holds the different memory address and hence are different.

2. Why constant allow additon/deletion of elements in object/arrays but doesnot allow reinitialization.

	const arrData = [1,2,3];
	arrData.push(4);

	console.log(arrData);	// this will output [1,2,3,4]

	arrData = [1,4,5,3];	// this will give a reinitialization error message.

	So why the push operation was successfull , because we changed the value in the heap an didn't actually change the value stored in constant.

	In case of assignining a new value, we are actually changing the meomory address stored in the constant , which is invalid.

--------------------------------------------------------------------------------------
 Garbage Collection
--------------------------------------------------------------------------------------

Javascript engine have a garbarge collector which periodically checks for memory heap, if it find any unused object (without any reference to it), it then removes any unused object.

	let arrData = [1,2,3];
	arrData = null;

When we set the above array to null, the memory location containing the value [1,2,3] is now not referenced by any variable, this is the candidate for garbage collector and will be removed by javascript engine in its periodic review of the memoery heap.

One use case where memory leaks are created is the usage of anonymous function binding to an event listener. such eventlistner bind same function multiple times in case the addEvenListener is called multiple times. Garbage collector in such case cannot detect it to be removed.

garbage collector not only looks for derefrenced objects but also for those objects which are no longer used even if not derefrenced explicitly.

--------------------------------------------------------------------------------------
 Functions
--------------------------------------------------------------------------------------

Functions are objects.

Fuctions inside an object is called a method.

When Anonymous functions is used in event binding it should be bind once, binding an anonymous functions multiple times create memory leaks.

Anonymous functions can be given a name, this can be useful in debuging.

--------------------------------------------------------------------------------------
 Functions - Arrow Function
--------------------------------------------------------------------------------------

An arrow function has => sign as below 

	const add = (a,b) => {
		return a + b;
	}

In case it only has a single expression it can be written as below

	const add = (a,b) => a + b;

In case it only has 1 argument then

	const add = a => a + 2;

In case of no argument is passed then

	const add = () => 1 + 2;

--------------------------------------------------------------------------------------
 Functions - Parameters and Arguments
--------------------------------------------------------------------------------------

Default parameters

	const add = (a,b=2) => a + b;
	console.log(add(1));	// this will output 3, though we only pass one argument b uses the default value of 2

Rest Operator in function Arguments

	const add = (...numbers) => {
		let retval = 0;
		for(const num of numbers){
			retval  += num;
		}
		return retval;
	}

	console.log(add(1,3,3,4));			// log 11
	console.log(add(1,3,3,4,5,5));		// log 21

so with this we can pass n numbers of parameters and can then access with rest operator.

Rest operator can be used with other parameters

	const add = (a,b, ...numbers) => {// function body};
	
Argument keyword in function Arguments

	const add = function(){
		let retval = 0;
		for(const num of arguments){
			retval  += num;
		}
		return retval;
	}

	console.log(add(1,3,3,4));			// log 11
	console.log(add(1,3,3,4,5,5));		// log 21

before the introduction of rest operator in ES6, arguments was the method to handle such usecase. now the rest operator is the recomended way to do the same.

--------------------------------------------------------------------------------------
 Functions - Callback Function
--------------------------------------------------------------------------------------

We can actually pass function as an argument to other function, we have being unknowngly doing this while adding the event using the addEventListner

	someButtonControl.addEventListner('click',doAction);

In in the above code the doAction is the callback function.

--------------------------------------------------------------------------------------
 Functions - Using bind() 
--------------------------------------------------------------------------------------