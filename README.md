###DOCTYPE 头部开始

Bad:
```
<html>
  ...
</html>
```
Good:
```
<!DOCTYPE html>
<html>
  ...
</html>
```
###不要用旧的 DOCTYPE

Bad:
```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN"
  "http://www.w3.org/TR/html4/strict.dtd">
  ```
Good:
```
<!DOCTYPE html>
```
###不要用 XML 声明

Bad:
```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<!DOCTYPE html>
```
Good:
```
<!DOCTYPE html>
```
###最好不要用字符引用

Bad:
```
<p><small>Copyright &copy; 2014 W3C<sup>&reg;</sup></small></p>
```
Good:
```
<p><small>Copyright © 2014 W3C<sup>®</sup></small></p>
```

		###Escape &, <, >, ", and ' 可以用字符引用

Bad:
```
<h1>The "&" character</h1>
```
Good:
```
<h1>The &quot;&amp;&quot; character</h1>
```
###Use named character references for control or invisible characters

Bad:
```
<p>This book can read in 1 hour.</p>
```
Good:
```
<p>This book can read in 1&nbsp;hour.</p>
```
###注释的内容两边留个空格
Bad:
```
<!--This section is non-normative-->
```
Good:
```
<!-- This section is non-normative -->
```

###不要忽略闭合标签
Bad:
```
<html>
  <body>
    ...
```
Good:
```
<html>
  <body>
    ...
  </body>
</html>
```
###不要搞混空元素的格式
Bad:
```
<img alt="HTML Best Practices" src="/img/logo.png">
<hr />
```
Good:
```
<img alt="HTML Best Practices" src="/img/logo.png">
<hr>
```
###在标签里面和属性值里不要留空格
Bad:
```
<h1 class=" title " >HTML Best Practices</h1>
```
Good:
```
<h1 class="title">HTML Best Practices</h1>
```

###不要搞混大小写
Bad:
```
<a HREF="#general">General</A>
```
Good:
```
<a href="#general">General</a>
```

###不要混用引号标记
Bad:
```
<img alt="HTML Best Practices" src='/img/logo.jpg'>
```
Good:
```
<img alt="HTML Best Practices" src="/img/logo.jpg">
```
Don't separate attributes with two or more white spaces
###属性之间不要用两个空格隔开
Bad:
```
<input   name="q"  type="search">
```
Good:
```
<input name="q" type="search">
```

###省略布尔属性的值
Bad:
```
<audio autoplay="autoplay" src="/audio/theme.mp3">
```
Good:
```
<audio autoplay src="/audio/theme.mp3">
```

###省略命名空间
Bad:
```
<svg xmlns="http://www.w3.org/2000/svg" version="1.1">
  ...
</svg>
```
Good:
```
<svg version="1.1">
  ...
</svg>
```

###不要用 xml 属性
Bad:
```
<span lang="ja" xml:lang="ja">...</span>
```
Good:
```
<span lang="ja">...</span>
```

### 不要搞混 data-*,Microdata，RDFa Lite  属性和通用的属性
Bad:
```
<img alt="HTML Best Practices" data-height="31" data-width="88" itemprop="image" src="/img/logo.png">
```
Good:
```
<img alt="HTML Best Practices" src="/img/logo.png" data-width="88" data-height="31" itemprop="image">
```
### 更强的原生语义
Bad:
```
<nav role="navigation">
  ...
</nav>

<hr role="separator">
```
Good:
```
<nav>
  ...
</nav>

<hr>
```

## 根元素
###添加语言属性
Bad:
```
<html>
```
Good:
```
<html lang="en-US">
```
### 保持语言属性值尽可能的短

Bad
```
<html lang="ja-JP">
```
Good:
```
<html lang="ja">
```

##文档的元数据

###添加 title 元素
Bad:
```
<head>
  <meta charset="UTF-8">
</head>
```
Good:
```
<head>
  <meta charset="UTF-8">
  <title>HTML Best Practices</title>
</head>
```

### 指定微链接资源的 MIME 类型
Bad:
```
<link href="/pdf" rel="alternate">
<link href="/feed" rel="alternate">
<link href="/css/screen.css" rel="stylesheet">
```
Good:
```
<link href="/pdf" rel="alternate" type="application/pdf">
<link href="/feed" rel="alternate" type="application/rss+xml">
<link href="/css/screen.css" rel="stylesheet">
```

