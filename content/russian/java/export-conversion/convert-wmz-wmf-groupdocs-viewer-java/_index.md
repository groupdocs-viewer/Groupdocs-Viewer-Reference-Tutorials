---
date: '2026-02-18'
description: Узнайте, как конвертировать файлы WMZ и WMF в PDF, HTML, JPG и PNG с
  помощью GroupDocs Viewer для Java. Это руководство охватывает GroupDocs Viewer Java
  и конвертацию векторной графики в Java.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Как конвертировать WMZ в PDF и другие форматы с помощью GroupDocs Viewer для
  Java
type: docs
url: /ru/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 content.# Как конвертировать WMZ в PDF и другие форматы с помощью GroupDocs Viewer для Java

Конвертация файлов WMZ (Web Metafile) и WMF (Windows Metafile) в более доступные форматы — особенно **convert WMZ to PDF** — может быть сложной, поскольку эти векторные графические форматы хранят инструкции по рисованию, а не пиксельные данные. С помощью **GroupDocs Viewer for Java** вы можете отрисовывать документы WMZ/WMF в HTML, JPG, PNG, **PDF** и другие популярные форматы всего в несколько строк кода.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

В этом руководстве вы узнаете, как настроить библиотеку, отрисовать файлы WMZ/WMF в нужный формат и справиться с распространёнными подводными камнями. К концу вы сможете интегрировать **groupdocs viewer java** в свои Java‑приложения для **java convert vector graphics** быстро и надёжно.

## Быстрые ответы
- **В какие форматы можно конвертировать WMZ/WMF?** HTML, JPG, PNG и PDF полностью поддерживаются.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия снимает ограничения оценки.  
- **Какая версия Java требуется?** Рекомендуется Java 8 или новее.  
- **Можно ли отрисовать только определённые страницы?** Да, можно указать диапазоны страниц в параметрах просмотра.  
- **Является ли использование памяти проблемой для больших файлов?** Используйте try‑with‑resources и отрисовывайте только необходимые страницы, чтобы снизить потребление памяти.

## Что такое “convert WMZ to PDF”?
Конвертация WMZ в PDF означает взятие векторного файла WMZ и растеризацию его (или сохранение векторных данных) внутри контейнера PDF. PDF универсально просматривается, поддерживает поиск и печать, что делает его идеальным для архивирования и обмена графикой WMZ.

## Почему стоит использовать GroupDocs Viewer for Java для конвертации векторной графики?
- **High fidelity**: Библиотека сохраняет оригинальное качество рисунка, независимо от того, выводите ли вы в PDF или PNG.  
- **Zero external dependencies**: Нет необходимости в нативных библиотеках Windows; всё работает на любой платформе с JDK.  
- **Simple API**: Один экземпляр `Viewer` и один вызов `view` обрабатывают всю конвертацию.  
- **Scalable**: Работает одинаково хорошо как с одностраничными иконками, так и с многостраничными техническими чертежами.

## Предварительные требования

### Требуемые библиотеки
- **GroupDocs.Viewer for Java** – основной движок рендеринга.  
- Java Development Kit (JDK) 8+.

### Настройка окружения
- IDE, например IntelliJ IDEA или Eclipse.  
- Maven для управления зависимостями (или Gradle, если предпочитаете).

### Требуемые знания
- Знание Java I/O файлов (`java.nio.file.Path`).  
- Базовое понимание того, как документные просмотрщики рендерят контент.

## Настройка GroupDocs.Viewer для Java

Добавьте репозиторий и зависимость в ваш `pom.xml`:

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

> **License tip:** Используйте бесплатную пробную версию для оценки, затем примените временную или приобретённую лицензию, чтобы разблокировать полную функциональность.

После разрешения зависимости вы можете создать экземпляр `Viewer`, который будет переиспользоваться для каждого шага конвертации.

## Руководство по реализации

