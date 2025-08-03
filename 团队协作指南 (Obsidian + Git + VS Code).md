# 🚀 一份献给科研新手的团队协作指南 (Obsidian + Git + VS Code)

> [!INFO] 开篇：我们的目标是什么？
> 欢迎来到现代科研的世界！忘掉用U盘传来传去、在微信群里发不同版本`v1, v2, final, final_final`的 Word 文档吧。我们将搭建一套专业、高效且完全免费的系统，来解决团队协作中的三大难题：
> 1.  **版本混乱**：谁都不知道哪个文件是最终版。
> 2.  **修改丢失**：A同学的修改覆盖了B同学的成果。
> 3.  **工作冲突**：无法同时对一个文件进行不同部分的修改。
> 
> 这套系统将成为你们团队的“中央大脑”，清晰地记录每一次修改，让协作变得轻松而有序。

---

## Part 1：准备你的“数字实验室”：安装必备软件

在开始之前，我们需要在电脑上安装一些“神器”。别担心，这个过程就像安装QQ或微信一样简单。

> [!TIP] 我们的工具箱与比喻
> - **Obsidian**: 你的 **“数字笔记本”**，随手记录灵感和知识，并建立它们之间的联系。
> - **VS Code**: 你的 **“精加工车间”**，处理需要精密操作的任务，比如写代码和排版论文。
> - **Git**: 一台 **“时光机”**，可以记录你对文件的每一次修改，并随时“穿越”回任何一个历史版本。
> - **GitHub**: 一个 **“云端图书馆”**，存放你们团队所有工作成果的最终版本，所有人都可以来这里借阅（下载）和上交新书稿（上传修改）。
> - **Anaconda**: 你的 **“Python工具包”** 管理员，为不同的项目提供独立的工具箱。
> - **MiKTeX + Perl**: 专业的 **“排版印刷机”**，将你的 `.tex` 论文手稿变成精美的 PDF。

---

### ✅ 第一站：安装 Git (时光机)

这是所有协作的基础，它能追踪你文件的每一次变化。

