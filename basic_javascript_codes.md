# Basic JavaScript Codes

![Cambyze Logo](cambyze_icon.png)

This document summarizes essential JavaScript coding techniques, including best practices and practical examples for use in modern development environments.

## Table of Contents

- [Variables](#variables)
- [Collections](#collections)
- [Events listening](#events-listening)
- [Dynamic web](#dynamic-web)
- [Miscellaneous](#miscellaneous)
- [Related content](#related-content)

---

# Basic JavaScript codes
## Variables

- Undefined variable

```javascript
let y // x has no value at all, it is undefined
const isItUndefined = (y === undefined)
console.log({ y, isItUndefined })

// will NOT fail, length will be "undefined"

const length = y?.length 
console.log({ length })


// length will be 0, even though y is undefined

const length2 = y?.length || 0
console.log({ length2 })

// Null is not undefined
const x = null
const isItUndefined2 = (x === undefined)
console.log({ x, isItUndefined2 })

const obj = { lastName: "PARKER" }
// firstName is NOT undefined because of the default value
const { firstName = "default first name", lastName } = obj 
console.log({obj, firstName,  lastName})

const obj4 = {
 field1: "bla",
 field2: "bla",
 field3: null,
 field4: undefined,
}
// returns an object with 3 fields only, "field4" being trimmed out as it has the value "undefined".
console.log(JSON.stringify(obj4))
```

 

## Collections

- Loop on a array

```javascript
for (i in strings) {
 if (stringToSearch === strings[i]) { ...
```

 

```javascript
for (let string of strings) {
 if (stringToSearch === string) { ...
```

 

- Map a collection see below or see React JavaScript library 

```javascript
 const superHeroes = [
 { name: "SUPERMAN", lastName: "PARKER", firstName: "Peter" },
 { name: "SPIDERMAN", lastName: "KENT", firstName: "Clark" },
 { name: "IRONMAN", lastName: "STARK", firstName: "Tony" },
 ]

 // we define an anonymous function that takes an superheroe item
 // and returns his lastName
 const lastNames = superHeroes.map(it => it.lastName)
 console.log(lastNames) // lastNames is an array of strings

```

 

- Sort a collection

```javascript
const sortButton = document.querySelector(".btn-sort");

// Sort by price
sortButton.addEventListener("click", function () {
 const sortedItems = Array.from(items);
    sortedItems.sort((a, b) => a.prix - b.prix)
 console.log(sortedItems)
});
```

 

- Find the first element within a collection

```javascript
 const superHeroes = [
 { name: "SUPERMAN", lastName: "PARKER", firstName: "Peter" },
 { name: "SPIDERMAN", lastName: "KENT", firstName: "Clark" },
 { name: "IRONMAN", lastName: "STARK", firstName: "Tony" },
 ]

the fist item that matches the criteria "its lastName is KENT"
 const superman = superHeroes.find(it => it.lastName === "KENT")
 console.log(superman)

```

 

- Filter a collection

```javascript
const filterButton = document.querySelector(".btn-filter");

filterButton.addEventListener("click", function () {
 const filterItems = items.filter(function (item) {
 return item.prix <= 35;
 });
 console.log(filterItems)
});
```

 

- Find unique elements (reducing) in a collection

```javascript
 // Reducing with a unique list of categories
 const categories = bookList.reduce(
 (acc, book) =>
			acc.includes(book.category) ? acc : acc.concat(book.category),
 []
 )
```

 

## Events listening

- Listen the keyboard


```javascript
// Listen the keyboard
document.addEventListener('keydown', (event) => {
 console.log(event.key);
});
```

 

- Listen a submit within a form

```javascript
 <section>
 <div id="content">
 <form>
 <p>
 <label for="username">Name *</label>
 <input class ="content" type="text" id="username" name="username" placeholder="Your name" required>
 </p><p>
 <label for="email">Email *</label>
 <input class="content" type="email" id="email" name="email" placeholder="Your email" required>
 <input type="submit" id="submit" value="Submit">
 </p>
 </form>
 </div>
        ...
```

 

```javascript
// Listen the submit of the form block
const form = document.querySelector('form');
form.addEventListener("submit",(event) => {...
```

 

## Dynamic web

- Create new elements with createElement

```javascript
 // Create new elements with createElement
 let baliseVarBlock = document.getElementById("varblock")

 let newDiv = document.createElement("div")
 let newHeader= document.createElement("h1")
 let newText= document.createElement("p")

        newHeader.textContent="Result"
        newHeader.className="content"
        newText.textContent="It is a real success !!!"
        newText.className="content"

        newDiv.appendChild(newHeader)
        newDiv.appendChild(newText)
        baliseVarBlock.appendChild(newDiv)
```

 

- Create new elements with interpolation

```javascript
 // Create new elements by interpolation
 let newText2="Isn't it, " + saveUsername + " ?"
 let div = `
                <div><p class="content">${newText2}</p></div>
 `;
 let baliseVarText2 = document.getElementById("varblock2")
        baliseVarText2.innerHTML = div
```

 

## Miscellaneous

- Test the format of an email

```javascript
// test the structure of an email
function validateEmail(input) {

 const validRegex = /^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/;
 return input.value.match(validRegex);
}
```

 

- Class creation


```javascript
// Creation of a class
class Person {
 constructor(firstName, lastName) {
 this._firstName = firstName
 this._lastName = lastName
 }

 getFullName() {
 return `${this._firstName} ${this._lastName}`
 }
 }

 const me = new Person("Thierry", "NESTELHUT")

 // Returns name + last name
 console.log(me.getFullName())
```
