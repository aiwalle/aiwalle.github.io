---
title: 给自己在网上搭个窝-个人blog搭建
date: 2017-04-10 15:33:10
tags:
---
![](http://7xteev.com2.z0.glb.clouddn.com/next.png)

每个优秀的程序员在成长过程都有许多个人的体会与感悟，这些感悟让他走的更远，而通常个人博客就是这样一个记录个人成长的地方。在这里，程序员可以畅所欲言，分享自己的对技术的体会，对生活的感悟，在这里你可以看到一个对技术对生活充满追求的码农。


拥有一个这样的独立而自由的空间是一件非常有趣的事情。

下面我将带领大家一步步的建立起自己的个人博客。

<!--more-->
### 1.需要用到的应用程序
- node.js     [下载地址](https://nodejs.org/en/) 我下载的版本为v4.4.3

- Git [下载地址](https://git-scm.com/) 如果你已经安装xcode，那已经默认集成git了，不需要再继续安装

- hexo 如果你已经安装好上面两个应用程序，那么现在可以通过[npm](http://baike.baidu.com/link?url=lqLSamEYLbqT81nAaxUPkR-GnBtZc6wTczi_eWYPvLwkfCi88qZ26cwHn0lnqavk4j42QuDuorOrH448L4z7sa#2)来安装hexo，这个过程会需要一些时间，请耐心等待
- **注意：有些教程没有加下面的sudo，操作是执行不成功的，因为需要管理员权限，因此这里需要在下面的命令中加入sudo**

```
$ sudo npm install -g hexo-cli
```
- 执行完上  面的三个操作，那么现在你的电脑已经安装了node.js,git和hexo了

### 2.在GitHub上面建立GitHub Pages
在不购买服务器的前提下，我们的网站需要挂在GitHub Pages上，其实也可以托管在coding上，但是这个就自己去试验，我们这里以GitHub Pages为例。


- 首先建立一个[GitHub](https://github.com/)账号，如下图所示
![Login](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_4.png)

- 然后去注册好的邮箱里面验证一下

- 验证完成后，需要添加一个仓库Repositories
![addRepo](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_6.png)
- 具体的配置信息参考下图
![Repositories](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_10.png)

- 现在我们在地址栏输入：http://bloggithub.github.io
会看到下面这样一个界面
![404](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_12.png)

- 现在我们已经搭建好个人博客的基础了，下面我们要做的就是真正将窝建立起来。

### 3.使用Hexo来显示博客
- 将我们在`github`中建立的仓库`clone`到本地
- 首先建立一个文件夹用来存放`blog`相关的文件，例如我创建了一个`TestBlog`文件，下面的命令是基于我的用户和`github`，不能直接`copy`，需要替换成自己的。
```
$ cd /Users/apple/Documents/TestBlog 
$ git clone https://github.com/bloggithub/bloggithub.github.io.git
```

- 执行完上面的操作我们可以看到下面的文件
![document](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_13.png)

- 使用Hexo建站，参考[地址](https://hexo.io/zh-cn/docs/setup.html)
- 执行下列命令，Hexo将会在指定文件夹中新建所需要的文件。

```
$ hexo init <folder>
$ cd <folder>
$ npm install
```
例如在我的电脑上执行如下命令，第一个命令基于`TestBlog`文件夹，第三个命令基于`bloggithub.github.io`文件夹

```
$ hexo init bloggithub.github.io
$ cd bloggithub.github.io
$ npm install
```
在执行命令的过程中看到如下代码，表示Hexo初始化成功

```
├── cheerio@0.20.0 (entities@1.1.1, dom-serializer@0.1.0, css-select@1.2.0, htmlparser2@3.8.3, jsdom@7.2.2)
├── warehouse@2.2.0 (graceful-fs@4.1.3, is-plain-object@2.0.1, JSONStream@1.1.1, cuid@1.3.8)
├── lodash@4.11.2
├── hexo-log@0.1.2 (bunyan@1.8.1)
├── hexo-util@0.5.3 (striptags@2.1.1, html-entities@1.2.0, camel-case@1.2.2, cross-spawn@2.2.3, highlight.js@9.3.0)
├── hexo-fs@0.1.5 (escape-string-regexp@1.0.5, graceful-fs@4.1.3, chokidar@1.4.3)
└── nunjucks@2.4.2 (asap@2.0.3, yargs@3.32.0, chokidar@1.4.3)
INFO  Start blogging with Hexo!
```

- 显示Hexo的Blog
- 执行以下命令就可以在本地看到我们的`blog`原型了，以下命令都是基于`bloggithub.github.io`文件夹
```
$ hexo s
```
- 命令行中显示
```
INFO  Start processing
INFO  Hexo is running at http://0.0.0.0:4000/. Press Ctrl+C to stop.
```
- 现在我们打开浏览器输入http://0.0.0.0:4000/
将会看到如下的界面
![wangye](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_14.png)
- 是不是很有成就感，不要高兴的太早啦，这里我们仅仅是在本地生成了预览，打开http://bloggithub.github.io  仍然是404的界面。
- 将blog部署到github上，执行下面的操作
先Ctrl+C退出本地预览, 进入`bloggithub.github.io`文件夹，修改站点配置文件(打开_config.yml文件)，将下面的repo地址修改为你的地址
**这里需要注意的是每个冒号和后面之间有一个空格，一定要加上空格，否则会部署失败**
```
deploy:
type: git
repo: https://github.com/bloggithub/bloggithub.github.io.git
branch: master
```

- 执行完上面的操作后，现在我们输入部署命令
```
$ hexo clean
$ hexo g
$ hexo d
```
在部署的过程中如果出现以下的提示
```
ERROR Deployer not found: git
```
那么执行下面的代码后，重新部署一遍

```
$ npm install hexo-deployer-git --save
```
在这个过程中会让你输入你的github账号及密码，部署成功后会出现下面的提示

```
https://github.com/bloggithub/bloggithub.github.io.git.
INFO  Deploy done: git
```
现在我们再打开http://bloggithub.github.io 看看吧
![success](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_16.png)

#### 到现在为止，我们已经将我们的个人blog部署到github上面了，现在无论你在哪里，都可以访问到这个网址啦。

### 4.Hexo 常用的指令
- 这里只说四个指令，说太多容易混乱，请务必牢记下面四个指令
- `hexo s`等同于`hexo serve`生成本地预览
- `hexo clean`清除本地生成的文件
- `hexo g`等同于`hexo generate` 生成最终的静态html文件
- `hexo d`等同于`hexo deploy`部署到github
- `generate`和`deploy，generate`会把我们的配置、文章和主题结合起来生成一堆酷炫的html静态文件放在`public`里面。但此时用户还看不到本地`public`文件里的页面，我们必须用后一个指令`deploy`才能把静态文件部署到`GitHub Pages`上。

#### 每次我们修改了站点配置和主题配置文件后，我们先hexo clean->hexo s->Ctrl+C->hexo g->hexo d，请记住这几个命令的调用顺序。


### 5.关于Hexo的一些设置(不是很重要，可以跳过)
- 官方文档[地址](https://hexo.io/zh-cn/docs/configuration.html)
- _config.yml是整体的配置文件，很多基础配置、插件配置等都需要在里面进行。要注意的是，该文件格式要求极为严格，缺少一个空格都会导致运行错误。

```
title: walle #站点名，站点左上角
subtitle: 我走的很慢，但我从不后退。 #副标题，站点左上角
description: walle #给搜索引擎看的，对站点的描述，可以自定义
author: aiwalle #默认在站点左下角可以看到
email: 12345678@qq.com #邮箱
language: zh-CN #语言包设置。
```

```
# URL 访问地址等信息设置，可根据需要自己修改
url: http://bloggithub.github.io #访问域名
root: /
permalink: :year/:month/:day/:title/ #具体内容页的存储路径结构
tag_dir: tags #标签目录名
archive_dir: archives #归档目录名
category_dir: categories #分类目录名
```
```
#Directory 默认文章和生成目录设置
source_dir: source
public_dir: public
```
```
# Writing 文章布局、写作格式的定义
new_post_name: :title.md # File name of new posts
default_layout: post
auto_spacing: false # Add spaces between asian characters and western characters
titlecase: false # Transform title into titlecase
max_open_file: 100
filename_case: 0
highlight:
enable: true
backtick_code_block: true
line_number: true
tab_replace:
```
```
# Category & Tag 分类和标签设置
default_category: uncategorized
category_map:
tag_map:
```

``` 
# Archives 默认值为2，如果这里都修改为1，相应页面就只会列出标题，而非全文(2: Enable pagination,1: Disable pagination,Fully Disable)
archive: 1
category: 1
tag: 1
```
```
# Server 本地预览服务信息，默认端口是4000，有需要的话可以自己修改
port: 4000
logger: false
logger_format:
```
```
# Date / Time format 日期格式
date_format: MMM D YYYY
time_format: H:mm:ss
```
```
# Pagination 每页显示文章数，可以自定义
per_page: 5
pagination_dir: page
```
```
# Extensions 这里配置站点所用主题和插件
theme: landscape
exclude_generator:
```
```
# Deployment 站点部署到github要配置
deploy:
type: github
repo: https://github.com/bloggithub/bloggithub.github.io.git
branch: master
```

### 6.使用其他主题
- 配置主题
Hexo主题非常多，可以参考[Hexo主题](https://hexo.io/themes/)
- 在这里我们使用的主题为Next，大家可以看一下效果http://aiwalle.com/ ，从我的个人博客上可以看到，这个主题还是比较酷炫的。
- 首先放上Next主题的[官方地址](http://theme-next.iissnan.com/getting-started.html)
- 在终端窗口下，定位到 Hexo 站点目录下。使用` Git clone` 代码，`your-hexo-site `在这里就是`bloggithub.github.io`这个文件夹

```
$ cd your-hexo-site 
$ git clone https://github.com/iissnan/hexo-theme-next themes/next
```

clone的过程也许会需要一点时间，请耐心等待。在我们clone完成后，会在theme文件夹里看到一个next文件夹。这时，进入站点配置文件_config.yml，找到 theme 字段，并将其值更改为 next

```
theme: next
```
- 配置好以后，我们重新生成`hexo s`本地预览看一下效果吧，是不是一个酷炫的页面就出来啦，如果要部署的话记得上面的命令顺序哦---[next官网](http://theme-next.iissnan.com/getting-started.html)。
![next主题效果](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_19.png)

### 7.使用个人域名
- 有时候我们想将blog的地址关联我们的个人域名，看上去也高大上不是！
- 注册个人域名，我的域名实在万网注册的 `aiwalle.com `
当我们在万网买了一个域名后，进入域名解析界面会发现已经有了一些域名，这些都是阿里默认做的操作，我们可以统统删除。
- 上面的github page是我为了截图，专门注册的账号，因此会与下面的账号信息有所不同
修改添加域名解析如下图
![万网解析](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_18.png)
####但是，此时并不能成功访问，因为Github Pages是有限制的，它不允许任意域名都跳转过来，而是只限制一个域名，而且这个域名必须声明在CNAME文件中。
- 创建CNAME文件，创建地址为`source`文件夹下，**这里添加的路径一定要正确，否则很容易跳转域名失败**。

```
$ touch CNAME
```
创建成功以后将CNAME的内容改为你的网站名称，例如我的改为aiwalle.com
- 重新部署hexo，部署完成后在github界面点击Setting。
![github的Setting](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_20.png)

- 向下拉可以看到`Your site is published at http://aiwalle.com.`
![Published](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_21.png)
- 现在我们直接输入网址很可能是无法显示的，不要着急，等待一段时间看看，毕竟解析生效也需要时间。

### 8.添加多说评论
- 使用多说前需要先在 多说 创建一个站点。具体步骤如下：
- 登录后在首页选择 “我要安装”。
- 创建站点，填写站点相关信息。 多说域名 这一栏填写的即是你的 `duoshuo_shortname`，如图：
![创建多说](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_24.png)
- 创建站点完成后在 站点配置文件(_config.yml) 中新增 `duoshuo_shortname `字段，值设置成上一步中的值
![_config.yml中的设置](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_26.png)
- 现在我们在多说后台的设置完成了，现在需要添加代码到我们网页代码中。
修改`themes\landscape\layout\_partial\article.ejs`模板
把

```
<% if (!index && post.comments && config.disqus_shortname){ %>
<section id="comments">
<div id="disqus_thread">
<noscript>Please enable JavaScript to view the <a href="//disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
</div>
</section>
<% } %>
```
改为

```
<% if (!index && post.comments && config.duoshuo_shortname){ %>
<section id="comments">
<!-- 多说评论框 start -->
<div class="ds-thread" data-thread-key="<%= post.layout %>-<%= post.slug %>" data-title="<%= post.title %>" data-url="<%= page.permalink %>"></div>
<!-- 多说评论框 end -->
<!-- 多说公共JS代码 start (一个网页只需插入一次) -->
<script type="text/javascript">
var duoshuoQuery = {short_name:'<%= config.duoshuo_shortname %>'};
(function() {
var ds = document.createElement('script');
ds.type = 'text/javascript';ds.async = true;
ds.src = (document.location.protocol == 'https:' ? 'https:' : 'http:') + '//static.duoshuo.com/embed.js';
ds.charset = 'UTF-8';
(document.getElementsByTagName('head')[0] 
|| document.getElementsByTagName('body')[0]).appendChild(ds);
})();
</script>
<!-- 多说公共JS代码 end -->
</section>
<% } %>
```
- 完成啦，`hexo s`看一看效果
![评论效果](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_27.png)
- 为评论添加系统和浏览器标识
我们常常看到有的blog下面有如下所示的标识，即显示了评论者的系统，又显示了评论者的浏览器，真的是很cool啊，像下面一样。
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_33.png)
这个操作我们只需要修改主题配置的小小的一个地方就可以啦，在next主题里`bloggithub.github.io/themes/next/_config.yml`文件，这里就是主题配置文件，前面都是站点配置文件，打开主题配置文件，将箭头所指的false改为true就可以啦，是不是B格爆棚= =。
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_32.png)
- 还有别的设置就自己看多说文档啦。

###8.使用百度统计
- 首先进入[百度统计网站](http://tongji.baidu.com/web/welcome/login)，选择站长账号登录
- 登录完成后如下图，复制 `hm.js?` 后面那串统计脚本 id，如：
![百度统计](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_28.png)
- 编辑 站点配置文件， 新增字段 `baidu_analytics` 字段，值设置成你的百度统计脚本 id(这里的步骤和上面添加多说评论配置相同)，只是对应的值改变。
- 站点配置完成后，我们需要将baidu提供的代码放到我们的代码中去，我放的位置为`/TestBlog/bloggithub.github.io/themes/next/layout/_partials/footer.swig`中，将上面的代码直接粘贴到`footer.swig`的末尾即可，然后重新部署。
- 如果操作顺利，我们重新部署过后，可以在代码安装检查中看到如下所示
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_29.png)
- 至此，我们添加统计的功能完全搞好了，看看效果
![百度统计表](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_31.png)

### 9.为NexT主题添加文章阅读量统计功能
- 请查看 [为NexT主题添加文章阅读量统计功能](https://notes.wanghao.work/2015-10-21-%E4%B8%BANexT%E4%B8%BB%E9%A2%98%E6%B7%BB%E5%8A%A0%E6%96%87%E7%AB%A0%E9%98%85%E8%AF%BB%E9%87%8F%E7%BB%9F%E8%AE%A1%E5%8A%9F%E8%83%BD.html#%E9%85%8D%E7%BD%AELeanCloud)，这篇blog写的非常详细，我这里就不再复数了
- 添加成功后的效果如下图
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_34.png)
- ####注意：这里有一个巨大的坑啊！！！
- 在我的个人博客我完全按照以上地址进行修改，`leanclound`添加`Classes`与作者写的略有不同我也没放在心上，但是发现第一次的时候可以显示有阅读次数为1，但是第二次就不可以了，一直不显示阅读次数，通过`chrome`的开发者工具查看网页，发现如下图所示
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_1.png)
- 根据上面的博客所写的
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_2.png)
完全不管用啊，我完全没有填写安全域名，为什么会出现这种问题，真的欲哭无泪/(ㄒoㄒ)/~~
- 最后经过我的查找才发现，在Counter数据的ACL里面，默认写入功能被设置为false，因此无论我怎么搞都不行，因此创建Counter的时候，我们不应该使用默认权限，而是应该如下所示来创建。
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_7.png)
- 现在再看，是不是好啦O(∩_∩)O

### 10.搜索
- 当我们的blog建立好以后，是希望别人在搜索相关资源的时候能搜索到我们的，一来提高人气，二来有人关注我们的作品也更能激发我们创作的决心。
- 我的网站SEO做的不好，google可以搜到，但是baidu搜不到，也不知道是什么原因+_+
- 因此也给不了大家太多的建议，大家可以参看这个blog来试试，当然有更好的方法也欢迎给我留言
- 博客地址-----[动动手指，不限于NexT主题的Hexo优化（SEO篇）](http://www.arao.me/2015/hexo-next-theme-optimize-seo/)

### 11.使用七牛来存储图片
- 在使用Hexo的过程中我发现要使用到图片的地方还是很多的，而这些图片虽然占用空间并不大，可是积少成多，当达到一定数量以后，对于电脑的空间还是很浪费的，尤其是对于我128G的Pro来说。
- 因此我将我的所有图片信息都放到七牛上面，上传非常方便，直接通过外链来访问图片。
- 注册七牛账号，具体的过程我就不写了，比较简单都。
- 当我们的账号设置好以后，可以添加资源
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_8.png)
- 上传图片文件
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_9.png)
- 复制外链来使用图片
![](http://7xteev.com2.z0.glb.clouddn.com/Snip20160505_11.png)
- 当上面的操作都做完了以后，我们用`markdown`写文章的时候，插入图片只需要直接复制外链就好啦，是不是很方便呢！

### 12.写文章
- 写文章的具体操作参考官方的指导，[地址](https://hexo.io/zh-cn/docs/writing.html)
- 我说一下我写文章的方式吧。
- 首先通过下面的命令，其中`my new post`为文章标题，执行命令后，会在项目`\source\ _posts`中生成`my new post.md`文件，用编辑器打开编写即可。
```
$ hexo new "My New Post"

```
- `markdown`的语法还是非常简单且易用的，推荐大家去学一下，这个网站我觉得非常不错，简单易懂，大家可以参考去使用`markdown`----[我是网站，点我](https://www.zybuluo.com/mdeditor?url=https%3A%2F%2Fwww.zybuluo.com%2Fstatic%2Feditor%2Fmd-help.markdown)
- 写完文章以后，通过`hexo g`和`hexo d`来进行部署。

### 13.总结
- 最后还是希望大家记住部署的命令**hexo clean->hexo s->Ctrl+C->hexo g->hexo d**，来来回回就这几个命令，相信大家也已经记住了。
- 写了这么多，相信大家也可以顺利的搭建好自己的blog了吧，有了网站不要紧，常写博客才是正道，希望大家能收获到自己创作的喜悦！


###参考资料
- [如何在一天之内搭建以你自己名字为域名且具备cool属性的个人博客](http://www.jianshu.com/p/99665608d295)
- [如何搭建一个独立博客](http://www.jianshu.com/p/05289a4bc8b2)
- [动动手指，不限于NexT主题的Hexo优化（SEO篇）](http://www.arao.me/2015/hexo-next-theme-optimize-seo/)
- [hexo.io](https://hexo.io/)
- [theme-next](http://theme-next.iissnan.com/theme-settings.html)
