---
"description": "Интегрируйте Groupdocs.Viewer для .NET с легкостью в свои проекты .NET для эффективного просмотра документов."
"linktitle": "Отменить рендеринг с помощью токена отмены"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Отменить рендеринг с помощью токена отмены"
"url": "/ru/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# Отменить рендеринг с помощью токена отмены

## Введение
Groupdocs.Viewer для .NET — это мощный инструмент, разработанный для упрощения просмотра и обработки документов в приложениях .NET. Независимо от того, работаете ли вы с PDF-файлами, документами Microsoft Office или другими распространенными форматами, эта библиотека предлагает надежную функциональность для бесшовной интеграции возможностей просмотра документов в ваши проекты .NET.
## Предпосылки
Прежде чем приступить к интеграции Groupdocs.Viewer для .NET, убедитесь, что выполнены следующие предварительные условия:
1. Установка: Загрузите и установите библиотеку Groupdocs.Viewer для .NET из предоставленного [ссылка для скачивания](https://releases.groupdocs.com/viewer/net/).
   
2. Лицензия: Получите лицензию от [Groupdocs](https://purchase.groupdocs.com/buy) чтобы раскрыть весь потенциал библиотеки. В качестве альтернативы вы можете начать с бесплатной пробной версии, используя [временная лицензия](https://purchase.groupdocs.com/temporary-license/).
   
3. Среда разработки: убедитесь, что у вас настроена совместимая среда разработки, включая Visual Studio или любую другую .NET IDE по вашему выбору.

## Импорт пространств имен
Для эффективного использования Groupdocs.Viewer для .NET вам необходимо импортировать необходимые пространства имен в ваш проект. Выполните следующие шаги:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Теперь давайте разберем приведенный пример на несколько шагов для лучшего понимания и реализации:
## Шаг 1: Определите выходной каталог
```csharp
string outputDirectory = "Your Document Directory";
```
На этом этапе задается каталог, в котором будут храниться отрисованные страницы документа.
## Шаг 2: Определите формат пути к файлу подкачки
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Здесь мы определяем формат путей к файлам отдельных страниц документа.
## Шаг 3: Инициализация CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource используется для генерации экземпляров CancellationToken, которые можно использовать для отмены асинхронных операций.
## Шаг 4: Получите CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
На этом этапе из CancellationTokenSource извлекается токен, который будет использоваться для отмены операции рендеринга.
## Шаг 5: Визуализация страниц документа
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Здесь мы инициируем рендеринг страниц документа асинхронно с помощью Task.Run(). Экземпляр Viewer создается с указанным файлом документа (SAMPLE_DOCX), и настраиваются параметры рендеринга. Затем процесс рендеринга запускается с помощью метода View класса Viewer.
## Шаг 6: Установите тайм-аут рендеринга
```csharp
cancellationTokenSource.CancelAfter(10);
```
Этот шаг устанавливает тайм-аут в 10 миллисекунд для операции рендеринга. Если операция превысит этот тайм-аут, она будет автоматически отменена.
## Шаг 7: Отображение сообщения об успешном завершении
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Наконец, отображается сообщение об успешном завершении обработки документа.

## Заключение
В этом руководстве мы рассмотрели основы интеграции Groupdocs.Viewer для .NET в ваши проекты. Выполнив шаги, описанные выше, вы сможете легко интегрировать возможности просмотра документов в свои приложения .NET, улучшая пользовательский опыт и производительность.
## Часто задаваемые вопросы
### Совместим ли Groupdocs.Viewer для .NET со всеми форматами документов?
Groupdocs.Viewer для .NET поддерживает широкий спектр форматов документов, включая PDF, документы Microsoft Office, изображения и многое другое.
### Могу ли я настроить внешний вид отображаемых страниц документа?
Да, вы можете настраивать различные аспекты процесса рендеринга, включая размер страницы, качество, водяные знаки и многое другое.
### Требуется ли для Groupdocs.Viewer for .NET подключение к Интернету?
Нет, Groupdocs.Viewer для .NET работает локально в вашей среде .NET и не требует подключения к Интернету для просмотра документов.
### Доступна ли техническая поддержка для Groupdocs.Viewer для .NET?
Да, техническая поддержка доступна через [Форум Groupdocs](https://forum.groupdocs.com/c/viewer/9), где вы можете задавать вопросы, сообщать о проблемах и взаимодействовать с сообществом.
### Могу ли я попробовать Groupdocs.Viewer для .NET перед покупкой?
Да, вы можете начать с бесплатной пробной версии, используя предоставленную [Пробная версия](https://releases.groupdocs.com/).