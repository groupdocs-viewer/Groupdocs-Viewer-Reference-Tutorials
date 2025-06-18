---
"description": "Изучите возможности Groupdocs.Viewer для .NET в бесшовном рендеринге файлов Numbers. Конвертируйте в HTML, JPG, PNG и PDF без усилий."
"linktitle": "Рендеринг чисел"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Рендеринг чисел"
"url": "/ru/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# Рендеринг чисел

## Введение
Добро пожаловать в это пошаговое руководство по рендерингу файлов Numbers с помощью Groupdocs.Viewer для .NET. Независимо от того, являетесь ли вы опытным разработчиком или новичком, это руководство проведет вас через процесс преобразования документов Numbers в различные форматы. Groupdocs.Viewer для .NET — это мощный инструмент, позволяющий вам легко интегрировать возможности просмотра документов в ваши приложения .NET.
## Предпосылки
Прежде чем приступить к изучению руководства, убедитесь, что у вас выполнены следующие предварительные условия:
- Практические знания разработки на C# и .NET.
- Groupdocs.Viewer для .NET библиотека установлена. Вы можете скачать ее [здесь](https://releases.groupdocs.com/viewer/net/).
- Путь к каталогу документов, в котором будут сохранены выходные файлы.
## Импорт пространств имен
В вашем проекте C# обязательно импортируйте необходимые пространства имен для использования библиотеки Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Шаг 1: Настройка выходного каталога
Перед началом рендеринга определите выходной каталог, в котором будут сохранены преобразованные файлы. Замените «Ваш каталог документов» на фактический путь:
```csharp
string outputDirectory = "Your Document Directory";
```
## Шаг 2: Рендеринг в многостраничный HTML
Используйте следующий код для преобразования файла Numbers в многостраничный HTML:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Шаг 3: Рендеринг в JPG
Конвертируйте файл Numbers в формат JPG с помощью следующего кода:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Шаг 4: Рендеринг в PNG
Преобразуйте файл Numbers в формат PNG, используя следующий код:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Шаг 5: Преобразование в PDF
Наконец, преобразуйте файл Numbers в формат PDF, используя следующий код:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Поздравляем! Вы успешно преобразовали файлы Numbers в различные форматы с помощью Groupdocs.Viewer для .NET.
## Заключение
В этом уроке мы рассмотрели основы рендеринга файлов Numbers с помощью Groupdocs.Viewer для .NET. Эта мощная библиотека обеспечивает бесшовную интеграцию для просмотра и преобразования документов в ваших приложениях .NET.
## Часто задаваемые вопросы
### Могу ли я использовать Groupdocs.Viewer для .NET с другими типами документов?
Да, Groupdocs.Viewer поддерживает широкий спектр форматов документов, включая Word, Excel, PDF и другие.
### Доступна ли временная лицензия для целей тестирования?
Да, вы можете получить временную лицензию. [здесь](https://purchase.groupdocs.com/temporary-license/) для тестирования.
### Где я могу найти поддержку Groupdocs.Viewer для .NET?
Посетите [Форум Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) за помощь и обсуждения.
### Как приобрести полную версию Groupdocs.Viewer для .NET?
Вы можете приобрести полную версию [здесь](https://purchase.groupdocs.com/buy).
### Есть ли бесплатная пробная версия?
Да, вы можете изучить бесплатную пробную версию. [здесь](https://releases.groupdocs.com/).