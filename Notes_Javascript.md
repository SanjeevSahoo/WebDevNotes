
************************************************
			Notes on Javascript
************************************************

-------------------------------------------------------
 Script Declaration Inline or External File
-------------------------------------------------------

// // Scripts can be writen directly in the html page under the <script></script> tag

//  <html>
//     <head>
//         <script>
//             console.log('hello world!');
//         </script>
//     </head>
//     <body>
//         This is the body
//     </body>
// </html> 

// // The recomended method is to put the javascript in a seperaate file and link usihg the script tag at the end of body.

//  <html>
//     <head>
//     </head>
//     <body>
//         This is the body
//         <script scr="script.js"></script> 
//     </body>
// </html> 



-------------------------------------------------------
 Variable Declaration and Syntax
-------------------------------------------------------

// var firstName = 'John'; // declare a variable

// console.log(firstName ); // display in console

// var job ;  // decalre a variable without initializing with value

// console.log(job); // undefined means not defined.

// console.log(anotherjob) // this would give a compilation error not defined



-------------------------------------------------------
 Type of Datatypes
-------------------------------------------------------

// 6 type of primitive data types in javascript

// Number  - Values are actually floating number
// String  - set of characters
// Boolean - stores true or false
// undefined   - variable declared but undefined
// null    - variable not declared
// symbol  -  it can be used to define unique value , like a unique property or key.

// Javascript is a Dynamically Typed and Weakly Typed language

// There is no static typing in javascript

// typeof NaN is number

// typeof null is object        this is due to a bug in javascript which is not fixed due to legacy codes

// const x = +'123' // this will convert it to number.

// const x = '' + 123 // this will convert it to string.

-------------------------------------------------------
 Comments in Javascripts
-------------------------------------------------------

// // This is a single line comment

// // In the above data type declaration shows a muliline comment using /* */. Anything between this is a multi line comment.



-------------------------------------------------------
 Invalid Variable Names
-------------------------------------------------------

// var 3somevar = 3; // this is not a valid variable name (variable name cannot start with number)

// var &somevar = 'something'; // this is also invalid. (variable name cannot start with a special characters)

// var _somevar = 'valid'; // this is valid (_ and $ sign can be used to start a varaible name)

// var $somevar = 'valid with $ sign'; //this is valid

// var somevar&more = 'invlaid again'; // this is invalid (variable name cannot contain special characters)

// var some var = 'no space is invalid'; // this is invlaid

// // now again at this point the line not 51 (var 3somevar) would give error and the code doesnot interpret, nothing happens.  
// If a JavaScript file contains a syntax error, none of the code in the file will execute.

// ReferenceError   - when something is not defined.
// TypeError        - when variable is accessed as function.

// var someVar = 'recomended way to name a variable, '

// // the above is the way of nameing a variable, it should be camelCase.



// var function = 'this'; // this is invalid variable name, as the name is a reserved word.


// var if = 'this is invalid';

// var number = 'this is valid';

// var string = 'this is valid';

// var javascript = 'this is valid';

// var $ = 'this is valid';

// var undefined = 'this is valid';

// console.log(undefined);



-------------------------------------------------------
 Recomendated Variable Name 
-------------------------------------------------------

// camelCase - first letter small and then all starting letter as capitals
//             firstName, firstAndLastName, eBay, iPhone.

// PascalCase - similar to camelCase but the first letter should be caps.
//             FirstName, FirstAndLastName.

// snake_Case - similar to camelCase but the word seperator is _. starting letter is generally starts with lowercase,
//             but all letter can be either lower or upper case.
//             foo_bar, Hello_world, first_Name.


-------------------------------------------------------
 Declare multiple variables in same line
-------------------------------------------------------

// var firstName, job, isMarried ;

// firstName= 'John';
// job = 'teacher';
// isMarried=false;

// console.log(firstName + ' is a '+ job + ' and is he married?'+ isMarried);

-------------------------------------------------------
 Type Coercion
-------------------------------------------------------

// When conversion of value happens from one type to other (like string to number) automatically, its is called Type Coercion.
// When this happens Explicitly it is called Type Casting.

// Javascript is a Loosely typed language.

