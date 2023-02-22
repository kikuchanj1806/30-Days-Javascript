<div align="center">
  <h1> 30 Days Of JavaScript: Arrays</h1>
  <sub>Author:
<a href="https://www.facebook.com/tung.lexuan.33449138/" target="_blank">TungLx</a><br>
<small> January, 2022</small>
</sub>
</div>

[<< Day 4](../04_Day_Conditionals/04_day_Conditionals.md) | [Day 6 >>](../06_Day_Loops/06_day_loops.md)

![Day 5](../images/banners/day_1_5.png)

- [📔 Day 5](#-day-5)
  - [Arrays](#arrays)
    - [How to create an empty array](#how-to-create-an-empty-array)
    - [How to create an array with values](#how-to-create-an-array-with-values)
    - [Creating an array using split](#creating-an-array-using-split)
    - [Accessing array items using index](#accessing-array-items-using-index)
    - [Modifying array element](#modifying-array-element)
    - [Methods to manipulate array](#methods-to-manipulate-array)
      - [Array Constructor](#array-constructor)
      - [Creating static values with fill](#creating-static-values-with-fill)
      - [Concatenating array using concat](#concatenating-array-using-concat)
      - [Getting array length](#getting-array-length)
      - [Getting index an element in arr array](#getting-index-an-element-in-arr-array)
      - [Getting last index of an element in array](#getting-last-index-of-an-element-in-array)
      - [Checking array](#checking-array)
      - [Converting array to string](#converting-array-to-string)
      - [Joining array elements](#joining-array-elements)
      - [Slice array elements](#slice-array-elements)
      - [Splice method in array](#splice-method-in-array)
      - [Adding item to an array using push](#adding-item-to-an-array-using-push)
      - [Removing the end element using pop](#removing-the-end-element-using-pop)
      - [Removing an element from the beginning](#removing-an-element-from-the-beginning)
      - [Add an element from the beginning](#add-an-element-from-the-beginning)
      - [Reversing array order](#reversing-array-order)
      - [Sorting elements in array](#sorting-elements-in-array)
    - [Array of arrays](#array-of-arrays)
  - [💻 Exercise](#-exercise)
    - [Exercise: Level 1](#exercise-level-1)
    - [Exercise: Level 2](#exercise-level-2)
    - [Exercise: Level 3](#exercise-level-3)

# 📔 Day 5

## Arrays

Ngược lại với biến, một mảng có thể lưu trữ nhiều giá trị. Mỗi giá trị trong một mảng có một chỉ mục và mỗi chỉ mục có một tham chiếu trong một địa chỉ bộ nhớ. Mỗi giá trị có thể được truy cập bằng cách sử dụng các chỉ mục của chúng. Chỉ mục của một mảng bắt đầu từ 0 và chỉ mục của phần tử cuối cùng nhỏ hơn một so với độ dài của mảng.

Mảng là một tập hợp các loại dữ liệu khác nhau được sắp xếp theo thứ tự và có thể thay đổi (có thể sửa đổi). Một mảng cho phép lưu trữ các phần tử trùng lặp và các kiểu dữ liệu khác nhau. Một mảng có thể trống hoặc có thể có các giá trị kiểu dữ liệu khác nhau.

### How to create an empty array

Trong JavaScript, chúng ta có thể tạo một mảng theo nhiều cách khác nhau. Việc sử dụng _const_ thay vì _let_ để khai báo một biến Array là rất phổ biến. Nếu bạn đang sử dụng const, điều đó có nghĩa là bạn không thể sử dụng lại tên biến đó.

- Using Array constructor

```js
// syntax
const arr = Array();
// or
// let arr = new Array()
console.log(arr); // []
```

- Using square brackets([])

```js
// syntax
// This the most recommended way to create an empty list
const arr = [];
console.log(arr);
```

### How to create an array with values

Mảng với các giá trị ban đầu. Chúng tôi sử dụng _length_ để tính độ dài của một mảng.

```js
const numbers = [0, 3.14, 9.81, 37, 98.6, 100]; // array of numbers
const fruits = ["banana", "orange", "mango", "lemon"]; // array of strings, fruits
const vegetables = ["Tomato", "Potato", "Cabbage", "Onion", "Carrot"]; // array of strings, vegetables
const animalProducts = ["milk", "meat", "butter", "yoghurt"]; // array of strings, products
const webTechs = ["HTML", "CSS", "JS", "React", "Redux", "Node", "MongDB"]; // array of web technologies
const countries = ["Finland", "Denmark", "Sweden", "Norway", "Iceland"]; // array of strings, countries

// Print the array and its length

console.log("Numbers:", numbers);
console.log("Number of numbers:", numbers.length);

console.log("Fruits:", fruits);
console.log("Number of fruits:", fruits.length);

console.log("Vegetables:", vegetables);
console.log("Number of vegetables:", vegetables.length);

console.log("Animal products:", animalProducts);
console.log("Number of animal products:", animalProducts.length);

console.log("Web technologies:", webTechs);
console.log("Number of web technologies:", webTechs.length);

console.log("Countries:", countries);
console.log("Number of countries:", countries.length);
```

```sh
Numbers: [0, 3.14, 9.81, 37, 98.6, 100]
Number of numbers: 6
Fruits: ['banana', 'orange', 'mango', 'lemon']
Number of fruits: 4
Vegetables: ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
Number of vegetables: 5
Animal products: ['milk', 'meat', 'butter', 'yoghurt']
Number of animal products: 4
Web technologies: ['HTML', 'CSS', 'JS', 'React', 'Redux', 'Node', 'MongDB']
Number of web technologies: 7
Countries: ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']
Number of countries: 5
```

- Mảng có thể có các mục thuộc các kiểu dữ liệu khác nhau

```js
const arr = [
  "Asabeneh",
  250,
  true,
  { country: "Finland", city: "Helsinki" },
  { skills: ["HTML", "CSS", "JS", "React", "Python"] },
]; // arr containing different data types
console.log(arr);
```

### Creating an array using split

Như chúng ta đã thấy trong phần trước, chúng ta có thể tách một chuỗi ở các vị trí khác nhau và chúng ta có thể thay đổi thành một mảng. Chúng ta hãy xem các ví dụ dưới đây.

```js
let js = "JavaScript";
const charsInJavaScript = js.split("");

console.log(charsInJavaScript); // ["J", "a", "v", "a", "S", "c", "r", "i", "p", "t"]

let companiesString = "Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon";
const companies = companiesString.split(",");

console.log(companies); // ["Facebook", " Google", " Microsoft", " Apple", " IBM", " Oracle", " Amazon"]
let txt =
  "I love teaching and empowering people. I teach HTML, CSS, JS, React, Python.";
const words = txt.split(" ");

console.log(words);
// the text has special characters think how you can just get only the words
// ["I", "love", "teaching", "and", "empowering", "people.", "I", "teach", "HTML,", "CSS,", "JS,", "React,", "Python"]
```

### Accessing array items using index

Chúng ta truy cập từng phần tử trong một mảng bằng chỉ mục của chúng. Chỉ số của mảng bắt đầu từ 0. Hình bên dưới thể hiện rõ chỉ số của từng phần tử trong mảng.

![arr index](../images/array_index.png)

```js
const fruits = ["banana", "orange", "mango", "lemon"];
let firstFruit = fruits[0]; // we are accessing the first item using its index

console.log(firstFruit); // banana

secondFruit = fruits[1];
console.log(secondFruit); // orange

let lastFruit = fruits[3];
console.log(lastFruit); // lemon
// Last index can be calculated as follows

let lastIndex = fruits.length - 1;
lastFruit = fruits[lastIndex];

console.log(lastFruit); // lemon
```

```js
const numbers = [0, 3.14, 9.81, 37, 98.6, 100]; // set of numbers

console.log(numbers.length); // => to know the size of the array, which is 6
console.log(numbers); // -> [0, 3.14, 9.81, 37, 98.6, 100]
console.log(numbers[0]); //  -> 0
console.log(numbers[5]); //  -> 100

let lastIndex = numbers.length - 1;
console.log(numbers[lastIndex]); // -> 100
```

```js
const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
]; // List of web technologies

console.log(webTechs); // all the array items
console.log(webTechs.length); // => to know the size of the array, which is 7
console.log(webTechs[0]); //  -> HTML
console.log(webTechs[6]); //  -> MongoDB

let lastIndex = webTechs.length - 1;
console.log(webTechs[lastIndex]); // -> MongoDB
```

```js
const countries = [
  "Albania",
  "Bolivia",
  "Canada",
  "Denmark",
  "Ethiopia",
  "Finland",
  "Germany",
  "Hungary",
  "Ireland",
  "Japan",
  "Kenya",
]; // List of countries

console.log(countries); // -> all countries in array
console.log(countries[0]); //  -> Albania
console.log(countries[10]); //  -> Kenya

let lastIndex = countries.length - 1;
console.log(countries[lastIndex]); //  -> Kenya
```

```js
const shoppingCart = [
  "Milk",
  "Mango",
  "Tomato",
  "Potato",
  "Avocado",
  "Meat",
  "Eggs",
  "Sugar",
]; // List of food products

console.log(shoppingCart); // -> all shoppingCart in array
console.log(shoppingCart[0]); //  -> Milk
console.log(shoppingCart[7]); //  -> Sugar

let lastIndex = shoppingCart.length - 1;
console.log(shoppingCart[lastIndex]); //  -> Sugar
```

### Modifying array element

Một mảng có thể thay đổi (có thể sửa đổi). Khi một mảng được tạo, chúng ta có thể sửa đổi nội dung của các phần tử mảng.

```js
const numbers = [1, 2, 3, 4, 5];
numbers[0] = 10; // changing 1 at index 0 to 10
numbers[1] = 20; // changing  2 at index 1 to 20

console.log(numbers); // [10, 20, 3, 4, 5]

const countries = [
  "Albania",
  "Bolivia",
  "Canada",
  "Denmark",
  "Ethiopia",
  "Finland",
  "Germany",
  "Hungary",
  "Ireland",
  "Japan",
  "Kenya",
];

countries[0] = "Afghanistan"; // Replacing Albania by Afghanistan
let lastIndex = countries.length - 1;
countries[lastIndex] = "Korea"; // Replacing Kenya by Korea

console.log(countries);
```

```sh
["Afghanistan", "Bolivia", "Canada", "Denmark", "Ethiopia", "Finland", "Germany", "Hungary", "Ireland", "Japan", "Korea"]
```

### Methods to manipulate array

Có nhiều phương pháp khác nhau để thao tác với một mảng. Đây là một số phương pháp có sẵn để xử lý mảng:_Array, length, concat, indexOf, slice, splice, join, toString, includes, lastIndexOf, isArray, fill, push, pop, shift, unshift_

#### Array Constructor

Array: Để tạo một mảng.

```js
const arr = Array(); // creates an an empty array
console.log(arr);

const eightEmptyValues = Array(8); // it creates eight empty values
console.log(eightEmptyValues); // [empty x 8]
```

#### Creating static values with fill

fill: Điền vào tất cả các phần tử mảng một giá trị tĩnh

```js
const arr = Array(); // creates an an empty array
console.log(arr);

const eightXvalues = Array(8).fill("X"); // it creates eight element values filled with 'X'
console.log(eightXvalues); // ['X', 'X','X','X','X','X','X','X']

const eight0values = Array(8).fill(0); // it creates eight element values filled with '0'
console.log(eight0values); // [0, 0, 0, 0, 0, 0, 0, 0]

const four4values = Array(4).fill(4); // it creates 4 element values filled with '4'
console.log(four4values); // [4, 4, 4, 4]
```

#### Concatenating array using concat

concat: Dùng để nối 2 mảng.

```js
const firstList = [1, 2, 3];
const secondList = [4, 5, 6];
const thirdList = firstList.concat(secondList);

console.log(thirdList); // [1, 2, 3, 4, 5, 6]
```

```js
const fruits = ["banana", "orange", "mango", "lemon"]; // array of fruits
const vegetables = ["Tomato", "Potato", "Cabbage", "Onion", "Carrot"]; // array of vegetables
const fruitsAndVegetables = fruits.concat(vegetables); // concatenate the two arrays

console.log(fruitsAndVegetables);
```

```sh
["banana", "orange", "mango", "lemon", "Tomato", "Potato", "Cabbage", "Onion", "Carrot"]
```

#### Getting array length

Length: Được dùng để lấy chiều dài (số lượng phần tử) của mảng

```js
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.length); // -> 5 is the size of the array
```

#### Getting index an element in arr array

indexOf: Phương thức indexOf() sẽ kiểm tra và tra về vị trí xuất hiện đầu tiên trong chuỗi gốc của chuỗi con do người dùng cung cấp. Nếu không tìm thấy chuỗi con trong chuỗi gốc, phương thức sẽ trả về -1.

```js
const numbers = [1, 2, 3, 4, 5];

console.log(numbers.indexOf(5)); // -> 4
console.log(numbers.indexOf(0)); // -> -1
console.log(numbers.indexOf(1)); // -> 0
console.log(numbers.indexOf(6)); // -> -1
```

Kiểm tra một phần tử nếu nó tồn tại trong một mảng.

- Kiểm tra các mục trong danh sách

```js
// let us check if a banana exist in the array

const fruits = ["banana", "orange", "mango", "lemon"];
let index = fruits.indexOf("banana"); // 0

if (index != -1) {
  console.log("This fruit does exist in the array");
} else {
  console.log("This fruit does not exist in the array");
}
// This fruit does exist in the array

// we can use also ternary here
index != -1
  ? console.log("This fruit does exist in the array")
  : console.log("This fruit does not exist in the array");

// let us check if a avocado exist in the array
let indexOfAvocado = fruits.indexOf("avocado"); // -1, if the element not found index is -1
if (indexOfAvocado != -1) {
  console.log("This fruit does exist in the array");
} else {
  console.log("This fruit does not exist in the array");
}
// This fruit does not exist in the array
```

#### Getting last index of an element in array

lastIndexOf: Phương thức string.lastIndexOf() sẽ kiểm tra và tra về vị trí xuất hiện cuối cùng trong chuỗi gốc của chuỗi con do người dùng cung cấp. Nếu không tìm thấy chuỗi con trong chuỗi gốc, phương thức sẽ trả về -1.

```js
const numbers = [1, 2, 3, 4, 5, 3, 1, 2];

console.log(numbers.lastIndexOf(2)); // 7
console.log(numbers.lastIndexOf(0)); // -1
console.log(numbers.lastIndexOf(1)); //  6
console.log(numbers.lastIndexOf(4)); //  3
console.log(numbers.lastIndexOf(6)); // -1
```

includes: Phương thức string.includes() sẽ kiểm tra xem một chuỗi con được người dúng cung cấp có nằm trong chuỗi hay không. Phương thức sẽ trả về True nếu chuỗi chứa chuỗi con mà người dùng cung cấp, ngược lại sẽ trả về False.

```js
const numbers = [1, 2, 3, 4, 5];

console.log(numbers.includes(5)); // true
console.log(numbers.includes(0)); // false
console.log(numbers.includes(1)); // true
console.log(numbers.includes(6)); // false

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
]; // List of web technologies

console.log(webTechs.includes("Node")); // true
console.log(webTechs.includes("C")); // false
```

#### Checking array

Array.isArray: Để kiểm tra xem kiểu dữ liệu có phải là mảng không

```js
const numbers = [1, 2, 3, 4, 5];
console.log(Array.isArray(numbers)); // true

const number = 100;
console.log(Array.isArray(number)); // false
```

#### Converting array to string

toString: Phương thức string.toString() sẽ trả về một đối tượng kiểu chuỗi. Ta có thể sử dụng phương thức này để chuyển một mảng, một số thành kiểu chuỗi.

```js
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.toString()); // 1,2,3,4,5

const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
console.log(names.toString()); // Asabeneh,Mathias,Elias,Brook
```

#### Joining array elements

join: Hàm join sẽ nối các phần tử của mảng thành một chuỗi, các phần tử được ngăn cách nhau bởi kí tự do người dùng quy định. Nếu không truyền ký tự ngăn cách vào thì giá trị mặc định là dấu phẩy ",".

```js
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.join()); // 1,2,3,4,5

const names = ["Asabeneh", "Mathias", "Elias", "Brook"];

console.log(names.join()); // Asabeneh,Mathias,Elias,Brook
console.log(names.join("")); //AsabenehMathiasEliasBrook
console.log(names.join(" ")); //Asabeneh Mathias Elias Brook
console.log(names.join(", ")); //Asabeneh, Mathias, Elias, Brook
console.log(names.join(" # ")); //Asabeneh # Mathias # Elias # Brook

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
]; // List of web technologies

console.log(webTechs.join()); // "HTML,CSS,JavaScript,React,Redux,Node,MongoDB"
console.log(webTechs.join(" # ")); // "HTML # CSS # JavaScript # React # Redux # Node # MongoDB"
```

#### Slice array elements

Slice: Hàm slice có chức năng trích xuất một số phần tử của mảng, vị trí bắt đầu và kết thúc việc trích xuất sẽ được xác định bởi tham số truyền vào hàm.

```js
const numbers = [1, 2, 3, 4, 5];

console.log(numbers.slice()); // -> it copies all  item
console.log(numbers.slice(0)); // -> it copies all  item
console.log(numbers.slice(0, numbers.length)); // it copies all  item
console.log(numbers.slice(1, 4)); // -> [2,3,4] // it doesn't include the ending position
```

#### Splice method in array

Splice: Hàm splice sẽ thay thế một hoặc một số phần tử của mảng bằng một hoặc một số phần tử khác, lưu ý rằng số phần tử bị bỏ đi có thể ít hơn số phần tử được thêm vào và ngược lại. Nó nhận ba tham số: Vị trí bắt đầu, số lần xóa và số mục được thêm vào.

```js
const numbers = [1, 2, 3, 4, 5];

console.log(numbers.splice()); // -> remove all items
```

```js
const numbers = [1, 2, 3, 4, 5];
console.log(numbers.splice(0, 1)); // remove the first item
```

```js
const numbers = [1, 2, 3, 4, 5, 6];
console.log(numbers.splice(3, 3, 7, 8, 9)); // -> [1, 2, 3, 7, 8, 9] //it removes three item and replace three items
```

#### Adding item to an array using push

Push: Hàm push() sẽ thêm mới một hoặc nhiều phần tử vào cuối mảng, hàm trả về chiều dài của mảng mới.

```js
// syntax
const arr = ["item1", "item2", "item3"];
arr.push("new item");

console.log(arr);
// ['item1', 'item2','item3','new item']
```

```js
const numbers = [1, 2, 3, 4, 5];
numbers.push(6);

console.log(numbers); // -> [1,2,3,4,5,6]

numbers.pop(); // -> remove one item from the end
console.log(numbers); // -> [1,2,3,4,5]
```

```js
let fruits = ["banana", "orange", "mango", "lemon"];
fruits.push("apple");

console.log(fruits); // ['banana', 'orange', 'mango', 'lemon', 'apple']

fruits.push("lime");
console.log(fruits); // ['banana', 'orange', 'mango', 'lemon', 'apple', 'lime']
```

#### Removing the end element using pop

pop: Hàm array.pop() có chức năng xóa bỏ phần tử cuối cùng của mảng, hàm sẽ trả về phần tử bị xóa.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.pop(); // -> remove one item from the end

console.log(numbers); // -> [1,2,3,4]
```

#### Removing an element from the beginning

shift: Hàm shift có chức năng loại bỏ phần tử đầu tiên của mảng. Hàm sẽ trả về phần tử đó.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.shift(); // -> remove one item from the beginning

console.log(numbers); // -> [2,3,4,5]
```

#### Add an element from the beginning

unshift: Hàm unshift sẽ giúp ta thêm một hoặc nhiều phần tử vào vị trí đầu mảng, sau đó trả về chiều dài của mảng sau khi thêm.

```js
const numbers = [1, 2, 3, 4, 5];
numbers.unshift(0); // -> add one item from the beginning

console.log(numbers); // -> [0,1,2,3,4,5]
```

#### Reversing array order

reverse: Hàm reverse trong javascript có chức năng đúng với tên gọi của nó là đảo ngược thứ tự của các phần tử trong mảng. Cụ thể, phần tử đầu tiên sẽ trở thành phần tử cuối cùng, phần tử thứ 2 sẽ trở thành phần tử kế cuối..

```js
const numbers = [1, 2, 3, 4, 5];
numbers.reverse(); // -> reverse array order

console.log(numbers); // [5, 4, 3, 2, 1]

numbers.reverse();
console.log(numbers); // [1, 2, 3, 4, 5]
```

#### Sorting elements in array

sort: Hàm sort() dùng để sắp xếp các phần tử trong chính mảng đó, đồng thời sẽ kết quả đã sắp xếp đó vào một mảng mới.

```js
const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
];

webTechs.sort();
console.log(webTechs); // ["CSS", "HTML", "JavaScript", "MongoDB", "Node", "React", "Redux"]

webTechs.reverse(); // after sorting we can reverse it
console.log(webTechs); // ["Redux", "React", "Node", "MongoDB", "JavaScript", "HTML", "CSS"]
```

### Array of arrays

Mảng có thể lưu trữ các kiểu dữ liệu khác nhau kể cả chính mảng đó. Hãy để chúng tôi tạo một mảng các mảng

```js
const firstNums = [1, 2, 3];
const secondNums = [1, 4, 9];

const arrayOfArray = [
  [1, 2, 3],
  [1, 2, 3],
];
console.log(arrayOfArray[0]); // [1, 2, 3]

const frontEnd = ["HTML", "CSS", "JS", "React", "Redux"];
const backEnd = ["Node", "Express", "MongoDB"];
const fullStack = [frontEnd, backEnd];
console.log(fullStack); // [["HTML", "CSS", "JS", "React", "Redux"], ["Node", "Express", "MongoDB"]]
console.log(fullStack.length); // 2
console.log(fullStack[0]); // ["HTML", "CSS", "JS", "React", "Redux"]
console.log(fullStack[1]); // ["Node", "Express", "MongoDB"]
```

🌕 You are diligent and you have already achieved quite a lot. You have just completed day 5 challenges and you are 5 steps a head in to your way to greatness. Now do some exercises for your brain and for your muscle.

## 💻 Exercise

### Exercise: Level 1

```js
const countries = [
  "Albania",
  "Bolivia",
  "Canada",
  "Denmark",
  "Ethiopia",
  "Finland",
  "Germany",
  "Hungary",
  "Ireland",
  "Japan",
  "Kenya",
];

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
];
```

1. Declare an _empty_ array;
2. Declare an array with more than 5 number of elements
3. Find the length of your array
4. Get the first item, the middle item and the last item of the array
5. Declare an array called _mixedDataTypes_, put different data types in the array and find the length of the array. The array size should be greater than 5
6. Declare an array variable name itCompanies and assign initial values Facebook, Google, Microsoft, Apple, IBM, Oracle and Amazon
7. Print the array using _console.log()_
8. Print the number of companies in the array
9. Print the first company, middle and last company
10. Print out each company
11. Change each company name to uppercase one by one and print them out
12. Print the array like as a sentence: Facebook, Google, Microsoft, Apple, IBM,Oracle and Amazon are big IT companies.
13. Check if a certain company exists in the itCompanies array. If it exist return the company else return a company is _not found_
14. Filter out companies which have more than one 'o' without the filter method
15. Sort the array using _sort()_ method
16. Reverse the array using _reverse()_ method
17. Slice out the first 3 companies from the array
18. Slice out the last 3 companies from the array
19. Slice out the middle IT company or companies from the array
20. Remove the first IT company from the array
21. Remove the middle IT company or companies from the array
22. Remove the last IT company from the array
23. Remove all IT companies

### Exercise: Level 2

1. Create a separate countries.js file and store the countries array in to this file, create a separate file web_techs.js and store the webTechs array in to this file. Access both file in main.js file
1. First remove all the punctuations and change the string to array and count the number of words in the array

   ```js
   let text =
     "I love teaching and empowering people. I teach HTML, CSS, JS, React, Python.";
   console.log(words);
   console.log(words.length);
   ```

   ```sh
   ["I", "love", "teaching", "and", "empowering", "people", "I", "teach", "HTML", "CSS", "JS", "React", "Python"]

   13
   ```

1. In the following shopping cart add, remove, edit items

   ```js
   const shoppingCart = ["Milk", "Coffee", "Tea", "Honey"];
   ```

   - add 'Meat' in the beginning of your shopping cart if it has not been already added
   - add Sugar at the end of you shopping cart if it has not been already added
   - remove 'Honey' if you are allergic to honey
   - modify Tea to 'Green Tea'

1. In countries array check if 'Ethiopia' exists in the array if it exists print 'ETHIOPIA'. If it does not exist add to the countries list.
1. In the webTechs array check if Sass exists in the array and if it exists print 'Sass is a CSS preprocess'. If it does not exist add Sass to the array and print the array.
1. Concatenate the following two variables and store it in a fullStack variable.

   ```js
   const frontEnd = ["HTML", "CSS", "JS", "React", "Redux"];
   const backEnd = ["Node", "Express", "MongoDB"];

   console.log(fullStack);
   ```

   ```sh
   ["HTML", "CSS", "JS", "React", "Redux", "Node", "Express", "MongoDB"]
   ```

### Exercise: Level 3

1.  The following is an array of 10 students ages:

        ```js
        const ages = [19, 22, 19, 24, 20, 25, 26, 24, 25, 24]
        ```

        - Sort the array and find the min and max age
        - Find the median age(one middle item or two middle items divided by two)
        - Find the average age(all items divided by number of items)
        - Find the range of the ages(max minus min)
        - Compare the value of (min - average) and (max - average), use *abs()* method

    1.Slice the first ten countries from the [countries array](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js)

1.  Find the middle country(ies) in the [countries array](https://github.com/Asabeneh/30DaysOfJavaScript/tree/master/data/countries.js)
1.  Divide the countries array into two equal arrays if it is even. If countries array is not even , one more country for the first half.

🎉 CONGRATULATIONS ! 🎉

[<< Day 4](../04_Day_Conditionals/04_day_Conditionals.md) | [Day 6 >>](../06_Day_Loops/06_day_loops.md)
