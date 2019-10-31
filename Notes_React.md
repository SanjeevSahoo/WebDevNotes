
************************************************
				Notes on React	
************************************************


1. ES6+ Features
	
	a.	let and const, they cannot be 2 variable with same name with let in same lexical scope
		and with const in same scope. const variable can be mutated but not be assigned.
	
	b.	primitive types are copied by value.
	
	c.	object and array are copied by reference.
	
	d.	... is called spread operator, used to either split an array/object to a new array.
		or as rest to merge function parameters into a single array.
		
		const arrData = [1,2,3];
		const newData = [...arrData, 3, 4];
		console.log(newData);
		
		function someFunc(...args){
			console.log(args);
		}
		
		someFunc('someval', [1, 2, 3]);
		
	e.	export & imports
		
		i)	default export
			
			export default <function  name>
		
			import newname from pathofmodule
			
		ii)	import types (named imports)
		
			import {somename} from pathsomemodule;
			
			import {somename, somenewname} from pathsomemodule;
		
		iii)import all 
		
			import * as somename from pathsomemodule;
			
	f.	Arrow functions
	
		const getLength = ()=>{ return somedata.length};
		
		console.log(arrdata.map(item => item.length));
		
		in arrow function for single parameter the () can be omited.
		in case of single line the {} can be removed.
	
	g.	classes
	
		class Person{
			constructor(somename){
				this.name = somename;
			}
			
			printName = ()=>{
				console.log(this.name);
			}
		}
		
		const objperson = new Person('Sanjeev');
		objperson.printName(); // this will output sanjeev
		
	h.	classes inheritence
	
		class human {
			gender = 'male';			
		}

		class Person{
			constructor(somename, gender){
				this.name = somename;
				this.gender = gender;
			}
			
			printName = ()=>{
				console.log(this.name, this.gender);
			}
		}
		
		const objperson = new Person('Sanjeev','male');
		objperson.printName(); // this will output sanjeev
		
	i.	destructuring array/object
		
		const arrData = [1,2,3];
		const [num1, num2] = arrData;
		console.log(num1, num2);
		
		calling arrow function with destructuring argument
		
		const printName = ({name}) => name;

		console.log(printName({name: 'Max', age: 28}));

2. Create a react app using create-react-app

	create-react-app is a build chain used for creating single page react app. It has dependency over nodejs for the build process. we can use yarn or npm as package manager.

		npm install create-react-app -g 

	to install the via npm globally.

	to create a new app use the command below:

		create-react-app my-app

	this will create a new react app named my-app.

3. JSX means javascript xml

	It is used in react to make react elements.

	It looks similar to HTML. It is like a template, They are rendered by react to actual HTML elements in the DOM.

	JSX uses camelCase attribute names instead of the HTML lowercase attributes. 

	JSX allows creating dynamic html content by allows embedded javascript expressions inside it.

4.	React Components

	a. 	Class based components

			import React, { Component } from 'react';

			class App extends Component {
				render() {
					return (
					<div className="App">
						<h1>This is the Root Component</h1>
						<Person name="Sanjeev" age="32" />
						<Person name="Aparna" age="26" />
						<Person name="Kritika" age="1.5" />
					</div>
					);
				}
			}

	b. 	Functional Components

			import React from 'react';

			const person = (props) => {
				return <p>I am {props.name} and my age is {props.age} years.</p>
			}

			export default person;

5.	Add Dynamic Content

	Dynamic content can be added using a javascript expression inside {} curly braces.

		return <p>Current Date is {(new Date()).toDateString()}</p>

6.	Props

	Props can be used to send properties/attributes from UI to the Component class/function.

	all the properties are by default accesible as a parameters in the component class.

	Class based component

		this.props.name

	in class based component no need to pass the props they are available by default.

	Function based component

		const person = (props) => {
			return <p>I am {props.name} and my age is {props.age} years.</p>
		}

7.	Element Children

		<Person name="Kritika" age="1.5" >She is a Child</Person>

	here any thing inside the closing person tag is child elements for the components

	this can be accessed by using props.children property 

	Adjecent Elements in the Component class JSX , must be wrapped inside a parent element.

		return (
			<div>
				<p>I am {props.name} and my age is {props.age} years.</p>
				<p>{props.children}</p>
			</div>
		)

	they must also be returned inside a paranthesis ().

