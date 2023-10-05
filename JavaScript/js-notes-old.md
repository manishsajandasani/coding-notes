# JavaScript Array Methods & Properties

## constructor property

- The constructor property returns the function that created the Array prototype.
- For JavaScript arrays the constructor property returns:
   - function Array() { [native code] }

```javascript
/**
 * Output:
 * ƒ Array() { [native code] }
*/
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let text = fruits.constructor;
console.log(text);
```

## length property

- The length property sets or returns the number of elements in an array.

```javascript
/**
 * output:
 * 4
 * (4) ['Banana', 'Orange', 'Apple', 'Mango']
 * 2
 * (2) ['Banana', 'Orange']
*/
const fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.length);
console.log(fruits);
fruits.length = 2;
console.log(fruits.length);
console.log(fruits);
```

## sort method

- The sort() sorts the elements of an array.
- The sort() overwrites the original array.
- The sort() sorts the elements as strings in alphabetical and ascending order.

```javascript
/**
 * output:
 * (4) ['Apple', 'Banana', 'Mango', 'Orange']
 * (4) ['Orange', 'Mango', 'Banana', 'Apple']
 */
const fruitsArr = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruitsArr.sort());
console.log(fruitsArr.sort().reverse());

/**
 * output:
 * (6) [1, 5, 10, 25, 100, 400]
 * Highest Value is 400
 */
const points1 = [400, 100, 1, 5, 25, 10];
points1.sort(function (a, b) {
	return a - b;
});
console.log(points1);
console.log(`Highest Value is ${points1[points1.length - 1]}`);

/**
 * output:
 * (6) [100, 40, 25, 10, 5, 1]
 */
const points2 = [40, 100, 1, 5, 25, 10];
points2.sort(function (a, b) {
	return b - a;
});
console.log(points2);
```

## reverse method

- The reverse() method reverses the order of the elements in an array.
- The reverse() method overwrites the original array.

```javascript
/**
 * output:
 * (5) ['Cranberry', 'Mango', 'Apple', 'Orange', 'Banana']
 * (5) ['Cranberry', 'Mango', 'Apple', 'Orange', 'Banana']
 */
const fruits = ["Banana", "Orange", "Apple", "Mango", "Cranberry"];
console.log(fruits.reverse());
console.log(fruits);
```

## pop method

- The pop() method removes (pops) the last element of an array.
- The pop() method changes the original array.
- The pop() method returns the removed element.

```javascript
/**
 * output:
 * Mango
 * Apple
 * (2) ['Banana', 'Orange']
 */
const fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.pop());
console.log(fruits.pop());
console.log(fruits);
```

## push method

- The push() method adds new items to the end of an array.
- The push() method changes the length of the array.
- The push() method returns the new length.

```javascript
/**
 * output:
 * 5
 * 6
 * (6) ['Sanjay', 'Kailash', 'Adtani', 'Rahul', 'Chiku', 'Priya']
 */
const friends = ["Sanjay", "Kailash", "Adtani", "Rahul"];
console.log(friends.push("Chiku"));
console.log(friends.push("Priya"));
console.log(friends);
```

## shift method

- The shift() method removes the first item of an array.
- The shift() method changes the original array.
- The shift() method returns the shifted element.

```javascript
/**
 * output:
 * Sanjay
 * Kailash
 * (2) ['Adtani', 'Rahul']
 * (2) ['Rahul', 'Adtani']
 */
const friends = ["Sanjay", "Kailash", "Adtani", "Rahul"];
console.log(friends.shift());
console.log(friends.shift());
console.log(friends);
console.log(friends.reverse());
```

## unshift method

- The unshift() method adds new elements to the beginning of an array.
- The unshift() method overwrites the original array.

```javascript
/**
 * output:
 * (6) ['Lemon', 'Pineapple', 'Banana', 'Orange', 'Apple', 'Mango']
 */
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon", "Pineapple");
console.log(fruits);
```

## concat method

- The concat() method concatenates (joins) two or more arrays.
- The concat() method returns a new array, containing the joined arrays.
- The concat() method does not change the existing arrays.

