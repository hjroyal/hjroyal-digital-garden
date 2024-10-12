- linux [[python]]环境
	- 安装conda环境
		- 1、下载miniconda
		  wget https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-py39_23.11.0-1-Linux-x86_64.sh
		- 2、创建可执行权限 chmod 777 Miniconda3-py39_23.11.0-1-Linux-x86_64.sh
		- 3、执行安装命令 ./Miniconda3-py39_23.11.0-1-Linux-x86_64.sh
		- 4、测试conda命令，如果执行报错，则配置环境变量。具体操作为在/etc/profile文件的最后面添加一行 `export PATH=$PATH:/root/miniconda3/bin`，文件保存后再执行 source /etc/profile
			- ```
			  vim /etc/profile
			  
			  # 最后一行添加
			  export PATH=$PATH:/root/miniconda3/bin
			  ```
		- 5、执行 conda init bash ，然后再执行 bash即可进入conda环境
	- pip配置豆瓣源
		-
	- 更新pip
		- `python.exe -m pip install --upgrade pip`
		- 报错解决
		- [『踩坑记录』Ubuntu安装python3-pip报错Package ‘python3-pip‘ has no installation candidate_package python3-pip is not available, but is refer-CSDN博客](https://blog.csdn.net/Xxy605/article/details/135779402)
			- ```
			  sudo add-apt-repository universe
			  sudo apt-get install python3-pip
			  ```
		- Ubuntu换源后没有添加Universe库导致搜不到pip库
-