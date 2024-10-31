# Build-Chrome-Extention

#### Challenge
Create an input element with type="text" and id="input-el" 
Create a SAVE INPUT button with id="input-btn"
```js
<html>
    <head>
        <link rel="stylesheet" href="index.css">
    </head>
    <body>
        <input type="text" id="input-el">
        <button id="input-btn">SAVE INPUT</button>
        <script src="index.js"></script>
    </body>
</html>
```
#### CSS
```js
body {
    margin: 0;
    padding: 10px;
    font-family: Arial, Helvetica, sans-serif;
}

input {
    width: 100%;
    padding: 10px;
    box-sizing: border-box;
    border: 1px solid #5f9341;
    margin-bottom: 4px;
}

button {
    background: #5f9341;
    color: white;
    padding: 10px 20px;
    border: none;
    font-weight: bold;
}

```
#### challenge
Log out "Button clicked!" when the user clicks the "SAVE INPUT" button
"clickButton()" id="input-btn">
```js
let clicked =document.getElementById("input-btn")
function clickButton(){
    console.log( "Button clicked!")   // <button onclick="clickButton()" id="input-btn">SAVE INPUT</button>
}
```
##### Button clicked from addEventListener
```js
let inputBtn = document.getElementById("input-btn")
                                     // <button id="input-btn">SAVE INPUT</button>
inputBtn.addEventListener("click", function() {
    console.log("Button clicked from addEventListener")
})

```
#### challenge addEventListener("click", function(){})
 Grab the box from the DOM and store it in a variable
 Add a click event listener to the box 
 Log out "I want to open the box!" when it's clicked
```js
 let box = document.getElementById("box")
           // <div id="box">Open the box!</div>
box.addEventListener("click", function(){
    console.log("I want to open the box!")
})
-------------------------------------------------------------
-------------------------------------------------------------
     //CSS
html, body {
    margin: 0;
    padding: 0;
    font-family: Arial, Helvetica, sans-serif;
}

#box {
    cursor: pointer;
    background: lightseagreen;
    padding: 40px;
    width: 200px;
    text-align: center;
    margin: 20px auto;
    color: white;
    font-weight: bold;
}
```
Create two variables:
 myLeads -> should be assigned to an empty array
 inputEl -> should be assigned to the text input field
 ```js
   let myLeads = []
const inputEl = document.getElementById("input-el")
```
#### const and let variable
```js
// If possible, use const. If not, use let.

// Which variables below should be changed from let to const?

// The customer wants to order some stuff. Here are the details:
let basePrice = 520  //it is const not assining again
let discount = 120  //it is const not assining again
let shippingCost = 12 //it is let assining again
let shippingTime = "5-12 days" //it is let assining again

// Whops! Turns out the shipping will be a bit more complex
shippingCost = 15
shippingTime = "7-14 days"

// Calculating the full price
let fullPrice = basePrice - discount + shippingCost

// Finally, notifying the customer
console.log("Total cost: " + fullPrice + ". It will arrive in " + shippingTime)


```
#### challenge
Push the value "www.awesomelead.com" to myArray when the input button is clicked
```js
let myLeads = []
inputBtn.addEventListener("click", function() {
     myLeads.push("www.awesomelead.com")
      console.log(myLeads)
})

```
#### challenge
Push the value from the inputEl into the myLeads array 
instead of the hard-coded "www.awesomeleads.com" value
Google -> "get value from input field javascript"
```js
let myLeads = []  //Add value in input and click button
const inputEl = document.getElementById("input-el")
const inputBtn = document.getElementById("input-btn")
inputBtn.addEventListener("click", function() {
    myLeads.push(inputEl.value)
    console.log(myLeads)
})
```
#### challenge
Log out the items in the myLeads array using a for loop 

```js
let myLeads = ["www.awesomelead.com", "www.epiclead.com", "www.greatlead.com"]
for(let i=0; i<myLeads.length;i++){
    console.log(myLeads[i])
}

```
#### challenge
 Create an unordered list element (<ul>) with id="ul-el" 
 Grab the unordered list and store it in a const variable called ulEl
 ```js
 <ul id="ul-el"></ul>
const ulEl = document.getElementById("ul-el")
console.log(ulEl)
```
#### challenge
 Render the leads in the unordered list using ulEl.textContent

 ```js
let myLeads = ["www.awesomelead.com", "www.epiclead.com", "www.greatlead.com"]
const ulEl = document.getElementById("ul-el")
for (let i = 0; i < myLeads.length; i++) {
  ulEl.innerHTML+="<li>" myLeads[i]+" " "</li>"
}
```
#### challenge
Use .innerHTML to render a Buy! button inside the div container
```js
 document.getElementById("container").innerHTML="<button>Buy!</button>"
                 //or
const container = document.getElementById("container")
container.innerHTML = "<button>Buy!</button>"

```
#### challenge
When clicked, render a paragraph under the button (in the container)
 that says "Thank you for buying!"

 ```js
const container = document.getElementById("container")
container.innerHTML = "<button onclick='buy()'>Buy!</button>"
  function buy(){
    container.innerHTML += "<p >Thank you for buying</p>"
  }
```
  ##### create element
  #####   set text content
  #####   append to ul
