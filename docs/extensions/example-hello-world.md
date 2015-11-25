---
Order: 2
Area: extensions
TOCTitle: Example-Hello World
PageTitle: Your First Visual Studio Code Extension - Hello World
DateApproved: 11/18/2015
MetaDescription: Create your first Visual Studio extension (plug-in) with a simple Hello Word example.  This walkthrough will take you through the basics of VS Code extensibility.
---

# Example - Hello World

## 你的第一个扩展

本文章将带着你创建你的第一个 VS Code 扩展 ("Hello World") 并且将解释最基本的 VS Code 扩展性概念。  

在本环节，你将向VS Code里添加一个显示一个简单的"Hello World"信息的新的命令。在本环节后期，你将与VS Code 编辑器交互并且查询用户当前选择文本。

## 最低要求
你需要 [node.js](https://nodejs.org/en/) 安装了并且你的`$PATH` 可用。

## 生成一个新扩展

最简单的方式是添加你自己的功能到 VS Code 是通过添加一个命令。一个命令注册一个回调函数它可以被触发通过命令面板或者快捷键。

我们已经写了一个Yeoman生成器来帮助你起步。安装Yeoman 和[Yeoman VS Code Extension generator](/docs/tools/yocode.md) 然后起草一个新扩展:

```sh
npm install -g yo generator-code
yo code
```

对于 hello world 扩展，你既可以创建一个 **TypeScript** 扩展也可以 创建一个 **JavaScript** 。在本列子中，我们选择创建一个 **TypeScript** 扩展。

![The command generator](images/example-hello-world/generator.png)

## 运行你的扩展

* 运行VS Code, 选择 `File` > `Open Folder` 然后选择你生成的那个目录。
* 按 `kb(workbench.action.debug.start)` 或 点击`Debug` 图标然后点击 `Start`.
* 一个新的 VS Code 实例将会以一个特殊模式(`扩展开发Host`)启动然后 **这个新的实例将会注意到你的扩展**。
* 按快捷键 `kb(workbench.action.showCommands)` 然后运行名为`Hello World`的命令。
* 恭喜你! 你已经刚刚创建并执行了你的第一个 VS Code 命令!

![Running VS Code with an extension](images/example-hello-world/running.png)

## 扩展的结构
在执行之后，生成的扩展应当遵循下面的结构:

```
.
├── .gitignore
├── .vscode                     // VS Code integration
│   ├── launch.json
│   ├── settings.json
│   └── tasks.json
├── .vscodeignore
├── README.md
├── src                         // sources
│   └── extension.ts			// extension.js, in case of JavaScript extension
├── test                        // tests folder
│   ├── extension.test.ts	   // extension.test.js, in case of JavaScript extension
│   └── index.ts	            // index.js, in case of JavaScript extension
├── node_modules
│   ├── vscode                  // language services
│   └── typescript              // compiler for typescript (TypeScript only)
├── out                         // compilation output (TypeScript only)
│   ├── src
│   |   ├── extension.js
│   |   └── extension.js.map
│   └── test
│       ├── extension.test.js
│       ├── extension.test.js.map
│       ├── index.js
│       └── index.js.map
├── package.json                // extension's manifest
├── tsconfig.json               // jsconfig.json, in case of JavaScript extension
├── typings                     // type definition files
│   ├── node.d.ts               // link to Node.js APIs
│   └── vscode-typings.d.ts     // link to VS Code APIs
└── vsc-extension-quickstart.md // extension development quick start
```

让我们捋一捋所有文件的意图并解释下他们起什么作用:

### 扩展清单: `package.json`

* 请详读[`package.json` 扩展清单手册](/docs/extensionAPI/extension-manifest.md)
* 更多参见[`package.json` 贡献点](/docs/extensionAPI/extension-points.md)
* 每一个 VS Code 扩展必须有 一个 `package.json` 文件来描述它和它的能力。
* VS Code 在启动时读取这个文件然后立即响应每个 `contributes` 区 。

#### 示列 TypeScript 扩展清单

```json
{
	"name": "myFirstExtension",
	"description": "",
	"version": "0.0.1",
	"publisher": "",
	"engines": {
		"vscode": "^0.10.1"
	},
	"categories": [
		"Other"
	],
	"activationEvents": [
		"onCommand:extension.sayHello"
	],
	"main": "./out/src/extension",
	"contributes": {
		"commands": [{
			"command": "extension.sayHello",
			"title": "Hello World"
		}]
	},
	"scripts": {
		"vscode:prepublish": "node ./node_modules/vscode/bin/compile",
		"compile": "node ./node_modules/vscode/bin/compile -watch -p ./"
	},
	"devDependencies": {
		"typescript": "^1.6.2",
		"vscode": "0.10.x"
	}
}
```

> **注意:** 一个JavaScript扩展不编译时不需要`scripts`字段。

* 这个指定的 package.json 描述一个扩展:
 * *贡献* 一个入口到 Command Palette (`kb(workbench.action.showCommands)`) 通过标签 `"Hello world"` 将会触发一个命令 `"extension.sayHello"`。 
 * 请求将会加载 (*activationEvents*) 当`"extension.sayHello"`触发时。
 * has its *main* JavaScript code in a file called `"./out/src/extension.js"`.

> **注意:** VS Code **不会** 启动时立即加载一个扩展的代码。一个扩展必须描述通过[`activationEvents`](/docs/extensionAPI/activation-events.md) 属性来说明什么情况下它将会被激活(加载)。

### 代码e

生成的扩展的 代码 在 `extension.ts`中 (或者 `extension.js` 一个JavaScript情况下):

```javascript
// The module 'vscode' contains the VS Code extensibility API
// Import the module and reference it with the alias vscode in your code below
import * as vscode from 'vscode';

// this method is called when your extension is activated
// your extension is activated the very first time the command is executed
export function activate(context: vscode.ExtensionContext) {

	// Use the console to output diagnostic information (console.log) and errors (console.error)
	// This line of code will only be executed once when your extension is activated
	console.log('Congratulations, your extension "my-first-extension" is now active!');

	// The command has been defined in the package.json file
	// Now provide the implementation of the command with  registerCommand
	// The commandId parameter must match the command field in package.json
	var disposable = vscode.commands.registerCommand('extension.sayHello', () => {
		// The code you place here will be executed every time your command is executed

		// Display a message box to the user
		vscode.window.showInformationMessage('Hello World!');
	});
	
	context.subscriptions.push(disposable);
}
```

* 每个扩展应当在它的主文件里输出一个名为`activate()`的函数, 这个函数 VS Code 将 **触发一次** 当前仅当任意 `activationEvents` 描述于`package.json`的事件发生时。
* 本扩展导入了 `vscode` API 并注册了一个命令， 当命令`"extension.sayHello"`被触发时关联一个调用函数。命令实现是在VS Code中显示一个"Hello world"信息。

> **注意:**  `package.json`的`contributes`区域添加一个命令面板的入口。在 extension.ts/.js 中的代码定义了 `"extension.sayHello"`的实现。

> **注意:** 对于TypeScript 扩展, 生成在`out/src/extension.js` 将会被运行时被VS Code加载并运行。

### 其他文件

* `.vscode/launch.json` 定义在扩展开发模式下运行。同样的， `preLaunchTask`对应一个定义在`.vscode/tasks.json`中的任务将会执行 TypeScript 编译器。
* `.vscode/settings.json` 默认包含 `out` 目录。你可以修改那些文件类型你想隐藏的。
* `.gitignore` - 告诉Git 版本控制那些模式被忽略。
* [`.vscodeignore`](/docs/tools/vscecli.md#advanced-usage) - 告诉打包工具那些文件在发布成扩展时忽略。
* `README.md` - README 文件向VS Code 用户描述你的扩展。
* `vsc-extension-quickstart.md` - 一个给你的快速向导。
* `test/extension.test.ts` - 你可以放置你扩展的单元测试并且执行你的测试通过VS Code API (见 [测试你的扩展](/docs/extensions/testing-extensions.md))

## 运行你的扩展

既然扩展包含的文件的职责已经明确了，下面是你的扩展如何被激活的:

* 扩展开发实例发现扩展并读取它的`package.json` 文件。
* 之后当你按下快捷键`kb(workbench.action.showCommands)`:
 * 注册过的命令显示在命令面板中。
 * 列表里现在有一个入口`"Hello world"` 在`package.json`中被定义了。
* 当选择了`"Hello world"`命令:
 * 命令`"extension.sayHello"`被触发:
   * 一个激活事件`"onCommand:extension.sayHello"`被创建。
   * 所有扩展在`activationEvents`中监听此激活事件被激活。
     * 位于`./out/src/extension.js`的文件加载到JavaScript VM。
     * VS Code 寻找一个输出函数`activate` 并且调用它.
     * 命令 `"extension.sayHello"` 被注册并且他的实现被定义了。
 * 命令`"extension.sayHello"` 实现函数被触发。
 * 命令实现显示"Hello World" 信息。

## 调试你的扩展

简单的设置一个断点，举个列子在registered 命令里然后运行`"Hello world"`命令在扩展开发VS Code实例里。

![Debug Extension](images/example-hello-world/hitbp.png)

> **注意:** 对于扩展，尽管 VS Code 加载和执行 `out/src/extension.js`，你实际上能调试原始的 TypeScript 代码 由于生成了 source map `out/src/extension.js.map` 而 VS Code's 调试器支持 source maps。

> **Tip:** 调试终端将显示所有你调试的日志。

了解更多参见扩展 [开发环境](/docs/extensions/debugging-extensions.md)。

## 一个简单的修改

在 `extension.ts` (或 `extension.js`, 在 一个 JavaScript 扩展), 尝试替换`extension.sayHello` 命令实现为显示编辑器里选择的字符的个数:

```javascript
var editor = vscode.window.activeTextEditor;
if (!editor) {
	return; // No open text editor
}

var selection = editor.selection;
var text = editor.document.getText(selection);

// Display a message box to the user
vscode.window.showInformationMessage('Selected characters: ' + text.length);
```

> **Tip:** 一旦你改变了扩展的源码，你需要重启VS Code的开发实例。你可以通过在第二实例中使用快捷键 `kbstyle(Ctrl+R)` (Mac: `kbstyle(Cmd+R)`) 或通过点击主VS Code实例的上方的重启按钮。

![Running the modified extension](images/example-hello-world/selection-length.png)

## 本地安装你的扩展

到目前为止，你写的扩展只能运行在一个特定的VS Code实例里，即扩展开发实例。为了使你的扩展运行在所有VS Code 实例中，你需要复制它到一个新的你本地扩展目录中:

* Windows: `%USERPROFILE%\.vscode\extensions`
* Mac/Linux: `$HOME/.vscode/extensions`

## 发布你的扩展

阅读关于如何[分享一个扩展](/docs/tools/vscecli.md).

## 接下来做什么

在刚刚的环节，我们已经看到一个非常简单的扩展。了解更多细节示列，见[Word Count 示列](/docs/extensions/example-word-count.md) 它将展示如何争对一个指定的语言language (Markdown) 然后监听编辑器的document changed 事件。

如果你想了解更多通用extension APIs, 尝试读下面主题:

* [Extension API 概述](/docs/extensionAPI/overview.md) - 学习全部的 VS Code 扩展性模型。
* [API 模式和原则](/docs/extensions/patterns-and-principles.md) - VS Code 扩展性基于的几个指导模式和原则。
* [贡献点](/docs/extensionAPI/extension-points.md) - 很多 VS Code 贡献点的细节。
* [Activation Events](/docs/extensionAPI/activation-events.md) - VS Code 激活 事件手册

## Common Questions

Nothing yet


