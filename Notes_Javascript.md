
*****************************************************************************************************
											Notes on Javascript
*****************************************************************************************************

-------------------------------------------------------
 History of Javascript
-------------------------------------------------------

"Brendan Eich" created Javascript, He developed the language in 10 days (May 1995) while working at Netscape Communication which later collaborated with Sun Microsystems (even before Brendan start working on the it.)

Although it was developed under the name "Mocha", the language was officially called "LiveScript" when it first shipped in beta releases of Netscape Navigator 2.0 in September 1995, but it was renamed JavaScript when it was deployed in the Netscape Navigator 2.0 beta 3 in December 1995.

Javascript was largely influenced by Java, Self and Scheme programming language.

Soon after release Javascript for Browser, it also introduced an implementation of the language for Server Side Scripting in Netscape Enterprise Server.

Since 1996, Microsoft IIS Server has supported microsofts server side javascript (JScript) in ASP and ASP.Net

Node.js was introduced in 2009 by "Ryan Dahl"

-------------------------------------------------------
 Javascript Versions and Release Cycle
-------------------------------------------------------

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

-------------------------------------------------------
 Javascript Specification 
-------------------------------------------------------

Javascript is also known as ECMAScript. Javascript version is often refered as ES5, ES6, ES7, or ESNext. 
ECMA Stands for European Computer Manufacturers Association. They are the one who manages the javascript specification / ECMA Specification.

ECMA Specification is how the javascript language should work, but doesnot gurantee its implementation. Its upto the browsers vendors to implement the same. or rather say the individual Javascript Engine.

Current ECMAScript Specification is ECMA - 262 URL below:

https://www.ecma-international.org/ecma-262/10.0/index.html

Actually there is a committee who looks after the Spec and adds any change. The committe is TC39.

TC39 committee meets 6 times every year to discuss on proposed changes in the spec.

-------------------------------------------------------
 Javascript Feature Addition
-------------------------------------------------------

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

-------------------------------------------------------
 Browser Support
-------------------------------------------------------

https://kangax.github.io/compat-table/es6/


-------------------------------------------------------
 Javascript Engine
-------------------------------------------------------

There are various javascript engines some are given below:

1. V8               -       Used by Chrome
2. Chakra           -       Used by Edge
3. SpiderMonkey    	-       Used by Firefox
4. JavascriptCore   -       Used by Safari

NodeJs by default runs on V8 Engine, but it also has compiled versions for Chakra and SpiderMonkey

Some Javascript Engines for IOT - such as DuckTape.


-------------------------------------------------------
 Javascript Engine (How it Works)
-------------------------------------------------------

Source Code -> 
            Parser ->
                AST (Abstract Syntax Tree) ->
                                    Baseline Complier ->
                                                    Machine Code
                                    Optimizing Complier ->
                                                    Optimized Machine Code ->
                                                                Machine Code


-------------------------------------------------------
 Variable Declaration and Syntax
-------------------------------------------------------

var firstName = 'John'; // declare a variable

console.log(firstName ); // display in console

var job ;  // decalre a variable without initializing with value

console.log(job); // undefined means not defined.

console.log(anotherjob) // this would give a compilation error not defined

-------------------------------------------------------
 Invalid Variable Names
-------------------------------------------------------

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

-------------------------------------------------------
 Recomendated Variable Name case is camelCase
-------------------------------------------------------

camelCase - 	first letter small and then all starting letter as capitals
            	firstName, firstAndLastName, eBay, iPhone.

PascalCase - 	similar to camelCase but the first letter should be caps.
             	FirstName, FirstAndLastName.

snake_Case -	similar to camelCase but the word seperator is _. 
				starting letter is generally starts with lowercase,
            	but all letter can be either lower or upper case.
            	foo_bar, Hello_world, first_Name.


-------------------------------------------------------
 Declare multiple variables in same line
-------------------------------------------------------

var firstName, job, isMarried ;

firstName= 'John';
job = 'teacher';
isMarried=false;

console.log(firstName + ' is a '+ job + ' and is he married?'+ isMarried);


-------------------------------------------------------
 Type of Datatypes
-------------------------------------------------------

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

-------------------------------------------------------
 Comments in Javascripts
-------------------------------------------------------

// This is a single line comment

Comment using /* */. Anything between this is a multi line comment.

-------------------------------------------------------
 Template Literals
-------------------------------------------------------

Back-ticks(`) can be used instead of Single Quotes(') or Double Quotes(") for string containation as below

	let name = 'Sanjeev'
	let age = 29;
	let someValue = 'My Name is ' + name + " and my age is " + age;

same can written with back-ticks, the advantage is it can be written with newline (output will appear with newline)

	let someValue = `My Name is 
		`+name+` and my age is ` + age;

using Template Literals. its even more easier.

	let someValue = `My Name is ${name} and my age is ${age}`;




