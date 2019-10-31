

// ********************************************************
// Include Bootstrap
// ********************************************************

To use only CSS based Components add the below

<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">

The above CSS link should be add at the top of page under head section

To use Javascript based Components also add the JS parts as below

<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>

Popper JS is required for Dropdowns and Tooltips.

JQuery is to be added first , then the Popper and then the bootstrap JS.

The JS part should be added at the end, just before the body closing tag (This would help load the JS in at the end and not block the Page Render.)


Reboot is build upon normalise to reset browser defaults.

// ********************************************************
// Bootstrap files
// ********************************************************

// In case of source code downloaded. The dist folder files would have as below

bootstrap/
├── dist/
│   ├── css/
│   ├── bootstrap-grid.css
│   ├── bootstrap-grid.css.map
│   ├── bootstrap-grid.min.css
│   ├── bootstrap-grid.min.css.map
│   ├── bootstrap-reboot.css
│   ├── bootstrap-reboot.css.map
│   ├── bootstrap-reboot.min.css
│   ├── bootstrap-reboot.min.css.map
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   └── bootstrap.min.css.map
└── │── js/
│   ├── bootstrap.bundle.js
│   ├── bootstrap.bundle.js.map
│   ├── bootstrap.bundle.min.js
│   ├── bootstrap.bundle.min.js.map
│   ├── bootstrap.js
│   ├── bootstrap.js.map
│   ├── bootstrap.min.js
│   └── bootstrap.min.js.map
├── js/
└── scss/
// CSS

bootstrap.css or bootstrap.min.css can be used to include all features of bootstrap

bootstrap-grid.css or bootstrap-grid.min.css  can be used if only layout and utility features are required.

bootstrap-reboot.css or bootstrap-reboot.min.css can be used if only reboot settings are required.


// JS

bootstrap.bundle.js includes the popper.js but not the jquery files

bootstrap.js doesnot include the popper.js as well as the jquery files.

// scss

This folder contains all the sass source files



// ********************************************************
// Browser Support
// ********************************************************

Chrome >= 45
Firefox >= 38
Edge >= 12
Explorer >= 10
Safari >= 9
Android >= 4.4


// ********************************************************
// Customize Bootstrap with your own settings
// ********************************************************

use npm to customize the bootstrap variables

npm init

npm install bootstrap --save

This will add a node_modules under the current directory

now create a main.scss file and add the below code

$theme-colors: (
  "primary": #83249b,
  "danger": #da8581
);


//Bootrap imports (all at once)

@import "node_modules/bootstrap/scss/bootstrap";

Save this an use sass compiler on main.scss to generate a main.css file.

now use this main.css file to link in the html page. instead of the bootstrap cdn.

you will notice a change in the primary color and the danger color.

This way we can have our own Settings

For the above import to work the folder structure should be as below

your-project/
├── scss
│   └── custom.scss
└── node_modules/
    └── bootstrap
        ├── js
        └── scss

// ********************************************************
// Modify the Bootstrap source file and Recompile
// ********************************************************

1. Download and install node.js on the windows machine.
2. Download the bootstrap source files
3. Navigate to the bootstrap root folder (This is folder where dist folder exists, package.json file exists.)
4. use npm to install all dependencies

    npm install

    During the dependencies intall , there would be some errors about missing files, it will suggest to run npm fix audit.
    run it to remove erros and then continue.
5. Download and install Ruby
6. open cmd and run ridk install, and then reopen cmd
7. open cmd and go to the bootstrap root folder
    
    gem install bundler 
    
    and then reopen cmd
8. bundle install
    and then reopen cmd
9. gem install jekyll
    and then reopen cmd
10. Now do the required update in the files (scss / js)
11. To recompile, delete the dist folder which contains the compiled css and js files. and run the below command
    npm run dist / npm test
This will recompile the files, recreate the dist folder and the compiled css and js files as before, do look for any errors, 
if there are any erros the compiled files will not be created.
