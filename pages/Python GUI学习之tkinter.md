- [[tkinter]]教程
	- tags:: python, tkinter
	- [GUI是什么 (biancheng.net)](https://c.biancheng.net/tkinter/what-is-gui.html)
	- example
		- ```python
		  import tkinter as tk
		  
		  # 调用Tk()创建主窗口
		  root_window =tk.Tk()
		  
		  # 给主窗口起一个名字，也就是窗口的名字
		  root_window.title('C语言中文网：c.biancheng.net')
		  # 设置窗口大小:宽x高,注,此处不能为 "*",必须使用 "x"
		  root_window.geometry('450x300')
		  
		  #开启主循环，让窗口处于显示状态
		  root_window.mainloop()
		  ```