---
"description": "Мастер рендеринга документов MS Project с GroupDocs.Viewer для .NET. Рендеринг заметок, настройка единиц времени и изучение различных форматов вывода без усилий."
"linktitle": "Отображение заметок и настройка единиц времени (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Отображение заметок и настройка единиц времени (MS Project)"
"url": "/ru/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# Отображение заметок и настройка единиц времени (MS Project)

## Введение
GroupDocs.Viewer для .NET — это мощный API для рендеринга документов, который позволяет разработчикам просматривать и манипулировать различными форматами документов в своих приложениях .NET. В этом руководстве мы сосредоточимся на рендеринге заметок и настройке единиц времени специально для документов MS Project.
## Предпосылки
Прежде чем начать, убедитесь, что у вас выполнены следующие предварительные условия:
1. GroupDocs.Viewer for .NET: Убедитесь, что вы загрузили и установили библиотеку GroupDocs.Viewer for .NET. Вы можете загрузить ее с [здесь](https://releases.groupdocs.com/viewer/net/).
2. Среда разработки: настройте предпочитаемую вами среду разработки с поддержкой .NET.
3. Документ MS Project: подготовьте образец документа MS Project для тестирования.
## Импорт пространств имен
Сначала давайте импортируем необходимые пространства имен, чтобы начать рендеринг документов MS Project:
## Шаг 1: Импорт пространств имен
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Теперь, когда мы импортировали необходимые пространства имен, давайте разберем каждый пример на несколько шагов для полного понимания.
## Преобразование документа MS Project в HTML
Чтобы преобразовать документ MS Project в формат HTML с включенными примечаниями, выполните следующие действия:
### Шаг 2: Задайте выходной каталог и формат файла
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Шаг 3: Инициализация объекта Viewer и настройка параметров
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Шаг 4: Преобразование документа в HTML
```csharp
viewer.View(options);
```
## Преобразование документа MS Project в форматы изображений
Вы также можете преобразовать документы MS Project в форматы изображений, такие как JPG и PNG. Вот как это сделать:
### Шаг 5: Задайте выходной каталог и формат файла для JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Шаг 6: Инициализация объекта Viewer и настройка параметров JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Шаг 7: Преобразовать документ в формат JPG
```csharp
viewer.View(options);
```
Повторите аналогичные шаги для рендеринга в PNG и другие форматы изображений.
## Преобразование документа MS Project в формат PDF
Чтобы преобразовать документ MS Project в формат PDF, выполните следующие действия:
### Шаг 8: Задайте выходной каталог и формат файла для PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Шаг 9: Инициализация объекта Viewer и настройка параметров PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Шаг 10: Преобразование документа в PDF
```csharp
viewer.View(options);
```

## Заключение
Поздравляем! Вы успешно научились визуализировать документы MS Project и настраивать единицы времени с помощью GroupDocs.Viewer для .NET. Используйте эти знания в своих проектах для улучшения возможностей просмотра документов.
## Часто задаваемые вопросы
### Могу ли я преобразовывать документы MS Project в другие форматы, помимо HTML, изображений и PDF?
Да, GroupDocs.Viewer для .NET поддерживает рендеринг в различные форматы, такие как DOCX, XLSX, PPTX и другие.
### Существует ли пробная версия GroupDocs.Viewer для .NET?
Да, вы можете получить бесплатную пробную версию от [здесь](https://releases.groupdocs.com/).
### Как получить временную лицензию на GroupDocs.Viewer для .NET?
Посещать [эта ссылка](https://purchase.groupdocs.com/temporary-license/) для получения временной лицензии.
### Где можно найти документацию по GroupDocs.Viewer для .NET?
См. документацию. [здесь](https://tutorials.groupdocs.com/viewer/net/).
### Где я могу обратиться за поддержкой или задать вопросы, связанные с GroupDocs.Viewer для .NET?
Вы можете посетить форум поддержки [здесь](https://forum.groupdocs.com/c/viewer/9).