---
title: Добавить водяной знак в документ
linktitle: Добавить водяной знак в документ
second_title: GroupDocs.Viewer .NET API
description: Узнайте, как легко добавлять водяные знаки в документы с помощью GroupDocs.Viewer для .NET. Повысьте безопасность документов и брендинг с помощью этого простого руководства.
type: docs
weight: 10
url: /ru/net/rendering-options/add-watermark/
---
## Введение
В современную цифровую эпоху беспрепятственное управление и просмотр документов различных форматов является необходимостью как для многих предприятий, так и для частных лиц. К счастью, с такими инструментами, как GroupDocs.Viewer для .NET, обработка документов становится проще простого. Эта мощная библиотека .NET позволяет разработчикам легко интегрировать функции просмотра документов в свои приложения, позволяя пользователям просматривать документы без использования исходного программного обеспечения, в котором они были созданы.
## Предварительные условия
Прежде чем приступить к использованию GroupDocs.Viewer для .NET для добавления водяных знаков в документы, убедитесь, что у вас есть следующее:
1. Настройка среды: Настройте среду разработки с установленным .NET Framework или .NET Core.
2.  GroupDocs.Viewer для .NET: Загрузите и установите библиотеку GroupDocs.Viewer для .NET из библиотеки[страница загрузки](https://releases.groupdocs.com/viewer/net/).
3. Файлы документов: подготовьте файлы документов, с которыми вы хотите работать, например DOCX, PDF или другие.
4. Базовые знания C#: Для реализации примеров кода необходимо знание языка программирования C#.

## Импортировать пространства имен
Прежде чем добавлять водяные знаки в документы с помощью GroupDocs.Viewer для .NET, обязательно импортируйте необходимые пространства имен в свой код C#. Этот шаг позволяет вам беспрепятственно получить доступ к классам и методам, предоставляемым библиотекой.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Теперь давайте рассмотрим процесс добавления водяного знака в документ с помощью GroupDocs.Viewer для .NET. Выполните следующие действия, чтобы легко интегрировать функцию водяных знаков в ваше приложение.
## Шаг 1. Установите выходной каталог
```csharp
string outputDirectory = "Your Document Directory";
```
Укажите каталог, в котором вы хотите сохранять выходные файлы после применения водяного знака.
## Шаг 2. Определите формат пути к файлу подкачки
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Установите формат путей к файлам отображаемых страниц. В этом примере будут созданы HTML-файлы с номерами страниц.
## Шаг 3. Создание экземпляра объекта просмотра
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Код продолжается на следующем шаге...
}
```
Создайте экземпляр класса Viewer, передав путь к файлу документа в качестве параметра. В этом примере мы используем образец файла DOCX.
## Шаг 4. Настройте параметры просмотра HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Настройте параметры просмотра HTML, включая текст водяного знака, который вы хотите добавить в документ.
## Шаг 5. Просмотр документа с водяным знаком
```csharp
viewer.View(options);
```
Вызовите метод View объекта Viewer, передав настроенные параметры. Это отобразит документ с указанным водяным знаком.
## Шаг 6. Отображение пути к выходному каталогу
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Сообщите пользователю об успешном рендеринге документа и укажите каталог, в котором сохраняются выходные файлы.

## Заключение
GroupDocs.Viewer для .NET предоставляет удобный способ программного добавления водяных знаков в документы. Следуя инструкциям, описанным в этом руководстве, вы сможете легко интегрировать функцию водяных знаков в свои приложения .NET, повысив безопасность документов и брендинг.
## Часто задаваемые вопросы
### Могу ли я настроить внешний вид водяного знака?
Да, вы можете настроить различные свойства водяного знака, такие как текст, шрифт, цвет, размер и положение.
### Поддерживает ли GroupDocs.Viewer просмотр документов из удаленных источников?
Да, GroupDocs.Viewer поддерживает просмотр документов из локального хранилища, а также удаленных URL-адресов.
### Доступна ли пробная версия GroupDocs.Viewer для .NET?
Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.groupdocs.com/).
### Могу ли я добавить водяные знаки на несколько страниц документа?
Разумеется, GroupDocs.Viewer позволяет добавлять водяные знаки на отдельные страницы или на все страницы документа.
### Как я могу получить поддержку или помощь, если у меня возникнут какие-либо проблемы?
 Вы можете обратиться за помощью и поддержкой на форумы сообщества GroupDocs.[здесь](https://forum.groupdocs.com/c/viewer/9).