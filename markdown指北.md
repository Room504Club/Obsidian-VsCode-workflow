
# 基本语法

`# 一级标题`
# 一级标题

`# 二级标题`
## 二级标题


# $\LaTeX$ 公式
 $\LaTeX$ 公式在markdown中用 `$` 标记，公式分为行内公式（可以和其他文本一起写在一行内）和行间公式（又叫块状公式，写在行与行之间）。
## 行内公式与行间公式
### 行内公式示例
> 其中 $\alpha$ 代表导热系数，$\frac{\partial u}{\partial t}$ 代表变量随时间变化的情况

### 行间公式示例
> 所以求和公式如下：
> $$
 N=\sum_{i=1}^N f(\lambda_i)
 $$

具体的数学符号和数学公式写法可以在知乎查询 LaTeX

# ✨ Obsidian Callout 功能详解与示例

> [!INFO] Callout 基础语法
> Callout 的基础语法非常简单，就是在标准的 Markdown 引用符号 `>` 后面加上 `[!KEYWORD]` 即可。
> ```markdown
> > [!KEYWORD] 这里是标题（标题可选）
> > 这里是 Callout 的正文内容。
> > 可以有多行。
> ```
>`[!KEYWORD]` 后加上 `-` 可以折叠文本。
> ```markdown
> > [!KEYWORD]- 这里是标题（标题可选）
> > 这里是 Callout 的正文内容。
> > 可以有多行。
> ```


---

### Obsidian 内置 Callout 类型一览

以下是 Obsidian 官方支持的所有 Callout 关键词。您提供的文档中也使用了其中的几种。

> [!NOTE] Note
> [cite_start]`note` 是最常用的类型，用于普通的注释和笔记 [cite: 2]。
> ```markdown
> > [!NOTE]
> > 这是一条普通的笔记。
> ```

> [!INFO] Info
> [cite_start]`info` 是 `note` 的一个别名，外观完全一样，用于提示信息 [cite: 2]。
> ```markdown
> > [!INFO]
> > 这是一条提示信息。
> ```

> [!TODO] Todo
> 用于标记待办事项。
> ```markdown
> > [!TODO]
> > - [x] 安装所有必备软件
> > - [ ] 学习 Git 命令
> ```

> [!TIP] Tip / Hint / Important
> [cite_start]用于提供技巧、暗示或重要提示 [cite: 2][cite_start]。`tip`, `hint`, `important` 是别名，外观一致 [cite: 2]。
> ```markdown
> > [!TIP]
> > 每天工作前先 `git pull` 是一个好习惯。
> ```

> [!SUCCESS] Success / Check / Done
> 用于表示成功、完成或检查通过的事项。
> ```markdown
> > [!SUCCESS]
> > 恭喜！您已成功配置好所有环境。
> ```

> [!QUESTION] Question / Help / FAQ
> 用于提出问题、寻求帮助或整理常见问题解答。
> ```markdown
> > [!QUESTION]
> > 如果 Git 出现冲突该怎么办？
> ```

> [!WARNING] Warning / Caution / Attention
> [cite_start]用于需要注意的警告信息 [cite: 2]。`warning`, `caution`, `attention` 是别名，外观一致。
> ```markdown
> > [!WARNING]
> > 在 `settings.json` 中修改配置时请务必小心。
> ```

> [!FAILURE] Failure / Fail / Missing
> 用于表示失败、缺失或错误的结果。
> ```markdown
> > [!FAILURE]
> > 宏包 `tikz-ext` 未找到，请在 MiKTeX Console 中安装。
> ```

> [!DANGER] Danger / Error
> 用于表示危险操作或严重错误。
> ```markdown
> > [!DANGER]
> > `git reset --hard` 命令会永久删除未提交的修改，请谨慎使用！
> ```

> [!BUG] Bug
> 用于报告和记录 Bug。
> ```markdown
> > [!BUG]
> > 在 1.8.10 版本下，插件 A 与插件 B 不兼容。
> ```

> [!EXAMPLE] Example
> 用于提供示例代码或用例。
> ```markdown
> > [!EXAMPLE]
> > `git commit -m "这是一个提交示例"`
> ```

> [!QUOTE] Quote / Cite
> 用于引用名言或文献。
> ```markdown
> > [!QUOTE]
> > “让每个软件做自己最擅长的事。”
> ```

---

### ✨ Callout 的高级用法

> [!TIP] 1. 自定义标题
> 您可以在关键词后面直接跟上您想要的标题。
> ```markdown
> > [!SUCCESS] 操作成功！
> > 您的文件已成功推送到 GitHub。
> ```

> [!TIP] 2. 可折叠的 Callout
> [cite_start]在关键词后面加上 `+` 或 `-` 可以让 Callout 默认展开或折叠 [cite: 2]。
> 
> **默认折叠 (常用于隐藏长篇的详细步骤或代码)**
> ```markdown
> > [!NOTE]- 点击这里展开详细信息
> > 这里是默认被隐藏起来的详细内容。
> ```
> 
> **默认展开 (与不加符号效果一样，但明确表示可折叠)**
> ```markdown
> > [!NOTE]+ 这是一个默认展开的 Callout
> > 内容默认可见，但标题旁有一个小箭头可以点击收起。
> ```

