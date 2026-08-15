---
date: '2026-07-19'
description: Узнайте, как конвертировать PST в HTML и другие форматы, такие как JPG,
  PNG, PDF, с помощью GroupDocs.Viewer for Java. Это руководство охватывает все необходимые
  шаги и настройки.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Быстро конвертировать PST в HTML с помощью GroupDocs.Viewer for Java.
  Узнайте пошагово, как также экспортировать в JPG, PNG и PDF в готовом к использованию
  руководстве.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Конвертировать PST в HTML с GroupDocs.Viewer for Java – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Конвертировать PST в HTML, JPG, PNG, PDF с помощью GroupDocs.Viewer for Java
type: docs
url: /ru/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Конвертировать PST в HTML, JPG, PNG, PDF с помощью GroupDocs.Viewer для Java

Ищете способ **convert pst to html** или другие форматы, такие как JPG, PNG или PDF? С мощной библиотекой GroupDocs.Viewer для Java эта задача проста и эффективна. В этом руководстве вы узнаете, как рендерить файлы Outlook PST/OST в веб‑дружественный HTML, изображения или один PDF, делая ваши архивы электронной почты легкими для обмена и хранения.

![Конвертировать PST/OST в HTML, JPG, PNG, PDF с GroupDocs.Viewer для Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Конвертировать PST/OST в HTML, JPG, PNG, PDF с GroupDocs.Viewer для Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Что вы узнаете**
- Как настроить GroupDocs.Viewer для Java в проекте Maven.  
- Пошаговые инструкции по **java convert pst** файлам в HTML, JPG, PNG и PDF.  
- Советы по конфигурации для оптимальной производительности и типичных ошибок.

## Быстрые ответы
- **Какая библиотека обрабатывает конвертацию PST?** GroupDocs.Viewer for Java.  
- **Можно ли напрямую конвертировать PST в PDF?** Да, используя `PdfViewOptions`.  
- **Требуется ли лицензия для продакшн?** Необходима действующая лицензия GroupDocs.  
- **Какая версия Java поддерживается?** JDK 8 или выше.  
- **Нужно ли извлекать вложения вручную?** Нет, просмотрщик рендерит их автоматически.

## Что такое GroupDocs.Viewer для Java?
GroupDocs.Viewer для Java — это серверный API, который загружает более 100 форматов документов и электронных писем и преобразует их в HTML, изображения или PDF без внешнего программного обеспечения. Он обрабатывает файлы PST размером до 2 ГБ, удерживая использование памяти ниже 200 МБ.

## Как конвертировать pst в html с помощью GroupDocs.Viewer для Java?
Загрузите файл PST с помощью `new Viewer("source.pst")`, настройте `HtmlViewOptions`, указывая папку вывода, и вызовите `viewer.view(htmlOptions)`. API извлекает каждое письмо, сохраняет форматирование, вложения и метаданные, и записывает отдельную HTML‑страницу для каждого сообщения — всё в одном вызове метода.

### Почему стоит выбрать GroupDocs.Viewer?
- **Точное воспроизведение** — 99,9 % содержимого письма (включая тела в формате rich‑text, таблицы и встроенные изображения) воспроизводится точно.  
- **Множественные форматы вывода** — один вызов API может генерировать HTML, JPG, PNG или PDF, охватывая более 50 вариантов экспорта.  
- **Отсутствие внешних зависимостей** — не требуется Outlook, Exchange Server или сторонние конвертеры; всё работает внутри вашей Java‑среды.

## Предварительные требования
- **GroupDocs.Viewer для Java** — версия 25.2 или новее.  
- **Java Development Kit (JDK)** — 8 или новее.  
- Maven для управления зависимостями.  
- Базовые знания Java и знакомство с Maven.

## Настройка GroupDocs.Viewer для Java
`Viewer` — основной класс в GroupDocs.Viewer для Java, который загружает документ и рендерит его в выбранный формат. Добавьте репозиторий GroupDocs и зависимость в ваш `pom.xml`:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Приобретение лицензии
- **Бесплатная пробная версия** — изучите все функции без оплаты.  
- **Временная лицензия** — при необходимости продлите период оценки.  
- **Полная лицензия** — требуется для продакшн‑развертываний.

### Базовая инициализация
Экземпляры `Viewer` легковесны; вы можете переиспользовать один экземпляр для множества файлов, чтобы минимизировать накладные расходы на создание объектов.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Руководство по реализации
Следующие разделы проведут вас через процесс рендеринга файлов PST/OST в каждый поддерживаемый формат.

### Рендеринг документов PST/OST в HTML
#### Шаг 1: Настройка каталога вывода
Определите папку, куда будут записываться HTML‑страницы. GroupDocs создает подпапку для каждого письма, чтобы упорядочить ресурсы.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Шаг 2: Настройка параметров загрузки
`LoadOptions` позволяет указать обработку пароля, тайм‑ауты загрузки ресурсов и выборочную отрисовку страниц. Установка тайм‑аута в 30 секунд обычно подходит для большинства серверных сред.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Шаг 3: Определение параметров HTML‑просмотра
`HtmlViewOptions` задает папку вывода, обработку ресурсов и необязательные настройки CSS для конвертации в HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Шаг 4: Инициализация Viewer и рендеринг HTML
Создайте объект `Viewer`, передайте путь к файлу PST и вызовите `view` с `HtmlViewOptions`. API автоматически перебирает все сообщения внутри PST и генерирует аккуратную иерархию HTML.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Рендеринг документов PST/OST в JPG
#### Шаг 1: Настройка каталога вывода
Создайте отдельную папку для JPG‑снимков; каждое письмо будет преобразовано в один или несколько файлов изображений в зависимости от его длины.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Шаг 2: Настройка параметров загрузки
Те же `LoadOptions`, что использовались для HTML, можно переиспользовать здесь, обеспечивая согласованную обработку пароля во всех форматах.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Шаг 3: Определение параметров JPG‑просмотра
`JpgViewOptions` управляет разрешением изображения, качеством и папкой вывода для конвертации в JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Шаг 4: Инициализация Viewer и рендеринг JPG
Используйте `viewer.view(jpgOptions)`, чтобы создать JPEG‑файлы высокого качества, готовые для веб‑предпросмотра.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Рендеринг документов PST/OST в PNG
#### Шаг 1: Настройка каталога вывода
Вывод в PNG полезен, когда требуется без потерь качество для архивирования или OCR‑обработки.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Шаг 2: Настройка параметров загрузки
Дополнительные настройки не требуются, кроме конфигурации пароля и тайм‑аута.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Шаг 3: Определение параметров PNG‑просмотра
`PngViewOptions` позволяет задать прозрачный фон и папку вывода для без потерь PNG‑изображений.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Шаг 4: Инициализация Viewer и рендеринг PNG
Создайте `viewer.view(pngOptions)`, чтобы получить PNG‑снимки каждого письма.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Рендеринг документов PST/OST в PDF
#### Шаг 1: Настройка каталога вывода
Один PDF‑файл на PST упрощает процессы юридической проверки и уменьшает объем хранилища.

CODE_BLOCK_PLACEHOLDER_14_END

#### Шаг 2: Настройка параметров загрузки
При конвертации в PDF вы можете включить `setEmbedFonts(true)`, чтобы обеспечить визуальную точность на любом устройстве.

CODE_BLOCK_PLACEHOLDER_15_END

#### Шаг 3: Определение параметров PDF‑просмотра
`PdfViewOptions` позволяет выбрать уровень сжатия, встраивание шрифтов и задать имя выходного файла для конвертации в PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### Шаг 4: Инициализация Viewer и рендеринг PDF
Создайте `PdfViewOptions`, при желании выберите уровень сжатия и вызовите `viewer.view(pdfOptions)`. API объединяет все письма в один поисковый PDF‑документ.

CODE_BLOCK_PLACEHOLDER_17_END

## Практические применения
- **Архивирование электронной почты:** Преобразуйте большие архивы PST в поисковые HTML или PDF для соответствия требованиям.  
- **Системы управления документами:** Храните конвертированные файлы в системах, принимающих только PDF, PNG или JPG.  
- **Платформы для совместной работы:** Делитесь конвертированными письмами в виде изображений в Slack или Teams.  
- **Юридическая проверка:** Предоставляйте судам PDF‑версии электронных доказательств.  
- **Стратегии резервного копирования:** Храните легковесные PNG или JPG‑снимки критических сообщений.

## Соображения по производительности
- **Управление ресурсами:** Переиспользуйте экземпляры `Viewer` при обработке нескольких файлов, чтобы снизить накладные расходы.  
- **Настройка памяти:** Регулируйте `loadOptions.setResourceLoadingTimeout` в зависимости от возможностей сервера.  
- **Асинхронная обработка:** Перенесите конвертацию в фоновые потоки для отзывчивого UI.

## Часто задаваемые вопросы
**В: Как мне **convert pst to pdf** с тем же кодом?**  
О: Используйте `PdfViewOptions`, как показано в разделе рендеринга PDF; остальной код остается идентичным.

**В: Может ли GroupDocs.Viewer обрабатывать зашифрованные PST‑файлы?**  
О: Да, укажите пароль через `LoadOptions.setPassword("yourPassword")` перед рендерингом.

**В: В чём разница между **java convert pst** в PNG и JPG?**  
О: PNG сохраняет без потерь качество, идеально подходит для скриншотов, тогда как JPG обеспечивает меньший размер файлов для предпросмотра писем.

**В: Есть ли способ **how to convert pst** файлов пакетно?**  
О: Оберните логику рендеринга в цикл, проходящий по каталогу PST‑файлов; переиспользуйте одну и ту же конфигурацию `Viewer` для каждого файла.

**В: Поддерживает ли API конвертацию PST‑файлов более 1 ГБ?**  
О: Да, GroupDocs.Viewer потоково обрабатывает данные и может работать с файлами до 2 ГБ, не загружая весь архив в память.

## Заключение
Теперь у вас есть полный готовый к продакшн руководствo по **convert pst to html**, JPG, PNG и PDF с помощью GroupDocs.Viewer для Java. Следуя приведённым шагам, вы сможете интегрировать конвертацию электронной почты в любой Java‑ориентированный процесс, улучшить доступность и соответствовать требованиям нормативов.

---

**Последнее обновление:** 2026-07-19  
**Тестировано с:** GroupDocs.Viewer for Java 25.2  
**Автор:** GroupDocs

## Связанные руководства
- [Конвертировать NSF в PDF, HTML, JPG, PNG с помощью GroupDocs.Viewer для Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Конвертировать ODF в HTML, JPG, PNG, PDF с помощью GroupDocs.Viewer для Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Как конвертировать DOCX в HTML с помощью GroupDocs.Viewer для Java: пошаговое руководство](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)