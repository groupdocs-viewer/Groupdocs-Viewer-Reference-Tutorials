---
date: '2026-07-19'
description: Узнайте, как конвертировать WMZ в PDF, HTML, JPG и PNG с помощью GroupDocs
  Viewer for Java. Пошаговое руководство по java‑конвертации векторной графики.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Конвертировать WMZ в PDF, HTML, JPG и PNG с помощью GroupDocs Viewer
  for Java. Этот учебник демонстрирует пошаговую java‑конвертацию векторной графики
  с высоким качеством.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Конвертировать WMZ в PDF с помощью GroupDocs Viewer for Java – Быстрое руководство
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Конвертировать WMZ в PDF и другие форматы с помощью GroupDocs Viewer for Java
type: docs
url: /ru/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Преобразование WMZ в PDF и другие форматы с помощью GroupDocs Viewer для Java

Преобразование файлов WMZ (Web Metafile) и WMF (Windows Metafile) в более доступные форматы — особенно **convert WMZ to PDF** — может быть сложным, поскольку эти векторные графические форматы хранят инструкции по рисованию, а не пиксельные данные. С помощью **GroupDocs Viewer for Java** вы можете отрисовывать документы WMZ/WMF в HTML, JPG, PNG, **PDF** и другие популярные форматы всего в несколько строк кода, при этом сохраняя оригинальное визуальное качество.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Быстрые ответы
- **В какие форматы можно конвертировать WMZ/WMF?** HTML, JPG, PNG и PDF полностью поддерживаются.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия снимает ограничения оценки.  
- **Какая версия Java требуется?** Рекомендуется Java 8 или новее.  
- **Можно ли отрисовывать только определённые страницы?** Да, вы можете указать диапазоны страниц в параметрах просмотра.  
- **Является ли использование памяти проблемой для больших файлов?** Используйте try‑with‑resources и отрисовывайте только необходимые страницы, чтобы снизить потребление памяти.

## Что такое “convert WMZ to PDF”?
**Convert WMZ to PDF** означает взятие векторного файла WMZ и внедрение его инструкций рисования в контейнер PDF, создавая документ, который можно просматривать на любых устройствах, искать в нём и печатать. Конверсия сохраняет качество линий и формы, поэтому полученный PDF выглядит идентично оригинальной графике на любом устройстве.

## Почему стоит использовать GroupDocs Viewer для Java для конвертации векторной графики?
GroupDocs Viewer для Java обрабатывает отрисовку WMZ и WMF с **high fidelity**, сохраняет векторные детали независимо от того, выводите ли вы в PDF, PNG или HTML. Библиотека работает на любой платформе с JDK, не требует нативных компонентов Windows и предоставляет API единого вызова, масштабируемое от файлов с одной иконкой до многостраничных технических чертежей. В тестах производительности она обрабатывает **более 200‑страничные WMZ файлы менее чем за 12 секунд** на стандартном 4‑ядерном сервере.

## Предварительные требования

- **GroupDocs.Viewer for Java** – основной движок отрисовки.  
- Java Development Kit (JDK) 8 или новее.  
- IDE, например IntelliJ IDEA или Eclipse (необязательно, но рекомендуется).  
- Maven (или Gradle) для управления зависимостями.  

Знание Java NIO (`java.nio.file.Path`) и базовых операций ввода‑вывода файлов поможет вам легко следовать примерам.

## Настройка GroupDocs.Viewer для Java

Класс `Viewer` является точкой входа для всех операций отрисовки. Он представляет собой потокобезопасный движок, который можно переиспользовать для нескольких конвертаций.

Добавьте репозиторий и зависимость в ваш `pom.xml` (или эквивалент Gradle). После того как Maven разрешит артефакт, вы сможете создать экземпляр `Viewer`, который будет переиспользоваться для каждого шага конвертации.

> **Подсказка по лицензии:** Используйте бесплатную пробную версию для оценки, затем примените временную или приобретённую лицензию, чтобы разблокировать полную функциональность.

## Руководство по реализации

Ниже мы рассмотрим четыре сценария конвертации — HTML, JPG, PNG и PDF. Каждый сценарий следует одной и той же трёхшаговой схеме:

1. **Определите каталог вывода**, куда будут сохраняться отрисованные файлы.  
2. **Создайте экземпляр `Viewer`**, указывающий на исходный файл WMZ/WMF.  
3. **Настройте специфичные для формата параметры просмотра** и вызовите метод `view`.

Метод `view` выполняет отрисовку на основе предоставленных параметров.

