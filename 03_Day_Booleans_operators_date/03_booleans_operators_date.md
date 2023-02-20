<div align="center">
  <h1> 30 Days Of JavaScript: Booleans, Operators, Date</h1>
<sub>Author:
<a href="https://www.facebook.com/tung.lexuan.33449138/" target="_blank">TungLx</a><br>
<small> January, 2022</small>
</sub>
</div>

[<< Day 2](../02_Day_Data_types/02_day_data_types.md) | [Day 4 >>](../04_Day_Conditionals/04_day_conditionals.md)

![Thirty Days Of JavaScript](../images/banners/day_1_3.png)

- [📔 Day 3](#-day-3)
  - [Booleans](#booleans)
    - [Truthy values](#truthy-values)
    - [Falsy values](#falsy-values)
  - [Undefined](#undefined)
  - [Null](#null)
  - [Operators](#operators)
    - [Assignment operators](#assignment-operators)
    - [Arithmetic Operators](#arithmetic-operators)
    - [Comparison Operators](#comparison-operators)
    - [Logical Operators](#logical-operators)
    - [Increment Operator](#increment-operator)
    - [Decrement Operator](#decrement-operator)
    - [Ternary Operators](#ternary-operators)
    - [Operator Precendence](#operator-precendence)
  - [Window Methods](#window-methods)
    - [Window alert() method](#window-alert-method)
  - [Date Object](#date-object)
    - [Creating a time object](#creating-a-time-object)
    - [Getting full year](#getting-full-year)
    - [Getting month](#getting-month)
    - [Getting date](#getting-date)
    - [Getting day](#getting-day)
    - [Getting hours](#getting-hours)
    - [Getting minutes](#getting-minutes)
    - [Getting seconds](#getting-seconds)
    - [Getting time](#getting-time)
  - [💻 Day 3: Exercises](#-day-3-exercises)
    - [Exercises: Level 1](#exercises-level-1)
    - [Exercises: Level 2](#exercises-level-2)
    - [Exercises: Level 3](#exercises-level-3)

# 📔 Day 3

## Booleans

Kiểu dữ liệu boolean đại diện cho một trong hai giá trị: đúng hoặc sai. Giá trị Boolean là true hoặc false. Việc sử dụng các kiểu dữ liệu này sẽ rõ ràng khi bạn khởi động toán tử so sánh. Bất kỳ phép so sánh nào cũng trả về một giá trị boolean đúng hoặc sai.

**Example: Boolean Values**

```js
let isLightOn = true;
let isRaining = false;
let isHungry = false;
let isMarried = true;
let truValue = 4 > 3; // true
let falseValue = 4 < 3; // false
```

- JavaScript sử dụng Type conversion(chuyển đổi dữ liệu từ kiểu dữ liệu này sang kiểu dữ liệu khác) để ép giá trị bất kỳ thành một giá trị Boolean trong một ngữ cảnh yêu cầu giá trị Boolean.
- Truthy và falsy là những giá trị mà JavaScript khi ép về kiểu Boolean, hoặc trong một ngữ cảnh Boolean, nó sẽ cho ra giá trị true hoặc false.

### Truthy values

- All numbers(positive and negative) are truthy except zero
- All strings are truthy
- The boolean true

### Falsy values

- 0
- 0n
- null
- undefined
- NaN
- the boolean false
- '', "", ``, empty string

## Undefined

Nếu chúng ta khai báo một biến và không gán giá trị, thì giá trị đó sẽ không được xác định. Ngoài ra, nếu một hàm không trả về giá trị, nó sẽ không được xác định.

```js
let firstName;
console.log(firstName); //not defined, because it is not assigned to a value yet
```

## Null

```js
let empty = null;
console.log(empty); // -> null , means no value
```

## Operators

### Assignment operators

Dấu bằng trong JavaScript là toán tử gán. Nó dùng để gán một biến.

```js
let firstName = "Asabeneh";
let country = "Finland";
```

Assignment Operators

![Assignment operators](../images/assignment_operators.png)

### Arithmetic Operators

Arithmetic operators are mathematical operators.

- Addition(+): a + b
- Subtraction(-): a - b
- Multiplication(_): a _ b
- Division(/): a / b
- Modulus(%): a % b
- Exponential(**): a ** b

```js
let numOne = 4;
let numTwo = 3;
let sum = numOne + numTwo;
let diff = numOne - numTwo;
let mult = numOne * numTwo;
let div = numOne / numTwo;
let remainder = numOne % numTwo;
let powerOf = numOne ** numTwo;

console.log(sum, diff, mult, div, remainder, powerOf); // 7,1,12,1.33,1, 64
```

```js
const PI = 3.14;
let radius = 100; // length in meter

//Let us calculate area of a circle
const areaOfCircle = PI * radius * radius;
console.log(areaOfCircle); //  314 m

const gravity = 9.81; // in m/s2
let mass = 72; // in Kilogram

// Let us calculate weight of an object
const weight = mass * gravity;
console.log(weight); // 706.32 N(Newton)

const boilingPoint = 100; // temperature in oC, boiling point of water
const bodyTemp = 37; // body temperature in oC

// Concatenating string with numbers using string interpolation
/*
 The boiling point of water is 100 oC.
 Human body temperature is 37 oC.
 The gravity of earth is 9.81 m/s2.
 */
console.log(
  `The boiling point of water is ${boilingPoint} oC.\nHuman body temperature is ${bodyTemp} oC.\nThe gravity of earth is ${gravity} m / s2.`
);
```

### Comparison Operators

Trong lập trình, chúng ta so sánh các giá trị, chúng ta sử dụng các toán tử so sánh để so sánh hai giá trị. Chúng ta kiểm tra xem một giá trị lớn hơn hay nhỏ hơn hoặc bằng giá trị khác.

![Comparison Operators](../images/comparison_operators.png)
**Example: Comparison Operators**

```js
console.log(3 > 2); // true, because 3 is greater than 2
console.log(3 >= 2); // true, because 3 is greater than 2
console.log(3 < 2); // false,  because 3 is greater than 2
console.log(2 < 3); // true, because 2 is less than 3
console.log(2 <= 3); // true, because 2 is less than 3
console.log(3 == 2); // false, because 3 is not equal to 2
console.log(3 != 2); // true, because 3 is not equal to 2
console.log(3 == "3"); // true, compare only value
console.log(3 === "3"); // false, compare both value and data type
console.log(3 !== "3"); // true, compare both value and data type
console.log(3 != 3); // false, compare only value
console.log(3 !== 3); // false, compare both value and data type
console.log(0 == false); // true, equivalent
console.log(0 === false); // false, not exactly the same
console.log(0 == ""); // true, equivalent
console.log(0 == " "); // true, equivalent
console.log(0 === ""); // false, not exactly the same
console.log(1 == true); // true, equivalent
console.log(1 === true); // false, not exactly the same
console.log(undefined == null); // true
console.log(undefined === null); // false
console.log(NaN == NaN); // false, not equal
console.log(NaN === NaN); // false
console.log(typeof NaN); // number

console.log("mango".length == "avocado".length); // false
console.log("mango".length != "avocado".length); // true
console.log("mango".length < "avocado".length); // true
console.log("milk".length == "meat".length); // true
console.log("milk".length != "meat".length); // false
console.log("tomato".length == "potato".length); // true
console.log("python".length > "dragon".length); // false
```

### Logical Operators

Các ký hiệu sau đây là các toán tử logic phổ biến: &&(dấu và) , ||(hoặc) và !(phủ định). Toán tử && chỉ đúng nếu hai toán hạng là đúng. Toán tử || trở thành true nếu một trong hai toán hạng là true. Toán tử ! phủ định true thành false và false thành true.

```js
// && ampersand operator example

const check = 4 > 3 && 10 > 5; // true && true -> true
const check = 4 > 3 && 10 < 5; // true && false -> false
const check = 4 < 3 && 10 < 5; // false && false -> false

// || pipe or operator, example

const check = 4 > 3 || 10 > 5; // true  || true -> true
const check = 4 > 3 || 10 < 5; // true  || false -> true
const check = 4 < 3 || 10 < 5; // false || false -> false

//! Negation examples

let check = 4 > 3; // true
let check = !(4 > 3); //  false
let isLightOn = true;
let isLightOff = !isLightOn; // false
let isMarried = !false; // true
```

### Increment Operator

Trong JavaScript, chúng tôi sử dụng toán tử gia tăng để tăng giá trị được lưu trữ trong một biến:

1. Pre-increment

```js
let count = 0;
console.log(++count); // 1
console.log(count); // 1
```

1. Post-increment

```js
let count = 0;
console.log(count++); // 0
console.log(count); // 1
```

### Decrement Operator

Trong JavaScript, chúng tôi sử dụng toán tử giảm để giảm giá trị được lưu trữ trong một biến:

1. Pre-decrement

```js
let count = 0;
console.log(--count); // -1
console.log(count); // -1
```

2. Post-decrement

```js
let count = 0;
console.log(count--); // 0
console.log(count); // -1
```

### Ternary Operators

Javascript ternary cũng giống như điều kiện javascript if else. Ternary operator giúp lập trình viên có thể nhanh chóng check một điều kiện trong javascript.

```js
//Syntax ternary operator javascript

expression ? if true : if not true

```

Javascript ternary được sử dụng để rút ngắn câu lệnh khi check một điều kiện. Điều này có ích để trả về một giá trị nhanh chóng (nghĩa là để gán nó đến một biến khác). Giờ ta đi xem xét một số ví dụ

````js
let isRaining = true;
isRaining
  ? console.log("You need a rain coat.")
  : console.log("No need for a rain coat.");
isRaining = false;

isRaining
  ? console.log("You need a rain coat.")
  : console.log("No need for a rain coat.");

```sh
You need a rain coat.
No need for a rain coat.
````

```js
let number = 5;
number > 0
  ? console.log(`${number} is a positive number`)
  : console.log(`${number} is a negative number`);
number = -5;

number > 0
  ? console.log(`${number} is a positive number`)
  : console.log(`${number} is a negative number`);
```

```sh
5 is a positive number
-5 is a negative number
```

- Mặc dù trông có vẻ rất hữu ích trong việc check conditions javascript, nhưng conditions ternary lại không hợp lệ trong những trường hợp sau:

# không thể break khi dùng ternary operator

```js
let animal = 'kitty';
for (let i = 0; i < 5; ++i) {
 (animal === 'kitty') ? break: console.log(i);
}
```

# không thể return khi dùng ternary operator

```js
var animal = 'kitty';
(animal === 'kitty') ? return 'meow' : return 'woof';
```

mà phải như thế này:

```js
var animal = "kitty";
return animal === "kitty" ? "meow" : "woof";
```

### Operator Precendence

Các bạn có thể thảm khảo thêm tại đây [link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence)

## Window Methods

### Window alert() method

Như bạn đã thấy ngay từ đầu, phương thức alert() hiển thị một hộp cảnh báo với một thông báo được chỉ định và một nút OK. Nó là một phương thức dựng sẵn và nó có đối số.

```js
alert(message);
```

```js
alert("Welcome to 30DaysOfJavaScript");
```

## Date Object

Trong JavaScript, thời gian và ngày hiện tại được tạo bằng cách sử dụng JavaScript Date Object. Trong Javascript tổng cộng có 10 hàm thiết lập thời gian thông dụng:

# Các hàm nhóm Date Get trong Javascript:

```sh

getDate() lấy ngày (1 - 31)
getDay() lấy ngày trong tuần (0-6)
getFullYear() lấy năm đầy đủ (YYYY)
getYear() lấy năm 2 số cuối (YY)
getHours() lấy số giờ (0 - 23)
getMiliSeconds() lấy số mili giây (0 - 999)
getMinutes() lấy số phút (0 - 59)
getMonth() lấy tháng (0 - 11)
getSeconds() lấy số giây (0 - 59)
getTime() thời gian đã được convert sang dạng miliseconds.**

```

### Creating a time object

Cách sử dụng các hàm trên khá đơn giản, vì nó là các phương thức của đối tượng Date nên bạn chỉ việc gọi ra và dùng.

Khi chúng ta tạo đối tượng thời gian. Đối tượng time sẽ cung cấp thông tin về thời gian.

```js
const now = new Date();
console.log(now); // Sat Jan 04 2020 00:56:41 GMT+0200 (Eastern European Standard Time)
```

### Getting full year

Hãy trích xuất hoặc lấy cả năm từ một đối tượng thời gian.

```js
const now = new Date();
console.log(now.getFullYear()); // 2020
```

### Getting month

Hãy trích xuất hoặc lấy tháng từ một đối tượng thời gian.

```js
const now = new Date();
console.log(now.getMonth()); // 0, because the month is January,  month(0-11)
```

### Getting date

Hãy trích xuất hoặc lấy ngày tháng từ một đối tượng thời gian.

```js
const now = new Date();
console.log(now.getDate()); // 4, because the day of the month is 4th,  day(1-31)
```

### Getting day

Hãy trích xuất hoặc lấy ngày trong tuần từ một đối tượng thời gian.

```js
const now = new Date();
console.log(now.getDay()); // 6, because the day is Saturday which is the 7th day
//  Sunday is 0, Monday is 1 and Saturday is 6
// Getting the weekday as a number (0-6)
```

### Getting hours

Hãy trích xuất hoặc lấy số giờ từ một đối tượng thời gian.

```js
const now = new Date();
console.log(now.getHours()); // 0, because the time is 00:56:41
```

### Getting minutes

Hãy trích xuất hoặc lấy số phút từ một đối tượng thời gian.

```js
const now = new Date();
console.log(now.getMinutes()); // 56, because the time is 00:56:41
```

### Getting seconds

Hãy trích xuất hoặc lấy giây từ một đối tượng thời gian.

```js
const now = new Date();
console.log(now.getSeconds()); // 41, because the time is 00:56:41
```

### Getting time

1. Using _getTime()_

```js
const now = new Date(); //
console.log(now.getTime()); // 1578092201341, this is the number of seconds passed from January 1, 1970 to January 4, 2020 00:56:41
```

1. Using _Date.now()_

```js
const allSeconds = Date.now(); //
console.log(allSeconds); // 1578092201341, this is the number of seconds passed from January 1, 1970 to January 4, 2020 00:56:41

const timeInSeconds = new Date().getTime();
console.log(allSeconds == timeInSeconds); // true
```

**Example:**

```js
const now = new Date();
const year = now.getFullYear(); // return year
const month = now.getMonth() + 1; // return month(0 - 11)
const date = now.getDate(); // return date (1 - 31)
const hours = now.getHours(); // return number (0 - 23)
const minutes = now.getMinutes(); // return number (0 -59)

console.log(`${date}/${month}/${year} ${hours}:${minutes}`); // 4/1/2020 0:56
```

# Các nhàm nhóm Date Set trong Javascript

Tương ứng với mỗi hàm Date Get thì sẽ có một hàm Date Set (trừ hàm getDay()).

```sh

setDate() thiết lập ngày (1 - 31)
setFullYear() thiết lập năm đầy đủ (YYYY)
setYear() thiết lậpnăm 2 số cuối (YY)
setHours() thiết lập số giờ (0 - 23)
setMiliSeconds() thiết lập số mili giây (0 - 999)
setMinutes() thiết lập số phút (0 - 59)
setMonth() thiết lập tháng (0 - 11)
setSeconds() thiết lập số giây (0 - 59)
setTime() thiết lập thời gian đã được convert sang dạng miliseconds.

```

_Lưu ý_:

- Vì đây là hàm set nên bạn phải truyền tham số vào.
- Các hàm có ảnh hưởng lẫn nhau nhé các bạn, ví dụ bạn thiết lập ngày giờ không đúng thì nó sẽ lấy ngày giờ mặc định.
- Nếu bạn dùng hàm setTime() để thiết lập thì nó ảnh hưởng tới tất cả các giá trị còn lại bởi vì setTime() là hàm thiết lập thời gian đầy đủ đã chuyển sang dạng miniseconds.

```sh
// Đối tượng thời gian hiện tại
var d = new Date();

d.setDate(20);
d.setFullYear(2011);
d.setHours(2);
d.setMilliseconds(2);
d.setMinutes(3);
d.setMonth(4);
d.setSeconds(5);

```

🌕 You have boundless energy. You have just completed day 3 challenges and you are three steps a head in to your way to greatness. Now do some exercises for your brain and for your muscle.

## 💻 Day 3: Exercises

### Exercises: Level 1

1. Declare firstName, lastName, country, city, age, isMarried, year variable and assign value to it and use the typeof operator to check different data types.
2. Check if type of '10' is equal to 10
3. Check if parseInt('9.8') is equal to 10
4. Boolean value is either true or false.

   1. Write three JavaScript statement which provide truthy value.
   2. Write three JavaScript statement which provide falsy value.

5. Figure out the result of the following comparison expression first without using console.log(). After you decide the result confirm it using console.log()

   1. 4 > 3
   2. 4 >= 3
   3. 4 < 3
   4. 4 <= 3
   5. 4 == 4
   6. 4 === 4
   7. 4 != 4
   8. 4 !== 4
   9. 4 != '4'
   10. 4 == '4'
   11. 4 === '4'
   12. Find the length of python and jargon and make a falsy comparison statement.

6. Figure out the result of the following expressions first without using console.log(). After you decide the result confirm it by using console.log()

   1. 4 > 3 && 10 < 12
   2. 4 > 3 && 10 > 12
   3. 4 > 3 || 10 < 12
   4. 4 > 3 || 10 > 12
   5. !(4 > 3)
   6. !(4 < 3)
   7. !(false)
   8. !(4 > 3 && 10 < 12)
   9. !(4 > 3 && 10 > 12)
   10. !(4 === '4')
   11. There is no 'on' in both dragon and python

7. Use the Date object to do the following activities
   1. What is the year today?
   2. What is the month today as a number?
   3. What is the date today?
   4. What is the day today as a number?
   5. What is the hours now?
   6. What is the minutes now?
   7. Find out the numbers of seconds elapsed from January 1, 1970 to now.

### Exercises: Level 2

1. Write a script that prompt the user to enter base and height of the triangle and calculate an area of a triangle (area = 0.5 x b x h).

   ```sh
   Enter base: 20
   Enter height: 10
   The area of the triangle is 50
   ```

1. Write a script that prompt the user to enter side a, side b, and side c of the triangle and and calculate the perimeter of triangle (perimeter = a + b + c)

   ```sh
   Enter side a: 5
   Enter side b: 4
   Enter side c: 3
   The perimeter of the triangle is 12
   ```

1. Get length and width using prompt and calculate an area of rectangle (area = length x width and the perimeter of rectangle (perimeter = 2 x (length + width))
1. Get radius using prompt and calculate the area of a circle (area = pi x r x r) and circumference of a circle(c = 2 x pi x r) where pi = 3.14.
1. Calculate the slope, x-intercept and y-intercept of y = 2x -2
1. Slope is (m = y2-y1/x2-x1). Find the slope between point (2, 2) and point(6,10)
1. Compare the slope of above two questions.
1. Calculate the value of y (y = x^2 + 6x + 9). Try to use different x values and figure out at what x value y is 0.
1. Writ a script that prompt a user to enter hours and rate per hour. Calculate pay of the person?

   ```sh
   Enter hours: 40
   Enter rate per hour: 28
   Your weekly earning is 1120
   ```

1. If the length of your name is greater than 7 say, your name is long else say your name is short.
1. Compare your first name length and your family name length and you should get this output.

   ```js
   let firstName = "Asabeneh";
   let lastName = "Yetayeh";
   ```

   ```sh
   Your first name, Asabeneh is longer than your family name, Yetayeh
   ```

1. Declare two variables _myAge_ and _yourAge_ and assign them initial values and myAge and yourAge.

   ```js
   let myAge = 250;
   let yourAge = 25;
   ```

   ```sh
   I am 225 years older than you.
   ```

1. Using prompt get the year the user was born and if the user is 18 or above allow the user to drive if not tell the user to wait a certain amount of years.

   ```sh

   Enter birth year: 1995
   You are 25. You are old enough to drive

   Enter birth year: 2005
   You are 15. You will be allowed to drive after 3 years.
   ```

1. Write a script that prompt the user to enter number of years. Calculate the number of seconds a person can live. Assume some one lives just hundred years

   ```sh
   Enter number of yours you live: 100
   You lived 3153600000 seconds.
   ```

1. Create a human readable time format using the Date time object
   1. YYYY-MM-DD HH:mm
   2. DD-MM-YYYY HH:mm
   3. DD/MM/YYYY HH:mm

### Exercises: Level 3

1. Create a human readable time format using the Date time object. The hour and the minute should be all the time two digits(7 hours should be 07 and 5 minutes should be 05 )
   1. YYY-MM-DD HH:mm eg. 20120-01-02 07:05

[<< Day 2](../02_Day_Data_types/02_day_data_types.md) | [Day 4 >>](../04_Day_Conditionals/04_day_conditionals.md)
