# 上传到 GitHub Pages

`更新包解压文件` 里的内容就是 GitHub Pages 的站点根目录。上传时把这一层的文件拖入仓库根目录，不要把整个外层文件夹一起上传。

## 网页上传

1. 在 GitHub 新建一个仓库，例如 `jlpt-n1-problem6`，选择 `Public`。
2. 进入仓库，点击 `Add file` → `Upload files`。
3. 上传：
   - `index.html`
   - `demo/` 文件夹
   - `README.md`
   - `GITHUB_PAGES.md`
   - `RELEASE_NOTES.md`
   - `CHECKSUMS.sha256`
4. 点击 `Commit changes`。
5. 打开仓库的 `Settings` → `Pages`。
6. `Source` 选择 `Deploy from a branch`。
7. 分支选择 `main`，目录选择 `/ (root)`，点击 `Save`。
8. 等待 1—2 分钟后访问：

```text
https://你的用户名.github.io/仓库名/
```

五题体验版地址：

```text
https://你的用户名.github.io/仓库名/demo/
```

## 命令行上传

先在 GitHub 创建空仓库，再把下面的用户名和仓库名换成实际值：

```sh
cd "更新包解压文件目录"
git init
git add .
git commit -m "Release JLPT N1 problem 6 v11"
git branch -M main
git remote add origin https://github.com/你的用户名/你的仓库名.git
git push -u origin main
```

然后再按网页上传步骤的第 5—8 步开启 GitHub Pages。

## 后续更新

- 正式版更新：替换根目录的 `index.html`。
- 体验版更新：替换 `demo/index.html`。
- 本项目没有 Service Worker，因此不需要同步升级缓存文件名。
- 如果浏览器仍显示旧页面，强制刷新一次即可。

## 注意

GitHub Pages 是公开静态站点。页面可以被访问、保存或复制，不适合直接承载需要登录或付费保护的内容。