### Отрисовка WMZ/WMF в HTML

#### Обзор
HTML‑вывод позволяет внедрять графику напрямую в веб‑страницы, при этом все ресурсы (изображения, CSS) находятся в одном файле.

**Шаг 1: Определите путь к каталогу вывода**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Шаг 2: Инициализируйте Viewer и отрисуйте в HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Отрисовка WMZ/WMF в JPG

#### Обзор
JPG — широко поддерживаемый растровый формат, идеальный для быстрых превью или вложений в электронную почту.

**Шаг 1: Определите путь к каталогу вывода**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Шаг 2: Инициализируйте Viewer и отрисуйте в JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Отрисовка WMZ/WMF в PNG

#### Обзор
PNG поддерживает прозрачность, что делает его идеальным для графики, которой необходимо сочетаться с различными фонами.

**Шаг 1: Определите путь к каталогу вывода**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Шаг 2: Инициализируйте Viewer и отрисуйте в PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Отрисовка WMZ/WMF в PDF

#### Обзор
PDF предоставляет кроссплатформенный, поисковый документ, сохраняющий оригинальное расположение.

**Шаг 1: Определите путь к каталогу вывода**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Шаг 2: Инициализируйте Viewer и отрисуйте в PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Распространённые проблемы и решения

`PageStreamViewOptions` позволяет отрисовывать конкретные страницы как потоки.  
`PdfViewOptions` настраивает параметры вывода PDF, такие как диапазон страниц и DPI.  
`FontSettings` позволяет предоставить пользовательские шрифты, когда исходный документ ссылается на отсутствующие шрифты.

| Проблема | Причина | Решение |
|----------|---------|----------|
| **OutOfMemoryError** при больших WMZ файлах | Viewer загружает весь документ в память | Отрисовывайте одну страницу за раз, используя `PageStreamViewOptions`, или увеличьте размер кучи JVM (`-Xmx`). |
| **Missing fonts** в PDF | Шрифт не встроен в исходный WMZ | Установите необходимые шрифты на хост‑машине или используйте `FontSettings` для предоставления пользовательских шрифтов. |
| **Blank PNG output** | Неправильный путь вывода или недостаточные права записи | Убедитесь, что `outputDirectory` существует и приложение имеет права записи. |
| **HTML resources not loading** | Использование `forExternalResources` без копирования файлов | Оставайтесь с `forEmbeddedResources` для автономного HTML‑файла. |

## Часто задаваемые вопросы

**Q: Могу ли я конвертировать WMF в PNG, используя тот же код?**  
A: Да. Пример PNG работает как для WMZ, так и для WMF файлов; просто замените `TestFiles.SAMPLE_WMZ` на ваш WMF‑источник.

**Q: Можно ли конвертировать только часть страниц?**  
A: Конечно. Используйте `PdfViewOptions` (или соответствующие параметры для других форматов) и вызовите `setPageNumbers(List<Integer>)` перед отрисовкой.

**Q: Нужна ли отдельная лицензия для каждого формата вывода?**  
A: Нет. Одна лицензия GroupDocs Viewer покрывает все поддерживаемые форматы, включая HTML, JPG, PNG и PDF.

**Q: Как “java convert vector graphics” влияет на производительность?**  
A: Преобразование вектор‑в‑растр является ресурсоёмким для CPU. Для больших пакетов рассмотрите многопоточность и переиспользование одного экземпляра `Viewer` для нескольких файлов.

**Q: Сохранит ли PDF векторное качество или будет растрирован?**  
A: При конвертации WMZ/WMF в PDF GroupDocs Viewer сохраняет векторные инструкции, где это возможно, что приводит к масштабируемому PDF.

## Заключение

Теперь у вас есть полный, готовый к продакшену гид по **convert WMZ to PDF** и другим распространённым форматам с использованием **GroupDocs Viewer for Java**. Независимо от того, создаёте ли вы веб‑службу, обслуживающую графику «на лету», или архивный инструмент, сохраняющий документы в PDF, приведённые выше шаги помогут вам быстро и надёжно достичь цели. Изучайте API дальше, чтобы настраивать диапазоны страниц, параметры DPI или водяные знаки в соответствии с требованиями вашего проекта.

---

**Last Updated:** 2026-07-19  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

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

## Связанные руководства

- [Как конвертировать OBJ в HTML, JPG, PNG и PDF в Java с помощью GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Конвертировать IGS в PDF, HTML, JPG и PNG с использованием GroupDocs.Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Конвертировать документы в PDF – Полное руководство](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)