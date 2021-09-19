# How to write clean code?
I think there is not once on programmers life that we have not wondered on how to make our code clean and organized. Or like me when you saw some awesome opensource projects on github, and felt like:

![wow](assets/wondered.png)

Saying I will try to write clean code later is like cracked screen protector in your phone, which you know you need to change but nevers gives an effort to go and change it.

These are some of the technique I myself follow. Regardless of any programming language you can easily use these steps to make your code clean and organized.

### 1) Stop copy pasting code blindly from online websites.

![stackoverflow](assets/stackoverflow.png)

Yes you heard it right, though there may be barely anyone who till now hasn't used code from online sites specially from stack overflow. It isn't actually bad to copy and paste code from online sites but you should really know what you're doing before copying from other sources. If the copied code solves your issue or you got desired output doesn't really mean the code you're copying is right one. You have to check if it brings any kind of vulnerability? How many extra dependencies it brings with it. If it requires any extra dependency package that may have any kind of vulnerability. You have to make sure that code doesnot brings any kind of typos or bugs with them. Copying sphaggeti code will bring extra complexity on your codebase. So you have to think twice or any required time before copying codes from google.

### 2) Follow Proper Naming rules
While naming a variable of function always keep in mind about the purpose of it and use descriptive and unambiguous names. For example:
```js
// bad practice
let a = 25;

// good practice
let age = 25;

// bad practice
const getData = () => Promise.resolve([{id: 1, name: 'hello world'}]);

// good practice
const getUser = () => Promise.resolve([{id: 1, name: 'hello world'}]);

// bad practice
for (let i = 0; i <= 20; i++) {
	// do some thing
}

// good practice
const TotalStudents = 20;
for (let i = 0; i <= TotalStudents; i++) {
	// do some thing
}

```
choosing right name can make it much better to understand its intent. If its serves the purpose don't hesitate if expressive name becomes too long. For naming purpose be sure to follow either *camel case* or *snake case* . Never use magic never try making those constants.
In case of class name avoid using verb and use noun.
```js
// bad practice
class Info {
	// ...
}

// good practice
class Profile {
	// ...
}

```

### 3) Function rules
* Always try to make it small. Don't make it monolith. If you can break it into separate reusable chunk you should always do it.
* Make function arguments as few as possible.
```ts
// bad practice
const search = (keywords, limit, page) => Promise.resolve([]);

// good practice
interface SearchFilterInterface {
  keywords: string;
  limit: number;
  page: number;
}

const searchUsers = (filters: SearchFilterInterface) => Promise.resolve([]);
```
* Make sure the dat type of argument the function takes is always the one required by function. Don't let user pass boolean where string is needed.
* Make your function in that way that it always return consistent type. Your function should not return different data type in any cases.

### 4) Use lint checks
Most of the popular programming language have lint checker available in popular IDE they use. You can also configure lint on you specific projects. These lints helps to avoid some minor mistakes like variable, class, method naming, code duplicates, indentation error etc. beforehand. Be sure to setup project in a way that when you push your code to github repo it always checks if there are any lint error in your code.

### 5) Comment
This is one of the essential virtue a programmer should have. Always try to comment on your codes explaining the intent of your code. You should avoid commenting out code and leaving it. Its better to just remove it. Since nowdays everybody uses git, you can easily view history and revert your code if you need it again.You should not add unnecessary comment that doesnot serve any purpose. Don't make your comment redundant and obviously don't be person like below.

<img src="assets/comment.jpeg" alt="code comment" width="500"/>


### 6) Follow detail code structure
It doesn't matter how small project is, always organize your code in proper concerned folder and subfolder. Do not write multiple domain code in same files. Try to organize it with in accordance with its purpose. Don't make your code structure spaghetti. Make it easily searchable and easy to go through.

### 6) Error Handling
Error handling is vital part of programming. You should never be lazy to handle errors.  If you have implemented proper error handling your code will continue to function without crashing your project. Unhandled error can cause your program to crash, end user to lose their work and if its supports stack trace error it can even release some important information. Be sure to avoid below behavior.

![Error Handling](assets/error_handling.png)

### 7) Testing
Make sure to write tests for your code. Writing tests for code will reduce maximum chance to have error codes in your deployment environment. Keep on assert per test. While creating function or class, make sure to make it mockable and avoid unwnated and unused dependency which will make it hard to code test cases for it. Test should be independent and fast too.

### 8) Increase networking
Best way to learn clean codes is try to communicate with your team members and review each other codes and suggest them what can be done to make it more optimized, efficient and organized. You should be always ready to take positive criticism from others. You should also have learning and teamwork mentality because

![Team Work](assets/team.jpeg)

