
************************************************
				Notes on Angular8
************************************************


1. Installation
    
   a. Install Node JS
   b. Install Angular globally using the NPM 
        
      npm install -g @angular/cli    
    
2. Creating a New Project
  
   ng new my-app
    
3. Compile and Build, using 

   ng build

4. Compile and run using

   ng serve --open
   
5. File Structure

   a. package.json 
      
      The npm package dependency file.
      
   b. angular.json
   
      The file that contains refrence to the styles and scripts being used.
      
   c. src/main.ts 
   
      The main file called when app is executed. It sets environment and boot load the App Module
      
   d. src/app.module.ts
   
      This file is called from the main file, This file that contains reference to all the components, 
      Each component is registered here, all the  angular modules are loaded here.
      
   e. src/app.component.ts
   
      This is the default component/root component file. all other components are chained inside this component.
      Each component will have one or more of the files below:
      
      i.    app.component.css       - This contains the component css.
      ii.   app.component.html      - This contains the component template.
      iii.  app.component.spec.ts   - This is for Testing the component.
      iv.   app.component.ts        - This is the brain of the component, all component logic resides here.
      
   f. index.html
   
	  This is main html file that is called, every component is displayed inside this, this is the only page that is loaded.
	  
	  
6. Creating New Component

	ng generate component my-new-component
	
	This creates a component named "my-new-component" and registers in the app.module.ts file.
	
	Component by default has the below code
	
	import { Component, OnInit } from '@angular/core';
	
	@Component({
	  selector: 'app-shopping-list',
	  templateUrl: './shopping-list.component.html',
	  styleUrls: ['./shopping-list.component.css']
	})
	
	export class ShoppingListComponent implements OnInit {
	  constructor() { }

	  ngOnInit() {
	  }
	}

7. Data Binding
	
	a. String Interpolation
	
	b. Property Binding
	
	c. Event Binding
	
	d. Two way data binding using ngModel.
	
8. Using FormsModule for two way data binding. This forms module must be imported in the app module.

9. Directives

	a. ngIf is a Structural directive, used to show a element based on a condition.
	
	b. ngStyle directive can be used to add style to an element
	
	c. ngClass directive can be used to add a class to an element based on a condition.
	
	d. ngFor drective is used to list a group of data.
	
10. For debugging 
	
	a. Install the Augury Chrome extension.  
		This will list all the Components and its properties.

	b. Using Source maps while debugging, to debug the Typescript codes directly in the browsers.

11. Custom Property Binding

	@Input Decorator can be used to mark a property as DOM property of that Component.	

	This helps Parent Components to access the exposed property. That is set the property in the Parent Component Template file.
	
	@Input('AliasName') can be used to all an alias to the Property.	
	
12.	Custom Event Binding

	@Output Decorator is similar to the @Input Decorator, the output is used to Emit Child Events to the Parent Component.
	
	Output can also have an alias.
	
13. View Encapsulation in Angular Components.

	Styles created in a component is applied to that component only, 
	they are not shared to other component by default.
	
	This is managed by angular by  applying a auto genreated attribute to each element within a component.
	The styles are then based on that attribute.
	
	This emulates a Shadow Dom feature which is not supported by all browsers.
	
	This can be overidden using the encapsulation property in the Component selector section.
	
	Using the ViewEncapsulation None property. Once overiden ,the styles are applied globally.
	
14. Using Local Reference 
	
	Instead of Two way data binding to get the Input value field data local refrence can be used.
	
	Local reference can be directly used in the Typescript code and passed to the component function as a parameter.
	
15. ViewChild Decorator 

	@ViewChild() can be used to access the element marked with local reference name in the HTML Element
	
	

