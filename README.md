# 徐彦文 · 个人简历与作品集

一个使用纯 HTML、CSS 和少量 JavaScript 编写的静态个人主页，适合直接部署到 Vercel。当前经历、项目、邮箱和简历下载内容均为初版占位，请替换成真实信息。

## 文件结构

```text
resume-portfolio/
├── index.html     # 页面内容
├── styles.css     # 样式与响应式布局
├── script.js      # 移动端导航、年份和简历占位提示
└── README.md
```

## 本地预览

直接用浏览器打开 `index.html` 即可预览。也可以在项目目录启动一个本地静态服务器：

```bash
python3 -m http.server 8000
```

然后访问 <http://localhost:8000>。

## 上传到 GitHub

1. 登录 GitHub，创建一个新仓库，例如 `resume-portfolio`。
2. 在本项目目录打开终端，执行以下命令（把 `YOUR_GITHUB_NAME` 换成你的 GitHub 用户名）：

   ```bash
   git init
   git add .
   git commit -m "Create personal resume website"
   git branch -M main
   git remote add origin https://github.com/YOUR_GITHUB_NAME/resume-portfolio.git
   git push -u origin main
   ```

3. 后续改完网页后，执行 `git add .`、`git commit -m "Update resume website"` 和 `git push`，Vercel 会自动重新部署。

## 在 Vercel 部署

1. 登录 [Vercel](https://vercel.com/) 并选择 **Add New → Project**。
2. 授权连接 GitHub，导入 `resume-portfolio` 仓库。
3. 这是纯静态网页，无需构建框架。Framework Preset 选择 **Other**；Build Command 和 Output Directory 留空（或使用默认设置），然后点击 **Deploy**。
4. 部署完成后，Vercel 会提供一个 `*.vercel.app` 公网网址。将它发给别人即可访问；之后推送到 GitHub 的更新会自动触发部署。

## 绑定自定义域名

1. 在 Vercel 项目的 **Settings → Domains** 中输入你已注册的域名并添加。
2. 按 Vercel 页面显示的 DNS 记录，到域名注册商的 DNS 管理页面添加记录。常见配置是根域名添加 A 记录、`www` 子域名添加 CNAME；具体以 Vercel 为你的域名给出的值为准。
3. 等待 DNS 生效。Vercel 验证通过并签发 HTTPS 证书后，自定义域名即可访问。你也可以在 Vercel 中设置主域名，并让另一个域名自动跳转过去。

## 替换占位内容

- 在 `index.html` 中更新姓名介绍、经历、项目、技能和 `mailto:` 邮箱。
- 将 PDF 文件放到 `assets/resume.pdf`，然后把首页的“简历 PDF”按钮改成 `<a href="assets/resume.pdf" download>…</a>`。当前按钮会显示提示，不会尝试下载不存在的文件。
- 图片可放入 `assets/`，并在 HTML 中引用；记得把图片一并提交到 GitHub。
