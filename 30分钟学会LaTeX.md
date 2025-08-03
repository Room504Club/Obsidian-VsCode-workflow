## 什么是 $\LaTeX$？

LaTeX (发音为 “LAY-tek” 或 “LAH-tek”) 是一种用于排版专业外观文档的工具。然而，LaTeX 的操作模式与你可能使用过的许多其他文档生产应用程序有很大不同，例如 Microsoft Word 或 LibreOffice Writer：那些“所见即所得”(WYSIWYG) 的工具为用户提供了一个交互式页面，用户可以在其中键入和编辑文本，并应用各种形式的样式。

LaTeX 的工作方式截然不同：你的文档是一个纯文本文件，其中散布着用于表达所需（排版）结果的 LaTeX _命令_。为了生成一个可见的、经过排版的文档，你的 LaTeX 文件会被一个名为 _TeX 引擎_ 的软件处理，该引擎使用嵌入在你文本文件中的命令来指导和控制排版过程，将 LaTeX 命令和文档文本转换为专业排版的 PDF 文件。这意味着你只需要专注于文档的 _内容_，而计算机将通过 LaTeX 命令和 TeX 引擎来处理 _视觉外观_（格式）。

## 为什么要学习 $\LaTeX$？

关于学习使用 LaTeX 而不是其他文档编写应用程序，可以提出各种支持或反对的论点；但最终，这是一种基于个人偏好、亲和力及文档需求的个人选择。

支持 LaTeX 的论点包括：

- 支持为物理科学排版极其复杂的数学、表格和技术内容；
- 提供脚注、交叉引用和参考文献管理的功能；
- 轻松生成复杂或繁琐的文档元素，如索引、术语表、目录、图表列表；
- 由于其固有的可编程性和通过数千个免费 _附加包_ 的可扩展性，使其高度可定制，适用于定制化的文档制作。

总的来说，LaTeX 为用户提供了对文档制作的高度控制，这些文档可以被排版到极高的标准。当然，也有些类型的文档或出版物 LaTeX 并不擅长，包括许多杂志类出版物中常见的“自由形式”页面设计。

LaTeX 的一个重要好处是文档内容与文档样式的分离：一旦你写好了文档的内容，它的外观就可以轻松改变。同样，你可以创建一个定义特定文档类型布局/样式的 LaTeX 文件，该文件可以用作_模板_，以标准化该类型其他文档的创作/制作；例如，这使得科学出版商可以创建 LaTeX 文章模板，作者使用这些模板来撰写提交给期刊的论文。Overleaf 有一个包含数千个模板的 _画廊_，涵盖了极其广泛的文档类型——从科学文章、报告和书籍到简历和演示文稿。因为这些模板定义了文档的布局和样式，作者只需在 Overleaf 中打开它们——创建一个新项目——然后开始写作以添加他们的内容。

## 编写你的第一份 $\LaTeX$ 文档

第一步是创建一个新的 LaTeX 项目。你可以在自己的计算机上通过创建一个新的 `.tex` 文件来完成此操作；或者，你可以在 Overleaf 中 _开始一个新项目_。

让我们从最简单的可运行示例开始，这个示例可以直接在 Overleaf 中打开：

```latex
\documentclass{article}
\begin{document}
First document. This is a simple example, with no 
extra parameters or packages included.
\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Simplest+working+example+LaTeX+document&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0AFirst+document.+This+is+a+simple+example%2C+with+no+%0Aextra+parameters+or+packages+included.%0A%5Cend%7Bdocument%7D)。

这个例子会产生以下输出：
```
   First document. This is a simple example, with no extra prameters or packages included.
```
你可以看到 LaTeX 已经自动缩进了段落的第一行，为你处理了那部分格式。让我们仔细看看我们代码的每个部分都做了什么。

代码的第一行，`\documentclass{article}`，声明了文档类型，即其 _类_ (class)，它控制了文档的整体外观。不同类型的文档需要不同的类；例如，一份简历/履历将需要与一篇可能使用标准 LaTeX `article` 类的科学论文不同的类。你可能正在处理的其他类型的文档可能需要不同的类，如 `book` 或 `report`。要了解众多可用的 LaTeX 类类型，请访问 [CTAN（Comprehensive TeX Archive Network）](https://www.ctan.org/topic/class)上的相关页面。

设置好文档类之后，我们的内容，即文档的 _主体_ (body)，被写在 `\begin{document}` 和 `\end{document}` 标签之间。打开上面的示例后，你可以对文本进行更改，完成后，通过_重新编译文档_来查看最终排版的 PDF。在 Overleaf 中，只需点击 `Recompile`，如此简短的视频片段所示：
<iframe width="800" height="640"
  src="https://videos.ctfassets.net/nrgyaltdicpt/6yo2PA5aMV3OEZl5NtZKWu/54395f569b830b8183b5e0058d5bc0cc/LL30recompile.mp4"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>

任何 Overleaf 项目都可以配置为每次编辑后自动重新编译：单击 `Recompile` 按钮旁边的小箭头，并将 `Auto Compile` 设置为 `On`，如以下截图所示：
![[LL30autocompile.png]]
看过了如何向文档添加内容后，下一步是给它一个标题。为此，我们必须简要地谈谈 _序言_ (preamble)。

> [!NOTE]- 注释
> ### **对 “什么是 LaTeX？” 的解释**
> 
> 嗨，同学你好！我们来把 LaTeX 想象成两种不同的做事方式，就用画画来打比方吧。
> 
> - **Word/WPS (所见即所得)**: 这就像你直接在一张画布上画画。你拿起画笔，选择颜色，画一笔，画布上立刻就出现一道痕迹。你看到的就是你最后得到的，非常直观。这叫 “WYSIWYG” (What You See Is What You Get)。
>     
> - **LaTeX (代码排版)**: 这更像是你不是亲自画画，而是给一个超级聪明的绘画机器人写指令。你不会直接在画布上画，而是在一个记事本（纯文本文档）里写下这样的指令：“机器人，请在纸的顶端中央，用大号字体写上‘我的暑假报告’”，或者“接下来，请用一个带编号的列表列出我的三个发现”。
>     
> 
> 在这个比喻里：
> 
> - **你的 `.tex` 文件**：就是你写给机器人的那份指令清单。
>     
> - **LaTeX 命令 (比如 `\documentclass`)**：就是指令的具体内容，以 `\` 开头。
>     
> - **TeX 引擎**：就是那个绘画机器人。它会阅读你的指令清单，然后一丝不苟地帮你画出一幅精美、专业的画（也就是最终的 PDF 文件）。
>     
> 
> **核心思想**：用 LaTeX，你只需要管好你要写什么（**内容**），而那些头疼的格式问题，比如字体大小、行间距、页边距、段落缩进等等（**视觉外观**），都交给机器人（LaTeX）去操心。这能让你更专注于写作本身。
> 
> ---
> 
> ### **对 “为什么要学习 LaTeX？” 的解释**
> 
> 你可能会想：“既然 Word 那么直观，我为啥要学写代码这么麻烦的方式呢？” 问得好！在很多情况下，Word 足够了。但 LaTeX 有几个“超能力”，在某些场景下特别厉害：
> 
> 1. **数学公式的“超级英雄”**：如果你是理科生，要写很多复杂的数学公式，比如 $\int_a^bf(x)$，$dx=F(b)−F(a)$ 或者 $\frac{\partial^2u}{\partial t^2}=c^2\nabla^2u$。在 Word 里敲这些简直是噩梦，又慢又丑。但在 LaTeX 里，你只需要写几行代码，就能生成印刷品一样漂亮的公式。
>     
> 2. **自动化的小助手**：想象一下你写了一篇几十页的报告。
>     
>     - **目录**：你只需要一个命令 `\tableofcontents`，LaTeX 就会自动帮你生成完整的目录，而且页码绝对正确。
>         
>     - **引用**：你在文章里提到了“见第5章的图3”，后来你在第2章加了一张图，原来的图3变成了图4。在 Word 里你得手动改，但在 LaTeX 里，它会自动更新所有引用，保证正确。
>         
>     - **参考文献**：管理几十个参考文献很痛苦。LaTeX 可以帮你自动排序、格式化，你只需要专注于写作。
>         
> 3. **“一键换装”的模板**：这是 LaTeX 最酷的功能之一。你可以把**内容**和**样式**分开。
>     
>     - **打个比方**：你写了一篇作文（内容）。今天老师要求用A班的格式上交，你就给它套上A班的“皮肤”（模板）。明天学校要求用正式报告的格式，你就给它换上报告的“皮肤”。你的作文内容一个字都不用改，但它看起来完全不一样了！
>         
>     - **Overleaf 的模板库**：Overleaf 网站上有成千上万个现成的“皮肤”（模板），涵盖了简历、学术论文、报告、演示文稿等。你只需要找一个喜欢的，把自己的内容填进去，一份专业级别的文档就诞生了。
>         
> 
> **总结一下**：学习 LaTeX 就像学习一项新技能，初期可能有点不适应，但一旦掌握，它会在处理复杂、规范的文档时，帮你节省大量的时间和精力，并让你的作品看起来非常专业。
> 
> ---
> 
> ### **对 “编写你的第一份 LaTeX 文档” 的解释**
> 
> 好了，理论说完了，我们来动手“给机器人下达第一条指令”吧！
> 
> 
> ```
> \documentclass{article} % 指令1：告诉机器人，我们要制作一份“文章”
> ```
>
> \begin{document} % 指令2：告诉机器人，正文从这里开始
>
> First document. This is a simple example, with no extra parameters or packages included. % 这是我们要写的内容
>
> \end{document} % 指令3：告诉机器人，正文到此结束
> 
> 这段代码非常简单，我们来逐行拆解：
>
> - `\documentclass{article}`: 这是每份 LaTeX 文档的“开场白”。`\documentclass` 是一个命令，意思是“文档的类型是...”。花括号 `{}` 里的 `article` 就是具体的类型。这就好比你告诉机器人：“听好了，我们这次的目标是制作一份‘文章’(article)。” 如果你要写一本书，这里可能就会写 `book`；写报告就用 `report`。这个命令决定了文档最基本的框架，比如默认纸张大小、有没有章节等。
>     
>
> - `\begin{document}` 和 `\end{document}`: 这是一对“开关”。
>     
>
> ```
>   * `\begin{document}`：意思是“正片开始！”。所有你希望最终出现在 PDF 里的文字、图片、表格，都必须放在这个命令**之后**。
>   * `\end{document}`：意思是“到此结束，收工！”。机器人会忽略这行代码之后的所有内容。
>   * 它们之间的区域，我们称之为 **文档主体 (body)**。
> ```
>
> - **重新编译 (Recompile)**: 你在左边写完了代码（指令），总得让机器人“执行”一下才能看到结果吧？点击 Overleaf 上的 `Recompile` 按钮，就相当于按下了“启动”键。TeX 引擎（机器人）会立刻读取你的所有指令，然后把最终的 PDF 文件显示在右边。
>     
>
> ```
>   * **自动编译 (Auto Compile)**：把它打开后，就相当于机器人一直在盯着你。你左边代码每改动一点，它右边就立刻刷新一次，让你能实时看到效果，非常方便。
> ```
>
> - **序言 (Preamble)**：在我们这个例子里，`\documentclass{article}` 这一行所在的位置，以及它和 `\begin{document}` 之间的那片空白区域，被称为**序言**。现在它虽然是空的，但它其实是“准备区”。以后所有“加载额外工具”（比如加载数学公式包、图片包）或者“进行全局设置”（比如修改页边距）的命令，都将写在这个地方。我们下一节就会讲到它。


---

## 文档的序言 (preamble)

上方的截图显示 Overleaf 将一个 LaTeX 文档存储为名为 `main.tex` 的文件：按照惯例，在命名包含 LaTeX 代码的文档文件时，使用 `.tex` 文件扩展名。

前面的例子展示了文档内容是如何在 `\begin{document}` 命令之后输入的；然而，在你的 `.tex` 文件中，出现在该点**之前**的所有内容都被称为**序言 (preamble)**，它扮演着文档的“设置”部分。在序言中，你定义文档的类（类型），以及诸如撰写文档时使用的语言等具体信息；加载你想要使用的 _包_（稍后会详细介绍），并且在这里你还可以应用其他类型的配置。

一个最小的文档序言可能看起来像这样：

```latex
\documentclass[12pt, letterpaper]{article}
\usepackage{graphicx}
```

其中 `\documentclass[12pt, letterpaper]{article}` 定义了文档的整体类（类型）。附加的参数，必须用逗号分隔，包含在方括号 (`[...]`) 中，用于配置这个 `article` 类的实例；也就是说，我们希望为这个特定的、基于 `article` 类的文档使用的设置。

在这个例子中，这两个参数的作用如下：

1. `12pt` 设置字体大小。

2. `letterpaper` 设置纸张大小。
  

当然，也可以使用其他字体大小，如 `9pt`、`11pt`、`12pt`，但如果没有指定，默认大小是 `10pt`。至于纸张大小，其他可能的值是 `a4paper` 和 `legalpaper`。更多信息请参见关于[页面大小和边距](https://www.overleaf.com/learn/latex/Page_size_and_margins)的文章。

序言中的这行： `\usepackage{graphicx}` 是加载外部包（这里是 `graphicx`）以扩展 LaTeX 功能的一个例子，使其能够导入外部图形文件。LaTeX 包将在[查找和使用 LaTeX 包](https://www.google.com/search?q=https://www.overleaf.com/learn/latex/Management_in_a_large_project%23Finding_and_using_LaTeX_packages)一节中讨论。

### 包含标题、作者和日期信息

要在我们的文档中添加标题、作者和日期，需要在**序言**（**不是**文档的主体部分）中增加三行。这些行是：

- `\title{My first LaTeX document}`: 文档的标题。
    
- `\author{Hubert Farnsworth}`: 在这里你写下作者的名字，并可以选择在花括号内使用 `\thanks` 命令：
    
    - `\thanks{Funded by the Overleaf team.}`: 可以加在作者名之后，在 `author` 命令的花括号内。它会添加一个上标和一个脚注，内容为花括号内的文本。如果你需要在文章中感谢某个机构，这个功能很有用。
        
- `\date{August 2022}`: 你可以手动输入日期，或使用 `\today` 命令在每次编译文档时排版当前日期。
    

添加这些行后，你的序言应该看起来像这样：

```latex
\documentclass[12pt, letterpaper]{article}

