# Markdown扩展语法

## 01.数学公式

```bash
行间公式：$$a+b=c$$
行内公式：1.{math}`a+b=c`   2.$a+b=c$
```

## 02.引用

```bash
[文字](链接)

(1)注意"/"方向   
(2)通过../访问上级目录    
```

## 03.特殊效果

```{note}
我在写论文！
```

````bash
```{note}
我在写论文！
```
````

## 04.dropdown

```{dropdown} MyContent
:open:

Is already visible
```

````bash
```{dropdown} MyContent
:open:
Is already visible
```
````

```{dropdown} MyContent
:animate: fade-in
Is already fade-in
```

````bash
```{dropdown} MyContent
:animate: fade-in
Is already fade-in
```
````

## 05.panels

```{panels}
:container: container-lg pb-3
:column: col-lg-4 col-md-4 col-sm-4 col-xs-6 p-2

地震学主站
^^^^^^^^^^
- 计算机基础
- 编程基础

---

地震“学”科研入门教程
^^^^^^^^^^^^^^^^^^^
- 计算机基础
- 编程基础
 
---

地震“学”软件
^^^^^^^^^^^^
- 计算机基础
- 编程基础
```

````bash
```{panels}
:container: container-lg pb-3
:column: col-lg-4 col-md-4 col-sm-4 col-xs-6 p-2

地震学主站
^^^^^^^^^^
- 计算机基础
- 编程基础

---

地震“学”科研入门教程
^^^^^^^^^^^^^^^^^^^
- 计算机基础
- 编程基础
 
---

地震“学”软件
^^^^^^^^^^^^
- 计算机基础
- 编程基础
```
````

## 06.link-button

```{link-button} https://www.baidu.com/
:text: baidu
:classes: stretched-link btn-outline-primary
```

````
```{link-button} https://www.baidu.com/
:text: baidu
:classes: stretched-link btn-outline-primary
```
````

## 07. tabbed

```{eval-rst}
.. tabbed:: macOS

    ::
    
        $ brew install git

.. tabbed:: Windows

   打开 https://git-scm.com/downloads\ ，下载并安装 Git for Windows
```

````bash
```{eval-rst}
.. tabbed:: macOS

    ::
    
        $ brew install git

.. tabbed:: Windows

   打开 https://git-scm.com/downloads\ ，下载并安装 Git for Windows
```
````

## 08.添加下载附件

```bash
{download}`Jason_TEC爬虫程序<../_static/Get_JASON_TEC_FTP.m>`
```

