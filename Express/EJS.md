### EJS

EJS 的全名是「Embedded Javascript」，顧名思義就是內嵌式的樣板引擎，可以將邏輯與內容直接嵌入到 HTML 頁面上。

---

### app.js
```
var express = require('express');
var app = express();
app.set('view engine', 'ejs');                         // 代表 view engine 我們宣告為 ejs
app.get('/', function (req, res) {
  res.render('index', {                                // 表示渲染 views 資料夾內的 index.ejs
    game: 'Final Fantasy VII',
    category: '<p><b>Characters:</b></p>',
    characters: ['Cloud', 'Aerith', 'Tifa', 'Barret']
  });
});
app.listen(3000, function() {
  console.log('Example app listening on port 3000!');
});
```

---

### views/index.ejs
```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <title>簡單實作 EJS</title>
    </head>
    <body>
        <h1><%= game %></h1>
        <%- category %>
        <ul>
            <% for(var i=0; i<characters.length; i++) { %>
            <li><%= characters[i] %></li>
            <% } %>
        </ul>
    </body>
</html>
```

---

#### <%= code %>
* 這寫法是將 res.render('index',{...}); 輸出過來的變數當 `值` 來使用。
* 也就是說 <%= game %> 的 game 就是 game:'Final Fantasy VII'，所以這段內容 `<h1><%= game %></h1>` 變成 `<h1>Final Fantasy VII</h1>`。

#### <%- code %>
* 這寫法是將 res.render('index',{...}); 輸出過來的變數做 `保留字元` 來使用。
* 也就是說其變數送過來後，會被當作 HTML 語法來使用。因此 `<%- category %>` 變成 `<p><b>Characters:</b></p>`。

#### <% code %>
* 這寫法是將標籤內的內容，當作程式邏輯來使用，像是 if else 判斷式、for 迴圈。

---

`app.js` 和 `index.ejs` 都準備好後，在瀏覽器中輸入 http://127.0.0.1:3000/ ，就可以成功看到 index.ejs 所呈現的畫面。

![image](https://miro.medium.com/max/991/1*tUC5w4hc97aPH5w7y4F_dQ.png)
---

Reference:
* [EJS 內嵌式的樣板引擎 (筆記)](https://medium.com/@charming_rust_oyster_221/ejs-%E5%85%A7%E5%B5%8C%E5%BC%8F%E7%9A%84%E6%A8%A3%E6%9D%BF%E5%BC%95%E6%93%8E-%E7%AD%86%E8%A8%98-482d83c73887)