// Loosely typed language are those who donot stricly apply their laid down type rules , if a programmer breaks its rule.

// Strongly typed language are strict to it and it breaks the program, if any type rules are violated by the programmer.

// var myvalue = (5 == "5"); // this will log true , as == makes the javascript do type coercion.
// console.log(myvalue);

// var myvalue = (5 === "5"); // will log false, as === operator does not do coercion.
// console.log(myvalue);

// var myvalue = [] + "5"; // This will log 5, as part of coercion, the both will be converted into String and then + operator works as Concatination.
// console.log(myvalue);

// var myvalue = ['sdfs','ddd'] + "5"; // This will log sdfs, ddd5, as part of coercion, the both will be converted into String and then + operator works as Concatination.
// console.log(myvalue);


-------------------------------------------------------
 Variable Mutation
-------------------------------------------------------

// Now if same variable value is changed from say string to Number, without using the var keyword. the javascript automatically detects a type change,
// this is called variable Mutation.

// job = 24;
// console.log(job);


-------------------------------------------------------
 Alert and Prompt
-------------------------------------------------------

// Instead of using the console.log , we can use the alert() function to output the data to the user in form of an alert message on screen.

// alert(job);

// // Prompt allows us to actually take input from user. This can then be stored in a variable and used further.

// var somevar = prompt('enter your name?');
// alert('you entered...'+ somevar);

-------------------------------------------------------
 Operators
-------------------------------------------------------

// // Assignment Operators

// var a, b;
// a= 10;  // = is an assignment operator
// b= 20;

// // Math Operator

// console.log(a-b);  // This will output -10

// console.log(a+b); // This will output 30

// console.log(a*b); // this will output 200

// console.log(a/b); // this will output 0.5

// // Logical Operators

// console.log(a>b); // this would return false

// console.log(a<=b); // this would return false


// // typeof operator
 
// console.log(typeof a); // this returns number

// console.log(typeof (a<=b)); // this returns boolean

// var x;
// console.log(typeof x); // this will return undefined

// var x = [];
// console.log(typeof x); // this returns object



-------------------------------------------------------
 Operators - Associativity & Precedence
-------------------------------------------------------

// Operator Precedence decides which operator will be parsed first in which Order.
// Operator with higher precedence becomes operands for lower precedence operator.

// If operator precedence is same the associativity determines which will be parsed first.
// it can be either left-to-right or right-to-left.

// console.log(3+4*5); // here * operator has higher prcedence over + hence it is parsed first. so the results 
//                     // becomes 3 + 20 = 23.

// console.log(a=b=5); // here = is used twice, since same prcedence associativity is used, = has right to left associativity,
//                     // so b=5 is parsed first and it is assigned to a, which is then output to console log.
// console.log('all ok');


-------------------------------------------------------
 CHALLENGE 1
-------------------------------------------------------

// Check if Marks BMI is Greater than Johns

// var markWeight, markHeight, johnWeight, johnHeight;

// markWeight = prompt('Enter Marks Weight in Kgs');
// markHeight = prompt('Enter Marks Height in Meters');
// johnWeight = prompt('Enter Marks Weight in Kgs');
// johnHeight = prompt('Enter Marks Height in Meters');

// var markBMI, johnBMI;

// markBMI = markWeight/ (markHeight*markHeight);
// johnBMI = johnWeight/ (johnHeight*johnHeight);


// alert('Is Marks BMI ('+markBMI+') greater than John BMI ('+johnBMI+')?'+ (markBMI>johnBMI));

-------------------------------------------------------
 IF ELSE Statement
-------------------------------------------------------

// var firstName = 'John';
// var maritalStatus = 'Single';
// var isMarried = false;
// if (maritalStatus === 'Married') {
//     isMarried = true;    
// }
// else{
//     isMarried = false;
// }

// if (isMarried) {
//     console.log(firstName + ' is Married');
// }
// else{
//     console.log(firstName + ' is Single');
// }

-------------------------------------------------------
  Boolean Logic (&&, || , !)  Operator
-------------------------------------------------------

// var firstName = 'John';
// var age = 10;

