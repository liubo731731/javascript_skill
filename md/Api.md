#### 这里放一些常用的函数清单和简单的说明,或者注意事项



* 选择图片转换为base64:利用H5的bitmap控件

	```
	function GetBase64Code(path) //path绝对路径  
	{  
			var bitmap = new plus.nativeObj.Bitmap("test"); //test随便取  
			// 从本地加载Bitmap图片  
			bitmap.load(path,function(){  
				var base64=bitmap.toBase64Data();  
				var datastr=base64.split(',',3)  
				if(datastr.length>1)  
				{  
				   pics.push(datastr[1]);  
				}else  
				{  
				   pics.push(datastr[0]);  
				}  
				console.log('加载图片：'+base64);  
			},function(e){  
				console.log('加载图片失败：'+JSON.stringify(e));  
			});  
	}  

	```
	
* object-fit 让大小不一的图片保持大小相同 相册，表情包;<img style="width:200px;height:200px;object-fit:cover" src="">

```
属性	描述
fill	默认值。整个对象将完全填充此框。 如果对象的高宽比不匹配其框的宽高比，那么该对象将被拉伸以适应。
contain	整个对象在填充盒子的同时保留其长宽比，因此如果宽高比与框的宽高比不匹配，该对象将被添加“黑边”。
cover	被替换的内容大小保持其宽高比，同时填充元素的整个内容框。 如果对象的宽高比与盒子的宽高比不匹配，该对象将被剪裁以适应。
none	内容尺寸不会被改变。
scale-down	内容的尺寸就像是指定了none或contain，默认应用尺寸最小的值


```	