```javascript
/**
 * output:
 * (6) ['Cecilie', 'Lone', 'Emil', 'Tobias', 'Linus', 'Robin']
 */
const arr1 = ["Cecilie", "Lone"];
const arr2 = ["Emil", "Tobias", "Linus"];
const arr3 = ["Robin"];
const children = arr1.concat(arr2, arr3);
console.log(children);
```

## join method

- The join() method returns an array as a string.
- The join() method does not change the original array.
- Any separator can be specified. The default is comma (,).

```javascript
/**
 * output:
 * Banana /Orange /Apple /Mango
 */
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let text = fruits.join(" /");
console.log(text);
```

## slice method

- The slice() method returns selected elements in an array, as a new array.
- The slice() method selects from a given start, up to a (not inclusive) given end.
- The slice() method does not change the original array.

```javascript
/**
 * output:
 * (5) ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
 * ['Banana']
 * (4) ['Banana', 'Orange', 'Lemon', 'Apple']
 * (5) ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
 * (5) ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
 * ['Mango']
 * (2) ['Apple', 'Mango']
 * (2) ['Lemon', 'Apple']
 * (5) ['Banana', 'Orange', 'Lemon', 'Apple', 'Mango']
 * (4) ['Orange', 'Lemon', 'Apple', 'Mango']
 */
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
let sliceMe = fruits.slice(0);
console.log(sliceMe);
sliceMe = fruits.slice(0, 1);
console.log(sliceMe);
sliceMe = fruits.slice(0, 4);
console.log(sliceMe);
sliceMe = fruits.slice(0, 5);
console.log(sliceMe);
sliceMe = fruits.slice(0, 6);
console.log(sliceMe);
sliceMe = fruits.slice(-1);
console.log(sliceMe);
sliceMe = fruits.slice(-2);
console.log(sliceMe);
sliceMe = fruits.slice(-3, -1);
console.log(sliceMe);
sliceMe = fruits.slice(-fruits.length);
console.log(sliceMe);
sliceMe = fruits.slice(-fruits.length + 1);
console.log(sliceMe);
```

## splice method

- The splice() method adds and/or removes array elements.
- The splice() method overwrites the original array.

```javascript
/**
 * output:
 * (3) ['Banana', 'Orange', 'Kiwi']
 * (5) ['Guava', 'Pineapple', 'Banana', 'Orange', 'Kiwi']
 * (7) ['Guava', 'Pineapple', 'Banana', 'Orange', 'Kiwi', 'Watermelon', 'Chiku']
 * (8) ['Guava', 'Pineapple', 'Banana', 'Orange', 'Kiwi', 'Watermelon', 'Gold', 'Chiku']
 * (8) ['Guava', 'Pineapple', 'Banana', 'Orange', 'Kiwi', 'Watermelon', 'Gold', 'Silver']
 */
const fruits = ["Banana", "Orange", "Apple", "Mango", "Kiwi"];
fruits.splice(2, 2);
console.log(fruits);
fruits.splice(0, 0, "Guava", "Pineapple");
console.log(fruits);
fruits.splice(fruits.length, 0, "Watermelon", "Chiku");
console.log(fruits);
fruits.splice(fruits.length - 1, 0, "Gold");
console.log(fruits);
fruits.splice(fruits.length - 1, 1, "Silver");
console.log(fruits);
```

## isArray method

- The isArray() method returns true if an object is an array, otherwise false.
- Array.isArray() is a static property of the JavaScript Array object.
- You can only use it as Array.isArray().
- Using x.isArray(), where x is an array will return undefined.

```javascript
/**
 * output:
 * false
 * true
 */
let text = "W3Schools";
console.log(Array.isArray(text));
let numbers = [1, 2, 3, 4, 5];
console.log(Array.isArray(numbers));
```

## indexOf method

- The indexOf() method returns the first index (position) of a specified value.
- The indexOf() method returns -1 if the value is not found.
- The indexOf() method starts at a specified index and searches from left to right.
- By default the search starts at the first element and ends at the last.
- Negative start values counts from the last element (but still searches from left to right).

```javascript
/**
 * output:
 * 2
 * 2
 * 4
 * -1
 * 4
 * 4
 * 2
 */
const fruits = ["Banana", "Orange", "Apple", "Mango", "Apple"];
let index = fruits.indexOf("Apple");
console.log(index);
index = fruits.indexOf("Apple", 2);
console.log(index);
index = fruits.indexOf("Apple", 3);
console.log(index);
index = fruits.indexOf("Guava");
console.log(index);
index = fruits.indexOf("Apple", -1);
console.log(index);
index = fruits.indexOf("Apple", -2);
console.log(index);
index = fruits.indexOf("Apple", -4);
console.log(index);
```