// if (age < 13) {
//     console.log(firstName + ' is a boy.');
// }
// else if (age >= 13 && age < 20) {
//     console.log(firstName + ' is a teenager');
// }
// else if (age == 30 || age >=20 && age <30 ) {
//     console.log(firstName + ' is a young men');
// }
// else if (age > 30 && !(age > 100)) {
//     console.log(firstName + ' is a man');
// }
// else {
//     console.log('invalid age');
// }

-------------------------------------------------------
 Ternary Operator
-------------------------------------------------------

// Similar to if else statement but can be written in a single line.

// var firstName = 'John';
// var age = 15;

// age >= 18 ? console.log(firstName + ' can drink bear'): console.log(firstName + ' can drink juice.');

// var drink = age >= 18 ? 'bear':'juice';
// console.log(firstName + ' can drink ' + drink);



-------------------------------------------------------
 Switch Statement
-------------------------------------------------------

// var job = 'driver';

// switch (job){
//     case 'teacher':
//         console.log('Teaches how to code');
//         break;
//     case 'doctor':
//     case 'practioner':
//         console.log('Does operation');
//         break;
//     case 'driver':
//         console.log('drives me home');
//         break;
//     default:
//         console.log('unknown');
// }


// var age = 15;

// switch (true) {
//     case age < 13 :
//         console.log('boy');
//         break;
//     case age >=13 && age < 20:
//         console.log('teenager');
//         break;
//     case age >=20 && age <=30:
//         console.log('young man');
//         break;
//     case age >30 && age <=110:
//         console.log('old men');
//     default:
//         console.log('invalid age');
// }

-------------------------------------------------------
 Truthy and Falsy Values
-------------------------------------------------------

// undefined , null, 0, '', NaN  are the only values that are Falsy, rest all values are Truthy.

// var height;

// if(height){console.log('true');}    // height is undefined and hence no output

// height = 23;

// if(height){console.log('true');}    // height is 23 and hence output is true

// height = 0;

// if(height){console.log('true');}    // height is 0 and hence output is false, as 0 is falsy

// if(undefined){console.log('true');}     // undefined is falsy
// if(null){console.log('true');}     // null is falsy
// if(0){console.log('true');}     // 0 is falsy
// if(''){console.log('true');}     // '' is falsy
// if(NaN){console.log('true');}     // NaN is falsy

// if("somedata"){console.log('true');} // its true

// if(true) {console.log('true');}

// height = 0;
// if (height||height ===0){
//     console.log('true');
// }

// === is the equality operator which checks for value as well as type

// typeof can be used to check the type of variable.

-------------------------------------------------------
 CODING CHALLENGE 2
-------------------------------------------------------

// var scoreJohn = (233,211,189)/3;
// var scoreMark = (211,240,199)/3;
// var scoreSara = (211,240.225)/3;

// console.log(scoreJohn, scoreMark, scoreSara);

// if(scoreJohn > scoreMark && scoreJohn > scoreSara){
//     console.log('John wins with score of '+ scoreJohn);
// }
// else if (scoreMark > scoreJohn && scoreMark > scoreSara){
//     console.log('Mark wins with score of '+ scoreMark);
// }
// else if (scoreSara > scoreJohn && scoreSara > scoreMark){
//     console.log('Sara wins with score of '+ scoreSara);
// }
// else {
//     console.log('Its a Tie between one or more players');
// }

-------------------------------------------------------
 Functions
-------------------------------------------------------

// function calculateAge(birthyear){
//     return 2019-birthyear;
// }

// console.log(calculateAge(1989));
// console.log(calculateAge(1986));
// console.log(calculateAge(1993));  

// function yearUntilRetirement(year, firstName){
//     var age = calculateAge(year);
//     var retirementyear = 60-age;
//     if(retirementyear<=0){
//         console.log(firstName + ' has already retired');
//     }
//     else{
//         console.log(firstName + ' would retire in '+ retirementyear+ ' years');
//     }
// }

// yearUntilRetirement(1986,'Jane');
// yearUntilRetirement(1976,'Mark');
// yearUntilRetirement(1916,'Sara');



-------------------------------------------------------
 Functions Statements and Expressions
-------------------------------------------------------

