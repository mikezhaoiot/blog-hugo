---
title: "hugo 部署过程"
date: 2023-12-29T11:19:32+08:00
draft: false
---

# 背景

在2023年12月27日浏览微信朋友圈的过程中，看到范冰朋友圈这样写到 : 

打算重新恢复独立博客了，现在托管在 Github Pages 上，域名是 xdash.me。

正逐渐将 2008 以来的博文、公众号、杂志专栏、好书推荐、自制播客视频 shownotes 等迁移过来。

为何恢复独立播客 & 从 WordPress 搬迁到 Github Pages：

- 从「椒盐豆豉」这篇博文获得启发：https://blog.douchi.space/static-blog-half-year/#gsc.tab=0

- 遵循「Setup and Forget」原则，希望在博客这件事上减少折腾，提升动力。避免每年空间续费、时不时被动迁移 IP、需要打开浏览器写誊写博文等麻烦；以后可在任意设备 Markdown 写 + Git 提交 + Github Actions 完成 hugo 渲染生成。

- 静态，既加速读者访问，也让我自己不要动辄去想装插件、widget 的花活了。

- Github backed by Microsoft，稳定可靠。

- 简单，专注在输出，尤其是输出文字之美本身。

- 本地 repo 的草稿，可以直接在 Obsidian 方便地编辑；Obsidian 又是买了 Sync 同步的。所以可以移动状态下随时写，回到电脑前整理妥帖再 commit 发布。

- 没有阅读计数，不被商业裹挟，写自己想写的文，交自己想交的人。

- 部分回归初心，重拾 Geek 人格。

于是准备恢复写博客了，博客中包含技术、总结、生活，就像[云风的blog](https://blog.codingnow.com/) ，随意写写，多总结，多记录，会有不一样的风景。

# blog主题

- 针对event主题主要是字体和颜色的修改，参考[hugo-even 主题样式](https://blog.herbert.top/2020/07/09/how_change_hugo_even_font/)，相关改动可以参考 [字体和颜色修改提交](https://github.com/olOwOlo/hugo-theme-even/compare/master...mikezhaoiot:hugo-theme-even:master)
- 如果even主题有更新，[mike hugo even](https://github.com/olOwOlo/hugo-theme-even/compare/master...mikezhaoiot:hugo-theme-even:master)

# 文章发布

- 在blog目录，使用`hugo new post/some-content.md`创建markdown文件
- 发布：在blog根目录执行`hugo`命令或者`hugo -t even`命令，自动根据md文件生成文章的静态页面，静态页面发布在根目录的public文件夹下面
- 启动Hugo server，查看网站最新效果，在blog根目录执行如下命令: hugo server

# 自动部署

- [GitHub Action实现Hugo博客在GitHub Pages自动部署](https://lucumt.info/post/hugo/using-github-action-to-auto-build-deploy/)

- [ ] Github Action 自动部署存在问题，没办法提交public，导致无法及时更新到github pages

- 自动化部署问题于2023.12.30晚已经解决，参考[自动部署](https://zhuanlan.zhihu.com/p/568764664),核心原因是github_token不支持外部库，我们采用的两个仓库的方案不能使用github_token，另外external_repository 拼写也出现错误。

- theme/even 如果单独的仓库更新会出错，该问题需要待解决。


# 参考文章

- [Hugo搭建个人博客](https://qoant.com/2019/04/blog-with-hugo/)
- [ GitHub Pages + Hugo 搭建个人博客](https://cuttontail.blog/blog/create-a-wesite-using-github-pages-and-hugo/)
