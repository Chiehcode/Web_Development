XML 和所謂 HTML 的寫法非常相似，
兩個都是『標記語言』的形式，也就是會把資料儲存在以下的形式中:

XML 是非常早期就開始被使用的資料交換格式，

不過 XML 資料格式的結構，相較 JSON 龐大，
除了資料本身較大外，程式在處理時也較花時間。

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

JSON

JSON 因為資料結構體積小，因此傳遞快速方便，
而且解析上比 XML 方便許多，不會眼花瞭亂，

現在幾乎各大現代網站的資料交換方式，都是用 JSON 格式，
像是 Google Map API, FB Login API，

由於前後端分離網站的興起，需要用 JavaScript 這個程式語言處理後端傳來的資料，
而最常使用的交換技術就是『AJAX』，
那 AJAX 就是使用 JSON 作為資料交換的標準格式。
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
