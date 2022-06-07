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
ECMAScript (ES) is a scripting language specification created to standardize JavaScript. ES6 is a superset of JavaScript (ES5). It introduced new conventions and OOP concepts such as classes.
   A. var & let
   The var keyword, which defines a variable globally, or locally to an entire function regardless of block scope, let allows you to declare variables that are limited in scope to the block, statement, or expression in which they are used.


   
        





















     




     