## lastIndexOf method

- The lastIndexOf() method returns the last index (position) of a specified value.
- The lastIndexOf() method returns -1 if the value is not found.
- The lastIndexOf() starts at a specified index and searches from right to left.
- By defalt the search starts at the last element and ends at the first.
- Negative start values counts from the last element (but still searches from right to left).

```javascript
/**
 * output:
 * 4
 * -1
 * 2
 * 0
 * 2
 * 4
 */
const fruits = ["Apple", "Orange", "Apple", "Mango", "Apple", "Kiwi"];
let index = fruits.lastIndexOf("Apple");
console.log(index);
index = fruits.lastIndexOf("Guava");
console.log(index);
index = fruits.lastIndexOf("Apple", 2);
console.log(index);
index = fruits.lastIndexOf("Apple", 1);
console.log(index);
index = fruits.lastIndexOf("Apple", -3);
console.log(index);
index = fruits.lastIndexOf("Apple", -1);
console.log(index);
```

# entries method

- The entries() method returns an Array Iterator object with key/value pairs:
   - [0, "Banana"]
   - [1, "Orange"]
   - [2, "Apple"]
   - [3, "Mango"]
- The entries() method does not change the original array.

```javascript
/**
 * output:
 * (2) [0, 'Banana'] 0 'Banana'
 * (2) [1, 'Orange'] 1 'Orange'
 * (2) [2, 'Apple'] 2 'Apple'
 * (2) [3, 'Mango'] 3 'Mango'
 */
const fruits = ["Banana", "Orange", "Apple", "Mango"];
for (let x of fruits.entries()) {
	console.log(x, x[0], x[1]);
}
```

## every method

- The every() method executes a function for each array element.
- The every() method returns true if the function returns true for all elements.
- The every() method returns false if the function returns false for one element.
- The every() method does not execute the function for empty elements.
- The every() method does not change the original array

```javascript
/**
 * output:
 * false
 * true
 */
let ages = [32, 33, 19, 10];
console.log(ages.every(checkAge));
ages = [32, 33, 41, 19];
console.log(ages.every(checkAge));
function checkAge(age) {
	return age > 18;
}
```

## filter method

- The filter() method creates a new array filled with elements that pass a test provided by a function.
- The filter() method does not execute the function for empty elements.
- The filter() method does not change the original array.

```javascript
/**
 * output:
 * (3) [66, 78, 90]
 */
const numbers = [18, 66, 78, 10, 90];
let passedTest = numbers.filter(greaterThan50);
console.log(passedTest);
function greaterThan50(x) {
	return x > 50;
}
```

## find method

- The find() method returns the value of the first element that passes a test.
- The find() method executes a function for each array element.
- The find() method returns undefined if no elements are found.
- The find() method does not execute the function for empty elements.
- The find() method does not change the original array.

```javascript
/**
 * output:
 */
let findCount = 0;
const ages = [3, 10, 66, 20];
console.log(ages.find(checkAge));
function checkAge(age) {
	findCount++;
	return age > 18;
}
console.log(findCount);
```

## findIndex method

- The findIndex() method executes a function for each array element.
- The findIndex() method returns the index (position) of the first element that passes a test.
- The findIndex() method returns -1 if no match is found.
- The findIndex() method does not execute the function for empty array elements.
- The findIndex() method does not change the original array.

```javascript
/**
 * output:
 * 1
 */
const ages = [3, 40, 18, 20];
console.log(ages.findIndex(checkAge));
function checkAge(age) {
	return age > 18;
}
```

## includes method

- The includes() method returns true if an array contains a specified value.
- The includes() method returns false if the value is not found.
- The includes() method is case sensitive.

```javascript
/**
 * output:
 * true
 * false
 * false
 */
let fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.includes("Banana"));
console.log(fruits.includes("BanaNA"));
console.log(fruits.includes("Banana", 3));
```

## some method

