<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<title>jquery窗口震动特效</title>
<script type="text/javascript" src="jquery-1.6.2.min.js"></script>
<script type="text/javascript">
;(function($){
 var element = {};
 $.fn.jshaker = function(){
  element = $(this);
  element.css('position', 'relative');
  element.find('*').each(function(i, el){
   $(el).css('position', 'relative');
  });
 var iFunc = function(){ $.fn.jshaker.animate($(element)); };
 setTimeout(iFunc, 50);
 };
 $.fn.jshaker.animate = function(el){
  $.fn.jshaker.shake(el);
 el.find('*').each(function(i, el){
  $.fn.jshaker.shake(el);
 });
 var iFunc = function(){ $.fn.jshaker.animate(el); };
 setTimeout(iFunc, 50);
 }
 $.fn.jshaker.shake = function(el){
 var pos = $(el).position();
 if(Math.random() > 0.5){
  $(el).css('top', pos['top'] + Math.random() * 20 < 10 ? (Math.random() * 20 * (-1)) : Math.random() * 20);
 } else {
  $(el).css('left', pos['left'] + Math.random() * 20 < 10 ? (Math.random() * 20 * (-1)) : Math.random() * 20);
 }
 }
})(jQuery);
</script>
<script type="text/javascript">
 $(document).ready(function(){
  $('.block').click(function(){
  $(this).jshaker();
  });
 });
</script>
<style type="text/css">
BODY{font-family: "Lucida Grande", Arial, Helvetica, sans-serif;color: #666666;font-size: 12px;background: #FFFFFF;}
A{color: #0A8ECC;}
A: HOVER{text-decoration: none;color: #8FCB2F;}
H1{font-weight: normal;color: #0A8ECC;margin: 0;padding: 0;}
BODY{margin: 20px;padding: 20px;}
STRONG{color: #000000;}
.vspacer{height: 20px;}
PRE.code{padding: 7px;background: #777777;color: #F0F0F0;width: 400px;overflow: auto;}
#content-area{border: 3px solid #CCCCCC;background: #F0F0F0;padding: 10px;width: 500px;}
P.script-link{clear: both;padding: 10px 0;border-top: 1px dotted #CCCCCC;}
#content .block {float: left;border: 1px solid #CCCCCC;background: #F0F0F0;padding: 10px;margin: 10px;width: 300px;}
</style>
</head>
<body>
 <div id="page">
 <h1>jquery窗口震动特效</h1>
 <div id="content">
  <div class="block">
  <p>点击本框内，可实现震动。。</p>
  <ul>
   <li>Item 1</li>
   <li>Item 2</li>
   <li>
   Item 3
   <ul>
    <li>Sub Item 1</li>
    <li>Sub Item 2</li>
    <li>Sub Item 3</li>
    <li>Sub Item 4</li>
    <li>Sub Item 5</li>
   </ul>
   </li>
   <li>Item 4</li>
   <li>Item 5</li>
  </ul>
  </div>
  <div class="block">
  <form action="#">
   <p><label for="inp1">Text Field 1:</label><input type="text" name="inp1" id="inp1" value="" /></p>
   <p><label for="inp2">Text Field 2:</label><input type="text" name="inp2" id="inp2" value="" /></p>
   <p><button type="submit">Submit</button></p>
  </form>
  </div>
 </div>
 <p class="script-link">
 </p>
 </div>
</body>
</html>
