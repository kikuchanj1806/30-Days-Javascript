<div align="center">
  <h1> 30 Days Of JavaScript: Objects</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> January, 2020</small>
</sub>

</div>

[<< Day 7](../07_Day_Functions/07_day_functions.md) | [Day 9 >>](../09_Day_Higher_order_functions/09_day_higher_order_functions.md)

![Thirty Days Of JavaScript](../images/banners/day_1_8.png)

- [📔 Day 8](#-day-8)
  - [Scope](#scope)
    - [Window Scope](#window-scope)
    - [Global scope](#global-scope)
    - [Local scope](#local-scope)
  - [📔 Object](#-object)
    - [Creating an empty object](#creating-an-empty-object)
    - [Creating an objecting with values](#creating-an-objecting-with-values)
    - [Getting values from an object](#getting-values-from-an-object)
    - [Creating object methods](#creating-object-methods)
    - [Setting new key for an object](#setting-new-key-for-an-object)
    - [Object Methods](#object-methods)
      - [Getting object keys using Object.keys()](#getting-object-keys-using-objectkeys)
      - [Getting object values using Object.values()](#getting-object-values-using-objectvalues)
      - [Getting object keys and values using Object.entries()](#getting-object-keys-and-values-using-objectentries)
      - [Checking properties using hasOwnProperty()](#checking-properties-using-hasownproperty)
  - [💻 Exercises](#-exercises)
    - [Exercises: Level 1](#exercises-level-1)
    - [Exercises: Level 2](#exercises-level-2)
    - [Exercises: Level 3](#exercises-level-3)

# 📔 Day 8

## Scope

Biến là phần cơ bản trong lập trình. Chúng ta khai báo biến để lưu trữ các kiểu dữ liệu khác nhau. Để khai báo một biến, chúng ta sử dụng từ khóa var, let và const. Một biến có thể được khai báo ở các phạm vi khác nhau. Trong phần này, chúng ta sẽ xem các biến phạm vi, phạm vi của biến khi chúng ta sử dụng var hoặc let. Phạm vi biến có thể là:

- Global
- Local

Biến có thể được khai báo phạm vi toàn cầu hoặc cục bộ. Chúng ta sẽ thấy cả phạm vi toàn cầu và cục bộ. Mọi thứ được khai báo mà không có let, var hoặc const đều nằm trong phạm vi toàn cục.

### Window Scope

Nếu không dùng console.log() mở trình duyệt lên và kiểm tra, bạn sẽ thấy giá trị của a và b nếu bạn viết a hoặc b trên trình duyệt. Điều đó có nghĩa là a và b đã có sẵn trong window.

```js
//scope.js
a = "JavaScript"; // is a window scope this found anywhere
b = 10; // this is a window scope variable
function letsLearnScope() {
  console.log(a, b);
  if (true) {
    console.log(a, b);
  }
}
console.log(a, b); // accessible
```

### Global scope

Một biến được khai báo toàn cầu có thể được truy cập ở mọi nơi trong cùng một tệp. Nhưng thuật ngữ toàn cầu là tương đối. Nó có thể là toàn cầu đối với tệp hoặc nó có thể là toàn cầu so với một số khối mã.

```js
//scope.js
let a = "JavaScript"; // is a global scope it will be found anywhere in this file
let b = 10; // is a global scope it will be found anywhere in this file
function letsLearnScope() {
  console.log(a, b); // JavaScript 10, accessible
  if (true) {
    let a = "Python";
    let b = 100;
    console.log(a, b); // Python 100
  }
  console.log(a, b);
}
letsLearnScope();
console.log(a, b); // JavaScript 10, accessible
```

### Local scope

Một biến được khai báo là cục bộ chỉ có thể được truy cập trong mã khối nhất định.

- Block Scope
- Function Scope

```js
//scope.js
let a = "JavaScript"; // is a global scope it will be found anywhere in this file
let b = 10; // is a global scope it will be found anywhere in this file
function letsLearnScope() {
  console.log(a, b); // JavaScript 10, accessible
  let c = 30;
  if (true) {
    // we can access from the function and outside the function but
    // variables declared inside the if will not be accessed outside the if block
    let a = "Python";
    let b = 20;
    let d = 40;
    console.log(a, b, c); // Python 20 30
  }
  // we can not access c because c's scope is only the if block
  console.log(a, b); // JavaScript 10
}
letsLearnScope();
console.log(a, b); // JavaScript 10, accessible
```

Bây giờ, bạn đã hiểu về phạm vi. Một biến được khai báo với _var_ chỉ có phạm vi chức năng nhưng biến được khai báo với _let_ hoặc _const_ là phạm vi khối (khối chức năng, khối if, khối vòng lặp, v.v.). Khối trong JavaScript là một đoạn mã nằm giữa hai dấu ngoặc nhọn ({})

```js
//scope.js
function letsLearnScope() {
  var gravity = 9.81;
  console.log(gravity);
}
// console.log(gravity), Uncaught ReferenceError: gravity is not defined

if (true) {
  var gravity = 9.81;
  console.log(gravity); // 9.81
}
console.log(gravity); // 9.81

for (var i = 0; i < 3; i++) {
  console.log(i); // 1, 2, 3
}
console.log(i);
```

let và const được giới thiệu trong ES6. Câu hỏi đặt ra ở đây là nó khác gì với var? Trong phần này, chúng ta sẽ thảo luận về scope.

```js
//scope.js
function letsLearnScope() {
  // you can use let or const, but gravity is constant I prefer to use const
  const gravity = 9.81;
  console.log(gravity);
}
// console.log(gravity), Uncaught ReferenceError: gravity is not defined

if (true) {
  const gravity = 9.81;
  console.log(gravity); // 9.81
}
// console.log(gravity), Uncaught ReferenceError: gravity is not defined

for (let i = 0; i < 3; i++) {
  console.log(i); // 1, 2, 3
}
// console.log(i), Uncaught ReferenceError: gravity is not defined
```

Phạm vi let và const giống nhau. Sự khác biệt chỉ là gán lại. Chúng ta không thể thay đổi hoặc gán lại giá trị của biến const. Tôi thực sự khuyên bạn nên sử dụng let và const, bằng cách sử dụng let và const, bạn sẽ viết mã rõ ràng và tránh được những lỗi khó gỡ lỗi. Theo quy tắc chung, bạn có thể sử dụng let cho bất kỳ giá trị nào thay đổi, const cho bất kỳ giá trị không đổi nào và cho một array, object, arrow function và function expression.

## 📔 Object

Như các bạn đã biết, Javascript có 5 kiểu dữ liệu Number, String, Boolean, Undefined và Null và còn 1 kiểu khác nữa đó là Object (kiểu dữ liệu phức hợp). Kiểu Object là kiểu được sử dụng nhiều nhất vì tính linh hoạt cực kỳ mạnh mẽ của nó trong việc xử lý dữ liệu.

Trong JavaScript, một object là một thực thể độc lập, với thuộc tính và kiểu. Lấy cái tách làm ví dụ. Cái tách là một object có những thuộc tính của riêng nó. Một cái tách có màu sắc, thiết kế, trọng lượng, chất liệu tạo ra nó, vân vân... Tương tự như vậy, JavaScript objects có thể có những thuộc tính định nghĩa nên đặc tính của nó.

object trong Javascript là một tập hợp các cặp khóa - giá trị, tương tự như bản đồ, từ điển, hay hash-table trong ngôn ngữ lập trình khác.

- object là một tập hợp các thuộc tính
- Thuộc tính là một cặp khóa - giá trị chứa tên và giá trị
- Tên thuộc tính là một giá trị duy nhất có thể bị ép buộc vào một chuỗi và trỏ đến một giá trị
- Giá trị thuộc tính có thể là bất kỳ giá trị nào, bao gồm các object khác hoặc các hàm, được liên kết với tên/khóa

### Creating an empty object

Object rỗng

```js
const person = {};
```

### Creating an objecting with values

Bây giờ, object người có tên, họ, tuổi, vị trí, kỹ năng và thuộc tính isMarried. Giá trị của các thuộc tính hoặc khóa có thể là một chuỗi, số, boolean, một object, null, không xác định hoặc một hàm.

Chúng ta hãy xem một số ví dụ về object. Mỗi khóa có một giá trị trong object.

```js
const rectangle = {
  length: 20,
  width: 20,
};
console.log(rectangle); // {length: 20, width: 20}

const person = {
  firstName: "Asabeneh",
  lastName: "Yetayeh",
  age: 250,
  country: "Finland",
  city: "Helsinki",
  skills: [
    "HTML",
    "CSS",
    "JavaScript",
    "React",
    "Node",
    "MongoDB",
    "Python",
    "D3.js",
  ],
  isMarried: true,
};
console.log(person);
```

### Getting values from an object

Chúng ta có thể truy cập các giá trị của đối tượng bằng hai phương thức:

- using . followed by key name if the key-name is a one word
- using square bracket and a quote

```js
const person = {
  firstName: "Asabeneh",
  lastName: "Yetayeh",
  age: 250,
  country: "Finland",
  city: "Helsinki",
  skills: [
    "HTML",
    "CSS",
    "JavaScript",
    "React",
    "Node",
    "MongoDB",
    "Python",
    "D3.js",
  ],
  getFullName: function () {
    return `${this.firstName}${this.lastName}`;
  },
  "phone number": "+3584545454545",
};

// accessing values using .
console.log(person.firstName);
console.log(person.lastName);
console.log(person.age);
console.log(person.location);

// value can be accessed using square bracket and key name
console.log(person["firstName"]);
console.log(person["lastName"]);
console.log(person["age"]);
console.log(person["age"]);
console.log(person["location"]);

// for instance to access the phone number we only use the square bracket method
console.log(person["phone number"]);
```

### Creating object methods

Creating object methods là cách tạo ra các phương thức cho object trong JavaScript. Một phương thức là một hàm được gán cho một thuộc tính của object và có thể được gọi thông qua object đó. Các phương thức có thể được sử dụng để thực hiện các hành động hoặc tính toán trên các thuộc tính của object đó hoặc để thực hiện một số hành động khác liên quan đến object.

```js
const person = {
  firstName: "Asabeneh",
  lastName: "Yetayeh",
  age: 250,
  country: "Finland",
  city: "Helsinki",
  skills: [
    "HTML",
    "CSS",
    "JavaScript",
    "React",
    "Node",
    "MongoDB",
    "Python",
    "D3.js",
  ],
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};

console.log(person.getFullName());
// Asabeneh Yetayeh
```

### Setting new key for an object

Một đối tượng là một cấu trúc dữ liệu có thể thay đổi và chúng ta có thể sửa đổi nội dung của một đối tượng sau khi nó được tạo.

Thiết lập một khóa mới trong một đối tượng

```js
const person = {
  firstName: "Asabeneh",
  lastName: "Yetayeh",
  age: 250,
  country: "Finland",
  city: "Helsinki",
  skills: [
    "HTML",
    "CSS",
    "JavaScript",
    "React",
    "Node",
    "MongoDB",
    "Python",
    "D3.js",
  ],
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};
person.nationality = "Ethiopian";
person.country = "Finland";
person.title = "teacher";
person.skills.push("Meteor");
person.skills.push("SasS");
person.isMarried = true;

person.getPersonInfo = function () {
  let skillsWithoutLastSkill = this.skills
    .splice(0, this.skills.length - 1)
    .join(", ");
  let lastSkill = this.skills.splice(this.skills.length - 1)[0];

  let skills = `${skillsWithoutLastSkill}, and ${lastSkill}`;
  let fullName = this.getFullName();
  let statement = `${fullName} is a ${this.title}.\nHe lives in ${this.country}.\nHe teaches ${skills}.`;
  return statement;
};
console.log(person);
console.log(person.getPersonInfo());
```

```sh
Asabeneh Yetayeh is a teacher.
He lives in Finland.
He teaches HTML, CSS, JavaScript, React, Node, MongoDB, Python, D3.js, Meteor, and SasS.
```

### Object Methods

_Object.assign_: Để sao chép một đối tượng mà không sửa đổi đối tượng ban đầu

```js
const person = {
  firstName: "Asabeneh",
  age: 250,
  country: "Finland",
  city: "Helsinki",
  skills: ["HTML", "CSS", "JS"],
  title: "teacher",
  address: {
    street: "Heitamienkatu 16",
    pobox: 2002,
    city: "Helsinki",
  },
  getPersonInfo: function () {
    return `I am ${this.firstName} and I live in ${this.city}, ${this.country}. I am ${this.age}.`;
  },
};

//Object methods: Object.assign, Object.keys, Object.values, Object.entries
//hasOwnProperty

const copyPerson = Object.assign({}, person);
console.log(copyPerson);
```

#### Getting object keys using Object.keys()

_Object.keys_: Để lấy các khóa hoặc thuộc tính của một đối tượng dưới dạng một mảng

```js
const keys = Object.keys(copyPerson);
console.log(keys); //['name', 'age', 'country', 'skills', 'address', 'getPersonInfo']
const address = Object.keys(copyPerson.address);
console.log(address); //['street', 'pobox', 'city']
```

#### Getting object values using Object.values()

_Object.values_:Để lấy các giá trị của một đối tượng dưới dạng một mảng

```js
const values = Object.values(copyPerson);
console.log(values);
```

#### Getting object keys and values using Object.entries()

_Object.entries_:Để lấy các khóa và giá trị trong một mảng

```js
const entries = Object.entries(copyPerson);
console.log(entries);
```

#### Checking properties using hasOwnProperty()

_hasOwnProperty_: Để kiểm tra xem một khóa hoặc thuộc tính cụ thể có tồn tại trong một đối tượng không

```js
console.log(copyPerson.hasOwnProperty("name"));
console.log(copyPerson.hasOwnProperty("score"));
```

🌕 You are astonishing. Now, you are super charged with the power of objects. You have just completed day 8 challenges and you are 8 steps a head in to your way to greatness. Now do some exercises for your brain and for your muscle.

## 💻 Exercises

### Exercises: Level 1

1. Create an empty object called dog
1. Print the the dog object on the console
1. Add name, legs, color, age and bark properties for the dog object. The bark property is a method which return _woof woof_
1. Get name, legs, color, age and bark value from the dog object
1. Set new properties the dog object: breed, getDogInfo

### Exercises: Level 2

1. Find the person who has many skills in the users object.
1. Count logged in users,count users having greater than equal to 50 points from the following object.

   ````js
   const users = {
     Alex: {
       email: 'alex@alex.com',
       skills: ['HTML', 'CSS', 'JavaScript'],
       age: 20,
       isLoggedIn: false,
       points: 30
     },
     Asab: {
       email: 'asab@asab.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'Redux', 'MongoDB', 'Express', 'React', 'Node'],
       age: 25,
       isLoggedIn: false,
       points: 50
     },
     Brook: {
       email: 'daniel@daniel.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux'],
       age: 30,
       isLoggedIn: true,
       points: 50
     },
     Daniel: {
       email: 'daniel@alex.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'Python'],
       age: 20,
       isLoggedIn: false,
       points: 40
     },
     John: {
       email: 'john@john.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux', 'Node.js'],
       age: 20,
       isLoggedIn: true,
       points: 50
     },
     Thomas: {
       email: 'thomas@thomas.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React'],
       age: 20,
       isLoggedIn: false,
       points: 40
     },
     Paul: {
       email: 'paul@paul.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'MongoDB', 'Express', 'React', 'Node'],
       age: 20,
       isLoggedIn: false,
       points: 40
     }
   }```

   ````

1. Find people who are MERN stack developer from the users object
1. Set your name in the users object without modifying the original users object
1. Get all keys or properties of users object
1. Get all the values of users object
1. Use the countries object to print a country name, capital, populations and languages.

### Exercises: Level 3

1. Create an object literal called _personAccount_. It has _firstName, lastName, incomes, expenses_ properties and it has _totalIncome, totalExpense, accountInfo,addIncome, addExpense_ and _accountBalance_ methods. Incomes is a set of incomes and its description and expenses is a set of incomes and its description.
2. \*\*\*\* Questions:2, 3 and 4 are based on the following two arrays:users and products ()

```js
const users = [
  {
    _id: "ab12ex",
    username: "Alex",
    email: "alex@alex.com",
    password: "123123",
    createdAt: "08/01/2020 9:00 AM",
    isLoggedIn: false,
  },
  {
    _id: "fg12cy",
    username: "Asab",
    email: "asab@asab.com",
    password: "123456",
    createdAt: "08/01/2020 9:30 AM",
    isLoggedIn: true,
  },
  {
    _id: "zwf8md",
    username: "Brook",
    email: "brook@brook.com",
    password: "123111",
    createdAt: "08/01/2020 9:45 AM",
    isLoggedIn: true,
  },
  {
    _id: "eefamr",
    username: "Martha",
    email: "martha@martha.com",
    password: "123222",
    createdAt: "08/01/2020 9:50 AM",
    isLoggedIn: false,
  },
  {
    _id: "ghderc",
    username: "Thomas",
    email: "thomas@thomas.com",
    password: "123333",
    createdAt: "08/01/2020 10:00 AM",
    isLoggedIn: false,
  },
];

const products = [
  {
    _id: "eedfcf",
    name: "mobile phone",
    description: "Huawei Honor",
    price: 200,
    ratings: [
      { userId: "fg12cy", rate: 5 },
      { userId: "zwf8md", rate: 4.5 },
    ],
    likes: [],
  },
  {
    _id: "aegfal",
    name: "Laptop",
    description: "MacPro: System Darwin",
    price: 2500,
    ratings: [],
    likes: ["fg12cy"],
  },
  {
    _id: "hedfcg",
    name: "TV",
    description: "Smart TV:Procaster",
    price: 400,
    ratings: [{ userId: "fg12cy", rate: 5 }],
    likes: ["fg12cy"],
  },
];
```

Imagine you are getting the above users collection from a MongoDB database.
a. Create a function called signUp which allows user to add to the collection. If user exists, inform the user that he has already an account.  
 b. Create a function called signIn which allows user to sign in to the application

3. The products array has three elements and each of them has six properties.
   a. Create a function called rateProduct which rates the product
   b. Create a function called averageRating which calculate the average rating of a product

4. Create a function called likeProduct. This function will helps to like to the product if it is not liked and remove like if it was liked.

🎉 CONGRATULATIONS ! 🎉

[<< Day 7](../07_Day_Functions/07_day_functions.md) | [Day 9 >>](../09_Day_Higher_order_functions/09_day_higher_order_functions.md)
