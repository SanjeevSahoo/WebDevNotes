
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

D	-	Document, sicne it is representation of the HTML Document
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