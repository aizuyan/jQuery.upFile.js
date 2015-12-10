# jQuery.upFile.js
jquery无刷新上传文件的插件，支持html5异步ajax和iframe

### 使用简单
```html
<div id="show_up_img"></div>
<input type="button" id="up_trigger" value="上传">
<input type="button" id="up_trigger_do" value="DO上传">
<input type="file" name="up_file" id="up_file"/>
<input type="hidden" name="up_file_path" id="up_file_path"/>
<input type="submit" value="上传">
```


```javascript
$("#up_trigger").upFile($("#up_file"), {
	action: 'http://localhost/up.php',
	autoSubmit: false,
	manualSubmit: $('#up_trigger_do'),
	params: ['yanruitao', 23],
	onStart: function(name, age) {
		alert(this.val());
		alert("What is up!!\n"+ name + "\n" + age);
	},
	onSuccess: function(obj) {
		$("#show_up_img").html('<img src="'+ obj.img +'">');
		$("#up_file_path").val(obj.img);
	}
});
```
