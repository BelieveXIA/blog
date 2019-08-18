<h2 id="01">前言</h2>    
 
reset.css文档就是一个普通的层叠样式表文档，就是css文档，一个网站一般会用三种css文档来设定网站的样式。**重置样式**([reset.css](https://github.com/BelieveXIA/blog/blob/master/CSS/reset.css))(重置默认的css样式)；**公共样式** (common.css)(一系列页面共用共享的样式，如：头部底部样式)；**独立样式**(每个页面单独使用的样式，如index.css)。      
在这里具体讲得就是重置样式，其他两种样式就是因项目而定的没有太多的规定设定可讲。    

<h2 id="02">目录</h2>    

* [为什么要用reset.css](#03)      
* [怎么用](#04)
* [reset.css内容说明](#05)
* [总结](#06)     

<h2 id="03">为什么要用reset.css</h2> 

因为在不同的浏览器中，HTML标签会有一些默认的属性值，但是各个浏览器会渲染出各不一样的效果，例如边距不一致、字体颜色大小行高不一样等等。为了防止出现这种情况，其实主要是为了减少代码的重复定义，提高代码复用率，提高开发效率，重设各个浏览器的默认样式，还可以解决其引起的耦合问题。   
总结就是高复用，低耦合，文件小。   

<h2 id="04">怎么用</h2>   

独立新建一个css文档来储存重置样式，就是reset.css里面只存放重置样式，其他样式可以根据[前言](#01)分类分开存放css属性。这里有一个是本人参考了各大网站的reset.css整理写的[reset.css](https://github.com/BelieveXIA/blog/blob/master/CSS/reset.css)，文档没有绝对标准性的，很多都是根据项目的具体需求写，我总结的只是一些非常常用的重置样式，可以适用大部分项目，当然最好是理解了，每次自己根据项目需求对reset.css进行编写。     
    
<h2 id="05">reset.css说明</h2>        
  
```CSS
@charset 'utf-8';
/*这些元素都建议重新初始化*/
body,div,dl,dt,dd,ul,ol,li,tr,td,th,
h1,h2,h3,h4,h5,h6,hr,br,img,table,
input,form,a,p,textarea{
    padding:0;
    margin:0;
    font-family:Arial,'Microsoft YaHei','宋体';
}
/*去掉列表默认排列*/
ul,ol,li{
    list-style:none;
}
/*去掉底部横线*/
/*把a元素更改设置成块级元素，这个根据实际情况决定要不要*/
a{
    text-decoration:none;
    display:block;
}
/*img标签要清除border。*/
/*display设为block设置为块级元素，默认为display:inline;
存在下边线多出4px状况,所以一般设为block*/
img{
    border:0;
    display:block;
}
/*清除浮动破坏带来的塌陷问题*/
/*清除浮动的兼容IE*/
.clearfloat {
	zoom: 1;
}
.clearfloat:after {
	display:block;
	clear:both;
	content:"";
	visibility:hidden;
	height:0;
}
```   
    
<h2 id="06">总结</h2>        
 
为了更规范，为了更好的与人合作，就有了reset.css文档。这个文档最好最好在项目的开始就要先写好。如果问这个文档是不是必须的，我可以说不是，你自己在一个样式表内看到哪个属性就写哪个属性先也行，但是写了这个文档可以帮助你节省时间，可以让你的代码更优秀。谢谢！         
    
 * [回到顶部](#01)    
   