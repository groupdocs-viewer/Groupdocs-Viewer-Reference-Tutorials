---
title: Исключить шрифты из отображаемого HTML
linktitle: Исключить шрифты из отображаемого HTML
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как исключить шрифты из отображаемого HTML с помощью GroupDocs.Viewer для .NET. Следуйте этому пошаговому руководству, чтобы обеспечить бесперебойное отображение документов.
weight: 10
url: /ru/net/rendering-documents-html/exclude-fonts-html/
---

# Исключить шрифты из отображаемого HTML

## Введение
GroupDocs.Viewer для .NET — это мощная библиотека рендеринга документов, которая позволяет разработчикам отображать более 50 форматов документов в своих .NET-приложениях без необходимости использования внешних зависимостей. В этом руководстве мы сосредоточимся на конкретной функции GroupDocs.Viewer: исключении шрифтов из отображаемого вывода HTML. 
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
1. Базовое понимание разработки на C# и .NET.
2.  GroupDocs.Viewer для .NET установлен. Вы можете скачать его с[здесь](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio или любая другая IDE для разработки на C#.

## Импортировать пространства имен
Обязательно включите в свой код C# необходимые пространства имен:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Шаг 1. Определите выходной каталог
Настройте каталог, в котором вы хотите сохранять обработанные HTML-файлы.
```csharp
string outputDirectory = "Your Document Directory";
```
## Шаг 2. Определите формат пути к файлу подкачки
Укажите формат путей к файлам отдельных страниц визуализированного документа.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Шаг 3. Инициализация объекта просмотра
Создайте экземпляр объекта Viewer с документом, который вы хотите визуализировать.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Ваш код находится здесь
}
```
## Шаг 4. Установите параметры просмотра HTML
Определите параметры рендеринга HTML, включая формат встроенных ресурсов и исключаемые шрифты.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Шаг 5: Рендеринг документа
Передайте параметры просмотра HTML объекту Viewer для визуализации документа.
```csharp
viewer.View(options);
```
## Шаг 6: Расположение выходного визуализированного документа
Сообщите пользователю о месте, где сохраняются обработанные HTML-файлы.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Заключение
В этом руководстве мы узнали, как использовать GroupDocs.Viewer для .NET для исключения шрифтов из отображаемого вывода HTML. Следуя шагам, описанным выше, вы можете настроить процесс рендеринга в соответствии с вашими конкретными требованиями, обеспечивая оптимальное отображение документов в ваших приложениях.
## Часто задаваемые вопросы
### Могу ли я исключить несколько шрифтов из отображаемого HTML?
 Да, вы можете добавить несколько названий шрифтов в`FontsToExclude` список в параметрах просмотра HTML.
### Совместим ли GroupDocs.Viewer со всеми платформами .NET?
Да, GroupDocs.Viewer поддерживает .NET Framework 4.6.1 и выше.
### Могу ли я визуализировать документы из удаленных мест хранения?
Да, GroupDocs.Viewer поддерживает рендеринг документов из локального хранилища, а также из удаленных хранилищ и потоков.
### Поддерживает ли GroupDocs.Viewer адаптивный дизайн для вывода HTML?
Да, вы можете включить адаптивный рендеринг, соответствующим образом настроив параметры просмотра HTML.
### Доступна ли техническая поддержка для GroupDocs.Viewer?
 Да, вы можете обращаться за помощью и участвовать в обсуждениях по[Форум GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).