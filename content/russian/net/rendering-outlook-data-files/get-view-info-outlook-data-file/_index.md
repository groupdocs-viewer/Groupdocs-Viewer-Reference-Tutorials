---
title: Получить информацию о просмотре файлов данных Outlook (PST, OST)
linktitle: Получить информацию о просмотре файлов данных Outlook (PST, OST)
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как извлечь информацию о представлении из файлов данных Outlook (PST, OST) с помощью GroupDocs.Viewer для .NET. Расширьте свои возможности управления документами без особых усилий.
weight: 10
url: /ru/net/rendering-outlook-data-files/get-view-info-outlook-data-file/
---

# Получить информацию о просмотре файлов данных Outlook (PST, OST)

## Введение
В области управления документами и просмотра GroupDocs.Viewer для .NET представляет собой мощный инструмент, особенно когда речь идет об обработке файлов данных Outlook (PST, OST). В этом уроке мы шаг за шагом углубимся в процесс извлечения информации о представлении для этих файлов.
## Предварительные условия
Прежде чем мы приступим к этому руководству, убедитесь, что у вас есть следующие предварительные условия:
### 1. Установка GroupDocs.Viewer для .NET.
 Во-первых, вам необходимо установить GroupDocs.Viewer для .NET в вашей среде разработки. Вы можете скачать необходимый пакет с сайта[GroupDocs.Viewer для веб-сайта .NET](https://releases.groupdocs.com/viewer/net/).
### 2. Знакомство с языком программирования C#.
Базовые знания языка программирования C# необходимы для понимания и реализации предоставленных примеров кода.
### 3. Файлы данных Outlook (PST, OST)
Убедитесь, что у вас есть файлы данных Outlook (PST, OST) для целей тестирования. Вы можете получить образцы файлов из различных источников или использовать свои собственные файлы данных.

## Импортировать пространства имен
Прежде чем углубиться в код, давайте убедимся, что мы импортировали необходимые пространства имен:
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Теперь давайте разобьем приведенный пример на несколько этапов:
## Шаг 1. Создайте экземпляр объекта просмотра
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Здесь мы инициализируем объект Viewer с путем к файлу данных Outlook (OST), указанному в качестве аргумента.
## Шаг 2. Настройте параметры просмотра информации
```csharp
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
Мы настраиваем параметры для получения информации о просмотре. В данном случае мы выбираем просмотр HTML.
## Шаг 3. Получение информации о просмотре Outlook
```csharp
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```
Эта строка извлекает информацию о просмотре файла данных Outlook.
## Шаг 4. Отображение типа файла и количества страниц
```csharp
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```
Мы распечатываем тип файла и количество страниц в файле данных Outlook.
## Шаг 5. Перебор папок
```csharp
foreach (string folder in rootFolderInfo.Folders)
    Console.WriteLine(folder);
```
Этот цикл перебирает папки, содержащиеся в файле данных Outlook, и печатает их имена.
## Шаг 6: Завершите получение
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
Отображается сообщение, указывающее на успешное получение информации о просмотре.

## Заключение
GroupDocs.Viewer для .NET предоставляет простое решение для извлечения информации о представлении из файлов данных Outlook (PST, OST). Выполнив шаги, описанные в этом руководстве, вы сможете легко получить ценную информацию об этих файлах для расширенного управления документами.
## Часто задаваемые вопросы
### Совместим ли GroupDocs.Viewer для .NET с различными версиями файлов данных Outlook?
Да, GroupDocs.Viewer для .NET поддерживает различные версии файлов данных Outlook, обеспечивая совместимость в различных средах.
### Могу ли я настроить параметры просмотра файлов данных Outlook с помощью GroupDocs.Viewer для .NET?
Абсолютно! GroupDocs.Viewer для .NET предлагает широкие возможности настройки, позволяющие адаптировать просмотр в соответствии с вашими требованиями.
### Поддерживает ли GroupDocs.Viewer для .NET другие форматы файлов, кроме файлов данных Outlook?
Да, GroupDocs.Viewer для .NET поддерживает широкий спектр форматов файлов, включая, помимо прочего, PDF, DOCX, XLSX и другие.
### Доступна ли бесплатная пробная версия GroupDocs.Viewer для .NET?
 Да, вы можете получить доступ к бесплатной пробной версии GroupDocs.Viewer для .NET на веб-сайте:[Бесплатная пробная версия](https://releases.groupdocs.com/).
### Где я могу найти дополнительную поддержку или помощь по GroupDocs.Viewer для .NET?
 Если у вас есть какие-либо вопросы или помощь, вы можете посетить форум поддержки GroupDocs.Viewer for .NET:[Поддерживать](https://forum.groupdocs.com/c/viewer/9).