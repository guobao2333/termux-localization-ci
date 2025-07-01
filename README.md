# Termux Localization CI
自动构建[termux](https://github.com/termux/termux-app)程序的UI多语言版本。

[![Build](https://github.com/guobao2333/termux-localization-ci/actions/workflows/build.yml/badge.svg)](https://github.com/guobao2333/termux-localization-ci/actions/workflows/build.yml)

> [!NOTE]
> 仅支持程序界面中的字符串(比如长按菜单)，因为Android不支持区域设置(Locale)[^Locale]

[^Locale]: wiki: [区域设置](https://zh.wikipedia.org/wiki/%E5%8C%BA%E5%9F%9F%E8%AE%BE%E7%BD%AE)(简体中文) | [Locale](https://en.wikipedia.org/wiki/Locale_%28computer_software%29)(English)

## 增加更多语言
> [!IMPORTANT]
> 如果指定了语言变体，需要注意大小写！

创建以语言国家/地区代码为名称的目录，并在其中粘贴您翻译的字符串即可。

示例：
```bash
mkdir zh_TW
cat > zh_TW/strings.xml
```

输入您的翻译后 `Ctrl + D` 保存。然后您可以打开PR来提交您的翻译，CI将自动合并您的翻译并开始构建程序，接下来等待一会即可在Release看到已包含您提交翻译的程序包。

如果您想要重新开始翻译，原文可在[此处](https://github.com/termux/termux-app/tree/master/app/src/main/res/values/strings.xml)获取，但部分硬编码并不在 `values/strings.xml` 原始字符串中，您还可以在仓库中随意选择一种语言进行翻译。

## 常见问题 (QA)
1. Q: 为什么有时版本会落后？
   A: 暂未为工作流编写自动检测新版，只能手动更新。

2. Q: 为什么不编写自动检测并构建？
   A: 首先github会在仓库停止活动90天后禁用actions workflows的自动运行，其次actions并不支持在指定仓库更新时运行(即使hooks也需要仓库权限)，定时检测运行过于频繁可能会被封禁……

3. Q: 为什么不支持翻译终端？
   A: 如果您想要终端也拥有翻译，请通过proot安装其他系统，至于为什么只支持UI(用户界面)的翻译，您可以参考此官方人员回复: <https://github.com/termux/termux-app/pull/4410#issuecomment-2691513912>

4. Q: 为什么官方仓库本可以，但不支持界面翻译？
   A: 维护人员明确表示不会合并任何其他语言，因为就算翻译了termux应用程序(Application)，软件包(Packages)也没法或者说很难翻译。同时在没有翻译的情况下，业余用户都给维护者们带来了不少困扰，提供翻译之后会涌入更多非专业用户影响维护者的开发，因此维护者认为此工作的优先级较低。
