# Copyright 0.9.3 for Typecho 1.1
此插件修改并修复Bug自 [Yves-X/Copyright-for-Typecho](https://github.com/Yves-X/Copyright-for-Typecho)

这是一个 [Typecho](https://github.com/typecho/typecho) 插件，利用自定义字段功能灵活地在文章或独立页面尾部显示版权小尾巴。

就像这样：

> 版权声明：本文为原创文章，版权归 xxx 所有。
>
> 原文链接：https://github.com/YKilin/Copyright-for-Typecho
>
> 转载时须注明出处及本声明

## 安装

1. 下载插件
1. 打开 Typecho 根目录
1. 解压至 ./usr/plugins/
1. 将目录重命名为`Copyright`

你也可以：

```bash
# Initailly open the root document of your Typecho, then
cd usr/plugins/
git clone https://github.com/YKilin/Copyright-for-Typecho.git
mv Copyright-for-Typecho Copyright
```

## 启用

登入 Typecho 后台，控制台——插件——启用——设置

## 设置

你在插件管理中看到的设置项为**全局设置**，你也可以通过自定义字段，对单个文章/独立页面进行**特定设置**。

当然，特定设置的优先级始终高于全局设置。

你可以使用的字段有：

| 字段 |类型|说明|示例|
|:---:|:---:|:----|:----|
|switch|整数|版权信息的开关|1|
|author|字符|版权作者姓名|神代綺凜|
|url|字符|原文链接（当你的文章是转载的时候可以通过这个设置原文链接）|https://github.com/YKilin/Copyright-for-Typecho|
|notice|字符|版权声明|转载时须注明出处及本声明|

你可以把任意字段的值设定为**整数0**来关闭它。

## 定制

如果你想修改样式，插件输出的版权信息已提供 `.content-copyright` 的 CSS 钩子，请自定义你的CSS文件。

如果你想进行其他修改，喂，只有单文件插件也懒得改么……

## 示例

插件非常简单粗暴，但是为了体现灵活二字，让我们来看一个有意复杂化的示例。

假设你的全局设置如下：

- 作者：Collin
- 声明：转载时须注明出处及本声明
- 显示原文链接：开
- 在文章显示：关
- 在独立页面显示：关

显然，由于文章和独立页面的显示均关闭，插件并不会在任何地方输出版权信息。

现在你要对某篇特定的文章显示版权信息，有以下要求：

1. 不显示作者
1. 显示原文链接
1. 声明为“禁止转载”

你只需用自定义字段功能，将于全局设置不符的选项覆盖。在此处，你只需填写三条字段：

| 字段 |类型|值|
|:---:|:---:|:----:|
|switch|整数|1|
|author|整数|0|
|notice|字符|禁止转载|

显示效果为：

> 原文链接：https://github.com/Yves-X/Copyright-for-Typecho
>
> 禁止转载