// var whatDoYouDo = function(job, firstName){
//     switch (job) {
//         case 'teacher':
//             return firstName + ' teaches kids';
//         case 'driver':
//             return firstName + ' drives a car';
//         case 'designer':
//             return firstName + ' designes websites';
//         default:
//             return firstName + ' does something else';
//     }
// }

// console.log(whatDoYouDo('driver','Mark'));
// console.log(whatDoYouDo('dovtor','Jane'));
// console.log(whatDoYouDo('designer','John'));

// // anything tha returns something then its an expression.

// // statements that perform actions that doesnot immediately produce result is a statement.
// // like a if else statment. rather it consoles undefined.

// if(true){console.log(23);}

-------------------------------------------------------
 Arrays
-------------------------------------------------------

// Arrays are collections of variables , they can contain different datatypes.

// // initialized new array

// var names = ['John','Mark','Sara'];
// var years = new Array(1999, 2018, 2011);

// // Javascript array starts at index 0

// console.log(names[0]);      // gives item at index of 0
// console.log(names.length);  // length of an array

// // mutate array data

// names[1] = 'Krtika';
// names[names.length] = 'Aparna';
// console.log(names);

// // Array with different datatype

// var john = ['John', 'Smith', 1999, 'designer1', false];

// john.push('blue');  // add element to the end of the array
// john.unshift('Mr.');    // add element to the start of the array    

// console.log(john);

// john.pop(); // removes element from end of an array
// john.shift(); // removes element from start of an array

// console.log(john);

// // Find element in an array

// console.log(john.indexOf('blue'));  // indexOf finds the element in the array

// // if found it returns the index of the first occurence of the element
// // else it returns the value as -1

// var isDesigner = john.indexOf('designer') === -1? 'Not a Desinger':'Is a Designer';
// console.log('John '+ isDesigner);

-------------------------------------------------------
 ARRAYS - KEY THINGS TO NOTE
-------------------------------------------------------

// Array .length gives the item with highest index + 1 . This doesnot actually give the no of items.

// In arrays keys can aslo be added ,like the objects, but they dont show when we console it. because array only shows indexed properties, 
// since keys are non indexed properties, they are ignored.

// using [] with var will create an array

// using {} with var will create an object

// Array is indexed, while objects are unordered collection and hence cannot be sorted.

// var a = ['sd','sdf','sdsd'];
// console.log(typeof a);

// as can be seen above typeof Array is acctually an object.

// Sparse Array


// var b = [];
// b[2] = 2;
// console.log(b);

// Sparse Arrays are those which do not have contigious set of arrays starting from index 0, they have holes in between.

// Dense Array

// var a = [undefined, undefined , 2];
// console.log(a);

-------------------------------------------------------
 CODING CHALLENGE 3
-------------------------------------------------------

// var amount = [124,48,268];
// var tip = [0,0,0];
// var billamount = [0,0,0]

// function tipCalculator(netamount){
//     switch(true){
//         case netamount < 50:
//             return netamount * 0.2;
//         case netamount >= 50 && netamount < 200:
//             return netamount * 0.15;
//         default:
//             return netamount * 0.1;
//     }
// }

// console.log(tipCalculator(30));
// console.log(tipCalculator(60));
// console.log(tipCalculator(220));


// tip[0] = tipCalculator(amount[0]);
// tip[1] = tipCalculator(amount[1]);
// tip[2] = tipCalculator(amount[2]);

// billamount[0] = amount[0] + tip[0];
// billamount[1] = amount[1] + tip[1];
// billamount[2] = amount[2] + tip[2];


// console.log(amount);
// console.log(tip);
// console.log(billamount);


-------------------------------------------------------
 OBJECT AND PROPERTIES
-------------------------------------------------------

// // Object Literal

// var john = {
//     firstName : 'John',
//     lastName : 'Smith',
//     age : 28,
//     family : ['bob', 'sandy', 'mark'],
//     isMarried : false
// };

// console.log(john);

// console.log(john.firstName);

// console.log(john['lastName']);

// var x = 'age';

// console.log(john[x]);

// // new Object syntax

// var john = new Object();
// john.firstName = 'John';
// john.age = 29;
// john['lastName'] = 'Smith';

// console.log(john);



-------------------------------------------------------
 OBJECT AND METHODS
