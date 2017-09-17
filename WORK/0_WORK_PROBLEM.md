
# Issue

-----------------------------------

-----------------------------------

> 2017-03-30 10:46AM
## Issue Click link a tag data-? attribute

http://jsfiddle.net/z4wkp/1/
```
$('#myTable').on('click', 'a.modaldialogcenter', function (event) {
         event.preventDefault();
var params = $(this).attr("data-param");
alert(params);
});
```


## *#Issue* modal not large

http://www.bootply.com/85213#

http://jsfiddle.net/z4wkp/1/
```
#myModal .modal-dialog
{
  width: 70%;
}
```
-----------------------------------
## *#Issue* Browser load slow down?
```
close browser link in visual studio
```

-----------------------------------------------------
## Issue when load Ajax jquery not working

```
$('body').on('click','.heading',function(){
     $(this).css('color','red');  
});
```

try code after load ajax
http://stackoverflow.com/questions/18431407/jquery-code-doesnt-work-in-ajax-loaded-content

http://blog.codebusters.pl/en/click-doesn-t-work-after-ajax-load-jquery/#example-data
```
$.ajax({
  url: "yourUrl",     
}).done(function(data) {
   $("#yourId").html(data);   // Solution 1 :  your content is loaded with ajax, Also this data has your jQuery script
   // Solution 2:  Now start you can call your script via function or add directly here (only html data is needed)
   yourFunction();
   //Solution 3: Now add your jquery code directly
   $(".someClass").click(function(){
     //events
   });
});
```

## Issue  Jquery ทำงานซ้ำ
