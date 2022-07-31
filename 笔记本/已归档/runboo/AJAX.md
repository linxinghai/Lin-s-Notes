# AJAX
#runoob
## 简介
## 实例
## XHR创建对象
    
```jsx
var xmlhttp;
if(window.XMLHttpRequest){
	xmlhttp = new XMLHttpRequest();
}else{
	xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
}
```
    
## XHR请求
## XHR readyState
## AJAX ASP/PHP
## AJAX 数据库
    
```jsx
function showCustomer(str){

}
```
    
## AJAX XML
[XML](XML)
```jsx
function loadXMLDoc(){
	var xhttp = new XMLHttpRequest();
	xhttp.onreadystatechange = function(){
		if(this.readState == 4 && this.status == 200){
			myFunction(this);
		}
	};
	xhttp.open("GET","cd_catalog.xml",true);
	xhttp.send();
}
myFunction(xml){
	var i;
	var xmlDoc = xml.responseXML;
	var table = "<tr><th>Artist</th><th>Title</th></tr>";
	var x = xmlDoc.getElementsByTagName("CD");
	for(i = 0;i < x.length;i++){
		table += "<tr><td>" 
					+ x[i].getElementsByTagName("ARTIST")[0].childNodes[0].nodeValue
					+ "</tr></td>" 
					+ x[i].getElementsByTagName("TITLE")[0].childNodes[0].nodeValue
					+ "</tr></td>";
	}
	document.getElementById("demo").innerHTML = table;
}
```
    
## AJAX 实例

## AJAX JSON 实例
[JSON](笔记本/已归档/runboo/JSON.md)