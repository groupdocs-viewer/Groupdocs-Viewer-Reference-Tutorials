---
title: Рендеринг изображений FODG и ODG
linktitle: Рендеринг изображений FODG и ODG
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как визуализировать изображения FODG и ODG в HTML, JPG, PNG и PDF с помощью GroupDocs.Viewer для .NET. Улучшите обработку документов.
type: docs
weight: 15
url: /ru/net/image-rendering/render-fodg-odg-images/
---
## Введение
В мире разработки программного обеспечения эффективная обработка форматов документов имеет первостепенное значение. GroupDocs.Viewer для .NET — это мощный инструмент, предназначенный для упрощения процесса рендеринга изображений FODG и ODG в приложениях .NET. В этом руководстве вы узнаете, как выполнить преобразование этих изображений в различные форматы, такие как HTML, JPG, PNG и PDF, с помощью GroupDocs.Viewer для .NET.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1.  GroupDocs.Viewer для .NET: Загрузите и установите GroupDocs.Viewer для .NET с сайта[здесь](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: убедитесь, что в вашей системе установлена .NET Framework.
3. Базовые знания C#: Знакомство с языком программирования C# будет полезным.

## Импортировать пространства имен
Прежде чем приступить к реализации, импортируйте необходимые пространства имен:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Шаг 1. Установите выходной каталог
```csharp
string outputDirectory = "Your Document Directory";
```
 Заменять`"Your Document Directory"`с путем к каталогу, в котором вы хотите сохранить визуализированные изображения.
## Шаг 2. Рендеринг в HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
На этом этапе изображение FODG преобразуется в формат HTML.
## Шаг 3. Рендеринг в JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Здесь изображение FODG преобразуется в формат JPG.
## Шаг 4. Рендеринг в PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
На этом этапе изображение FODG преобразуется в формат PNG.
## Шаг 5. Рендеринг в PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Наконец, изображение FODG преобразуется в формат PDF.

## Заключение
В этом руководстве мы рассмотрели, как визуализировать изображения FODG и ODG в различные форматы с помощью GroupDocs.Viewer для .NET. Выполнив эти шаги, вы сможете легко интегрировать возможности рендеринга документов в свои приложения .NET.
## Часто задаваемые вопросы
### Совместим ли GroupDocs.Viewer для .NET со всеми версиями .NET Framework?
GroupDocs.Viewer для .NET совместим с широким спектром версий .NET Framework, включая самые последние.
### Могу ли я отображать документы асинхронно с помощью GroupDocs.Viewer для .NET?
Да, GroupDocs.Viewer для .NET предоставляет возможности асинхронной отрисовки для повышения производительности.
### Поддерживает ли GroupDocs.Viewer для .NET отображение зашифрованных документов?
Да, GroupDocs.Viewer для .NET поддерживает отображение зашифрованных документов с соответствующими ключами расшифровки.
### Можно ли настроить вывод рендеринга с помощью GroupDocs.Viewer для .NET?
Конечно, GroupDocs.Viewer для .NET предлагает различные варианты настройки, позволяющие адаптировать результат рендеринга в соответствии с вашими требованиями.
### Могу ли я визуализировать документы из удаленных хранилищ с помощью GroupDocs.Viewer для .NET?
Да, GroupDocs.Viewer для .NET поддерживает отображение документов как из локальных, так и из удаленных хранилищ.