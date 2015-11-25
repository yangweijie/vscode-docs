# Visual Studio Code 文档

你已经发现包含着[Visual Studio Code 文档](http://code.visualstudio.com/docs) 的GitHub repository。

这里发布的主题将会发布到[Visual Studio Code](http://code.visualstudio.com) 。

## Visual Studio Code

VS Code 是一个轻量级但是强力的开发环境用于构建和调试现代web和云端应用。它免费并且跨平台 - Linux, Mac OSX and Windows。

如果你还想了解其他关于VS Code的信息，前往[我们的网站](http://code.visualstudio.com) 查看更多信息。

## 贡献文档

贡献新的话题或者修改已有文档，见[贡献] (https://github.com/Microsoft/vscode-docs/blob/master/CONTRIBUTING.md) 寻求说明和引导。

如果你想反馈文档，请使用每个文档页下方的反馈控制。提交文档bug，请创建一个 GitHub issue。

## 编辑

为了编辑 Code 文档, 确保你安装了  [Git](http://git-scm.com/downloads)。

克隆一个repo 副本:

```
git clone https://github.com/Microsoft/vscode-docs.git
```

VS Code 本身在良好预览支持下就对检查和编辑[Markdown](http://code.visualstudio.com/docs/languages/markdown) 很友好。

如果你想使用VS Code，简单导航至 `vscode-docs` 目录然后从当前目录运行VS Code:

```
cd vscode-docs
code .
```
你可以现在打开任意Markdown files 然后简单的在预览和编辑状态间切换通过编辑器右上的`Open Preview` 按钮。 

# VS Code 官方文档中文版

### 你正在翻译的项目可能会使VS Code变的流行甚至超过Sublime Text！


## 缘起 

Microsoft在2015年4月30日Build 开发者大会上正式宣布了 Visual Studio Code 项目：一个运行于 Mac OS X、Windows和 Linux 之上的，针对于编写现代 Web 和云应用的跨平台源代码编辑器。

该编辑器也集成了所有一款现代编辑器所应该具备的特性，包括语法高亮（syntax hight lighting），可定制的热键绑定（customizable keyboard bindings），括号匹配（bracket matching）以及代码片段收集（snippets）。Somasegar 也告诉笔者这款编辑器也拥有对 Git 的开箱即用的支持。

虽然基于Atom同样的内核打造，微软以着自身的强技术方案解决了webkit内核做应用的巨大问题-卡顿。打开30M文件秒开这足以完全压倒Sublime和Atom了。但是刚发布那会还没有扩展机制。

随着时间的流逝，微软也没有忘记更新，2015-11 v0.10.1的发布，已经开始支持扩展了。

对于使用了Sublime来说深知其 GUI api的缺少，和更新缓慢，我也迫不及待的想在这个新工具上继续创造功能强大，界面友好的插件了。

欢迎使用过Sublime 编辑器 或对自己轻量编辑器缺少ide特性的专家和爱好者参与这一翻译项目，我们会为每位翻译和校对人员署名。

## 一起来参与

如果想做出贡献(翻译或者校对)的话，请加QQ群：376649226，谢谢！

## 内容来源

英文官方网站：     
<https://code.visualstudio.com/Docs>

官方GitHub仓库：   
<https://github.com/Microsoft/vscode-docs>

中文版 GitHub 仓库：  
<https://github.com/yangweijie/vscode-docs/tree/0.10.0-zh>

## 参与步骤

* fork主仓库（<https://github.com/yangweijie/vscode-docs/tree/0.10.0-zh>）
* 按照章节认领翻译(每次申请一个章节)，在下面这个`README.md`里找还没有被人申请的章节，写上（@你的github号），给主仓库的`0.10.0-zh`分支提pull request；
* 提的 pull request 被确认，合并到主仓库后，代表你申请的章节*认领*完成，开始翻译；
* 翻译的文件为README.md或者TOC.md中对应的md文件，请不要翻译单独文件夹中的index.md
* 翻译过程请参照 *翻译协作规范* (见下一节)，完成翻译后提交 pull request 给主仓库的`master`分支；
* 校核完成后，从主仓库的`master`分支合并到主`publish`分支；
* 全部翻译完成后，生成PDF/ePub文档，放在极客学院Wiki平台发布；

## 翻译协作规范   

为了让大家协作顺畅，需要每一个人遵循如下协作规范~

- 如果对Markdown和GitHub不了解，请先阅读[如何使用Markdown](markdown.md)以及[如何使用GitHub](learn-github.md)
- 使用Markdown进行翻译，文件名必须使用英文
- 翻译后的文档请放到docs文件夹下的对应章节中，然后pull request即可
- 如遇到文中的图片，请统一放在对应章节目录/images目录下
- 原文中的HTML标签及代码请不要修改、翻译
- 有其他任何问题都欢迎发issue，我们看到了会尽快回复
- 翻译人员需将对应的原文地址和翻译人姓名添加到译文末尾，审校人员需要将自己的名字添加到译文末尾，具体格式请参见样例：   

> 原文：[Color Palettes](http://www.google.com/design/spec/resources/color-palettes.html)  翻译：[iceskysl](https://github.com/iceskysl)  校对：[PoppinLp](https://github.com/poppinlp)   

## 校对规范

- 认领校对时请提供原计算机方面翻译文章的翻译文，保证校对质量
- 文章通顺，适合人类阅读与理解，别让人以为是机翻
- 确保图片都能正常显示，且其相对地址都是/images，图片存放正确
- 专有名词符合术语表中的翻译要求，拿不准的新词汇可以使用中文翻译后加括号内英文的形式
- 校对人员需有一定专业背景，保证译文无专业知识方面错误
- 请查看翻译人员是否将原文链接和翻译链接放到译文最下方，审校人员需要将自己的名字添加到译文末尾，具体格式请参见样例：   

> 原文：[Color Palettes](http://www.google.com/design/spec/resources/color-palettes.html)  翻译：[iceskysl](https://github.com/iceskysl)  校对：[PoppinLp](https://github.com/poppinlp)   

- 有任何问题请提Issues或到协同翻译群讨论，校对后提PR等待Merge，管理员通过后会在目录后面打√标识完成

## 参与者（按认领章节排序）

### 翻译 & 校对

- 编辑器
  - [安装](docs/editor/setup.md)
  - [基本](docs/editor/codebasics.md)
  - [扩展画廊](docs/editor/extension-gallery.md)
- 扩展
  - [概述](docs/extensions/overview.md) 翻译：（[@yangweijie](https://github.com/yangweijie)）√ 校对：（[@yangweijie](https://github.com/yangweijie)）√

## 进度记录

- 2015-11, VS Code 发布 v0.10.1 版 开始支持插件扩展 

## 感谢支持

## 离线版本 
