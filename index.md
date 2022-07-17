<!doctype html public "嘟嘟" "呼噜">
<html xmlns="测试">
<head>
<meta http-equiv="content-type" content="text/html; charset=utf-8" />
<title>jquery窗口震动特效</title>
<script type="text/javascript" src="https://www.codefans.net/ajaxjs/jquery-1.6.2.min.js"></script>
<script type="text/javascript">
;(function($){
var element = {};
$.fn.jshaker = function(){
element = $(this);
element.css('position', 'relative');
element.find('*').each(function(i, el){
$(el).css('position', 'relative');
});
var ifunc = function(){ $.fn.jshaker.animate($(element)); };
settimeout(ifunc, 50);
};
$.fn.jshaker.animate = function(el){
$.fn.jshaker.shake(el);
el.find('*').each(function(i, el){
$.fn.jshaker.shake(el);
});
var ifunc = function(){ $.fn.jshaker.animate(el); };
settimeout(ifunc, 50);
}
$.fn.jshaker.shake = function(el){
var pos = $(el).position();
if(math.random() > 0.5){
$(el).css('top', pos['top'] + math.random() * 20 < 10 ? (math.random() * 20 * (-1)) : math.random() * 20);
} else {
$(el).css('left', pos['left'] + math.random() * 20 < 10 ? (math.random() * 20 * (-1)) : math.random() * 20);
}
}
})(jquery);
</script>
<script type="text/javascript">
$(document).ready(function(){
$('.block').click(function(){
$(this).jshaker();
});
});
</script>
<style type="text/css">
body{font-family: "lucida grande", arial, helvetica, sans-serif;color: #666666;font-size: 12px;background: #ffffff;}
a{color: #0a8ecc;}
a: hover{text-decoration: none;color: #8fcb2f;}
h1{font-weight: normal;color: #0a8ecc;margin: 0;padding: 0;}
body{margin: 20px;padding: 20px;}
strong{color: #000000;}
.vspacer{height: 20px;}
pre.code{padding: 7px;background: #777777;color: #f0f0f0;width: 400px;overflow: auto;}
#content-area{border: 3px solid #cccccc;background: #f0f0f0;padding: 10px;width: 500px;}
p.script-link{clear: both;padding: 10px 0;border-top: 1px dotted #cccccc;}
#content .block {float: left;border: 1px solid #cccccc;background: #f0f0f0;padding: 10px;margin: 10px;width: 300px;}
</style>
</head>
<body>
<p id="page">
<h1>jquery窗 口 震 动 特 效</h1>
<p id="content">
<p class="block">
<p>点击本框内，可实现震动</p>
<ul>
<li>item 1</li>
<li>item 2</li>
<li>
item 3
<ul>
<li>sub item 1</li>
<li>sub item 2</li>
<li>sub item 3</li>
<li>sub item 4</li>
<li>sub item 5</li>
</ul>
</li>
<li>item 4</li>
<li>item 5</li>
</ul>
</p>
<p class="block">
<form action="#">
<p><label for="inp1">text field 1:</label><input type="text" name="inp1" id="inp1" value="" /></p>
<p><label for="inp2">text field 2:</label><input type="text" name="inp2" id="inp2" value="" /></p>
<p><button type="submit">submit</button></p>
</form>
</p>
</p>
<p class="script-link">
</p>
</p>
</body>
</html>
