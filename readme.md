# 季已晴 · 幼儿园毕业相册

《有你就幸福》大二班毕业纪念网页，自动轮播照片与背景音乐。

## 本地预览

在项目目录执行：

```bash
python3 -m http.server 8080
```

浏览器打开：http://localhost:8080

> 不要直接双击 `index.html`，否则部分浏览器可能无法播放音乐。

## 云端部署（推荐 GitHub Pages）

本项目是纯静态网站（`index.html` + `pic/` + `music.mp3`），约 50MB，适合免费静态托管。

### 第一步：上传到 GitHub

1. 在 [GitHub](https://github.com) 新建仓库（例如 `kindergarten-album`），**不要**勾选 README。
2. 在本项目目录执行：

```bash
cd /Users/jilingyang/Projects/Kindergarten
git init
git add index.html pic/ music.mp3 readme.md .gitignore .nojekyll .github/
git commit -m "毕业相册网站"
git branch -M main
git remote add origin https://github.com/你的用户名/kindergarten-album.git
git push -u origin main
```

### 第二步：开启 GitHub Pages

1. 打开仓库 → **Settings** → **Pages**
2. **Source** 选择 **GitHub Actions**
3. 推送代码后，Actions 会自动部署（约 1–3 分钟）
4. 访问地址：`https://你的用户名.github.io/kindergarten-album/`

把链接发给家人朋友，任何设备浏览器都能打开。

---

## 其他部署方式

### Netlify（拖拽上传，免命令行）

1. 打开 [https://app.netlify.com/drop](https://app.netlify.com/drop)
2. 将整个 `Kindergarten` 文件夹拖进去（不要包含 `.tools` 文件夹）
3. 获得 `https://随机名.netlify.app` 地址

### Cloudflare Pages（国内访问较稳定）

1. [Cloudflare Dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create**
2. 连接 GitHub 仓库，或上传文件夹
3. Build command 留空，Output directory 填 `/`（根目录）
4. 可绑定自己的域名

### Vercel

```bash
npx vercel --prod
```

在项目根目录执行，按提示登录即可。

---

## 项目文件说明

| 文件/目录 | 说明 |
|-----------|------|
| `index.html` | 主页面 |
| `pic/` | 照片素材 |
| `music.mp3` | 背景音乐 |
| `.github/workflows/pages.yml` | GitHub Pages 自动部署 |

## 注意事项

- 首次打开需点击 **▶ 播放** 才能播放音乐（浏览器限制）
- 仓库体积约 50MB，首次加载可能稍慢，属正常现象
- 不要上传 `.tools/` 目录（已在 `.gitignore` 中排除）
