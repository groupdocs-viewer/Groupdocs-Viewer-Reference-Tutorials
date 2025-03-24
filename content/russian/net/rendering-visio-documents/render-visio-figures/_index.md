---
title: Рендеринг фигур Visio
linktitle: Рендеринг фигур Visio
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как отображать фигуры Visio с помощью GroupDocs.Viewer для .NET с помощью этого комплексного руководства. Расширьте возможности просмотра документов в своих приложениях .NET.
weight: 10
url: /ru/net/rendering-visio-documents/render-visio-figures/
---
## Введение
В современную цифровую эпоху рендеринг документов играет решающую роль в различных приложениях. Будь то отображение документов на веб-сайте или преобразование их в другие форматы, эффективный рендеринг имеет важное значение. GroupDocs.Viewer для .NET предоставляет надежное решение для просмотра документов и управления ими в приложениях .NET. В этом руководстве мы углубимся в рендеринг фигур Visio с помощью GroupDocs.Viewer для .NET, разбив этот процесс на простые шаги.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1. Настройка среды: убедитесь, что у вас есть рабочая среда для разработки .NET.
2.  GroupDocs.Viewer для .NET: Загрузите и установите GroupDocs.Viewer для .NET с сайта[ссылка для скачивания](https://releases.groupdocs.com/viewer/net/).
3. Базовое понимание C#: ознакомьтесь с основами языка программирования C#.
4. Образец документа Visio. Подготовьте образец документа Visio для рендеринга.

## Импортировать пространства имен
В вашем проекте C# начните с импорта необходимых пространств имен:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Рендеринг в HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Выходной каталог: определите каталог, в котором будет сохранен отображаемый HTML.
- Формат пути к файлу страницы: укажите формат пути для HTML-страницы.
- Инициализация средства просмотра: инициализируйте объект средства просмотра путем к документу Visio.
- Параметры просмотра HTML: настройка параметров рендеринга HTML.
- Параметры рендеринга Visio: установите параметры, специфичные для рендеринга Visio, например рендеринг только фигур и ширины фигур.
## 2. Рендеринг в JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Аналогично рендерингу в HTML, настройте параметры рендеринга в формат JPG.
## 3. Рендеринг в PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Конфигурация рендеринга в формате PNG аналогична рендерингу JPG.
## 4. Рендеринг в PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Для рендеринга в PDF настройте параметры, специфичные для формата PDF.

## Заключение
В этом руководстве мы рассмотрели, как отображать фигуры Visio с помощью GroupDocs.Viewer для .NET. Следуя пошаговому руководству, вы сможете легко интегрировать возможности рендеринга документов в свои приложения .NET, повышая удобство работы и производительность пользователей.
## Часто задаваемые вопросы
### Могу ли я настроить параметры рендеринга фигур Visio?
Да, GroupDocs.Viewer для .NET предоставляет широкие возможности для настройки отрисовки, включая ширину фигуры, отрисовку только фигур и многое другое.
### Подходит ли GroupDocs.Viewer для .NET для крупномасштабной визуализации документов?
Безусловно, GroupDocs.Viewer для .NET оптимизирован для эффективной обработки крупномасштабного рендеринга документов.
### Поддерживает ли GroupDocs.Viewer другие форматы документов, кроме Visio?
Да, GroupDocs.Viewer поддерживает широкий спектр форматов документов, включая PDF, Microsoft Office, AutoCAD и другие.
### Могу ли я интегрировать GroupDocs.Viewer в веб-приложения?
Да, GroupDocs.Viewer можно легко интегрировать в веб-приложения для просмотра и управления документами.
### Доступна ли пробная версия для тестирования перед покупкой?
Да, вы можете воспользоваться бесплатной пробной версией от[Веб-сайт](https://releases.groupdocs.com/) протестировать возможности GroupDocs.Viewer для .NET.