-------------------------------------------------------

// var john = {
//     firstName : 'John',
//     lastName : 'Smith',
//     birthYear : 1999,
//     family : ['bob', 'sandy', 'mark'],
//     isMarried : false,
//     calcAge: function(){
//         this.age = 2019-this.birthYear;
//     }
// };

// john.calcAge();
// console.log(john.firstName + ' age is '+ john.age);

// this is a special keyword, that resembles current object

-------------------------------------------------------
 CODING CHALLENGE 4
-------------------------------------------------------


// var john = {
//     firstName : 'john',
//     lastName : 'Smith',
//     mass : 69,
//     height: 1.78,
//     calcBMI : function(){
//         this.bmi = this.mass/(this.height * this.height);
//         return this.bmi;
//     }
// }

// var mark = {
//     firstName : 'Mark',
//     lastName : 'Fetcher',
//     mass : 68,
//     height: 1.68,
//     calcBMI : function(){
//         this.bmi = this.mass/(this.height * this.height);
//         return this.bmi;
//     }
// }

// john.calcBMI();
// mark.calcBMI();

// console.log(john,mark);

// switch(true){
//     case john.bmi>mark.bmi :
//         console.log('John bmi of '+john.bmi+'is greater than mark which is '+mark.bmi);
//         break;
//     case john.bmi<mark.bmi :
//         console.log('John bmi of '+john.bmi+'is less than mark which is '+mark.bmi);
//         break;
//     default:
//         console.log('Both John and Mark have same BmI of '+ john.bmi);
// }

-------------------------------------------------------
 LOOP AND ITERATION
-------------------------------------------------------

// for loop

// for (var i = 0; i<20; i++){
//     console.log(i);
// }

// var john = ['john', 'smith','designer', 28, 1999, 'married'];

// for (var i = 0; i<john.length;i++){
//     console.log(john[i]);
// }

// // while loop

// var i = 0;
// while(i<20){
//     console.log(i);
//     i++;
// }

// continue

// continue is used to continue the for loop increment statement the moment it incounter the continue statement 
//it stops executing the next statement and increments/decrements the loop variable. that is checks for the next iteratin


// for (var i = 0; i<john.length;i++){
    //     if(typeof john[i] === 'number'){continue;}
    //     console.log(john[i]);
    // }
    
// break
    
// the moment the loop incounters the break statement it stops the loop execution and breaks out of the loop

// var john = ['john', 'smith','designer', 28, 1999, 'married'];
// for (var i = 0; i<john.length;i++){
//     if(typeof john[i] === 'number'){break;}
//     console.log(john[i]);
// }

// loop backward

// var john = ['john', 'smith','designer', 28, 1999, 'married'];
// for (var i=john.length-1;i>=0;i--){
//     console.log(john[i]);
// }

-------------------------------------------------------
 CODING CHALLENGE 5
-------------------------------------------------------

// // part 1

// var john = {
//     name : 'John',
//     bill : [124, 48, 268, 180, 42],
//     tip : [],
//     finalbill : [],
//     calcTip : function (){
//         for (var i = 0; i < this.bill.length; i++){
//             switch(true){
//                 case this.bill[i] < 50:
//                     this.tip[i] = this.bill[i]*0.2;                    
//                     break;
//                 case this.bill[i] >= 50 && this.bill[i] < 200:
//                     this.tip[i] = this.bill[i]*0.15;
//                     break;
//                 default:
//                     this.tip[i] = this.bill[i]*0.1;
//             }
//             this.finalbill[i] = this.bill[i] + this.tip[i];
//         }
//     },

//     calAvgTip : function(){
//         this.calcTip();
//         var sumTips = 0;        
//         for (var i = 0; i < this.bill.length; i++){
//             sumTips += this.tip[i];
//         }
//         this.avgTips =  sumTips/this.bill.length;
//         return this.avgTips;
//     }
// };

// john.calcTip();
// console.log(john.tip, john.finalbill);


// // part 2