```js
let myLeads = ["www.awesomelead.com", "www.epiclead.com", "www.greatlead.com"]
const ulEl = document.getElementById("ul-el")
for (let i = 0; i < myLeads.length; i++) {
    // ulEl.innerHTML += "<li>" + myLeads[i] + "</li>"
    const li = document.createElement("li")
    li.textContent = myLeads[i]
    ulEl.append(li)
}
```
Create a variable, listItems, to hold all the HTML for the list items
Assign it to an empty string to begin with
Add the item to the listItems variable instead of the ulEl.innerHTML
 Render the listItems inside the unordered list using ulEl.innerHTML
 ```js
let myLeads = ["www.awesomelead.com", "www.epiclead.com", "www.greatlead.com"]
const ulEl = document.getElementById("ul-el")
  let listItems=""
for (let i = 0; i < myLeads.length; i++) {
   listItems += "<li>" + myLeads[i] + "</li>"
}
   ulEl.innerHTML=listItems
```
```js
let myLeads = []
const inputEl = document.getElementById("input-el")
const inputBtn = document.getElementById("input-btn")
const ulEl = document.getElementById("ul-el")

inputBtn.addEventListener("click", function() {
    myLeads.push(inputEl.value)
    // 2. Call the renderLeads() function
})

// 1. Wrap the code below in a renderLeads() function
let listItems = ""
for (let i = 0; i < myLeads.length; i++) {
    listItems += "<li>" + myLeads[i] + "</li>"
}
ulEl.innerHTML = listItems

----------------Solve-------
let myLeads = []
const inputEl = document.getElementById("input-el")
const inputBtn = document.getElementById("input-btn")
const ulEl = document.getElementById("ul-el")

inputBtn.addEventListener("click", function() {
    myLeads.push(inputEl.value)
    // 2. Call the renderLeads() function
     inputEl.value = ""
    renderLeads()
})

// 1. Wrap the code below in a renderLeads() function
function renderLeads() {
    let listItems = ""
    for (let i = 0; i < myLeads.length; i++) {
        listItems += "<li>" + myLeads[i] + "</li>"
    }
    ulEl.innerHTML = listItems  
}


```
#### challenge
Wrap the lead in an anchor tag (<a>) inside the <li>
Can you make the link open in a new tab?
```js
function renderLeads() {
    let listItems = ""
    for (let i = 0; i < myLeads.length; i++) {
        // Wrap the lead in an anchor tag (<a>) inside the <li>
        // Can you make the link open in a new tab?
        listItems += "<li><a target='_blank' href='" + myLeads[i] + "'>" + myLeads[i] + "</a></li>"
        console.log(listItems)
    }
    ulEl.innerHTML = listItems  
}
```
#### challenge
Template String
```js
  listItems += `
            <li>
                <a target='_blank' href='${myLeads[i]}'>
                    ${myLeads[i]}
                </a>
            </li>
        `
const recipient = "James"

// Refactor the email string to use template strings
const email = `Hey  ${recipient} ! How is it going? Cheers Per`
console.log(email)

```
Build Chrom Extention 
```js
body {
    margin: 0;
    padding: 10px;
    font-family: Arial, Helvetica, sans-serif;
    min-width: 400px;
}

input {
    width: 100%;
    padding: 10px;
    box-sizing: border-box;
    border: 1px solid #5f9341;
    margin-bottom: 4px;
}

button {
    background: #5f9341;
    color: white;
    padding: 10px 20px;
    border: none;
    font-weight: bold;
}

ul {
    margin-top: 20px;
    list-style: none;
    padding-left: 0;
}

li {
    margin-top: 5px;
}

a {
    color: #5f9341;
}
//----------------------------------------------------------------
<html>
    <head>
        <link rel="stylesheet" href="index.css">
    </head>
    <body>
        <input type="text" id="input-el">
        <button id="input-btn">SAVE INPUT</button>
        <ul id="ul-el">
        </ul>
        <script src="index.js"></script>
    </body>
</html>
//---------------------------------------------------------------
let myLeads = []
const inputEl = document.getElementById("input-el")
const inputBtn = document.getElementById("input-btn")
const ulEl = document.getElementById("ul-el")



inputBtn.addEventListener("click", function() {
    myLeads.push(inputEl.value)
    inputEl.value = ""
                             ///****????
    renderLeads()
})

function renderLeads() {
    let listItems = ""
    for (let i = 0; i < myLeads.length; i++) {
        listItems += `
            <li>
                <a target='_blank' href='${myLeads[i]}'>
                    ${myLeads[i]}
                </a>
            </li>
        `
    }
    ulEl.innerHTML = listItems  
}
//--------------------------
{
    "manifest_version": 3,
    "version": "1.0",
    "name": "Leads tracker",
    "action": {
        "default_popup": "index.html",
        "default_icon": "icon.png"
    }
}


```
#### Store Value IN LOcalstorage
 1. Save a key-value pair in localStorage
 2. Refresh the page. Get the value and log it to the console
 3. Clear localStorage

 HINTS:
 localStorage.setItem(key, value)
 localStorage.getItem(key)
 localStorage.clear()
 PS: both key and value need to be strings

