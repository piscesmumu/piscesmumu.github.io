---

layout: post

title:  "UIView与CALayer的关系"

date:   2016-01-23 19:23:58 +0800

categories: iOS 

tags:

- iOS

- UIKit

---

UIView和CALayer是什么关系呢？

UIView继承自UIResponder，包含一个layer属性，而这个layer是CALayer的实例。

UIView的显示内容都是由layer.content提供的，包括backgroundColor，实质上也是对layer方法的封装。

UIView本身只负责UIResponder相关的事件响应，而CALayer负责视图显示。

这体现了**单一职责原则**