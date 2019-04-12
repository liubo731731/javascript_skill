#### 这里放一些常用的函数清单和简单的说明,或者注意事项



* 选择图片转换为base64:利用H5的bitmap控件

```
function GetBase64Code(path) //path绝对路径  
{  
        var bitmap = new plus.nativeObj.Bitmap("test"); //test标识谁便取  
        // 从本地加载Bitmap图片  
        bitmap.load(path,function(){  
            var base4=bitmap.toBase64Data();  
            var datastr=base4.split(',',3)  
            if(datastr.length>1)  
            {  
               pics.push(datastr[1]);  
            }else  
            {  
               pics.push(datastr[0]);  
            }  
            console.log('加载图片：'+base4);  
        },function(e){  
            console.log('加载图片失败：'+JSON.stringify(e));  
        });  
}  

```