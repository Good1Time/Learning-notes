1. 安装 Git
   - [https://git-scm.com](https://git-scm.com/)
2. 源代码控制
   - **查看**>**源代码管理 (SCM)** ( Ctrl+Shift+G )
3. 初始化存储库
   - `main`是默认分支
4. 打开命令面板。
   - **视图**>**命令面板**( Ctrl+Shift+P )
5. 重命名分支
   - **Git：重命名分支**；**Git: Rename Branch**
6. 文件版本控制状态
   - **U** - 未跟踪的文件 ；Untracked file
   - **A** - 添加文件；         Added file
   - **M** - 修改文件；        Modified file
7. 提交文件
   - **提交**☑️（复选标记）按钮
8. 创建一个分支
   - **Git：创建分支**；**Git: Create Branch**
9. 合并（差异）编辑器
   - **内嵌视图**的按钮
10. 阶段变化
    - **阶段变化**➕按钮；**Stage Changes** ➕ button
11. 切换分支
    - 状态栏分支项（左下）；Status bar branch item (lower left)
12. 合并分支
    - **视图和更多操作**( **...** ) >**分支**>**合并分支**；**Views and More Actions** (**...**) > **Branch** > **Merge Branch**
13. 发布分支到 GitHub
14. 克隆存储库
    - **Git：克隆**>**从 URL 克隆**；**Git: Clone** > **Clone from URL**





## [装订线指示器](https://code.visualstudio.com/docs/sourcecontrol/overview#_gutter-indicators)

如果您打开一个作为 Git 存储库的文件夹并开始进行更改，VS Code 将向装订线和总览标尺添加有用的注释。

- 红色三角形表示已删除行的位置
- 绿条表示新添加的行
- 蓝色条表示修改的行

![装订线指示器](https://code.visualstudio.com/assets/docs/sourcecontrol/overview/gutter.png)

## [合并冲突](https://code.visualstudio.com/docs/sourcecontrol/overview#_merge-conflicts)

![Git 合并](https://code.visualstudio.com/assets/docs/sourcecontrol/overview/merge-conflict.png)

VS Code 可以识别合并冲突。差异被突出显示，并且有内联操作可以接受一个或两个更改。解决冲突后，暂存有冲突的文件，以便您可以提交这些更改。

## [查看差异](https://code.visualstudio.com/docs/sourcecontrol/overview#_viewing-diffs)

我们的 Git 工具支持查看 VS Code 中的差异。

![VS Code 中的文件差异](https://code.visualstudio.com/assets/docs/sourcecontrol/overview/diff.png)

> **提示：**您可以通过首先右键单击资源管理器或**打开编辑**器列表中的文件并选择**Select for Compare**然后右键单击要比较的第二个文件并选择**与 'file_name_you_chose' 比较**来区分任何两个文件。或者，从键盘上按 Ctrl+Shift+P并选择**文件：将活动文件与比较**，您将看到最近文件的列表。

### [差异编辑器审阅窗格](https://code.visualstudio.com/docs/sourcecontrol/overview#_diff-editor-review-pane)

Diff 编辑器中有一个查看窗格，以统一的补丁格式显示更改。您可以使用**转到下一个差异**( F7 ) 和**转到上一个差异**( Shift+F7 ) 在更改之间导航。可以使用箭头键导航行，按Enter将跳回 Diff 编辑器和选定的行。

![差异审查窗格](https://code.visualstudio.com/assets/docs/sourcecontrol/overview/diff-review-pane.png)

**注意：**此体验对屏幕阅读器用户特别有用。

## [时间线视图](https://code.visualstudio.com/docs/sourcecontrol/overview#_timeline-view)

默认情况下可在文件资源管理器底部访问的时间线视图是用于可视化文件的时间序列事件（例如，Git 提交）的统一视图。

![时间线视图](https://code.visualstudio.com/assets/docs/sourcecontrol/overview/timeline-view.png)

VS Code 内置的 Git 支持提供了指定文件的 Git 提交历史。选择一个提交将打开该提交引入的更改的差异视图。当您右键单击提交时，您将获得**Copy Commit ID**和**Copy Commit Message**的选项。

---



---

### Git状态管理

我们先拿 `Git` 来举例。比如说 `Git` 中有三种主要的文件状态：已提交（`Committed`）、修改（`Modified`）和暂存（`Staged`）。这里借用 Git-SCM 文档 Git – Git Basics 里的一张图来解释，一个文件或者修改，能够在这三个状态直接切换。

当我们修改了一个文件，它会变成修改状态（`Modified`）；然后我们可以通过脚本 “`git add ${filename}`” 把这个文件的状态改为暂存（`Staged`），被标记为暂存状态的文件，才有机会被提交。 最后我们可以通过 “`git commit`” 来提交所有在暂存状态里的文件。

![VSCode 版本管理](http://img.geek-docs.com/vscode/version-control/vscode-versioning-view-04.png)

回到 VS Code 的版本管理界面，在下图里，我们能够看到两种不同的状态。

- 第一个是 “暂存的修改”，也就是所有处于暂存状态的修改，它们都有机会被提交；
- 第二种则是普通的修改。此时侧边活动栏上的版本管理图标已经显示了数字 2，它提示我们当前项目里有两个不同的修改。

![VSCode 版本管理](http://img.geek-docs.com/vscode/version-control/vscode-versioning-view-05.png)

上面我们提到，在 Git 中提交代码前，我们需要先将代码改动变成暂存状态。这个操作的对应的命令行是 `git add ${fileName}`。我们同样也可以通过版本管理的视图来完成这样的操作：只需将鼠标移动到我们想要提交的文件上，就能够看到三个图标。

![VSCode 版本管理](http://img.geek-docs.com/vscode/version-control/vscode-versioning-view-08.png)

它们分别是：打开文件、放弃更改和暂存更改。我们只需点击 “暂存更改” 这个按钮，就能完成跟上面`git add` 一样的操作。

### SVN 状态管理

在 SVN 中，则有一个变更列表（changelist 的概念），即可以使用变更列表来将不同任务里的代码变更统一到一起。在下图里，我们能够看到一个“两个分组”，一个是尚未被添加到变更列表里的代码变动，另一个是名叫 TEST 的变更列表。

![VSCode 版本管理](http://img.geek-docs.com/vscode/version-control/vscode-versioning-view-06.png)

而如果我们使用的是 SVN，鼠标移动到文件改动上时，只能看到一个按钮 “Set Changelist”。

![VSCode 版本管理](http://img.geek-docs.com/vscode/version-control/vscode-versioning-view-09.png)

按下这个按钮后，我们就能看到一个列表，通过这个列表，可以选择创建新的变更列表（changelist），或者选择将这个改动增加到现有的某个变更列表中。

![VSCode 版本管理](http://img.geek-docs.com/vscode/version-control/vscode-versioning-view-10.gif)

## 提交变更

在选择完哪些代码变更要提交之后，下一步就是填写描述信息并提交了。在版本管理视图的上方，有一个输入框，我们把描述信息填入到这个输入框后，按下 Cmd + Enter 就能提交了（Subversion 是 Ctrl + Enter），也可以通过输入框上方的对号按钮来提交。

![VSCode 版本管理](http://img.geek-docs.com/vscode/version-control/vscode-versioning-view-11.gif)

## 其他操作

查看代码变化、改变文件状态和代码提交，这就是我们日常最常使用的几个操作了。而其他的操作，比如更新、回退、发布、储藏代码等等，我们可以通过点击输入框上方最右侧的三个点的图标，打开一个下拉菜单，选择我们想要的功能并执行。

![VSCode 版本管理](http://img.geek-docs.com/vscode/version-control/vscode-versioning-view-12.gif)

## 差异编辑器

**VSCode 差异编辑器**，介绍差异编辑器功能，包括：从差异编辑器跳转到一个普通的编辑器；在差异编辑器里显示代码里行末的空格符的变化；在当前文件里的多个变动之间进行跳转了。

下面我们来说一下差异编辑器。在差异编辑器的右上角，我们能够看到一排按钮。

![VSCode 差异编辑器](http://img.geek-docs.com/vscode/version-control/vscode-differences-editor-01.png)

**第一个按钮**的功能是从差异编辑器跳转到一个普通的编辑器，并且打开这个文件。这样我们能够无干扰地进行编辑操作了。

![VSCode 差异编辑器](http://img.geek-docs.com/vscode/version-control/vscode-differences-editor-02.gif)

**第二个按钮**控制的是：是否要在差异编辑器里显示代码里行末的空格符的变化。比如说你不小心在行末添加了几个空格，默认情况下，VS Code 觉得这几个空格不影响代码，就不会在差异编辑器里显示。但我建议把它打开，这样你就可以确保能够看到所有的代码改动。

![VSCode 差异编辑器](http://img.geek-docs.com/vscode/version-control/vscode-differences-editor-03.gif)

接下来的**两个箭头按钮**，就是用于在当前文件里的多个变动之间进行跳转了。

![VSCode 差异编辑器](http://img.geek-docs.com/vscode/version-control/vscode-differences-editor-04.gif)

最后是一个**三个点的图标**，想必不用点击开你也知道，它意味着里面有更多的功能，点击后即可看到一个下拉菜单。

这个下拉框里的命令，前三个是和 Git 相关的。在版本管理视图里我们只能够对文件的状态进行操作，但是 Git 同样允许我们修改文件中某一段代码变动的状态，就是通过这三个命令实现的。

![VSCode 差异编辑器](http://img.geek-docs.com/vscode/version-control/vscode-differences-editor-05.gif)

比如在上面的动图中，index.js 文件里有两段不同的改动，现在我只想把第一段代码改动变为暂存状态。那接下来我要做的就是选中这段代码，从下拉菜单里选择 “暂存所选范围”运行。这之后，我们在版本管理视图里就能够看到两组代码变动，“暂存的更改”这个组里是我刚才选中的那段代码变动，而“更改”组里则是第二个代码变动。

相信你已经猜想到了这个功能的用途，有的时候我们在修一个 bug 或者完成一个功能时，对代码做了一些临时的变动，但我们既不想提交这个变动，也不想把它清除掉，那通过这几个命令我们就能够真正按需提交代码变动了。

不过遗憾的是，SVN 这个插件并没有支持这个功能。

下拉菜单里的第四个则是和差异编辑器呈现方式相关的。默认情况下，差异编辑器采取并排的方式显示两个编辑器，左边的编辑器显示改动前的文件内容，右侧则是改动后的文件内容。其实我们也可以使用 “切换内联视图”，将代码改动显示在同一个编辑器里。

![VSCode 差异编辑器](http://img.geek-docs.com/vscode/version-control/vscode-differences-editor-06.png)

在这个内联的差异编辑器里，我们依然可以看出代码变动的情况。

至于最后的三个则是通用的编辑器命令，打开任意编辑器时，我们都能够使用它们。这里就不多赘述。

## 内置版本管理操作

**VSCode 内置版本管理操作**，前面我们一起学习了如何使用版本管理视图和差异编辑器对代码变动进行管理，其实我们同样也能够在普通的编辑器里完成这样的操作。当我们对一个文件作了修改后，我们能够在普通编辑器里，行号的右侧看到不同颜色的竖线。它们代表着不同状态的代码变动，比如代码增加、修改和删除。

![VSCode 内置版本管理操作](http://img.geek-docs.com/vscode/version-control/vscode-editor-built-in-version-management-actions-01.png)

当我们点击这个竖线时，我们就能在当前编辑器里，立刻看到一个内置的差异编辑器。这样我们就不用每次都打开版本管理视图里去查看代码变动了。

![VSCode 内置版本管理操作](http://img.geek-docs.com/vscode/version-control/vscode-editor-built-in-version-management-actions-02.gif)

在这个内置的差异编辑器的内侧，我们能够看到一些按钮。它们的作用跟差异编辑器右上角的那些按钮是一样的，你能够通过它们暂存、撤销代码改动，以及在代码改动之间跳转。当我们把鼠标移动上去时，还能够看到它们对应的快捷键。

![VSCode 内置版本管理操作](http://img.geek-docs.com/vscode/version-control/vscode-editor-built-in-version-management-actions-03.png)

## 状态栏和资源管理器

**VSCode 版本管理状态栏和资源管理器**，除了版本管理视图以外，另外一个能够快速了解项目版本状态的就是状态栏了。无论是使用 Git，还是 SVN 来做版本管理的项目里，我们都能在状态栏的左侧看到当前代码属于哪个分支。不仅如此，我们还能通过点击它来进行分支的创建与切换。

![VSCode 版本管理状态栏和资源管理器](http://img.geek-docs.com/vscode/version-control/vscode-vc-status-bar-and-resource-manager-01.gif)

此外，当我们在专心于写代码的时候，大部分情况下我们打开的都是资源管理器。为了方便我们在这种情况下快速地了解哪些文件被修改了、有什么类型的改动，VS Code 会把资源管理器中对应的文件项的颜色改变，同时在这个文件项的最后附上一个简单的字母，用于表明这个文件的状态。比如说我们在下面的图中看到，index.js 这个文件被修改了，那么在资源管理器里，这个文件项变成了黄色的，同时最后还有一个字母 M，也就是修改 Modified 的首字母。

![VSCode 版本管理状态栏和资源管理器](http://img.geek-docs.com/vscode/version-control/vscode-vc-status-bar-and-resource-manager-02.png)

## 版本管理命令结果输出

**VSCode 版本管理输出版本管理命令**，VS Code 的设计哲学并不想当一个黑盒，而是尽可能地开放给你。就好比说版本管理，Git 非常流行，但它的学习成本也很高，即便是一个熟练使用它的工程师，也偶尔会遇到奇怪的情况，更不要说刚刚学习它的新手了。为了保证你知道你按下某个按钮后，VS Code 最终转化成了哪个 Git 命令，或者你遇到意外情况的时候 Git 发生了什么，VS Code 会把所有这些信息全部输出到输出面板中。你可以打开输出面板，点击下拉框，然后选择你使用的版本管理工具的 log 进行查看。

![VSCode 版本管理输出版本管理命令](http://img.geek-docs.com/vscode/version-control/vscode-vc-output-versioning-commands-01.png)