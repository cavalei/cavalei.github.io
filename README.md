# cavalei.github.io

个人主页，用 GitHub Pages 托管。

## 发布步骤

1. 新建仓库，**仓库名必须正好是** `cavalei.github.io`
2. 把本目录全部文件上传到该仓库（保留 `assets/` 目录）
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
index.html        页面内容
style.css         样式
assets/hero.jpg   头图（1600×600）
.nojekyll         跳过 Jekyll，纯静态直出
```

## 头图怎么换

**直接替换 `assets/hero.jpg` 就行**，文件名保持 `hero.jpg`，CSS 不用改。

建议：

| 项目 | 建议值 |
|---|---|
| 尺寸 | 1600 × 600（宽高比约 8:3） |
| 体积 | 300 KB 以内，否则手机上加载慢 |
| 内容 | 主体偏上，左侧留白（名字压在左下角） |
| 亮度 | 偏暗或中间调，纯白图会让白字看不清 |

如果换成浅色图，把 `style.css` 里 `.hero::after` 的遮罩加深即可：

```css
background: linear-gradient(
  to bottom,
  rgba(0, 0, 0, 0.6) 0%,      /* 从 0.42 改成 0.6 */
  rgba(0, 0, 0, 0.3) 45%,
  var(--bg) 100%
);
```

## 头图区域的工作方式

- 高度 400px（手机 300px），文字压在左下角
- 底部用渐变融进 `--bg`（主题背景色），所以往下滚是**平滑过渡**，不是硬切
- 图片加载失败时自动用 CSS 渐变兜底，不会出现空白
- 深色模式自动适配（渐变末端用的是主题色变量）

## 想改什么

| 位置 | 改什么 |
|---|---|
| `index.html` 的 `<h1>` | 名字或昵称 |
| `.tagline` | 一句话介绍 |
| 「项目」卡片 | 项目名、描述、链接 |
| 「关于」 | 自我介绍 |
| 页脚 | 年份、许可说明 |

## 说明

- 站点大小上限 1 GB，流量每月 100 GB 软限制
- 支持绑自定义域名（Settings → Pages → Custom domain），需要在域名商加 CNAME
- 不能用于商业网站或电商
