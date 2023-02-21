<div align="center">
  <h1> 30 Days Of JavaScript: Conditionals</h1>

<sub>Author:
<a href="https://www.facebook.com/tung.lexuan.33449138/" target="_blank">TungLx</a><br>
<small> January, 2022</small>
</sub>

</div>

[<< Day 3](../03_Day_Booleans_operators_date/03_booleans_operators_date.md) | [Day 5 >>](../05_Day_Arrays/05_day_arrays.md)

![Thirty Days Of JavaScript](../images/banners/day_1_4.png)

- [📔 Day 4](#-day-4)
  - [Conditionals](#conditionals)
    - [If](#if)
    - [If Else](#if-else)
    - [If Else if Else](#if-else-if-else)
    - [Switch](#switch)
    - [Ternary Operators](#ternary-operators)
  - [💻 Exercises](#-exercises)
    - [Exercises: Level 1](#exercises-level-1)
    - [Exercises: Level 2](#exercises-level-2)
    - [Exercises: Level 3](#exercises-level-3)

# 📔 Day 4

## Conditionals

Câu lệnh điều kiện được sử dụng để đưa ra quyết định dựa trên các điều kiện khác nhau. Mặc định, các câu lệnh trong tập lệnh JavaScript được thực thi tuần tự từ trên xuống dưới. Nếu logic xử lý yêu cầu như vậy, luồng thực thi tuần tự có thể được thay đổi theo hai cách:

Thực thi có điều kiện: một khối gồm một hoặc nhiều câu lệnh sẽ được thực thi nếu một biểu thức nào đó đúng

Thực hiện lặp lại: một khối gồm một hoặc nhiều câu lệnh sẽ được thực hiện lặp đi lặp lại miễn là một biểu thức nhất định là đúng. Trong phần này, chúng ta sẽ đề cập đến các câu lệnh _if_, _else_ , _else if_. Các toán tử so sánh và logic mà chúng ta đã học trong các phần trước sẽ hữu ích ở đây.

Điều kiện có thể được thực hiện bằng cách sử dụng các cách sau:

- if
- if else
- if else if else
- switch
- ternary operator

### If

Trong JavaScript và các ngôn ngữ lập trình khác, từ khóa _if_ được sử dụng để kiểm tra xem một điều kiện có đúng không và để thực thi khối mã. Để tạo điều kiện _if_, chúng ta cần từ khóa _if_, điều kiện bên trong dấu ngoặc đơn và khối mã bên trong dấu ngoặc nhọn ({}).

```js
// syntax
if (condition) {
  //this part of code runs for truthy condition
}
```

**Example:**

```js
let num = 3;
if (num > 0) {
  console.log(`${num} is a positive number`);
}
//  3 is a positive number
```

Như bạn có thể thấy trong ví dụ về điều kiện ở trên, 3 lớn hơn 0, vì vậy nó là một số dương. Điều kiện là đúng và khối mã đã được thực thi. Tuy nhiên, nếu điều kiện là sai, chúng tôi sẽ không thấy bất kỳ kết quả nào.

```js
let isRaining = true;
if (isRaining) {
  console.log("Remember to take your rain coat.");
}
```

Điều tương tự cũng xảy ra với điều kiện thứ hai, nếu isRaining sai thì khối if sẽ không được thực thi và chúng tôi không thấy bất kỳ đầu ra nào. Để xem kết quả của một điều kiện sai, chúng ta cần có một khối khác, khối này sẽ là khối _else_.

### If Else

Nếu điều kiện đúng thì khối đầu tiên sẽ được thực thi, nếu không thì điều kiện khác sẽ được thực hiện.

```js
// syntax
if (condition) {
  // this part of code runs for truthy condition
} else {
  // this part of code runs for false condition
}
```

```js
let num = 3;
if (num > 0) {
  console.log(`${num} is a positive number`);
} else {
  console.log(`${num} is a negative number`);
}
//  3 is a positive number

num = -3;
if (num > 0) {
  console.log(`${num} is a positive number`);
} else {
  console.log(`${num} is a negative number`);
}
//  -3 is a negative number
```

```js
let isRaining = true;
if (isRaining) {
  console.log("You need a rain coat.");
} else {
  console.log("No need for a rain coat.");
}
// You need a rain coat.

isRaining = false;
if (isRaining) {
  console.log("You need a rain coat.");
} else {
  console.log("No need for a rain coat.");
}
// No need for a rain coat.
```

Điều kiện cuối cùng là sai, do đó khối khác đã được thực thi. Nếu chúng ta có nhiều hơn hai điều kiện thì sao? Trong trường hợp đó, chúng tôi sẽ sử dụng điều kiện _else if_.

### If Else if Else

```js
// syntax
if (condition) {
  // code
} else if (condition) {
  // code
} else {
  //  code
}
```

**Example:**

```js
let a = 0;
if (a > 0) {
  console.log(`${a} is a positive number`);
} else if (a < 0) {
  console.log(`${a} is a negative number`);
} else if (a == 0) {
  console.log(`${a} is zero`);
} else {
  console.log(`${a} is not a number`);
}
```

```js
// if else if else
let weather = "sunny";
if (weather === "rainy") {
  console.log("You need a rain coat.");
} else if (weather === "cloudy") {
  console.log("It might be cold, you need a jacket.");
} else if (weather === "sunny") {
  console.log("Go out freely.");
} else {
  console.log("No need for rain coat.");
}
```

### Switch

Lệnh switch case dùng để xác định một danh sách các trường hợp và trong mỗi trường hợp sẽ có một đoạn mã, khi giá trị của bạn trùng khớp với trường hợp nào thì đoạn mã của trường hợp đó sẽ được thực thi.

```js
switch (caseValue) {
  case 1:
    // code
    break;
  case 2:
    // code
    break;
  case 3:
  // code
  default:
  // code
}
```

```js
let weather = "cloudy";
switch (weather) {
  case "rainy":
    console.log("You need a rain coat.");
    break;
  case "cloudy":
    console.log("It might be cold, you need a jacket.");
    break;
  case "sunny":
    console.log("Go out freely.");
    break;
  default:
    console.log(" No need for rain coat.");
}

// Switch More Examples
let dayUserInput = prompt("What day is today ?");
let day = dayUserInput.toLowerCase();

switch (day) {
  case "monday":
    console.log("Today is Monday");
    break;
  case "tuesday":
    console.log("Today is Tuesday");
    break;
  case "wednesday":
    console.log("Today is Wednesday");
    break;
  case "thursday":
    console.log("Today is Thursday");
    break;
  case "friday":
    console.log("Today is Friday");
    break;
  case "saturday":
    console.log("Today is Saturday");
    break;
  case "sunday":
    console.log("Today is Sunday");
    break;
  default:
    console.log("It is not a week day.");
}
```

// Examples to use conditions in the cases

```js
let num = prompt("Enter number");
switch (true) {
  case num > 0:
    console.log("Number is positive");
    break;
  case num == 0:
    console.log("Numbers is zero");
    break;
  case num < 0:
    console.log("Number is negative");
    break;
  default:
    console.log("Entered value was not a number");
}
```

### Ternary Operators

Một cách khác để viết điều kiện là sử dụng toán tử bậc ba. Chúng ta đã đề cập đến điều này trong phần trước.

```js
let isRaining = true;
isRaining
  ? console.log("You need a rain coat.")
  : console.log("No need for a rain coat.");
```

🌕 You are extraordinary and you have a remarkable potential. You have just completed day 4 challenges and you are four steps ahead to your way to greatness. Now do some exercises for your brain and muscle.

## 💻 Exercises

### Exercises: Level 1

1. Get user input using prompt(“Enter your age:”). If user is 18 or older , give feedback:'You are old enough to drive' but if not 18 give another feedback stating to wait for the number of years he neds to turn 18.

   ```sh
   Enter your age: 30
   You are old enough to drive.

   Enter your age:15
   You are left with 3 years to drive.
   ```

1. Compare the values of myAge and yourAge using if … else. Based on the comparison and log the result to console stating who is older (me or you). Use prompt(“Enter your age:”) to get the age as input.

   ```sh
   Enter your age: 30
   You are 5 years older than me.
   ```

1. If a is greater than b return 'a is greater than b' else 'a is less than b'. Try to implement it in to ways

   - using if else
   - ternary operator.

   ```js
   let a = 4;
   let b = 3;
   ```

   ```sh
     4 is greater than 3
   ```

1. Even numbers are divisible by 2 and the remainder is zero. How do you check, if a number is even or not using JavaScript?

   ```sh
   Enter a number: 2
   2 is an even number

   Enter a number: 9
   9 is is an odd number.
   ```

### Exercises: Level 2

1. Write a code which can give grades to students according to theirs scores:
   - 80-100, A
   - 70-89, B
   - 60-69, C
   - 50-59, D
   - 0-49, F
1. Check if the season is Autumn, Winter, Spring or Summer.
   If the user input is :
   - September, October or November, the season is Autumn.
   - December, January or February, the season is Winter.
   - March, April or May, the season is Spring
   - June, July or August, the season is Summer
1. Check if a day is weekend day or a working day. Your script will take day as an input.

```sh
    What is the day  today? Saturday
    Saturday is a weekend.

    What is the day today? saturDaY
    Saturday is a weekend.

    What is the day today? Friday
    Friday is a working day.

    What is the day today? FrIDAy
    Friday is a working day.
```

### Exercises: Level 3

1. Write a program which tells the number of days in a month.

```sh
  Enter a month: January
  January has 31 days.

  Enter a month: JANUARY
  January has 31 day

  Enter a month: February
  February has 28 days.

  Enter a month: FEbruary
  February has 28 days.
```

1. Write a program which tells the number of days in a month, now consider leap year.

🎉 CONGRATULATIONS ! 🎉

[<< Day 3](../03_Day_Booleans_operators_date/03_booleans_operators_date.md) | [Day 5 >>](../05_Day_Arrays/05_day_arrays.md)
