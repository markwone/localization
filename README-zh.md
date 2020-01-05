# 本地化

该项目包含Netdata HTML文档的翻译文件。 
所有贡献将通过GitHub Pull Requests提供。

## 增加新翻译语言

在根目录下，您将需要添加一个语言缩写的子目录，如 https://squidfunk.github.io/mkdocs-material/getting-started/#localization 所示。如果您的语言未出现在`mkdocs-material`翻译表中，您将看到一个链接，可让您在5分钟内提供新的翻译。一旦您的语言包含在`mkdocs-material`的发行版中，请告知我们，以便我们确保构建机制使用包含您的语言的版本。

你可以参照`netdata/netdata`项目目录树的精确结构，在你的目录下添加markdown文件。您可以翻译任意数量的文件。您提供的文件将用于覆盖本地化版本中现有的英文markdown文件。当然，文件名需要精确匹配。

例如，要提供有关如何更新Netdata的中文翻译，文件应为`zh/packaging/installer/UPDATE.md`。

当您对PR发出拉取请求时，您会看到针对您的语言自动执行Netlify检查。如果单击布局预览，则 https://docs.netdata.cloud/ 上的HTML文档也将以您提供的翻译的方式在`https://docs.netdata.cloud/[abbreviation]`下显示。对于前面的示例，可以在`https://docs.netdata.cloud/zh/packaging/installer/UPDATE.md`上找到翻译后的页面。

生成的文档具有语言切换器工具，一旦您的PR成功合并，我们将使用您的语言进行扩展。您可以通过添加[语言选项](https://github.com/netdata/netdata/blob/master/docs/generator/custom/themes/material/partials/header.html#L95)自行提交PR。

您可以看[netdata/netdata项目中的示例PR 7004](https://github.com/netdata/netdata/pull/7004)。

## 翻译更多文档

如果您已经在 https://docs.netdata.cloud 中看到您的语言，您会注意到许多文件仍以英文显示。按下“编辑”文件将导致您到一个无效的位置，因为没有人为该文件添加翻译。自行提供：
- 在`netdata/netdata` repo中找到对应的.md文档。
- 将其复制到`netdata/localization/[缩写]`下的同样的位置。
- 翻译并创建PR。

## 关于标题翻译的注意事项

Markdown文档中的标题既可以作为节的描述，又可以链接到文档的特定部分。翻译标题时，您将需要在文档中查找标题的其他索引，并更改该引用。修改指向节的所有链接的另一种解决方法是也保留原始的英文标题。这将导致标题重复，一个标题为英语，一个标题为您的语言，因此这并非一个妥当的解决方案。

解决了[构建过程中的问题](https://github.com/netdata/localization/issues/17)后，构建过程（`checklinks.sh`）会为您完成链接缺损的检查。因此，您将能够轻松找到需要修改的其他文件，以便成功构建。
