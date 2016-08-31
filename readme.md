# wordsdance

HTML5 单页面展示的华丽文字特效，CSS3 + JS 实现。

创意来源：[h2y/idea/#5](https://github.com/h2y/idea/issues/5)


## 预览

__请点击链接：[Github Page](https://h2y.github.io/wordsdance/i.html?0=%C2%A1feliz%20cumplea%C3%B1os!&5=Bon%20Anniversaire&10=Alles%20Gute%20Zum%20Geburtstag!&15=%D1%81%20%D0%B4%D0%B5%D0%BD%D1%8C%20%D1%80%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F&20=Hro%27nia%20Polla%27!!!&25=%E3%81%8A%E8%AF%9E%E7%94%9F%E6%97%A5%E3%81%8A%E3%82%81%E3%81%A7%E3%81%A8%E3%81%94%E3%81%96%E3%81%84%E3%81%BE%E3%81%99&30=%E7%94%9F%E6%97%A5%E5%BF%AB%E4%B9%90%EF%BC%81&time0=3000)__

<video width="100%" controls autoplay loop src="https://hzy.pw/wp-content/uploads/2016/08/nimbus-record8-video.webm">
(你的浏览器不支持 video 标签或 webm 视频格式)
</video>


## 用法

单页面 web 应用，地址：<https://h2y.github.io/wordsdance/i.html>

通过 GET 来设定信息显示的文字内容，以及其他设置项：

|Key            |Value                                 |
|:--------------|:-------------------------------------|
|>=0 的整数     |依次要显示的句子内容                     |
|time           |每句话默认的显示时间，默认为 5000(ms)    |
|timeN          |特别设置编号为 N 的句子的显示时间        |
|size           |每个字默认的 font-size，默认为 4(rem)   |
|sizeN          |特别设置编号为 N 的句子中每个字的大小    |

**例子：**

- **&size25=**第一句话**&size25=**the second**&size25=**2000**&size25=**6000
- **&size25=**FIRST!**&size25=**这句话字体必须缩小呢**&size25=**5**&size25=**3


## 实现

并没有使用 Canvas，也并没有使用 SVG。页面中的每个字其实都是一个 DOM，可以在网页中摁 Ctrl+A 试试~

是通过 CSS3 的 transition / transform 两个属性魔法般的实现这样的特效。

transition 设定好动画的持续时间，然后用 JS 修改 transform 为想要达到的特效，中间的补间动画都会由浏览器自动渲染好。
