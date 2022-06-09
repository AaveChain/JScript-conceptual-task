# JScript-conceptual-task

1:- Overview

2:- Basic Concepts

3:- Conditionals and Loops

4:- Functions

5:- Objects

6:- Core Objects
   A. JavaScript Arrays 
   Arrays store multiple values in a single variable.

   "var courses = new Array("HTML", "CSS", "JS");"

   B. The length Property
   JavaScript arrays have useful built-in properties and methods.An array's length property returns the number of it's elements.

      "array.length()"

   C. Associative Arrays 
   JavaScript does not support arrays with named indexes.In JS, arrays always use numbered indexes. It is better to use an object when you want the index to be a string (text). Use an array when you want the index to be a number.

   D. Math Object Methods
   To get a random number between 1-10, use Math.random(), which gives you a number between 0-1. Then multiply the number by 10, and then take Math.ceil() from it: Math.ceil(Math.random() * 10).

   E.The Date Object
   The Date object enables us to work with dates.A date consists of a year, a month, a day, an hour, a minute, a second, and milliseconds.
   Using new Date(), create a new date object with the current date and time.
      //Fri Jun 07 2022 03:51:09
      var date = new Date("June 7, 2022 03:51:09");

   JScript counts months from 0 to 11. January is 0, and December is 11. Date objects are static, rather than dynamic. The computer time is ticking, but date objects don't change, once created.  
       var date = newDate();
       alert(date.getMinutes());

7:- DOM
JavaScript can be used to manipulate the DOM of a page dynamically to add, delete and modify elements.
   A. DOM Tree
   The DOM represents a document as a treestructure.HTML elements become interrelated nodes in the tree. All those nodes in the tree have some kind of relations among each other. Nodes can have child nodes. Nodes on the same tree level are called siblings.
   B. The document Object
   The document object is the owner (or root) of all objects in your webpage. So, if you want to access objects in an HTML page, you always start with accessing the document object.

        "document.body.innerHTML = "Some text";"
   As body is an element of the DOM, we can access it using the document object and change the content of the innerHTML property.
   C.Selecting Elements
   The getElementById method is used to select the element with id="demo" and change its content.
        //finds element by id
        document.getElementById(id) 

        var elem = document.getElementById("demo");
        elem.innerHTML = "Hello World!";
   We used the length property of the array to loop through all the selected elements.  
   D. Changing Attributes
      <img id="myimg" src="orange.png" alt="" />
      <script>
        var el = document.getElementById("myimg");
        el.src = "apple.png";
      </script>
   We can change the href attribute of a link.
   E. Changing Style
    <div id="demo" style="color:... width:...">some text>/div>
    <script>
      var x = document.getElementById("demo");
      x.style.color= "";
      x.style.width="";
      x.style.backgroundColor="";
    </script>  
   F. Creating Elements
      var node = document.createTextNode("Some new text");

   element.appendChild(newNode) adds a new child node to an element as the last child node.
   element.insertBefore(node1, node2) inserts node1 as a child before node2.   
   G. Removing Elements
   An alternative way of achieving the same result would be the use of the parentNode property to get the parent of the element we want to remove:
      var child = document.getElementById("p1");
      child.parentNode.removeChild(child);
   or child.parentNode.replaceChild(child);

8:- Animations
we need to change the properties of an element at small intervals of time. 
    var t = setInterval(move, 500); 
