### 用户代理检测   
通过检测用户代理字符串来确认实际使用的浏览器。

在服务器端，通过检测用户代理字符串来确定用户使用的浏览器是一种常用而且广泛为接受的做法。而在客户端，用户代理检测一般被当作一种万不得已才用的做法，其优先级排在**能力检测**和（或）**怪癖检测**（在另一个文章讲到）之后。   
提到与用户代理字符串有关的争议，就不得不提到**电子欺骗**。所谓电子欺骗，就是指浏览器通过在自己的用户代理字符串加入一些错误或误导性信息，来达到欺骗服务器的目的。所以用户代理检测就是检测清楚客户端究竟原来的真面目，以区分用户浏览器的真实信息，剔除电子欺骗。     
### 用户代理字符串检测脚本，包括检测呈现引擎、平台、Window操作系统、移动设备和游戏系统。
至于个中的演变历史和演变内容不细分分析了，代码中有注释解释大致内容，代码如下（后面还有使用方法）：（如有错误，望指出，感谢）

```javascript
//客户端检测之
//用户代理检测（这个是最后的手段，优先能力检测和怪癖检测）
var client = function(){
	//呈现引擎
	var engine = {
		ie: 0,
		gecko: 0,
		webkit: 0,
		khtml: 0,
		opera: 0,

		//完整的版本号
		ver: null
	};

	//浏览器
	var browser = {
		//主要浏览器
		ie: 0,
		firefox: 0,
		safari: 0,
		konq: 0,
		opera: 0,
		chrome: 0,
		//具体的版本号
		ver: null
	};

	 //平台、设备和操作系统
	 var system = {
	 	win:false,
	 	mac:false,
	 	x11:false,

	 	//移动设备
	 	iphone:false,
	 	ipod:false,
	 	ipad:false,
	 	ios:false,
	 	android:false,
	 	nokiaN:false,
	 	winMobile:false,

	 	//游戏系统
	 	wii:false,
	 	ps:false
	 };

	 //检测呈现引擎和浏览器
	 var ua = navigator.userAgent;
	 if(window.opera){
	 	engine.ver = browser.ver = window.opera.version();
	 	engine.opera = browser.opera = parseFloat(engine.ver);
	 }else if(/AppleWebKit\/(\S+)/.test(ua)){
	 	engine.ver = RegExp["$1"];
	 	engine.webkit = parseFloat(engine.ver);

	 	//确定是chrome、还是safari
	 	if(/Chrome\/(\S+)/.test(ua)){
	 		browser.ver = RegExp["$1"];
	 		browser.chrome = parseFloat(browser.ver);
	 	}else if(/Version\/(\S+)/.test(ua)){
	 		browser.ver = RegExp["$1"];
	 		browser.safariv = parseFloat(browser.ver);
	 	}else{
	 		//近似地确定版本号
	 		var safariVersion = 1;
	 		if(engine.webkit < 100){
	 			safariVersion = 1;
	 		}else if (engine.webkit < 312){
	 			safariVersion = 1.2;
	 		} else if (engine.webkit < 412){
	 			safariVersion = 1.3;
	 		}else{
	 			safariVersion = 2;
	 		}
	 		browser.safari = browser.ver = safariVersion;
	 	}
	 }else if(/KHTML\/(\S+)/.test(ua) || /Konqueror\/([^;]+)/.test(ua)){
	 	engine.ver = browser.ver = RegExp["$1"];
	 	engine.khtml = browser.konq = parseFloat(engine.ver);
	 }else if(/rv:([^\)]+)\) Gecko\/\d{8}/.test(ua)){
	 	engine.var = RegExp["$1"];
	 	engine.gecko = parseFloat(engine.ver);

	 	//确认是不是Firefox
	 	if(/Firefox\/(\S+)/.test(ua)){
	 		browser.ver= RegExp["$1"];
	 		browser.firefox = parseFloat(browser.ver);
	 	}
	 }else if(/MSIE ([^;]+)/.test(ua)){
	 	engine.ver = browser.ver = RegExp["$1"];
	 	engine.ie = browser.ie = parseFloat(engine.ver);
	 }

	 //检测浏览器
	 browser.ie = engine.ie;
	 browser.opera = engine.opera;

	 //检测平台
    var p = navigator.platform;
    system.win = p.indexOf("Win") == 0;
    system.mac = p.indexOf("Mac") == 0;
    system.x11 = (p == "X11") || (p.indexOf("Linux") == 0);

	 //检测Window操作系统
	 if (system.win){
	 	if (/Win(?:dows )?([^do]{2})\s?(\d+\.\d+)?/.test(ua)){
	 		if (RegExp["$1"] == "NT"){
	 			switch(RegExp["$2"]){
	 				case "5.0":
	 				system.win = "2000";
	 				break;
	 				case "5.1":
	 				system.win = "XP";
	 				break;
	 				case "6.0":
	 				system.win = "Vista";
	 				break;
	 				case "6.1":
	 				system.win = "7";
	 				break;
	 				default:
	 				system.win = "NT";
	 				break;                
	 			}                            
	 		} else if (RegExp["$1"] == "9x"){
	 			system.win = "ME";
	 		} else {
	 			system.win = RegExp["$1"];
	 		}
	 	}
	 }

	 //移动设备
	 system.iphone = ua.indexOf("iPhone") > -1;
	 system.ipod = ua.indexOf("iPod") > -1;
	 system.ipad = ua.indexOf("iPad") > -1;
	 system.nokiaN = ua.indexOf("NokiaN") > -1;

	 //windo mobile
	 if(system.win =="CE"){
	 	system.winMobile = system.win;
	 }else if(system.win == "Ph"){
	 	if(/Window Phone OS (\d+.\d+)/.test(ua)){;
	 		system.win = "Phone";
	 		system.winMobile = parseFloat(RegExp["$1"]);
	 	}
	 }

	 //检测iOS版本
	 if (system.mac && ua.indexOf("Mobile") > -1) {
	 	if(/CPU (?:iPhone )?OS (\d+_\d)/.test(ua)){
	 		system.ios = parseFloat(RegExp.$1.replace("_","."));
	 	}else{
			system.ios = 2;//不能真正检测出来，所以只能猜测
		}
	}

	//检测Android版本
	if(/Android (\d+\.\d+)/.test(ua)){
		system.android = parseFloat(RegExp.$1);
	}

	//游戏系统
	system.wii = ua.indexOf("Wii") > -1;
	system.ps = /playstation/i.test(ua);

	//返回这些对象
	return {
		engine:engine,
		browser:browser,
		system:system,
	};
}();
```
### 使用方法
使用实例，记得先引用上面的js脚本，（因为在html文档中用了很多嵌入式的script脚本，里面的client函数引用是在上面的js脚本中声明初始化的）：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>UserAgentDetectionExample</title>
	<script type="text/javascript" src=""></script>
