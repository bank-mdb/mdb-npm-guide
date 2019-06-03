# 发布私有库
### Lib工程创建
 - 创建项目
    ```shell
    mkdir mdb-test-pkg && cd mdb-test-pkg
    ```
    - 项目npm 初始化,创建package.json
    ```shell
    npm init
    ```
    结果如下:
    ```
    {
    "name": "mdb-test-pkg",
    "version": "1.0.0",
    "description": "my first npm package",
    "main": "index.js",
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1"
    },
    "keywords": [
        "npm",
        "packge"
    ],
    "author": "shangwfa",
    "license": "ISC"
    }
    ```
    - 创建README.md
    ```
    ### mdb-test-pkg

    This is my first npm package!

    It is just for testing.
    ```
    - 创建index.js
    ```
    module.exports = {
        printMsg: function () {
            console.log('this message is from mdb-test-pkg!');
        }
    }
    ```
    - 最终目录结构
    ```
    └── mdb-test-pkg
        ├── README.md
        ├── index.js
        └── package.json
    ```
### 发布Lib到Npm私库
  - 切换镜像
    ```
    nrm use mdb
    ```
  - 登录仓库
    ```
    npm login
    ```
    键入用户名：deployer<br>
    键入密码：admin123<br>
    键入邮箱：npmuser@company.com
  - 镜像注册
    ```
    npm adduser -registry http://10.25.23.102:8081/repository/npm-hosted/
    ```
    键入用户名：deployer<br>
    键入密码：admin123<br>
    键入邮箱：npmuser@company.com
  - 修改 package.json
  ```
  {
  "name": "mdb-test-pkg",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "npm",
    "packge"
  ],
  "publishConfig": {
    "registry": "http://10.25.23.102:8081/repository/npm-hosted/"
  },
  "author": "shangwfa",
  "license": "ISC"
}
```
- 执行发布命令
```
npm publish
```
- 访问仓库，查看是否发布成功
::: tip
[仓库地址](http://10.25.23.102:8081/#browse/browse:npm-hosted)
:::