###不要链接到 favicon.ico
Bad:
```
<link href="/favicon.ico" rel="icon" type="image/vnd.microsoft.icon">
```
Good:
```
把 favicon.ico 放在根目录
```
### 添加 title 属性到 备用样式表
Bad:
```
<link href="/css/screen.css" rel="stylesheet">
<link href="/css/high-contrast.css" rel="alternate stylesheet">
```
Good:
```
<link href="/css/screen.css" rel="stylesheet">
<link href="/css/high-contrast.css" rel="alternate stylesheet" title="High contrast">
```

###给文档指定字符编码
Bad:
```
<head>
  <title>HTML Best Practices</title>
</head>
```
Good:
```
<head>
  <meta charset="UTF-8">
  <title>HTML Best Practices</title>
</head>
```
###不要用旧的字符编码格式
Bad:
```
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
```
Good:
```
<meta charset="UTF-8">
```

###首先就要指定字符编码
Bad:
```
<head>
  <meta content="width=device-width" name="viewport">
  <meta charset="UTF-8">
  ...
</head>
```
Good:
```
<head>
  <meta charset="UTF-8">
  <meta content="width=device-width" name="viewport">
  ...
</head>
```
###使用 utf-8 格式
Bad:
```
<meta charset="Shift_JIS">
```
Good:
```
<meta charset="UTF-8">
```

###css 的 type 属性不用写
Bad:
```
<style type="text/css">
  ...
</style>
```
Good:
```
<style>
  ...
</style>
```

###不要注释 style 元素的内容
Bad:
```
<style>
<!--
  ...
  -->
</style>
```
Good:
```
<style>
  ...
</style>
```

###不要搞混 css 和 js 标签
Bad:
```
<script src="/js/jquery.min.js"></script>
<link href="/css/screen.css" rel="stylesheet">
<script src="/js/main.js"></script>
```
Good:
```
<link href="/css/screen.css" rel="stylesheet">
<script src="/js/jquery.min.js"></script>
<script src="/js/main.js"></script>
```
Also good:
```
<script src="/js/jquery.min.js"></script>
<script src="/js/main.js"></script>
<link href="/css/screen.css" rel="stylesheet">
```


###添加 body 标签
Bad:
```
<html>
  <head>
    ...
  </head>
  ...
</html>
```
Good:
```
<html>
  <head>
    ...
  </head>
  <body>
    ...
  </body>
</html>
```

### 忘了 hgroup 元素吧
Bad:
```
<hgroup>
  <h1>HTML Best Practices</h1>
  <h2>For writing maintainable and scalable HTML documents.</h2>
</hgroup>
```
Good:
```
<h1>HTML Best Practices</h1>
<p>For writing maintainable and scalable HTML documents.</p>
```

###仅仅当在联系信息的时候用 address 元素
Bad:
```
<address>No rights reserved.</address>
```
Good:
```
<address>Contact: <a href="https://twitter.com/hail2u_">Kyo Nagashima</a></address>
```
### pre 元素不要在新的一行开始写


Bad:
```
<pre>
&lt;!DOCTYPE html&gt;
</pre>
```
Good:
```
<pre>&lt;!DOCTYPE html&gt;
</pre>
```

###在引号元素里面使用 appropriate 元素
Bad:
```
<blockquote>For writing maintainable and scalable HTML documents.</blockquote>
```
Good:
```
<blockquote>
  <p>For writing maintainable and scalable HTML documents.</p>
</blockquote>
```

### 不要直接包含属性在 blockquote 元素里
Bad:
```
<blockquote>
  <p>For writing maintainable and scalable HTML documents.</p>

  <p>— HTML Best Practices</p>
</blockquote>
```
Good:
```
<blockquote>
  <p>For writing maintainable and scalable HTML documents.</p>
</blockquote>

<p>— HTML Best Practices</p>
```
Also good (recommended by WHATWG):
```
<figure>
  <blockquote>
    <p>For writing maintainable and scalable HTML documents.</p>
  </blockquote>

  <figcaption>— HTML Best Practices</figcaption>
</figure>
```
Also good too (recommended by W3C):
```
<blockquote>
  <p>For writing maintainable and scalable HTML documents.</p>

  <footer>— HTML Best Practices</footer>
</blockquote>
```