- The some() method checks if any array elements pass a test (provided as a callback function).
- The some() method executes the callback function once for each array element.
- The some() method returns true (and stops) if the function returns true for one of the array elements.
- The some() method returns false if the function returns false for all of the array elements.
- The some() method does not execute the function for empty array elements.
- The some() method does not change the original array.

```javascript
/**
 * output:
 * false
 * false
 * true
 */
let ages = [];
console.log(ages.some(checkAdult));
ages = [3, 10, 18, 15];
console.log(ages.some(checkAdult));
ages = [3, 10, 18, 20];
console.log(ages.some(checkAdult));
function checkAdult(age) {
	return age > 18;
}
```

## forEach method

- The forEach() method calls a function for each element in an array.
- The forEach() method is not executed for empty elements.

```javascript
/**
 * output:
 * Manish === 0
 * 30 === 1
 * true === 2
 * Bhopal === 3
 * 7745991848 === 4
 */
let person = ["Manish", 30, true, "Bhopal", 7745991848];
person.forEach((value, index) => {
	console.log(value + " === " + index);
});
```

## toString method

- The toString() method returns a string with array values separated by commas.
- The toString() method does not change the original array.
- Every JavaScript object has a toString() method.
- The toString() method is used internally by JavaScript when an object needs to be displayed as a text (like in HTML), or when an object needs to be used as a string.
- Normally, you will not use it in your own code.

```javascript
/**
 * output:
 * Banana,Orange,Apple,Mango
 */
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let text = fruits.toString();
console.log(text);
```

## valueOf method

- The valueOf() method returns the array itself.
- The valueOf() method does not change the original array.
- fruits.valueOf() returns the same as fruits.

```javascript
/**
 * output:
 * (4) ['Banana', 'Orange', 'Apple', 'Mango']
 * (4) ['Banana', 'Orange', 'Apple', 'Mango']
 */
const fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.valueOf());
console.log(fruits);
```

## fill method

- The fill() method fills specified elements in an array with a value.
- The fill() method overwrites the original array.
- Start and end position can be specified. If not, all elements will be filled.

```javascript
/**
 * output:
 * (4) ['Kiwi', 'Kiwi', 'Kiwi', 'Kiwi']
 * (4) ['Banana', 'Kiwi', 'Kiwi', 'Mango']
 * (4) ['Banana', 'Biwi', 'Biwi', 'Biwi']
 * (4) ['Mivi', 'Mivi', 'Mivi', 'Mivi']
 */
let fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.fill("Kiwi"));
fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.fill("Kiwi", 1, 3));
console.log(fruits.fill("Biwi", 1, 4));
console.log(fruits.fill("Mivi", 0));
```

## at method

- The at() method returns an indexed element from an array.
- The at() method returns the same as [].

```javascript
/**
 * output:
 * Apple
 * Apple
 */
const fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(fruits.at(2));
console.log(fruits[2]);
```

## copyWithin method

- The copyWithin() method copies array elements to another position in the array.
- The copyWithin() method overwrites the existing values.
- The copyWithin() method does not add items to the array.

```javascript
/**
 * output:
 * (10) [1, 2, 1, 2, 3, 4, 5, 6, 7, 8]
 * (5) ['Banana', 'Orange', 'Banana', 'Orange', 'Kiwi']
 */
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0];
console.log(numbers.copyWithin(2));
const fruits = ["Banana", "Orange", "Apple", "Mango", "Kiwi"];
console.log(fruits.copyWithin(2, 0, 2));
```

## flat method

- The flat() method concatenates sub-array elements.

```javascript
/**
 * output:
 * (6) [1, 2, 3, 4, 5, 6]
 * (8) [1, 2, 3, 4, Array(1), 6, 7, 8]
 */
const myArr1 = [
	[1, 2],
	[3, 4],
	[5, 6],
];
console.log(myArr1.flat());
const myArr2 = [1, 2, [3, [4, [5], 6], 7], 8];
console.log(myArr2.flat(2));
```

## flatMap method

- The flatMap() method maps all array elements and creates a new flat array.
- flatMap() creates a new array from calling a function for every array element.
- flatMap() does not execute the function for empty elements.
- flatMap() does not change the original array.

```javascript
/**
 * output:
 * (6) [2, 4, 6, 8, 10, 12]
 */
const myArr = [1, 2, 3, 4, 5, 6];
const newArr = myArr.flatMap((x) => x * 2);
console.log(newArr);
```

