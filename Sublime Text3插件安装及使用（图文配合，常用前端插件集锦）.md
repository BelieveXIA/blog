## Sublime Text3插件安装及使用（图文配合，常用前端插件集锦）   

<h2 id="01">目录</h2>        

* [插件安装方法](#1)      
* [最常用的插件](#2)       
* [拓展](#3)       
* [更多自定义配置](#4)      

<h3 id="1">插件安装方法(这个是在软件内自动安装的方法)</h3>      

1.打开Sublime Text3   
2.第一次安装插件要先安装Package Control，Package Control可以说得上是软件的母插件，必须先安装。首先“ctrl+~”打开控制台，复制[Package Control官网](https://packagecontrol.io/installation)的安装代码，粘贴到控制台，“enter键”安装。使用Sublime Text3就选用Sublime Text3的官方插件安装代码    
![](https://user-gold-cdn.xitu.io/2019/8/17/16ca0463b810fdea?w=1547&h=831&f=png&s=186495)

例如Sublime Text3的安装代码为
```
import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```
过期了，就到官网自行复制。   
3.安装过程中不要关闭Sublime Text3，安装完成控制台会有提示的，安装完成后重启软件。然后在菜单栏的Preferences菜单下你会看到Package Settings和Package Control两个选项，这也代表安装成功。  
4.到了这里就是真正开始安装我们需要的插件的步骤了，我们想安装什么插件最好先到[Package Control官网插件页](https://packagecontrol.io/browse)，看看所要安装插件的样式及说明，手动安装插件也是到这里下载插件包，放在软件的安装目录下的Package Control文件内就行。     
5.首先“Ctrl+Shift+p”,输入pci,找到"Package Control:Install Package "选中，“enter键”确认，这时一般情况要等一会儿，才会出现新的输入框，然后输入插件名（例如“Emmet”）“enter键”确认进行安装。   

![](https://user-gold-cdn.xitu.io/2019/8/18/16ca0558c5217660?w=739&h=533&f=png&s=29644)

![](https://user-gold-cdn.xitu.io/2019/8/18/16ca058ab21fd2c5?w=749&h=497&f=png&s=30951)
6.然后在安装好插件后，会有相应的代码提示，比如告诉你成功安装之类的，部分插件没有提示。    
7.查看所安装的插件：“Ctrl+Shift+p”,输入pc,找到"Package Control:List Packages "选中，“enter键”确认，这时一般情况要等一会儿，就会出现你所安装的插件了
![](https://user-gold-cdn.xitu.io/2019/8/18/16ca064184c89f83?w=749&h=467&f=png&s=18213)

![](https://user-gold-cdn.xitu.io/2019/8/18/16ca0644892ce77b?w=747&h=493&f=png&s=26889)

<h3 id="2">最常用的插件</h3>       

[插件官网](https://packagecontrol.io)，以下链接插件的官方地址，里面有详细的样式及使用介绍，就不一一叙述了    
1.Emmet：（前端必备插件）[官网Emmet插件说明](https://packagecontrol.io/packages/Emmet)	||	[源码地址](https://github.com/sergeche/emmet-sublime)    
2.Theme - Spacegray：（颜色主题）[官网Theme - Spacegray插件说明](https://packagecontrol.io/packages/Theme%20-%20Spacegray)		||	[源码地址](https://github.com/kkga/spacegray)     
3.JavaScript & NodeJS Snippets：（js&node开发）[官网JavaScript & NodeJS Snippets插件说明](https://packagecontrol.io/packages/JavaScript%20%26%20NodeJS%20Snippets)	||	[源码地址](https://github.com/zenorocha/sublime-javascript-snippets)   
4.jQuery：（jQuery开发) [官网jQuery插件说明](https://packagecontrol.io/packages/jQuery)	||	[源码地址](https://github.com/SublimeText/jQuery)     
5.DocBlockr:（快速注释）[官网DocBlockr插件说明](https://packagecontrol.io/packages/DocBlockr)	||	[源码地址](https://github.com/spadgos/sublime-jsdocs)    
6.SublimeLinter：（语法及风格校验总框架）[官网SublimeLinter插件说明](https://packagecontrol.io/packages/SublimeLinter)	||	[源码地址](https://github.com/SublimeLinter/SublimeLinter)     
7.SublimeLinter-jshint：（js语法及风格校验）[官网SublimeLinter-jshint插件说明](https://packagecontrol.io/packages/SublimeLinter-jshint)		||	[源码地址](https://github.com/SublimeLinter/SublimeLinter-jshint)   
8.ColorPicker：（颜色拾取器）[官网ColorPicker插件说明](https://packagecontrol.io/packages/ColorPicker)		||	[源码地址](https://github.com/weslly/ColorPicker)    
9.AutoFileName：（文件名补充引用）[官网AutoFileName插件说明](https://packagecontrol.io/packages/AutoFileName)	||	[源码地址](https://github.com/BoundInCode/AutoFileName)      
      

<h3 id="3">拓展</h3>    

对6、7、插件安装及使用拓展：语法和编写风格的校验插件SublimeLinter 
1. 先安装SublimeLinter插件，它是总框架,具体语言再另行安装   
2. 安装具体语言风格例如js, 就再安装插件为SublimeLinter_JShint    
3. 在本身电脑上还需要先安装npm包，就是安装[node.js](https://nodejs.org/en/)（一般node包含了npm包），再在npm安装JShint,即在cmd命令行输入：npm install -g jshint,“enter键”确认安装（要安装大于2.5版本才能正常使用jshint）  
4. 自定义校验规则：在工程中创建配置文件，名字必须是.jshintrc ,（PS：语言风格是json，但不是json文件，是.jshintrc文件）   
5. 可以自定义校验风格 "eqeqeq":true //强制三等号验证；"curly":true//必须规范js有大括号，不能省略；还有其余自定义风格到[该插件的官网介绍](https://jshint.com/docs/options/)查找学习使用。

<h3 id="4">更多自定义配置</h3>    

更多Sublime Text3自定义配置到[作者的配置库](https://github.com/BelieveXIA/Custom-Configuration-sublime-text3)观看配置文件,库会一直更新的，当然风格配置是个人喜好，没有什么是最好的，按自己喜好，怎么舒服怎么配置。   

[回到顶部](#01)      





