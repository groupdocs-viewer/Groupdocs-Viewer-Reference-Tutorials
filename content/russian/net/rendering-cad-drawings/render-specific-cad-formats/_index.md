---
title: Специальные форматы САПР для рендеринга (CF2)
linktitle: Специальные форматы САПР для рендеринга (CF2)
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как преобразовать определенные форматы САПР, такие как CF2, в HTML, JPG, PNG и PDF с помощью Groupdocs.Viewer для .NET.
weight: 12
url: /ru/net/rendering-cad-drawings/render-specific-cad-formats/
---
## Введение
В этом руководстве мы рассмотрим, как визуализировать определенные форматы САПР с помощью Groupdocs.Viewer для .NET. Groupdocs.Viewer — это мощный API для просмотра документов, который позволяет разработчикам отображать более 170 типов документов в своих приложениях без необходимости установки какого-либо внешнего программного обеспечения. В частности, мы сосредоточимся на рендеринге форматов САПР, таких как CF2, в различные выходные форматы, такие как HTML, JPG, PNG и PDF.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
- Visual Studio установлена в вашей системе.
-  Groupdocs.Viewer для .NET SDK. Вы можете скачать его с[здесь](https://releases.groupdocs.com/viewer/net/).
- Базовые знания языка программирования C#.
## Импортировать пространства имен
Сначала давайте импортируем необходимые пространства имен, необходимые для рендеринга форматов САПР.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Теперь давайте разобьем каждый пример на несколько этапов:
## Рендеринг CF2 в HTML
### Шаг 1. Определите выходной каталог, в котором будет сохранен визуализированный HTML.
```csharp
string outputDirectory = "Your Document Directory";
```
### Шаг 2. Определите формат пути к файлу для вывода HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Шаг 3. Инициализируйте объект просмотра и укажите входной файл CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // При необходимости установите дополнительные параметры рендеринга
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Рендеринг CF2 в JPG
### Шаг 1. Определите формат пути к файлу для вывода JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Шаг 2. Инициализируйте объект просмотра и укажите входной файл CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // При необходимости установите дополнительные параметры рендеринга
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Рендеринг CF2 в PNG

### Шаг 1. Определите формат пути к файлу для вывода PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Шаг 2. Инициализируйте объект просмотра и укажите входной файл CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // При необходимости установите дополнительные параметры рендеринга
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Рендеринг CF2 в PDF
### Шаг 1. Определите формат пути к файлу для вывода PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Шаг 2. Инициализируйте объект просмотра и укажите входной файл CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // При необходимости установите дополнительные параметры рендеринга
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Заключение
В этом руководстве мы научились визуализировать определенные форматы САПР, такие как CF2, с помощью Groupdocs.Viewer для .NET. Следуя пошаговому руководству, вы сможете легко интегрировать возможности рендеринга документов в свои приложения .NET.
## Часто задаваемые вопросы
### Может ли Groupdocs.Viewer отображать другие форматы САПР, кроме CF2?
Да, Groupdocs.Viewer поддерживает широкий спектр форматов САПР, включая DWG, DXF, DGN и другие.
### Подходит ли Groupdocs.Viewer для рендеринга документов в веб-приложениях?
Безусловно, Groupdocs.Viewer можно легко интегрировать в веб-приложения для отображения документов непосредственно в браузере.
### Требуются ли Groupdocs.Viewer какие-либо внешние зависимости для рендеринга?
Нет, Groupdocs.Viewer — это автономный API, не требующий каких-либо внешних зависимостей или установки программного обеспечения.
### Могу ли я настроить параметры рендеринга в соответствии со своими требованиями?
Да, Groupdocs.Viewer предоставляет различные параметры рендеринга, которые можно настроить в соответствии с вашими конкретными потребностями.
### Доступна ли пробная версия для Groupdocs.Viewer?
 Да, вы можете получить бесплатную пробную версию Groupdocs.Viewer на сайте[здесь](https://releases.groupdocs.com/).