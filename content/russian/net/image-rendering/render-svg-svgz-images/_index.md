---
"description": "Узнайте, как визуализировать изображения SVG и SVGZ с помощью GroupDocs.Viewer для .NET. Конвертируйте векторную графику в HTML, JPG, PNG и PDF без усилий."
"linktitle": "Рендеринг изображений SVG и SVGZ"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Рендеринг изображений SVG и SVGZ"
"url": "/ru/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# Рендеринг изображений SVG и SVGZ

## Введение
В этом уроке мы проведем вас через процесс рендеринга изображений SVG и SVGZ с помощью GroupDocs.Viewer для .NET. GroupDocs.Viewer для .NET — это мощный API рендеринга документов, который позволяет разработчикам рендерить различные форматы документов в своих приложениях .NET. SVG и SVGZ — это популярные форматы изображений, используемые для векторной графики, и с помощью GroupDocs.Viewer для .NET вы можете легко рендерить их в различные выходные форматы, такие как HTML, JPG, PNG и PDF.

![Рендеринг изображений SVG и SVGZ с помощью GroupDocs.Viewer для .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Предпосылки
Прежде чем начать, убедитесь, что у вас установлены и настроены следующие компоненты:
1. GroupDocs.Viewer для .NET: Загрузите и установите GroupDocs.Viewer для .NET с сайта [здесь](https://releases.groupdocs.com/viewer/net/).
2. Среда разработки: убедитесь, что у вас есть рабочая среда разработки для .NET-разработки, например Visual Studio.
3. Образец файла SVGZ: подготовьте образец файла SVGZ для тестирования.

## Импорт пространств имен
Прежде чем погрузиться в код, давайте импортируем необходимые пространства имен:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Шаг 1: Рендеринг SVGZ в HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Шаг 2: Рендеринг SVGZ в JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Шаг 3: Рендеринг SVGZ в PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Шаг 4: Преобразование SVGZ в PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Заключение
В этом уроке мы узнали, как визуализировать изображения SVG и SVGZ с помощью GroupDocs.Viewer для .NET. Всего за несколько простых шагов вы можете преобразовать изображения SVGZ в различные выходные форматы, такие как HTML, JPG, PNG и PDF, сделав их доступными и просматриваемыми в различных средах.
## Часто задаваемые вопросы
### Может ли GroupDocs.Viewer отображать другие форматы изображений?
Да, GroupDocs.Viewer поддерживает рендеринг различных форматов изображений, включая PNG, JPEG, BMP, TIFF, GIF и другие.
### Совместим ли GroupDocs.Viewer с .NET Core?
Да, GroupDocs.Viewer совместим как с .NET Framework, так и с .NET Core.
### Могу ли я настроить параметры рендеринга?
Да, GroupDocs.Viewer предоставляет обширные возможности рендеринга, позволяя вам настраивать вывод в соответствии с вашими требованиями.
### Требуются ли для GroupDocs.Viewer какие-либо сторонние зависимости?
Нет, GroupDocs.Viewer — это автономный API, не требующий никаких сторонних зависимостей для рендеринга документов.
### Есть ли пробная версия для тестирования?
Да, вы можете загрузить бесплатную пробную версию GroupDocs.Viewer с сайта [здесь](https://releases.groupdocs.com/) чтобы оценить его характеристики перед покупкой.