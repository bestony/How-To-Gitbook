# 使用 Travis CI 构建 Gitbook HTML

## 为什么要使用 Travis CI 构建 Gitbook

为你的项目接入 Travis CI 后，可以实现你的项目完全在线自动部署，无论你在任何的地方，只要能够接入到互联网，访问到 Github ，就可以更新你的电子书，同时使其自动发布到 Github 上。

特别是你的电子书需要和一些**非技术**类同学协作时， 借助 Gitbook ，他可以只通过浏览器对电子书进行修改，无需在自己的电脑上配置 Gitbook 环境。


## 配置步骤
### 创建 `.travis.yml` 文件

如果你想要借助 Travis CI 来构建，首先，你需要使用你的 Github 账号登录 Travis CI。

![Travis CI 官网](https://postimg.aliavv.com/newmbp/0ilx8.jpg)


访问 [Travis CI](https://travis-ci.com/) 官网，使用 Github 登录

```yml
language: node_js

node_js:
  - "8"

cache:
  directories:
    - $HOME/.npm

before_install:
  - export TZ='Asia/Shanghai'

install:
  - npm install gitbook-cli -g
  - gitbook install

script:
  - gitbook build . ./build

branches:
  only:
    - master

deploy:
  provider: pages
  skip_cleanup: true
  github_token: $GITHUB_TOKEN
  local_dir: build
  on:
    branch: master
```