###每行只写一个列表项目
Bad:
```
<ul>
  <li>General</li><li>The root Element</li><li>Sections</li>...
</ul>
```
Good:
```
<ul>
  <li>General</li>
  <li>The root Element</li>
  <li>Sections</li>
  ...
</ul>
```
###给 ol 元素用上 type 属性

Bad:
```
<head>
  <style>
    .toc {
      list-style-type: upper-roman;
    }
  </style>
</head>
<body>
  <ol class="toc">
    <li>General</li>
    <li>The root Element</li>
    <li>Sections</li>
    ...
  </ol>
</body>
```
Good:
```
<body>
  <ol type="I">
    <li>General</li>
    <li>The root Element</li>
    <li>Sections</li>
    ...
  </ol>
</body>
```

###把 figcaption 元素放在 figure 元素里的开头或结尾

Bad:
```
<figure>
  <img alt="Front cover of the “HTML Best Practices” book" src="/img/front-cover.png">
  <figcaption>“HTML Best Practices” Cover Art</figcaption>
  <img alt="Back cover of the “HTML Best Practices” book" src="/img/back-cover.png">
</figure>
```
Good:
```
<figure>
  <img alt="Front cover of the “HTML Best Practices” book" src="/img/front-cover.png">
  <img alt="Back cover of the “HTML Best Practices” book" src="/img/back-cover.png">
  <figcaption>“HTML Best Practices” Cover Art</figcaption>
</figure>
```

###使用 main 元素

Bad:
```
<div id="content">
  ...
</div>
```
Good:
```
<main>
  ...
</main>
```

###尽量的避免使用 div 标签
Bad:
```
<div class="chapter">
  ...
</div>
```
Good:
```
<section>
  ...
</section>
Text-level semantics
```

###不要把相同的链接分开来，可以用一个来包围
Bad:
```
<h1><a href="https://whatwg.org/">WHATWG</a></h1>

<p><a href="https://whatwg.org/">A community maintaining and evolving HTML since 2004.</a></p>
```
Good:
```
<a href="https://whatwg.org/">
  <h1>WHATWG</h1>

  <p>A community maintaining and evolving HTML since 2004.</p>
</a>
```
###用下载属性下载一个资源


Bad:
```
<a href="/downloads/offline.zip">offline version</a>
```
Good:
```
<a download href="/downloads/offline.zip">offline version</a>
```

###如果需要的话就使用 rel,hreflang 等类型属性
Bad:
```
<a href="/ja/pdf">Japanese PDF version</a>
```
Good:
```
<a href="/ja/pdf" hreflang="ja" rel="alternate" type="application/pdf">Japanese PDF version</a>
```

###清理链接的文本
Bad:
```
<p><a href="/pdf" rel="alternate" type="application/pdf">Click here</a> to view PDF version.</p>
```
Good:
```
<p><a href="/pdf" rel="alternate" type="application/pdf">PDF version</a> is also available.</p>
```

###不要使用 em 元素来警告着重
Bad:
```
<em>Caution!</em>
```
Good:
```
<strong>Caution!</strong>
```

###尽量避免使用 s,i,b,u 这些元素
Bad:
```
<i class="icon-search"></i>
```
Good:
```
<span class="icon-search" aria-hidden="true"></span>
```
###不要在 q 元素里添加引号
Bad:
```
<q>“For writing maintainable and scalable HTML documents”</q>
```
Good:
```
<q>For writing maintainable and scalable HTML documents</q>
```
Also good:
```
“For writing maintainable and scalable HTML documents”
```

###给 abbr 元素添加 title 属性
Bad:
```
<abbr>HBP</abbr>
```
Good:
```
<abbr title="HTML Best Practices">HBP</abbr>
```

###ruby 标记元素要长一点

Bad:
```
<ruby>HTML<rt>えいちてぃーえむえる</ruby>
```
Good:
```
<ruby>HTML<rp> (</rp><rt>えいちてぃーえむえる</rt><rp>) </rp></ruby>
```

###给 non-machine-readable 元素添加 datetime 属性
Bad:
```
<time>Dec 19, 2014</time>
```
Good:
```
<time datetime="2014-12-19">Dec 19, 2014</time>
Specify code language with class attribute prefixed with language-
```