```js
localStorage.setItem("Name", "Jon Doe")

let name = localStorage.getItem("Name")
console.log(name)
//localStorage.clear()
```
JSON.Srigify
Change Arry into String
```js
let myLeads = ["www.awesomelead.com"]

myLeads = JSON.stringify(myLeads)

console.log(typeof myLeads)

```

 Turn the myLeads string into an array
 Push a new value to the array
Turn the array into a string again
Console.log the string using typeof to verify that it's a string

```js
let myLeads = `["www.awesomelead.com"]`
myLeads = JSON.parse(myLeads)
myLeads.push("www.lead2.com")
myLeads = JSON.stringify(myLeads)
console.log(typeof myLeads)

  localStorage.setItem("myLeads", JSON.stringify(myLeads) ) ///****????

localStorage.clear()
let leadsFromLocalStorage = JSON.parse( localStorage.getItem("myLeads") )

console.log(leadsFromLocalStorage)
```
#### truthy   falsy Value
Check the value true or false
```js

let trueOfFalse = Boolean("hello")

console.log(trueOfFalse)

console.log(  Boolean("")   ) // 
console.log(  Boolean("0")  ) //
console.log(  Boolean(100)  ) //
console.log(  Boolean(null) ) //
console.log(  Boolean([0])  ) //
console.log(  Boolean(-0)   ) //

const credits = 0

if ("yolo") {
    console.log("Let's play 🎰")
} else {
    console.log("Sorry, you have no credits 😭")
}

// false
// 0
// ""
// null  // Emptyness from developer
// undefined // Emptyness from computer
// NaN

```

```js
// ["lead1", "lead2"] or null
let leadsFromLocalStorage = JSON.parse( localStorage.getItem("myLeads") )
console.log(leadsFromLocalStorage)
// 1. Check if leadsFromLocalStorage is truthy
// 2. If so, set myLeads to its value and call renderLeads()

if (leadsFromLocalStorage) {
    myLeads = leadsFromLocalStorage
    renderLeads()
}

```
Store the delete button in a deleteBtn variable
 Listen for double clicks on the delete button (google it!)
 . When clicked, clear localStorage, myLeads, and the DOM


 ```js
const deleteBtn = document.getElementById("delete-btn")
const leadsFromLocalStorage = JSON.parse( localStorage.getItem("myLeads") )
deleteBtn.addEventListener("dblclick", function() {
    console.log("double clicked!")
    localStorage.clear()
    myLeads = []
    renderLeads()
})

```
####### Give the function a parameter, name, that replaces "name"
```js
const welcomeEl = document.getElementById("welcome-el")
function greetUser(name) {
    welcomeEl.textContent = `Welcome back, ${name} 👋`   
}
greetUser("Jon Doe")



const welcomeEl = document.getElementById("welcome-el")

// Add the ability to choose the emoji as well!

function greetUser(greeting, name, emoji) {
    welcomeEl.textContent = `${greeting}, ${name} ${emoji}`
}

greetUser("Howdy", "James", "🔥") 
```
```js
// Create a function, getFirst(arr), that returns the first item in the array

function getFirst(arr) {
    return arr[0]
}

let firstCard = getFirst([10, 2, 5])

console.log(firstCard)

// Call it with an array as an argument to verify that it works
```
```js
let myLeads = []
const inputEl = document.getElementById("input-el")
const inputBtn = document.getElementById("input-btn")
const ulEl = document.getElementById("ul-el")
const deleteBtn = document.getElementById("delete-btn")
const leadsFromLocalStorage = JSON.parse( localStorage.getItem("myLeads") )

if (leadsFromLocalStorage) {
    myLeads = leadsFromLocalStorage
    render(myLeads)
}

// Refector the function so that it takes a parameter, leads, that it uses
// instead of the global myLeads variable. Remember to update all invocations 
// of the function as well.

function render(leads) {
    let listItems = ""
    for (let i = 0; i < leads.length; i++) {
        listItems += `
            <li>
                <a target='_blank' href='${leads[i]}'>
                    ${leads[i]}
                </a>
            </li>
        `
    }
    ulEl.innerHTML = listItems
}

deleteBtn.addEventListener("dblclick", function() {
    localStorage.clear()
    myLeads = []
    render(myLeads)
})

inputBtn.addEventListener("click", function() {
    myLeads.push(inputEl.value)
    inputEl.value = ""
    localStorage.setItem("myLeads", JSON.stringify(myLeads) )
    render(myLeads)
})
```