## from method

- The Array.from() method returns an array from any object with a length property.
- The Array.from() method returns an array from any iterable object.
- Array.from() is a static property of the JavaScript Array object.
- You can only use it as Array.from().
- Using x.from(), where x is an array will return undefined.

```javascript
/**
 * output:
 * HTMLCollection(4) [div.item, div.item, div.item, div.item]
 * (4) [div.item, div.item, div.item, div.item]
 * (7) ['A', 'B', 'C', 'D', 'E', 'F', 'G']
 */
let items = document.getElementsByClassName("item");
console.log(items);
console.log(Array.from(items));
console.log(Array.from("ABCDEFG"));
```

## keys method

- The keys() method returns an Array Iterator object with the keys of an array.
- The keys() method does not change the original array.

```javascript
/**
 * output:
 * 0 => type is number
 * 1 => type is number
 * 2 => type is number
 * 3 => type is number
 * 0 => type is string
 * 1 => type is string
 * 2 => type is string
 * 3 => type is string
 */
const fruits = ["Banana", "Orange", "Apple", "Mango"];
for (let x of fruits.keys()) {
	console.log(x + " => type is " + typeof x);
}
for (let x of Object.keys(fruits)) {
	console.log(x + " => type is " + typeof x);
}
```

## map method

- map() creates a new array from calling a function for every array element.
- map() does not execute the function for empty elements.
- map() does not change the original array.

```javascript
/**
 * output:
 * (4) [2, 3, 4, 5]
 * (4) [5, 10, 15, 20]
 */
let numbers = [4, 9, 16, 25];
console.log(numbers.map(Math.sqrt));

numbers = [10, 20, 30, 40];
console.log(
	numbers.map((x) => {
		return x / 2;
	})
);
```

## prototype

- prototype allows you to add new properties and methods to arrays.
- prototype is a property available with all JavaScript objects.
- You are not advised to change the prototype of an object that you do not control.
- You should not change the prototype of built in JavaScript datatypes like:
   - Numbers
   - Strings
   - Arrays
   - Dates
   - Booleans
   - Function
   - Objects
- Only change the prototype of your own objects.

```javascript
/**
 * output:
 * (5) [10, 20, 30, 40, 50]
 */
Array.prototype.multiplyByTen = function () {
	for (let i = 0; i < this.length; i++) {
		this[i] = this[i] * 10;
	}
	return this;
};
console.log([1, 2, 3, 4, 5].multiplyByTen());
```

# Class Inheritance
```js
/**
 * Output:
 * Employee Constructor
 * Employee Constructor
 */
class Employee {
    constructor() {
        console.log("Employee Constructor");
    }
}

class Manager extends Employee {

}

let empObj = new Employee();
let manObj = new Manager();
```

```js
/**
 * Output:
 * Employee Constructor Manish
 * Employee Constructor Sanjay
 */
class Employee {
    constructor(name) {
        console.log(`Employee Constructor ${name}`);
    }
}

class Manager extends Employee {

}

let empObj = new Employee("Manish");
let manObj = new Manager("Sanjay");
```

```js
/**
 * Output:
 * Employee Constructor Manish
 * Manager Constructor
 * Uncaught ReferenceError: Must call super constructor in derived class before accessing 'this' or returning from derived constructor
 */
class Employee {
    constructor(name) {
        console.log(`Employee Constructor ${name}`);
    }
}

class Manager extends Employee {
    constructor() {
        console.log(`Manager Constructor`);
    }
}

let empObj = new Employee("Manish");
let manObj = new Manager("Sanjay");
```

```js
/**
 * Output:
 * Employee Constructor Manish
 * Employee Constructor undefined
 * Manager Constructor
 */
class Employee {
    constructor(name) {
        console.log(`Employee Constructor ${name}`);
    }
}

class Manager extends Employee {
    constructor() {
        super();
        console.log(`Manager Constructor`);
    }
}

let empObj = new Employee("Manish");
let manObj = new Manager("Sanjay");
```

