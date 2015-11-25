---
Order: 1
Area: extensions
TOCTitle: Overview
PageTitle: Extending Visual Studio Code
DateApproved: 11/18/2015
MetaDescription: Visual Studio Code has a rich extensibility model for interacting with and adding to the tool.  Learn how to create your own extensions (plug-ins) for Visual Studio Code.
---

# Extending Visual Studio Code

如果你对VS Code感兴趣，你可算找对地方了。下面是VS Code扩展文档的大纲，和如何快速创建你的第一个VS Code扩展。如果你对我们VS Code扩展能力的设计好奇，你看以读[这篇资料](/docs/extensions/our-approach.md).

![marketplace](images/overview/marketplace.png)

>**Tip:** 不要忘记不写扩展来[定制](/docs/customization/overview.md) VS Code 的几种方法。包括添加[主题](/docs/customization/themes.md)、[基本语言支持](/docs/customization/colorizer.md)及不写一行代码的添加 [Snippets](/docs/customization/userdefinedsnippets.md)。

所有VS Code扩展都遵循着一个通用模式 贡献（注册）、激活（加载）并访问VS Code 扩展 API。但是有两个特殊口味的VS Code扩展：language servers and debuggers, 他们有自己额外的协议并且有自己独立的文档。

1. [Extensions](/docs/extensions/overview.md#extensions) - 基本构建块
2. [Language Servers](/docs/extensions/overview.md#language-servers) - 高IO开销或者CPU敏感的任务
3. [Debuggers](/docs/extensions/overview.md#debuggers) - 链接一个外部调试器


## Extensions
所有激活的扩展跑再我们共享的扩展host进程上。这个供扩展用的单独的进程保证VS Code 自始自终保留响应性。 

扩展提供的支持包括:

* **Activation（激活）** - 当一个指定文件类型被检测到、一个指定类型文件存在或者当一个命令被选择了通过命令面板或者快捷键调用时加载一个扩展
* **Editor(编辑器)** - 作用域编辑器的内容 - 读和操作文本、单个或多个选区
* **Workspace(工作空间)** - 访问工作文件、状态栏、提示信息或者更多
* **Eventing(事件)** - 链接编辑器的生命周期，比如：打开、关闭、改变或其他
* **Evolved editing(增强编辑)** - 创建富语言的支持包括智能感知、Peek、悬停、诊断等等

我们有2个端对端的示列让你掌握扩展的基础:

1. **[Hello World](/docs/extensions/example-hello-world.md)** - 生成一个基本的扩展，理解一个扩展的目录结构、扩展主文件、学习激活的作用、本地执行和调试你的扩展。
2. **[Word Count](/docs/extensions/example-word-count.md)** - 激活于一个指定的文件类型、更新状态栏、响应文本编辑器的改变，移除文件时处理你的扩展。

## Language Servers(语言服务器)
Language servers （语言服务器）供你创建一个给你扩展专用的的进程。这是一个对于你的扩展来说很有用的设计选择当你的扩展运行占用高CPU或者IO开销敏感的任务时可能会拖慢其他扩展。比如这是一个工作空间里全部文件处理的惯例。检查器或者统计分析套件。

了解更多请看[language servers](/docs/extensions/example-language-server.md)。

## Debuggers（调试器）
链接一个用[任意语言编写的] 调试器到VS Code 是可能的通过穿件一个debug 调试服务。

了解更多请参阅[debuggers](/docs/extensions/example-debuggers.md)。
 
最简单的查看VS Code 有效扩展的方式是通过[扩展画廊](/docs/editor/extension-gallery.md)。你可以浏览有用的扩展、安装和尝试他们并且可能获得适合于你的开发场景的扩展。
## 编写扩展
扩展既可以用TypeScript也可以用JavaScript来写。 VS Code 提供了一个一流扩展开发体验，你可以[开发、编译、运行、测试和调试](/docs/extensions/debugging-extensions.md) 全部在VS Code中。

## 安装和分享
一旦你有一个可用的扩展，你可以[[安装它或者分享它给其他人]](/docs/extensions/install-extension.md)。我们支持本地安装、私有分享或者发布到 [扩展画廊](/docs/editor/extension-gallery.md)里。

## 测试扩展
我们同时也有方便的[[编写和执行测试]](/docs/extensions/testing-extensions.md) 你的扩展的支持。你可以轻松创建调用VS Code APIs 的测试集成 然后在执行VS Code 实例时测试你的代码。

## 接下来的步骤
* [Your First Extension](/docs/extensions/example-hello-world.md) - 尝试创建一个简单的 Hello World 扩展
* [Extension API](/docs/extensionAPI/overview.md) -了解 VS Code extensibility APIs
* [Samples](/docs/tools/samples.md) - 一系列示列扩展你可以回顾和编译

## Common Questions

Nothing yet

