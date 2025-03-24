---
title: Рендеринг примечаний и настройка единиц времени (MS Project)
linktitle: Рендеринг примечаний и настройка единиц времени (MS Project)
second_title: GroupDocs.Viewer .NET API
description: Освойте рендеринг документов MS Project с помощью GroupDocs.Viewer для .NET. Создавайте заметки, настраивайте единицы времени и без труда исследуйте различные форматы вывода.
weight: 11
url: /ru/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---

# Рендеринг примечаний и настройка единиц времени (MS Project)

## Введение
GroupDocs.Viewer для .NET — это мощный API рендеринга документов, который позволяет разработчикам просматривать различные форматы документов и манипулировать ими в своих приложениях .NET. В этом уроке мы сосредоточимся на отображении заметок и настройке единиц времени специально для документов MS Project.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1. GroupDocs.Viewer для .NET: убедитесь, что вы загрузили и установили библиотеку GroupDocs.Viewer для .NET. Вы можете скачать его с[здесь](https://releases.groupdocs.com/viewer/net/).
2. Среда разработки: настройте предпочитаемую среду разработки с поддержкой .NET.
3. Документ MS Project: подготовьте образец документа MS Project для тестирования.
## Импортировать пространства имен
Сначала давайте импортируем необходимые пространства имен, чтобы начать рендеринг документов MS Project:
## Шаг 1. Импортируйте пространства имен
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Теперь, когда мы импортировали необходимые пространства имен, давайте разобьем каждый пример на несколько шагов для более полного понимания.
## Рендеринг документа MS Project в HTML
Чтобы преобразовать документ MS Project в формат HTML с примечаниями, выполните следующие действия:
### Шаг 2. Установите выходной каталог и формат файла
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Шаг 3. Инициализация объекта просмотра и установка параметров
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Шаг 4. Преобразование документа в HTML
```csharp
viewer.View(options);
```
## Рендеринг документа MS Project в форматы изображений
Вы также можете преобразовать документы MS Project в форматы изображений, такие как JPG и PNG. Вот как:
### Шаг 5. Установите выходной каталог и формат файла для JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Шаг 6. Инициализируйте объект просмотра и установите параметры JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Шаг 7. Преобразование документа в JPG
```csharp
viewer.View(options);
```
Повторите аналогичные шаги для рендеринга в PNG и другие форматы изображений.
## Рендеринг документа MS Project в PDF
Чтобы преобразовать документ MS Project в формат PDF, выполните следующие действия:
### Шаг 8. Установите выходной каталог и формат файла для PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Шаг 9. Инициализируйте объект просмотра и установите параметры PDF
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
Поздравляем! Вы успешно научились визуализировать документы MS Project и настраивать единицы времени с помощью GroupDocs.Viewer для .NET. Включите эти знания в свои проекты, чтобы расширить возможности просмотра документов.
## Часто задаваемые вопросы
### Могу ли я преобразовать документы MS Project в другие форматы, кроме HTML, изображений и PDF?
Да, GroupDocs.Viewer для .NET поддерживает рендеринг в различные форматы, такие как DOCX, XLSX, PPTX и другие.
### Доступна ли пробная версия GroupDocs.Viewer для .NET?
 Да, вы можете получить бесплатную пробную версию на[здесь](https://releases.groupdocs.com/).
### Как получить временную лицензию на GroupDocs.Viewer для .NET?
 Посещать[эта ссылка](https://purchase.groupdocs.com/temporary-license/) получить временную лицензию.
### Где я могу найти документацию для GroupDocs.Viewer для .NET?
 Обратитесь к документации[здесь](https://tutorials.groupdocs.com/viewer/net/).
### Где я могу обратиться за поддержкой или задать вопросы, связанные с GroupDocs.Viewer для .NET?
 Вы можете посетить форум поддержки[здесь](https://forum.groupdocs.com/c/viewer/9).