```js
const tabBtn = document.getElementById("tab-btn")
const tabs = [
    {url: "https://www.linkedin.com/in/per-harald-borgen/"}
]

tabBtn.addEventListener("click", function(){
    // Save the url instead of logging it out
    // console.log(tabs[0].url)
    myLeads.push(tabs[0].url)
    localStorage.setItem("myLeads", JSON.stringify(myLeads) )
    render(myLeads)
})
```


## Save

```js
{  // menifest.json
    "manifest_version": 3,
    "version": "1.0",
    "name": "Leads tracker",
    "action": {
        "default_popup": "index.html",
        "default_icon": "icon.png"
    },
    "permissions": [
        "tabs"
    ]
}

----------------------------------------
tabBtn.addEventListener("click", function(){    
    chrome.tabs.query({active: true, currentWindow: true}, function(tabs){
        myLeads.push(tabs[0].url)
        localStorage.setItem("myLeads", JSON.stringify(myLeads) )
        render(myLeads)
    })
})
```
### Complete 


```js
let myLeads = []
const inputEl = document.getElementById("input-el")
const inputBtn = document.getElementById("input-btn")
const ulEl = document.getElementById("ul-el")
const deleteBtn = document.getElementById("delete-btn")
const leadsFromLocalStorage = JSON.parse( localStorage.getItem("myLeads") )
const tabBtn = document.getElementById("tab-btn")

if (leadsFromLocalStorage) {
    myLeads = leadsFromLocalStorage
    render(myLeads)
}

tabBtn.addEventListener("click", function(){    
    chrome.tabs.query({active: true, currentWindow: true}, function(tabs){
        myLeads.push(tabs[0].url)
        localStorage.setItem("myLeads", JSON.stringify(myLeads) )
        render(myLeads)
    })
})

function render(leads) {
    let listItems = ""
    for (let i = 0; i < leads.length; i++) {
        listItems += `
            <li>
                <a target='_blank' href='${leads[i]}'>
                    ${leads[i]}
                </a>
            </li>
        `
    }
    ulEl.innerHTML = listItems
}

deleteBtn.addEventListener("dblclick", function() {
    localStorage.clear()
    myLeads = []
    render(myLeads)
})

inputBtn.addEventListener("click", function() {
    myLeads.push(inputEl.value)
    inputEl.value = ""
    localStorage.setItem("myLeads", JSON.stringify(myLeads) )
    render(myLeads)
})

```
```js
<html>
    <head>
        <link rel="stylesheet" href="index.css">
    </head>
    <body>
        <input type="text" id="input-el">
        <button id="input-btn">SAVE INPUT</button>
        <button id="tab-btn">SAVE TAB</button>
        <button id="delete-btn">DELETE ALL</button>
        <ul id="ul-el">
        </ul>
        <script src="index.js"></script>
    </body>
</html>
```
```js
{
    "manifest_version": 3,
    "version": "1.0",
    "name": "Leads tracker",
    "action": {
        "default_popup": "index.html",
        "default_icon": "icon.png"
    },
    "permissions": [
        "tabs"
    ]
}
```
```js
body {
    margin: 0;
    padding: 10px;
    font-family: Arial, Helvetica, sans-serif;
    min-width: 400px;
}

input {
    width: 100%;
    padding: 10px;
    box-sizing: border-box;
    border: 1px solid #5f9341;
    margin-bottom: 4px;
}

button {
    background: #5f9341;
    color: white;
    padding: 10px 20px;
    border: 1px solid #5f9341;
    font-weight: bold;
}

#delete-btn {
    background: white;
    color: #5f9341;
}

ul {
    margin-top: 20px;
    list-style: none;
    padding-left: 0;
}

li {
    margin-top: 5px;
}

a {
    color: #5f9341;
}



```


















