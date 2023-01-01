#### 主题来源
- [hugo-theme-relearn](https://mcshelby.github.io/hugo-theme-relearn)

#### 主题设置相关
- Shortcodes中代码放置到各个md中，即可使用
- 界面设置MORE部分文档：[menushortcuts](https://mcshelby.github.io/hugo-theme-relearn/cont/menushortcuts/index.html)
- 定义Footer部分，参考[menu-footer](./themes/hugo-theme-relearn/exampleSite/layouts/partials/menu-footer.html)

#### Note
- `.nojekyll`: 用来避免Jekyll起作用，因为这个主题是用hugo来编译的，所以要避免Jekyll起作用
- `docs`： 用来放部署的网站静态文件
- 左下角Star设置在`themes/hugo-theme-relearn/layouts/partials/menu-footer.html`来自定义
- `weight`: 值越小，越靠上
- title是页面显示，menuTitle是左侧目录显示
    ```text
    title: "计算机视觉比赛经验贴"
    menuTitle: "CV"
    ```
- 更改左上角logo，文件：`themes/hugo-theme-relearn/layouts/partials/logo.html`

#### 分支说明
- `main`: 用来作为主要分支，更新从这里开始
- `hugo_source`: 用来放编译网站的必要文件，当`main`中有更新时，会自动同步更新到这里，这里会自动编译部署到`gh-pages`分支
- `gh-pages`: 部署的网站源码，Github Pages就是以这个部署的。
- 框架图如下：
    ```mermaid
    flowchart LR
        A(main) --将全部md文件转换格式为content，更新到--> B(hugo_source) --自动编译部署--> C(gh-pages) --CI--> D(Site)
    ```