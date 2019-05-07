#### Transpilation With Babel ####

1. Install *Node.js* from <https://nodejs.org/es/>

2. Create a directory *"BabelJS"* where we will place our modules and locate inside the folder.

  ~~~
  mkdir BabelJS
  cd BabelJS
  ~~~

3. Create a __package.json__. 
  Run `npm ini`.

  Set the *name* and *description* properties. The other propierties you can leave blank.
    
    ~~~
    name : example-babel.
    description : Use Babel to transpile JavaScript ES6 to ES5.
    ~~~
    
4. Create a directory *src* to copy your __code ES6__ inside.

  `mkdir src`

5. Install the packages:

  Run to install the Babel command line package.
  `npm install babel-cli -D`

  Run to install the Babel preset environment package.
  `npm install babel-preset-env -D`


  You can run to install all the packages at the same time.

  `npm i --save-dev babel-core babel-cli babel-preset-env babel-preset-es2015 -D`

  *-D* flag instructs npm to add each package to a property called devDependencies in package.json

  If you run `npm install` you can install all the package listed in desDependencies.


  --save-dev is used to save the package for development purpose. Example: unit tests, minification..
  --save is used to save the package required for the application to run.
  babel-core is Babel compiler core.
  babel-cli is Babel command line Babel tools.
  babel-env is a Babel preset that compiles ES2015+ down to ES5 by automatically determining the Babel plugins and polyfills you need based on your targeted browser or runtime environments.
  babel-preset-es2015 is a Babel preset for all es2015 plugins.

6. Create the file __.babelrc.__ To do this.
  - Create an archive txt.
  - Rename the archive. Run rename new.txt .babelrc

7. Inside the archive .babelrc add an object that specifies the preset:

  We can use
  
  ```javascript
  {
    "presets": ["es2015"]
  }
  ```
  
  or we can indicate “env” to use *babel-env*
   
  ```javascript
  {
    "presets": ["env"]
  }
  ```
  
8. Configure the property script inside package.json. This property contains an object "test". Below the tehs add the object "build"
   
  ```javascript
  "scripts": {
    "build": "babel src -d dist"
  }
  ```

  __babel__ — The Babel command call responsible for transpiling code.
  
  __src__ — Instructs Babel to transpile all JavaScript code inside the src directory.
  
  __-d__ — Instructs Babel to write the transpiled code to a directory.
  
  __lib__ — Babel writes the transpiled code to a directory called lib.

9. Transpile the ES6+ code to lib using the build command.
  
  `npm run build`