```js
/**
 * Output:
 * Employee Constructor Manish
 * Employee Constructor Sanjay
 * Manager Constructor Sanjay
 */
class Employee {
    constructor(name) {
        console.log(`Employee Constructor ${name}`);
    }
}

class Manager extends Employee {
    constructor(name) {
        super(name);
        console.log(`Manager Constructor ${name}`);
    }
}

let empObj = new Employee("Manish");
let manObj = new Manager("Sanjay");
```

```js
/**
 * Output:
 * Employee Constructor
 * Employee Name is Kailash
 * Employee Constructor
 * Manager Constructor
 * Employee Name is Rahul
 */
class Employee {
    constructor(name) {
        this.employeeName = name;
        console.log("Employee Constructor");
    }
    empInfo() {
        console.log(`Employee Name is ${this.employeeName}`);
    }
}

class Manager extends Employee {
    constructor(name) {
        super(name);
        console.log(`Manager Constructor`);
    }
}

let empObj = new Employee("Kailash");
empObj.empInfo();

let manObj = new Manager("Rahul");
manObj.empInfo();
```

```js
/**
 * Output:
 * Employee Name is Raman
 * Manager Name is Suman
 */
class Employee {
    constructor(name) {
        this.employeeName = name;
    }
    empInfo() {
        console.log(`Employee Name is ${this.employeeName}`);
    }
}

class Manager extends Employee {
    empInfo() {
        console.log(`Manager Name is ${this.employeeName}`);
    }
}

let empObj = new Employee("Raman");
empObj.empInfo();

let manObj = new Manager("Suman");
manObj.empInfo();
```

```js
/**
 * Output:
 * Employee Name is Raman
 * Employee Name is Suman
 * Manager Name is Suman
 */
class Employee {
    constructor(name) {
        this.employeeName = name;
    }
    empInfo() {
        console.log(`Employee Name is ${this.employeeName}`);
    }
}

class Manager extends Employee {
    empInfo() {
        super.empInfo();
        console.log(`Manager Name is ${this.employeeName}`);
    }
}

let empObj = new Employee("Raman");
empObj.empInfo();

let manObj = new Manager("Suman");
manObj.empInfo();
```

```js
/**
 * Output:
 * Employee Name is Raman
 * Manager Name is Suman
 * Employee Name is Suman
 */
class Employee {
    constructor(name) {
        this.employeeName = name;
    }
    empInfo() {
        console.log(`Employee Name is ${this.employeeName}`);
    }
}

class Manager extends Employee {
    empInfo() {
        console.log(`Manager Name is ${this.employeeName}`);
        super.empInfo();
    }
}

let empObj = new Employee("Raman");
empObj.empInfo();

let manObj = new Manager("Suman");
manObj.empInfo();
```

```js
/**
 * Output:
 * Employee Details are as follows:
 * Name is Manish
 * Age is 31
 * Salary is Rs. 50000

 * Manager Details are as follows:
 * Name is Shubham
 * Age is 50
 * Total Salary is Rs. 11500
 */
class Employee {
    constructor(name, age, salary) {
        this.employeeName = name;
        this.employeeAge = age;
        this.employeeSalary = salary;
    }

    empInfo() {
        document.write(`Employee Details are as follows: <br> 
                        Name is ${this.employeeName} <br> 
                        Age is ${this.employeeAge} <br>
                        Salary is Rs. ${this.employeeSalary}
                        `);
    }
}

class Manager extends Employee {
    empInfo() {
        let ta = 1000;
        let pa = 500;
        let totalSalary = this.employeeSalary + ta + pa;
        document.write(`<br> <br>Manager Details are as follows: <br> 
                        Name is ${this.employeeName} <br> 
                        Age is ${this.employeeAge} <br>
                        Total Salary is Rs. ${totalSalary}
                    `);
    }
}

let empObj = new Employee("Manish", 31, 50000);
empObj.empInfo();

let manObj = new Manager("Shubham", 50, 10000);
manObj.empInfo();
```

# Modules
- There are two files: file1.js and file2.
- We wish to use variables, functions, and classes of file1.js into file2.js
- For this we have to use Modules and its two functions - import and export
- To work with modules you need a server either install xampp or install live server extension in VS Code
- Process of using Modules in your project is as follows:
```
file1.js
export let name = 'Manish';
export function hello() {....};
export class Employee {....};

file2.js
import {name, hello, Employee} from './file1.js';
console.log(name);
hello();
let empObj = new Employee();

<script type="module" src="./file2.js"></script>
```

