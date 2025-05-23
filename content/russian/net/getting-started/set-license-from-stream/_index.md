---
title: Установить лицензию из потока
linktitle: Установить лицензию из потока
second_title: GroupDocs.Viewer .NET API
description: Улучшите свои приложения .NET с помощью GroupDocs.Viewer для удобного просмотра документов. Следуйте нашему пошаговому руководству и легко интегрируйте мощные возможности просмотра документов.
weight: 11
url: /ru/net/getting-started/set-license-from-stream/
---

# Установить лицензию из потока

## Введение
Вы хотите расширить возможности своих .NET-приложений с помощью расширенных возможностей просмотра документов? GroupDocs.Viewer для .NET предлагает комплексное решение для плавной интеграции функций просмотра документов в ваши проекты. В этом руководстве мы углубимся в процесс использования GroupDocs.Viewer для .NET, чтобы обогатить ваши приложения мощными возможностями просмотра документов. 
## Предварительные условия
Прежде чем мы углубимся в процесс интеграции, убедитесь, что у вас есть следующие предварительные условия:
1. Базовые знания разработки .NET. Для изучения этого руководства необходимо знание C# и .NET framework.
   
2.  Пакет GroupDocs.Viewer для .NET. Убедитесь, что вы загрузили и установили пакет GroupDocs.Viewer для .NET. Вы можете получить его из[ссылка для скачивания](https://releases.groupdocs.com/viewer/net/).
3.  Доступ к документации GroupDocs: сохраните[документация](https://tutorials.groupdocs.com/viewer/net/) удобно для справки в процессе интеграции.

## Импортировать пространства имен
Для начала импортируйте необходимые пространства имен в ваше .NET-приложение. Следуй этим шагам:
### Шаг 1. Откройте проект .NET.
Убедитесь, что проект .NET открыт в предпочитаемой вами среде разработки.
### Шаг 2. Добавьте пространство имен GroupDocs.Viewer.
В файле кода добавьте следующее пространство имен для доступа к функциям GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Установить лицензию из потока
Следующий шаг предполагает установку лицензии из потока. Выполните следующие подробные шаги:
### Шаг 1: Определите выходной каталог.
Установите каталог, в котором будут храниться ваши документы, указав выходной каталог:
```csharp
string outputDirectory = "Your Document Directory";
```
### Шаг 2. Проверьте существование файла лицензии.
Проверьте, существует ли файл лицензии в каталоге вашего проекта:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Шаг 3: Установите лицензию.
Если файл лицензии существует, установите лицензию, используя предоставленный поток:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Шаг 4. Обработка отсутствия лицензии.
Если файл лицензии не найден, предоставьте инструкции по получению лицензии:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://Purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://Purchase.groupdocs.com/temporary-license.");
}
```

## Заключение
Поздравляем! Вы успешно научились интегрировать GroupDocs.Viewer для .NET в свои приложения. С помощью этого мощного инструмента вы теперь можете легко просматривать различные форматы документов в своих проектах .NET, повышая удобство работы и производительность пользователей.
## Часто задаваемые вопросы
### Нужна ли мне лицензия для использования GroupDocs.Viewer для .NET?
Да, вам нужна лицензия для использования GroupDocs.Viewer для .NET. Вы можете получить временную или постоянную лицензию на веб-сайте GroupDocs.
### Могу ли я интегрировать GroupDocs.Viewer в мое приложение ASP.NET?
Абсолютно! GroupDocs.Viewer для .NET легко интегрируется как в настольные, так и в веб-приложения, включая ASP.NET.
### Какие форматы документов поддерживаются GroupDocs.Viewer?
GroupDocs.Viewer поддерживает широкий спектр форматов документов, включая PDF, Microsoft Office (Word, Excel, PowerPoint), изображения и многое другое.
### Совместим ли GroupDocs.Viewer с .NET Core?
Да, GroupDocs.Viewer для .NET совместим как с .NET Framework, так и с .NET Core.
### Могу ли я настроить интерфейс средства просмотра в соответствии с темой моего приложения?
Да, GroupDocs.Viewer предоставляет широкие возможности настройки, позволяющие легко адаптировать интерфейс средства просмотра в соответствии с темой вашего приложения.