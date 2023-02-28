<div align="center">
  <h1> 30 Days Of JavaScript: Functions</h1>
     <sub>Author:
<a href="https://www.facebook.com/tung.lexuan.33449138/" target="_blank">TungLx</a><br>
<small> January, 2022</small>
</sub>
</div>

[<< Day 6](../06_Day_Loops/06_day_loops.md) | [Day 8 >>](../08_Day_Objects/08_day_objects.md)

![Thirty Days Of JavaScript](../images/banners/day_1_7.png)

- [📔 Day 7](#-day-7)
  - [Functions](#functions)
    - [Function Declaration](#function-declaration)
    - [Function without a parameter and return](#function-without-a-parameter-and-return)
    - [Function returning value](#function-returning-value)
    - [Function with a parameter](#function-with-a-parameter)
    - [Function with two parameters](#function-with-two-parameters)
    - [Function with many parameters](#function-with-many-parameters)
    - [Function with unlimited number of parameters](#function-with-unlimited-number-of-parameters)
      - [Unlimited number of parameters in regular function](#unlimited-number-of-parameters-in-regular-function)
      - [Unlimited number of parameters in arrow function](#unlimited-number-of-parameters-in-arrow-function)
    - [Anonymous Function](#anonymous-function)
    - [Expression Function](#expression-function)
    - [Self Invoking Functions](#self-invoking-functions)
    - [Arrow Function](#arrow-function)
    - [Function with default parameters](#function-with-default-parameters)
    - [Function declaration versus Arrow function](#function-declaration-versus-arrow-function)
  - [💻 Exercises](#-exercises)
    - [Exercises: Level 1](#exercises-level-1)
    - [Exercises: Level 2](#exercises-level-2)
    - [Exercises: Level 3](#exercises-level-3)

# 📔 Day 7

## Functions

Function JavaScript (hàm trong JavaScript) là một thành phần không thể thiếu trong cấu trúc chương trình. Hàm giúp chương trình trở nên rõ ràng, dễ hiểu bằng cách gộp những đoạn code lặp lại. Nhờ vậy mà việc bảo trì phần mềm cũng dễ dàng hơn.

Hiện nay, với các ứng dụng hiện đại, các function có thể là một chương trình hoàn chỉnh, chứ không phải là khái niệm tổng quát như ”subprogram” nữa. Có sự khác nhau giữa function và procedure (thủ tục) rằng sự lý tưởng của function nên trả về một giá trị còn procedure thì không ( bây giờ điều này có thể thay đổi theo ngôn ngữ lập trình).

Function có thể được khai báo hoặc tạo theo một số cách:

- _Declaration function_
- _Expression function_
- _Anonymous function_
- _Arrow function_

### Function Declaration

Chúng ta hãy xem cách khai báo một hàm và cách gọi một hàm.

```js
//declaring a function without a parameter
function functionName() {
  // code goes here
}
functionName(); // calling function by its name and with parentheses
```

### Function without a parameter and return

Hàm có thể được khai báo mà không cần tham số.

**Example:**

```js
// function without parameter,  a function which make a number square
function square() {
  let num = 2;
  let sq = num * num;
  console.log(sq);
}

square(); // 4

// function without parameter
function addTwoNumbers() {
  let numOne = 10;
  let numTwo = 20;
  let sum = numOne + numTwo;

  console.log(sum);
}

addTwoNumbers(); // a function has to be called by its name to be executed
```

```js
function printFullName() {
  let firstName = "Asabeneh";
  let lastName = "Yetayeh";
  let space = " ";
  let fullName = firstName + space + lastName;
  console.log(fullName);
}

printFullName(); // calling a function
```

### Function returning value

Hàm cũng có thể trả về giá trị, nếu hàm không trả về giá trị thì giá trị của hàm không được xác định. Hãy để chúng tôi viết các chức năng trên với return. Từ giờ trở đi, chúng ta trả lại giá trị cho một hàm thay vì in nó ra.

```js
function printFullName() {
  let firstName = "Asabeneh";
  let lastName = "Yetayeh";
  let space = " ";
  let fullName = firstName + space + lastName;
  return fullName;
}
console.log(printFullName());
```

```js
function addTwoNumbers() {
  let numOne = 2;
  let numTwo = 3;
  let total = numOne + numTwo;
  return total;
}

console.log(addTwoNumbers());
```

### Function with a parameter

Trong một hàm, chúng ta có thể truyền các loại dữ liệu khác nhau (số, chuỗi, boolean, đối tượng, hàm) làm tham số.

```js
// function with one parameter
function functionName(parm1) {
  //code goes her
}
functionName(parm1); // during calling or invoking one argument needed

function areaOfCircle(r) {
  let area = Math.PI * r * r;
  return area;
}

console.log(areaOfCircle(10)); // should be called with one argument

function square(number) {
  return number * number;
}

console.log(square(10));
```

### Function with two parameters

```js
// function with two parameters
function functionName(parm1, parm2) {
  //code goes her
}
functionName(parm1, parm2); // during calling or invoking two arguments needed
// Function without parameter doesn't take input, so lets make a function with parameters
function sumTwoNumbers(numOne, numTwo) {
  let sum = numOne + numTwo;
  console.log(sum);
}
sumTwoNumbers(10, 20); // calling functions
// If a function doesn't return it doesn't store data, so it should return

function sumTwoNumbers(numOne, numTwo) {
  let sum = numOne + numTwo;
  return sum;
}

console.log(sumTwoNumbers(10, 20));
function printFullName(firstName, lastName) {
  return `${firstName} ${lastName}`;
}
console.log(printFullName("Asabeneh", "Yetayeh"));
```

### Function with many parameters

```js
// function with multiple parameters
function functionName(parm1, parm2, parm3,...){
  //code goes here
}
functionName(parm1,parm2,parm3,...) // during calling or invoking three arguments needed


// this function takes array as a parameter and sum up the numbers in the array
function sumArrayValues(arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum = sum + arr[i];
  }
  return sum;
}
const numbers = [1, 2, 3, 4, 5];
    //calling a function
console.log(sumArrayValues(numbers));


    const areaOfCircle = (radius) => {
      let area = Math.PI * radius * radius;
      return area;
    }
console.log(areaOfCircle(10))

```

### Function with unlimited number of parameters

Đôi khi chúng ta không biết người dùng sẽ truyền vào hàm bao nhiêu đối số. Do đó, chúng ta nên biết cách viết một hàm có thể nhận số lượng đối số không giới hạn. Cách chúng tôi thực hiện có sự khác biệt đáng kể giữa function declaration (regular function) và arrow function. Chúng ta hãy xem các ví dụ cả trong function declaration và arrow function.

#### Unlimited number of parameters in regular function

Một khai báo hàm cung cấp một mảng đối số phạm vi chức năng giống như đối tượng. Bất kỳ thứ gì chúng ta chuyển làm đối số trong hàm đều có thể được truy cập từ đối tượng đối số bên trong hàm.

```js
// Let us access the arguments object
​
function sumAllNums() {
 console.log(arguments)
}

sumAllNums(1, 2, 3, 4))
// Arguments(4) [1, 2, 3, 4, callee: ƒ, Symbol(Symbol.iterator): ƒ]

```

```js
// function declaration
​
function sumAllNums() {
  let sum = 0
  for (let i = 0; i < arguments.length; i++) {
    sum += arguments[i]
  }
  return sum
}

console.log(sumAllNums(1, 2, 3, 4)) // 10
console.log(sumAllNums(10, 20, 13, 40, 10))  // 93
console.log(sumAllNums(15, 20, 30, 25, 10, 33, 40))  // 173
```

#### Unlimited number of parameters in arrow function

Arrow function không có đối tượng đối số phạm vi chức năng. Để triển khai một hàm nhận số lượng đối số không giới hạn trong Arrow function, chúng tôi sử dụng toán tử trải rộng theo sau bởi bất kỳ tên tham số nào. Bất kỳ thứ gì chúng ta truyền làm đối số trong hàm đều có thể được truy cập dưới dạng mảng trong Arrow function. Hãy để chúng tôi xem một ví dụ

```js
// Let us access the arguments object
​
const sumAllNums = (...args) => {
 // console.log(arguments), arguments object not found in arrow function
 // instead we use an a parameter followed by spread operator
 console.log(args)
}

sumAllNums(1, 2, 3, 4))
// [1, 2, 3, 4]

```

```js
// function declaration
​
const sumAllNums = (...args) => {
  let sum = 0
  for (const element of args) {
    sum += element
  }
  return sum
}

console.log(sumAllNums(1, 2, 3, 4)) // 10
console.log(sumAllNums(10, 20, 13, 40, 10))  // 93
console.log(sumAllNums(15, 20, 30, 25, 10, 33, 40))  // 173
```

### Anonymous Function

Function ẩn danh

```js
const anonymousFun = function () {
  console.log(
    "I am an anonymous function and my value is stored in anonymousFun"
  );
};
```

### Expression Function

Expression functions là các hàm ẩn danh. Sau khi chúng ta tạo một hàm không có tên và chúng ta gán nó cho một biến. Để trả về một giá trị từ hàm, chúng ta nên gọi biến. Nhìn vào ví dụ dưới đây.

```js
// Function expression
const square = function (n) {
  return n * n;
};

console.log(square(2)); // -> 4
```

### Self Invoking Functions

Hàm tự gọi là hàm ẩn danh không cần gọi để trả về giá trị.

```js
(function (n) {
  console.log(n * n);
})(2); // 4, but instead of just printing if we want to return and store the data, we do as shown below

let squaredNum = (function (n) {
  return n * n;
})(10);

console.log(squaredNum);
```

### Arrow Function

Arrow function - còn được gọi là "fat arrow", là cú pháp được mượn từ CoffeeScript (một ngôn ngữ chuyển tiếp), cú pháp này là cách ngắn gọn hơn dùng để viết function. Ở đây sử dụng kí tự =>, trông giống như một mũi tên "béo". Arrow function là một hàm vô danh và nó thay đổi cách this bind đến function. Arrow function làm code của ta trông ngắn gọn hơn, giúp đơn giản hóa function scoping cũng như từ khóa this. Arrow function hoạt động tương tự như Lambdas trong các ngôn ngữ khác như C # hay Python. Bằng cách sử dụng arrow function, chúng ta tránh được việc phải gõ từ khoá function, return và dấu ngoặc nhọn.

```js
// This is how we write normal or declaration function
// Let us change this declaration function to an arrow function
function square(n) {
  return n * n;
}

console.log(square(2)); // 4

const square = (n) => {
  return n * n;
};

console.log(square(2)); // -> 4

// if we have only one line in the code block, it can be written as follows, explicit return
const square = (n) => n * n; // -> 4
```

```js
const changeToUpperCase = (arr) => {
  const newArr = [];
  for (const element of arr) {
    newArr.push(element.toUpperCase());
  }
  return newArr;
};

const countries = ["Finland", "Sweden", "Norway", "Denmark", "Iceland"];
console.log(changeToUpperCase(countries));

// ["FINLAND", "SWEDEN", "NORWAY", "DENMARK", "ICELAND"]
```

```js
const printFullName = (firstName, lastName) => {
  return `${firstName} ${lastName}`;
};

console.log(printFullName("Asabeneh", "Yetayeh"));
```

The above function has only the return statement, therefore, we can explicitly return it as follows.

```js
const printFullName = (firstName, lastName) => `${firstName} ${lastName}`;

console.log(printFullName("Asabeneh", "Yetayeh"));
```

### Function with default parameters

Sometimes we pass default values to parameters, when we invoke the function if we do not pass an argument the default value will be used. Both function declaration and arrow function can have a default value or values.

```js
// syntax
// Declaring a function
function functionName(param = value) {
  //codes
}

// Calling function
functionName();
functionName(arg);
```

**Example:**

```js
function greetings(name = "Peter") {
  let message = `${name}, welcome to 30 Days Of JavaScript!`;
  return message;
}

console.log(greetings());
console.log(greetings("Asabeneh"));
```

```js
function generateFullName(firstName = "Asabeneh", lastName = "Yetayeh") {
  let space = " ";
  let fullName = firstName + space + lastName;
  return fullName;
}

console.log(generateFullName());
console.log(generateFullName("David", "Smith"));
```

```js
function calculateAge(birthYear, currentYear = 2019) {
  let age = currentYear - birthYear;
  return age;
}

console.log("Age: ", calculateAge(1819));
```

```js
function weightOfObject(mass, gravity = 9.81) {
  let weight = mass * gravity + " N"; // the value has to be changed to string first
  return weight;
}

console.log("Weight of an object in Newton: ", weightOfObject(100)); // 9.81 gravity at the surface of Earth
console.log("Weight of an object in Newton: ", weightOfObject(100, 1.62)); // gravity at surface of Moon
```

Let us see how we write the above functions with arrow functions

```js
// syntax
// Declaring a function
const functionName = (param = value) => {
  //codes
};

// Calling function
functionName();
functionName(arg);
```

**Example:**

```js
const greetings = (name = "Peter") => {
  let message = name + ", welcome to 30 Days Of JavaScript!";
  return message;
};

console.log(greetings());
console.log(greetings("Asabeneh"));
```

```js
const generateFullName = (firstName = "Asabeneh", lastName = "Yetayeh") => {
  let space = " ";
  let fullName = firstName + space + lastName;
  return fullName;
};

console.log(generateFullName());
console.log(generateFullName("David", "Smith"));
```

```js
const calculateAge = (birthYear, currentYear = 2019) => currentYear - birthYear;
console.log("Age: ", calculateAge(1819));
```

```js
const weightOfObject = (mass, gravity = 9.81) => mass * gravity + " N";

console.log("Weight of an object in Newton: ", weightOfObject(100)); // 9.81 gravity at the surface of Earth
console.log("Weight of an object in Newton: ", weightOfObject(100, 1.62)); // gravity at surface of Moon
```

### Function declaration versus Arrow function

It ill be covered in other time

🌕 You are a rising star, now you knew function . Now, you are super charged with the power of functions. You have just completed day 7 challenges and you are 7 steps a head in to your way to greatness. Now do some exercises for your brain and for your muscle.

## 💻 Exercises

### Exercises: Level 1

1. Declare a function _fullName_ and it print out your full name.
2. Declare a function _fullName_ and now it takes firstName, lastName as a parameter and it returns your full - name.
3. Declare a function _addNumbers_ and it takes two two parameters and it returns sum.
4. An area of a rectangle is calculated as follows: _area = length x width_. Write a function which calculates _areaOfRectangle_.
5. A perimeter of a rectangle is calculated as follows: _perimeter= 2x(length + width)_. Write a function which calculates _perimeterOfRectangle_.
6. A volume of a rectangular prism is calculated as follows: _volume = length x width x height_. Write a function which calculates _volumeOfRectPrism_.
7. Area of a circle is calculated as follows: _area = π x r x r_. Write a function which calculates _areaOfCircle_
8. Circumference of a circle is calculated as follows: _circumference = 2πr_. Write a function which calculates _circumOfCircle_
9. Density of a substance is calculated as follows:_density= mass/volume_. Write a function which calculates _density_.
10. Speed is calculated by dividing the total distance covered by a moving object divided by the total amount of time taken. Write a function which calculates a speed of a moving object, _speed_.
11. Weight of a substance is calculated as follows: _weight = mass x gravity_. Write a function which calculates _weight_.
12. Temperature in oC can be converted to oF using this formula: _oF = (oC x 9/5) + 32_. Write a function which convert oC to oF _convertCelciusToFahrenheit_.
13. Body mass index(BMI) is calculated as follows: _bmi = weight in Kg / (height x height) in m2_. Write a function which calculates _bmi_. BMI is used to broadly define different weight groups in adults 20 years old or older.Check if a person is _underweight, normal, overweight_ or _obese_ based the information given below.

    - The same groups apply to both men and women.
    - _Underweight_: BMI is less than 18.5
    - _Normal weight_: BMI is 18.5 to 24.9
    - _Overweight_: BMI is 25 to 29.9
    - _Obese_: BMI is 30 or more

14. Write a function called _checkSeason_, it takes a month parameter and returns the season:Autumn, Winter, Spring or Summer.
15. Math.max returns its largest argument. Write a function findMax that takes three arguments and returns their maximum with out using Math.max method.

    ```js
    console.log(findMax(0, 10, 5));
    10;
    console.log(findMax(0, -10, -2));
    0;
    ```

### Exercises: Level 2

1. Linear equation is calculated as follows: _ax + by + c = 0_. Write a function which calculates value of a linear equation, _solveLinEquation_.
1. Quadratic equation is calculated as follows: _ax2 + bx + c = 0_. Write a function which calculates value or values of a quadratic equation, _solveQuadEquation_.

   ```js
   console.log(solveQuadratic()); // {0}
   console.log(solveQuadratic(1, 4, 4)); // {-2}
   console.log(solveQuadratic(1, -1, -2)); // {2, -1}
   console.log(solveQuadratic(1, 7, 12)); // {-3, -4}
   console.log(solveQuadratic(1, 0, -4)); //{2, -2}
   console.log(solveQuadratic(1, -1, 0)); //{1, 0}
   ```

1. Declare a function name _printArray_. It takes array as a parameter and it prints out each value of the array.
1. Write a function name _showDateTime_ which shows time in this format: 08/01/2020 04:08 using the Date object.

   ```sh
   showDateTime()
   08/01/2020 04:08
   ```

1. Declare a function name _swapValues_. This function swaps value of x to y.

   ```js
   swapValues(3, 4); // x => 4, y=>3
   swapValues(4, 5); // x = 5, y = 4
   ```

1. Declare a function name _reverseArray_. It takes array as a parameter and it returns the reverse of the array (don't use method).

   ```js
   console.log(reverseArray([1, 2, 3, 4, 5]));
   //[5, 4, 3, 2, 1]
   console.log(reverseArray(["A", "B", "C"]));
   //['C', 'B', 'A']
   ```

1. Declare a function name _capitalizeArray_. It takes array as a parameter and it returns the - capitalizedarray.
1. Declare a function name _addItem_. It takes an item parameter and it returns an array after adding the item
1. Declare a function name _removeItem_. It takes an index parameter and it returns an array after removing an item
1. Declare a function name _sumOfNumbers_. It takes a number parameter and it adds all the numbers in that range.
1. Declare a function name _sumOfOdds_. It takes a number parameter and it adds all the odd numbers in that - range.
1. Declare a function name _sumOfEven_. It takes a number parameter and it adds all the even numbers in that - range.
1. Declare a function name evensAndOdds . It takes a positive integer as parameter and it counts number of evens and odds in the number.

   ```sh
   evensAndOdds(100);
   The number of odds are 50.
   The number of evens are 51.
   ```

1. Write a function which takes any number of arguments and return the sum of the arguments

   ```js
   sum(1, 2, 3); // -> 6
   sum(1, 2, 3, 4); // -> 10
   ```

1. Writ a function which generates a _randomUserIp_.
1. Write a function which generates a _randomMacAddress_
1. Declare a function name _randomHexaNumberGenerator_. When this function is called it generates a random hexadecimal number. The function return the hexadecimal number.

   ```sh
   console.log(randomHexaNumberGenerator());
   '#ee33df'
   ```

1. Declare a function name _userIdGenerator_. When this function is called it generates seven character id. The function return the id.

   ```sh
   console.log(userIdGenerator());
   41XTDbE
   ```

### Exercises: Level 3

1. Modify question number n . Declare a function name _userIdGeneratedByUser_. It doesn’t take any parameter but it takes two inputs using prompt(). One of the input is the number of characters and the second input is the number of ids which are supposed to be generated.

   ```sh
   userIdGeneratedByUser()
   'kcsy2
   SMFYb
   bWmeq
   ZXOYh
   2Rgxf
   '
   userIdGeneratedByUser()
   '1GCSgPLMaBAVQZ26
   YD7eFwNQKNs7qXaT
   ycArC5yrRupyG00S
   UbGxOFI7UXSWAyKN
   dIV0SSUTgAdKwStr
   '
   ```

1. Write a function name _rgbColorGenerator_ and it generates rgb colors.

   ```sh
   rgbColorGenerator()
   rgb(125,244,255)
   ```

1. Write a function **_arrayOfHexaColors_** which return any number of hexadecimal colors in an array.
1. Write a function **_arrayOfRgbColors_** which return any number of RGB colors in an array.
1. Write a function **_convertHexaToRgb_** which converts hexa color to rgb and it returns an rgb color.
1. Write a function **_convertRgbToHexa_** which converts rgb to hexa color and it returns an hexa color.
1. Write a function **_generateColors_** which can generate any number of hexa or rgb colors.

   ```js
   console.log(generateColors("hexa", 3)); // ['#a3e12f', '#03ed55', '#eb3d2b']
   console.log(generateColors("hexa", 1)); // '#b334ef'
   console.log(generateColors("rgb", 3)); // ['rgb(5, 55, 175)', 'rgb(50, 105, 100)', 'rgb(15, 26, 80)']
   console.log(generateColors("rgb", 1)); // 'rgb(33,79, 176)'
   ```

1. Call your function _shuffleArray_, it takes an array as a parameter and it returns a shuffled array
1. Call your function _factorial_, it takes a whole number as a parameter and it return a factorial of the number
1. Call your function _isEmpty_, it takes a parameter and it checks if it is empty or not
1. Call your function _sum_, it takes any number of arguments and it returns the sum.
1. Write a function called _sumOfArrayItems_, it takes an array parameter and return the sum of all the items. Check if all the array items are number types. If not give return reasonable feedback.
1. Write a function called _average_, it takes an array parameter and returns the average of the items. Check if all the array items are number types. If not give return reasonable feedback.
1. Write a function called _modifyArray_ takes array as parameter and modifies the fifth item of the array and return the array. If the array length is less than five it return 'item not found'.

   ```js
   console.log(modifyArray(['Avocado', 'Tomato', 'Potato','Mango', 'Lemon','Carrot']);
   ```

   ```sh
   ['Avocado', 'Tomato', 'Potato','Mango', 'LEMON', 'Carrot']
   ```

   ```js
   console.log(modifyArray(['Google', 'Facebook','Apple', 'Amazon','Microsoft',  'IBM']);
   ```

   ```sh
   ['Google', 'Facebook','Apple', 'Amazon','MICROSOFT',  'IBM']
   ```

   ```js
   console.log(modifyArray(['Google', 'Facebook','Apple', 'Amazon']);
   ```

   ```sh
     'Not Found'
   ```

1. Write a function called _isPrime_, which checks if a number is prime number.
1. Write a functions which checks if all items are unique in the array.
1. Write a function which checks if all the items of the array are the same data type.
1. JavaScript variable name does not support special characters or symbols except \$ or \_. Write a function **isValidVariable** which check if a variable is valid or invalid variable.
1. Write a function which returns array of seven random numbers in a range of 0-9. All the numbers must be unique.

   ```js
   sevenRandomNumbers()[(1, 4, 5, 7, 9, 8, 0)];
   ```

1. Write a function called reverseCountries, it takes countries array and first it copy the array and returns the reverse of the original array

🎉 CONGRATULATIONS ! 🎉

[<< Day 6](../06_Day_Loops/06_day_loops.md) | [Day 8 >>](../08_Day_Objects/08_day_objects.md)