\title{My first LaTeX document}
\author{Hubert Farnsworth\thanks{Funded by the Overleaf team.}}
\date{August 2022}
```

要排版标题、作者和日期，请在文档的**主体**部分使用 `\maketitle` 命令：

```latex
\begin{document}
\maketitle

We have now added a title, author and date to our first \LaTeX{} document!
\end{document}
```

现在可以将序言和主体组合起来，生成一个完整的文档，并可以在 Overleaf 中打开：

```latex
\documentclass[12pt, letterpaper]{article}

\title{My first LaTeX document}
\author{Hubert Farnsworth\thanks{Funded by the Overleaf team.}}
\date{August 2022}

\begin{document}

\maketitle
We have now added a title, author and date to our first \LaTeX{} document!

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=My+first+LaTeX+document&snip=%5Cdocumentclass%5B12pt%2C+letterpaper%5D%7Barticle%7D%0A%5Ctitle%7BMy+first+LaTeX+document%7D%0A%5Cauthor%7BHubert+Farnsworth%5Cthanks%7BFunded+by+the+Overleaf+team.%7D%7D%0A%5Cdate%7BAugust+2022%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cmaketitle%0AWe+have+now+added+a+title%2C+author+and+date+to+our+first+%5CLaTeX%7B%7D+document%21%0A%5Cend%7Bdocument%7D)。


### 添加注释

LaTeX 是一种“程序代码”，但它专门用于文档排版；因此，就像用任何其他编程语言编写的代码一样，在文档中包含注释会非常有用。LaTeX **注释**是一段不会被排版或以任何方式影响文档的文本——通常用于添加“待办事项”笔记、包含解释性说明、为复杂的宏提供行内解释或在调试时注释掉 LaTeX 代码的行/节。

要在 LaTeX 中创建注释，只需在该行的开头写一个 `%` 符号，如下面的代码所示，它使用了上面的例子：

```latex
\documentclass[12pt, letterpaper]{article}

\title{My first LaTeX document}
\author{Hubert Farnsworth\thanks{Funded by the Overleaf team.}}
\date{August 2022}

\begin{document}

\maketitle

We have now added a title, author and date to our first \LaTeX{} document!
% 这行是一个注释。它不会被排版在文档中。

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=My+first+LaTeX+document+with+a+comment&snip=%5Cdocumentclass%5B12pt%2C+letterpaper%5D%7Barticle%7D%0A%5Ctitle%7BMy+first+LaTeX+document%7D%0A%5Cauthor%7BHubert+Farnsworth%5Cthanks%7BFunded+by+the+Overleaf+team.%7D%7D%0A%5Cdate%7BAugust+2022%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cmaketitle%0AWe+have+now+added+a+title%2C+author+and+date+to+our+first+%5CLaTeX%7B%7D+document%21%0A%0A%25+This+line+here+is+a+comment.+It+will+not+be+typeset+in+the+document.%0A%5Cend%7Bdocument%7D)。

这个例子产生的输出与之前不含注释的 LaTeX 代码完全相同。

### 粗体、斜体和下划线

接下来，我们来看一些文本格式化命令：

- **粗体**: LaTeX 中的粗体文本使用 `\textbf{...}` 命令排版。
    
- **斜体**: 斜体文本使用 `\textit{...}` 命令产生。
    
- **下划线**: 要给文本加下划线，使用 `\underline{...}` 命令。
    

下一个例子演示了这些命令：

```latex
Some of the \textbf{greatest}
discoveries in \underline{science} 
were made by \textbf{\textit{accident}}.
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=First+example+with+formatted+text&snip=%5Cdocumentclass%5B12pt%2C+letterpaper%5D%7Barticle%7D%0A%5Ctitle%7BMy+first+LaTeX+document%7D%0A%5Cauthor%7BHubert+Farnsworth%5Cthanks%7BFunded+by+the+Overleaf+team.%7D%7D%0A%5Cdate%7BAugust+2022%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cmaketitle%0ASome+of+the+%5Ctextbf%7Bgreatest%7D%0Adiscoveries+in+%5Cunderline%7Bscience%7D+%0Awere+made+by+%5Ctextbf%7B%5Ctextit%7Baccident%7D%7D.%0A%5Cend%7Bdocument%7D)。

另一个非常有用的命令是 `\emph{参数}`，它对其_参数_的影响取决于上下文。在普通文本中，被强调的文本是斜体的，但如果在一个斜体文本中使用，这个行为会反转——见下一个例子：

```latex
Some of the greatest \emph{discoveries} in science 
were made by accident.

\textit{Some of the greatest \emph{discoveries} 
in science were made by accident.}

\textbf{Some of the greatest \emph{discoveries} 
in science were made by accident.}
```

[在 Overleaf 中打开此 `\emph` 示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Using+the+emph+command&snip=%5Cdocumentclass%5B12pt%2C+letterpaper%2C+twoside%5D%7Barticle%7D%0A%5Ctitle%7BMy+first+LaTeX+document%7D%0A%5Cauthor%7BHubert+Farnsworth%5Cthanks%7BFunded+by+the+Overleaf+team.%7D%7D%0A%5Cdate%7BAugust+2022%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cparindent0pt%25+To+remove+the+paragraph+indentation%0A%5Cmaketitle%0ASome+of+the+greatest+%5Cemph%7Bdiscoveries%7D+in+science+%0Awere+made+by+accident.%0A%0A%5Ctextit%7BSome+of+the+greatest+%5Cemph%7Bdiscoveries%7D+%0Ain+science+were+made+by+accident.%7D%0A%0A%5Ctextbf%7BSome+of+the+greatest+%5Cemph%7Bdiscoveries%7D+%0Ain+science+were+made+by+accident.%7D%0A%5Cend%7Bdocument%7D)。

