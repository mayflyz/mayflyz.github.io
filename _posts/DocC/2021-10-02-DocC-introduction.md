---
layout:     post
title:      "DocC简介"
subtitle:   "Swift Framework和package制作丰富的API参考文档和交互式教程"
date:       2021-10-02
author:     "mayfly"
header-img: "img/header/post-bg-ios.jpg"
tags:
    - iOS
    - DocC
---

# 概述
DocC(Documentation Compiler)是Xcode 13为Swift的Framework或package生成丰富的API参考文档和交互式教程提供的工具。通过对Markdown语法的扩充，DocC语法增加了对文档添加交叉符号链接、术语定义、代码列表和旁白的功能。将文档标记添加到源代码中，Xcode的`Product->Build Documentation`构建文档功能生成显示在Xcode文档窗口中的API参考文档。

DocC提供了两种文件类型
* API Documentation：根据源代码注释和文档扩展文件来创建参考文档，向开发人员传授API。
* Interactive Tutorials：通过循序渐进的交互式内容来生成教程，向开发人员传授API。

# API Documentation
DocC通过将源代码中的编写的注释及XCode中与项目相关的扩展文件、文章和其他资源结合来创建内容丰富的API文档。

## 从源注释构建简单的文档
XCode首先构建项目的Framework或package，并在在编译期间存储公共API的附加信息。DocC对目标所依赖的每个Swift Framework或package都重复此过程，然后利用该信息生成文档并添加进DocC的档案。
在DocC仅编译源代码中的注释时，会按照协议、类、枚举等类型来将这些文档组织在一起。

![docc-compilation-default](/img/DocC/docc-compilation-default.png)

DocC使用在源代码中编写的注释作为生成的文档页面的内容。可以在注释中添加接口摘要、说明、参数信息、返回值、抛出异常等内容，DocC根据这些内容编写Markdown文档。更多格式信息可参看 [Writing Symbol Documentation in Your Source Files](https://developer.apple.com/documentation/xcode/writing-symbol-documentation-in-your-source-files)。

```swift
/// Eat the provided specialty sloth food.
///
/// Sloths love to eat while they move very slowly through their rainforest 
/// habitats. They're especially happy to consume leaves and twigs, which they 
/// digest over long periods of time, mostly while they sleep.
///
/// When they eat food, a sloth's `energyLevel` increases by the food's `energy`.
///
/// - Parameters:
///   - food: The food for the sloth to eat.
///   - quantity: The quantity of the food for the sloth to eat.
///
/// - Returns: The sloth's energy level after eating.
///
/// - Throws: `SlothError.tooMuchFood` if the quantity is more than 100.
mutating public func eat(_ food: Food, quantity: Int) throws -> Int {
```
对源代码添加文档注释并进行编译，在文档查看器中找到对应的接口文档可以看到以下信息：

![doc-viewer-parameters](/img/DocC/doc-viewer-parameters.jpg)

## 配置更丰富的文档体验
当想在文档中添加附加内容活自定义扩建符号时，可以使用documentation catalog对文档注释进行补充：
* 在文档首页介绍Framework或Package和主要接口，已经自定义组织文档的结构
* 对源代码注释扩展及提供概念支持的文字
* 通过交互式的教程指导开发实践
* 在文档中包含图像和视频等资源文件

在现有项目中创建Documentation Catalog，并与库文件放在统一文件夹中，方便DocC将库与calatlog关联起来。当然也可以在创建Swift Framework项目时，直接选中`Include Documentation`选项创建文档目录。

![docc-compilation-catalog](/img/DocC/docc-compilation-catalog.png)

DocC将来自Swift编译器的公共API信息与文档目录的内容相结合，以生成更丰富的DocC档案。

![landing-page](/img/DocC/landing-page.png)

# Interactive Tutorials
使用Markdown编写教程文档，使用定义的特定类型如介绍、部分、步骤等来创建页面和元素。之后Xcode运行DocC编译器来构建文档，生成丰富的交互式教程。

![interactive-tutorials](/img/DocC/interactive-tutorials.png)

创建教程目录如下所示，包含介绍、部分等内容
```swift
@Tutorials(name: "Add the name of your tutorial here. This usually matches your framework name.") {
    @Intro(title: "Add a title for your introduction here.") {
        Add engaging introduction text here.
        
        @Image(source: "toc-introduction-image-filename.png", alt: "Add an accessible description for your image here.")
    }
    
    @Chapter(name: "Add a chapter title here.") {
        Add chapter text here.
        
        @Image(source: "chapter-image-filename-here.png", alt: "Add an accessible description for your image here.")
        
        @TutorialReference(tutorial: "doc:tutorial-page-file-name-here")
        @TutorialReference(tutorial: "doc:another-tutorial-page-file-name-here")
    }

    @Chapter(name: "Add the next chapter title here.") {

        ...

    }

    ...

}

```
对交互式教程进行构建，然后在文档查看器中可以看到以下信息：
![tutorial-toc](/img/DocC/tutorial-toc.png)


参考文档：
* [DocC](https://developer.apple.com/documentation/docc/)
* [DocC API Documentation](https://developer.apple.com/documentation/docc/api-reference-syntax)
* [DocC Interactive Tutorials](https://developer.apple.com/documentation/docc/tutorial-syntax)
* [DocC: 未曾设想的苹果文档](https://mp.weixin.qq.com/s/pft_R47ZDGjYz0vaIxsThw)