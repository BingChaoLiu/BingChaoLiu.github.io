---
layout: post
title:  "Markdown"
date:   2018-12-09 00:16:00
categories: 工具
tags: 转载
author: Other
---


# Markdown使用介绍

***************

    [TOC]

# 1.Markdown的介绍

## Markdown 是什么？

Markdown
: 是一种纯文本标记语言，用户可以使用这些标记符号以最小的输入代价生成极富表现力的文档。

标记语言
: 是一种将文本以及文本相关的其他信息结合起来，展现出关于文档结构和数据处理细节的语言.

HTML
: HyperText Markup Language 超文本标记语言 。超文本，即页面可以包含图片、音乐、链接等非文字元素。

CSS
: Cascading Style Sheets 层叠样式单。定义样式结构（如字体、颜色、背景）的语言。

随着html的功能的增多，html也变得越来越乱越臃肿，后面于是就有了CSS，主要负责外观样式等。

**Markdown最终转换的语法，其实就是html** 。比如标题的显示， `### 标题三 `, ` <h3> 标题三  <h3/>` 因此makedown工具同时也支持html标签的。通俗的说，makedown就是将html部分语言转换为更简单的符号标记，方便用户学习与写作。

    ### 标题三

    <h3> 标题三  <h3/>


**Markdown的格式排版显示，是由CSS决定的** 。在不同的Makedown客户端支持的CSS可能不同，最终显示会不同。比如：一、二级标题的下划线、显示背景；







## Markdown 的功能

它可以使用简单的符号标记不同的标题，分割不同的段落，强调粗体或者斜体文字。更棒的是，它还可以通过符号标记制作表格、流程图、复杂公式。

总而言之，不同于其它的编辑器，你只需使用键盘专注于书写文本内容，方便快捷，就可以生成印刷级的排版格式，省却在键盘和工具栏之间来回切换，调整内容和格式的麻烦。目前它已经成为世界上最大的技术分享网站 GitHub (README.MD)和 技术问答网站 StackOverFlow 的御用书写格式。国内很多技术网站也用到，如简书、掘金、CSDN等。


# 2.markdown的作用


> * 发布日记，杂文，所见所想；  如 个人年终总结
>
> * 整理知识，学习笔记；如 代码格式的总结
>
> * 发布个人技术文稿（代码支持）；如 CSDN 、简书、掘金等
>
> * 发布学术论文（公式支持）；


# 3.Markdown 编辑器

**在线：**

