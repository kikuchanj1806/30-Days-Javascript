<div align="center">
  <h1> 30 Days Of JavaScript: Introduction</h1>
<sub>Author:
<a href="https://www.facebook.com/tung.lexuan.33449138/" target="_blank">TungLx</a><br>
<small> January, 2022</small>
</sub>
</div>

[<< Day 1](../readMe.md) | [Day 3 >>](../03_Day_Booleans_operators_date/03_booleans_operators_date.md)

![Thirty Days Of JavaScript](../images/banners/day_1_2.png)

- [📔 Day 2](#-day-2)
  - [Data Types](#data-types)
    - [Primitive Data Types](#primitive-data-types)
    - [Non-Primitive Data Types](#non-primitive-data-types)
  - [Numbers](#numbers)
    - [Declaring Number Data Types](#declaring-number-data-types)
    - [Math Object](#math-object)
      - [Random Number Generator](#random-number-generator)
  - [Strings](#strings)
    - [String Concatenation](#string-concatenation)
      - [Concatenating Using Addition Operator](#concatenating-using-addition-operator)
      - [Long Literal Strings](#long-literal-strings)
      - [Escape Sequences in Strings](#escape-sequences-in-strings)
      - [Template Literals (Template Strings)](#template-literals-template-strings)
    - [String Methods](#string-methods)
  - [Checking Data Types and Casting](#checking-data-types-and-casting)
    - [Checking Data Types](#checking-data-types)
    - [Changing Data Type (Casting)](#changing-data-type-casting)
      - [String to Int](#string-to-int)
      - [String to Float](#string-to-float)
      - [Float to Int](#float-to-int)
  - [💻 Day 2: Exercises](#-day-2-exercises)
    - [Exercise: Level 1](#exercise-level-1)
    - [Exercise: Level 2](#exercise-level-2)
    - [Exercises: Level 3](#exercises-level-3)

# 📔 Day 2

## Data Types

Trong phần trước, chúng ta đã đề cập một chút về kiểu dữ liệu. Dữ liệu hoặc giá trị có kiểu dữ liệu. Các kiểu dữ liệu mô tả các đặc tính của dữ liệu. Các loại dữ liệu có thể được chia thành hai:

1. Các kiểu dữ liệu nguyên thủy
2. Các kiểu dữ liệu không nguyên thủy (Tham chiếu đối tượng)

### Primitive Data Types

Các kiểu dữ liệu nguyên thủy trong JavaScript bao gồm:

1.  Numbers - Integers, floats
2.  Strings - Any data under single quote, double quote or backtick quote
3.  Booleans - true or false value
4.  Null - empty value or no value
5.  Undefined - a declared variable without a value

Các kiểu dữ liệu không nguyên thủy trong JavaScript bao gồm:

1. Objects
2. Functions
3. Arrays

Bây giờ, chúng ta hãy xem chính xác các kiểu dữ liệu nguyên thủy và không nguyên thủy có nghĩa là gì. Các kiểu dữ liệu nguyên thủy là các kiểu dữ liệu bất biến (không thể sửa đổi). Khi một kiểu dữ liệu nguyên thủy được tạo, chúng ta không thể sửa đổi nó.

**Example:**

```js
let word = "JavaScript";
```

Nếu chúng ta cố gắng sửa đổi chuỗi được lưu trữ trong từ biến, JavaScript sẽ gây ra lỗi. Bất kỳ loại dữ liệu nào dưới dấu ngoặc đơn, dấu nháy kép hoặc dấu ngoặc kép đều là kiểu dữ liệu chuỗi.

```js
word[0] = "Y";
```

Biểu thức này không thay đổi chuỗi được lưu trữ trong biến. Vì vậy, chúng ta có thể nói rằng các chuỗi không thể sửa đổi hay nói cách khác là bất biến. Các kiểu dữ liệu nguyên thủy được so sánh bởi các giá trị của nó. Hãy để chúng tôi so sánh các giá trị dữ liệu khác nhau. Xem ví dụ dưới đây:

```js
let numOne = 3;
let numTwo = 3;

console.log(numOne == numTwo); // true

let js = "JavaScript";
let py = "Python";

console.log(js == py); //false

let lightOn = true;
let lightOff = false;

console.log(lightOn == lightOff); // false
```

### Non-Primitive Data Types

Các kiểu dữ liệu không nguyên thủy có thể sửa đổi hoặc có thể thay đổi. Chúng tôi có thể sửa đổi giá trị của các loại dữ liệu không nguyên thủy sau khi nó được tạo. Một mảng là một danh sách các giá trị dữ liệu trong một dấu ngoặc vuông. Mảng có thể chứa các kiểu dữ liệu giống nhau hoặc khác nhau. Các giá trị mảng được tham chiếu bởi chỉ số của chúng. Trong JavaScript, chỉ mục mảng bắt đầu từ 0. Tức là, phần tử đầu tiên của một mảng được tìm thấy ở chỉ mục 0, phần tử thứ hai ở chỉ mục một và phần tử thứ ba ở chỉ mục hai, v.v.

```js
let nums = [1, 2, 3];
nums[0] = 10;

console.log(nums); // [10, 2, 3]
```

Như bạn có thể thấy, một mảng, là kiểu dữ liệu không nguyên thủy, có thể thay đổi được. Các loại dữ liệu không nguyên thủy không thể được so sánh theo giá trị. Ngay cả khi hai kiểu dữ liệu không nguyên thủy có cùng thuộc tính và giá trị, chúng cũng không hoàn toàn bằng nhau.

```js
let nums = [1, 2, 3];
let numbers = [1, 2, 3];

console.log(nums == numbers); // false

let userOne = {
  name: "Asabeneh",
  role: "teaching",
  country: "Finland",
};

let userTwo = {
  name: "Asabeneh",
  role: "teaching",
  country: "Finland",
};

console.log(userOne == userTwo); // false
```

Các giá trị không nguyên thủy được gọi là các loại tham chiếu, vì chúng được so sánh theo tham chiếu thay vì giá trị. Hai đối tượng chỉ hoàn toàn bằng nhau nếu chúng đề cập đến cùng một đối tượng cơ bản.

```js
let nums = [1, 2, 3];
let numbers = nums;

console.log(nums == numbers); // true

let userOne = {
  name: "Asabeneh",
  role: "teaching",
  country: "Finland",
};

let userTwo = userOne;

console.log(userOne == userTwo); // true
```

Nếu bạn gặp khó khăn trong việc hiểu sự khác biệt giữa kiểu dữ liệu nguyên thủy và kiểu dữ liệu không nguyên thủy, thì bạn không phải là người duy nhất. Hãy bình tĩnh và chuyển sang phần tiếp theo và cố gắng quay lại sau một thời gian. Bây giờ chúng ta hãy bắt đầu kiểu dữ liệu theo kiểu số.

## Numbers

Số là số nguyên và giá trị thập phân có thể thực hiện tất cả các phép tính số học. Hãy xem một số ví dụ về Số.

### Declaring Number Data Types

```js
let age = 35;
const gravity = 9.81; // we use const for non-changing values, gravitational constant in  m/s2
let mass = 72; // mass in Kilogram
const PI = 3.14; // pi a geometrical constant

// More Examples
const boilingPoint = 100; // temperature in oC, boiling point of water which is a constant
const bodyTemp = 37; // oC average human body temperature, which is a constant

console.log(age, gravity, mass, PI, boilingPoint, bodyTemp);
```

### Math Object

Trong JavaScript, Math Object cung cấp rất nhiều phương thức để làm việc với các con số.

```js
const PI = Math.PI;

console.log(PI); // 3.141592653589793

// Rounding to the closest number
// if above .5 up if less 0.5 down rounding

console.log(Math.round(PI)); // 3 to round values to the nearest number

console.log(Math.round(9.81)); // 10

console.log(Math.floor(PI)); // 3 rounding down

console.log(Math.ceil(PI)); // 4 rounding up

console.log(Math.min(-5, 3, 20, 4, 5, 10)); // -5, returns the minimum value

console.log(Math.max(-5, 3, 20, 4, 5, 10)); // 20, returns the maximum value

const randNum = Math.random(); // creates random number between 0 to 0.999999
console.log(randNum);

// Let us  create random number between 0 to 10

const num = Math.floor(Math.random() * 11); // creates random number between 0 and 10
console.log(num);

//Absolute value
console.log(Math.abs(-10)); // 10

//Square root
console.log(Math.sqrt(100)); // 10

console.log(Math.sqrt(2)); // 1.4142135623730951

// Power
console.log(Math.pow(3, 2)); // 9

console.log(Math.E); // 2.718

// Logarithm
// Returns the natural logarithm with base E of x, Math.log(x)
console.log(Math.log(2)); // 0.6931471805599453
console.log(Math.log(10)); // 2.302585092994046

// Trigonometry
Math.sin(0);
Math.sin(60);

Math.cos(0);
Math.cos(60);
```

#### Random Number Generator

Kỹ thuật tạo một số ngẫu nhiên bằng phương thức random trong JavaScript

```js
let randomNum = Math.random(); // generates 0 to 0.999...
```

Bây giờ, hãy xem cách chúng ta có thể sử dụng phương thức random() để tạo một số ngẫu nhiên trong khoảng từ 0 đến 10:

```js
let randomNum = Math.random(); // generates 0 to 0.999
let numBtnZeroAndTen = randomNum * 11;

console.log(numBtnZeroAndTen); // this gives: min 0 and max 10.99

let randomNumRoundToFloor = Math.floor(numBtnZeroAndTen);
console.log(randomNumRoundToFloor); // this gives between 0 and 10
```

## Strings

Các chuỗi là các văn bản, nằm dưới dấu **_nháy đơn_**, **_kép_**, **_dấu gạch ngược_**. Để khai báo một chuỗi, chúng ta cần một tên biến, toán tử gán, một giá trị trong dấu **_nháy đơn_**, **_kép_**, **_dấu gạch ngược_**. Hãy xem một số ví dụ về chuỗi:

```js
let space = " "; // an empty space string
let firstName = "Asabeneh";
let lastName = "Yetayeh";
let country = "Finland";
let city = "Helsinki";
let language = "JavaScript";
let job = "teacher";
let quote = "The saying,'Seeing is Believing' is not correct in 2020.";
let quotWithBackTick = `The saying,'Seeing is Believing' is not correct in 2020.`;
```

### String Concatenation

Kết nối hai hoặc nhiều chuỗi với nhau được gọi là nối. Sử dụng các chuỗi đã khai báo trong phần Chuỗi trước đó:

```js
let fullName = firstName + space + lastName; // concatenation, merging two string together.
console.log(fullName);
```

```sh
Asabeneh Yetayeh
```

Chúng ta có thể nối các chuỗi theo nhiều cách khác nhau.

#### Concatenating Using Addition Operator

Nối chuỗi bằng Template String.

```js
// Declaring different variables of different data types
let firstName = "Asabeneh";
let lastName = "Yetayeh";
let country = "Finland";
let city = "Helsinki";
let language = "JavaScript";
let job = "teacher";
let age = 250;
let fullName = firstName + " " + lastName;

let personInfoOne = `I am ${fullName}. I am ${age}. I live in ${country}.`; //ES6 - String interpolation method
let personInfoTwo = `I am ${fullName}. I live in ${city}, ${country}. I am a ${job}. I teach ${language}.`;

console.log(personInfoOne);
console.log(personInfoTwo);
```

```sh
Asabeneh Yetayeh. I am 250. I live in Finland
```

#### Long Literal Strings

Một chuỗi có thể là một ký tự hoặc một đoạn hoặc một trang. Nếu chiều dài chuỗi quá lớn, nó không vừa với một dòng. Chúng ta có thể sử dụng ký tự gạch chéo ngược (\) ở cuối mỗi dòng để chỉ ra rằng chuỗi sẽ tiếp tục ở dòng tiếp theo. Ví dụ:
**Example:**

```js
const paragraph =
  "My name is Asabeneh Yetayeh. I live in Finland, Helsinki.\
I am a teacher and I love teaching. I teach HTML, CSS, JavaScript, React, Redux, \
Node.js, Python, Data Analysis and D3.js for anyone who is interested to learn. \
In the end of 2019, I was thinking to expand my teaching and to reach \
to global audience and I started a Python challenge from November 20 - December 19.\
It was one of the most rewarding and inspiring experience.\
Now, we are in 2020. I am enjoying preparing the 30DaysOfJavaScript challenge and \
I hope you are enjoying too.";

console.log(paragraph);
```

#### Escape Sequences in Strings

Trong JavaScript và các ngôn ngữ lập trình khác \ theo sau bởi một số ký tự là một chuỗi thoát. Hãy xem các ký tự thoát phổ biến nhất:

- \n: new line
- \t: Tab, means 8 spaces
- \\\\: Back slash
- \\': Single quote (')
- \\": Double quote (")

```js
console.log(
  "I hope everyone is enjoying the 30 Days Of JavaScript challenge.\nDo you ?"
); // line break
console.log("Days\tTopics\tExercises");
console.log("Day 1\t3\t5");
console.log("Day 2\t3\t5");
console.log("Day 3\t3\t5");
console.log("Day 4\t3\t5");
console.log("This is a backslash  symbol (\\)"); // To write a backslash
console.log('In every programming language it starts with "Hello, World!"');
console.log("In every programming language it starts with 'Hello, World!'");
console.log("The saying 'Seeing is Believing' isn't correct in 2020");
```

Output in console:

```sh
I hope everyone is enjoying the 30 Days Of JavaScript challenge.
Do you ?
Days  Topics  Exercises
Day 1 3 5
Day 2 3 5
Day 3 3 5
Day 4 3 5
This is a backslash  symbol (\)
In every programming language it starts with "Hello, World!"
In every programming language it starts with 'Hello, World!'
The saying 'Seeing is Believing' isn't correct in 2020
```

#### Template Literals (Template Strings)

Để tạo một chuỗi mẫu, chúng ta sử dụng hai dấu tích ngược. Chúng ta có thể thêm dữ liệu dưới dạng biểu thức bên trong chuỗi mẫu. Để chèn dữ liệu, chúng tôi đặt biểu thức bằng dấu ngoặc nhọn ({}) trước dấu $. Xem cú pháp bên dưới.

```js
//Syntax
`String literal text``String literal text ${expression}`;
```

**Example: 1**

```js
console.log(`The sum of 2 and 3 is 5`); // statically writing the data
let a = 2;
let b = 3;
console.log(`The sum of ${a} and ${b} is ${a + b}`); // injecting the data dynamically
```

Sử dụng string template hoặc string interpolation method, chúng ta có thể thêm các biểu thức, có thể là một giá trị hoặc một số phép toán (so sánh, phép toán số học, phép toán bậc ba).

```js
let a = 2;
let b = 3;
console.log(`${a} is greater than ${b}: ${a > b}`);
```

```sh
2 is greater than 3: false
```

### String Methods

Mọi thứ trong JavaScript đều là một đối tượng. Một chuỗi là một kiểu dữ liệu nguyên thủy có nghĩa là chúng ta không thể sửa đổi nó sau khi nó được tạo. Đối tượng chuỗi có nhiều phương thức chuỗi. Có nhiều phương thức chuỗi khác nhau có thể giúp chúng ta làm việc với chuỗi.

1. _length_: Phương thức độ dài chuỗi trả về số lượng ký tự trong một chuỗi bao gồm khoảng trống.
   **Example:**

```js
let js = "JavaScript";
console.log(js.length); // 10
let firstName = "Asabeneh";
console.log(firstName.length); // 8
```

2. _Accessing characters in a string_: Chúng ta có thể truy cập từng ký tự trong một chuỗi bằng cách sử dụng chỉ mục của nó. Trong lập trình, việc đếm bắt đầu từ 0. Chỉ số đầu tiên của chuỗi bằng 0 và chỉ số cuối cùng là độ dài của chuỗi trừ đi một.

![Accessing sting by index](../images/string_indexes.png)

Hãy để chúng tôi truy cập các ký tự khác nhau trong chuỗi 'JavaScript'.

```js
let string = "JavaScript";
let firstLetter = string[0];

console.log(firstLetter); // J

let secondLetter = string[1]; // a
let thirdLetter = string[2];
let lastLetter = string[9];

console.log(lastLetter); // t

let lastIndex = string.length - 1;

console.log(lastIndex); // 9
console.log(string[lastIndex]); // t
```

3. _toUpperCase()_: phương pháp này thay đổi chuỗi thành chữ hoa.

```js
let string = "JavaScript";

console.log(string.toUpperCase()); // JAVASCRIPT

let firstName = "Asabeneh";

console.log(firstName.toUpperCase()); // ASABENEH

let country = "Finland";

console.log(country.toUpperCase()); // FINLAND
```

4. _toLowerCase()_: phương pháp này thay đổi chuỗi thành chữ thường.

```js
let string = "JavasCript";

console.log(string.toLowerCase()); // javascript

let firstName = "Asabeneh";

console.log(firstName.toLowerCase()); // asabeneh

let country = "Finland";

console.log(country.toLowerCase()); // finland
```

5. _substr()_: Trích xuất một chuỗi ký tự con bên trong chuỗi cha (Chuỗi con sẽ bắt đầu được trích xuất tại một vị trí xác định với số lượng ký tự được chỉ định)

```js
//syntax
let string = "JavaScript";
string.substr(start, length);
// Trong đó:
// start là chỉ số của ký tự mà bạn muốn bắt đầu trích xuất.
// length là số lượng ký tự mà bạn muốn trích xuất.

console.log(string.substr(4, 6)); // Script

let country = "Finland";
console.log(country.substr(3, 4)); // land
```

6. _substring()_: Trích xuất một chuỗi ký tự con nằm giữa hai chỉ số được chỉ định trong chuỗi cha

```js
// syntax
let string = "JavaScript";
string.substring(start, end);
// Trong đó:
// start là chỉ số của ký tự đầu tiên mà bạn muốn bắt đầu việc trích xuất.
// end là chỉ số của ký tự cuối cùng mà bạn muốn kết thúc việc trích xuất.

console.log(string.substring(0, 4)); // Java
console.log(string.substring(4, 10)); // Script
console.log(string.substring(4)); // Script

let country = "Finland";

console.log(country.substring(0, 3)); // Fin
console.log(country.substring(3, 7)); // land
console.log(country.substring(3)); // land
```

7. _split()_: Phương thức split tách một chuỗi tại một vị trí xác định.

```js
let string = "30 Days Of JavaScript";

console.log(string.split()); // Changes to an array -> ["30 Days Of JavaScript"]
console.log(string.split(" ")); // Split to an array at space -> ["30", "Days", "Of", "JavaScript"]

let firstName = "Asabeneh";

console.log(firstName.split()); // Change to an array - > ["Asabeneh"]
console.log(firstName.split("")); // Split to an array at each letter ->  ["A", "s", "a", "b", "e", "n", "e", "h"]

let countries = "Finland, Sweden, Norway, Denmark, and Iceland";

console.log(countries.split(",")); // split to any array at comma -> ["Finland", " Sweden", " Norway", " Denmark", " and Iceland"]
console.log(countries.split(", ")); //  ["Finland", "Sweden", "Norway", "Denmark", "and Iceland"]
```

8. _trim()_: Loại bỏ dấu cách ở đầu hoặc cuối chuỗi.

```js
let string = "   30 Days Of JavaScript   ";

console.log(string);
console.log(string.trim(" "));

let firstName = " Asabeneh ";

console.log(firstName);
console.log(firstName.trim()); // still removes spaces at the beginning and the end of the string
```

```sh
   30 Days Of JavasCript
30 Days Of JavasCript
  Asabeneh
Asabeneh
```

9. _includes()_: Phương thức này sử dụng để tìm kiếm một phần tử có tồn tại trong mảng hay không. Trả về dữ liệu kiểu Boolean, Nếu tìm thấy phần tử trong mảng sẽ trả về giá trị true, ngược lại trả về giá trị false

```js
let string = "30 Days Of JavaScript";

console.log(string.includes("Days")); // true
console.log(string.includes("days")); // false - it is case sensitive!
console.log(string.includes("Script")); // true
console.log(string.includes("script")); // false
console.log(string.includes("java")); // false
console.log(string.includes("Java")); // true

let country = "Finland";

console.log(country.includes("fin")); // false
console.log(country.includes("Fin")); // true
console.log(country.includes("land")); // true
console.log(country.includes("Land")); // false
```

10. _replace()_: Phương thức string.replace() có chức năng tìm kiếm một chuỗi con hoặc một biểu thức chính quy nào đó trong chuỗi sau đó thay thế nó bằng một giá trị được cung cấp bởi người dùng. Phương thức sẽ trả về chuỗi đã được thay thế mà không hề thay đổi chuỗi gốc.

```js
string.replace(oldsubstring, newsubstring);
```

```js
let string = "30 Days Of JavaScript";
console.log(string.replace("JavaScript", "Python")); // 30 Days Of Python

let country = "Finland";
console.log(country.replace("Fin", "Noman")); // Nomanland
```

11. _charAt()_: Phương thức string.charAt() có chức năng tìm kiếm kí tự ở một vị trí nào đó trong chuỗi, vị trí tìm kiếm đó sẽ do người dùng xác định.

```js
string.charAt(index);
```

```js
let string = "30 Days Of JavaScript";
console.log(string.charAt(0)); // 3

let lastIndex = string.length - 1;
console.log(string.charAt(lastIndex)); // t
```

12. _charCodeAt()_: Hàm string.charCodeAt() sẽ trả về mã unicode của kí tự tại vị trí nào đó trong chuỗi, vị trí đó được xác định bởi người dùng khi gọi phương thức.

```js
string.charCodeAt(index);
```

```js
let string = "30 Days Of JavaScript";
console.log(string.charCodeAt(3)); // D ASCII number is 68

let lastIndex = string.length - 1;
console.log(string.charCodeAt(lastIndex)); // t ASCII is 116
```

13. _indexOf()_: Hàm indexOf sẽ tìm kiếm một phần tử trong mảng dựa vào giá trị của phần tử, hàm sẽ trả về vị trị( khóa) của phần tử nếu tìm thấy và trả về -1 nếu không tìm thấy.

```js
string.indexOf(substring);
```

```js
let string = "30 Days Of JavaScript";

console.log(string.indexOf("D")); // 3
console.log(string.indexOf("Days")); // 3
console.log(string.indexOf("days")); // -1
console.log(string.indexOf("a")); // 4
console.log(string.indexOf("JavaScript")); // 11
console.log(string.indexOf("Script")); //15
console.log(string.indexOf("script")); // -1
```

14. _lastIndexOf()_: Lấy một chuỗi con và nếu chuỗi con tồn tại trong một chuỗi, nó trả về vị trí cuối cùng của chuỗi con nếu nó không tồn tại, nó trả về -1

```js
//syntax
string.lastIndexOf(substring);
```

```js
let string =
  "I love JavaScript. If you do not love JavaScript what else can you love.";

console.log(string.lastIndexOf("love")); // 67
console.log(string.lastIndexOf("you")); // 63
console.log(string.lastIndexOf("JavaScript")); // 38
```

15. _concat()_: Phương thức string.concat() có chức năng nối hai hay nhiều chuỗi lại với nhau thành một chuỗi.

```js
string.concat(substring, substring, substring);
```

```js
let string = "30";
console.log(string.concat("Days", "Of", "JavaScript")); // 30DaysOfJavaScript

let country = "Fin";
console.log(country.concat("land")); // Finland
```

16. _startsWith_: Phương thức string.startsWith() sẽ kiểm tra xem chuỗi có được bắt đầu bằng một chuỗi con được cung cấp hay không. Nó trả về một giá trị boolean (đúng hoặc sai).

```js
//syntax
string.startsWith(substring);
```

```js
let string = "Love is the best to in this world";

console.log(string.startsWith("Love")); // true
console.log(string.startsWith("love")); // false
console.log(string.startsWith("world")); // false

let country = "Finland";

console.log(country.startsWith("Fin")); // true
console.log(country.startsWith("fin")); // false
console.log(country.startsWith("land")); //  false
```

17. _endsWith_: Phương thức string.endsWith() có chức năng xác định liệu một chuỗi có kết thúc bằng một kí tự hoặc một chuỗi được người dùng cung cấp hay không. Nó trả về một giá trị boolean (đúng hoặc sai).

```js
string.endsWith(substring);
```

```js
let string = "Love is the most powerful feeling in the world";

console.log(string.endsWith("world")); // true
console.log(string.endsWith("love")); // false
console.log(string.endsWith("in the world")); // true

let country = "Finland";

console.log(country.endsWith("land")); // true
console.log(country.endsWith("fin")); // false
console.log(country.endsWith("Fin")); //  false
```

18. _search_: Phương thức string.search() tìm kiếm một chuỗi con nào đó trong chuỗi gốc, phương thức sẽ trả về vị trị xuất hiện của chuỗi con đó trong chuỗi gốc. Giá trị được tìm kiếm có thể là một chuỗi đơn giản hoặc một biểu thức chính quy. Nếu chuỗi con hoặc biểu thức chính quy không được tìm thấy trong chuỗi gốc, phương thức sẽ trả về -1.

```js
string.search(substring);
```

```js
let string =
  "I love JavaScript. If you do not love JavaScript what else can you love.";
console.log(string.search("love")); // 2
console.log(string.search(/javascript/gi)); // 7
```

19. _match_: Phương thức string.match() sẽ tìm kiếm các chuỗi con phù hợp với biểu thức chính quy được cung cấp. Phương thức sẽ trả về các chuỗi tìm được dưới dạng một mảng.

```js
let string = "love";
let patternOne = /love/; // with out any flag
let patternTwo = /love/gi; // g-means to search in the whole text, i - case insensitive
```

Match syntax

```js
// syntax
string.match(substring);
```

```js
let string =
  "I love JavaScript. If you do not love JavaScript what else can you love.";
console.log(string.match("love"));
```

```sh
["love", index: 2, input: "I love JavaScript. If you do not love JavaScript what else can you love.", groups: undefined]
```

```js
let pattern = /love/gi;
console.log(string.match(pattern)); // ["love", "love", "love"]
```

Ví dụ sử dụng biểu thức chính quy.

```js
let txt =
  "In 2019, I ran 30 Days of Python. Now, in 2020 I am super exited to start this challenge";
let regEx = /\d+/;

// d with escape character means d not a normal d instead acts a digit
// + means one or more digit numbers,
// if there is g after that it means global, search everywhere.

console.log(txt.match(regEx)); // ["2", "0", "1", "9", "3", "0", "2", "0", "2", "0"]
console.log(txt.match(/\d+/g)); // ["2019", "30", "2020"]
```

20. _repeat()_: Phương thức string.repeat() sẽ lặp lại chuỗi string với số lần nhất định được cung cấp khi gọi phương thức. Phương thức sẽ trả về một chuỗi chính là n chuỗi string nối với nhau( n là số lần lặp được xác định khi gọi phương thức).

```js
string.repeat(n);
```

```js
let string = "love";
console.log(string.repeat(10)); // lovelovelovelovelovelovelovelovelovelove
```

## Checking Data Types and Casting

### Checking Data Types

Để kiểm tra kiểu dữ liệu của một biến nào đó ta sử dụng phương thức _typeof_.

**Example:**

```js
// Different javascript data types
// Let's declare different data types

let firstName = "Asabeneh"; // string
let lastName = "Yetayeh"; // string
let country = "Finland"; // string
let city = "Helsinki"; // string
let age = 250; // number, it is not my real age, do not worry about it
let job; // undefined, because a value was not assigned

console.log(typeof "Asabeneh"); // string
console.log(typeof firstName); // string
console.log(typeof 10); // number
console.log(typeof 3.14); // number
console.log(typeof true); // boolean
console.log(typeof false); // boolean
console.log(typeof NaN); // number
console.log(typeof job); // undefined
console.log(typeof undefined); // undefined
console.log(typeof null); // object
```

### Changing Data Type (Casting)

- Casting: Chuyển đổi một kiểu dữ liệu này sang kiểu dữ liệu khác. Chúng tôi sử dụng _parseInt()_, _parseFloat()_, _Number()_, + _sign_, _str()_ Khi chúng tôi thực hiện các phép toán số học, các số chuỗi trước tiên phải được chuyển đổi thành số nguyên hoặc float nếu không nó sẽ trả về lỗi.

#### String to Int

Chúng ta có thể chuyển đổi chuỗi số thành một số. Bất kỳ số nào bên trong dấu ngoặc kép đều là số chuỗi. Một ví dụ về số chuỗi: '10', '5', v.v. Chúng ta có thể chuyển đổi chuỗi thành số bằng các phương thức sau:

- parseInt()
- Number()
- Plus sign(+)

```js
let num = "10";
let numInt = parseInt(num);
console.log(numInt); // 10
```

```js
let num = "10";
let numInt = Number(num);

console.log(numInt); // 10
```

```js
let num = "10";
let numInt = +num;

console.log(numInt); // 10
```

#### String to Float

Chúng ta có thể chuyển đổi số float của chuỗi thành số float. Bất kỳ số float nào bên trong dấu ngoặc kép đều là số float chuỗi. Một ví dụ về số float của chuỗi: '9.81', '3.14', '1.44', v.v. Chúng ta có thể chuyển đổi chuỗi float thành số bằng các phương pháp sau:

- parseFloat()
- Number()
- Plus sign(+)

```js
let num = "9.81";
let numFloat = parseFloat(num);

console.log(numFloat); // 9.81
```

```js
let num = "9.81";
let numFloat = Number(num);

console.log(numFloat); // 9.81
```

```js
let num = "9.81";
let numFloat = +num;

console.log(numInt); // 9.81
```

#### Float to Int

Chúng ta có thể chuyển đổi số float thành số nguyên. Chúng tôi sử dụng phương pháp sau để chuyển đổi float thành int:

- parseInt()

```js
let num = 9.81;
let numInt = parseInt(num);

console.log(numInt); // 9
```

🌕 You are awesome. You have just completed day 2 challenges and you are two steps ahead on your way to greatness. Now do some exercises for your brain and for your muscle.

## 💻 Day 2: Exercises

### Exercise: Level 1

1. Declare a variable named challenge and assign it to an initial value **'30 Days Of JavaScript'**.
2. Print the string on the browser console using **console.log()**
3. Print the **length** of the string on the browser console using _console.log()_
4. Change all the string characters to capital letters using **toUpperCase()** method
5. Change all the string characters to lowercase letters using **toLowerCase()** method
6. Cut (slice) out the first word of the string using **substr()** or **substring()** method
7. Slice out the phrase _Days Of JavaScript_ from _30 Days Of JavaScript_.
8. Check if the string contains a word **Script** using **includes()** method
9. Split the **string** into an **array** using **split()** method
10. Split the string 30 Days Of JavaScript at the space using **split()** method
11. 'Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon' **split** the string at the comma and change it to an array.
12. Change 30 Days Of JavaScript to 30 Days Of Python using **replace()** method.
13. What is character at index 15 in '30 Days Of JavaScript' string? Use **charAt()** method.
14. What is the character code of J in '30 Days Of JavaScript' string using **charCodeAt()**
15. Use **indexOf** to determine the position of the first occurrence of **a** in 30 Days Of JavaScript
16. Use **lastIndexOf** to determine the position of the last occurrence of **a** in 30 Days Of JavaScript.
17. Use **indexOf** to find the position of the first occurrence of the word **because** in the following sentence:**'You cannot end a sentence with because because because is a conjunction'**
18. Use **lastIndexOf** to find the position of the last occurrence of the word **because** in the following sentence:**'You cannot end a sentence with because because because is a conjunction'**
19. Use **search** to find the position of the first occurrence of the word **because** in the following sentence:**'You cannot end a sentence with because because because is a conjunction'**
20. Use **trim()** to remove any trailing whitespace at the beginning and the end of a string.E.g ' 30 Days Of JavaScript '.
21. Use **startsWith()** method with the string _30 Days Of JavaScript_ and make the result true
22. Use **endsWith()** method with the string _30 Days Of JavaScript_ and make the result true
23. Use **match()** method to find all the **a**’s in 30 Days Of JavaScript
24. Use **concat()** and merge '30 Days of' and 'JavaScript' to a single string, '30 Days Of JavaScript'
25. Use **repeat()** method to print 30 Days Of JavaScript 2 times

### Exercise: Level 2

1. Using console.log() print out the following statement:

   ```sh
   The quote 'There is no exercise better for the heart than reaching down and lifting people up.' by John Holmes teaches us to help one another.
   ```

2. Using console.log() print out the following quote by Mother Teresa:

   ```sh
   "Love is not patronizing and charity isn't about pity, it is about love. Charity and love are the same -- with charity you give love, so don't just give money but reach out your hand instead."
   ```

3. Check if typeof '10' is exactly equal to 10. If not make it exactly equal.
4. Check if parseFloat('9.8') is equal to 10 if not make it exactly equal with 10.
5. Check if 'on' is found in both python and jargon
6. _I hope this course is not full of jargon_. Check if _jargon_ is in the sentence.
7. Generate a random number between 0 and 100 inclusively.
8. Generate a random number between 50 and 100 inclusively.
9. Generate a random number between 0 and 255 inclusively.
10. Access the 'JavaScript' string characters using a random number.
11. Use console.log() and escape characters to print the following pattern.

    ```js
    1 1 1 1 1
    2 1 2 4 8
    3 1 3 9 27
    4 1 4 16 64
    5 1 5 25 125
    ```

12. Use **substr** to slice out the phrase **because because because** from the following sentence:**'You cannot end a sentence with because because because is a conjunction'**

### Exercises: Level 3

1. 'Love is the best thing in this world. Some found their love and some are still looking for their love.' Count the number of word **love** in this sentence.
2. Use **match()** to count the number of all **because** in the following sentence:**'You cannot end a sentence with because because because is a conjunction'**
3. Clean the following text and find the most frequent word (hint, use replace and regular expressions).

   ```js
   const sentence =
     "%I $am@% a %tea@cher%, &and& I lo%#ve %te@a@ching%;. The@re $is no@th@ing; &as& mo@re rewarding as educa@ting &and& @emp%o@weri@ng peo@ple. ;I found tea@ching m%o@re interesting tha@n any ot#her %jo@bs. %Do@es thi%s mo@tiv#ate yo@u to be a tea@cher!? %Th#is 30#Days&OfJavaScript &is al@so $the $resu@lt of &love& of tea&ching";
   ```

4. Calculate the total annual income of the person by extracting the numbers from the following text. 'He earns 5000 euro from salary per month, 10000 euro annual bonus, 15000 euro online courses per month.'

🎉 CONGRATULATIONS ! 🎉

[<< Day 1](../readMe.md) | [Day 3 >>](../03_Day_Booleans_operators_date/03_booleans_operators_date.md)