1.  **访问官网**: [https://git-scm.com/downloads](https://git-scm.com/downloads)
2.  **下载并安装**: 下载适合你系统的版本（Windows 用户直接下载 `.exe` 文件）。
3.  **安装过程**: 像安装普通软件一样，**一路点击“Next”** 即可，不需要修改任何默认设置。
4.  **验证**: 安装完成后，在“开始菜单”搜索 `cmd` 打开“命令提示符”，输入 `git --version` 然后按回车。如果出现版本号（如 `git version 2.44.0.windows.1`），恭喜你，时光机已就位！

### ✅ 第二站：安装 Anaconda (Python 工具包管理员)

它帮你管理做数据分析和科学计算需要的所有 Python 工具。

1.  **访问官网**: [https://www.anaconda.com/products/distribution](https://www.anaconda.com/products/distribution)
2.  **下载并安装**: 下载最新版的安装包。
3.  **安装过程**:
    > [!WARNING] 安装过程中的重要选项
    > - 当被问及为“Just Me”还是“All Users”安装时，推荐选择 **“Just Me”** (为我安装)。这样安装路径在你的用户文件夹下，后续操作不需要管理员权限，能省去很多麻烦。
    > - 当看到“Add Anaconda to my PATH environment variable”（添加到环境变量）的选项时，如果它是**可选的并且不被推荐**，可以**不勾选**。我们会使用专门的 Anaconda 终端来工作。

### ✅ 第三站：安装 VS Code (精加工车间)

1.  **访问官网**: [https://code.visualstudio.com/](https://code.visualstudio.com/)
2.  **下载并安装**: 使用默认选项一路“Next”即可。
3.  **安装核心扩展 (给车间增加设备)**:
    - 打开 VS Code，点击左侧边栏的“扩展”图标（四个方块）。
    - 在搜索框中，搜索并安装以下**必装**插件：
        - `Python` (由 Microsoft 发布)
        - `Jupyter` (由 Microsoft 发布)
        - `LaTeX Workshop` (由 James Yu 发布)
        - `Chinese (Simplified) Language Pack` (微软官方中文包，可选)

### ✅ 第四站：安装 LaTeX 印刷机 (MiKTeX + Perl)

这两样是用来将 `.tex` 论文手稿变成精美 PDF 的工具。

1.  **安装 MiKTeX (印刷机本体)**
    - **访问官网**: [https://miktex.org/download](https://miktex.org/download)
    - **下载并安装**:
    > [!IMPORTANT] 关键设置
    > 在安装过程中，请**务必勾选“将 MiKTeX 添加到系统路径 (Add MiKTeX to the system PATH)”** 或类似的选项。这一步至关重要！

2.  **安装 Strawberry Perl (印刷机墨水)**
    - **访问官网**: [https://strawberryperl.com/](https://strawberryperl.com/)
    - **下载并安装**: 在下载选项中，选择 **MSI 安装包**（文件名以 `.msi` 结尾的那个）。运行它，用默认选项一路“Next”完成安装。

### ✅ 第五站：安装 Obsidian (数字笔记本)
1.  **访问官网**: [https://obsidian.md/](https://obsidian.md/)
2.  **下载并安装**: 这个过程非常简单。

---

## Part 2：搭建团队的“云端图书馆” (GitHub)

1.  **创建仓库**: 由团队负责人登录 GitHub，访问 [github.com/new](https://github.com/new) 创建一个新仓库。
    * **Repository name**: 仓库名，比如 `team-research-notes`。
    * **Description**: 简单描述，如“XX科研项目团队笔记”。
    * **Public / Private**: **务必选择 `Private` (私有)**。
    * **Initialize**: 勾选 `Add a README file`。

2.  **添加成员**: 进入刚创建好的仓库页面，点击 `Settings` -> `Collaborators` -> `Add people`，将所有团队成员的 GitHub 账号添加为协作者。

---

## Part 3：连接你的“笔记本”与“图书馆”

### 3.1 克隆仓库到本地（第一次操作）
每位团队成员都需要执行一次这个操作，把“图书馆”的书架搬到自己电脑上。

1.  打开 GitHub 仓库页面，点击绿色的 `<> Code` 按钮，复制 HTTPS 地址。
2.  在电脑上找一个你喜欢的位置，右键选择“在终端中打开”或“Git Bash Here”。
3.  在弹出的终端窗口中，输入命令并回车：
    ```bash
    git clone <你刚刚复制的仓库HTTPS地址>
    ```
    例如: `git clone https://github.com/inroom504/team-research-notes.git`

### 3.2 用 Obsidian 打开仓库
- 打开 Obsidian，选择“打开另一个库” -> “打开本地文件夹作为库”，并指向你刚刚通过 `git clone` 创建的那个文件夹。

### 3.3 在 Obsidian 中安装 Git 插件
- 在 Obsidian 的 `设置` -> `社区插件` 市场中，搜索并安装 `Obsidian Git` 插件并启用。

---

## Part 4：日常协同工作流

> [!WARNING] 团队协作黄金法则
> **每天开始工作前，第一件事永远是 `Pull` (拉取)！**
> 这会把队友最新的修改同步到你的电脑上，能避免 90% 的冲突。在 Obsidian Git 插件里，这通常是一个向下的箭头图标 `⬇️`。

### ✅ 一位团队成员的一天 (示例)

**上午 9:00 - 开始工作**
1.  小明打开 Obsidian。Obsidian Git 插件可能会自动执行 `Pull`，或者他会手动点击 `Pull` 按钮，确保自己电脑上的内容是最新版。

**上午 10:00 - 撰写 Markdown 笔记**
1.  小明在 Obsidian 中创建了新笔记 `思路整理.md`，并修改了 `文献综述.md`。
2.  他觉得完成了一个小阶段，于是打开命令面板 (`Ctrl+P`)，输入 `Git Commit`。
3.  在弹出的窗口中，他写下本次修改的说明：“新增“神经网络结构”的初步想法”，然后点击“Commit”。

**下午 2:00 - 进行 Python 实验**
1.  实验需要用到 `pinns` 库，小明打开 VS Code，并选择打开整个 Obsidian 库的文件夹。
2.  他点击 `实验数据.ipynb` 文件。
3.  他点击 VS Code 右上角的内核选择器，确保选中的是他为这个项目创建的 `pinns-env` Anaconda 虚拟环境。
4.  他在 Notebook 中运行代码，生成了新的图表和结果，并保存了文件。

**下午 4:00 - 撰写 LaTeX 报告**
1.  小明需要把实验结果写入正式报告。他在 VS Code 中打开 `周报.tex` 文件。
2.  `LaTeX Workshop` 插件被激活，他一边写代码，一边在右侧实时预览 PDF 效果。

**晚上 6:00 - 结束工作**
1.  小明回到 Obsidian，或者继续在 VS Code 的 Git 面板操作。
2.  他再次 `Commit` 所有未提交的修改（`.ipynb` 和 `.tex` 文件），写下说明：“完成 PINNs 实验并更新周报结果”。
3.  最后，他点击 `Push` 按钮（向上的箭头 `⬆️`），将今天所有的 `Commit` 一次性上传到 GitHub 云端图书馆。
4.  团队的其他成员明天早上 `Pull` 的时候，就能看到小明的所有新成果了。

##### 小结（适合打印出来给队员）

| 操作    | 你要做什么                              |
| ----- | ---------------------------------- |
| 初次配置  | 注册 GitHub + 安装 Obsidian + 插件 + Git |
| 每天写作前 | 点一下「Pull」拉取他人内容                    |
| 写完后   | 「Commit」提交 + 「Push」推送              |
| 遇到冲突  | Obsidian Git 会提示怎么解决               |
| 新人加入  | 让他 clone 仓库 + 用 Obsidian 打开即可      |

---

## Part 5：附录：常见问题与深度解析 (FAQ)

> [!QUESTION]- 什么是 `nbdime`？如何配置和排错？
> 
> **用途**：让 Git 能够“读懂” `.ipynb` 文件的修改，提供清晰的、富文本的 `diff` 效果。
> 
> **最佳实践**：将其作为开发工具，安装在 Anaconda 的 `base` 环境中，一劳永逸。
> 
> #### **安装**
> 1.  打开 **Anaconda Prompt (以管理员身份运行)**。
> > [!FAILURE] 报错 `EnvironmentNotWritableError`?
> > 这是因为您的 Anaconda 安装在了系统盘（如 `C:\ProgramData`），需要管理员权限才能修改。请右键点击 Anaconda Prompt，选择“以管理员身份运行”。
> 2.  在管理员终端中，运行以下命令：
> ```bash
> conda install -c conda-forge nbdime
> ```
> 
> #### **配置**
> 3.  安装成功后，在同一个管理员终端中，运行全局配置命令：
> ```bash
> nbdime config-git --enable --global
> ```
> 
> #### **验证与排错**
> 4. **检查命令为何物？**
> > [!TIP] `grep` vs `findstr`
> > `grep` 是 Linux/macOS 的命令，`findstr` 是 Windows 的等效命令。
> 5. **运行检查命令**：
>     - (Windows) `git config --global --list | findstr ipynb`
>     - (Mac/Linux) `git config --global --list | grep ipynb`
> 6. **预期输出**: 必须包含 `diff.ipynb.command=nbdiff` 和 `merge.ipynb.driver=nbmerge...` 两行。
> 7. **如果输出不完整怎么办？**
> > [!bug] 如果自动配置不完整，请逐一运行以下命令来手动补全：
> > ```batch
> > git config --global diff.ipynb.command "nbdiff"
> > git config --global merge.ipynb.driver "nbmerge -i %A %B %O %P"
> > git config --global core.attributesfile "%USERPROFILE%\.gitattributes"
> > echo "*.ipynb diff=ipynb merge=ipynb" >> "%USERPROFILE%\.gitattributes"
> > ```
> 8. **最终测试**: 创建一个临时 git 仓库，放入一个简单的 `.ipynb`，提交后修改，再运行 `git diff`，观察输出是否为清晰的单元格对比。

> [!QUESTION]- `LaTeX` 编译失败怎么办？(完整排错指南)
> 
> `LaTeX` 的配置链条较长（`VS Code -> LaTeX Workshop -> latexmk -> MiKTeX/Perl`），任何一环出错都会导致编译失败。以下是我们之前遇到的所有错误的完整解决方案。
> 
> #### **错误 1: `spawn latexmk ENOENT`**
> - **症状**: 点击编译后立刻报错，提示找不到 `latexmk`。
> - **原因**: 没有安装 MiKTeX，或者安装时没有将其添加到系统路径 (PATH)。
> - **解决方案**: 重新安装 MiKTeX，并确保勾选“添加到 PATH”的选项。
> 
> #### **错误 2: `MiKTeX could not find the script engine 'perl'`**
> - **症状**: 找到了 `latexmk`，但运行时提示找不到 `perl` 引擎。
> - **原因**: 系统中没有安装 Perl 语言环境。
> - **解决方案**: 安装 Strawberry Perl，务必选择 MSI 安装包，它会自动配置好一切。
> 
> #### **错误 3: 中文显示为乱码或报错**
> - **症状**: 日志提示 `xeCJK package requires XeTeX...` 或大量 `Unicode character ... not set up`。
> - **原因**: 使用了默认的 `pdflatex` 引擎，它不支持处理中文的 `xeCJK` 宏包。
> - **解决方案**: 在 VS Code 的 `settings.json` 文件中，将默认编译配方改为 `xelatex`。
>     ```json
>     "latex-workshop.latex.recipe.default": "latexmk (xelatex)"
>     ```
> 
> #### **错误 4: 提示找不到字体 (如 `FandolSong`)**
> - **症状**: 日志提示 `The font "FandolSong" cannot be found`。
> - **原因**: Overleaf 等在线平台的字体，你本地电脑上没有。
> - **解决方案**: 在 `.tex` 文件中，换用你系统自带的中文字体，如 `SimSun` (宋体), `SimHei` (黑体), `Microsoft YaHei` (微软雅黑)。
>     ```latex
>     \setCJKmainfont{SimSun}
>     ```
> 
> #### **错误 5: 提示找不到宏包/库 (如 `shapes.signals`)**
> - **症状**: 日志提示 `did not find the ... library ...`。
> - **原因**: MiKTeX 默认是最小化安装，很多宏包需要在使用时才会下载。
> - **解决方案 (一劳永逸)**:
>     1.  以**管理员身份**打开 **MiKTeX Console**。
>     2.  进入“**设置 (Settings)**”标签页，将“**自动安装缺失的宏包**”设置为“**总是询问 (Ask me first)**”。
>     3.  如果因权限问题不弹窗，请切换到“**更新 (Updates)**”标签页，**将所有可用的包全部更新**。
>     4.  重启 VS Code 后再次编译，MiKTeX 应该会弹窗提示你安装缺失的包，全部同意即可。

> [!QUESTION]- Anaconda 虚拟环境到底该怎么用？
> 
> #### **核心理念：工具与库分离**
> 
> - **开发工具** (如 `nbdime`, `jupyter`): 安装在 Anaconda 的 **`base`** 环境中，以保证全局可用。
> - **项目依赖库** (如 `numpy`, `pandas`, `pinns`): **必须**安装在**每个项目自己**的虚拟环境中，以保证隔离性和可复现性。
> 
> #### **在 VS Code 中为 Notebook 选择环境**
> 1.  在 VS Code 中打开您的项目文件夹。
> 2.  按下 `Ctrl + Shift + P`，搜索并选择 `Python: Select Interpreter`。
> 3.  在弹出的列表中，选择您为该项目创建的 Anaconda 虚拟环境（例如 `'pinns-env': conda`）。
> 4.  当您打开一个 `.ipynb` 文件时，请检查并确保右上角的**内核 (Kernel)** 也被设置为同一个虚拟环境。

> [!QUESTION]- `Pandoc` 有什么用？
> 
> **用途**：一个文档格式的“瑞士军刀”，可以在几乎所有标记语言之间进行转换。
> 
> #### **安装与使用**
> 1.  在电脑系统上独立安装 **Pandoc** 软件。
> 2.  在 Obsidian 的社区插件市场安装 **`Pandoc Plugin`**。
> 3.  之后，您可以通过 Obsidian 的命令面板调用 Pandoc，轻松地将笔记导出为 Word (`.docx`), HTML, 甚至是格式化的 `.tex` 文件，非常适合生成报告。

> [!SUCCESS] 恭喜！
> 至此，您和您的团队已经拥有了一套专业、强大、可靠且完全免费的科研协同工作环境。虽然初次配置略显繁琐，但它将为你们后续的研究与写作节省下大量的时间和精力。祝你们协作愉快，成果丰硕！

## Part 6：🚀 项目主创首次上传指南：从本地到 GitHub

> [!NOTE] 操作概览
> 作为项目主创，您需要执行一个“首次上传”的操作，将您本地已经存在的项目文件夹与一个全新的 GitHub 仓库关联起来。
> 这个过程分为两步：
> 1.  先在 GitHub 上创建一个**空的“图书馆”**。
> 2.  然后在您本地的项目文件夹里使用 Git 命令将所有文件“上架”进去。

---

> [!TIP] 第 1 步：在 GitHub 上创建空的远程仓库
> **目标**：在云端创建一个空的、不带任何文件的仓库，像一个等待接收文件的新建文件夹。
>
> 1.  **登录 GitHub**：打开 [github.com](https://github.com/) 并登录。
> 2.  **创建新仓库**：访问 [github.com/new](https://github.com/new) 来创建一个新的仓库。
>     - **Repository name (仓库名)**：给您的项目起一个名字，例如 `team-research-project`。
>     - **Description (描述)**：简单描述一下项目内容（可选）。
>     - **Public / Private**：选择 **`Private` (私有)**。
>     - **Initialize this repository with (初始化选项)**：**请不要勾选**任何选项（不要添加 `README`, `.gitignore` 或 `license`）。我们需要一个完全空的仓库来接收您本地的文件。
> 3.  **创建并复制地址**：点击页面底部的 `Create repository` 按钮。创建成功后，页面会显示一些指引。请找到并复制仓库的 HTTPS 地址，它看起来像这样：`https://github.com/你的用户名/team-research-project.git`。

---

> [!TODO] 第 2 步：在您的本地项目文件夹中执行 Git 命令
> **目标**：在您的本地项目文件夹里初始化一个“Git时光机”，并把它和你刚刚在云端创建的“图书馆”连接起来。
>
> 1.  **打开终端**：进入您存放项目的本地文件夹（例如 `D:\Projects\MyResearch`），在文件夹空白处右键，选择“在终端中打开”或“Git Bash Here”。
>
> 2.  **初始化 Git 仓库**：
>     ```bash
>     git init
>     ```
>     > *说明：这个命令会在当前文件夹下创建一个本地的 Git 仓库（你会看到一个隐藏的 `.git` 文件夹）。*
>
> 3.  **将所有文件添加到暂存区**：
>     ```bash
>     git add .
>     ```
>     > *说明：这个命令告诉 Git，当前文件夹下的所有文件都准备好要被“拍照”记录下来。*
>
> 4.  **提交文件到本地仓库**：
>     ```bash
>     git commit -m "Initial commit: My research project files"
>     ```
>     > *说明：这是“按下快门”的动作，将所有暂存的文件正式记录为第一个历史版本。`-m` 后面是本次提交的说明。*
>
> 5.  **关联远程仓库**：
>     ```bash
>     git remote add origin [https://github.com/你的用户名/team-research-project.git](https://github.com/你的用户名/team-research-project.git)
>     ```
>     > [!WARNING]
>     > **请务必**将上面的地址替换为您在第一步中复制的、您自己的仓库地址。
>
> 6.  **重命名主分支**：
>     ```bash
>     git branch -M main
>     ```
>     > *说明：为了符合当前主流规范，我们将默认分支重命名为 `main`。*
>
> 7.  **推送（上传）到 GitHub**：
>     ```bash
>     git push -u origin main
>     ```
>     > *说明：这是最后一步，将您本地的 `main` 分支上的所有内容全部上传到 GitHub。`-u` 参数只需要在第一次推送时使用，它会建立本地 `main` 分支和远程 `main` 分支的联系。*

---

> [!SUCCESS] 上传完成！
> 执行完以上所有步骤后，刷新您的 GitHub 仓库页面，您会看到本地的所有文件都已经成功上传了。
> 
> 接下来，您的团队成员就可以通过 `git clone <仓库地址>` 的命令将项目下载到他们各自的电脑上，并开始协作了。

## 🎓 Pandoc 终极指南：你的文档格式“瑞士军刀”

> [!INFO] 什么是 Pandoc？为什么我需要它？
> 想象一下，你用 Obsidian 写了一篇非常漂亮的 Markdown 笔记，但现在你需要：
> - 把它作为 Word 文档（`.docx`）提交给老师。
> - 把它变成一份看起来非常专业的 PDF 实验报告。
> - 把它发布成一篇网页（`.html`）到你的个人博客。
> 
> 如果手动复制粘贴，所有格式都会丢失，非常痛苦。**Pandoc** 就是解决这个问题的神器！
> 
> [cite_start]它是一个文档格式的“瑞士军刀”，能帮你把一种格式（如 Markdown）的文档，自动转换成几乎任何其他你想要的格式 [cite: 2]。
> 
> > [!TIP] Pandoc 的工作方式
> [cite_start]> 在 Obsidian 中使用 Pandoc 需要两样东西，就像电视和遥控器一样 [cite: 2]：
> [cite_start]> 1.  **Pandoc 软件 (电视机)**：这是真正干活的程序，需要独立安装在你的电脑上 [cite: 2]。
> [cite_start]> 2.  **Obsidian 的 Pandoc 插件 (遥控器)**：这个插件能让你在 Obsidian 内部方便地“指挥”Pandoc 程序工作，而不用去敲复杂的命令 [cite: 2]。

---

### Part 1：安装 Pandoc (两步走)

> [!TODO] 安装步骤清单
> 1.  ✅ 安装 Pandoc 软件本体。
> 2.  ✅ 在 Obsidian 中安装 Pandoc 插件。

#### 步骤一：安装 Pandoc “引擎” (软件本体)

1.  **访问官网下载**：
    * [Pandoc 官方下载页面](https://pandoc.org/installing.html)
2.  **选择并下载安装包**：
    * 在下载页面，找到 Windows 部分，点击推荐的 `.msi` 安装包进行下载。
3.  **运行安装程序**：
    * 双击下载好的 `.msi` 文件。
    * 像安装普通软件一样，使用默认选项一路点击“Next”即可。安装程序会自动把它添加到系统环境中，让“遥控器”能找到它。
4.  **验证安装**：
    * 安装完成后，在“开始菜单”搜索 `cmd` 打开“命令提示符”，输入 `pandoc --version` 然后按回车。
    * 如果你看到一串版本号信息，恭喜你，Pandoc “引擎”已就位！

#### 步骤二：在 Obsidian 中安装 “遥控器” (Pandoc 插件)

1.  打开 Obsidian -> `设置` -> `社区插件`。
2.  确保“安全模式”已关闭，点击`浏览`。
3.  在搜索框中，搜索 **`Pandoc Plugin`**。
4.  点击`安装`，安装成功后点击`启用`。

> [!SUCCESS] 安装完成！
> 现在，你的 Obsidian 已经学会了“号令” Pandoc 的能力。让我们来试试看！

---

### Part 2：牛刀小试：Pandoc 应用示例

#### 示例一：将课堂笔记转换为 Word 文档 (`.docx`)

> [!EXAMPLE]- 场景：你需要将一份图文并茂的历史笔记提交为 Word 作业。
> 
> #### 1. 你的 Markdown 源代码 (`历史笔记.md`)
> ```markdown
> # 第二次世界大战简史
> 
> ## 战争的起因
> 
> 第二次世界大战的起因复杂多样，主要包括：
> - **经济危机**：1929年的大萧条导致全球经济动荡。
> - **政治因素**：法西斯主义在德国、意大利和日本的兴起。
> - **《凡尔赛和约》**：对德国过于苛刻的条款埋下了复仇的种子。
> 
> ## 主要战场
> 
> | 战场 | 主要参与国 |
> |---|---|
> | 欧洲战场 | 德国、苏联、英国、法国、美国 |
> | 太平洋战场 | 日本、美国、中国 |
> 
> > [!NOTE] 关键转折点
> > 斯大林格勒战役被普遍认为是欧洲战场的转折点。
> ```
> 
> #### 2. 操作步骤
> 1.  确保你正处在 `历史笔记.md` 这个笔记页面。
> 2.  按下 `Ctrl + P` (或 `Cmd + P`) 打开 Obsidian 的命令面板。
> 3.  输入 `Pandoc`，你会看到很多导出选项。
> 4.  选择 **`Pandoc Plugin: Export as docx`**。
> 5.  稍等片刻，插件会自动调用 Pandoc 完成转换。
> 
> #### 3. 查看成果
> - 在你的笔记库文件夹中，会出现一个名为 `历史笔记.docx` 的 Word 文件。
> - 打开它，你会发现所有的标题、列表、粗体、表格，甚至 Callout 的引用格式都完美地保留了下来！

#### 示例二：制作一份正式的实验报告 (`.pdf` via LaTeX)

> [!EXAMPLE]- 场景：你需要将一份包含数学公式的物理实验报告，转换成具有专业学术外观的 PDF。
> 
> #### 1. 你的 Markdown 源代码 (`自由落体实验报告.md`)
> ```markdown
> # 实验报告：测量重力加速度
> 
> **作者**：小明
> 
> ## 1. 实验原理
> 
> 根据自由落体运动公式，物体下落的高度 $h$ 与时间 $t$ 的关系为：
> $$h = \frac{1}{2} g t^2$$
> 通过测量多组 $h$ 和 $t$ 的数据，我们可以拟合出重力加速度 $g$ 的值。
> 
> ## 2. 实验数据
> 
> | 高度 (m) | 时间 (s) |
> |---|---|
> | 5.0 | 1.01 |
> | 10.0 | 1.43 |
> | 15.0 | 1.75 |
> 
> ## 3. 结论
> 
> 本次实验测得的重力加速度 $g \approx 9.8 \, \text{m/s}^2$，符合理论预期。
> ```
> 
> #### 2. 操作步骤
> > [!TIP] PDF 导出提示
> > 导出为 PDF 需要你已经按照我们之前的讨论，安装好了 MiKTeX 和 Perl。Pandoc 会在后台使用它们。
> 
> 1.  确保你正处在 `自由落体实验报告.md` 这个笔记页面。
> 2.  按下 `Ctrl + P` (或 `Cmd + P`) 打开命令面板。
> 3.  输入 `Pandoc`，选择 **`Pandoc Plugin: Export as pdf`**。
> 
> #### 3. 查看成果
> - 在你的笔记库文件夹中，会出现一个 `自由落体实验报告.pdf` 文件。
> - 打开它，你会看到一份排版精美、公式渲染正确的专业 PDF 文档。

#### 示例三：发布一篇博客文章 (`.html`)

> [!EXAMPLE]- 场景：你写了一篇影评，想把它发布到你的个人网站或博客上。
> 
> #### 1. 你的 Markdown 源代码 (`《星际穿越》影评.md`)
> ```markdown
> # 爱与引力：评《星际穿越》
> 
> 《星际穿越》不仅仅是一部硬核科幻电影，它更是一部关于爱、时间与人性的史诗。
> 
> ### 视觉奇观
> 
> 影片中对黑洞“卡冈图雅”的描绘，是基于物理学家基普·索恩的理论计算生成的，堪称科学与艺术的完美结合。
> 
> ```
> 电影中最震撼我的一句台词是：
> > 爱是唯一一种能超越时空维度的事物。
> ```
> 
> 总之，这是一部值得反复品味的杰作。
> ```
> 
> #### 2. 操作步骤
> 1.  确保你正处在 `《星际穿越》影评.md` 这个笔记页面。
> 2.  按下 `Ctrl + P` (或 `Cmd + P`) 打开命令面板。
> 3.  输入 `Pandoc`，选择 **`Pandoc Plugin: Export as html`**。
> 
> #### 3. 查看成果
> - 在你的笔记库文件夹中，会出现一个 `《星际穿越》影评.html` 文件。
> - 你可以用任何浏览器打开它，看到一个排版好的网页。你也可以把这个文件的内容直接粘贴到你的博客发布后台。

#### 示例四：Pandoc 教程：从 Markdown 到 LaTeX

> [!EXAMPLE]- Pandoc 终极教程：从 Markdown 到 LaTeX
> 
> > [!INFO] 我们的目标
> > 这份指南将手把手教你，如何将一篇在 Obsidian 中写好的、包含各种格式和数学公式的 Markdown 笔记，转换为一份标准的、可以被任何 LaTeX 编辑器打开和编译的 `.tex` 源码文件。
> 
> ---
> 
> #### Part 1：准备我们的“实验材料”
> 
> 首先，让我们准备一篇内容丰富的 Markdown 笔记作为示例。请在你的 Obsidian 库中创建一个新笔记，命名为 `MyArticle.md`，并将以下内容完整地复制进去。
> 
> > [!EXAMPLE]- 示例 Markdown 源代码 (`MyArticle.md`)
> > ```markdown
> > # 探索物理世界：从牛顿到爱因斯坦
> > 
> > **摘要**: 本文旨在简要回顾经典力学与相对论的核心思想，并探讨它们之间的联系。
> > 
> > ---
> > 
> > #### 1. 牛顿的经典力学
> > 
> > 艾萨克·牛顿爵士为我们描绘了一个宏伟的、确定性的宇宙图景。其核心是三大运动定律和万有引力定律。
> > 
> > ##### 1.1 牛顿第二定律
> > 
> > 物体所受的合外力 $F$ 等于其质量 $m$ 与加速度 $a$ 的乘积。这个关系可以用一个简洁的数学公式表达：
> > $$F = ma$$
> > 
> > ##### 1.2 万有引力
> > 
> > 任意两个质点之间都存在相互吸引力，其大小与质量乘积成正比，与距离的平方成反比。
> > 
> > | 变量 | 符号 | 含义 |
> > |---|---|---|
> > | 引力 | $F_g$ | 两个物体间的引力 |
> > | 万有引力常数 | $G$ | 一个普适常数 |
> > | 质量 | $m_1, m_2$ | 两个物体的质量 |
> > | 距离 | $r$ | 两个物体中心的距离 |
> > 
> > 对应的公式为：$F_g = G \frac{m_1 m_2}{r^2}$。
> > 
> > #### 2. 爱因斯坦的相对论
> > 
> > 相对论颠覆了牛顿的绝对时空观，它分为狭义相对论和广义相对论。
> > 
> > > [!NOTE] 核心思想
> > > 广义相对论的核心思想是：引力并非一种“力”，而是时空因质量分布而发生弯曲的一种几何效应。
> > 
> > 最著名的莫过于质能方程：
> > $$E = mc^2$$
> > 这个公式揭示了质量和能量之间深刻的等价关系。
> > ```
> 
> ---
> 
> #### Part 2：方法一：在 Obsidian 中使用 Pandoc 插件 (一键转换)
> 
> > [!TIP] 优点与适用场景
> > - **优点**: 极其简单、快速，无需打开终端，在 Obsidian 内部即可完成。
> > - **适用场景**: 适合快速生成 `.tex` 初稿，或者进行简单的格式转换。
> 
> ###### **操作步骤**
> 
> 1.  **确保你已准备好**:
>     - ✅ 你的电脑上已经安装了 **Pandoc 软件**。
>     - ✅ 你的 Obsidian 中已经安装并启用了 **`Pandoc`** 插件。
> 
> 2.  **打开你的 Markdown 笔记**: 在 Obsidian 中，打开我们刚刚创建的 `MyArticle.md` 文件。
> 
> 3.  **呼出命令面板**: 按下快捷键 `Ctrl + P` (Windows) 或 `Cmd + P` (Mac)。
> 
> 4.  **选择导出命令**: 在弹出的搜索框中，输入 `pandoc`，然后从列表中找到并点击 **`Pandoc Plugin: Export as latex`**。
> 
> > [!SUCCESS] 转换完成！
> > - 插件会在后台自动调用 Pandoc 程序。
> > - 完成后，在你的 Obsidian 库文件夹中，会自动出现一个名为 **`MyArticle.tex`** 的新文件。
> > - 你可以用任何文本编辑器（如 VS Code）打开这个 `.tex` 文件，查看转换后的 LaTeX 源代码。
> 
> ---
> 
> #### Part 3：方法二：使用命令行 (更专业、更可控)
> 
> > [!TIP] 优点与适用场景
> > - **优点**: 功能更强大，可以添加各种自定义参数来精确控制输出效果（例如指定文档模板、参考文献样式等）。这是更专业的做法。
> > - **适用场景**: 当你需要精细排版，或者需要将转换过程自动化时（例如写入脚本）。
> 
> ###### **操作步骤**
> 
> 5.  **打开终端**:
>     - 进入你的 Obsidian 库所在的文件夹。
>     - 在文件夹的空白处右键，选择“在终端中打开”或“Git Bash Here”。
> 
> 6.  **输入 Pandoc 命令**: 在弹出的终端窗口中，输入以下命令，然后按回车。
> 
>     ```bash
>     pandoc MyArticle.md -o MyArticle_cmd.tex
>     ```
> 
> > [!NOTE]- 命令详解
> > `pandoc MyArticle.md -o MyArticle_cmd.tex`
> > - **`pandoc`**: 这是调用 Pandoc 程序本身的命令。
> > - **`MyArticle.md`**: 这是**输入文件**，也就是我们想要转换的源文件。
> > - **`-o`**: 这是 “output”（输出）的缩写，一个参数，告诉 Pandoc 接下来要指定输出文件名。
> > - **`MyArticle_cmd.tex`**: 这是**输出文件**的名称。我特意加了 `_cmd` 后缀，以便和插件生成的文件区分开。
> 
> > [!SUCCESS] 转换完成！
> > - 命令运行后，终端不会有太多提示，直接回到可输入状态就表示成功了。
> > - 现在，你的文件夹里会出现一个名为 **`MyArticle_cmd.tex`** 的新文件。它的内容应该和插件生成的版本完全一样。
> 
> ---
> 
> #### Part 4：成果检验：看看 `.tex` 文件里有什么
> 
> 无论你用哪种方法，生成的 `.tex` 文件内容都会是标准的 LaTeX 源代码。让我们来看看 Pandoc 是如何巧妙地将 Markdown 语法翻译成 LaTeX 语言的。
> 
> > [!EXAMPLE]- 生成的 `MyArticle.tex` 源代码 (部分)
> > ```latex
> > \documentclass{article}
> > \usepackage{amsmath} % Pandoc 聪明地知道你有公式，自动加入了数学包
> > % ... 其他宏包定义
> > 
> > \author{摘要: 本文旨在简要回顾经典力学与相对论的核心思想，并探讨它们之间的联系。}
> > \title{探索物理世界：从牛顿到爱因斯坦}
> > \date{} % Pandoc 默认不添加日期
> > 
> > \begin{document}
> > \maketitle
> > 
> > \section{牛顿的经典力学}\label{sec:牛顿的经典力学}
> > 
> > 艾萨克·牛顿爵士为我们描绘了一个宏伟的、确定性的宇宙图景。其核心是三大运动定律和万有引力定律。
> > 
> > \subsection{牛顿第二定律}\label{subsec:牛顿第二定律}
> > 
> > 物体所受的合外力 \(F\) 等于其质量 \(m\) 与加速度 \(a\) 的乘积。这个关系可以用一个简洁的数学公式表达：
> > \[F = ma\]
> > 
> > \subsection{万有引力}\label{subsec:万有引力}
> > 
> > % ... 表格会被转换成 \begin{tabular} ... \end{tabular}
> > 
> > 对应的公式为：\(F_g = G \frac{m_1 m_2}{r^2}\)。
> > 
> > \section{爱因斯坦的相对论}\label{sec:爱因斯坦的相对论}
> > 
> > % ... Callout 会被转换成 \begin{quote} ... \end{quote}
> > 
> > 最著名的莫过于质能方程：
> > \[E = mc^2\]
> > 
> > \end{document}
> > ```
> 
> > [!TODO]- 翻译对照表：Markdown -> LaTeX
> > | Markdown 语法 | Pandoc 转换后的 LaTeX 命令 |
> > |---|---|
> > | `# 标题` | `\section{标题}` |
> > | `## 标题` | `\subsection{标题}` |
> > | `**粗体**` | `\textbf{粗体}` |
> > | `*斜体*` | `\textit{斜体}` |
> > | `> 引用` | `\begin{quote}引用\end{quote}` |
> > | `$行内公式$` | `\(行内公式\)` |
> > | `$$块级公式$$` | `\[块级公式\]` |
> > | 表格 | `\begin{longtable}...\end{longtable}` |
> 
> 通过这个过程，你不仅学会了如何使用 Pandoc，也顺便复习了 Markdown 和 LaTeX 之间的对应关系，为将来直接撰写 `.tex` 文件打下了基础！

---

> [!SUCCESS] 总结
> Pandoc 是打通“笔记”与“成品”之间壁垒的强大工具。今天我们只尝试了最常见的三种格式，它还支持导出为幻灯片（beamer）、思维导图（opml）等数十种格式，等待你去探索！