```
Folder Structure of the below example
advanced-javascript.html
modules (folder)
    library.js
    main.js
```

```html
**advanced-javascript.html file**

<script type="module" src="./modules/main.js"></script>
```

```js
**library.js file**
export let message = "Hello World";

export function greet(name) {
    return `Namaste ${name}`;
}

export class Employee {
    constructor() {
        console.log("Employee Constructor Called");
    }
}

**main.js file**
import { message, greet, Employee } from "./library.js";

console.log(message);
console.log(greet("Manish"));
let empObj = new Employee();

// Output
Hello World
Namaste Manish
Employee Constructor Called
```

```js
**library.js file**
let message = "Hello World";

function greet(name) {
    return `Namaste ${name}`;
}

class Employee {
    constructor() {
        console.log("Employee Constructor Called");
    }
}

export { message, greet, Employee };

**main.js file**
import { message, greet as gre, Employee } from "./library.js";

console.log(message);
console.log(gre("Manish"));
let empObj = new Employee();

// Output
Hello World
Namaste Manish
Employee Constructor Called
```

```js
**library.js file**
let message = "Hello World";

function greet(name) {
    return `Namaste ${name}`;
}

class Employee {
    constructor() {
        console.log("Employee Constructor Called");
    }
}

export { message, greet, Employee };

**main.js file**
import * as all from "./library.js";

console.log(all.message);
console.log(all.greet("Manish"));
let empObj = new all.Employee();

// Output
Hello World
Namaste Manish
Employee Constructor Called
```

```js
# Default Function

**library.js file**
export default function () {
    console.log("This is default function which doesn't have a name.");
}

let message = "Hello World";

function greet(name) {
    return `Namaste ${name}`;
}

class Employee {
    constructor() {
        console.log("Employee Constructor Called");
    }
}

export { message, greet, Employee };

**main.js file**
import { message, greet, Employee } from "./library.js";
import { default as machine } from "./library.js"
or
import machine from "./library.js"

machine();
console.log(message);
console.log(greet("Manish"));
let empObj = new Employee();

// Output
Hello World
Namaste Manish
Employee Constructor Called
```

```js
# Aggregate Modules

**library.js file**
export function greet(name) {
    return `Namaste ${name}`;
}

**bridge.js file**
export { greet } from './library.js';

**main.js file**
import { greet } from './bridge.js';
console.log(greet("Manish"));

// Output
Namaste Manish
```

# Promises

```js
let complete = true;
let prom = new Promise(function (resolve, reject) {
    (complete) ? resolve("Successfull") : reject("Failed");
});
console.log(prom);

// Output
Promise {<fulfilled>: 'Successfull'}
```

```js
let complete = false;
let prom = new Promise(function (resolve, reject) {
    (complete) ? resolve("Successfull") : reject("Failed");
});
console.log(prom);

// Output
Promise {<rejected>: 'Failed'}
```

```js
function prom(state) {
    return new Promise(function (resolve, reject) {
        (state) ? resolve("Successfull") : reject("Failed");
    })
}
console.log(prom(true));

// Output
Promise {<fulfilled>: 'Successfull'}
```

```js
function prom(state) {
    return new Promise(function (resolve, reject) {
        (state) ? resolve("Hurray!!!") : reject("Offffooooo!!!");
    })
}
let onSuccess = (result) => {
    console.log(result);
}
let onError = (err) => {
    console.log(err);
}
prom(false).then(onSuccess).catch(onError);

// Output
Offffooooo!!!
```

```js
function prom(state) {
    console.log("Pending. Data is being fetched.");
    return new Promise(function (resolve, reject) {
        setTimeout(() => {
            (state) ? resolve("Hurray!!!") : reject("Offffooooo!!!");
        }, 3000);
    })
}
let onSuccess = (result) => {
    console.log(result);
}
let onError = (err) => {
    console.log(err);
}
prom(true).then(onSuccess).catch(onError);

// Output
Hurray!!!
```