// var mark = {
//     name : 'Mark',
//     bill : [77, 375, 110, 45],
//     tip : [],
//     finalbill : [],
//     calcTip : function (){
//         for (var i = 0; i < this.bill.length; i++){
//             switch(true){
//                 case this.bill[i] < 100:
//                     this.tip[i] = this.bill[i]*0.2;                    
//                     break;
//                 case this.bill[i] >= 100 && this.bill[i] < 300:
//                     this.tip[i] = this.bill[i]*0.15;
//                     break;
//                 default:
//                     this.tip[i] = this.bill[i]*0.25;
//             }
//             this.finalbill[i] = this.bill[i] + this.tip[i];
//         }
//     },

//     calAvgTip : function(){
//         this.calcTip();
//         var sumTips = 0;        
//         for (var i = 0; i < this.bill.length; i++){
//             sumTips += this.tip[i];
//         }
//         this.avgTips =  sumTips/this.bill.length;
//         return this.avgTips;
//     }
// };

// var johnAvgTip = john.calAvgTip();
// var markAvgTip = mark.calAvgTip();

// if(johnAvgTip>markAvgTip){
//     console.log('John Average tip of '+ johnAvgTip+ ' is greater than Mark Average tip of '+ markAvgTip);
// }
// else if (johnAvgTip<markAvgTip){
//     console.log('John Average tip of '+ johnAvgTip+ ' is less than Mark Average tip of '+ markAvgTip);
// }
// else{
//     console.log('John and Mark both paid same amount of Tips');
// }

// console.log(john,mark);

-------------------------------------------------------
 JAVASCRIPT ENGINE
-------------------------------------------------------

// There are various javascript engines some are given below:

// 1. V8               -       Used by Chrome
// 2. Chakra           -       Used by Edge
// 3. SpiderMonkey    -       Used by Firefox
// 4. JavascriptCore   -       Used by Safari

// NodeJs by default runs on V8 Engine, but it also has compiled versions for Chakra and SpiderMonkey

// Some Javascript Engines for IOT - such as DuckTape.


-------------------------------------------------------
 JAVASCRIPT ENGINE - How it Works
-------------------------------------------------------

// Source Code -> 
//             Parser ->
//                 AST (Abstract Syntax Tree) ->
//                                     Baseline Complier ->
//                                                     Machine Code
//                                     Optimizing Complier ->
//                                                     Optimized Machine Code ->
//                                                                 Machine Code

-------------------------------------------------------
 EXECUTION CONTEXT
-------------------------------------------------------

// Global Execution Context

/* 

Execution context can be thought of as the space where our code runs. 

any code that is not inside the function is run under the global execution context.

for each function a new execution context is created. as such any subsecuent context created are added to the execution stack.

STACK = LIFO
QUEUE = FIFO

we can think of a executuon context as an object. 

The global executuon context is attached to a global object. which in a  browser is the window object.

any variable and functions declared in global context is attached to the window object.

*/


// var x = 21;
// console.log(x);

// function a(){
//     var x = 22;
//     console.log(x);
//     b();
// }

// function b(){
//     var x = 23;
//     console.log(x);
//     c();
// }

// function c(){
//     var x = 24;
//     console.log(x);    
// }

// a();

// in the above codes there are separate exection context created for the functions a, b, c, 
// they all stack over the global context, the moment the a function is called at the bottom.

-------------------------------------------------------
 EXECUTION CONTEXT DETAILS
-------------------------------------------------------

// Execution Context Object has 3 properties

// 1. Variable Object          - This holds all function declaratins, Arguments, and Variables declarations in the context.
// 2. Scope Chain              - This holds the variable object of current context and all parent contexts.
// 3. This Variable            - This hold the invoking object, it is set once the code enters the execution Static.
                                // In case of a regular function call this points to the global oject (window), while in a method call
                                // it points to the calling Object.

// Now difference between a method and a function is  that

// any function that is a property of any object is called a method, while anything that is not is called a function.

// technically all functions are actually methods, because they would either have been explicitly attached to a object 
// or implicitly attached to a global object.

/*

Javascript code runs in 2 phases.

1. Creation Phase:
    -> Variable Object is created
    -> Scope Chain is created
    -> This variable is determined
2. Execution Phase.
    -> Code is run in this phase, variables are defined.

    

-------------------------------------------------------
// VARIABLE SCOPE
-------------------------------------------------------