
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

Some time between 1996 and 1997, Netscape took JavaScript to the Ecma standards organization to carve out and maintain a specification for the language to enable other browser vendors to implement based on the work they had done. The Ecma Technical Committee 39 (better known as TC39) was created to continue to evolve the language, eventually releasing ECMA-262 Ed.1 in June 1997. ECMAScript is name of the official standard with JavaScript being the most well-known implementation of the standard. ActionScript (Macromedia) and JScript (Microsoft) are examples of other implementations.

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
 Javascript Runtime Environment
--------------------------------------------------------------------------------------

Javascript Engine runs inside some kind of environment, be it browser or nodejs. This provides some additonal features that the environment exposes via its API.

JRE is responsible for making JavaScript asynchronous. It is the reason JavaScript is able to add event listeners and make HTTP requests asynchronously

JRE is just like a container which consists of the following components:
	
	JS Engine
	Web API
	Callback Queue or message queue
	Event Table
	Event loop

Web API contains the Event Listeners, Ajax Call, and Timeout methods. 

Web APIs are not part of the JS engine but they are part of the JavaScript Runtime Environment which is provided by the browser. JavaScript just provides us with a mechanism to access these API’s. As Web APIs are browser specific, they may vary from browser to browser.

Event Table is a table data structure to store the asynchronous methods which need to be executed when some event occurs.

Callback queue follows FIFO, any event callback function is added to this queue. 

Methods are executed neither in the event table nor in the event queue. They are executed by the JavaScript engine, only if it is present in the ECS. So, for the execution of any method, we need to move that method from the callback queue to the execution context stack. This is what the event loop does

Event loop continuously checks if the execution context stack is empty and if there are any messages in the event queue. It will move the method from the callback queue to ECS only when the execution context stack is empty.

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
 First Class functions
--------------------------------------------------------------------------------------

A programming language is said to have First-class functions when functions in that language are treated like any other variable. For example, in such a language, a function can be passed as an argument to other functions, can be returned by another function and can be assigned as a value to a variable

--------------------------------------------------------------------------------------
 Higher Order functions
--------------------------------------------------------------------------------------

A higher order function is a function that takes a function as an argument, or returns a function.

Higher order function is in contrast to first order functions, which don’t take a function as an argument or return a function as output.

For examples .map() and .filter(). Both of them take a function as an argument. They're both higher order functions.

--------------------------------------------------------------------------------------
 Programming Paradigms
--------------------------------------------------------------------------------------

The term programming paradigm is the style or way of thinking about and approaching problems. Simply, it is a style of programming. There can be more than one type programming paradigms. 

	Imperative Programming

		Procedural 
		Object Oriented
		Parallel

	Declarative Programming

		Functional
		Logical
		Database Processing

https://medium.com/@darrion/what-is-meant-by-programming-paradigms-9b965a62b7c7

Funtional Programming

The Functional programming paradigm is mainly used to perform mathematical functions without changing the state. This paradigm can contain concepts like: pure functions, higher order functions and recursion(functions that call itself)

Logical Programming

It can be termed as abstract model of computation. It would solve logical problems like puzzles, series etc. In logic programming we have a knowledge base which we know before and along with the question and knowledge base which is given to machine, it produces result. In normal programming languages, such concept of knowledge base is not available but while using the concept of artificial intelligence, machine learning we have some models like Perception model which is using the same mechanism.

--------------------------------------------------------------------------------------
 Imperative vs Declarative Programming Styles
--------------------------------------------------------------------------------------

Imperative programming is like how you do something, and declarative programming is more like what you do.

An imperative approach (HOW): “I see that table located under the Gone Fishin’ sign is empty. My husband and I are going to walk over there and sit down.”

A declarative approach (WHAT): “Table for two, please.”

The imperative approach is concerned with HOW you’re actually going to get a seat. You need to list out the steps to be able to show HOW you’re going to get a table. The declarative approach is more concerned with WHAT you want, a table for two.

	Imperative: C, C++, Java

	Declarative: SQL, HTML

	(Can Be) Mix: JavaScript, C#, Python

Example of Imperative Code:

	function double (arr) {
		let results = []
		for (let i = 0; i < arr.length; i++){
			results.push(arr[i] * 2)
		}
		return results
	}

Example of Same Code in Declarative Form:

	function double (arr) {
		return arr.map((item) => item * 2)
	}

https://tylermcginnis.com/imperative-vs-declarative-programming/


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
 Javascript has Dynamic type checking
--------------------------------------------------------------------------------------

Dynamic type checking means the type of a varaible is checked at runtime, so you can assign different type of data to same variable at different parts of your code, the type will checked at the time any operation is done on it.

In static typed language, you have to explicitly specify the type of any variable.

So in dynamically typed language any error if there is found at runtime, while in static typed language it gives error at compile time.

Javascript is weakly typed/ dynamic typed language.

to implement static type checking in javascript we need to use a type checker, like Flow or Typescript.

With Flow, the below code will give an error during transpilling (transpiling is required as the annonated strings are not supported by vanilla javascript.)

	function concat(a: string, b: string) {
		return a + b;
	}

	let string1: string = "hello"
	let string2: number = 42

	concat(string1, string2)

Dynamic Typed use case

	function fn(x) {
		if(!x) {
			return false;
		}
	
		x += 1;
		return x;
	}

	fn(2)			// 3
	fn("hello") 	// "hello1"
	fn(_ => 3) 		// "_ => 31"
	fn({prop:1}) 	// "[object Object]1"

So the output depends on the type of data passed as an argument to the function.

https://blog.bitsrc.io/static-type-checking-vs-dynamic-type-checking-in-javascript-13643f4952a9


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

	it returns -1 if not found an > -1 if found

We can also used includes() which returns a true if found and false it not found. This works on primitive values only