we need to define the move() function, that changes the position of the box.    

    // starting position
    var pos = 0; 
    //our box element
    var box = document.getElementById("box");

    function move() {
      if(pos>= 150) {
        clearInterval(t);
      }
      else{
        pos += 1;
        box.style.left = pos+"px"; //px = pixels
    }

   A. Events Handlers
   Corresponding events can be added to HTML elements as attributes.
       vart x= document.grtElementByid("demo);
       x.onclick =function (){
           document.body.innerHTML = Date();
        }
   
   The onload and onunload events are triggered when the user enters or leaves the page. These can be useful when performing actions after the page is loaded.  
         <body onload="doSomething()">

         window.onload = function() {
         //some code
         }
   B. Event Listeners
   The addEventListener() method attaches an event handler to an element without overwriting existing event handlers. You can add many event handlers to one element.You can also add many event handlers of the same type to one element, i.e., two "click" events.
        element.addEventListener(event, function, useCapture);
   This adds two event listeners to the element.
      element.addEventListener("click", myFunction);
      element.addEventListener("mouseover", myFunction);

      function myFunction() {
         alert("Hello World!");
       }
    We can remove one of the listeners:
       element.removeEventListener("mouseover", myFunction);

    C. Event Propagation
    There are two ways of event propagation in the HTML DOM: bubbling and capturing.Capturing goes down the DOM.Bubbling goes up the DOM.
    In bubbling, the innermost element's event is handled first and then the outer element's event is handled.
    In capturing, the outermost element's event is handled first and then the inner. 
        //Capturing propagation
        elem1.addEventListener("click", myFunction, true); 

        //Bubbling propagation
        elem2.addEventListener("click", myFunction, false);

9:- ECMAScript 6  
ECMAScript (ES) is a scripting language specification created to standardize JavaScript. ES6 is a superset of JavaScript (ES5). It introduced new conventions and #OOP concepts such as classes.
   A. var & let
   The var keyword, which defines a variable #globally, or #locally to an entire function regardless of block scope, let allows you to declare variables that are limited in scope to the block, statement, or expression in which they are used.

   B. const
   const variables have the same scope as variables declared using let. The difference is that const variables are immutable - they are not allowed to be reassigned.

   C. Template Literals in ES6
   Template literals are enclosed by the backtick (` `) character instead of double or single quotes.The ${expression} is a placeholder, and can include any expression, which will get evaluated and inserted into the template literal.
         let a=8;
         let b=34;
         let msg= `The sum is ${a+b}`;
         console.log(msg);

9.1 Loops in ECMAScript 6
The for...in loop is intended for iterating over the enumerable keys of an object.It could iterate in an arbitrary order. Also, the iterating variable is a string, not a number.
       #for (let v in obj)
ES6 introduces the new for...of loop, which creates a loop iterating over iterable objects.During each iteration the val variable is assigned the corresponding element in the list.
       #for(let val of list)
The for...of loop works for other iterable objects as well, including strings.Its also works on collections(Map, Set, WeakMap, and WeakSet).
       for (let ch of "Hello")

9.2 Functions in ECMAScript 6
We can skip typing function and return, as well as some parentheses and braces. 'greet'has one argument and returns a message.
         #cont greet= x => "Welcome " + x;
If there are no parameters, an empty pair of parentheses should be used, as in #const x = () => alert("Hi");  
     A. ForEach Method 
     for each element of the array we need to execute a function then use this method of the array tocall a function for each element.
          const arr =[2,3,7,8]
          arr.forEach(v => {
             console.log(v*2);
          });


***What is ES6
It brought several new features like, let and const keyword, rest and spread operators, template literals, classes, modules and many other enhancements to make JavaScript programming easier. 


1. let and const keywords :
The keyword "let" enables the users to define variables and on the other hand, "const" enables the users to define constants. Variables were previously declared using "var" which had function scope and were hoisted to the top. It means that a variable can be used before declaration. But,the "let" variables and constants have block scope which is surrounded by curly-braces "{}" and cannot be used before declaration.

let i = 10;
console.log(i);   //Output 10

const PI = 3.14;
console.log(PI);  //Output 3.14

2. Arrow Functions
ES6 provides a feature known as Arrow Functions. It provides a more concise syntax for writing function expressions by removing the "function" and "return" keywords.

Arrow functions are defined using the fat arrow (=>) notation.

// Arrow function
let sumOfTwoNumbers = (a, b) => a + b;
console.log(sum(10, 20)); // Output 30

It is evident that there is no "return" or "function" keyword in the arrow function declaration.

We can also skip the parenthesis in the case when there is exactly one parameter, but will always need to use it when you have zero or more than one parameter.

But, if there are multiple expressions in the function body, then we need to wrap it with curly braces ("{}"). We also need to use the "return" statement to return the required value.

3. Multi-line Strings
ES6 also provides Multi-line Strings. Users can create multi-line strings by using back-ticks(`).

It can be done as shown below :

let greeting = `Hello World,     
                Greetings to all,
                Keep Learning and Practicing!`
                
4. Default Parameters
In ES6, users can provide the default values right in the signature of the functions. But, in ES5, OR operator had to be used.

//ES6
let calculateArea = function(height = 100, width = 50) {  
    // logic
}

//ES5
var calculateArea = function(height, width) {  
   height =  height || 50;
   width = width || 80;
   // logic
}

5. Template Literals
ES6 introduces very simple string templates along with placeholders for the variables. The syntax for using the string template is ${PARAMETER} and is used inside of the back-ticked string.

let name = `My name is ${firstName} ${lastName}`

6. Destructuring Assignment
Destructuring is one of the most popular features of ES6. The destructuring assignment is an expression that makes it easy to extract values from arrays, or properties from objects, into distinct variables.

There are two types of destructuring assignment expressions, namely, Array Destructuring and Object Destructuring. It can be used in the following manner :

//Array Destructuring
let fruits = ["Apple", "Banana"];
let [a, b] = fruits; // Array destructuring assignment
console.log(a, b);

//Object Destructuring
let person = {name: "Peter", age: 28};
let {name, age} = person; // Object destructuring assignment
console.log(name, age);

7. Enhanced Object Literals
ES6 provides enhanced object literals which make it easy to quickly create objects with properties inside the curly braces.

function getMobile(manufacturer, model, year) {
   return {
      manufacturer,
      model,
      year
   }
}
getMobile("Samsung", "Galaxy", "2020");

8. Promises
In ES6, Promises are used for asynchronous execution. We can use promise with the arrow function as demonstrated below.

var asyncCall =  new Promise((resolve, reject) => {
   // do something
   resolve();
}).then(()=> {   
   console.log('DON!');
})
9. Classes
Previously, classes never existed in JavaScript. Classes are introduced in ES6 which looks similar to classes in other object-oriented languages, such as C++, Java, PHP, etc. But, they do not work exactly the same way. ES6 classes make it simpler to create objects, implement inheritance by using the "extends" keyword and also reuse the code efficiently.

In ES6, we can declare a class using the new "class" keyword followed by the name of the class.

class UserProfile {   
   constructor(firstName, lastName) { 
      this.firstName = firstName;
      this.lastName = lastName;     
   }  
    
   getName() {       
     console.log(`The Full-Name is ${this.firstName} ${this.lastName}`);    
   } 
}
let obj = new UserProfile('John', 'Smith');
obj.getName(); // output: The Full-Name is John Smith
10. Modules
Previously, there was no native support for modules in JavaScript. ES6 introduced a new feature called modules, in which each module is represented by a separate ".js" file. We can use the "import" or "export" statement in a module to import or export variables, functions, classes or any other component from/to different files and modules.

export var num = 50; 
export function getName(fullName) {   
   //data
};
import {num, getName} from 'module';
console.log(num); // 50





       
               







   
        





















     




     