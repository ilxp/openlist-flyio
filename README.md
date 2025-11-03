在windows下：事先安装好flyctl
* 1、cd cmd
* 2、flyctl auth login
* 3、克隆
* git clone https://github.com/ilxp/openlist-flyio
* cd openlist-flyio
* flyctl launch
选择Y进行微调：地方选择nrt东京，然后弹出网页修改，确认。开始部署，
【#4、flyctl volumes create data --size 1 --app app名字】
* 4、fly volume create data -r nrt -n 1   #创建1g的空间
* 5、找到alist-render目录下fly.toml文件，增加：
[[mounts]]
  destination = "/opt/openlist/data"
  source = "data"
  
* 6、重新部署：
flyctl deploy --remote-only
