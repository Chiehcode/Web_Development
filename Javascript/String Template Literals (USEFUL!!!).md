### String Template Literals

模版字符串（template literal）: 如果你會在 JS 中「放入 HTML 的內容」、或者有「很長的字串包含換行」、又或者會有「字串連結變數」這樣的需求，模版字符串會是非常方便的作法。

``` Javascript
let a = 5;
let b = 10;
console.log(`Fifteen is ${a + b} and not ${2 * a + b}.`);

// "Fifteen is 15 and not 20."
```

``` Javascript
let myName = "PJCHENder",
    numA = 4,
    numB = 7;

let content = `Hello, my name is ${myName}, my lucky number is ${2*(numA + numB)}`;

console.log(content);  // "Hello, my name is PJCHENder, my lucky number is 22"
```

* [Template literals (Template strings)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
* [String Template Literals -SUPER USEFUL](https://www.udemy.com/course/the-web-developer-bootcamp/learn/lecture/21935984#questions/12871580)
* https://pjchender.blogspot.com/2017/01/javascript-es6-template-literalstagged.html
