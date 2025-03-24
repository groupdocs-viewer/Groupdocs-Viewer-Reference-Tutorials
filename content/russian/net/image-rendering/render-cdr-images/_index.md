---
title: Рендеринг изображений CDR
linktitle: Рендеринг изображений CDR
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как визуализировать изображения CDR в HTML, JPG, PNG и PDF с помощью GroupDocs.Viewer для .NET. С помощью этого руководства легко конвертируйте файлы CorelDRAW.
weight: 12
url: /ru/net/image-rendering/render-cdr-images/
---
## Введение
В этом руководстве мы покажем вам процесс рендеринга изображений CDR (CorelDRAW) с помощью GroupDocs.Viewer для .NET. CDR — это формат файла, в первую очередь связанный с CorelDRAW, редактором векторной графики. С помощью GroupDocs.Viewer вы можете легко конвертировать файлы CDR в различные форматы, такие как HTML, JPG, PNG и PDF.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:
1.  GroupDocs.Viewer для .NET: убедитесь, что вы установили GroupDocs.Viewer для .NET. Вы можете скачать его с[здесь](https://releases.groupdocs.com/viewer/net/).
2. Каталог документов: подготовьте каталог, в котором вы хотите сохранить визуализированные изображения.
3. Базовые знания C#: Для понимания примеров кода необходимо знание языка программирования C#.
## Импортировать пространства имен
Прежде чем углубляться в примеры кода, импортируйте необходимые пространства имен в файл C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Теперь давайте разобьем каждый пример на несколько этапов:
## Рендеринг в HTML
1. Определите выходной каталог, в котором вы хотите сохранить обработанные HTML-файлы:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Укажите формат пути к файлу HTML-файлов:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Используйте класс Viewer для преобразования файла CDR в HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Рендеринг в JPG
1. Определите формат пути к файлам JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Используйте класс Viewer для преобразования файла CDR в JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Рендеринг в PNG
1. Определите формат пути к файлам PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Используйте класс Viewer для преобразования файла CDR в PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Рендеринг в PDF
1. Определите формат пути к файлу PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Используйте класс Viewer для преобразования файла CDR в PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  При желании вы можете указать параметры рендеринга или отрисовать определенные страницы, передав дополнительные параметры в метод`viewer.View()` метод.
## Заключение
Рендеринг изображений CDR в различные форматы, такие как HTML, JPG, PNG и PDF, с помощью GroupDocs.Viewer для .NET — это простой процесс. Следуя инструкциям, описанным в этом руководстве, вы сможете эффективно конвертировать файлы CDR в различные форматы в соответствии с вашими требованиями.
## Часто задаваемые вопросы
### Совместим ли GroupDocs.Viewer для .NET со всеми версиями файлов CDR?
GroupDocs.Viewer для .NET поддерживает рендеринг файлов CDR, созданных различными версиями CorelDRAW.
### Могу ли я настроить вывод визуализированных файлов?
Да, GroupDocs.Viewer для .NET предоставляет различные параметры для настройки вывода, например настройку качества изображения, установку водяных знаков и т. д.
### Требует ли GroupDocs.Viewer для .NET каких-либо внешних зависимостей?
Нет, GroupDocs.Viewer для .NET — это автономная библиотека, не требующая каких-либо внешних зависимостей для отображения документов.
### Доступна ли пробная версия GroupDocs.Viewer для .NET?
 Да, вы можете загрузить бесплатную пробную версию GroupDocs.Viewer для .NET с сайта[здесь](https://releases.groupdocs.com/).
### Где я могу получить поддержку GroupDocs.Viewer для .NET?
 Вы можете получить поддержку на форуме сообщества GroupDocs.Viewer.[здесь](https://forum.groupdocs.com/c/viewer/9).