if found it returns the index of the first occurence of the element else it returns the value as -1

	var isDesigner = john.indexOf('designer') === -1? 'Not a Desinger':'Is a Designer';
	console.log('John '+ isDesigner);

in case of array with multiple objects , like [{name:'Sanjeev'},{name:'Rohan'}] we cannot use indexOf but find()

	const persons = [{name:'Sanjeev'},{name:'Rohan'}];
	const currPerson = persons.find(person=>person.name==='Sanjeev');
	console.log(currPerson);		// this would log {name:"Sanjeev"}

in case of array index is required for a given value

	const currPersonIndex = persons.findIndex(person=>person.name==='Sanjeev');
	console.log(currPersonIndex);		// this would log index of {name:"Sanjeev"} that is 0

push() and pop() has better performance then unshift() and shift()

splice()	- takes 3 parameters, start Index, the no of items to delete or replace and the actual item or items to replace.

	someArray.splice(0)					- deletes all items from array.
	someArray.splice(1,0,'new item')	- adds new item after index 1
	someArray.splice(1,1, 'new item')	- replaces the item at index 1
	someArray.splice(0,1)	 `			- deletes 1 item from index 1.
	someArray.spliace(-2,1)				- deletes 1 item starting backwards, 2 last element.

slice()		- takes 2 arguments from Index to to index. returns a slice of the array.

	someArray.slice(0,3)				- returns items from 0 to 3, it actually returns a copy of array and not a refrence.
	someArray.slice(-3,-1)				- returns from 3rd last item to the last item.

concat()	- returns an array contains items from first array and the passwed arrays.

map()		- runs a loop for each item , we can then do some operation on each item .

sort()		- sorts an array by comparing them as string, its ascending order. it also takes a sorting function 

	const arrData = [2,335,35,5,3,4,344];
	const sortedData = arrData.sort((a,b)=>{
		if(a>b){
			return 1;
		}
		else if(a===b){
			return 0;
		}
		else {
			return -1;
		}
	});
	console.log(sortedData);	// this will log (7) [344, 335, 35, 5, 4, 3, 2]

reverse()	- sorted arrays can be ordered in descending order using this function

filter()	- filter functions takes a filter function and returns any filtered data

	const filteredData = arrData.filter(item=>item>6);
	console.log(filteredData);		// this will log (3) [344, 335, 35]

reduce()	- it takes 2 arguments, one reducer function and the inital value.

	const sum = filteredData.reduce((prevValue, currValue)=> prevValue + currValue,0);
	console.log(sum);			// this logs 714

split()		- it splits a string in array 

	const commaSeperatedString = 'This, is , the string, for, comma';
	console.log(commaSeperatedString.split(','));		// (5) ["This", " is ", " the string", " for", " comma"]

join()		- it joins a array in string seperated by , by default.

	const arrData = ['this','is','value'];
	console.log(arrData.join());	// this,is,value
	console.log(arrData.join(' '));	// this is value

...			- Spread operator can be used to actually spread and array / object.

	const arrData = [{name:'sanjeev',age:31},{name:'rohan',age:33}];
	const copiedArray = [...arrData];	// this copies the actual refrence so, changing the array length has no effect but changing the referenced items value will affect both original and copied array. copying via slice() is better 

[item1, item2]	- array destructuring is when array items are destructured to extract individual items.

	const arrStrings = ['sanjeev','sahoo',32,'Designer'];
	const [startName, lastName, age, job] = arrStrings;
	console.log(startName);			// logs 'sanjeev

...			- Rest operator is same as spread, the type depends on how we use it.

	const arrStrings = ['sanjeev','sahoo',32,'Designer'];
	const [startName, lastName, ...othersValues] = arrStrings;

	here the ... works as the rest operator as it takes all other items and stores it in othersValues.

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

When creating array with Array() constructor, the below to be noted

	const someArray = new Array(1,5);
	console.log(someArray);		// logs (2)[1,5]

	const againArray = new Array(5);
	console.log(againArray); 	// logs (5)[empty x 5]

so in case a single argument is passed then creates the number of empty items in the array.

some other methods to create arrays

	const numbers = new Array.of(1,2);

	const splitString = Array.from('Sanjeev');
	console.log(splitString);			// ['S','a','n','j','e','e','v']

Array.from() takes a iterable object and converts it into an array. 

array functions can also being changed after each other.

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

delete john.age;		// this removes the property from an object

john['new value'] = 'sdf'	// this is posiible to have key with space using the square bracket notation

john[1.5] = 'hello'		// key can be number also

const newkey = 'somekey';
john[newkey] = 'data';	// newkey is a variable

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

Object.assign() can be used to copy an object to new object. it can also be used to merge objects

	const person = {name:'sanjeev',age:30};
	const newPerson = Object.assign({},person);

Object Destructuring is little different from array destructuring as the order is not guranteed in Objects. so while in array destructuring we can use an custom name of destructured item. In Object we have to use the key name only.

	cont person = {name:'sanjeev', age:32, job:'developer'};
	const {name, age} = person;

we can also give a alias name like this

	const {name:userName, age} = person;

here userName can now be used instead of name.


--------------------------------------------------------------------------------------
 Iterable and Iterator Object
--------------------------------------------------------------------------------------

There is a iterable and iterator protocol that helps any object to be converted to an iterable object. such that for-of can be used on it.

	let range = {
		from: 1,
		to: 5
	};

	range[Symbol.iterator] = function() {

		// ...it returns the iterator object:
		// 2. Onward, for..of works only with this iterator, asking it for next values
		return {
			current: this.from,
			last: this.to,

			// 3. next() is called on each iteration by the for..of loop
			next() {
				// 4. it should return the value as an object {done:.., value :...}
				if (this.current <= this.last) {
					return { done: false, value: this.current++ };
				} else {
					return { done: true };
				}
			}
		};
	};

	// now it works!
	for (let num of range) {
		alert(num); // 1, then 2, 3, 4, 5
	}

In the above code an non iterable range object is converted to a iterable object beacuse it now has a method with name Symbol.iterator and it returns a iterator object which must have a next() method to get the next value.

The iterator object must be like {done: Boolean, value: any}

Of course, Arrays are iterable. But there are many other built-in objects, that are iterable as well. For instance, strings are also iterable.

--------------------------------------------------------------------------------------
 Array Like Object
--------------------------------------------------------------------------------------

An Object which has a length property of a non-negative Integer, and usually some indexed properties

	var ao1 = {length: 0},                     // like []
    ao2 = {0: 'foo', 5: 'bar', length: 6}; // like ["foo", undefined × 4, "bar"]

They are called array like but not an array because 

It's not constructed by Array or with an Array literal [], and so (usually) won't inherit from Array.prototype. The length property will not usually automatically update either

Now we can use slice() function or Array.from() to convert to an Array.

--------------------------------------------------------------------------------------
 Sets
--------------------------------------------------------------------------------------

Similar to Arrays, they allow store unique sets of primitive types /array or object. they cannot be accessed based on index.
Sets order is not guranteed.

	const ids = new Set([1,2,3,4,5]);
	ids.add(6) 	// this add 6

	ids.add(2)	// this will not add as duplicate value, but wil not give any error.

	ids.delete(3)	// this will delete 3

entries() returns a iterable object. which can be used in a for-of loops, this returns the value twice(to match the map object).

	for(let id of ids.entries()){
		console.log(id);
	}

	// this outputs as below
	
	(2) [1, 1]
 	(2) [2, 2]
 	(2) [4, 4]
 	(2) [5, 5]
 	(2) [6, 6]

values() can be used to get object with single value.

	for(let id of ids.entries()){
		console.log(id);
	}

	// this outputs as below
	
	1
	2
	3
	4
	5
	6

WeakSet() is used to created sets that can have the items get garbage collected once the item refrence is removed.

	let person1 = {name:'sanjeev'};
	const personData = new WeakSet(person1);

	person1 = null;

	console.log(personData);

--------------------------------------------------------------------------------------
 Maps
--------------------------------------------------------------------------------------

similar to sets, but ordred is guranteed and access by keys. keys cannot be duplicate

	const person1 = {name:'sanjeev'};
	const person2 = {name:'rohit'};

	const personData = new Map([[person1,['date':'yesterday', price:200]]]);
	console.log(personData);

	personData.set(person2, [{date:'now',price:223}]);

	console.log(personData);

we can set an array like using push() in array we use set() in maps.

we use get() to get the value based on key

	console.log(personData.get(person2));

we can also use .entries() and .values() as earlier to get the values, we can also use .keys() to get the keys only

WeakMap() is used to created maps that can have they keys get garbage collected once the key refrence is removed.

	let person1 = {name:'sanjeev'};
	const personData = new WeakMap([[person1, 'some text']]);

	person1 = null;

	console.log(personData);

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

Array.forEach()		- This can be used to loop through and array. The advantage over for-of is both item and index are avilable at once.

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

Since functions are also objects so they also have various methods. bind() is one such method that is used to prepare a function.

bind() helps pass argument / rather say bind an argument while attaching it as callback function/simply passing it as an argument to other function to be invoked afterwards.

	const computeData = (operation, a, b, alertFunction)=> {
		let val = 0;
		if(operation ==='ADD'){
			val = a + b;
		}
		else if(operation === 'SUBS'){
			val = a - b;
		}
		alertFunction(val);
	}

	function alertFunc(message, val){
		console.log(message + ', computed data : '+ val);
	}
	
	computeData('ADD', 1,2 ,alertFunc.bind(this,'Addition Operation'));			// Addition Operation 3
	computeData('SUBS', 3,2 ,alertFunc.bind(this,'Substraction Operation'));		// Substraction Operation 1

The above example alertFunc is passed with a bind message.
Note the order of bind parameter, it must be first.

--------------------------------------------------------------------------------------
 WHATWG - Group that Standardizes Browser API's
--------------------------------------------------------------------------------------

https://whatwg.org/

--------------------------------------------------------------------------------------
 DOM API
--------------------------------------------------------------------------------------

DOM stands for Document Object model. 

JavaScript is a "hosted language". The browser as host environment exposes this DOM API to your JS code automatically.

When the browser parsed the HTML document, it forms a tree structure containing the object representation of all the HTML Tags.

D	-	Document, since it is representation of the HTML Document
O	-	Oject, since the elements are represented as object.
M	-	Model, the way the objects are arranged , the structure of the object, which is a tree structure.

DOM is the browsers internal programmatic representation of the web page. This representation can be manipulated by javascript.

DOM API is the way browsers allows javascript code to manipulate this DOM at runtime. So this way the actually page on the server doesnot change but the parsed structure in the browser can be changed.

document object which is the top most node, also called the root node, all other nodes comes under this.

window object represents the window that contains the document, for each tab in a browser a new window object is created.

all properties and methods under window object can directly accessed in the code, so instead of window.document.querySelector we can simply write document.querySelector.

--------------------------------------------------------------------------------------
 DOM API - Element vs Node
--------------------------------------------------------------------------------------

All objects inside a DOM is a node. there are various kind of nodes (element node, document node, text node etc.)

So, Element node is a type of node that represents the HTML tag, It has properties such as id and class.

document.getElementById() returns a single HTML element, hence it an element node.

docment.getElementByClassName() can return muliple object, hence it returns NodeList (prior to HTML5) with HTML5 now it returns HTMLCollection.

--------------------------------------------------------------------------------------
 DOM API - querySelectorAll is non-live 
--------------------------------------------------------------------------------------

	document.getElementsByClassName()
	document.getElementsByTagName()
	document.getElementsByName()

The above methods are used to query the document, the result returned are in sync with the DOM and hence called live collection, in case new nodes are added the same would be available in the HTMLElementCollection list already queried.

	document.querySelectorAll()

The document.querySelectorAll() is a non live list, this is an snapshot of the collection at the time the query executed. This is because the querySelector can be used to selector very complex css selector. now to keep track of all the changes and updating will have performance issue. because it will have to be reevaluated periodically.

	document.querySelectorAll() returns as NodeList

	document.getElementsByClassName() returns a HTMLCollection

NodeList is are mostly non live list, HTMLCollection is mostly live list. there are exceptions also
NodeList contains all nodes, Element, Text , comment etc. while HTMLCollection only hold element nodes.

Array.from() is used to conver a iterable object to array.

we can use this over HTMLCollection or NodeList to get an array. But converting to array makes the list non live.

--------------------------------------------------------------------------------------
 DOM API - property vs attribute
--------------------------------------------------------------------------------------

We define attrubute in out html document, when the same is parsed to created the DOM element node, the attributes are converted to the corresponding properties and can be accessed as the part the element node property. 

The property name can be same / different from attribute name.

like background-color is an attribute and backgroundColor is the property.

For a given DOM node object, properties are the properties of that object, and attributes are the elements of the attributes property of that object.

--------------------------------------------------------------------------------------
 DOM API - Traversing DOM
--------------------------------------------------------------------------------------

Child 			- Direct Children
Decsendents		- Children/ Children of Children
Parent			- Direct Parent
Ancestors		- Parent/ Parent of Parent

Parent Selectors

	parentNode		- Selects direct parent Node
	parentElement	- Selects direct the parent Node if its also an element node else returns null

Ancestors Selectors

	closest			- Selects the parent element based on the css selector

Child Selectors

	childNodes			- Selects all direct child nodes
	children			- Selects all direct child elements. only availble if the current object is an element	
	firstChild			- first child node
	firstElementChild	- first child element 
	lastChild			- last child node
	lastElementChild	- last child element

Sibling Selectors

	previousSibling			- previous sibling same parent node
	previousElementSibling	- previous sibling same parent Element
	nextSibling				- next sibling same parent node
	nextElementSibling		- next sibling same parent element

Descendent Selectors

	querySelector		- This can also be used to find children. instead of document.querySelector we can use it with the item 	itself.

--------------------------------------------------------------------------------------
 DOM API - Traversing DOM vs Query Selector
--------------------------------------------------------------------------------------	

Query Selector is touch slower then Traversing DOM with ether nodes or element selectors. But in case of complex selectors/ nested selectors the Query Selector is the preferred way, as it would be easier to read and maintain.


--------------------------------------------------------------------------------------
 DOM API - Adding Style
--------------------------------------------------------------------------------------	

We can use the style property to set inline style

	someElement.style.color = "white";
	someElement.style.backgroundColor = "#fff";

We can use the className property to modify the class names of a given element

	someElement.className = "redClass blueClass";

We can also use the classList propety to add, delete, replace or toggle a class.

	someElement.classList.add('redClass');
	someElement.classList.remove('blueClass');

Adding class using the classList property is the recommended method, as it can handle complex cases.

--------------------------------------------------------------------------------------
 DOM API - Adding Element to DOM
--------------------------------------------------------------------------------------	

innerHTML				- adds as a string of html markup. this rerenders and is performance heavy.

insetAdjacentHTML()		- it takes 2 parameters, position and the html markup to be added.

		beforebegin		- it adds the markup before the current element
		afterbegin		- it adds before the first element
		beforeend		- it adds at the end
		afterend		- it adds after the current element

		beforebegin and afterend works only if the current element has a parent element.

insertAdjacentElement()	- it takes 2 parameters, position and the element node.

appendChild()			- adds an element node created using document.createElement() to the end

append()				- adds an element node or a dom string to the end of the current node.

prepend()				- add to the top of the current element.

before()				- adds before the current selected node

after()					- adds after the current selected node

cloneNode(false)		- clones an element node with or wihouth child nodes based on a boolean parameter.

replaceWith()			- this actually replace the current node with the passed node.

replaceChild()			- this replaces the child node with new node passed

--------------------------------------------------------------------------------------
 DOM API - Removing Element from DOM
--------------------------------------------------------------------------------------	

	element.parentElement.removeChild(element);

The above method is well supported by all browsers.

	element.remove():

The above method is also supported by all browsers (except IE)

--------------------------------------------------------------------------------------
 this keyword
--------------------------------------------------------------------------------------	

1. this keyword inside an object method

	const person = {
		name:'sanjeev', 
		age:32, 
		job:'developer',
		getFormattedData(){
			return this
		}
	};

	console.log(person.getFormattedData());		// logs the person object
	let {getFormattedData} = person;
	console.log(getFormattedData);				// logs the window object

	so this refers to the calling object.

		person.getFormattedData()	, the calling object is person.

	in second destructured way

		getFormattedData()			, we directly call it which is equivalent to window.getFormattedData(). so calling object is window

	lets use the bind() method to pass this of our choice.

		getFormattedData = getFormattedData.bind(person);
		getFormattedData();			// now we have passed the person object as this using bind so, this now points to person

	lets use the call() method to pass this of our choice. the difference is bind() makes the function ready for future use, call() and apply() is used when the function needs to be executed immediately.

		getFormattedData.call(movie);		// this can take n number of arguments

		getFormattedData.apply(movie);		// this takes only 2 arguments.


2. this when function is attached to event listener

	in such case the this referes to the event object who triggered that event.  Browser defines this in such case.

	for anonymous function

		const showData = function() {
			return this;
		}

		someButton.addEventListener('click',showData);

	on click the this will return the button object.

	for arrow function

		const showData = () => {
			return this;
		}

	on click the this will be the windows object, as arrow function doesnot set their own this. 

3. this inside an arrow function

	function declared with function keyword / the method shortcut, will bind their own this. which will depend on who called that function

		function showData(){
			console.log(this);
		}

		showData();		// logs window object

	in strict mode, this will return as undefined with the function being declared with function keyword.

		'use strict';

		function showData(){
			console.log(this);
		}

		showData();		// logs undefined		

	in strict mode, if explicityly called with window.showData() then it will again log window.

		'use strict';

		function showData(){
			console.log(this);
		}

		window.showData();	// logs window object

	in strict mode/ normal mode, with arrow function the behaviour will be same and this will be outside the arrow function

		'use strict';

		const showData = ()=>{
			console.log(this);
		}

		showData();		// logs window object.

	inside object, now this keyword will point to what it was outside the arrow function. here it is nested inside another function which is declared with function keyword

		const person = {
			name:'sanjeev', 
			age:30,
			getAge : function(){
				const getThis = () => {
					return this;
				}
				return getThis();
			}
		};

		console.log(person.getAge());		// logs the person object.

	changing the getAge() function to arrow function will behave as below

		const person = {
			name:'sanjeev', 
			age:30,
			getAge : () => {
				const getThis = () => {
					return this;
				}
				return getThis();
			}
		};

		console.log(person.getAge());		// logs the windows object.

	lets nest normal function inside the arrow function.

		const person = {
			name:'sanjeev', 
			age:30,
			getAge : () => {
				const getThis = function(){
					return this;
				}
				return getThis();
			}
		};

		console.log(person.getAge());	// this logs window

	here the function inside the getAge() is not a method but a function and hence it is same if we declare it outside the object. an how the this binds for a function outside an object, it binds to the global window object.

	now if we use the strict mode it will make it clear.

		'use strict';

		const person = {
			name:'sanjeev', 
			age:30,
			getAge : () => {
				const getThis = function(){
					return this;
				}
				return getThis();
			}
		};

		console.log(person.getAge());	// this again logs undefined.

4. when method is passed to another object

		const person = { 
			name: 'Max',
			greet() {
				console.log(this.name);
			}
		};	
		
		const anotherPerson = { name: 'Manuel' }; // does NOT have a built-in greet method!
	
		anotherPerson.sayHi = person.greet; // greet is NOT called here, it's just assigned to a new property/ method on the "anotherPerson" object
		
		anotherPerson.sayHi(); // logs 'Manuel'

	lets pass a normal function then

		const person = { 
			name: 'Max',
			greet() {
				return function(){console.log(this.name)};
			}
		};

		const anotherPerson = { name: 'Manuel' }; // does NOT have a built-in greet method!
		
		anotherPerson.sayHi = person.greet(); // greet is called here and returned function is stored in "anotherPerson" object
		
		anotherPerson.sayHi(); // logs 'Manuel' 
	
	since function is normal function it binds its own this, this is what called the function which is anotherPerson.

	let pass a arrow function then

		const person = { 
			name: 'Max',
			greet() {
				return ()=>{console.log(this.name)};
			}
		};
		
		function outGreet(){console.log(this.name)};

		const anotherPerson = { name: 'Manuel' }; // does NOT have a built-in greet method!
		
		anotherPerson.sayHi = person.greet(); // greet is NOT called here, it's just assigned to a new property/ method on the "anotherPerson" object
		
		anotherPerson.sayHi(); // logs 'Max' 

	this is happening due to closure, since in the arrow function this is as it outside the function and any scope is also passed, now three are 2 names one in global scope and local scope, the local scope is being used.

--------------------------------------------------------------------------------------
 Getter and Setter
--------------------------------------------------------------------------------------	

Normal properties used in the object are called data properties, while getter and setter are called accesor property.

Benifit of using getter and setter over data properties:

1. we can validate the data before being set.
2. we can process the data, before being set. like uppercase the input or concat something.
3. we can set read only property.
4. we can set private data property which can be set and get using the encapsulated setter and getter properties.
5. instead of explicitly calling a method for data assign and retreival, the setter and getter methods are called implicitly, and hence help inforce data integrity.

all private data properties have a prefixed _ character to ressemble it being a private property. this is rather a recommendation and not a syntax.

we can create setter and getter either using the set and get keyword, or using the object.defineProperty method.

	let person = {
		_name: 'Johnson Ogwuru',
		_age: 137,

		set age(newage){
			if(typeof newage === 'number'){
				this._age = newage;				
			}
			else{
				console.log ('Invalid input');
			}
		}
  	};

in the above code the age method has a preceding set keyword, which makes the method a accessor property. now we can use the property as normal data property.

	person.age = 38;

note here we used the age not the _age property.

we can also have a getter function using the get keyword.

	get age(){
      return this._age
    }

to get the age we can use the getter as normal property is used.

	console.log(person.age);	// this will output the value of _age data property.

so the actual _age property is encapsulated by using the age accesor property.

with the defineProperty method we can actually create a property after it has been initialized.

	var o = {a: 0};

	Object.defineProperty(o, 'b', { get: function() { return this.a + 1; } });

	console.log(o.b) // Runs the getter, which yields a + 1 (which is 1)

--------------------------------------------------------------------------------------
 Class 
--------------------------------------------------------------------------------------	

Class can be used to create a blueprint for object which have similar structure, it helps in code reusablity. Class are not hoisted like function declaration.

	class Product {
		title = "DEFAULT";
		imageURL;
		description;
		price;
	}

	const obj = new Product();

class is created with class keyword, the class contains fields, these fields are converted to properties when actual objects are created using the new keyword.

we can assign property by . notation like obj.title = "Game CD". but there is a better way using class contructor method.

	class Product {
		contructor(title, imageURL, description, price) {
			this.title = title;
			this.price = price;
		}
	}

	const obj1 = new Product('Game CD', 2003);
	const obj2 = new Product('Movie CD', 1003);

--------------------------------------------------------------------------------------
 Class	- Static Method & Properties
--------------------------------------------------------------------------------------	

static methods and properties can be accessed without creating an instance of the class.

	class App {
		static cart;
		
		static init(){
			const shop = new Shop();
			shop.render();
			this.cart = shop.cart;
		}
	}

So here we are creating a static method called init() within class App.

	App.init();

to call we simply use the class name and called the method, without creating any object.

--------------------------------------------------------------------------------------
 Class	- Inheritance
--------------------------------------------------------------------------------------	

classes can have more generic versions which have common method and attributes. we can then extend the class to create more specific version of it.
This way we can have more reusable code and structure. Extended class have access to all the parent classes properties and methods.

	class Animal {
		constructor(name) {
			this.speed = 0;
			this.name = name;
		}
		run(speed) {
			this.speed += speed;
			alert(`${this.name} runs with speed ${this.speed}.`);
		}
		stop() {
			this.speed = 0;
			alert(`${this.name} stands still.`);
		}
	}

	let animal = new Animal("My animal");

here we are creating and Animal class which we can then inherit to create other animals (more specific animal class).

	class Rabbit extends Animal {
		hide() {
			console.log(`${this.name} hides!`);
		}
	}

	let rabbit = new Rabbit("White Rabbit");

	rabbit.run(5); // White Rabbit runs with speed 5.
	rabbit.hide(); // White Rabbit hides!

here we have created a Rabbit class which inherits the Animal class, and hence the rabbit object created can access both the hide() method which is declared in the Rabbit class but also the run() method in Animal class

we can also use the super() method that actually calls the constructor method of the parent class. since both child class and the parent class can have their own constructor methods. this is way that allows to call a parents constructor in the child contructor. 

One thing to note is its recomended to call the super() before any other statement in the child contructor method.

In case the child class doesnot have its own constructor method then the parent class constructor method is implicitly called. this is the reason why in the above code the "White Rabbit" name is assined to the name property . though we didn't specify this in the Rabbit class.

But in case the child class has its own constructor mehtod than that is called and the parent class constructor is overriden. this creates a problem that the parent class constructor is never called. hence super() should be used.

	class Rabbit extends Animal {
		constructor(name, color){
			super(name);
			this.color = color;
		}
		hide() {
			console.log(`${this.name} of ${this.color} color hides!`);
		}
	}

	let rabbit = new Rabbit("Rabbit","White");

here we have created constructor method for the child class with a new parameter of color. now we call the parent constructor with super() with name as an argument.


--------------------------------------------------------------------------------------
 Class	- Private Property
--------------------------------------------------------------------------------------	

private properties can be defined via prepending any field inside the class with a # symbol. only fields can be marked as private not the property. 

private properties are useful when the property is only used inside the class and cannot be/should not be accessible outside the classs.

	class Rectangle {
		#height = 0;
		width;
		constructor(height, width) {    
			this.#height = height;
			this.width = width;
		}
	}

here width is a normal field while the height is a private field.

Before the private property feature came , there is also a pseudo private property we have looked earlier. here any private property is marked with a prpended _ sign. this symbolyses that the property is private. It is rather a convention than a feature and the private property declared as such is accessible outside the class. it just a flag that the property is private and should not be modified outside the class.

	class User {
		constructor() {
			this._role = 'admin';
		}
	}
	
	// or directly in an object
	
	const product = {
		_internalId: 'abc1'
	};

--------------------------------------------------------------------------------------
 Class	- instanceof operator
--------------------------------------------------------------------------------------	

It is used to test if a given object is an instance of a class.


	class Animal {
		constructor(name) {
			this.speed = 0;
			this.name = name;
		}
		run(speed) {
			this.speed += speed;
			alert(`${this.name} runs with speed ${this.speed}.`);
		}
		stop() {
			this.speed = 0;
			alert(`${this.name} stands still.`);
		}
	}

	let animal = new Animal("My animal");
	let someObj = new Object();

	console.log(animal instanceof Animal)		// returns true.

	console.log(animal instanceof Object)		// returns true.

	console.log(someObj instanceof Animal)		// returns false.

It actually tests whether the given Object appears in the protorype chain or not. This is the reason that animal instanceof Object returns true. Though the animal object is not directly an instanceof Object but is part of the prototype chain.


--------------------------------------------------------------------------------------
 Object Descriptor
--------------------------------------------------------------------------------------	

By default objects have key value pair. but there is more to it. They also have Descriptors/ Property Flags. They are automatically created, they are the meta information stored by the engine.

other than values we have 3 more flags, these are set to true by default but can be changed to have more control.

	writable – if true, the value can be changed, otherwise it’s read-only.

	enumerable – if true, then listed in loops, otherwise not listed.

	configurable – if true, the property can be deleted and these attributes can be modified, otherwise not.

we can view an object decriptors by using 

	Object.getOwnPropertyDescriptor(obj, propertyName)
	
This will get the Descriptor for a specific property

	let user = {
		name: "John"
	};

	let descriptor = Object.getOwnPropertyDescriptor(user, 'name');

	alert( JSON.stringify(descriptor, null, 2 ) );
	
	/* property descriptor:
	{
		"value": "John",
		"writable": true,
		"enumerable": true,
		"configurable": true
	}

for all descriptors at once use

	Object.getOwnPropertyDescriptors(Obj);

--------------------------------------------------------------------------------------
 Object Descriptor	- Make Non Writable Property
--------------------------------------------------------------------------------------

we can use the Object.defineProperty(obj, propertyName, propertyObject)

This can be used to not only define new object property but also edit existing property.

To make an object non writable do as below:

	let user = {
		name: "John"
	};

	Object.defineProperty(user, "name", {
	writable: false
	});

	user.name = "Pete";   	// Though this wont give an error but the value assignment will be ignorned.

	console.log(user.name)  // this will list John

--------------------------------------------------------------------------------------
 Object Descriptor	- Make Non Enumrable Property
--------------------------------------------------------------------------------------

Non Enumerable properties cannot be used inside a loop

By default, both our properties are listed:

	let user = {
		name: "John",
		toString() {
			return this.name;
		}
	};

	
	for (let key in user) alert(key); // name, toString

lets make the toString method Non enumerable.

	let user = {
		name: "John",
		toString() {
			return this.name;
		}
	};

	Object.defineProperty(user, "toString", {
		enumerable: false
	});

	for (let key in user) alert(key); // Now our toString disappears:

--------------------------------------------------------------------------------------
 Object Descriptor	- Make Non Configurable Property
--------------------------------------------------------------------------------------

The non-configurable flag (configurable:false) is sometimes preset for built-in objects and properties.

A non-configurable property can not be deleted.

For instance, Math.PI is non-writable, non-enumerable and non-configurable:

	let user = { };

	Object.defineProperty(user, "name", {
		value: "John",
		writable: false,
		configurable: false
	});

	
	Object.defineProperty(user, "name", {writable: true}); // This will give an error as property made configurable false can now cannot be deleted as well as udpated,

Property marked as configurable false, we can no longer delete as well as change the descriptors further.

--------------------------------------------------------------------------------------
 Object Descriptor	- Set at Globally for the Object
--------------------------------------------------------------------------------------

Property descriptors work at the level of individual properties.

There are also methods that limit access to the whole object:

	Object.preventExtensions(obj)

		Forbids the addition of new properties to the object.

	Object.seal(obj)
		
		Forbids adding/removing of properties. Sets configurable: false for all existing properties.

	Object.freeze(obj)
		
		Forbids adding/removing/changing of properties. Sets configurable: false, writable: false for all existing properties.

	And also there are tests for them:

	Object.isExtensible(obj)
		
		Returns false if adding properties is forbidden, otherwise true.

	Object.isSealed(obj)

		Returns true if adding/removing properties is forbidden, and all existing properties have configurable: false.

	Object.isFrozen(obj)
		
		Returns true if adding/removing/changing properties is forbidden, and all current properties are configurable: false, writable: false.

--------------------------------------------------------------------------------------
 Constructor Function
--------------------------------------------------------------------------------------

The regular {...} syntax allows to create one object. But often we need to create many similar objects, like multiple users or menu items and so on.

That can be done using constructor functions and the "new" operator.

Constructor functions technically are regular functions. There are two conventions though:

	They are named with capital letter first.
	They should be executed only with "new" operator.

	function User(name) {
		this.name = name;
		this.isAdmin = false;
	}

	let user = new User("Jack");

	alert(user.name); // Jack
	alert(user.isAdmin); // false

When a function is executed with new, it does the following steps:

	A new empty object is created and assigned to this.
	The function body executes. Usually it modifies this, adds new properties to it.
	The value of this is returned.

In other words, new User(...) does something like:

	function User(name) {
		// this = {};  (implicitly)

		// add properties to this
		this.name = name;
		this.isAdmin = false;

		// return this;  (implicitly)
	}

So let user = new User("Jack") gives the same result as:

	let user = {
		name: "Jack",
		isAdmin: false
	};

Now if we want to create other users, we can call new User("Ann"), new User("Alice") and so on. Much shorter than using literals every time, and also easy to read.

That’s the main purpose of constructors – to implement reusable object creation code.

Let’s note once again – technically, any function can be used as a constructor. That is: any function can be run with new, and it will execute the algorithm above. The “capital letter first” is a common agreement, to make it clear that a function is to be run with new.

Isnside a function, we can check whether it was called with new or without it, using a special new.target property.

It is empty for regular calls and equals the function if called with new:

	function User() {
		alert(new.target);
	}

	// without "new":
	User(); // undefined

	// with "new":
	new User(); // function User { ... }

Usually, constructors do not have a return statement. Their task is to write all necessary stuff into this, and it automatically becomes the result.

But if there is a return statement, then the rule is simple:

	If return is called with an object, then the object is returned instead of this.
	If return is called with a primitive, it’s ignored.
	In other words, return with an object returns that object, in all other cases this is returned.


--------------------------------------------------------------------------------------
 Constructor Function - Class Contructor (A Syntactical Sugar)
--------------------------------------------------------------------------------------

class in javascript are syntactical sugars, that means they donot introduce any new feature, but are just some gives an option to use nice syntax. So the same thing can be done with older methods.

	class Animal {
		constructor(name, type){
			this.name = name;
			this.type = type;			
		}	

		printSummary() {
			console.log(`The Animal is ${this.name} and its type is ${this.type}`);
		}
	}

	let tiger = new Animal('Tiger', 'Mammal');
	let snake = new Animal('Snake', 'Reptile');

The above class can be written using the contructor function.

	function Animal(name, type) {		
		this.name = name;
		this.type = type;
		
		Animal.prototype.printSummary = function() {
			console.log(`The Animal is ${this.name} and its type is ${this.type}`);
		}	
	}

	let tiger = new Animal('Tiger', 'Mammal');
	let snake = new Animal('Snake', 'Reptile');

But then there are more to class , there not just a syntactical sugar.

	First, a function created by class is labelled by a special internal property [[FunctionKind]]:"classConstructor". So it’s not entirely the same as creating it manually.

	And unlike a regular function, a class constructor must be called with new

	Also, a string representation of a class constructor in most JavaScript engines starts with the “class…”

	Class methods are non-enumerable. A class definition sets enumerable flag to false for all methods in the "prototype".

	That’s good, because if we for..in over an object, we usually don’t want its class methods.

	Classes always use strict. All code inside the class construct is automatically in strict mode.

--------------------------------------------------------------------------------------
 Prototype
--------------------------------------------------------------------------------------

The property [[Prototype]] is internal and hidden, but there are many ways to set it.

One of them is to use __proto__

	let animal = {
		eats: true
	};
	let rabbit = {
		jumps: true
	};

	rabbit.__proto__ = animal;

If we look for a property in rabbit, and it’s missing, JavaScript automatically takes it from animal.

	alert( rabbit.eats ); // true (**)
	alert( rabbit.jumps ); // true

There are only two limitations:

	The references can’t go in circles. JavaScript will throw an error if we try to assign __proto__ in a circle.	
	The value of __proto__ can be either an object or null. Other types are ignored.
	Also it may be obvious, but still: there can be only one [[Prototype]]. An object may not inherit from two others.

__proto__ is not the same as [[Prototype]]. That’s a getter/setter for it.

It exists for historical reasons. In modern language it is replaced with functions Object.getPrototypeOf/Object.setPrototypeOf that also get/set the prototype. 

difference between prototype property and __proto__ property:

	prototype property is used when new keyword is used to instantiate and new object from a function constructor. 
	
	we can also set the prototype object to a custom object. this property only takes a object and primitive type assigned will be ignored.

	Not all objects have this prototype property. only function object/ constructor function have this property.

	The default "prototype" is an object with the only property constructor that points back to the function itself.
	
		function Rabbit() {}
		
		alert( Rabbit.prototype.constructor == Rabbit ); // true

	__proto__ is what stores the prototype object which gets referenced from the function contructors prototype property.

	so to get an objects prototype object we actually use the __proto__ and to know what would be the prototype of the objects inhertited from this object we can used the prototype prototype property

When a function is created in JavaScript, the JavaScript engine adds a prototype property to the function. 
This prototype property is an object (called as prototype object) which has a constructor property by default. 

The constructor property points back to the function on which prototype object is a property. We can access the function’s prototype property using functionName.prototype.

prototype property of the function is an object (prototype object) with two properties:
	
	constructor property which points to Human function itself
	__proto__ property: We will discuss this while explaining inheritance in JavaScript

When an object is created in JavaScript, JavaScript engine adds a __proto__ property to the newly created object which is called dunder proto. dunder proto or __proto__ points to the prototype object of the constructor function.

As prototype object is an object, we can attach properties and methods to the prototype object. Thus, enabling all the objects created using the constructor function to share those properties and methods.

When we try to access a property of an object, JavaScript engines first tries to find the property on the object, if the property is present on the object it outputs its value. But, if the property is not present on the object then it tries to find the property on the prototype object or dunder proto of the object. If the property is found the value is returned else JavaScript engine tries to find the property on the dunder proto of the object. This chain continues until the dunder proto property is null. In these cases, the output will be undefined.

To solve the problems with the prototype and the problems with the constructor, we can combine both the constructor and function.
	
	Problem with the constructor function: Every object has its own instance of the function
	Problem with the prototype: Modifying a property using one object reflects the other object also
	
To solve both problems, we can define all the object-specific properties inside the constructor and all shared properties and methods inside the prototype

Object.prototype is end of prototype chain.

we can add static method to class or as property to a normal constructor function. such property is not part of the object prototype, but they are actually accesible via the object. notation as object property is accesed. they are nether copied to the child object created using the new keyword.

	class Animal{
		constructor(type,legs){
			this.type = type;
			this.legs = legs
			this.speed = function(){
				console.log(this.legs * 5);
			}
		}

		getLegs = function(){
			console.log(this.legs);
		}

		getType(){
			console.log(this.type);
		}
	}

	let objAn = new Animal('Cat',4);
	objAn.speed();
	objAn.getLegs();
	objAn.getType();

In the above code the methods speed(), getLegs() are copied to every object created, while the method using the shorthand syntax getType() is added to the prototype object and hence is only refereced in every object via the prototype object. This is equivalent to writing the below code using the function constructor.


	function Animal(type, legs){
		this.type = type;
		this.legs = legs;
		this.speed = function(){
			console.log(this.legs*5);
		}
		this.getLegs = function(){
			console.log(this.legs);
		}	
		
	}

	Animal.prototype.getType = function(){
		console.log(this.type);
	}

	let objAn = new Animal('Cat',4);
	objAn.speed();
	objAn.getLegs();
	objAn.getType();

--------------------------------------------------------------------------------------
 Prototype - setPrototypeOf() and getPrototypeOf(), Object.create()
--------------------------------------------------------------------------------------

using the __proto__ is an outdated way of accessing and updating the proto object. we can instead use the setPrototypeOf and getPrototypeOf method.

	let animal = {
		eats: true
	};

	// create a new object with animal as a prototype
	let rabbit = Object.create(animal);

	alert(rabbit.eats); // true

	alert(Object.getPrototypeOf(rabbit) === animal); // true

	Object.setPrototypeOf(rabbit, {}); // change the prototype of rabbit to {}

The Object.create() method creates a new object, using an existing object as the prototype of the newly created object.

	let animal = {
		eats: true
	};

	let rabbit = Object.create(animal, {
		jumps: {
			value: true
		}
	});

	alert(rabbit.jumps); // true

here the first argument is the object to be used as the prototype and second argument is the object descriptors.
