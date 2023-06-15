# Unknown at rule @tailwindcss(unknownAtRules)
此问题出现在 VS Code 编辑器中，此问题在 TailwindCSS 官网中也有提到：
```
Syntax support
Tailwind CSS uses a lot of custom CSS at-rules like @tailwind, @apply, and @screen, and in many editors this can trigger warnings or errors where these rules aren’t recognized.

The solution to this is almost always to install a plugin for your editor/IDE for PostCSS language support instead of regular CSS.

If you’re using VS Code, our official Tailwind CSS IntelliSense plugin includes a dedicated Tailwind CSS language mode that has support for all of the custom at-rules and functions Tailwind uses.

In some cases, you may need to disable native CSS linting/validations if your editor is very strict about the syntax it expects in your CSS files.
```
简而言之，官网中的解决办法就是安装 TailwindCSS 提供的 VS Code 插件 [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)。

但这里还有一个容易被忽略的问题，安装插件后异常信息依旧存在，并没有消失。导致这个问题的原因是还需要在插件中进行配置，参考插件文档中的说明：
```
Recommended VS Code Settings

files.associations

Use the setting to tell VS Code to always open files in Tailwind CSS mode:files.associations.css
```

插件的说明文档中建议设置 VS Code 编辑器打开css文件时使用 Tailwind CSS 模式。使用 VS Code 工作区设置后，内容如下：

./.vscode/setting.json
```
{
  "files.associations": {
    "*.css": "tailwindcss"
  }
}
```

更进一步可以把插件加入 VS Code 工作区项目推荐插件配置中，更好与插件的配置配对。

./.vscode/extensions.json
```
{
  "recommendations": ["bradlc.vscode-tailwindcss"]
}
```

推荐数组中的值是插件的唯一标识符（Unique Identifier），可以在插件介绍页面中找到。
