# termux-localization-ci
自动构建[termux](https://github.com/termux/termux-app)程序界面的多语言版本。

[![Build](https://github.com/guobao2333/termux-localization-ci/actions/workflows/build.yml/badge.svg)](https://github.com/guobao2333/termux-localization-ci/actions/workflows/build.yml)

**注意：** 仅支持程序界面中字符串(比如长按菜单)，而非终端的提示信息！如果您想要终端也拥有翻译，请安装其他系统(proot)

## 添加语言
> [!IMPORTANT]
> 如果指定语言变体，需要注意大小写！

创建以语言国家/地区代码为名称的目录，并在其中粘贴您翻译的字符串即可。

示例：
```bash
mkdir en_US
cat > strings.xml
```

输入您的翻译后 `Ctrl + D` 保存。然后您可以打开PR来提交您的翻译，CI将自动合并您的翻译并开始构建程序，接下来等待一会即可在Release看到已包含您提交翻译的程序包。

如果您想要重新开始翻译，原文可在[此处](https://github.com/termux/termux-app/tree/master/app/src/main/res/values/strings.xml)获取，也可以在仓库中随意选择一种语言进行翻译。
