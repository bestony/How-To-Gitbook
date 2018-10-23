# 使用 Travis CI 构建 Gitbook HTML

## 为什么要使用 Travis CI 构建 Gitbook

为你的项目接入 Travis CI 后，可以实现你的项目完全在线自动部署，无论你在任何的地方，只要能够接入到互联网，访问到 Github ，就可以更新你的电子书，同时使其自动发布到 Github 上。

特别是你的电子书需要和一些**非技术**类同学协作时， 借助 Gitbook ，他可以只通过浏览器对电子书进行修改，无需在自己的电脑上配置 Gitbook 环境。



## 配置步骤
### 创建 `.travis.yml` 文件

Travis CI 的构建是基于 `.travis.yml` 文件进行的，因此，为了让 Travis CI 能够正常构建，我们先来创建 `.travis.yml`。

访问你的 Github 项目主页，点击其中的 **Create new File**，

![](https://postimg.aliavv.com/newmbp/2z0b1.jpg)

在弹出的界面中填入文件名`.travis.yml`

![](https://postimg.aliavv.com/newmbp/yjb5e.jpg)

并粘贴如下代码：
[import](../.travis.yml)


添加完成后，选择 **commit new file** 即可。

![](https://postimg.aliavv.com/newmbp/6s7wq.jpg)

### 配置 Travis CI


如果你想要借助 Travis CI 来构建，除了创建配置文件外，还需要使用你的 Github 账号登录 Travis CI，进行一些简单的配置。

![Travis CI 官网](https://postimg.aliavv.com/newmbp/0ilx8.jpg)


访问 [Travis CI](https://travis-ci.com/) 官网，使用 Github 登录。

登录后，点击右上角的用户头像，在弹出的下拉窗口中选择 **Settings**

![](https://postimg.aliavv.com/newmbp/jf0vr.jpg)

在下方的 Repository 列表中找到你的项目

![](https://postimg.aliavv.com/newmbp/u8ggk.jpg)

点击项目后的 **Settings**,进入到项目的界面。

在项目界面中找到 **More Options**，选择其中的 **Settings**，

![](https://postimg.aliavv.com/newmbp/66iwj.jpg)

进入到项目设置界面。

在下方的**Environment Variables**中添加一个新的名为`GITHUB_TOKEN` 的环境变量，，将你自己的 [Personal Access Token](https://github.com/settings/tokens) 填入其中，用于后续的 Github Pages 自动上传。

> **[danger] 安全须知**
>
> 请不要将 Token 告诉他人，以免他人使用你的 Token 修改你的项目

![](https://postimg.aliavv.com/newmbp/7ol3l.jpg)



添加完成后，再次点击 **More Options** ，选择其中的 **Trigger Build**。

![](https://postimg.aliavv.com/newmbp/rno5l.jpg)

在弹出的界面中直接点击按钮开始构建

![](https://postimg.aliavv.com/newmbp/7026n.jpg)

随后，你就可以等待 Travis CI 的自动构建了

![](https://postimg.aliavv.com/newmbp/3gi8p.jpg)

稍等片刻，当你发现 Travis CI 的构建变成绿色后，就说明已经构建完成了。

![](https://postimg.aliavv.com/newmbp/910s4.jpg)

此时，回到 Github ，点击界面中的 **Branch**，就可以看到所有的分支了，此时可以看到，已经有了 *gh-pages* 分支，则说明目前我们的 Gitbook 已经构建完成了。

![](https://postimg.aliavv.com/newmbp/quuae.jpg)

此时，你可以访问 `<用户名>.github.io/<仓库名>` 来查看构建好的电子书，比如这本书的地址就是 https://bestony.github.io/gitbook-guide/ 
