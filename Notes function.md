### v8

javascript engine

open-source JS engine

 [Google Chrome](https://en.wikipedia.org/wiki/Google_Chrome) and [Chromium](https://en.wikipedia.org/wiki/Chromium_(web_browser)) web browsers

used in [Couchbase](https://en.wikipedia.org/wiki/Couchbase), [MongoDB](https://en.wikipedia.org/wiki/MongoDB) and [Node.js](https://en.wikipedia.org/wiki/Node.js) that are used server-side.



## abbreviation

####GO:global context

####EC:exection context

####AO:activation object

####VO:variable object



# Functions

## Function Declaration

- The name of the function.
- A list of parameters to the function, enclosed in parentheses and separated by commas.
- The JavaScript statements that define the function, enclosed in curly brackets, `{ }`

- have its body hoisted

- ```javascript
  foo(); // 'FOOOOO'
  function foo() {
    console.log('FOOOOO');
  }
  ```

if the function changes the value of the parameter, **this change is not reflected globally or in the calling function**.



If you pass an object (i.e. a non-primitive value, such as [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) or a user-defined object) as a parameter and the function changes the object's properties, that change is visible outside the function, as shown in the following example:

## Function Expression

- can be **anonymous**
- convenient when passing a function as an argument to another function

```javascript
foo(); // Uncaught TypeError: foo is not a function
var foo = function() {
  console.log('FOOOOO');
};
```

## Arrow Function

 alternative to a regular [function expression

## Syntax

**parameter**

**①** 如果箭头函数没有参数，直接写一个空括号即可。

**②** 如果箭头函数的参数只有一个，也可以省去包裹参数的括号。

**③** 如果箭头函数有多个参数，将参数依次用逗号(,)分隔，包裹在括号中即可

**body**

**①** 只有一句代码

- 就是简单返回某个变量或者返回一个简单的JS表达式，可以省去函数体的大括号{ }。

- 返回一个对象:

  - ```javascript
    let getTempItem = id => ({ id: id, name: "Temp" });
    ```

- 不需要返回值

```javascript
let fn = () => void doesNotReturn();
```

### Different

1. 箭头函数没有`prototype`(原型)，所以箭头函数本身没有this
2. 箭头函数的this在定义的时候继承自外层第一个普通函数的this。
3. 如果箭头函数外层没有普通函数，严格模式和非严格模式下它的this都会指向`window`(全局对象)
4. 箭头函数本身的this指向不能改变，但可以修改它要继承的对象的this。
5. 箭头函数的this指向全局，使用arguments会报未声明的错误。
6. 箭头函数的this指向普通函数时,它的`argumens`继承于该普通函数
7. 使用`new`调用箭头函数会报错，因为箭头函数没有`constructor`
8. 箭头函数不支持`new.target`
9. 箭头函数不支持重命名函数参数,普通函数的函数参数支持重命名
10. 箭头函数相对于普通函数语法更简洁优雅

### 注意事项及不适用场景

1. 箭头函数一条语句返回对象字面量，需要加括号
2. 箭头函数在参数和箭头之间不能换行
3. 箭头函数的解析顺序相对`||`靠前

**不适用场景**：箭头函数的this意外指向和代码的可读性

### Pros

- the value of this gets set at the time of the function creation and can't change after that

-  if you are passing around your arrow function to different parts of your application, you wouldn't have to worry about the context changing. 
- helpful in React class components