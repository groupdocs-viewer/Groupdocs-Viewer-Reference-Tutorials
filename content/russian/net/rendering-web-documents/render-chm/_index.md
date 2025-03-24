---
title: Рендеринг файлов CHM
linktitle: Рендеринг файлов CHM
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как отображать файлы CHM в .NET с помощью GroupDocs.Viewer. Легко конвертируйте CHM в форматы HTML, JPG, PNG и PDF.
weight: 10
url: /ru/net/rendering-web-documents/render-chm/
---

# Рендеринг файлов CHM

## Введение
В этом руководстве мы рассмотрим, как отображать файлы CHM (скомпилированная HTML-справка) с помощью GroupDocs.Viewer для .NET. GroupDocs.Viewer для .NET — это мощный API рендеринга документов, который позволяет разработчикам отображать более 170 типов документов в своих приложениях .NET, не требуя установки какого-либо внешнего программного обеспечения.

## Предварительные условия

Прежде чем мы углубимся в рендеринг файлов CHM, убедитесь, что у вас есть следующие предварительные условия:

### Установка GroupDocs.Viewer для .NET

 Для начала вам необходимо установить GroupDocs.Viewer для .NET. Вы можете скачать библиотеку с сайта[Веб-сайт ГруппДокс](https://releases.groupdocs.com/viewer/net/) или установите его через диспетчер пакетов NuGet, выполнив следующую команду в консоли диспетчера пакетов:

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

## Шаг 1. Определите выходной каталог

Определите каталог, в котором вы хотите сохранить визуализированные файлы:

```csharp
string outputDirectory = "Your Document Directory";
```

## Шаг 2. Рендеринг в HTML

Чтобы преобразовать файлы CHM в HTML, используйте следующий фрагмент кода:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Установите значение true, чтобы преобразовать все содержимое CHM на одну страницу.

    viewer.View(options); //Конвертировать все страницы
}
```

## Шаг 3. Рендеринг в JPG

Чтобы преобразовать файлы CHM в изображения JPG, используйте следующий фрагмент кода:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Конвертировать только страницы 1, 2, 3
}
```

## Шаг 4. Рендеринг в PNG

Чтобы преобразовать файлы CHM в изображения PNG, используйте следующий фрагмент кода:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Конвертировать только страницы 1, 2, 3
}
```

## Шаг 5. Рендеринг в PDF

Чтобы преобразовать файлы CHM в документ PDF, используйте следующий фрагмент кода:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Конвертировать все страницы
}
```

## Шаг 6: Проверьте вывод

После завершения процесса рендеринга проверьте указанный выходной каталог на наличие визуализированных файлов:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Заключение

Отображение файлов CHM с помощью GroupDocs.Viewer для .NET — это простой процесс. Следуя инструкциям, описанным в этом руководстве, вы сможете эффективно конвертировать документы CHM в различные форматы, такие как HTML, изображения (JPG, PNG) и PDF, в ваших приложениях .NET.

## Часто задаваемые вопросы

### Вопрос 1. Может ли GroupDocs.Viewer отображать документы других форматов, кроме CHM?

О1: Да, GroupDocs.Viewer поддерживает рендеринг более 170 форматов документов, включая PDF, DOCX, XLSX, PPTX и другие.

### Вопрос 2. Совместим ли GroupDocs.Viewer с .NET Core?

О2: Да, GroupDocs.Viewer поддерживает .NET Core в дополнение к традиционной .NET Framework.

### Вопрос 3. Могу ли я настроить параметры рендеринга для разных выходных форматов?

О3: Да, GroupDocs.Viewer предоставляет различные параметры для настройки процесса рендеринга, такие как указание номеров страниц, настройка качества изображения и настройка путей вывода.

### Вопрос 4. Требуются ли GroupDocs.Viewer какие-либо внешние зависимости для отображения документов?

О4: Нет, GroupDocs.Viewer — это автономная библиотека, не требующая каких-либо внешних зависимостей или установки стороннего программного обеспечения.

### Вопрос 5. Доступна ли бесплатная пробная версия GroupDocs.Viewer?

 О5: Да, вы можете воспользоваться бесплатной пробной версией GroupDocs.Viewer, посетив[Веб-сайт](https://releases.groupdocs.com/).