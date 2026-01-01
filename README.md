## 概述
使用Gemini 3等免费 AI 工具辅助能够轻松制作美观与设计感兼具的 PPT。

**tips：如果能熟练掌握 html 语言，就能高效率制作好看的 PPT。**

## 整体流程

以制作面试PPT为例：

### 第一步： AI 制作 PPT 草稿
1. 将 **个人简历** 投喂给 **Gemini 3**，告诉它需求和目的（即我要参加什么级别单位的什么岗位面试，面试有什么要求，比如 PPT 时长、需要涵盖哪些方面的内容等），请它帮忙撰写一份 **PPT 演讲稿**。
2. 把自己感觉满意的演讲稿作为笔记保存到 **Notebooklm**，还可以跟Notebooklm聊天，为该笔记增加其他想要了解或表达的内容。
3. 使用 Notebooklm **“演示文稿”**功能生成 PPT，可以多生成几个版本以储备和参考不同版本的设计亮点。需要注意的是，**Notebooklm 生成的PPT只能以 pdf 格式下载。**

### 第二步：AI 辅助制作精致 PPT
到这一步，操作方法就见仁见智。根据自身的需求和习惯，可以选择不同的方法路径。

**路径1:**  参考 Notebooklm 演示文稿中的设计亮点，使用 Powerpoint 绘制。

**路径2:**  将 Notebooklm 演示文稿中的设计亮点（保存为图片）再次投喂给 **Gemini 3**，请它用 **html语言** 通过**网页**的形式还原该图片。再通过**精修网页代码**来实现美观与设计感兼具的效果。

我个人比较推崇使用**路径2**。因为**网页**相较于**Powerpoint**，有一些独到之处。比如说，网页能够通过代码使用很多成品icon；Powerpoint就可能需要自己额外去找或者绘制。网页制作的模块看起来比较立体，基于代码能够快速制作很多小亮点；Powerpoint视觉效果相对比较扁平。

至于使用html语言制作网页的技巧，这里就不过多展开。总之，我感觉**PPT能实现的效果，网页基本都能实现**。如果不拘泥于格式，也可以使用网页进行放映，而且网页可以有多样的交互设计，相较于Powerpoint更生动有趣。更重要的是，制作网页（用代码表达）是大语言模型的看家本领。大语言模型（主要指Gemini 3）学习过很多很好的网页设计，在网页设计和修改方面可以提供很专业的指导。

## 案例讲解

### Gemini 3 结合 Notebooklm 制作演示文稿

我选择了设计亮点页面，放置在 `Gemini3` 文件夹中。

### html 语句还原设计亮点

将设计亮点图片上传给Gemini 3，给它限定页面格式，同时给一部分其他页面代码作为参考。

如我的其中一个prompt：
```
    # 用html语句还原这张图片，作为网页的一个section。参照以下css style和部分页面代码：
    # 以下是限定网页设计的格式，如使用什么颜色，画布大小（可以理解为ppt页面），标题设计样式等
    <style>
        :root {
            /* 学术灰金配色方案 */

            --slate-gray: #2C3E50;

            /* 深灰蓝，代表学术严谨 */

            --academic-gold: #B08D57;

            /* 沉稳的哑光金 */

            --light-gold: #E5D5B7;

            --bg-neutral: #F4F4F2;

            /* 浅米灰背景 */

            --white: #ffffff;

            --transition-smooth: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);

        }

        body {

            background: radial-gradient(circle at top right, #ffffff, #f0f4f8);

            font-family: "Inter", "system-ui", "PingFang SC", sans-serif;

            margin: 0;

            display: flex;

            justify-content: center;

            align-items: center;

            min-height: 100vh;

            overflow: hidden;

        }

        /* 主页面：增加呼吸感 */

        main {

            flex: 1;

            overflow-y: auto;

            padding: 60px;

            scroll-behavior: smooth;

            background: radial-gradient(circle at top right, #edf2f7, #f8fafc);

        }



        .section-content.active {

            display: block;

        }



        .section-content {

            display: none;

            width: 1168px;

            height: 657px;

            margin: 0 auto;

            background: var(--white);

            padding: 50px;

            border-radius: 16px;

            box-shadow: var(--shadow-md);

            animation: slideUp 0.6s ease-out;

            position: relative;

        }

        .header {

            border-bottom: 1px solid #eee;

            padding-bottom: 30px;

            margin-bottom: 40px;

            text-align: center;

        }

        .title {

            font-size: 32px;

            color: var(--slate-gray);

            margin: 0;

            letter-spacing: 1px;

            font-weight: 600;

        }

        .subtitle {

            font-size: 16px;

            color: var(--academic-gold);

            margin-top: 10px;

            text-transform: uppercase;

            letter-spacing: 3px;

        }
    </style>

    # 篇幅限制，部分页面代码就不展示了。
```

### 手动修改html代码

#### 修改方法
1. 用浏览器打开html文件可以查看页面布局与具体内容。
2. 用VS code打开相应的html文件可以对代码进行编辑和修改。
3. 保存修改的html文件后，刷新浏览器页面，可以查看修改后的页面布局和具体内容。

#### 修改建议
1. 可以将html文件上传给 Gemini 3，向它询问关于网页设计方面的修改建议。
2. 可以把自己的修改需求告诉大语言模型，请它给出修改方案。需要注意的是，由于token限制，大语言模型可能会只给出一个样式，而不给出全部代码。我们可以参考它给出的样式，自己手动补全，或开启新对话分段落请 AI 补全。

我的 html 页面成品代码在 `html` 文件夹中。

### 将网页转换为 PPT
目前可能没有特别好的方法可以将网页直接转换成可以编辑的 PPT 格式文件。如果限定放映格式必须为 PPT 的话，可以将制作好的网页先导出为 pdf 文档，再转为高清的图片（如 300 dpi 的 png 文件），再插入到 Powerpoint 中。

以下展示几个由 Gemini3 亮点设计转换成 html-PPT 页面的案例，相应的Powerpoint文件在 `ppt` 文件夹中。

#### 案例1

![设计亮点1](./Gemini3/pdf1.png "Gemini 3设计亮点1")

![html页面1](./ppt/page1.png "html-ppt页面1")

#### 案例2

![设计亮点2](./Gemini3/pdf2.png "Gemini 3设计亮点2")

![设计亮点3](./Gemini3/pdf3.png "Gemini 3设计亮点3")

![html页面2-3](./ppt/page2-3.png "html-ppt页面2")

## 总结
通过 AI 辅助高效率完成工作的底层逻辑是————理解 AI，善用 AI。
即先了解目前大语言模型的特点，比如：tokoen限制等。先将大任务基于目前商用大语言模型推出的功能分解成 AI 擅长的小任务，再使用 AI 能够理解的语言（**表述清晰，目的明确**）请它完成任务，然后我们根据它提供的结果进行修改。