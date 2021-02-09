关于position 和transform 移动后还会不会占据原来的空间  
> 如果是相对定位（relative），那么它的位置是保留的；
如果是绝对定位（absolute）或固定定位（fixed），则它的位置是不保留的。   
translate()是transform的一个值。
> 
> 改变transform或opacity不会触发浏览器重新布局（reflow）或重绘（repaint），只会触发复合（compositions）(复合是什么，我也不懂，没听说过，有知道的朋友可以在留言区告诉我)。
> 
> transform使浏览器为元素创建一个 GPU 图层
> 
> translate改变位置时，元素依然会占据其原始空间
> 
> 而改变绝对定位会触发重新布局，进而触发重绘和复合。
> 
> 改变绝对定位会使用到 CPU。
> 
> 因此translate()更高效，可以缩短平滑动画的绘制时间。
> 
 