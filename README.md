---
tags: Web Development, Mosh, Youtube
---

# JavaScript

* **JavaScript:**
    * connect language and data format (JSON) ?more detail
    * text-based programming language that allows you to make web pages interactive.
    * Javascript engine(like spyder, v8).
    * 

#### [Crash Course](https://www.youtube.com/watch?v=W6NZfCO5SIk)

* Earlier, js was limited with browser(console) but now with node.js, it can be run outside the browser(can be used in Google Chrome console too). 
* Can be used for: frontend, backend or for full stack development
* Used by: netflix and wallmart
* Used in: mobile apps, real time networking apps, games and cmd tools
* node.js : is a js engine(called V8) embeded in c++ programme(provide 3rd party support for js)
* ECMA: is a international script specification followed by js!
* Use live server extention: To bind Visual studio with browser
* Script section: can be in body/head section, best(end in body section as no loading issue).
* To seperate js script file: `<script src= 'index.js'></script>`
* Using Node to run JS(cmd): open js file from terminal`$node index.js`
1. let name = 'Mosh'; 
    * var is nearest function scope
    * let has nearest block scope
2. Variable : 
    * dynamic(type can change later in code)
    * camel notation(firstName) & case sensitive
    * don't have float
    * undefined(declared but not initialised)
    * "null" is primitive type
    
```
const selectorName = 'fixed';
let person = {name: 'Mosh', age = 12}; //object 
Notation for properties : use dot or bracket
Array: 
    list in py(but object type in js)
    length is dynamic
    a[2] = 'green'(like dictionary in py)

function greet(){
    console.log('Hello' + 'World!');
    }
greet();
```





## [Detailed](https://www.youtube.com/watch?v=W6NZfCO5SIk)?

### **Introduction**:
ECMA6 introduced "symbol" primitive type(similar to enumeration)?
Analogy for undefined and null: intentionally choose to not to fill value.
Type coercion('==='): no automatic conversion as {10 == '10'} is true in JS
Empty string is evaluated as a false in boolean.
Object created without any class!, no class template, assign property dynamically and no access specifier.
Nested object:
```
var obj1 ={"p1":1,
           'p2':'hello',
           'obj2' = {'p11':11, 'p12':'hey1'}
          };

or 

var obj = {};
obj.prop = 'hello';
```
To remove property: `delete.person.age`
Array\object.length: dosen't count the no. of property of an object, instead it count the index of last property.
Wrapper Objects: provide equivalent object for each primitive types
No function overloading: as flexible with arguments
Anonymous function expression :Function are values in JS, without name; `var f = function(){};`
Array.unshift(): to delete from front
For each:
```
var abc = [1, 2, 3];
var f = function(item, index, array){console.log(item)};
abc.foreach(f);
```

### **Scopes and Closures In-depth**:
If you redeclare a variable with the let keyword, you will get an error.
In the creation phase, the let variables are assigned storage spaces but are not initialized. Referencing uninitialized variables will cause a ReferenceError.
IIFE: avoid global var, anonymous function call directly.(invoked function)
```
(function(){var a=10;var b =10;console.log(a+b);})();
```
a = b; RHS is read, LHS is write, similarlily in passing an argument to a function is a write operation.
Declaration is must in js for read operation but ok for write operation.
Global object in browser is window object. Every global variable\function would be the property on that global object window(let variables are not added to the global object).
Interpreted: run source code directly
Compiled: run intimidiatory\converted final code
Browser does compilation step not to generate intimediatory file but to look for signs needed to execute it. 
Compilation Step: scope creation\creating space in memory(function(an object), local, global) 
Interpreter Step: execute the steps, knowing scope of variable(create undefined variable in global scope)
***Note:*** carefull about the nested example of scope
Hoisting: you can define variable\function even in end of code, dosen't work for function expression!
```
console.log(a);
var a = 10;
```
Js can be run in "Strict mode": `"use strict";`
Closure: function that remember its scope
1. When you create function object in JS, it also create scope chain also!(i.e pointer to that variable)
2. Garbage collector: only for object without any pointer
CallBack API : SetTimeout
```
var a =10;
var fn=function(){console.log(a)};
setTimeout(fn, 1000)
console.log("Done")

# here CLOSURE is being used!
```
Closure used for hiding:
```
function createPerson()
{
    var firstName = "Prateek";
    var lastName = 'Chauhan';
    var retrunObject()
    {
        "getFirstName" : function(){return firstName;},
        "getLastName" : function(){return lastName;}
    };
    return returnObject;
}
var person = createPerson();
console.log(person.getFirstName());
```
Closures in async Callbacks: idea is to save var itself not its address
```
var j;
for (j =1; j<10; j++)
{
    (function(){var currentValue = j;
                setTimeout(function(){console.log(currentValue)}, 1000);})();
}
```


### **Objects and prototypes**:
ES6 allow to use keyword "Class", but still you don't have full functionality in js.
Constructor call with "new" keyword allow us to skip 2 very statement that needed to create and return an object.(no need to have class name), use this!

