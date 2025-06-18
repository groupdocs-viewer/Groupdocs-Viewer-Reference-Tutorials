---
"description": "Узнайте, как визуализировать файлы CHM в .NET с помощью GroupDocs.Viewer. Конвертируйте CHM в форматы HTML, JPG, PNG и PDF без усилий."
"linktitle": "Рендеринг файлов CHM"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Рендеринг файлов CHM"
"url": "/ru/net/rendering-web-documents/render-chm/"
"weight": 10
---

# Рендеринг файлов CHM

## Введение
В этом уроке мы рассмотрим, как визуализировать файлы CHM (Compiled HTML Help) с помощью GroupDocs.Viewer для .NET. GroupDocs.Viewer для .NET — это мощный API визуализации документов, который позволяет разработчикам отображать более 170 типов документов в своих приложениях .NET без необходимости установки какого-либо внешнего программного обеспечения.

## Предпосылки

Прежде чем приступить к рендерингу CHM-файлов, убедитесь, что выполнены следующие предварительные условия:

### Установка GroupDocs.Viewer для .NET

Для начала вам необходимо установить GroupDocs.Viewer for .NET. Скачать библиотеку можно с сайта [Сайт GroupDocs](https://releases.groupdocs.com/viewer/net/) или установите его через диспетчер пакетов NuGet, выполнив следующую команду в консоли диспетчера пакетов:

```bash
Install-Package GroupDocs.Viewer
```

## Импорт пространств имен

Обязательно импортируйте необходимые пространства имен в свой проект:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Теперь давайте разобьем процесс рендеринга на несколько этапов:

## Шаг 1: Определите выходной каталог

Определите каталог, в котором вы хотите сохранить обработанные файлы:

```csharp
string outputDirectory = "Your Document Directory";
```

## Шаг 2: Рендеринг в HTML

Для преобразования CHM-файлов в HTML используйте следующий фрагмент кода:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Установите значение true, чтобы преобразовать весь контент CHM в одну страницу.

    viewer.View(options); // Конвертировать все страницы
}
```

## Шаг 3: Рендеринг в JPG

Для преобразования файлов CHM в изображения JPG используйте следующий фрагмент кода:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Конвертировать только страницы 1, 2, 3
}
```

## Шаг 4: Рендеринг в PNG

Для преобразования файлов CHM в изображения PNG используйте следующий фрагмент кода:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Конвертировать только страницы 1, 2, 3
}
```

## Шаг 5: Преобразование в PDF

Для преобразования CHM-файлов в PDF-документ используйте следующий фрагмент кода:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Конвертировать все страницы
}
```

## Шаг 6: Проверьте вывод

После завершения процесса рендеринга проверьте указанный выходной каталог на наличие отрендеренных файлов:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Заключение

Рендеринг файлов CHM с помощью GroupDocs.Viewer для .NET — это простой процесс. Следуя шагам, описанным в этом руководстве, вы сможете эффективно преобразовывать документы CHM в различные форматы, такие как HTML, изображения (JPG, PNG) и PDF в ваших приложениях .NET.

## Часто задаваемые вопросы

### В1: Может ли GroupDocs.Viewer отображать другие форматы документов, помимо CHM?

A1: Да, GroupDocs.Viewer поддерживает рендеринг более 170 форматов документов, включая PDF, DOCX, XLSX, PPTX и другие.

### В2: Совместим ли GroupDocs.Viewer с .NET Core?

A2: Да, GroupDocs.Viewer поддерживает .NET Core в дополнение к традиционному .NET Framework.

### В3: Могу ли я настроить параметры рендеринга для различных форматов вывода?

A3: Да, GroupDocs.Viewer предоставляет различные возможности для настройки процесса рендеринга, такие как указание номеров страниц, настройка качества изображения и настройка выходных путей.

### В4: Требуются ли GroupDocs.Viewer какие-либо внешние зависимости для рендеринга документов?

A4: Нет, GroupDocs.Viewer — это автономная библиотека, не требующая никаких внешних зависимостей или установки стороннего программного обеспечения.

### В5: Существует ли бесплатная пробная версия GroupDocs.Viewer?

A5: Да, вы можете воспользоваться бесплатной пробной версией GroupDocs.Viewer, посетив [веб-сайт](https://releases.groupdocs.com/).