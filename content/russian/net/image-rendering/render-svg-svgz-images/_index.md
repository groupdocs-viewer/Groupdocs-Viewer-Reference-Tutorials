---
title: Рендеринг изображений SVG и SVGZ
linktitle: Рендеринг изображений SVG и SVGZ
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как визуализировать изображения SVG и SVGZ с помощью GroupDocs.Viewer для .NET. Легко конвертируйте векторную графику в HTML, JPG, PNG и PDF.
type: docs
weight: 16
url: /ru/net/image-rendering/render-svg-svgz-images/
---
## Введение
В этом уроке мы покажем вам процесс рендеринга изображений SVG и SVGZ с помощью GroupDocs.Viewer для .NET. GroupDocs.Viewer для .NET — это мощный API рендеринга документов, который позволяет разработчикам визуализировать различные форматы документов в своих приложениях .NET. SVG и SVGZ — популярные форматы изображений, используемые для векторной графики, а с помощью GroupDocs.Viewer для .NET вы можете легко преобразовать их в различные выходные форматы, такие как HTML, JPG, PNG и PDF.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас установлены и настроены следующие необходимые компоненты:
1.  GroupDocs.Viewer для .NET: Загрузите и установите GroupDocs.Viewer для .NET с сайта[здесь](https://releases.groupdocs.com/viewer/net/).
2. Среда разработки. Убедитесь, что у вас есть работающая среда разработки для разработки .NET, например Visual Studio.
3. Образец файла SVGZ: подготовьте образец файла SVGZ для тестирования.

## Импортировать пространства имен
Прежде чем мы углубимся в код, давайте импортируем необходимые пространства имен:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Шаг 1. Преобразуйте SVGZ в HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Шаг 2. Преобразуйте SVGZ в JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Шаг 3. Преобразуйте SVGZ в PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Шаг 4. Преобразование SVGZ в PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Заключение
В этом уроке мы научились визуализировать изображения SVG и SVGZ с помощью GroupDocs.Viewer для .NET. Всего за несколько простых шагов вы можете конвертировать изображения SVGZ в различные выходные форматы, такие как HTML, JPG, PNG и PDF, делая их доступными и пригодными для просмотра в различных средах.
## Часто задаваемые вопросы
### Может ли GroupDocs.Viewer отображать другие форматы изображений?
Да, GroupDocs.Viewer поддерживает рендеринг различных форматов изображений, включая PNG, JPEG, BMP, TIFF, GIF и другие.
### Совместим ли GroupDocs.Viewer с .NET Core?
Да, GroupDocs.Viewer совместим как с .NET Framework, так и с .NET Core.
### Могу ли я настроить параметры рендеринга?
Да, GroupDocs.Viewer предоставляет широкие возможности рендеринга, позволяющие настроить вывод в соответствии с вашими требованиями.
### Требуются ли для GroupDocs.Viewer какие-либо сторонние зависимости?
Нет, GroupDocs.Viewer — это автономный API, не требующий каких-либо сторонних зависимостей для отображения документов.
### Доступна ли пробная версия для тестирования?
Да, вы можете скачать бесплатную пробную версию GroupDocs.Viewer с сайта[здесь](https://releases.groupdocs.com/) оценить его возможности перед покупкой.