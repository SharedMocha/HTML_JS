# HTML_JS

HTML + JS ->
**use handle abr as its easy for tempalting--
VV IMP -> USE DEFER -> <script src="example.js" defer></script>  //The defer attribute specifies scripts should be executed after the HTML file is completely parsed. //When a script contains functionality that requires interaction with the DOM, the defer attribute is the way to go. This way, it ensures that the entire HTML file has been parsed before the script is executed.
vv IMP -> USE ASYNC -> <script src="example.js" async></script> //The async attribute loads and executes the script asynchronously with the rest of the webpage. This means that, similar to the defer attribute, the HTML parser will continue parsing the rest of the HTML as the script is downloaded in the background. However, with the async flag, the script will not wait until the entire page is parsed: it will execute immediately after it has been downloaded. Here is an example of the async tag:
async vs defer -> Async is useful for scripts that are independent of other scripts in order to function accordingly. Thus, if it does not matter exactly at which point the script file is executed, asynchronous loading is the most suitable option as it optimizes web page load time.
vv imp --> First things first! The document object in JavaScript is the door to the DOM structure. The document allows you to access the root node of the DOM tree. Before you can access a specific element in the page, first you must access the document structure itself. The document allows scripts to access children of the DOM as properties.
document.(node/element).(dom proeprty or attribute) = document.body.innerHTML ='';

*document.body.innerHTML //modify body element contents
*document.querySelector('p'); //CSS SELECTOR to change first paragaporh rule
*document.querySelector('p'); //CSS ID SELECTOR
*document.querySelector('.blue').style.backgroundColor = 'blue'; //change color
*document.querySelector('.blue').style.fontFamily = 'Roboto'; //change font
*create and add a paragrpah rule to html -> let paragraph = document.createElement('p');paragraph.innerHTML = 'The text inside paragraph';document.body.appendChild(paragraph);
*document.getElementById('sign').hidden = true; //hide an elment 
*document.body.removeChild(paragraph); //remove an elemenbt
*let element = document.getElementById('interact'); element.onclick = function() { element.style.backgroundColor = 'blue' }; //handle on click events
*In the DOM hierarchy, parent and children relationships are defined in relation to the position of the root node.A parent node is the closest connected node to another node in the direction towards the root.A child node is the closest connected node to another node in the direction away from the root.
let first = document.body.firstChild;
first.innerHTML = "First child";
first.parentNode.innerHTML = "I am the parent and my inner HTML has been replaced!";
*It’s best practice to create named event handler functions, instead of anonymous functions. Your code will remain organized and reusable this way, even if your code gets complex. Check out the syntax:
let eventHandlerFunction = function() {
  // this block of code will run
}
*eventTarget.addEventListener('click', eventHandlerFunction); 
he .addEventListener() method is another common syntax for registering event handlers. An event listener waits for a specific event to occur and calls a named event handler function to respond to it. This method requires two arguments:

The event type as a string
The event handler function
*eventTarget.removeEventListener('click', eventHandlerFunction); //remove event handler
*.taget,.type,.timestamp ->JavaScript stores events as event objects with their related data and functionality as properties and methods
**types of events other than click  like mouse,keyboard -> https://developer.mozilla.org/en-US/docs/Web/Events



-----
eventTarget.onclick = eventHandlerFunction;


-------------------
These relationships follow the nesting structure present in HTML code. Elements nested within one HTML tag are children of that parent element.
The <script> element allows you to add JavaScript code inside an HTML file. Below, the <script> element embeds valid JavaScript code:
<h1>This is an embedded JS example</h1>
<script>
  function Hello() {
    alert ('Hello World');
  }
</script>


The src attribute -
 <script src=/exampleScript.js> </script> //load external js
 
 
 Notes-
 HTML creates the skeleton of a webpage, but JavaScript introduces interactivity

The <script> element has an opening and closing tag. You can embed JavaScript code inside the opening and closing <script> tags.

You link to external JavaScript files with the src attribute in the opening <script> tag.

By default, scripts are loaded and executed as soon as the HTML parser encounters them in the HTML file, preventing the HTML parser from proceeding to parse the rest of the page elements.

The defer attribute ensures that the entire HTML file has been parsed before the script is executed.

The async flag will allow the HTML parser to continue parsing as the script is being downloaded, but will execute immediately after it has been downloaded.