```js
function prom(state) {
    console.log("Pending. Data is being fetched.");
    return new Promise(function (resolve, reject) {
        setTimeout(() => {
            (state) ? resolve("Hurray!!!") : reject("Offffooooo!!!");
        }, 3000);
    })
}
prom(true).then((result) => {
    console.log(result);
}).catch((err) => {
    console.log(err);
});

// Output
Hurray!!!
```

```js
function prom(a, b) {
    console.log("Pending. Data is being fetched.");
    return new Promise(function (resolve, reject) {
        setTimeout(() => {
            (a, b) ? resolve(`Your answer is ${a / b}`) : reject(`Calculation Failed.`);
        }, 3000);
    })
}
prom(5, 0).then((result) => {
    console.log(result);
}).catch((err) => {
    console.log(err);
});

// Output
Calculation Failed.
```

```js
function prom() {
    console.log("Pending. Data is being fetched.");
    return new Promise(function (resolve, reject) {
        setTimeout(() => {
            // Need jQuery to fetch data via Ajax
            $.get("https://jsonplaceholder.typicode.com/users", function (data) {
                resolve(data);
            }).fail((err) => {
                reject(`Failed to load JSON - ${err}`);
            })
        }, 3000);
    })
}
prom().then((result) => {
    console.log(result);
}).catch((err) => {
    console.log(err);
});

// Output
(10) [{…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}]
```

# Promises.all

```js
let p1 = new Promise((resolve, reject) => {
    setTimeout(() => {
        console.log("First Promise has been Resolved");
        resolve(10);
    }, 1 * 1000);
});

let p2 = new Promise((resolve, reject) => {
    setTimeout(() => {
        console.log("Second Promise has been Resolved");
        resolve(20);
    }, 2 * 1000);
});

let p3 = new Promise((resolve, reject) => {
    setTimeout(() => {
        console.log("Third Promise has been Resolved");
        resolve(30);
    }, 3 * 1000);
});

let total = 0;
Promise.all([p1, p2, p3]).then((result) => {
    for (let i in result) {
        total += result[i];
    }
    console.log(`Result is ${result}`);
    console.log(`Total is ${total}`);
}).catch((err) => {
    console.log(err);
});

// Output
First Promise has been Resolved
Second Promise has been Resolved
Third Promise has been Resolved
Result is 10,20,30
Total is 60
```

```js
let promiseCall = function (returnData, message) {
    return function (resolve, reject) {
        setTimeout(() => {
            console.log(`${message} has been resolved`);
            resolve(returnData);
        }, returnData * 100);
    }
}

let p1 = new Promise(promiseCall(40, "First"));
let p2 = new Promise(promiseCall(50, "Second"));
let p3 = new Promise(promiseCall(60, "Third"));

let total = 0;
Promise.all([p1, p2, p3]).then((result) => {
    for (let i in result) {
        total += result[i];
    }
    console.log(`Result is ${result}`);
    console.log(`Total is ${total}`);
}).catch((err) => {
    console.log(err);
});

// Output
First has been resolved
Second has been resolved
Third has been resolved
Result is 40,50,60
Total is 150
```

```js
let promiseCall = function (returnData, message) {
    return function (resolve, reject) {
        setTimeout(() => {
            console.log(`${message} has been resolved`);
            resolve(returnData);
        }, returnData * 100);
    }
}

let p1 = new Promise(promiseCall(40, "First"));
let p2 = new Promise(promiseCall(50, "Second"));
let p3 = new Promise(promiseCall(60, "Third"));
let p4 = new Promise(function (resolve, reject) {
    reject("Promise 4 failed.");
});

let total = 0;
Promise.all([p1, p2, p3, p4]).then((result) => {
    for (let i in result) {
        total += result[i];
    }
    console.log(`Result is ${result}`);
    console.log(`Total is ${total}`);
}).catch((err) => {
    console.log(`Error : ${err}`);
});

// Output
Error : Promise 4 failed.
First has been resolved
Second has been resolved
Third has been resolved
```

# Ajax

- XMLHttpRequest class is used to send request to the server.
- We get data in the form of Text, XML or JSON.
- The request process is called 'readyState' which consists of five steps:
    - 0 : request not initialized 
    - 1 : server connection established 
    - 2 : request received
    - 3 : processing request
    - 4 : request finished and response is ready
- The response has two things:
    - statusCode [200 - OK, 403 - Forbidden, 404 - Not Found]
    - responseText or responseXML