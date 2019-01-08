# Android Memo


- viewpager获取当前view
解决方案：每个 Item setTag后，通过 findViewByTag 获取view.



- android:clipToPadding=“boolean”
	- true:绘制区域会往里面锁
	- flase: 滑动时忽略padding的值
	系统默认是true。