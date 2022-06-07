# Sphinx开发网页基本流程

## 01.下载Sphinx

```bash
pip install sphinx
```

## 02.新建文件夹并打开cmd

F1：在新文件目录输入``cmd``回车

<img src="..\_static\001.png" alt="001" style="zoom:50%;" />

F2：打开cmd，切换当前路径至新文件夹

<img src="..\_static\002.png" alt="001" style="zoom:50%;" />

## 03.新建Sphinx项目

在``cmd``中输入`sphinx-quickstart`，新建项目，过程如下：

<img src="..\_static\003.png" alt="001" style="zoom:50%;" />

你会发现，当前文件夹生成了如下文件！

<img src="..\_static\004.png" alt="001" style="zoom:50%;" />

## 04.下载额外的包

1.如果你选择用`markdown`而不是`rst`来编写网页，请下载`myst_parser`

```matlab
pip install myst_parser
```

2.在[sphinx-themes](https://sphinx-themes.org/#themes)选择主题

以选择`Read the Docs`主题为例，你需要安装以下的包

```
pip install sphinx-rtd-theme
```

<img src="..\_static\005.png" alt="001" style="zoom:50%;" />

3.为代码增加“复制代码”按钮的包

```bash
pip install sphinx_copybutton
```

4.使用panels功能需要安装以下包

```bash
pip install sphinx_panels
```

## 05.更改conf.py的默认设置

将下面的代码复制到conf.py中，请根据实际情况做相应更改（比如项目名，扩展的包等）

```bash
# -- Project configuration -----------------------------------------------------
project = 'HappyLaber'
author = 'Happy'
copyright = '2022, Happy'
release = '1.0.0'

# -- General configuration ------------------------------------------------
source_suffix = {
    '.rst': 'restructuredtext',
    '.txt': 'markdown',
    '.md': 'markdown',
}

extensions = [
    'myst_parser',            # Markdown
    'sphinx.ext.mathjax',     # Math
    'sphinx.ext.githubpages', # Gighub
    'sphinx_panels',          # panels
    'sphinx_copybutton',      # Copy Code
]
mathjax_path = "https://cdn.jsdelivr.net/npm/mathjax@2/MathJax.js?config=TeX-AMS-MML_HTMLorMML"

# -- Options for HTML output ----------------------------------------------
templates_path = ['_templates']
html_theme = 'sphinx_rtd_theme'
html_static_path = ['_static']
html_theme_options = {
    "prev_next_buttons_location": "bottom",
}
```

## 06.设置index的默认配置

将`index.rst`更改为`index.md`，然后粘贴下面代码，构建`Matlab`文件夹，在文件夹下建立`index.md`文件，同理，构建`Python`文件夹，在文件夹下建立`index.md`文件，在两个`index.md`中输入你的笔记。

````bash
```{toctree}
:caption: 编程
:maxdepth: 1

Matlab/index
Python/index
```
````

## 07.生成网页

在主文件夹(包含`make.bat`的那个文件夹，这里是`HappyLaber`)下打开cmd，输入如下代码。

```matlab
make clean
make html
```

在下面的路径中打开`index.html`，即可看到你的网页。

<img src="..\_static\006.png" alt="006" style="zoom:50%;" />

<img src="..\_static\007.png" alt="007" style="zoom:50%;" />

## 08.Github托管

### ① 下载git

安装完成后，需要将`C:\Program Files\Git\bin`添加至环境变量

### ② 配置Git SSH

打开Git Bash，输入如下格式代码

```bash
% 配置Git SSH
git config --global user.name 'simplehappy'
git config --global user.email '1292584987@qq.com'
ssh-keygen -t rsa -C '1292584987@qq.com'
```

<img src="..\_static\014.png" alt="014" style="zoom:50%;" />

找到密钥所在文件夹(上图红框里的路径)，复制`id_rsa.pub`的内容。

### ③ 在GitHub上配置SSH keys

点击`New SSH key`，粘贴剪贴板上的内容，完成相关配置。

<img src="..\_static\015.png" alt="014" style="zoom:50%;" />

### ④ 为conf.py增加Github发布的拓展

```bash
extensions = [
    'sphinx.ext.githubpages', # Gighub
]
```

### ⑤ 为Sphinx项目生成网页

```bash
make clean
make html
```

### ⑥ 建立docs文件夹

`docs`文件夹与`build`和`source`同级，并且要把`build/html`下的文件复制到`docs`文件夹

### ⑦ Github上新建项目并上传Sphinx项目

新建项目时一定要选择`Public`，上传代码模板如下：

```bash
git init
git add .
git commit -m "first commit"
git remote add origin https://github.com/happysimple/happysimple.github.io.git
git push -u origin master
```

### ⑧ 生成网址

<img src="..\_static\016.png" alt="014" style="zoom:50%;" />



