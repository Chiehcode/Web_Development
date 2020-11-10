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

----


https://nijialin.com/2020/06/13/learn-javascript-promise/
