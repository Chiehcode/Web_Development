### NPM (Node Package Manager, 套件管理機制)

* 開發者可以透過 NPM，進行套件的安裝及管理。
* 開發者可以透過專案中的 package.json，羅列出專案需要哪些套件，之後安裝時只需要 npm install，npm 便會自動依照 package.json 的內容下載套件與版本需求。

### package.json

每個項目的根目錄下面，一般都有一個package.json文件，定義了這個項目所需要的各種模塊，以及項目的配置信息（比如名稱、版本、許可證等元數據）。npm install命令根據這個配置文件，自動下載所需的模塊，也就是配置項目所需的運行和開發環境。