Bad:
```
<code>&lt;DOCTYPE html></code>
```
Good:
```
<code class="language-html">&lt;DOCTYPE html></code>
```

### 让 kbd 元素尽可能的简单

Bad:
```
<kbd><kbd>Ctrl</kbd>+<kbd>F5</kbd></kbd>
```
Good:
```
<kbd>Ctrl+F5</kbd>
```
###尽可能的避免 span 元素
Bad:
```
HTML <span class="best">Best</span> Practices
```
Good:
```
HTML <em>Best</em> Practices
```
###br 元素后面要换行
Bad:
```
<p>HTML<br>Best<br>Practices</p>
```
Good:
```
<p>HTML<br>
Best<br>
Practices</p>
```

###不要滥用 br 元素标签
Bad:
```
<p><label>Rule name: <input name="rule-name" type="text"></label><br>
<label>Rule description:<br>
<textarea name="rule-description"></textarea></label></p>
```
Good:
```
<p><label>Rule name: <input name="rule-name" type="text"></label></p>
<p><label>Rule description:<br>
<textarea name="rule-description"></textarea></label></p>
```

###不要在 del 和 ins 元素里插入其他标签元素

Bad:
```
<p>For writing maintainable and scalable HTML documents.<del> And for mental stability.</p>

<p>Don't trust!</p></del>
```
Good:
```
<p>For writing maintainable and scalable HTML documents.<del> And for mental stability.</del></p>

<del><p>Don't trust!</p></del>
```
##嵌入内容

###如果需要就给 img 元素添加  alt 属性值

Bad:
```
<img src="/img/logo.png">
```
Good:
```
<img alt="HTML Best Practices" src="/img/logo.png">
```

###如果可以就把  Alt 的值空着
Bad:
```
<img alt="Question mark icon" src="/img/icon/help.png">
```
Good:
```
<img alt="" src="/img/icon/help.png"> 
```

###如果有可能就省略 alt 标签
Bad:
```
<img alt="CAPTCHA" src="captcha.cgi?id=82174">
```
Good:
```
<img src="captcha.cgi?id=82174" title="CAPTCHA">
```

###清空 iframe 元素
Bad:
```
<iframe src="/ads/default.html">
  <p>If your browser support inline frame, ads are displayed here.</p>
</iframe>
```
Good:
```
<iframe src="/ads/default.html"></iframe>
```
###map 元素内容

Bad:
```
<map name="toc">
  <a href="#general">General</a>
  <area alt="General" coords="0, 0, 40, 40" href="#General"> |
  <a href="#the_root_element">The root element</a>
  <area alt="The root element" coords="50, 0, 90, 40" href="#the_root_element"> |
  <a href="#sections">Sections</a>
  <area alt="Sections" coords="100, 0, 140, 40" href="#sections">
</map>
```
Good:
```
<map name="toc">
  <p>
    <a href="#general">General</a>
    <area alt="General" coords="0, 0, 40, 40" href="#General"> |
    <a href="#the_root_element">The root element</a>
    <area alt="The root element" coords="50, 0, 90, 40" href="#the_root_element"> |
    <a href="#sections">Sections</a>
    <area alt="Sections" coords="100, 0, 140, 40" href="#sections">
  </p>
</map>
```
###提供音频或视频元素后备内容

Bad:
```
<video>
  <source src="/mov/theme.mp4" type="video/mp4">
  <source src="/mov/theme.ogv" type="video/ogg">
  ...
</video>
```
Good:
```
<video>
  <source src="/mov/theme.mp4" type="video/mp4">
  <source src="/mov/theme.ogv" type="video/ogg">
  ...
  <iframe src="//www.youtube.com/embed/..." allowfullscreen></iframe>
</video>
```

## 表格数据

###每行写一个 td
Bad:
```
<tr>
  <td>General</td><td>The root Element</td><td>Sections</td>
</tr>
```
Good:
```
<tr>
  <td>General</td>
  <td>The root Element</td>
  <td>Sections</td>
</tr>
```
### 给表格使用表头 header

