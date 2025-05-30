---
title: Установите формат даты и времени и смещение часового пояса (электронная почта)
linktitle: Установите формат даты и времени и смещение часового пояса (электронная почта)
second_title: GroupDocs.Viewer .NET API
description: Легко интегрируйте GroupDocs.Viewer для .NET в свои приложения, чтобы получить мощные возможности просмотра документов. Улучшите взаимодействие с пользователем с помощью настраиваемых параметров.
weight: 11
url: /ru/net/rendering-email-messages/set-date-time-format-offset-email/
---

# Установите формат даты и времени и смещение часового пояса (электронная почта)


## Введение
GroupDocs.Viewer для .NET — это мощный инструмент, который позволяет разработчикам легко интегрировать возможности просмотра документов в свои .NET-приложения. С помощью GroupDocs.Viewer вы можете отображать широкий спектр форматов документов, включая PDF-файлы, документы Microsoft Office, изображения и многое другое, непосредственно в вашем приложении, без необходимости использования каких-либо внешних плагинов или средств просмотра. В этом подробном руководстве мы проведем вас через процесс настройки GroupDocs.Viewer для .NET, изучим его функции и продемонстрируем, как эффективно использовать его для расширения возможностей просмотра документов вашего приложения.
## Предварительные условия
Прежде чем приступить к изучению этого руководства, убедитесь, что у вас настроены следующие предварительные условия:
1. Visual Studio: убедитесь, что в вашей системе установлена Visual Studio. GroupDocs.Viewer для .NET полностью совместим с Visual Studio, что обеспечивает плавную интеграцию в ваши проекты .NET.
2.  GroupDocs.Viewer для .NET: Загрузите и установите GroupDocs.Viewer для .NET с сайта[ссылка для скачивания](https://releases.groupdocs.com/viewer/net/). Следуйте инструкциям по установке, чтобы настроить библиотеку в вашей среде разработки.
3. .NET Framework: убедитесь, что у вас установлена соответствующая версия .NET Framework. GroupDocs.Viewer для .NET поддерживает различные версии .NET Framework, включая .NET Core и .NET Standard.

## Импортировать пространства имен
Чтобы эффективно использовать GroupDocs.Viewer для .NET, вам необходимо импортировать необходимые пространства имен в ваш проект. Выполните следующие действия, чтобы импортировать необходимые пространства имен:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Давайте разобьем приведенный пример на несколько шагов, чтобы понять каждый компонент и его функциональность.
## Шаг 1. Установите выходной каталог и путь к файлу
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
На этом этапе мы определяем выходной каталог, в котором будет сохранен визуализированный документ, и указываем путь к выходному HTML-файлу.
## Шаг 2. Создание экземпляра объекта просмотра
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Здесь мы создаем новый экземпляр`Viewer` класс, передавая путь к просматриваемому документу (в данном случае образец файла EML) в качестве параметра.
## Шаг 3. Определите параметры просмотра HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
На этом этапе мы настраиваем параметры представления HTML для рендеринга документа, указывая путь к выходному файлу для визуализированного HTML-документа.
## Шаг 4. Установите формат даты и времени и смещение часового пояса.
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Здесь мы настраиваем формат даты и времени для сообщений электронной почты и устанавливаем смещение часового пояса в соответствии с желаемым часовым поясом.
## Шаг 5: Рендеринг документа
```csharp
viewer.View(options);
```
 Наконец, мы вызываем`View` метод`Viewer` объект, передавая настроенные параметры представления HTML для преобразования документа в формат HTML.
## Шаг 6: Отображение выходного каталога
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
На этом шаге просто отображается сообщение, указывающее на успешную визуализацию документа, и указывается путь к выходному каталогу, в котором находится обработанный HTML-документ.

## Заключение
GroupDocs.Viewer для .NET предлагает надежное решение для интеграции возможностей просмотра документов в ваши .NET-приложения. Следуя инструкциям, описанным в этом руководстве, вы можете легко настроить GroupDocs.Viewer, импортировать необходимые пространства имен и использовать его функции для отображения документов с настраиваемыми параметрами. Независимо от того, работаете ли вы с PDF-файлами, документами Microsoft Office или другими форматами, GroupDocs.Viewer упрощает процесс просмотра документов, повышая удобство использования ваших приложений.
## Часто задаваемые вопросы
### Совместим ли GroupDocs.Viewer с .NET Core?
Да, GroupDocs.Viewer для .NET поддерживает .NET Core, обеспечивая кроссплатформенную совместимость ваших приложений.
### Могу ли я настроить внешний вид отображаемых документов?
Абсолютно! GroupDocs.Viewer предоставляет различные параметры настройки, включая уровни масштабирования, поворот страниц и многое другое, чтобы настроить просмотр в соответствии с вашими предпочтениями.
### Доступна ли пробная версия для тестирования?
 Да, вы можете загрузить бесплатную пробную версию GroupDocs.Viewer для .NET с сайта[ссылка на сайт](https://releases.groupdocs.com/viewer/net/) оценить его возможности перед покупкой.
### Поддерживает ли GroupDocs.Viewer отображение документов, защищенных паролем?
Да, GroupDocs.Viewer имеет встроенную поддержку отображения документов, защищенных паролем, что обеспечивает безопасный просмотр документов в ваших приложениях.
### Где я могу найти дополнительную поддержку или помощь по GroupDocs.Viewer?
 По любым техническим вопросам или помощи вы можете посетить GroupDocs.Viewer.[Форум](https://forum.groupdocs.com/c/viewer/9) или обратитесь в их службу поддержки для получения оперативной помощи и рекомендаций.