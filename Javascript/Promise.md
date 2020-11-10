### Promise 應用

在寫 Javascript 時一定會看到有套件或是範例有使用到 callback function，在過往的 coding 過程中最擔心的問題就是遇到 Callback Hell，最常見的範例為：

```
doSomething(function(result) {
  doSomethingElse(result, function(newResult) {
    doThirdThing(newResult, function(finalResult) {
      console.log('Got the final result: ' + finalResult);
    }, failureCallback);
  }, failureCallback);
}, failureCallback);
```

為了避免 Callback Hell，可以使用 Promise 來幫忙處理。

### Promise 介紹
* The Promise object represents the `eventual completion (or failure)` of an `asynchronous operation` and its resulting value.
* Promise 是 Javascript 的非同步運算的物件，並且包含 `resolve(成功)`、`reject(失敗)`、`pending(處理中)` 三種狀態。

![image](https://cdn.rawgit.com/Vectaio/a76330b025baf9bcdf07cb46e5a9ef9e/raw/26c4213a93dee1c39611dcd0ec12625811b20a26/js-promise.svg)


* 主要提供了 `.then()` 以及 `.catch()` 方法讓使用者可以做 Promise Chain 去串聯方法，它的用意是讓之前的 Chain 在做完之後去執行接下來的事情。
* 新增一個 Promise 時一定要兩個參數 `(resolve & reject)`，`resolve` 用在當 Promise 裡的判斷式成功後所需要回傳的物件，而 `reject` 顧名思義就是當答案非預期時的回傳物件。

Sample
``` Javascript
function numberCondition(num){
  return new Promise(function(resolve, reject){
    if(num === 0){
      resolve("Yeah you got it, the number is 0")
    }else{
      reject(new Error('No No, your number is wrong'))
    }
  })
}

numberCondition(999)
  .then(function(result) { console.log("答對了！") })
  .catch(function(error) { console.log("糟糕，答錯了") })
```

---

### 我知道 Promise 了，那 Async/Await 跟它有什麼關係？
Promise 因為需要一直使用 `.then()`、`.catch()`，所以後來誕生了 async/await。

```
function numberCondition(num){
  let result = new Promise(function(resolve, reject){
    if(num === 0){
      resolve("Yeah you got it, the number is 0")
    }else{
     reject(new Error('No No, your number is wrong'))
    }
  })
  return result
}

(async () => {
    const result = await numberCondition(0)
    console.log(result)
})()
```

---

### Async / Await 是所謂的語法糖衣
* async/await 是一種新的語法撰寫方式，來處理「非同步事件」
* async/await 讓非同步的程式碼讀起來更像在寫「同步程式碼」
* async/await 是用來簡單化和清楚化 Promise Chain 相對複雜的結構
* async function 回傳的一樣是 Promise 物件，只是針對 promise-based 寫法進行包裝


### Async 關鍵字
async 關鍵字可以放在任意函式以前，這意味者：「我們正宣告一個非同步的函式，且這個函式會回傳一個 Promise 物件」
```
// 一般函式
function getGroupInfo() {
  return data
}

// 使用 async 函式
async function getGroupInfo() {
  return  data
}
```

### Await 關鍵字
在 async 函式中使用 await 關鍵字意味者：「我們請 JavaScript 等待這個非同步的作業完成，才展開後續的動作」

```
function getFirstInfo() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('first data')
    }, 1000);
  })
}

function getSecondInfo() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('second data')
    }, 2000);
  })
}

async function getGroupInfo() {
  // 代表等到第一筆資料回傳後，才印出結果和請求第二筆資料
  const firstInfo = await getFirstInfo()
  console.log(firstInfo)
  // 代表等到第二筆資料回傳後，才印出結果
  const secondInfo = await getSecondInfo()
  console.log(secondInfo)
}

getGroupInfo()
```

----


* https://nijialin.com/2020/06/13/learn-javascript-promise/
* [[筆記] 認識同步與非同步 — Callback + Promise + Async/Await](https://medium.com/%E9%BA%A5%E5%85%8B%E7%9A%84%E5%8D%8A%E8%B7%AF%E5%87%BA%E5%AE%B6%E7%AD%86%E8%A8%98/%E5%BF%83%E5%BE%97-%E8%AA%8D%E8%AD%98%E5%90%8C%E6%AD%A5%E8%88%87%E9%9D%9E%E5%90%8C%E6%AD%A5-callback-promise-async-await-640ea491ea64)