[CMD Makedown](https://www.zybuluo.com/mdeditor) ：(收费)  免费版只能使用基本功能，但有非常详细的中文语法介绍，也有客户端。

[StackEdit](https://stackedit.io/) ：开源免费，功能强大，体验良好。

**客户端：**(win)

[有道云笔记](http://note.youdao.com/) ： 功能齐全的工具栏，支持扩展语法，支持网页版、云同步、有历史记录；不支持快捷键操作，不能导出pdf格式文档，滚动编辑器不够流畅；适合平时整理笔记。

[MarkDownPad2](http://markdownpad.com/) ：支持快捷键，能够将文档转换pdf、html格式，界面操作流畅；需要收费（可pojie）、对于较为复杂的语法不支持，但满足平时需求；适合较为简单的说明文档


> *不同编辑器，标准语法基本兼容，但也存在在一些语法和渲染效果上有改动，或者对扩展语法不支持，例如流程图与时序图，复杂表格与复杂公式的呈现。关于Makedown工具有很多，功能强大，但对于复杂语法，兼容性不一，能满足需求即可。*

# 3.Markdown的语法使用

创始人为約翰·格魯伯（John Gruber）的 Markdown 语法说明：  [English](https://daringfireball.net/projects/markdown/syntax)    [Chinese](http://wowubuntu.com/markdown/#list)

作者的标准语法，支持绝大部分的编辑器。但由于Markdown本身的功能有限，一些特定的需求和场景无法被满足，因此产生了许多第三方的扩展语法（如流程图、待办事项、公式）。因此就有标准语法和扩展语法。

## Makedown 标准语法

### 1.分级标题

可以选择在行首加 “#”号和空格（有些编辑器不需要空格），表示不同级别的标题 (H1-H6)，最多6级。如：

    # 一级标题
    ## 二级标题
    ### 三级标题
    #### 四级标题
    ##### 五级标题
    ###### 六级标题


### 2.粗体和斜体

使用 * 和 ** 表示斜体和粗体，符号和文本之间无空格。（也可以使用 _ 和 __ 表示斜体和粗体）

	**我是粗体字**    

	*我是斜体字*

	***我是粗斜体字***


	__我是粗体字__   

	_我是斜体字_

	___我是粗斜体字___


### 3.无序列表

使用 *，+，- 表示无序列表，效果一样。

    * 无序列表项 一
    + 无序列表项 二
    - 无序列表项 三

    + 序列
        + 子序列
            + 子序列
                + 子序列


### 4.有序列表

使用数字 加“.”表示有序列表。

    1. 有序列表项 一
    2. 有序列表项 二
    3. 有序列表项 三


### 5.文字引用

使用 > 表示文字引用。

    >  Markdown 语法的目标是：成为一种适用于网络的书写语言


### 6.行内代码块

使用反引号包起来  \`代码` ，表示行内代码块。

    一起学习下`Activity`，`servier`，`onCreate()`


### 7.代码块

使用四个缩进空格，或者直接使用Tab键，表示代码块

    Bitmap bitmap = Bitmap.createBitmap(view.getWidth(), view.getHeight(), Bitmap.Config.ARGB_8888);
    Canvas mCanvas = new Canvas();
    if (bitmap != null)
    {
    	mCanvas.setBitmap(bitmap);
    	view.draw(mCanvas);
    	mCanvas.setBitmap(null); // 清除引用
    }
    return bitmap;


### 8.高亮代码块

使用 三个反引号 + 语言名称，就可以根据该语法高亮代码。支持多种编程语言的语法高亮

    python:

        ```python

        @requires_authorization
        class SomeClass:
            pass

        if __name__ == '__main__':
            # A comment
            print 'hello world'

        ```

java:

        ```java

        Bitmap bitmap = Bitmap.createBitmap(view.getWidth(), view.getHeight(), Bitmap.Config.ARGB_8888);
        Canvas mCanvas = new Canvas();
        if (bitmap != null)
        {
        	mCanvas.setBitmap(bitmap);
        	view.draw(mCanvas);
        	mCanvas.setBitmap(null);
        }
        return bitmap;

        ```

### 9.外链接

使用  \[描述](链接地址)  为文字增加外链接。

    1.详细介绍可以参考 [MakeDown语法](http://note.youdao.com/iyoudao/?p=2411)

    2.详细介绍可以参考 [http://note.youdao.com/iyoudao/?p=2411](http://note.youdao.com/iyoudao/?p=2411)


### 10.插入图像

使用 \!\[描述](图片链接地址) 插入图像。

    ![Makedown图标](http://markdown.tw/images/208x128.png)


### 11.删除线

使用 ~~ 表示删除线，符号与文本之间没有空格。

    ~~这是一段错误的文本~~


### 12.分割线

另起一行，连续输入三个以上“ * ”，或者“ - ”，或者“ _ ” ，即可分割两段文字内容。

    ---------------------------------------
    华丽的分割线
    *******
    ________


### 13.表格


| 设备      | 价格   |  数量  | 总额|
| :--------  | -----:  | :----: |----|
| 计算机      | \$1600 |   5     
| 手机        |   \$12   |   12   |
| 管线        |    \$1    |  234  |





第一行是标题，标题下面的冒号“：”，可以改变标题对齐方式。

***
***以上这些语法，最常用，也是很多makedown基本支持的。  下面的是扩展，也是进阶***
***

## Makedown 进阶语法

### 1.待办事宜 Todo 列表

在待办的事项文本或者清单文本前加上- [ ]、- [x]

    - [ ] **六月旅行准备**
        - [x] 人员登记
        - [ ] 酒店预订
        - [x] 大巴预订
        - [ ] 购买保险

### 2.目录

使用 [TOC] 可以在当前位置生成文档大纲目录


### 3. 流程图


```flow
st=>start: 开始:>https://note.youdao.com/
io=>inputoutput: 数据
op1=>operation: 执行过程
op=>operation: 执行过程
cond=>condition: 判断条件?
sub=>subroutine: 子程序
e=>end: 结束

st->io->op1->op->cond
cond(yes)->e
cond(no)->sub->io
```

语法：

    tag=>type: content:>url

其中，tag：元素名字，可自定义；

type ：是元素类型，共有6种：

    start  开始

    end  结束

    operation  操作

    subroutine  子程序

    condition  条件

    inputoutput  输入或输出数据

content ：显示的内容

url：添加外链接 （可选）


### 4. 序列图


    ```sequence
    产品->软件: hi，这个功能能实现吗？
    Note right of 软件: 软件看了下效果
    软件-->产品: 以后别问我能不能实现，就问你要不要
    ```


**语法：**

***标题***  
> title:message

***参与者***
>participant 参与者A

***注释***
> note left of 参与者: 信息    //左侧
>
>note right of 参与者: 信息   //右侧
>
> note cover of 参与者: 信息  > 覆盖一个
>
> note cover of 参与者1，参与者2: 信息 //覆盖二个

***交互***

> ->  //直线，实心箭头；
>
> ->>  //直线，空心箭头；
>
> --> //虚线，实心箭头；
>
> -->> //虚线，空心箭头


例子：

    ```sequence
    title: 登录通行证
    participant 客户端
    participant 服务器
    participant 通行证中心
    Note over 客户端: 用户输入通行证的账号、密码
    客户端->>通行证中心: 发送账号、密码
    Note over 通行证中心: 验证账号、密码
    通行证中心-->>客户端: 返回token
    客户端->>服务器: 发送token
    服务器->>通行证中心: 验证token
    通行证中心-->>服务器: 验证成功
    服务器-->>客户端: 登陆成功
    ```

### 5.Mermaid 制图

能够使用文本生成图表和流程图。


更多语法参考：[更多Mermaid语法](https://mermaidjs.github.io/)


#### 流程图

    ```
    graph TD;
        A[开始]-->B{你家人知道你是傻逼吗};
        B-->|知道|C[家人知道了];
        B-->|不知道|D[还未被发现];
        C-->E((傻逼));
        D-->E((傻逼));
    ```


#### 序列图

    ```
    sequenceDiagram
    A->>B: How are you?
    B->>A: Great!
    ```


#### 甘特图

通过活动列表和时间刻度表示出特定项目的顺序与持续时间。一条线条图，横轴表示时间，纵轴表示项目，线条表示期间计划和实际完成情况

    ```
    gantt
        title 项目开发流程
        section 项目确定
            需求分析       :a1, 2016-06-22, 3d
            可行性报告     :after a1, 5d
            概念验证       : 5d
        section 项目实施
            概要设计      :2016-07-05  , 5d
            详细设计      :2016-07-08, 10d
            编码          :2016-07-15, 10d
            测试          :2016-07-22, 5d
        section 发布验收
            发布: 2d
            验收: 3d
    ```



### 6.Html 标签

当makedown的效果，不能准确满足时，那么就可以使用html语法来实现。

**定义字体：**

    <font color="#ff0000" size="5" face="黑体" >我是一行红色的文字</font>

**定义图片：**

    <img src="http://markdown.tw/images/208x128.png">

    <img src="http://markdown.tw/images/208x128.png" width="50%"  alt="图片描述">


    <div  align="center">    
       <img src="http://markdown.tw/images/208x128.png" width="30%" alt="图片描述">
    </div>

    <center> <img src="http://markdown.tw/images/208x128.png" width="30%" alt="图片描述"></center>

**定义表格：**

    <table>
        <tr>
            <th rowspan="2">值班人员</th>
            <th>星期一</th>
            <th>星期二</th>
            <th>星期三</th>
        </tr>
        <tr>
            <td>李强</td>
            <td>张明</td>
            <td>王平</td>
        </tr>
    </table>

### 7.数学公式

    ```math
    E = mc^2

    \sum_{i=1}^n a_i=0

    ```

更多参考语法：[MathJax](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference)

****
***注：使用符号时，注意符号与空格的组合***
****

### 4.为什么要使用Markdown？

1. **易学**  虽然是一门语言，但语法及其简单。（看到这里，你已经学会了）

1. **易写**  掌握十个不到的标记符号，就可以优雅地沉浸式写作，专注内容而不纠结排版。

1. **易读**  纯文本格式，任何文本编辑器多可以打开。部分markdown客户端，可以转换成html、pdf、work等格式。

2.  ...



### 5.在AndroidStudio使用Markdown插件

1. 下载插件  [Markdown Navigator ](https://github.com/vsch/idea-multimarkdown)

![](https://i.imgur.com/tWYjheI.png)

如果下载失败，修改设置再重新下载：

![](https://i.imgur.com/AZdcJJY.png)

2. 使用插件

![](https://i.imgur.com/cwzpRN0.png)

该插件的工具栏是增强功能，需要收费，如想体验，可以免费注册使用15天：

![](https://i.imgur.com/KnpnyUn.png)



> 如工具栏不能使用，或者对语法不熟悉，可以在其他编辑器编辑，然后在复制过来


***************
<center>
     <font color="	#FF7F50" size="50" face="STCAIYUN" > Thank you </font>
</center>

***************


***