**注意**: 一些包，如 `Beamer`，会改变 `\emph` 命令的行为。

### 添加图片

在本节中，我们将学习如何向 LaTeX 文档中添加图片。Overleaf 支持三种插入图片的方式：

1. 使用编辑器工具栏上的**插入图片**按钮 (`Insert Figure`)，将图片插入**可视化编辑器**或**代码编辑器**。
    
2. **复制并粘贴图片**到**可视化编辑器**或**代码编辑器**中。
    
3. 使用**代码编辑器**编写 LaTeX 代码来插入图形。
    

选项1和2会自动生成插入图片所需的 LaTeX 代码，但这里我们介绍选项3——请注意，你需要先**上传这些图片**到你的 Overleaf 项目中。以下示例演示了如何包含一张图片：


```latex
\documentclass{article}
\usepackage{graphicx} % 导入图形的LaTeX包
\graphicspath{ {images/} } % 配置graphicx包

\begin{document}
The universe is immense and it seems to be homogeneous, 
on a large scale, everywhere we look.
% \includegraphics 命令是由
% graphicx 包提供（实现）的
\includegraphics{universe}  
 
There's a picture of a galaxy above.
\end{document}
```

[在 Overleaf 中打开此图片示例](https://www.overleaf.com/project/new/template/25686?id=107971142&templateName=Example+using+images+in+LaTeX&latexEngine=pdflatex&texImage=texlive-full%3A2022.1&mainFile=)。

将图形导入 LaTeX 文档需要一个**附加包**，它提供了包含外部图形文件所需的命令和功能。上面的例子加载了 `graphicx` **包**，该包提供了许多命令，其中包括用于导入图形的 `\includegraphics{...}` 和告知 LaTeX 图形存放位置的 `\graphicspath{...}`。

要使用 `graphicx` 包，请在你的 Overleaf 文档序言中包含以下行： `\usepackage{graphicx}`

在我们的例子中，命令 `\graphicspath{ {images/} }` 通知 LaTeX 图片存放在一个名为 `images` 的文件夹中，该文件夹位于当前目录下：

![[ImagesInAFolder.png]]

`\includegraphics{universe}` 命令执行了将图片插入文档的实际工作。这里，`universe` 是图片文件的名称，但**没有**扩展名。

**注意**：

- 虽然 `\includegraphics` 命令中允许使用包含扩展名的完整文件名，但最佳实践是**省略文件扩展名**，因为这会提示 LaTeX 搜索所有支持的格式。
    
- 通常，图形的文件名不应包含空格或多个点；在向 Overleaf 上传图片文件时，也建议对文件扩展名使用小写字母。
    

更多关于 LaTeX 包的信息可以在本教程末尾的[查找和使用 LaTeX 包](https://www.google.com/search?q=https://www.overleaf.com/learn/latex/Management_in_a_large_project%23Finding_and_using_LaTeX_packages)一节中找到。

### 图注、标签和引用

图片可以通过 `figure` 环境来添加图注、标签和引用，如下所示：

```latex
\documentclass{article}
\usepackage{graphicx}
\graphicspath{ {images/} }

\begin{document}

\begin{figure}[h]
    \centering
    \includegraphics[width=0.75\textwidth]{mesh}
    \caption{A nice plot.}
    \label{fig:mesh1}
\end{figure}
 
As you can see in figure \ref{fig:mesh1}, the function grows near the origin. This example is on page \pageref{fig:mesh1}.

\end{document}
```

[在 Overleaf 中打开此图片示例](https://www.overleaf.com/project/new/template/25519?id=107980830&templateName=Example+using+image+captions+in+LaTeX&latexEngine=pdflatex&texImage=texlive-full%3A2022.1&mainFile=)。

这个例子会产生以下输出：

这个例子中有几个值得注意的命令：

- `\includegraphics[width=0.75\textwidth]{mesh}`: 这种形式的 `\includegraphics` 指示 LaTeX 将图片的宽度设置为文本宽度的75%——文本宽度的值存储在 `\textwidth` 命令中。
    
- `\caption{A nice plot.}`: 顾名思义，此命令设置图片下方的说明文字（图注），可以放在图片上方或下方。如果你创建了图表列表，这个图注将被用在列表中。
    
- `\label{fig:mesh1}`: 要在文档中引用此图片，你使用 `\label` 命令给它一个标签。该标签用于为图片生成一个编号，并与下一个命令结合使用，让你能够引用它。
    
- `\ref{fig:mesh1}`: 这段代码将被替换为所引用图片对应的编号。
    

插入到 LaTeX 文档中的图片应该放在 `figure` 环境或类似环境中，这样 LaTeX 就可以自动将图片放置在文档中的合适位置。

更多指导包含在以下 Overleaf 帮助文章中：

- [图片的位置](https://www.google.com/search?q=https://www.overleaf.com/learn/latex/Positioning_of_Images)
    
- [插入图片](https://www.overleaf.com/learn/latex/Inserting_Images)

> [!TIP]- 注释
>
> ### **对 “文档的序言” 的解释**
> 
> 咱们继续用“给机器人写指令”的比喻。
> 
> **序言 (Preamble)** 就是你正式开始写正文 (`\begin{document}`) **之前**的所有内容。你可以把它想象成**菜谱的准备阶段** 👨‍🍳。在真正开始炒菜前，你得先把要用的工具和调料都准备好，放在手边。
> 
> `\documentclass[12pt, letterpaper]{article}`
> 
> - 这句指令现在更丰富了。`{article}` 还是告诉机器人我们要做“文章”这道菜。
>     
> - 方括号 `[...]` 里的内容，是**对这道菜的具体要求**。`12pt` 是说“字体要用12号大小”，`letterpaper` 是说“用信纸大小的纸张”。这就好比你对厨师说：“我要一份牛排，五分熟，配黑胡椒酱。”
>     
> 
> `\usepackage{graphicx}`
> 
> - `\usepackage` 是一个超级重要的命令，意思是“**加载一个工具包**”。
>     
> - 这就好比你对机器人说：“等会儿我要在菜里加点装饰（图片），你先把那个专门用来放装饰的工具 (`graphicx` 包) 拿出来准备好。”
>     
> - 没有这个工具包，机器人就不知道怎么处理图片。LaTeX 有成千上万个这样的工具包，用来实现各种各样的功能。
>     
> 
> ### **对 “标题、作者和日期” 的解释**
> 
> 准备工作做好了，现在我们来告诉机器人这份文档的一些基本信息。
> 
> `\title{...}`, `\author{...}`, `\date{...}`
> 
> - 这三条指令非常直白，就是**定义信息**。你只是在告诉机器人：“这份文档的标题叫...”、“作者是...”以及“日期是...”。
>     
> - 注意，这时候机器人只是把这些信息记在脑子里，**它还没有把它们写到纸上**。
>     
> 
> `\maketitle`
> 
> - 这条指令才是真正的“**行动**”命令！它必须放在 `\begin{document}` **之后**。
>     
> - 它的意思是：“机器人，把我刚才告诉你的标题、作者和日期，按照标准的格式，现在就打印出来！”
>     
> 
> 简单说：序言里定义信息（记笔记），正文里用 `\maketitle` 来显示信息（去执行）。
> 
> `\thanks{...}`
> 
> - 这个 `\thanks` 命令像个小彩蛋，它会在作者名字右上角加一个星号 `*`，然后在页脚附上一行小字。通常用来写一些致谢信息，比如“感谢XX团队的资助”。
>     
> 
> ### **对 “添加注释” 的解释**
> 
> 写代码（或者说“指令集”）的时候，我们有时想给自己留个言，做个备忘，但又不希望机器人把这些话也打印到最终的文档里。这时候就需要**注释**。
> 
> 在 LaTeX 里，`%` 这个符号就是“**隐身咒**” 🪄。只要一行代码以 `%` 开头，机器人就会完全忽略这一行。
> 
> - **用途**：你可以用它来写“待办事项”（`% 这里需要再检查一下数据`），或者临时“关掉”某行代码看看效果，而不用真的删除它。这在调试和整理思路时非常有用！
>     
> 
> ### **对 “粗体、斜体和下划线” 的解释**
> 
> 这些是基本的“排版调料”，让你的文本更有表现力。
> 
> - `\textbf{文字}`: 把 `text` 和 `bold` 两个词结合起来记，就是 **text bold** (粗体字)。
>     
> - `\textit{文字}`: `text` 和 `italic`，就是 **text italic** (斜体字)。
>     
> - `\underline{文字}`: `underline` (下划线)。
>     
> 
> `\emph{文字}`
> 
> - 这个 `emph` 是 "emphasize" (强调) 的缩写，它更“聪明”一点。
>     
> - 在普通文字里用它，效果和 `\textit` 一样，会变斜体。
>     
> - 但如果在一句_已经是斜体_的话里用它，它会把被强调的词**变回正体**，从而在斜体中突出出来。它懂得如何“反着来”以达到强调的效果。
>     
> 
> ### **对 “添加图片” 的_解释_**
> 
> 现在，我们来实践一下之前准备好的 `graphicx` 工具包。
> 
> 1. `\usepackage{graphicx}`: (在序言里) 告诉机器人“我们要用图片工具了”。
>     
> 2. `\graphicspath{ {images/} }`: 这句是可选的，但非常推荐。它告诉机器人：“我把所有要用的图片都放在一个叫 `images` 的文件夹里了，你直接去那里找就行。” 这样你的主目录就不会乱七八糟了。
>     
> 3. `\includegraphics{universe}`: 这是**真正插入图片**的命令。意思是：“机器人，把那张名叫 `universe` 的图片放在这里。”
>     
>     - **小技巧**：你发现我们没写 `.jpg` 或 `.png` 这样的文件后缀名吗？这是故意的。这样可以让机器人自己去找它认识的图片格式，更灵活。
>         
> 
> ### **对 “图注、标签和引用” 的解释**
> 
> 这是 LaTeX 的一个**王牌功能** 👑！它能让你像专业人士一样管理图片和引用。
> 
> `\begin{figure}[h]` 和 `\end{figure}`
> 
> - 这创造了一个“**图片专属浮动容器**”。你可以想象成你把图片放进了一个带框的画框里，而不是直接贴在墙上。
>     
> - **为什么需要它？** LaTeX 是个排版专家，它会自动帮你把这个“画框”摆在页面上最美观、最合适的位置（比如页面的顶部或底部），而不是傻傻地在你写代码的地方硬生生挤出一块地方。这能避免出现大段的空白，让版面更好看。 `[h]` 是你给它的一个建议，意思是“尽量放在**这里(here)**”。
>     
> 
> 在 `figure` 这个画框里，你可以做三件大事：
> 
> 1. `\caption{A nice plot.}`: 给这幅画写一个**标题**（图注）。比如“图1：我的实验装置”。
>     
> 2. `\label{fig:mesh1}`: 给这幅画贴一个**秘密的、独一无二的标签**。这个标签 `fig:mesh1` 不会显示在文档里，只有你和机器人知道。这是为了后面能找到它。
>     
> 3. `As you can see in figure \ref{fig:mesh1}...`
>     
>     - `\ref{fig:mesh1}`: 这就是**引用**！你告诉机器人：“还记得那个秘密标签是 `fig:mesh1` 的画吗？把它正式的**编号**（比如 “1” 或者 “5.2”）写在这里。”
>         
> 
> **这个功能为什么强大？** 假设你后来在文章前面又加了三张图，这张图自动从“图1”变成了“图4”。你完全不用管！当你重新编译时，LaTeX 会自动更新所有 `\ref` 的地方，保证你的引用“如图4所示”永远是正确的。再也不用手动检查和修改了！

---
## 在 $\LaTeX$ 中创建列表

你可以使用**环境 (environments)** 来创建不同类型的列表，环境用于封装实现特定排版功能所需的 LaTeX 代码。一个环境以 `\begin{环境名称}` 开始，并以 `\end{环境名称}` 结束，其中 `环境名称` 可能是 `figure`、`tabular` 或列表类型之一：`itemize` 用于无序列表，`enumerate` 用于有序列表。

### 无序列表

无序列表由 `itemize` 环境产生。每个列表项都必须以 `\item` 命令开头，如下所示：

```latex
\documentclass{article}
\begin{document}

\begin{itemize}
  \item 单个条目用一个黑点（即项目符号）表示。
  \item 条目中的文本可以是任意长度。
\end{itemize}

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Example+of+a+LaTeX+unordered+list&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cbegin%7Bitemize%7D%0A++%5Citem+The+individual+entries+are+indicated+with+a+black+dot%2C+a+so-called+bullet.%0A++%5Citem+The+text+in+the+entries+may+be+of+any+length.%0A%5Cend%7Bitemize%7D%0A%5Cend%7Bdocument%7D)。

你也可以打开这个[**更详细的 Overleaf 项目**](https://www.overleaf.com/project/new/template/25521?id=107987258&templateName=Demonstrating+various+types+of+LaTeX+list&latexEngine=pdflatex&texImage=texlive-full%3A2022.1&mainFile=)，它演示了各种类型的 LaTeX 列表。

### 有序列表

有序列表使用与无序列表相同的语法，但是使用 `enumerate` 环境创建的：

Code snippet

```
\documentclass{article}
\begin{document}

\begin{enumerate}
  \item 这是我们列表中的第一个条目。
  \item 列表的数字会随着我们添加的每个条目而增加。
\end{enumerate}

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Example+of+the+enumerate+environment&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cbegin%7Benumerate%7D%0A++%5Citem+This+is+the+first+entry+in+our+list.%0A++%5Citem+The+list+numbers+increase+with+each+entry+we+add.%0A%5Cend%7Benumerate%7D%0A%5Cend%7Bdocument%7D)。

与**无序**列表一样，每个条目都必须以 `\item` 命令开头，在这里，该命令会自动生成从 1 开始的数字有序列表标签值。

要获取更多信息，你可以打开这个[**更详细的 Overleaf 项目**](https://www.overleaf.com/project/new/template/25521?id=107987258&templateName=Demonstrating+various+types+of+LaTeX+list&latexEngine=pdflatex&texImage=texlive-full%3A2022.1&mainFile=)，它演示了各种类型的 LaTeX 列表，或者访问我们关于 **LaTeX 列表的专门帮助文章**，其中提供了更多示例并展示了如何创建自定义列表。

## 在 $\LaTeX$ 中添加数学公式

LaTeX 的主要优点之一是可以轻松地编写数学表达式。LaTeX 提供了两种用于排版数学内容的写作模式：

- **行内 (inline)** 数学模式，用于编写作为段落一部分的公式。
    
- **陈列 (display)** 数学模式，用于编写不属于文本或段落、并且需要另起一行排版的表达式。
    

### 行内数学模式

让我们看一个行内数学模式的例子：

```latex
\documentclass[12pt, letterpaper]{article}
\begin{document}

In physics, the mass-energy equivalence is stated 
by the equation $E=mc^2$, discovered in 1905 by Albert Einstein.

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Inline+LaTeX+maths+example&snip=%5Cdocumentclass%5B12pt%2C+letterpaper%5D%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0AIn+physics%2C+the+mass-energy+equivalence+is+stated+%0Aby+the+equation+%24E%3Dmc%5E2%24%2C+discovered+in+1905+by+Albert+Einstein.%0A%5Cend%7Bdocument%7D)。

要排版行内数学公式，你可以使用以下定界符对之一：`\( ... \)`、`$ ... $` 或 `\begin{math} ... \end{math}`，如下例所示：

```latex
\documentclass[12pt, letterpaper]{article}
\begin{document}

\begin{math}E=mc^2\end{math} is typeset in a paragraph using inline math mode---as is $E=mc^2$, and so too is \(E=mc^2\).

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Demonstrating+inline+math+mode&snip=%5Cdocumentclass%5B12pt%2C+letterpaper%5D%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cbegin%7Bmath%7D%0AE%3Dmc%5E2%0A%5Cend%7Bmath%7D+is+typeset+in+a+paragraph+using+inline+math+mode---as+is+%24E%3Dmc%5E2%24%2C+and+so+too+is+%5C%28E%3Dmc%5E2%5C%29.%0A%5Cend%7Bdocument%7D)。

### 陈列数学模式

在陈列模式下排版的方程可以带编号，也可以不带编号，如下例所示：

```latex
\documentclass[12pt, letterpaper]{article}
\begin{document}

The mass-energy equivalence is described by the famous equation
\[ E=mc^2 \] 
discovered in 1905 by Albert Einstein. 

In natural units ($c = 1$), the formula expresses the identity
\begin{equation}
E=m
\end{equation}

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Display+math+mode+example&snip=%5Cdocumentclass%5B12pt%2C+letterpaper%5D%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0AThe+mass-energy+equivalence+is+described+by+the+famous+equation%0A%5C%5B+E%3Dmc%5E2+%5C%5D+discovered+in+1905+by+Albert+Einstein.+%0A%0AIn+natural+units+%28%24c+%3D+1%24%29%2C+the+formula+expresses+the+identity%0A%5Cbegin%7Bequation%7D%0AE%3Dm%0A%5Cend%7Bequation%7D%0A%5Cend%7Bdocument%7D)。

要排版陈列模式的数学公式，你可以使用以下定界符对之一：`\[ ... \]`、`\begin{displaymath} ... \end{displaymath}` 或 `\begin{equation} ... \end{equation}`。在过去，排版陈列模式数学公式需要使用 `$$` 字符定界符，如 `$$... 此处是陈列数学公式 ...$$`，但**这种方法已不再推荐**：请改用 LaTeX 的定界符 `\[ ... \]`。

### 更完整的例子

以下示例演示了使用 LaTeX 排版的各种数学内容。

```latex
\documentclass{article}
\begin{document}

Subscripts in math mode are written as $a_b$ and superscripts are written as $a^b$. These can be combined and nested to write expressions such as
\[ T^{i_1 i_2 \dots i_p}_{j_1 j_2 \dots j_q} = T(x^{i_1},\dots,x^{i_p},e_{j_1},\dots,e_{j_q}) \]
 
We write integrals using $\int$ and fractions using $\frac{a}{b}$. Limits are placed on integrals using superscripts and subscripts:
\[ \int_0^1 \frac{dx}{e^x} =  \frac{e-1}{e} \]

Lower case Greek letters are written as $\omega$ $\delta$ etc. while upper case Greek letters are written as $\Omega$ $\Delta$.

Mathematical operators are prefixed with a backslash as $\sin(\beta)$, $\cos(\alpha)$, $\log(x)$ etc.

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=More+advanced+LaTeX+math+example&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0ASubscripts+in+math+mode+are+written+as+%24a_b%24+and+superscripts+are+written+as+%24a%5Eb%24.+These+can+be+combined+and+nested+to+write+expressions+such+as%0A%0A%5C%5B+T%5E%7Bi_1+i_2+%5Cdots+i_p%7D_%7Bj_1+j_2+%5Cdots+j_q%7D+%3D+T%28x%5E%7Bi_1%7D%2C%5Cdots%2Cx%5E%7Bi_p%7D%2Ce_%7Bj_1%7D%2C%5Cdots%2Ce_%7Bj_q%7D%29+%5C%5D%0A+%0AWe+write+integrals+using+%24%5Cint%24+and+fractions+using+%24%5Cfrac%7Ba%7D%7Bb%7D%24.+Limits+are+placed+on+integrals+using+superscripts+and+subscripts%3A%0A%0A%5C%5B+%5Cint_0%5E1+%5Cfrac%7Bdx%7D%7Be%5Ex%7D+%3D++%5Cfrac%7Be-1%7D%7Be%7D+%5C%5D%0A%0ALower+case+Greek+letters+are+written+as+%24%5Comega%24+%24%5Cdelta%24+etc.+while+upper+case+Greek+letters+are+written+as+%24%5COmega%24+%24%5CDelta%24.%0A%0AMathematical+operators+are+prefixed+with+a+backslash+as+%24%5Csin%28%5Cbeta%29%24%2C+%24%5Ccos%28%5Calpha%29%24%2C+%24%5Clog%28x%29%24+etc.%0A%5Cend%7Bdocument%7D)。

下一个例子使用了 `equation*` 环境，它由 `amsmath` 包提供，所以我们需要在文档序言中添加以下行：
```latex
\usepackage{amsmath} % 为了使用amsmath环境
```

关于使用 `amsmath` 的更多信息，请参见[**我们的帮助文章**](https://www.overleaf.com/learn/latex/Aligning_equations)。

```latex
\documentclass{article}
\usepackage{amsmath} % 用于 equation* 环境
\begin{document}
\section{First example}

The well-known Pythagorean theorem \(x^2 + y^2 = z^2\) was proved to be invalid for other exponents, meaning the next equation has no integer solutions for \(n>2\):
\[ x^n + y^n = z^n \]

\section{Second example}

This is a simple math expression \(\sqrt{x^2+1}\) inside text. 
And this is also the same: \begin{math}\sqrt{x^2+1}\end{math}
but by using another command.

This is a simple math expression without numbering
\[\sqrt{x^2+1}\] 
separated from text.

This is also the same:
\begin{displaymath}\sqrt{x^2+1}\end{displaymath}
\ldots and this:
\begin{equation*}\sqrt{x^2+1}\end{equation*}
\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=More+math+content+typeset+in+LaTeX&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cusepackage%7Bamsmath%7D%25+For+the+equation%2A+environment%0A%5Cbegin%7Bdocument%7D%0A%5Csection%7BFirst+example%7D%0A%0AThe+well-known+Pythagorean+theorem+%5C%28x%5E2+%2B+y%5E2+%3D+z%5E2%5C%29+was+proved+to+be+invalid+for+other+exponents%2C+meaning+the+next+equation+has+no+integer+solutions+for+%5C%28n%3E2%5C%29%3A%0A%0A%5C%5B+x%5En+%2B+y%5En+%3D+z%5En+%5C%5D%0A%0A%5Csection%7BSecond+example%7D%0A%0AThis+is+a+simple+math+expression+%5C%28%5Csqrt%7Bx%5E2%2B1%7D%5C%29+inside+text.+%0AAnd+this+is+also+the+same%3A+%0A%5Cbegin%7Bmath%7D%0A%5Csqrt%7Bx%5E2%2B1%7D%0A%5Cend%7Bmath%7D%0Abut+by+using+another+command.%0A%0AThis+is+a+simple+math+expression+without+numbering%0A%5C%5B%5Csqrt%7Bx%5E2%2B1%7D%5C%5D+%0Aseparated+from+text.%0A%0AThis+is+also+the+same%3A%0A%5Cbegin%7Bdisplaymath%7D%0A%5Csqrt%7Bx%5E2%2B1%7D%0A%5Cend%7Bdisplaymath%7D%0A%0A%5Cldots+and+this%3A%0A%5Cbegin%7Bequation%2A%7D%0A%5Csqrt%7Bx%5E2%2B1%7D%0A%5Cend%7Bequation%2A%7D%0A%5Cend%7Bdocument%7D)。

LaTeX 中数学公式的可能性是无穷的，所以请务必访问我们的帮助页面，获取关于特定主题的建议和示例：

- [数学表达式](https://www.overleaf.com/learn/latex/Mathematical_expressions)
    
- [下标和上标](https://www.overleaf.com/learn/latex/Subscripts_and_superscripts)
    
- [方括号和圆括号](https://www.overleaf.com/learn/latex/Brackets_and_Parentheses)
    
- [分数和二项式](https://www.overleaf.com/learn/latex/Fractions_and_Binomials)
    
- [对齐方程](https://www.overleaf.com/learn/latex/Aligning_equations_with_amsmath)
    
- [运算符](https://www.overleaf.com/learn/latex/Operators)
    
- [数学模式中的间距](https://www.overleaf.com/learn/latex/Spacing_in_math_mode)
    
- [积分、求和与极限](https://www.overleaf.com/learn/latex/Integrals%2C_sums_and_limits)
    
- [数学模式中的陈列样式](https://www.overleaf.com/learn/latex/Integrals%2C_sums_and_limits)
    
- [希腊字母和数学符号列表](https://www.overleaf.com/learn/latex/List_of_Greek_letters_and_math_symbols)
    
- [数学字体](https://www.overleaf.com/learn/latex/Mathematical_fonts)
    

## 基本文档结构

接下来，我们探讨摘要以及如何将 LaTeX 文档划分为不同的章、节和段落。

### 摘要 (Abstracts)

科学文章通常会提供一个**摘要 (abstract)**，它是对其核心主题或论点的简要概述/总结。下一个例子演示了如何使用 LaTeX 的 `abstract` 环境来排版摘要：

Code snippet

```
\documentclass{article}
\begin{document}

\begin{abstract}
This is a simple paragraph at the beginning of the 
document. A brief introduction about the main subject.
\end{abstract}

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=How+to+create+a+document+abstract&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cbegin%7Babstract%7D%0AThis+is+a+simple+paragraph+at+the+beginning+of+the+%0Adocument.+A+brief+introduction+about+the+main+subject.%0A%5Cend%7Babstract%7D%0A%5Cend%7Bdocument%7D)。

### 段落和换行

有了摘要之后，我们就可以开始写第一个段落了。下一个例子演示了：

- 如何通过按两次“回车键”来创建一个新段落，即结束当前行并插入一个随后的空行；
    
- 如何通过使用 `\\` 命令（一个双反斜杠）插入手动换行符来开始一个新行，而不开始一个新段落；或者，使用 `\newline` 命令。
    

本例中的第三段演示了 `\\` 和 `\newline` 命令的用法：
```latex
\documentclass{article}
\begin{document}
\begin{abstract}
This is a simple paragraph at the beginning of the 
document. A brief introduction about the main subject.
\end{abstract}

After our abstract we can begin the first paragraph, then press ``enter'' twice to start the second one.

This line will start a second paragraph.

I will start the third paragraph and then add \\ a manual line break which causes this text to start on a new line but remains part of the same paragraph. Alternatively, I can use the \verb|\newline|\newline command to start a new line, which is also part of the same paragraph.
\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Example+to+create+a+new+paragraph&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0A%0A%5Cbegin%7Babstract%7D%0AThis+is+a+simple+paragraph+at+the+beginning+of+the+%0Adocument.+A+brief+introduction+about+the+main+subject.%0A%5Cend%7Babstract%7D%0A%0AAfter+our+abstract+we+can+begin+the+first+paragraph%2C+then+press+%60%60enter%27%27+twice+to+start+the+second+one.%0A%0AThis+line+will+start+a+second+paragraph.%0A%0AI+will+start+the+third+paragraph+and+then+add+%5C%5C+a+manual+line+break+which+causes+this+text+to+start+on+a+new+line+but+remains+part+of+the+same+paragraph.+Alternatively%2C+I+can+use+the+%5Cverb%7C%5Cnewline%7C%5Cnewline+command+to+start+a+new+line%2C+which+is+also+part+of+the+same+paragraph.%0A%5Cend%7Bdocument%7D)。

注意 LaTeX 是如何自动缩进段落的——除非紧跟在如节、小节这样的文档标题之后——[我们稍后会看到](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes#Chapters_and_sections)。

建议新用户**不要**使用多个 `\\` 或 `\newline` 来“模拟”段落之间有较大间距的效果，因为这可能会干扰 LaTeX 的排版算法。推荐的方法是继续使用空行来创建新段落，不加任何 `\\`，并通过在序言中添加 `\usepackage{parskip}` 来加载 `parskip` 包。

更多关于段落的信息可以在以下文章中找到：

- [段落和换行](https://www.overleaf.com/learn/latex/Paragraphs_and_new_lines)
    
- [如何在 LaTeX 中更改段落间距](https://www.google.com/search?q=https://www.overleaf.com/learn/latex/Paragraphs%23How_to_change_paragraph_spacing_in_LaTeX)
    
- [LaTeX 错误：There's no line here to end](https://www.google.com/search?q=https://www.overleaf.com/learn/latex/Errors/There%27s_no_line_here_to_end) 提供了关于使用 `\\` 的额外建议和指导。
    

### 章和节

较长的文档，无论使用何种创作软件，通常都会被划分为部、章、节、小节等。LaTeX 也提供了文档结构化命令，但可用的命令及其实现（它们做什么）可能取决于所使用的文档类。举个例子，使用 `book` 类创建的文档可以被分割成部、章、节、小节等，但 `letter` (信件) 类则不提供（不支持）任何这样做的命令。

下一个例子演示了用于构建基于 `book` 类的文档的命令：

Code snippet

```
\documentclass{book}
\begin{document}

\chapter{First Chapter}
\section{Introduction}

This is the first section.

Lorem  ipsum  dolor  sit  amet,  consectetuer  adipiscing  
elit. Etiam  lobortisfacilisis sem.  Nullam nec mi et 
neque pharetra sollicitudin.  Praesent imperdietmi nec ante. 
Donec ullamcorper, felis non sodales...

\section{Second Section}

Lorem ipsum dolor sit amet, consectetuer adipiscing elit.  
Etiam lobortis facilisissem.  Nullam nec mi et neque pharetra 
sollicitudin.  Praesent imperdiet mi necante...

\subsection{First Subsection}
Praesent imperdietmi nec ante. Donec ullamcorper, felis non sodales...

\section*{Unnumbered Section}
Lorem ipsum dolor sit amet, consectetuer adipiscing elit.  
Etiam lobortis facilisissem...

\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Book+class+example+document&snip=%5Cdocumentclass%7Bbook%7D%0A%5Cbegin%7Bdocument%7D%0A%0A%5Cchapter%7BFirst+Chapter%7D%0A%0A%5Csection%7BIntroduction%7D%0A%0AThis+is+the+first+section.%0A%0ALorem++ipsum++dolor++sit++amet%2C++consectetuer++adipiscing++%0Aelit.+Etiam++lobortisfacilisis+sem.++Nullam+nec+mi+et+%0Aneque+pharetra+sollicitudin.++Praesent+imperdietmi+nec+ante.+%0ADonec+ullamcorper%2C+felis+non+sodales...%0A%0A%5Csection%7BSecond+Section%7D%0A%0ALorem+ipsum+dolor+sit+amet%2C+consectetuer+adipiscing+elit.++%0AEtiam+lobortis+facilisissem.++Nullam+nec+mi+et+neque+pharetra+%0Asollicitudin.++Praesent+imperdiet+mi+necante...%0A%0A%5Csubsection%7BFirst+Subsection%7D%0APraesent+imperdietmi+nec+ante.+Donec+ullamcorper%2C+felis+non+sodales...%0A%0A%5Csection%2A%7BUnnumbered+Section%7D%0ALorem+ipsum+dolor+sit+amet%2C+consectetuer+adipiscing+elit.++%0AEtiam+lobortis+facilisissem...%0A%5Cend%7Bdocument%7D)。


分节命令的名称大多是不言自明的；例如，`\chapter{First Chapter}` 创建一个名为 `First Chapter` 的新章，`\section{Introduction}` 产生一个名为 `Introduction` 的节，依此类推。节可以进一步划分为 `\subsection{...}` 甚至 `\subsubsection{...}`。节、小节等的编号是自动的，但可以通过使用相应命令的所谓**星号版本**来禁用，即在命令末尾加一个星号 (\*)，例如 `\section*{...}` 和 `\subsection*{...}`。

总的来说，LaTeX 文档类提供了以下分节命令，具体的类各自支持其中的一个相关子集：

- `\part{部}`
    
- `\chapter{章}`
    
- `\section{节}`
    
- `\subsection{小节}`
    
- `\subsubsection{小小节}`
    
- `\paragraph{段}`
    
- `\subparagraph{子段}`
    

特别地，`\part` 和 `\chapter` 命令仅在 `report` (报告) 和 `book` (书籍) 文档类中可用。

请访问 Overleaf 关于**章节的文章**以获取有关文档结构命令的更多信息。

> [!TIP]- 注释
> ### **对 “在 LaTeX 中创建列表” 的解释**
> 
> 嗨，同学！我们来学习怎么在 LaTeX 里做清单。这就要用到一个叫“**环境 (environment)**”的概念。
> 
> 你可以把“环境”想象成一个**拥有特殊规则的“魔法区域”**。当你用 `\begin{环境名称}` 进入这个区域后，里面的一些代码行为会变得不一样。当你用 `\end{environment}` 出来后，一切又恢复正常。
> 
> 对于列表，我们有两个主要的“魔法区域”：
> 
> 1. `itemize` 环境 (无序列表)
>     
>     - **规则**：在这个区域里，你每用一次 `\item` 命令，机器人就会在前面放一个**黑点** (●)。
>         
>     - **用途**：用于列出不分先后顺序的事项，比如购物清单、要点总结。
>         
> 2. `enumerate` 环境 (有序列表)
>     
>     - **规则**：在这个区域里，你每用一次 `\item` 命令，机器人不仅会另起一行，还会在前面自动帮你**编号** (1, 2, 3...)。
>         
>     - **用途**：用于列出有步骤、有顺序的事项，比如操作步骤、排名。
>         
> 
> `\item` 命令本身很简单，就相当于你在对机器人说：“**这是清单里的下一项！**”
> 
> ---
> 
> ### **对 “在 LaTeX 中添加数学公式” 的解释**
> 
> 这绝对是 LaTeX 的**超级能力** 🦸！如果你觉得在 Word 或记事本里打数学公式很痛苦，那 LaTeX 就是你的救星。
> 
> LaTeX 有两种处理公式的模式：
> 
> - **行内模式 (Inline Mode)**
>     
>     - **是什么**：把简短的公式像普通文字一样，**嵌在句子中间**。比如，“爱因斯坦提出了著名的质能方程 E=mc2。”
>         
>     - **怎么用**：最简单的方法就是用一对美元符号 `$...$` 把公式包起来。
>         
> - **陈列模式 (Display Mode)**
>     
>     - **是什么**：把重要或者复杂的公式单独拿出来，**放在正中间，自己占一行**，非常醒目。
>         
>     - **怎么用**：最简单的方法是用 `\[...\]` 把公式包起来。
>         
>     - **带编号和不带编号**：`\[...\]` 是不带编号的。如果你想让机器人自动给公式编号（如 (1), (2), (3)...），以便在文章中引用，就用 `\begin{equation}...\end{equation}` 环境。
>         
> 
> **写公式的基本语法：**
> 
> - **上标 (Superscript)**：用 `^` 符号。比如 `x^2` 就会得到 x2。
>     
> - **下标 (Subscript)**：用 `_` 符号。比如 `H_2O` 就会得到 H_2O。
>     
> - **分数 (Fraction)**：用 `\frac{分子}{分母}`。比如 `\frac{1}{2}` 就会得到 frac12。
>     
> - **特殊符号**：像积分 `\int`、希腊字母 `\alpha`, `\beta`, `\Sigma` 等，都有对应的命令。
>     
> 
> ---
> 
> ### **对 “基本文档结构” 的解释**
> 
> 当你的文章变长时，就需要好的结构来保持清晰。
> 
> #### **摘要 (Abstract)**
> 
> - `abstract` 环境是专门为学术文章设计的“魔法区域”。你把文章的**内容摘要**放进去，LaTeX 就会自动以标准格式把它放在文章的最前面。
>     
> 
> #### **段落和换行**
> 
> 这是个新手很容易搞混的地方，但非常重要！
> 
> - **新段落（空一行）**：在你的代码里，**按两次回车键（即留出一个空行）**，是在告诉 LaTeX：“我这一段的思路讲完了，请开始一个**全新的段落**。” LaTeX 会自动帮你处理好段落之间的间距和首行缩进。这是最常用、最正确的换段方式。
>     
> - **强制换行 (`\\` 或 `\newline`)**：这个命令的意思是：“我还是在**同一个段落**里，思路还没断，但我需要**立即、马上换到下一行**。” 这就像写诗或者地址时，需要在特定地方断开，但它们仍属于一个整体。
>     
>     > **⚠️重要提醒**：绝对不要用一堆 `\\` 来增加段落之间的垂直空白！这会破坏 LaTeX 的排版美感。想调整段间距，有更专业的包（比如 `parskip`）可以用。
>     
> 
> #### **章和节 (Chapters and Sections)**
> 
> 这些命令是帮你组织长文档的“**大纲工具**”。
> 
> - **层级关系**：`\chapter` (章) > `\section` (节) > `\subsection` (小节) > `\subsubsection` (小小节)。这就跟你写作文的大纲一样，一级管一级。
>     
> - **自动编号**：最爽的是，你只管用这些命令划分内容，LaTeX 会自动帮你搞定所有编号！比如 “第1章”、“1.1节”、“1.2节”、“1.2.1小节”... 如果你在中间加了一节，后面的所有编号都会自动更新。它还会根据这些命令帮你生成**目录**！
>     
> - **星号版本**：如果你不想要某个标题带编号，比如“前言”、“致谢”，就在命令后面加个星号 `*`，例如 `\section*{前言}`。机器人就会把它显示出来，但不会给它编号，也不会放进目录里。
>     
> - **可用性**：不是所有文档类型都支持所有层级。比如你写 `article` (文章) 就没有 `\chapter` (章)，这是合理的，因为一篇文章通常没有“章”那么大的结构。而 `book` (书) 和 `report` (报告) 就有。

---

## 创建表格

Overleaf 提供了三种创建表格的选项：

1. 使用**可视化编辑器**（或**代码编辑器**）工具栏中的[**插入表格**按钮](https://www.overleaf.com/learn/how-to/How_to_insert_tables_in_Overleaf%23inserttable#Using_Insert_Table_to_create_a_table_in_your_project)。
    
2. 在使用**可视化编辑器**时，从其他文档[**复制和粘贴表格**](https://www.overleaf.com/learn/how-to/How_to_paste_formatted_content_into_Overleaf%23pastingtables)。
    
3. 在**代码编辑器**中为表格编写 LaTeX 代码。


如果你是 LaTeX 新手，使用**可视化编辑器**中的工具栏（选项1）是入门的好方法——你可以在**可视化编辑器**和**代码编辑器**之间切换，以查看表格背后的代码。

在这里，我们专注于选项3——创建表格最灵活的方法——并提供示例来演示如何在 LaTeX 中创建表格，包括添加线条（边框）和图注。随着你经验的积累，可以查阅我们关于**如何使用 LaTeX 创建表格**的详细指南。

### 在 LaTeX 中创建基本表格

我们从一个展示如何排版一个基本表格的例子开始：

```latex
\begin{center}
  \begin{tabular}{c c c}
    cell1 & cell2 & cell3 \\ 
    cell4 & cell5 & cell6 \\  
    cell7 & cell8 & cell9
  \end{tabular}
\end{center}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=An+example+of+a+basic+table&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cbegin%7Bcenter%7D%0A%5Cbegin%7Btabular%7D%7Bc+c+c%7D%0A+cell1+%26+cell2+%26+cell3+%5C%5C+%0A+cell4+%26+cell5+%26+cell6+%5C%5C++%0A+cell7+%26+cell8+%26+cell9++++%0A%5Cend%7Btabular%7D%0A%5Cend%7Bcenter%7D%0A%5Cend%7Bdocument%7D%0A%3C%2Fsource%3E)。

`tabular` 环境是 LaTeX 创建表格的默认方法。你必须为这个环境指定一个参数，本例中是 `{c c c}`，它告知 LaTeX 将有三列，并且每一列内的文本都必须居中。你也可以使用 `r` 来使文本右对齐，`l` 来使其左对齐。对齐符号 `&` 用于分隔表格行内的单个单元格。要结束一个表格行，请使用换行命令 `\\`。我们的表格被包含在 `center` 环境中，使其在页面的文本宽度内居中。

### 添加边框

`tabular` 环境支持在表格中加入水平和垂直的线条（边框）：

- 要添加水平线，在行的上方和下方，使用 `\hline` 命令。
    
- 要添加垂直线，在列与列之间，使用垂直线参数 `|`。
    

在这个例子中，参数是 `{|c|c|c|}`，它声明了三个（居中的）列，每列之间由一条垂直线分隔；此外，我们使用 `\hline` 在第一行的上方和最后一行的下方放置一条水平线：

```latex
\begin{center}
  \begin{tabular}{|c|c|c|} 
    \hline
    cell1 & cell2 & cell3 \\ 
    cell4 & cell5 & cell6 \\ 
    cell7 & cell8 & cell9 \\ 
    \hline
  \end{tabular}
\end{center}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Table+example+with+rules&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cbegin%7Bcenter%7D%0A%5Cbegin%7Btabular%7D%7B%7Cc%7Cc%7Cc%7C%7D+%0A+%5Chline%0A+cell1+%26+cell2+%26+cell3+%5C%5C+%0A+cell4+%26+cell5+%26+cell6+%5C%5C+%0A+cell7+%26+cell8+%26+cell9+%5C%5C+%0A+%5Chline%0A%5Cend%7Btabular%7D%0A%5Cend%7Bcenter%7D%0A%5Cend%7Bdocument%7D)。

这里是另一个例子：
```latex
\begin{center}
  \begin{tabular}{||c c c c||} 
    \hline
    Col1 & Col2 & Col2 & Col3 \\ [0.5ex] 
    \hline\hline
    1 & 6 & 87837 & 787 \\ 
    \hline
    2 & 7 & 78 & 5415 \\
    \hline
    3 & 545 & 778 & 7507 \\
    \hline
    4 & 545 & 18744 & 7560 \\
    \hline
    5 & 88 & 788 & 6344 \\ [1ex] 
    \hline
  \end{tabular}
\end{center}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Another+table+example+containing+rules&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0A%5Cbegin%7Bcenter%7D%0A+%5Cbegin%7Btabular%7D%7B%7C%7Cc+c+c+c%7C%7C%7D+%0A+%5Chline%0A+Col1+%26+Col2+%26+Col2+%26+Col3+%5C%5C+%5B0.5ex%5D+%0A+%5Chline%5Chline%0A+1+%26+6+%26+87837+%26+787+%5C%5C+%0A+%5Chline%0A+2+%26+7+%26+78+%26+5415+%5C%5C%0A+%5Chline%0A+3+%26+545+%26+778+%26+7507+%5C%5C%0A+%5Chline%0A+4+%26+545+%26+18744+%26+7560+%5C%5C%0A+%5Chline%0A+5+%26+88+%26+788+%26+6344+%5C%5C+%5B1ex%5D+%0A+%5Chline%0A%5Cend%7Btabular%7D%0A%5Cend%7Bcenter%7D%0A%5Cend%7Bdocument%7D)。

### 表注、标签和引用

你可以像处理图片一样为表格添加表注和引用。唯一的区别是，你使用的是 `table` 环境，而不是 `figure` 环境。

Code snippet

```
Table \ref{table:data} shows how to add a table caption and reference a table.

\begin{table}[h!]
  \centering
  \begin{tabular}{||c c c c||} 
    \hline
    Col1 & Col2 & Col2 & Col3 \\ [0.5ex] 
    \hline\hline
    1 & 6 & 87837 & 787 \\ 
    2 & 7 & 78 & 5415 \\
    3 & 545 & 778 & 7507 \\
    4 & 545 & 18744 & 7560 \\
    5 & 88 & 788 & 6344 \\ [1ex] 
    \hline
  \end{tabular}
  \caption{Table to test captions and labels.}
  \label{table:data}
\end{table}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Table+captions+and+references&snip=%5Cdocumentclass%7Barticle%7D%0A%5Cbegin%7Bdocument%7D%0ATable+%5Cref%7Btable%3Adata%7D+shows+how+to+add+a+table+caption+and+reference+a+table.%0A%5Cbegin%7Btable%7D%5Bh%21%5D%0A%5Ccentering%0A%5Cbegin%7Btabular%7D%7B%7C%7Cc+c+c+c%7C%7C%7D+%0A+%5Chline%0A+Col1+%26+Col2+%26+Col2+%26+Col3+%5C%5C+%5B0.5ex%5D+%0A+%5Chline%5Chline%0A+1+%26+6+%26+87837+%26+787+%5C%5C+%0A+2+%26+7+%26+78+%26+5415+%5C%5C%0A+3+%26+545+%26+778+%26+7507+%5C%5C%0A+4+%26+545+%26+18744+%26+7560+%5C%5C%0A+5+%26+88+%26+788+%26+6344+%5C%5C+%5B1ex%5D+%0A+%5Chline%0A%5Cend%7Btabular%7D%0A%5Ccaption%7BTable+to+test+captions+and+labels.%7D%0A%5Clabel%7Btable%3Adata%7D%0A%5Cend%7Btable%7D%0A%5Cend%7Bdocument%7D)。

## 添加目录

创建目录非常直接，因为 `\tableofcontents` 命令几乎为你完成了所有工作：

```latex
\documentclass{article}
\title{Sections and Chapters}
\author{Gubert Farnsworth}
\date{August 2022}
\begin{document}
  \maketitle
  
  \tableofcontents
  
  \section{Introduction}
   
This is the first section.
      
Lorem  ipsum  dolor  sit  amet,  consectetuer  adipiscing  
elit.   Etiam  lobortisfacilisis sem.  Nullam nec mi et 
neque pharetra sollicitudin.  Praesent imperdietmi nec ante. 
Donec ullamcorper, felis non sodales...
       
  \section*{Unnumbered Section}
  \addcontentsline{toc}{section}{Unnumbered Section}

Lorem ipsum dolor sit amet, consectetuer adipiscing elit.  
Etiam lobortis facilisissem.  Nullam nec mi et neque pharetra 
sollicitudin.  Praesent imperdiet mi necante...
  
  \section{Second Section}
       
Lorem ipsum dolor sit amet, consectetuer adipiscing elit.  
Etiam lobortis facilisissem.  Nullam nec mi et neque pharetra 
sollicitudin.  Praesent imperdiet mi necante...
\end{document}
```

[在 Overleaf 中打开此示例](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Generating+a+table+of+contents&snip=%5Cdocumentclass%7Barticle%7D%0A%5Ctitle%7BSections+and+Chapters%7D%0A%5Cauthor%7BGubert+Farnsworth%7D%0A%5Cdate%7BAugust+2022%7D%0A%5Cbegin%7Bdocument%7D%0A++%0A%5Cmaketitle%0A++%0A%5Ctableofcontents%0A%0A%5Csection%7BIntroduction%7D%0A+++%0AThis+is+the+first+section.%0A++++++%0ALorem++ipsum++dolor++sit++amet%2C++consectetuer++adipiscing++%0Aelit.+++Etiam++lobortisfacilisis+sem.++Nullam+nec+mi+et+%0Aneque+pharetra+sollicitudin.++Praesent+imperdietmi+nec+ante.+%0ADonec+ullamcorper%2C+felis+non+sodales...%0A+++++++%0A%5Csection%2A%7BUnnumbered+Section%7D%0A%5Caddcontentsline%7Btoc%7D%7Bsection%7D%7BUnnumbered+Section%7D%0A%0ALorem+ipsum+dolor+sit+amet%2C+consectetuer+adipiscing+elit.++%0AEtiam+lobortis+facilisissem.++Nullam+nec+mi+et+neque+pharetra+%0Asollicitudin.++Praesent+imperdiet+mi+necante...%0A%0A%5Csection%7BSecond+Section%7D%0A+++++++%0ALorem+ipsum+dolor+sit+amet%2C+consectetuer+adipiscing+elit.++%0AEtiam+lobortis+facilisissem.++Nullam+nec+mi+et+neque+pharetra+%0Asollicitudin.++Praesent+imperdiet+mi+necante...%0A%5Cend%7Bdocument%7D)。

节、小节和章会自动包含在目录中。要手动添加条目，比如一个未编号的节，请使用 `\addcontentsline` 命令，如示例所示。

## 下载你完成的文档

下面的简短视频片段展示了如何下载你的项目源代码或排版好的 PDF 文件： [视频：如何从 Overleaf 导出你的作品](https://videos.ctfassets.net/nrgyaltdicpt/2n6iw0AUELNtABCuva0oV5/cf27bff3a6099da94362d64645e69dfe/LL30download.mp4)
<iframe width="800" height="640"
  src="https://videos.ctfassets.net/nrgyaltdicpt/2n6iw0AUELNtABCuva0oV5/cf27bff3a6099da94362d64645e69dfe/LL30download.mp4"
  frameborder="0"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>

更多信息可以在 Overleaf 的帮助文章[**从 Overleaf 导出你的作品**](https://www.overleaf.com/learn/how-to/Exporting_your_work_from_Overleaf)中找到。

## 查找和使用 LaTeX 包

LaTeX 不仅提供了强大的排版能力，还通过使用附加**包 (packages)** 提供了一个**可扩展的框架**。LaTeX 的设计不是试图提供“能做所有事情”的命令和功能，而是**可扩展的**，允许用户加载外部代码体（包），这些包提供更专业的排版能力或扩展 LaTeX 的内置功能——例如排版表格。正如在**添加图片**一节中看到的，`graphicx` 包通过提供导入图形文件的命令来扩展 LaTeX，并通过在序言中写入以下代码来加载： `\usepackage{graphicx}`

### 加载包

如上所述，包是通过 `\usepackage` 命令在文档序言中加载的。但是因为（许多）LaTeX 包提供了一系列**选项**，可用于配置它们的行为，所以 `\usepackage` 命令通常看起来像这样： `\usepackage[选项]{某个包}`

方括号 `[...]` 告知 LaTeX 在加载 `某个包` 时应应用哪一套选项。在用户请求的一组选项中，单个选项或设置通常用逗号分隔；例如，`geometry` 包提供了许多选项来配置 LaTeX 中的页面布局，因此 `geometry` 的一个典型用法可能如下所示： `\usepackage[total={6.5in,8.75in}, top=1.2in, left=0.9in, includefoot]{geometry}`

`geometry` 包是由全球 LaTeX 社区成员编写和贡献的一个例子，免费提供给任何想使用它的人。

如果一个 LaTeX 包不提供任何选项，或者用户想使用一个包的选项的默认值，它会像这样加载： `\usepackage{某个包}`

当你写入 `\usepackage[...]{某个包}` 时，LaTeX 会寻找一个名为 `某个包.sty` 的对应文件，它需要加载并处理该文件——以使包的命令可用并执行该包提供的任何其他代码。如果 LaTeX 找不到 `某个包.sty`，它将以错误终止，如下面的 Overleaf 示例所示：

Code snippet

```
\documentclass[12pt, letterpaper]{article}
\usepackage{somepackage} % 一个不存在的包
\begin{document}
This will fail!
\end{document}
```

[在 Overleaf 中打开这个**产生错误的示例**](https://www.overleaf.com/docs?engine=pdflatex&snip_name=Error+due+to+missing+package&snip=%5Cdocumentclass%5B12pt%2C+letterpaper%5D%7Barticle%7D%0A%5Cusepackage%7Bsomepackage%7D%25+a+NON-EXISTENT+package%0A%5Cbegin%7Bdocument%7D%0AThis+will+fail%21%0A%5Cend%7Bdocument%7D)。

### 查找有关包的信息：CTAN

包通过**综合 TeX 存档网络 (Comprehensive TeX Archive Network)** 分发，通常称为 **CTAN**，在撰写本文时，该网络托管了来自 2881 位贡献者的 6287 个包。CTAN **自我描述**为：

> ... 一组遍布全球的互联网站点，提供与 TeX 相关的材料供下载。

你可以浏览 CTAN 来寻找有用的包；例如：

- **按主题**
    
- **按字母顺序**（如果你知道包名的话很有用）
    

你也可以使用（页面顶部的）**搜索功能**。

### Overleaf 上可用的包：介绍 TeX Live

每年一次，一个托管在 CTAN 上的包的（大型）**子集**，加上与 LaTeX 相关的字体和其他软件，会被整理并分发为一个名为 **TeX Live** 的系统，它可以用来安装你自己的（本地）LaTeX 环境。事实上，**Overleaf 的服务器也使用 TeX Live**，并在 TeX Live 新版本发布时进行更新。Overleaf 的 TeX Live 更新不是即时的，而是在发布后几个月进行，这给我们时间来对新版 TeX Live 与我们**画廊中数以千计的模板**进行兼容性测试。例如，这是我们的 **TeX Live 2022 升级公告**。

虽然 TeX Live 包含 CTAN 包的一个（大型）**子集**，但你可能会发现一个有趣的包，比如用于排版围棋图的 `igo`，它托管在 CTAN 上，但没有包含在（由）TeX Live（分发）中，因此在 Overleaf 上不可用。一些托管在 CTAN 上的包由于各种原因没有成为 TeX Live 的一部分：也许一个包已经过时，有许可问题，非常新（最近上传），或者有平台依赖性，比如在 Windows 上工作但在 Linux 上不行。

新包和现有包的更新全年都会上传到 CTAN，但 TeX Live 的更新是每年分发的；因此，当前版本 TeX Live 中包含的包不会像 CTAN 上托管的那样最新。因为 Overleaf 的服务器使用 TeX Live，我们服务器上安装的包——即我们的用户可用的包——可能不是 CTAN 上可用的最新版本，但通常来说，这不太可能成为问题。

> [!TIP]- 注释
> ### **对 “创建表格” 的解释**
> 
> 制作表格是写报告和论文的必备技能。LaTeX 提供了非常强大的表格制作功能。
> 
> #### **`tabular` 环境：表格的“画板”**
> 
> `tabular` 是用来画表格的“魔法区域”或“画板”。
> 
> - `\begin{tabular}{l c r}`：这是在告诉机器人：“我要开始画一个表格了，它有**三列**。第一列(`l`)的文字**左对齐**，第二列(`c`)**居中**，第三列(`r`)**右对齐**。”
>     
> 
> #### **填充表格内容**
> 
> 在画板里，你需要用两个符号来告诉机器人内容该放哪：
> 
> - `&` (单元格分隔符)：这个符号就像你在 Excel 里按 **Tab 键**，意思是“好了，这个单元格的内容说完了，请移动到**右边下一个单元格**。”
>     
> - `\\` (行分隔符)：这个双反斜杠就像你在 Excel 里按 **Enter 键**，意思是“这一行的所有单元格都填完了，请移动到**下一行开头**。”
>     
> 
> #### **画出边框线**
> 
> - `\hline` (Horizontal Line)：这个命令像一把尺子，它告诉机器人：“在这里画一条**横跨整个表格宽度的水平线**。”
>     
> - `|` (Vertical Line)：这个竖线符号是在定义列格式的时候加的。`{|c|c|c|}` 的意思是：“画条**竖线**，然后来个居中列，再画条**竖线**，再来个居中列，再画条**竖线**...”
>     
> 
> #### **`table` 环境：给表格一个“专属展位”**
> 
> 还记得图片的 `figure` 环境吗？`table` 环境的作用一模一样，但它是为表格准备的。
> 
> - 它把你的 `tabular` 表格放进一个“**浮动展位**”里。
>     
> - LaTeX 会自动寻找最佳位置安放这个展位，让页面整体看起来更美观。
>     
> - 最重要的是，只有在 `table` 环境里，你才能用 `\caption{}` 给表格加**标题**（表注），用 `\label{}` 给它贴上**秘密标签**，以便后续用 `\ref{}` 来**引用**它。
>     
> 
> ---
> 
> ### **对 “添加目录” 的解释**
> 
> 这是 LaTeX 最令人愉悦的功能之一，简直是“**一键生成，懒人福音**”！
> 
> `\tableofcontents`
> 
> - 你只需要在你想要显示目录的地方（通常在标题页之后）写下这个命令。
>     
> - 机器人（LaTeX）就会自动扫描你的整篇文档，找到所有用 `\chapter`, `\section`, `\subsection` 等命令创建的标题，把它们的**标题名称**和**页码**抓取出来，然后生成一个格式专业、页码绝对正确的目录。
>     
> - 你再也不用在交稿前一个一个手动检查目录和页码了！
>     
> 
> `\addcontentsline{toc}{section}{Unnumbered Section}`
> 
> - 这个命令是用来“**手动添加条目**”的。比如你用 `\section*{前言}` 创建了一个不带编号的“前言”，它默认不会出现在目录里。用这个命令就可以告诉机器人：“喂，把这个叫‘前言’的无编号章节，也按‘节’的格式加到目录里去！”
>     
> 
> ---
> 
> ### **对 “查找和使用 LaTeX 包” 的解释**
> 
> 我们最后来深入理解一下 LaTeX 的核心——**包 (package)**。我喜欢用**智能手机和 App** 来打比方 📱。
> 
> - **LaTeX 本身**：就像一部**刚出厂的手机**。它有打电话、发短信的基础功能（能排版基本文字），但功能有限。
>     
> - **包 (Packages)**：就是你手机上安装的各种 **App**。每个 App 都能给你的手机增加一项新功能。
>     
>     - `\usepackage{graphicx}` 就是安装了“**相册 App**”，让你的 LaTeX 能够处理图片。
>         
>     - `\usepackage{amsmath}` 就是安装了“**科学计算器 App**”，让你的 LaTeX 能处理各种复杂的数学公式。
>         
>     - `\usepackage{geometry}` 就是安装了“**页面布局设置 App**”。
>         
> - **包的选项 `[...]`**：就是 **App 内部的设置**。`\usepackage[top=1in]{geometry}` 就好比你打开“页面布局设置”这个 App，然后把“上边距”这个选项设置为 `1in`。
>     
> 
> #### **那么，这些“App”从哪里来呢？**
> 
> - **CTAN (The App Store)**：CTAN 是 LaTeX 的官方“**应用商店**”。全世界的开发者写的成千上万个包（App）都放在这里，它是所有包的最终来源地。
>     
> - **TeX Live (The Phone's Operating System)**：TeX Live 就像是手机的**操作系统**（比如 iOS 或安卓）。每年，TeX Live 的开发者会从 CTAN 这个巨大的应用商店里，精心挑选出数千个最常用、最稳定、最好用的包，打包成一个大的发行版。
>     
> 
> **Overleaf 和 TeX Live 的关系**：Overleaf 的服务器运行的就是这个 TeX Live 系统。所以，基本上所有 TeX Live 里的包，你在 Overleaf 上都能直接用。这也意味着，如果某个非常新或者非常小众的包只存在于 CTAN 上，还没被收录到最新的 TeX Live 里，那么在 Overleaf 上可能就暂时用不了。不过别担心，TeX Live 已经包含了你学习和工作中所需要的绝大部分包了！