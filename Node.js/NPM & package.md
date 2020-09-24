### NPM (Node Package Manager, 套件管理機制)

* 開發者可以透過 NPM，進行套件的安裝及管理。
* 開發者可以透過專案中的 `package.json`，羅列出專案需要哪些套件，之後安裝時只需要 `npm install`，NPM 便會自動依照 `package.json` 的內容下載套件。

---

### package.json

* 每個專案的根目錄下面，都有一個 `package.json` 文件，定義了這個專案所需要的各種套件，以及相關的配置資訊（比如名稱、版本...等資訊）。`npm install` 命令根據這個配置文件，自動下載所需的套件，也就是配置項目所需的運行和開發環境。

#### package.json ample
```
{
	"name": "Hello World",
	"version": "0.0.1",
	"author": "張三",
	"description": "第一個 node.js",
	"keywords":["node.js","javascript"],
	"repository": {
		"type": "git",
		"url": "https://path/to/url"
	},
	"license":"MIT",
	"engines": {"node": "0.10.x"},
	"bugs":{"url":"http://path/to/bug","email":"bug@example.com"},
	"contributors":[{"name":"李四","email":"lisi@example.com"}],
	"scripts": {
		"start": "node index.js"
	},
	"dependencies": {
		"express": "latest",
		"mongoose": "~3.8.3",
		"handlebars-runtime": "~1.0.12",
		"express3-handlebars": "~0.5.0",
		"MD5": "~1.2.0"
	},
	"devDependencies": {
		"bower": "~1.2.8",
		"grunt": "~0.4.1",
		"grunt-contrib-concat": "~0.3.0",
		"grunt-contrib-jshint": "~0.7.2",
		"grunt-contrib-uglify": "~0.2.7",
		"grunt-contrib-clean": "~0.5.0",
		"browserify": "2.36.1",
		"grunt-browserify": "~1.3.0",
	}
}
```

package.json 文件可以手工編寫，也可以使用 npm init 命令自動生成。
```
npm init
```

如果不想一直輸入資訊，可以使用 npm init -y 快速產生一個 package.json。
```
npm init -y
```

有了 package.json 文件，就可以直接使用 npm install 命令，在當前目錄中安裝所需要的套件。
```
npm install
```

如果一個套件不在 package.json 文件之中，可以單獨安裝這個套件，並使用相應的參數，將其寫入 package.json 文件之中。
```
npm install express --save
```
```
npm install express --save-dev
```
Remark: --save 參數表示將該模塊寫入 `dependencies` 屬性 ； --save-dev 表示將該模塊寫入 `devDependencies` 屬性

---

Reference:
* https://javascript.ruanyifeng.com/nodejs/packagejson.html