--------------------------------------------------------------------------------------
DOM ->browser converts html to dom so scripting language can alter it->
 https://s3.amazonaws.com/codecademy-content/courses/dom/dom_revision_1.svg
 https://s3.amazonaws.com/codecademy-content/courses/dom/dom_revision_6.svg
 https://s3.amazonaws.com/codecademy-content/courses/dom/dom_revision_5.svg
 
 //The DOM is a language-agnostic structure implemented by browsers to allow for web scripting languages, like JavaScript, to access, modify, and update the structure of an HTML web page in an organized way.For this reason, we like to think of the DOM as the link between an HTML web page and scripting languages.
 
 Node types->https://www.w3schools.com/jsref/prop_node_nodetype.asp
 
 Nodes and Elements in the DOM - As mentioned, a node is the equivalent of each family member in a family tree. A node is an intersecting point in a tree that also contains data.
 https://s3.amazonaws.com/codecademy-content/courses/dom/dom_revision_2.svg
 There are nine different types of node objects in the DOM tree. In our diagram, the node objects with the sharp-edge rectangles are of the type Element, while the rounded edge rectangles are of type Text, because they represent the text inside the HTML paragraph elements.

When trying to modify a web page, the script will mostly interact with the DOM nodes of type element. Elements are the building units of HTML web pages, they contain everything between an opening tag and a closing tag. If the tag is a self-closing tag, then that is the element itself.

Attributes of Element Node -->https://s3.amazonaws.com/codecademy-content/courses/dom/dom_revision_4.svg


--Congratulations on completing our introduction to the Document Object Model, or DOM, as a structure!

Let’s review what you’ve learned so far:

The DOM is a structural model of a web page that allows for scripting languages to access that page.
The system of organization in the DOM mimics the nesting structure of an HTML document.
Elements nested within another are referred to as the children of that element. The element they are nested within is called the parent element of those elements.
The DOM also allows access to the regular attributes of an HTML element such as its style, id, etc.


-->JS + DOM----------------------------
https://s3.amazonaws.com/codecademy-content/courses/dom/dom_revision_6.svg
https://developer.mozilla.org/en-US/docs/Web/API/Document

First things first! The document object in JavaScript is the door to the DOM structure. The document allows you to access the root node of the DOM tree. Before you can access a specific element in the page, first you must access the document structure itself. The document allows scripts to access children of the DOM as properties.

For example, if you wanted to access the <body> element in your script, you could access it as a property of the document by typing document.body. This property will return the body element of that DOM.
When using the DOM in your script to access an HTML element, you also have access to all of that element’s properties.so you can modify content using its proeprty -> document.body.innerHTML = 'The cat loves the dog.';


-> ACCESS ELEMENT USING CSS SELECTION ->
document.querySelector('p');
The .querySelector() method allows us to specify a CSS selector and then returns the first element that matches that selector. The following code would return the first paragraph in the document.
document.querySelector('p'); //RETURN FIRST PARAGH IN THE document.
*You can also use other CSS selectors such as an element’s . class or its # ID.

other way -> document.getElementById('bio').innerHTML = 'The description';


review--
The document keyword grants access to the root of the DOM in JavaScript
The DOM Interface allows you to select a specific element with CSS selectors by using the .querySelector() method
You can also access an element directly by its ID with .getElementById()
The .innerHTML and .style properties allow you to modify an element by changing its contents or style respectively
You can create, append, and remove elements by using the .createElement(),.appendChild() and .removeChild() methods respectively
The .onclick property can add interactivity to a DOM element based on a click event


------------------events and events handler--------------
After a specific event fires on a specific element in the document object model (or DOM), an event handler function can be created to run as a response. In this lesson, we will learn about event handler functions that modify and update DOM elements after an event fires.
https://s3.amazonaws.com/codecademy-content/courses/javascript-dom-events/Sorting_course_book_image.svg


example-
let eventTarget = document.getElementById('targetElement');

eventTarget.onclick = function() {
  // this block of code will run
}
-------
DOM EVENTS WITH JAVASCRIPT
Review
Congrats, you completed the lesson! Now you’ve learned about JavaScript events and you can leverage these events on the DOM to create interactivity with event handlers.

Let’s review what you’ve learned:

JavaScript engines register events as objects with properties and methods associated with them.
Event handlers are registered as properties of their event object.
Event object properties like .target, .type, and .timeStamp are used to provide information about the event.
The .addEventListener() method can be used to add multiple event handler functions to a single event.
The .removeEventListener() method stops specific event handlers from “listening” for specific events firing.
