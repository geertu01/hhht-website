作为一个单页模板，Big Picture 的使用要比我以前发布的一些复杂模板简单很多。实际上，除了主页面的 <header> 和 <footer> 外，它基本上就是一堆按照相同模式堆叠的 <section> 元素：

html
<section id="foobar" class="main">
    <div class="content container">
        <header>
            <h2>Foobar</h2>
        </header>
        ...
    </div>
</section>
每个 section 都可以分配一个样式类，用来控制其基本外观（以及在某些情况下的行为）：

style1
居中内容并使用超大号 <h2>。搭配背景图片或背景色使用效果最佳。

style2 left
内容以盒状形式出现在窗口左侧。适合搭配背景图或背景色使用。如果你在设置中启用了 useSectionTransitions，这个盒子将从左侧滑入页面。

style2 right
内容盒子靠右显示。适合搭配背景图或背景色使用。如果启用 useSectionTransitions，将从右侧滑入。

style3 primary
用于常规内容。背景颜色为主色（默认为白色）。

style3 secondary
用于常规内容。背景颜色为次要色（默认为浅灰色）。

另外，还有两个可选的修饰类可以用于增加额外效果：

dark
反转内容配色，使其在深色背景或图片上更清晰可见。

fullscreen
让 section 填满整个窗口（前提是你启用了 useFullScreen 设置）。

灯箱画廊：
画廊功能由我开发的 Poptrox 插件 提供支持。了解详情请查看：
https://github.com/ajlkn/jquery.poptrox

每张图片的 HTML 应该如下所示：

html
<article class="from-(方向)">
    <a href="path/to/fullsize.jpg" class="image fit">
        <img src="path/to/thumbnail.jpg" title="这是图片的标题/说明" alt="" />
    </a>
</article>
from-(方向) 类表示该图片从哪个方向滑入页面。可以是以下任意一个：

from-left（从左）

from-right（从右）

from-bottom（从下）

from-left（重复出现，应为误植）

如果你不想让某张图片滑入页面，可以移除 from-(方向) 类，此时图片将采用淡入效果出现。

联系表单：
要让它工作，请在你的服务器上设置一个脚本接收表单数据，然后将 <form> 的 action 属性指向该脚本，例如：

html
<form method="post" action="http://yourdomain.com/mail.php">
更多信息参考这篇文章：
https://1stwebdesigner.com/tutorials/custom-php-contact-forms
