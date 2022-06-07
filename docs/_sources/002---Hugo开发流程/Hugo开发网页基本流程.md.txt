# Hugo开发网页基本流程

```{tip}
本文以Windows系统为例!
```

## 1.下载Hugo

[Hugo下载地址](https://github.com/gohugoio/hugo/releases)

## 2.将下载文件的目录添加至环境变量

<img src="..\_static\018.png" alt="018" style="zoom:40%;" />

<img src="..\_static\019.png" alt="019" style="zoom:50%;" />

## 3.新建站点

```bash
% 打开cmd
hugo new site yourname
```

## 4.选择主题

```{tip}
本文以Coder主题为例,使用F1下载
```

①下载Coder主题，见[主题](https://themes.gohugo.io/)

F1：点击Download下载

F2：如果网络条件较好，可以选择git克隆

```
git init
git submodule add https://github.com/luizdepra/hugo-coder.git themes/hugo-coder
```

②下载完成后，解压至`\yourname\themes\`，并将名字中的`-main`去掉，见下图

<img src="..\_static\021.png" alt="019" style="zoom:50%;" />

③复制`\hugo-coder\exampleSite`下的所有文件至`\yourname\`

④打开`\content\posts`目录，删掉`rich-content.md`和`rich-content.pt-br.md`

## 5.生成博客

切换目录至`\yourname\`，在当前目录打开`cmd`，输入如下命令

```bash
hugo server
```

<img src="..\_static\022.png" alt="019" style="zoom:50%;" />

不要关闭cmd！在网页打开`http://localhost:1313/`，可以看到示例网站

<img src="..\_static\023.png" alt="019" style="zoom:50%;" />

---

## 6.Github托管-Hugo

① 下载git

安装完成后，需要将`C:\Program Files\Git\bin`添加至环境变量

② 配置Git SSH

打开Git Bash，输入如下格式代码

```bash
% 配置Git SSH
git config --global user.name 'simplehappy'
git config --global user.email '1292584987@qq.com'
ssh-keygen -t rsa -C '1292584987@qq.com'
```

<img src="..\_static\014.png" alt="014" style="zoom:50%;" />

找到密钥所在文件夹(上图红框里的路径)，复制`id_rsa.pub`的内容。

③ 在GitHub上配置SSH keys

点击`New SSH key`，粘贴剪贴板上的内容，完成相关配置。

<img src="..\_static\015.png" alt="014" style="zoom:50%;" />

---

④建立仓库

注意：仓库名前面部分要和你的用户名相同！我这里是因为已经有了这个仓库才报错的！

<img src="..\_static\024.png" alt="014" style="zoom:50%;" />

⑤生成网页

<img src="..\_static\025.png" alt="014" style="zoom:50%;" />

生成网页后，你的仓库会多出一个`_config.yml`文件，把下图的两个文件下载下来，放到hugo的public文件夹!

<img src="..\_static\026.png" alt="014" style="zoom:50%;" />

⑥执行Hugo命令生成页面

```bash
hugo
```

⑦上传Public文件夹

新建项目时一定要选择`Public`，上传代码模板如下：

```bash
git init
git add .
git commit -m "first commit"
git remote add origin https://github.com/happysimple/Test.git
git push -u origin master
```

⑧生成网址

<img src="..\_static\027.png" alt="014" style="zoom:50%;" />
