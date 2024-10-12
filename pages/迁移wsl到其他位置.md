- [[wsl]]迁移步骤
	- 依次执行命令
	- ```
	  # wsl关机
	  wsl --shutdown
	  
	  # 创建目的文件路径D:\wsl\backup
	  wsl --export Ubuntu-22.04 D:\wsl\backup\ubuntu-22.04.tar
	  
	  # 注销原有的WSL实例
	  wsl --unregister Ubuntu-22.04
	  
	  # 将备份文件导入到D盘的新位置
	  wsl --import Ubuntu-22.04 D:\wsl\ubuntu-22.04 D:\wsl\backup\ubuntu-22.04.tar
	   
	  # 验证迁移是否成功
	  wsl -l --verbose
	  
	  # 不成功重复注销和导入
	  
	  # 一般完成WSL迁移以后，WSL默认以root账户登录，需要使用命令更改默认登录账户
	  ubuntu2204 config --default-user hj
	  
	  
	  ```
- [[linux]]换源
	- ```
	  cp /etc/apt/sources.list /etc/apt/sources.list.bak
	  
	  vim /etc/apt/sources.list 
	  
	  # 全选并删除
	  # vim 中按键  ESC gg dG
	  
	  sudo apt-get upgrade
	  ```