---
date: '2026-08-08'
description: Узнайте, как конвертировать IGS в PDF, HTML, JPG и PNG с помощью GroupDocs.Viewer
  for Java. Пошаговое руководство, требования и устранение неполадок для Java‑разработчиков.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Конвертировать IGS в PDF, HTML, JPG и PNG с помощью GroupDocs.Viewer
  for Java. Подробная настройка, примеры кода и устранение неполадок для Java‑разработчиков.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Конвертировать IGS в PDF, HTML, JPG и PNG с помощью GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Конвертировать IGS в PDF, HTML, JPG и PNG с помощью GroupDocs.Viewer Java
type: docs
url: /ru/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Конвертировать IGS в PDF, HTML, JPG и PNG с помощью GroupDocs.Viewer Java

Если вам нужно **конвертировать IGS в PDF** (или в HTML, JPG, PNG) напрямую из Java‑приложения, вы попали по адресу. В этом руководстве мы пройдем всё необходимое — от установки библиотеки до рендеринга 3‑D модели в формате, подходящем вашему проекту. Вы поймёте, почему GroupDocs.Viewer — надёжный выбор для быстрых и надёжных конвертаций, и получите готовые фрагменты кода, которые можно сразу использовать в своём решении.

![Конвертировать файлы IGS в HTML, JPG, PNG и PDF с помощью GroupDocs.Viewer для Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Быстрые ответы
- **Могу ли я конвертировать IGS в PDF с помощью Java?** Да, используйте `PdfViewOptions` вместе с API `Viewer`.  
- **Какие форматы вывода поддерживаются?** HTML, JPG, PNG и PDF поддерживаются нативно.  
- **Нужна ли лицензия для продакшна?** Требуется коммерческая лицензия; бесплатная пробная версия позволяет протестировать основные функции.  
- **Какая версия Java требуется?** JDK 8 или выше; библиотека также работает на Java 11, 17 и более новых версиях.  
- **Является ли Maven единственным способом добавить библиотеку?** Нет, вы также можете использовать Gradle или вручную добавить JAR‑файлы в ваш classpath.

## Что такое конвертация IGS в PDF?
Конвертация IGS в PDF означает преобразование нейтрального 3‑D CAD‑файла в статический, универсально просматриваемый документ. Это позволяет делиться визуализацией дизайна с заинтересованными сторонами, у которых нет CAD‑инструментов, встраивать рендеринг в отчёты или архивировать модель для целей соответствия.

## Почему использовать GroupDocs.Viewer для конвертации IGS?
GroupDocs.Viewer обрабатывает файлы IGS без необходимости в стороннем CAD‑ПО. Он поддерживает **более 50 форматов ввода и вывода**, может рендерить сборки, содержащие **сотни деталей**, при этом потребляя память менее **200 МБ**, и выдаёт результаты менее чем за **2 секунды** для типовых моделей на стандартном сервере. Эти измеримые преимущества делают его высокопроизводительным и экономически эффективным выбором для корпоративных конвейеров.

## Предварительные требования
- **GroupDocs.Viewer for Java** ≥ 25.2 (последний стабильный релиз).  
- **JDK 8+** установлен и настроен в вашей IDE (IntelliJ IDEA, Eclipse, NetBeans и т.д.).  
- Базовые знания Maven (необязательно, но рекомендуется для управления зависимостями).  

## Настройка GroupDocs.Viewer для Java

### Зависимость Maven
Добавьте репозиторий GroupDocs и зависимость Viewer в ваш `pom.xml`:

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

### Получение лицензии
GroupDocs.Viewer предлагает три варианта лицензирования:
- **Free trial** – ограниченное использование, идеально подходит для быстрых тестов proof‑of‑concept.  
- **Temporary license** – полный набор функций на короткий период оценки, идеально для пилотных проектов.  
- **Commercial license** – неограниченное использование в продакшене, включает приоритетную поддержку и обновления.

### Базовая инициализация Viewer
Класс `Viewer` является точкой входа для всех операций рендеринга. Он загружает исходный файл, анализирует формат и предоставляет методы для создания требуемого вывода.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Рендеринг IGS в HTML

### Как конвертировать IGS в HTML?
Загрузите файл IGS с помощью экземпляра `Viewer` и передайте объект `HtmlViewOptions`, который встраивает все необходимые ресурсы. Вызов возвращает один HTML‑файл, содержащий полный 3‑D‑вид, что упрощает встраивание в веб‑страницы. Вы также можете настроить рендеринг, задав параметры, такие как размер страницы, цвет фона и включение интерактивных элементов управления.  
`HtmlViewOptions` настраивает процесс генерации HTML‑вывода, включая встраивание ресурсов и макет страницы.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Рендеринг IGS в JPG

### Как конвертировать IGS в JPG?
Создайте объект `JpgViewOptions`, настройте желаемое разрешение и качество сжатия, и позвольте `Viewer` генерировать растровые изображения для каждой страницы модели. Сгенерированные JPG‑файлы можно сохранить в указанный каталог, а параметр качества можно регулировать, чтобы сбалансировать размер файла и визуальное качество, что полезно для миниатюр или печати высокого разрешения.  
`JpgViewOptions` задаёт параметры генерации JPG‑изображений, такие как разрешение, качество и каталог вывода.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Рендеринг IGS в PNG

### Как конвертировать IGS в PNG?
Класс `PngViewOptions` позволяет создавать изображения без потерь с опциональной прозрачностью. Этот формат идеален для наложения модели на цветные фоны в маркетинговых материалах. Вы также можете задать разрешение и цвет фона в соответствии с рекомендациями вашего бренда, обеспечивая единообразный вид всех сгенерированных ресурсов.  
`PngViewOptions` определяет параметры рендеринга PNG, включая разрешение, прозрачность и цвет фона.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Рендеринг IGS в PDF

### Как конвертировать IGS в PDF?
Используйте `PdfViewOptions` для создания многостраничного PDF, сохраняющего визуальное расположение 3‑D модели. Вы также можете встраивать шрифты и управлять размером страниц в соответствии с корпоративными рекомендациями по брендингу. Дополнительные настройки позволяют задавать качество изображений, уровень сжатия и включать оглавление для сборок, состоящих из нескольких страниц.  
`PdfViewOptions` управляет созданием PDF, позволяя задавать размер страниц, качество изображений и конфигурацию встраивания шрифтов.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Практические применения
- **Веб‑порталы** – встраивание моделей, отрендеренных в HTML, непосредственно в конфигураторы продуктов, позволяя клиентам вращать и масштабировать их без установки плагинов.  
- **Маркетинговые материалы** – генерация изображений JPG/PNG высокого разрешения для брошюр, презентаций и публикаций в социальных сетях.  
- **Техническая документация** – включение PDF‑рендеров CAD‑моделей в руководства пользователя, обеспечивая возможность инженерам просматривать дизайны офлайн.  
- **Контроль качества** – автоматизация создания миниатюр для тысяч файлов IGS, ускоряя процессы визуального контроля.

## Распространённые проблемы и решения

| Проблема | Решение |
|----------|---------|
| **Папка вывода не найдена** | Проверьте путь, переданный в `Path outputDirectory`, и убедитесь, что процесс Java имеет права записи в целевой каталог. |
| **Пустые страницы в PDF** | Убедитесь, что исходный файл IGS не повреждён; сначала откройте его в нативном CAD‑просмотрщике. |
| **Медленный рендеринг больших сборок** | Увеличьте размер кучи JVM (`-Xmx2g` или более) и рассмотрите рендеринг постранично с использованием `viewer.getPageCount()` для обработки частей. |
| **Отсутствуют шрифты в PDF** | Используйте `PdfViewOptions` для встраивания необходимых шрифтов или установите недостающие шрифты на сервере, где работает сервис конвертации. |

## Часто задаваемые вопросы

**В: Могу ли я конвертировать несколько файлов IGS за один запуск?**  
A: Да. Пройдитесь по коллекции путей к файлам и вызовите соответствующий метод `view` для каждого файла в рамках одного экземпляра `Viewer`.

**В: Можно ли настроить размер страниц PDF?**  
A: Конечно. `PdfViewOptions` предоставляет `setPageSize(PageSize.A4)`, `PageSize.Letter` и пользовательские размеры через `setCustomSize(width, height)`.

**В: Нужна ли отдельная лицензия для каждого формата вывода?**  
A: Нет. Одна лицензия GroupDocs.Viewer покрывает все поддерживаемые форматы, включая HTML, JPG, PNG и PDF.

**В: Какой максимальный размер файла IGS, прежде чем производительность ухудшится?**  
A: Библиотека надёжно обрабатывает файлы до **500 МБ**; для моделей больше 200 МБ выделяйте дополнительную память JVM и рассматривайте рендеринг пакетами.

**В: Могу ли я отрендерить только определённый вид или ориентацию?**  
A: GroupDocs.Viewer рендерит ориентацию по умолчанию, определённую в файле IGS. Для пользовательских видов предварительно обработайте файл с помощью CAD‑инструмента или измените модель перед конвертацией.

**Последнее обновление:** 2026-08-08  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs

## Связанные руководства

- [конвертировать cdr в html, jpg, png, pdf с помощью GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Как конвертировать pdf в html и оптимизировать качество изображения в Java с помощью GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)