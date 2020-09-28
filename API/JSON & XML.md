### XML 
* 和 HTML 的寫法非常相似，兩個都是『標記語言』的形式。
* XML 是非常早期就開始被使用的資料交換格式。
* XML 資料格式的結構，相較 JSON 龐大，程式在處理時也較花時間。

#### XML 資料形式
```
<robot>
	<name>多拉A夢</name>
	<height>129.3</height>
	<weight>129.3</weight>
	<hobby>
		<food>銅鑼燒、機油</food>
		<relationship>和小咪約會</relationship>
	</hobby>
</robot>
```

---

### JSON
* JSON 因為資料結構體積小，因此傳遞快速方便。
* 解析上比 XML 方便許多。
* 現在幾乎各大現代網站的資料交換方式，都是用 JSON 格式，像是 Google Map API, FB Login API 等...。
* AJAX 就是使用 JSON 作為資料交換的標準格式。

#### JSON 資料形式
```
{
	“name” : “多拉A夢”,
	“height”: 129.3,
	“weight”:129.3,
	“hobby”:{
		“food” : “銅鑼燒、機油”,
		“relationship” : “和小咪約會”
	} 	
}
```
