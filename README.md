# cavalei.github.io

个人主页，用 GitHub Pages 托管。

## 发布步骤

1. 新建仓库，**仓库名必须正好是** `cavalei.github.io`
2. 把本目录全部文件上传到该仓库
3. 打开仓库 **Settings**（设置）
4. 左侧菜单找到 **Pages**
5. `Source`（来源）选 **Deploy from a branch**
6. `Branch`（分支）选 **main**，目录选 **/ (root)**
7. 点 **Save**
8. 等 1–2 分钟，访问 **https://cavalei.github.io**

## 本地预览

不需要服务器，直接双击 `index.html` 用浏览器打开即可。

## 结构

```
index.html        页面内容（首屏 + 项目分组 + 关于 + 页脚）
style.css         样式（含浅色/深色两套变量）
assets/hero.jpg   旧版头图，当前版本不再引用，可删
.nojekyll         跳过 Jekyll，纯静态直出
```

## 设计要点

- **首屏不再用大图**：改为排版驱动（标题 + 定位语 + 胶囊链接），手机上首屏更快
- **配色靠 CSS 变量**：`--bg / --fg / --accent / --accent-sf` 改一处全站跟着变
- **深浅色跟随系统**：`prefers-color-scheme` 自动切换，无需手动开关
- **卡片按类型分组**：工具 / 框架 / 游戏模组，标签颜色用 `.b-tool .b-kit .b-mod .b-dl`

## 想改什么

| 位置 | 改什么 |
|---|---|
| `.hero h1` | 名字或一句话主张 |
| `.tagline` | 一句话介绍 |
| `.group` | 分组标题（工具 / 框架 / 游戏模组） |
| `.card` | 项目名、描述、链接、`.meta` 里的元信息 |
| `.badge` | 标签文字与配色类名 |
| `#about` | 自我介绍与联系方式 |
| `footer` | 年份、许可说明 |

## 加一个新项目

复制一段 `<li>` 粘进对应的 `<ul class="cards">`：

```html
<li>
  <a class="card" href="项目链接" target="_blank" rel="noopener">
    <div class="card-top">
      <h4>项目名</h4>
      <span class="badge b-tool">工具</span>
    </div>
    <p>一两句话说明它解决什么问题。</p>
    <div class="meta"><span>版本</span><span>平台</span></div>
  </a>
</li>
```

记得把 `.sec-head` 里的 `.count`（总数）一起改。

## 说明

- 站点大小上限 1 GB，流量每月 100 GB 软限制
- 支持绑自定义域名（Settings → Pages → Custom domain），需要在域名商加 CNAME
- 不能用于商业网站或电商