Bad:
```
<table>
  <thead>
    <tr>
      <td><strong>Element</strong></td>
      <td><strong>Empty</strong></td>
      <td><strong>Tag omission</strong></td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong><code>pre</code></strong></td>
      <td>No</td>
      <td>Neither tag is omissible</td>
    </tr>
    <tr>
      <td><strong><code>img</code></strong></td>
      <td>Yes</td>
      <td>No end tag</td>
    </tr>
  </tbody>
</table>
```
Good:
```
<table>
  <thead>
    <tr>
      <th>Element</th>
      <th>Empty</th>
      <th>Tag omission</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th><code>pre</code></th>
      <td>No</td>
      <td>Neither tag is omissible</td>
    </tr>
    <tr>
      <th><code>img</code></th>
      <td>Yes</td>
      <td>No end tag</td>
    </tr>
  </tbody>
</table>
```
##表单


###用 label 元素包裹表单

Bad:
```
<p>Query: <input name="q" type="text"></p>
```
Good:
```
<p><label>Query: <input name="q" type="text"></label></p>
```
###尽可能的省略属性
Bad:
```
<label for="q">Query: <input id="q" name="q" type="text"></label>
```
Good:
```
<label>Query: <input name="q" type="text"></label>
```
###使用合适的类型属性的input元素

Bad:
```
<label>Search keyword: <input name="q" type="text"></label>
```
Good:
```
<label>Search keyword: <input name="q" type="search"></label>
```
###当输入框是提交属性时要添加 value 值
Bad:
```
<input type="submit">
```
Good:
```
<input type="submit" value="Search">
```

###当 input 元素有验证属性时，给他添加标题属性
Bad:
```
<input name="security-code" pattern="[0-9]{3}" type="text">
```
Good:
```
<input name="security-code" pattern="[0-9]{3}" title="A security code is a number in three figures." type="text">
```

###不要使用占位符属性标签
Bad:
```
<input name="email" placeholder="Email" type="text">
```
Good:
```
<label>Email: <input name="email" placeholder="john.doe@example.com" type="text"></label>
```
###每个 option 元素一行
Bad:
```
<datalist id="toc">
  <option label="General"><option label="The root element"><option label="Sections">
</datalist>
```
Good:
```
<datalist id="toc">
  <option label="General">
  <option label="The root element">
  <option label="Sections">
</datalist>
```

###给进度条 元素添加最大的属性值
Bad:
```
<progress value="0.5"> 50%</progress>
```
Good:
```
<progress max="100" value="50"> 50%</progress>
```

###给计数元素添加最小和最大值
Bad:
```
<meter value="0.5"> 512GB used (1024GB total)</meter>
```
Good:
```
<meter min="0" max="1024" value="512"> 512GB used (1024GB total)</meter>
```

###把 legend 元素作为 fieldest 元素的第一个元素
Bad:
```
<fieldset>
  <p><label>Is this section is useful?: <input name="usefulness-general" type="checkbox"></label></p>
  ...
  <legend>About "General"</legend>
</fieldset>
```
Good:
```
<fieldset>
  <legend>About "General"</legend>
  <p><label>Is this section is useful?: <input name="usefulness-general" type="checkbox"></label></p>
  ...
</fieldset>
```
##Scripting


###省略 js 的类型属性

Bad:
```
<script type="text/javascript">
  ...
</script>
```
Good:
```
<script>
  ...
</script>
```

###如果 script 元素有异步属性，需要给 script 标签添加异不属性
Bad:
```
<script async src="/js/main.js"></script>
```
Good:
```
<script async defer src="/js/main.js"></script>
```

###不要注释 script 标签里的元素

Bad:
```
<script>
/*<![CDATA[*/
  ...
/*]]>*/
</script>
```
Also bad:
```
<script>
<!--
  ...
// -->
</script>
```
Good:
```
<script>
  ...
</script>
```
###不要动态插入 script 元素标签

Bad:
```
<script>
  var script = document.createElement('script');
  script.async = true;
  script.src = "//example.com/widget.js";
  document.getElementsByTagName('head')[0].appendChild(script);
</script>
```
Good:
```
<script async defer src="//example.com/widget.js"></script>
```
###缩进始终保持一致

Bad:
```
<html>
    <head>
      ...
    </head>
  <body>
    ...
  </body>
</html>
```
Good:
```
<html>
  <head>
    ...
  </head>
  <body>
    ...
  </body>
</html>
```