Мы пройдём через четыре сценария конвертации: HTML, JPG, PNG и PDF. Каждый пример следует одной схеме — определить путь вывода, создать экземпляр `Viewer` с исходным файлом WMZ, настроить соответствующие параметры просмотра и вызвать `view`.

### Рендеринг WMZ/WMF в HTML

#### Обзор
HTML‑вывод позволяет встроить графику напрямую в веб‑страницы, при этом все ресурсы (изображения, CSS) находятся в одном файле.

**Шаг 1: Определите путь к каталогу вывода**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Шаг 2: Инициализируйте Viewer и отрендерите в HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Рендеринг WMZ/WMF в JPG

#### Обзор
JPG — широко поддерживаемый растровый формат, идеальный для быстрых превью или вложений в электронную почту.

**Шаг 1: Определите путь к каталогу вывода**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Шаг 2: Инициализируйте Viewer и отрендерите в JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Рендеринг WMZ/WMF в PNG

#### Обзор
PNG поддерживает прозрачность, что делает его идеальным для графики, которой необходимо сочетаться с разными фонами.

**Шаг 1: Определите путь к каталогу вывода**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Шаг 2: Инициализируйте Viewer и отрендерите в PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Рендеринг WMZ/WMF в PDF

#### Обзор
PDF предоставляет платформенно‑независимый, searchable документ, сохраняющий оригинальное расположение.

**Шаг 1: Определите путь к каталогу вывода**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Шаг 2: Инициализируйте Viewer и отрендерите в PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Распространённые проблемы и решения

| Issue | Cause | Solution |
|-------|-------|----------|
| **OutOfMemoryError** при больших файлах WMZ | Viewer загружает весь документ в память | Рендерьте одну страницу за раз, используя `PageStreamViewOptions`, или увеличьте размер кучи JVM (`-Xmx`). |
| **Missing fonts** в PDF | Шрифт не встроен в исходный WMZ | Установите необходимые шрифты на хост‑машине или используйте `FontSettings` для предоставления пользовательских шрифтов. |
| **Blank PNG output** | Неправильный путь вывода или недостаточные права записи | Проверьте, что `outputDirectory` существует и приложение имеет права на запись. |
| **HTML resources not loading** | Использование `forExternalResources` без копирования файлов | Оставайтесь с `forEmbeddedResources` для самодостаточного HTML‑файла. |

## Часто задаваемые вопросы

**Q: Можно ли конвертировать WMF в PNG с тем же кодом?**  
A: Да. Пример PNG работает как для файлов WMZ, так и WMF; просто замените `TestFiles.SAMPLE_WMZ` на ваш WMF‑источник.

**Q: Можно ли конвертировать только часть страниц?**  
A: Конечно. Используйте `PdfViewOptions` (или соответствующие параметры для других форматов) и вызовите `setPageNumbers(List<Integer>)` перед рендерингом.

**Q: Нужна ли отдельная лицензия для каждого формата вывода?**  
A: Нет. Одна лицензия GroupDocs Viewer покрывает все поддерживаемые форматы, включая HTML, JPG, PNG и PDF.

**Q: Как “java convert vector graphics” влияет на производительность?**  
A: Конвертация вектор‑в‑растр требует значительных ресурсов CPU. Для больших пакетов рассмотрите многопоточность и переиспользование одного экземпляра `Viewer` для нескольких файлов.

**Q: Сохранит ли PDF векторное качество или будет растеризован?**  
A: При конвертации WMZ/WMF в PDF GroupDocs Viewer сохраняет векторные инструкции, где это возможно, что приводит к масштабируемому PDF.

## Заключение

Теперь у вас есть полный, готовый к продакшн руководство по **convert WMZ to PDF** и другим распространённым форматам с использованием **GroupDocs Viewer for Java**. Независимо от того, создаёте ли вы веб‑службу, обслуживающую графику «на лету», или архивный инструмент, сохраняющий документы в PDF, приведённые выше шаги помогут вам быстро достичь цели.

---

**Last Updated:** 2026-02-18  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

---