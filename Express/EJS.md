### EJS

EJS 的全名是「Embedded Javascript」，顧名思義就是內嵌式的樣板引擎，可以將邏輯與內容直接嵌入到 HTML 頁面上

比較常用到的功能:
#### <%= code %>
* 這寫法是將 res.render('index',{...}); 輸出過來的變數當 `值` 來使用。
* 也就是說 <%= game %> 的 game 就是 game:'Final Fantasy VII'，所以這段內容 `<h1><%= game %></h1>` 變成 `<h1>Final Fantasy VII</h1>`。

#### <%- code %>
* 這寫法是將 res.render('index',{...}); 輸出過來的變數做 `保留字元` 來使用。
* 也就是說其變數送過來後，會被當作 HTML 語法來使用。因此 `<%- category %>` 變成 `<p><b>Characters:</b></p>`。

#### <% code %>
* 這寫法是將標籤內的內容，當作程式邏輯來使用，像是 if else 判斷式、for 迴圈。
