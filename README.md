![背景图](https://github.com/Faypp/test/blob/master/1.jpg)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>snow</title>
<style>
    body,html{
    margin: 0;
    padding: 0;
    overflow: hidden;
    height: 100%;
}
.snow{
    color:white;
    position: absolute; 
}
</style>
</head>
<body>
   
</body>
<script>
 //获取屏幕宽高
 var windowWidth = window.screen.width;
 var windowHeight = window.screen.height;

 //创建雪花
 function createSnow(){
     var left = 0;
     var top = 0;

     //定义一个初始化随机数,使雪花在屏幕中
     var left_random = Math.random() * windowWidth;
     var top_random = Math.random()* windowHeight;
     var div = document.createElement('div');
     div.className = 'snow';
     div.innerHTML = "❉";
     div.style.transform = 'scale('+(Math.random())+')'

     document.body.appendChild(div);

     //雪花飘落
     setInterval(function () {

         div.style.left = left_random + left +'px';
         div.style.top = top_random + top +'px'
         left += 0.2;
         top += 0.2;

         //如果雪花跑到屏幕外面了,让雪花重新返回屏幕顶部
         if(left_random + left >= windowWidth){
             left_random = Math.random();
             left = 0;
         }

         if(top_random + top >= windowHeight){
             top_random = Math.random();
             top = 0;
         }
     },1)

 }
 for(var i = 0 ; i < 200 ; i++){
     createSnow()
 }
</script>
</html>