8.	States

	Class based Component

		state = {
			persons: [
				{ name: 'Sanjeev', age: 29 },
				{ name: 'Aparna', age: 25 },
				{ name: 'Kritika', age: 1.5 }
			]
		}

		switchNameHandler = () => {
			this.state.persons.splice(2, 1, { name: 'Kritika', age: 22 });
			this.setState({
				persons: [...this.state.persons]
			});
		}

	Functional Component using useState Hooks

		const [personState, setPersonState] = useState({
			persons: [
				{ name: 'Sanjeev', age: 29 },
				{ name: 'Aparna', age: 25 },
				{ name: 'Kritika', age: 1.5 }
			]
		});

	useState hook returns 2 object, one the state variable defined and the other a setState function to set the variable.

	here we are using destructuring to get the 2 objects.

		const switchNameHandler = () => {
			personState.persons.splice(2, 1, { name: 'Kritika', age: 22 });
			setPersonState({
				persons: [...personState.persons]
			});
		}

	the above is used to set the State.

9.	Passing Method by reference to different components

	Add a new property to like the name and age property to the component in the parent component call.

		for (const [index, value] of personState.persons.entries()) {
			items.push(<Person id={index} name={value.name} age={value.age} click={switchNameHandler.bind(this, 'Max!!')} />)
		}

	then access it in the child component class using the props object and attach to the onClick event

		const person = (props) => {
			return (
				<div>
					<p onClick={props.click}>I am {props.name} and my age is {props.age} years.</p>
					<p>{props.children}</p>
				</div>
			)
		}

10.	Two way data binding

		const textChangedHandler = (event) => {
			personState.persons.splice(2, 1, { name: event.target.value, age: 22 });
			setPersonState({
			persons: [...personState.persons]
			});
		}

	This creates an event, pass it using the propeties on Component. then in the component class access it
	and attach it to the change event

		const person = (props) => {
			return (
				<div>
					<p onClick={props.click}>I am {props.name} and my age is {props.age} years.</p>
					<p>{props.children}</p>
					<input type="text" onChange={props.changed} value={props.name} />
				</div>
			)
		}
	The value property is here used to set the current state of the object

11.	Add Style with Extenal CSS

	Similar to App.css that is added by default we can add a new css for the Person component with name Person.css and import it in the Person component class file

	Any Style added as such is globally applicable to all the component.

12.	Add Inline CSS for binding specific to the Component

	Inline style can be used but there are restrictions like adding a hover styles

	The below code adds a style

		const style = {
			backgroundColor:'green',
			border: '1px solid red',
			padding: '8px',
			color:'white'
		}

		return (
			<div className="App">
			<h1>This is the Root Component</h1>
			<button style={style} onClick={()=>switchNameHandler('Maxmillan!!')}>Switch Name</button>
			{items}
			</div>
		);

	Inline sytle are scoped to the respective component , unlike the external css file being added using the import which is globally applicable.
	
13.	Toggle Component Conditionally

		return (
			<div className="App">
			<h1>This is the Root Component</h1>
			<button style={style} onClick={()=>switchNameHandler('Maxmillan!!')}>Switch Name</button>
			<button style={style} onClick={toggleNameHandler}>Toggle Display</button>
			{(toggleState.toggleValue ? items : null)}
			</div>
		);

	here the ternary operation can be used to display or hide the element.

	The above way works but is not the prefered way. The toggle check should be outside the return

		if(toggleState.toggleValue){
			for (const [index, value] of personState.persons.entries()) {
			items.push(<Person id={index} name={value.name} age={value.age} click={switchNameHandler.bind(this, 'Max!!')} changed = {textChangedHandler} />)
			}
		}

14.	Update State in immutable ways

		const deleteNameHandler = (index) => {    
			const persons = [...personState.persons];   
			persons.splice(index,1);
			setPersonState({
			persons: persons
			});    
		}

	here the persons is copied in a new array using the spread operator and then the index of items passed to the delete handler is taken and removed

15.	Lists

		if(toggleState.toggleValue){
			for (const [index, value] of personState.persons.entries()) {
				items.push(<Person id={index} name={value.name} age={value.age} click={switchNameHandler.bind(this, 'Max!!')} changed = {textChangedHandler} />)
			}
		}

	we have already used list as shown above either using for loop or map.

	while creating list , the component used inside the list must have a unique key property.

		personState.persons.map((person,index)=>{
			return items.push(<Person key={person.id} name={person.name} age={person.age} click={deleteNameHandler.bind(this,index)} changed = {textChangedHandler} />)
		}); 

	As shown  above the key is added .
	The key is required for react to render specific list item in case of any change, if not provided the app will work, but in such case react have to rerender the complete list, now this can have performance issue in case of long list.

16. Updating Specific Item only

	After the id being used to identify an item we can use the same to update the item for which the text is being changed

		const textChangedHandler = (event, id) => {
			const persons = [...personState.persons]    
			const personIndex = persons.findIndex(person=>person.id===id);
			const person = {...personState.persons[personIndex]};
			person.name = event.target.value;
			persons.splice(personIndex,1, person);
			setPersonState({
			persons: persons
			});
		}
	