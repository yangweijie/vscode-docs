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

Visual Studio Code 是微软首次为开发者提供「跨平台」的代码编辑器，微软开发部门负责人称：“虽然许多人把 Windows 作为开发环境，但还有很多人用的是 Linux 和 Mac，与其说服这些人改用 Windows，不如在他们使用的平台上提供工具满足其要求。” 可以预见，VSC 的推出将会在开发界掀起轩然大波。

VS Code

VSC 的编辑器界面依然是微软经典的 VS 风格，对于常接触的人来说会很亲切。在编程语言和语法上支持 C++, jade, PHP, Python, XML, Batch, F#, DockerFile, Coffee Script, Java, HandleBars, R, Objective-C, PowerShell, Luna, Visual Basic, Markdown, JavaScript, JSON, HTML, CSS, LESS, SASS, C#, TypeScript (支持情况)。

经实际体验测试，VS Code 的启动速度以及打开大型文件的速度都非常迅速流畅，完全不卡，加载大文件几乎秒开，相比 Atom、Sublime Text 等感觉都要优秀！这一点对于某些追求效率的朋友来说的确非常诱人！

个人认为 VSC 对WEB和前端开发相对比较友好，相信日后会有不少如 PHP、Python、Ruby、Go、JS、Node 等的开发者会切换到 VSCode 来，它更像一个 WEB 开发界的 VS。

目前比较失望的是 Visual Studio Code 没有中文界面，而且也还没有开放插件扩展功能，不过从配置文件里的配置项命名空间看明显就是插件架构的，估计日后会在新版本开放，相信以微软的号召力，插件丰富繁荣起来应该不是什么问题。

随着时间的流逝，微软也没有忘记更新，2015-11 v0.10.1的发布，已经开始支持扩展了。

对于使用了Sublime来说深知其 GUI api的缺少，和更新缓慢，我也迫不及待的想在这个新工具上继续创造功能强大，界面友好的插件了。

欢迎使用过Sublime 编辑器 或对自己轻量编辑器缺少ide特性的专家和爱好者参与这一翻译项目，我们会为每位翻译和校对人员署名。

## 一起来参与

如果想做出贡献(翻译或者校对)的话，请加QQ群：432049227，谢谢！

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
  - [版本控制](docs/editor/versioncontrol.md)
  - [调试](docs/editor/debugging.md)
  - [任务](docs/editor/tasks.md)
  - [为什么需要VS Code](docs/editor/whyvscode.md)
- 定制化
  - [概述](docs/customization/overview.md)
  - [用户和工作空间配置](docs/customization/userandworkspace.md)
  - [快捷键](docs/customization/keybindings.md)
  - [代码片段](docs/customization/userdefinedsnippets.md)
  - [语言高亮](docs/customization/colorizer.md)
  - [主题](docs/customization/themes.md) 
- 语言
  - [概述](docs/languages/overview.md)
  - [JavaScript](docs/languages/javascript.md)
  - [C#](docs/languages/csharp.md)
  - [JSON](docs/languages/json.md)
  - [HTML](docs/languages/html.md)
  - [Markdown](docs/languages/markdown.md)
  - [TypeScript](docs/languages/typescript.md)
  - [Css、Sass和Less](docs/languages/css.md)
  - [Dockerfile](docs/languages/dockerfile.md)
- 运行时
  - [Node.js](docs/runtimes/nodejs.md)
  - [ASP.NET 5](docs/runtimes/ASPnet5.md)
  - [Unity](docs/runtimes/unity.md)
  - [Office](docs/runtimes/unity.md)
- 扩展
  - [概述](docs/extensions/overview.md) 翻译：（[@yangweijie](https://github.com/yangweijie)）√ 校对：（[@yangweijie](https://github.com/yangweijie)）√
  - [Example-Hello World](docs/extensions/example-hello-world.md) 翻译：（[@yangweijie](https://github.com/yangweijie)）√ 校对：（[@yangweijie](https://github.com/yangweijie)）√
  - [Example-字数统计](docs/extensions/example-word-count.md)
  - [Example-语言服务器](docs/extensions/example-language-server.md)
  - [Example-调试器](docs/extensions/example-debuggers.md)
  - [原则和模式](docs/extensions/patterns-adn-principles.md)
  - [运行和调试扩展](docs/extensions/debugging-extensions.md)
  - [安装扩展](docs/extensions/install-extension.md)
  - [测试扩展](docs/extensions/testing-extensions.md)
  - [我们扩展的方式](docs/extensions/our-approach.md)
- 可扩展性手册
  - [概述](docs/extensionAPI/overview.md)
  - [扩展清单文件](docs/extensionAPI/extension-mainfest.md)
  - [贡献点](docs/extensionAPI/extension-points.md)
  - [激活事件](docs/extensionAPI/activation-events.md)
  - [API vscode 命名空间](docs/extensionAPI/vscode-api.md)
  - [API调试](docs/extensionAPI/api-debugging.md)
- 工具
  - [发布工具](docs/tools/vscecli.md)
  - [扩展生成器](docs/tools/yocode,md)
  - [示列](docs/tools/samples.md)

## 进度记录

- 2015-11, VS Code 发布 v0.10.1 版 开始支持插件扩展 

## 感谢支持

## 离线版本 
