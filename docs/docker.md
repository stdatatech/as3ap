AS3AP支持docker方式安装。使用AS3AP的docker Image您可以快速体验AS3AP的所有功能。

#### 前置条件
* 您已经安装了docker在您的电脑上，并正确配置。
* 你拥有一个docker hub的账号，并获得我们的授权。

#### 开始使用

* 第一次使用在*nix上使用

我们只用了Docker的Volume映射来保存用户数据到本地磁盘。例如下面的例子中我们使用本地的/tmp/AS3AP来保存用户数据。这样做的目的是您以后使用新版本的AS3AP的docker image的时候，仍然可以加载原来的数据。

```shell
docker run -d -p 3000:3000 -p 8080:8080 -v /tmp/AS3AP:/opt/AS3AP/u-data stdatatech/AS3AP /opt/AS3AP/bin/start.sh <your ipaddress> 8080 
```
!> 上面的命令中有一个ip地址需要您设定为自己的IP地址,他通常为本地的私网地址。您可以设置为127.0.0.1，这种情况下您只能在本地访问AS3AP。

上面的命令运行成功之后，您可以通过 http://localhost:3000 来访问AS3AP。 默认的用户名和密码为admin/admin.
Docker版本的AS3AP仍然需要License。您可以和我们获得联系来获得License，并安装和激活他们。一份License只能和一个容器匹配。

* 停止AS3AP

您可以通过如下命令来停止AS3AP

```shell
docker stop <your container ID>
```
您可以通过如下命令获得container ID

```shell
docker container ls | grep stdatatech/AS3AP
```

* 重新启动AS3AP
  
您可以通过运行如下命令启动

```shell
docker start <container ID>
```
  您可以通过如下命令获得container ID

```shell
docker container ls --all | grep stdatatech/AS3AP
```

* 升级AS3AP

如同第一次运行一样，使用如下命令启动最新的容器:

```shell
docker run -d -p 3000:3000 -p 8080:8080 -v /tmp/AS3AP:/opt/AS3AP/u-data stdatatech/AS3AP /opt/AS3AP/bin/start.sh <your ipaddress> 8080 
```
您需要更新你的license文件，请和我们获得联系来获取您的新的license文件。

#### 使用测试数据

* 下载测试数据

您可以从 https://github.com/stdatatech/dash-examples/releases 下载最新的sqlite数据库文件demo.db.gz。Linux或者Mac下面执行下面的命令解压，Windows上请使用解压工具解压。
```shell
  gzip -d demo.db.gz
```
解压之后您将获得一个demo.db的文件，然后创建sqlite数据源,步骤可[参见](sqlite)

!> 请创建名称为demo的数据源，这很重要，将来导入图表的时候，会根据这个数据源的名称和类型进行自动绑定，这会省去您很多时间。

* 下载图表

您可以到github https://github.com/stdatatech/dash-examples 上下载我们为测试数据创建好的图表并导入进去。 如下图所示:

![Example](dash-example.jpg)

下载完毕之后，解压，您将看到很多json文件，这是您要导入的图表。导入图表见[导入/导出](imexport)