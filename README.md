1. 下载我的亮度变换器脚本,允许它执行,并将其放到/usr/local/bin/  
`git clone https://github.com/abelxiaoxing/brightness.git`  
`cd brightness`  
`chmod +x brightness`  
`sudo mv brightness /usr/local/bin`  
2. 我们必须允许编辑亮度文件,以便在任何地方都不需要sudo,然而亮度文件开机后默认修改回root权限,因此需要添加开机启动脚本  
`sudo nvim /etc/rc.local`  
  + 末尾添加以下内容  
  `/usr/local/bin/brightness restore`  
  + 重新启动rclocal服务(有的人是rc-local,自行修改)  
  `sudo systemctl restart rclocal`
3. brightness脚本使用方法  
  + `brightness` 获取当前亮度设置  
  + `brightness xx` 将亮度设置为xx,xx为亮度信息,最高亮度255  
  + `brightness inc step` , `brightness dec step` 增加或降低亮度,step为设定的值,不输入step默认为系统亮度的10%  
4. 最后将brightness映射为快捷键(自行设置)
