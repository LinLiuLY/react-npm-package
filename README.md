This is a exercise to get you familiar with npm.

# Prerequisite
- node

# Exercises
 - create a npm package
 
 ```bash
 mkdir yourpackage
 cd yourpackage
 npm init
 ```
 
 - install a thirdparty npm pacakge
 
 ```
 npm i first-n
 ```
 - uninstall the installed npm package
 
 ```
 npm un fist-n
 ```
 - install a thirdparty npm package as a dev dependency

 ```
 npm i validate-vat -D
 ```

 - install a thirdparty npm package as a dependency
 
 ```
 npm i diff-json -S
 ```

 - install a global package
 
 ```
 npm i grunt -g
 ```

 - add some code to your package
  
 ```
 echo "module.exports = 'Hello World'" > index.js
 ```
 - use your package inside another project without publishing it
 
 ```bash
 cd ..
 # Create a new folder
 mkdir test-yourpackage
 cd test-yourpackage
 
 # 
 npm link ../yourpackage
 
 echo "console.log(require('yourpackage'));" > index.js
 
 node index.js
 ```
 - change content in the `index.js` inside `yourpackage` and run `node index.js` inside `test-yourpackage`. You should see that the output is changed.
 
 - unlink `yourpackage` inside `test-yourpackage`
 
 ```bash
 npm unlink `yourpackage`
 ```
 
 and run `ls node_modules` to see if the linked package is gone
 
 
 - lock the version of your dependencies
 
 ```
 npm shrinkwrap
 ```
 and check the content of `npm-shrinkwrap.json` 
 
- create a new major version
 ```bash
 npm version major
 ```
 
- add a npm user
 
 ```
 npm adduser
 ```
 
- publish your package
 
 ```bash
 # run inside yourpackage
 npm publish .
 ```
 - use you published pacakge inside another project
 
 ```bash
 # run this inside test-yourpackage
 npm i yourpackage
 ```
 
- unpublish your package
 
 ```bash
 npm unpublish .
 ```
 and check it with `npm view yourpackage`

 ###
 The synopsis above loads the completions into your current shell. Adding it to your ~/.bashrc or ~/.zshrc will make the completions available everywhere:

 ```
npm completion >> ~/.bashrc
npm completion >> ~/.zshrc

 ```
