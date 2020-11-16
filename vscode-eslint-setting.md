## 一.简介

**为什么要配置eslint呢？**

​	我刚接触到eslint的时候，感觉这玩意也太烦人了吧，我写个分号也给我报警告，定义函数时与后面的括号没有个空格，也给我报警告or报错...，每一位程序员都有自己编码风格，包括我自己也是，写着写着就放飞自我了...。

​	有自己的编码风格其实是一件好事，毕竟谁想受限于别人的规范呢？但是在团队协作开发的时候，个人的编码习惯可能会提高项目的维护成本，因为一段代码是你写，但是可能不是你维护，这时团队的其他成员在维护的时候也根据自己的风格来维护，这时代码就看起来有点乱了，以后再看你可能就会”口吐芬芳“了。所以在团队协作中制定一个编码规范是有必要的。

- 有的可以帮我们[避免错误]
- 有的可以帮我们写出[最佳实践的代码]
- 有的可以帮我们规范[变量的使用方式]
- 有的可以帮我们[规范代码格式]
- 用的可以帮我们更合适的使用[新的语法]



好，话不多说，开始配置（仅供参考）

**时间：**此文2020-11月编，有时候会因为版本升级，有些命令可能不再被支持，请自行辨别！！！

首先，要在vscode安装几个插件（每个插件具体有什么用可以自己查资料）

**1.ESlint**

**2.prettier  - code formatter**

**3.vetur**



**接下来进行配置Vscode的Eslint自动格式化**

找到 settings.json 文件：首选项 -> 设置 -> 搜索settings,找到 **编辑settings.json** 这些字眼，点击就可以开始编辑

（三个插件搭配使用）

```json
{
  "editor.fontSize": 18,
  "C_Cpp.updateChannel": "Insiders",
  "window.zoomLevel": 0,
  "editor.tabSize": 2,
  "explorer.confirmDelete": false,
  "php.validate.executablePath": "D:/wamp/bin/php/php5.4.16/php.exe",
  "git.path": "D:/git/Git/cmd/git.exe",
  "px-to-vw.viewportWidth": 1920,
  "cssrem.rootFontSize": 80,
  "workbench.colorTheme": "Atom One Dark",
  "workbench.iconTheme": "vscode-great-icons",
    
    // 以上那些代码是我原本就有的,你的可能不同，不用在意
    
    // 接下来是要新加的配置eslint的代码
    
    
  "diffEditor.ignoreTrimWhitespace": false,
  "notebook.kernelProviderAssociations": [],
  "html.format.indentHandlebars": true,
  "explorer.confirmDragAndDrop": false,
  "editor.renderControlCharacters": true,
  "editor.renderWhitespace": "all",
  "prettier.useTabs": true,
  "prettier.requireConfig": true,
  "editor.formatOnType": true,
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "html.format.contentUnformatted": "",
  "[html]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  // 默认使用prettier格式化支持的文件
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "vetur.format.defaultFormatter.html": "prettyhtml",
  "vetur.format.defaultFormatter.css": "prettier",
  "vetur.format.defaultFormatter.postcss": "prettier",
  "vetur.format.defaultFormatter.scss": "prettier",
  "vetur.format.defaultFormatter.less": "prettier",
  "vetur.format.defaultFormatter.stylus": "stylus-supremacy",
  // "vetur.format.defaultFormatter.js": "prettier",
  "vetur.format.defaultFormatter.ts": "prettier",
  "vetur.format.defaultFormatter.sass": "sass-formatter",
  "open-in-browser.default": "Chrome",
  // 将vetur的js格式化工具指定为vscode自带的
  "vetur.format.defaultFormatter.js": "vscode-typescript",
  // 移除js语句的分号
  "javascript.format.semicolons": "remove",
  // 在函数名后面加上括号，类似这种形式 foo () {}
  "javascript.format.insertSpaceBeforeFunctionParenthesis": true,
  // eslint配置项，保存时自动修复错误。
  "editor.codeActionsOnSave": {
    "source.fixAll": true
  },
  // 指定 *.vue 文件的格式化工具为vetur
  "[vue]": {
    "editor.defaultFormatter": "octref.vetur"
  },
  // 指定 *.js 文件的格式化工具为vscode自带
  "[javascript]": {
    "editor.defaultFormatter": "vscode.typescript-language-features"
  },
  "vetur.format.defaultFormatterOptions": {
    "JS-beautify-HTML": {
      //  JS-beautify-HTML的设置在这里
      "wrap_attributes": "force-aligned"
    },
    " prettyhtml": {
      "printWidth'": 100, //  每一行不超过100个字符
      "singleQuote": false, //  不用单引号
      "wrapAttributes": false,
      "sortAttributes": true
    },
    "prettier": {
      //  去掉代码结尾的分号
      "semi": false, //不加分号
      "singleQuote": true, //用单引号
      // #让prettier使用eslint的代码格式进行校验
      "eslintIntegration": true,
      "arrowParens": "always"
    }
  },
  // vscode默认启用了根据文件类型自动设置tabsize的选项
  "editor.detectIndentation": false,
}
```