</head>
<body>
	<h2>Rendering Engines</h2>
	<ul>
		<li>client.engine.ie = <script>document.write(client.engine.ie);</script></li>
		<li>client.engine.webkit = <script>document.write(client.engine.webkit);</script></li>
		<li>client.engine.gecko = <script>document.write(client.engine.gecko);</script></li>
		<li>client.engine.khtml = <script>document.write(client.engine.khtml);</script></li>
		<li>client.engine.opera = <script>document.write(client.engine.opera);</script></li>
		<li>client.engine.ver = <script>document.write(client.engine.ver);</script></li>

	</ul>
	<h2>Browsers</h2>
	<ul>
		<li>client.browser.ie = <script>document.write(client.browser.ie);</script></li>
		<li>client.browser.safari = <script>document.write(client.browser.safari);</script></li>
		<li>client.browser.firefox = <script>document.write(client.browser.firefox);</script></li>
		<li>client.browser.konq = <script>document.write(client.browser.konq);</script></li>
		<li>client.browser.opera = <script>document.write(client.browser.opera);</script></li>
		<li>client.browser.chrome = <script>document.write(client.browser.chrome);</script></li>
		<li>client.browser.ver = <script>document.write(client.browser.ver);</script></li>
	</ul>

	<h2>System</h2>
	<ul>
		<li>client.system.win = <script>document.write(client.system.win);</script></li>
		<li>client.system.mac = <script>document.write(client.system.mac);</script></li>
		<li>client.system.x11 = <script>document.write(client.system.x11);</script></li>
		<li>client.system.iphone = <script>document.write(client.system.iphone);</script></li>
		<li>client.system.ipod = <script>document.write(client.system.ipod);</script></li>
		<li>client.system.ipad = <script>document.write(client.system.ipad);</script></li>
		<li>client.system.ios = <script>document.write(client.system.ios);</script></li>
		<li>client.system.android = <script>document.write(client.system.android);</script></li>
		<li>client.system.nokiaN = <script>document.write(client.system.nokiaN);</script></li>
		<li>client.system.winMobile = <script>document.write(client.system.winMobile);</script></li>
		<li>client.system.wii = <script>document.write(client.system.wii);</script></li>
		<li>client.system.ps = <script>document.write(client.system.ps);</script></li>    
	</ul>    
</body>
</html>
```