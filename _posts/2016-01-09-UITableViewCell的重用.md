---
layout: post
title:  "UITableViewCell的重用"
date:   2016-01-09 10:43:19 +0800
categories: iOS
---
***一句话概括***:  UITableView通过重用池（reusableCells），复用相同标识符的cell来达到节约内存的作用，这就是Cell的重用机制

具体过程如下，UITableView内部是包含两个可变数组来保存cell的，分别保存visibleCells以及reusableCells，

在tableView第一次加载cell的时候，在重用池中找不到指定identifier的cell，就会执行cell的初始化方法，并将其添加到visibleCells中，直至可以铺满屏幕。

在滑动屏幕时，完全离开屏幕的cell会从visibleCell中移出，移动至reusableCells中，将要在屏幕上显示的cell根据identifier在reusableCells中找到同类型的cell并显示到屏幕上，因此最多大约只需要可以铺满屏幕的cell的内存空间。而如果每个cell各自占用空间，对于数据量很大的tableView，内存的开销就不容小视了。

