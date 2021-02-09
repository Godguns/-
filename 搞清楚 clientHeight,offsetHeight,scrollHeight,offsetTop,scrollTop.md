clientHeight和offsetHeight属性和元素的滚动，位置没有关系，它代表元素的高度，其中：   
clientHeight ：==包括padding==,但不包括border,水平滚动条，margin的元素的高度，对于inline的这个元素属性一直为0，单位px，只读属性   

offsetHeight:==包括padding,border,水平滚动条==，但不包括margin的元素的高度。对于inline元素这个属性一直是0，单位px，只读属性   
scrollHeight: 只有在滚动条有的情况下讨论scrollHeight才有意义，在没有滚动条时scrollHeight==clientHeight恒成立     
scrolltop:的意思是   
还有一个offsettop:当前元素顶部距离最近父元素顶部的距离,和有没有滚动条没有关系。单位px，只读元素。   

![image](https://img.mukewang.com/58f5b3e80001873105110413.jpg)
![image](https://img.mukewang.com/58f5b3700001627d05110413.jpg)      
![image](https://img.mukewang.com/58f5b4050001e99204480302.jpg)   
![image](https://img.mukewang.com/58f5b32e0001a2fa04110247.jpg)   
![image](https://img.mukewang.com/58f5b2fa00012ea604110247.jpg)
