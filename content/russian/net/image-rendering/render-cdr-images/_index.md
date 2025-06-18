---
"description": "Узнайте, как преобразовать изображения CDR в HTML, JPG, PNG и PDF с помощью GroupDocs.Viewer для .NET. Легко конвертируйте файлы CorelDRAW с помощью этого руководства."
"linktitle": "Рендеринг изображений CDR"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Рендеринг изображений CDR"
"url": "/ru/net/image-rendering/render-cdr-images/"
"weight": 12
---

# Рендеринг изображений CDR

## Введение
В этом уроке мы проведем вас через процесс рендеринга изображений CDR (CorelDRAW) с помощью GroupDocs.Viewer для .NET. CDR — это формат файла, в первую очередь связанный с CorelDRAW, векторным графическим редактором. С помощью GroupDocs.Viewer вы можете легко конвертировать файлы CDR в различные форматы, такие как HTML, JPG, PNG и PDF.

![Рендеринг изображений CDR с помощью GroupDocs.Viewer для .NET](/viewer/image-rendering/render-cdr-images.png)

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:
1. GroupDocs.Viewer для .NET: Убедитесь, что у вас установлен GroupDocs.Viewer для .NET. Вы можете загрузить его с [здесь](https://releases.groupdocs.com/viewer/net/).
2. Каталог документов: подготовьте каталог, в котором вы хотите сохранить обработанные изображения.
3. Базовые знания C#: для понимания примеров кода необходимо знакомство с языком программирования C#.
## Импорт пространств имен
Прежде чем углубляться в примеры кода, импортируйте необходимые пространства имен в свой файл C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Теперь давайте разберем каждый пример на несколько шагов:
## Рендеринг в HTML
1. Определите выходной каталог, в котором вы хотите сохранить обработанные HTML-файлы:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Укажите формат пути к файлу для HTML-файлов:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Используйте класс Viewer для преобразования CDR-файла в HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Рендеринг в JPG
1. Определите формат пути к файлу для файлов JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Используйте класс Viewer для рендеринга CDR-файла в JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Рендеринг в PNG
1. Определите формат пути к файлу для файлов PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Используйте класс Viewer для рендеринга CDR-файла в PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Рендеринг в PDF
1. Определите формат пути к файлу для PDF:
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
3. При желании вы можете указать параметры рендеринга или рендерить определенные страницы, передав дополнительные параметры в `viewer.View()` метод.
## Заключение
Рендеринг изображений CDR в различные форматы, такие как HTML, JPG, PNG и PDF, с помощью GroupDocs.Viewer для .NET — это простой процесс. Следуя шагам, описанным в этом руководстве, вы сможете эффективно конвертировать файлы CDR в различные форматы в зависимости от ваших требований.
## Часто задаваемые вопросы
### Совместим ли GroupDocs.Viewer для .NET со всеми версиями файлов CDR?
GroupDocs.Viewer для .NET поддерживает рендеринг файлов CDR, созданных различными версиями CorelDRAW.
### Могу ли я настроить вывод обработанных файлов?
Да, GroupDocs.Viewer для .NET предоставляет различные возможности настройки вывода, такие как настройка качества изображения, установка водяного знака и т. д.
### Требуются ли для GroupDocs.Viewer for .NET какие-либо внешние зависимости?
Нет, GroupDocs.Viewer для .NET — это автономная библиотека, не требующая никаких внешних зависимостей для рендеринга документов.
### Существует ли пробная версия GroupDocs.Viewer для .NET?
Да, вы можете загрузить бесплатную пробную версию GroupDocs.Viewer для .NET с сайта [здесь](https://releases.groupdocs.com/).
### Где я могу получить поддержку по GroupDocs.Viewer для .NET?
Вы можете получить поддержку на форуме сообщества GroupDocs.Viewer. [здесь](https://forum.groupdocs.com/c/viewer/9).