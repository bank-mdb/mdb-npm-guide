# 使用私有库
Npm 私有库地址
[http://10.25.23.102:8081/repository/npm-group/](http://10.25.23.102:8081/repository/npm-group/)

- 切换网络
::: tip
可访问代码仓库
:::
- 添加mdb npm镜像
```
nrm add mdb http://10.25.23.102:8081/repository/npm-group/
```
查看是否安装成功
![](https://cdn.sinaimg.cn.52ecy.cn/large/005BYqpgly1g3o7fruiv9j30re0dsqd1.jpg)
- 安装Npm私有库包 mdb-test-pkg
::: tip
mdb-test-pkg 测试用
:::
执行以下命令安装
```
npm install mdb-test-pkg 或 yarn add mdb-test-pkg
```
查看是否安装成功