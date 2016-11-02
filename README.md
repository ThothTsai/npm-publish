# 如何将自己的项目发布到**npm**的**public**库和私有库中？
##将项目发布到**npm**的**public**库中
###在npm官网上注册**npm**帐号
官网地址：**[https://www.npmjs.com]**
点击官网右上角 **sign up** 进行注册
----
###登录**npm**
在命令行中输入 **_npm login_**
填写刚才注册的 **_username_** 并按回车
填写密码
填写邮箱
当显示 _**Logged in as username on https://registry.npmjs.org/.**_ 表示登录成功
----
###在**public**库中发布项目
进入**package.json**所在的文件夹
在命令行中输入 **_npm publish_**
显示 **_+ packagename@version_** (如：**_+ toto@1.1.1_**) 表示发布成功 
你可以在**npm**的官网上搜索到你发布的项目
其他人可以通过登录和你相同的**npm**镜像，然后在命令行输入 **_npm install packagename_** (如: **_npm install toto_**)对你发布的项目进行安装
----
###取消已发布在**public**库中的项目
登录 **npm**
在命令行中输入 **_npm unpublish packagename@version_** (如：**_npm unpublish toto@1.1.1_**)
显示 _**- packagenme@version**_ 表示成功取消发布
**npm**官网不在能搜索到已取消发布的项目
----
###用命令行注册**npm**帐号
在命令行中输入 **_npm adduser_**
输入用户名、密码、邮箱
当显示 _**Logged in as username on https://registry.npmjs.org/.**_ 表示注册并登录成功
----
###登录不成功
检查用户名密码是否正确
用户名密码正确，可能是当前镜像链接不是你当前用户所注册的镜像链接，在命令行中输入 **_npm set registry http://registry.npmjs.org/_** 完成设置后再重新登录**npm**帐号即可
----
----
##将项目发布到**npm**私有库中
###注册**npm**帐号
私有库限制**adduser**时，联系**npm**私有库管理者为你添加帐号
私有库未限制**adduser**时，可通过** set registry **后直接在命令行中输入 **_npm adduser_** 进行注册
----
###登录**npm** 私有库
首先**npm**需要连接到私有库 (**set registry**),在命令行中输入 **_npm set registry http://192.168.xxx.xxx:xxxx_** (**_http://192.168.xxx.xxx:xxxx_**为私有库地址，不同的私有库地址不同，注意不要省略"**_http://_**")
显示 **_Logged in as username on http://192.168.xxx.xxx:xxxx/._** 表示登录成功
----
###在私有库中发布项目
进入**package.json**所在的文件夹
在命令行中输入 **_npm publish_**
显示 **_+ packagename@version_** 表示发布成功
你可以在 **_http://192.168.xxx.xxx:xxxx _**上看到你发布的项目
其他人可以通过登录该私有库，然后在命令行输入 **_npm install packagename_** (如：**_npm install toto_**)对你发布的项目进行安装
----
###取消已发布在私有库中的项目
登录 **npm**私有库
在命令行中输入 **_npm unpublish packagename@version_**(如：**_npm unpublish toto@1.1.1_**)
显示 _**- packagenme@version**_ 表示成功取消发布
**npm**私有库中不再看到已取消发布的项目

