---
date: '2026-08-25'
description: Узнайте, как конвертировать файлы Apple Numbers с помощью GroupDocs.Viewer
  for Java, преобразуя их в PDF, HTML, JPG или PNG. Включает настройку, шаги конвертации
  документов Java и советы по отображению в вебе.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Узнайте, как конвертировать файлы Apple Numbers с помощью GroupDocs.Viewer
  for Java, преобразуя их в PDF, HTML, JPG или PNG. Включает настройку, шаги конвертации
  документов Java и советы по отображению в вебе.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Как конвертировать файлы Apple Numbers с помощью GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Как конвертировать файлы Apple Numbers с помощью GroupDocs.Viewer for Java
type: docs
url: /ru/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Как конвертировать Numbers с помощью GroupDocs.Viewer для Java

Отображение таблиц Apple Numbers в вебе или в настольном клиенте может быть настоящей головоломкой, особенно когда нужно **конвертировать Numbers в PDF** или вставить их как изображения в отчёты. В этом руководстве вы узнаете, как **конвертировать Numbers** в PDF, HTML, JPG и PNG с помощью **GroupDocs.Viewer для Java**. Мы пройдём настройку проекта, рендеринг на уровне кода и реальные сценарии, чтобы вы могли за считанные минуты создать надёжные конвейеры предварительного просмотра или архивирования.

![Отображение документов Apple Numbers с помощью GroupDocs.Viewer для Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Отображение документов Apple Numbers с помощью GroupDocs.Viewer для Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Что вы узнаете
- Как добавить GroupDocs.Viewer в Maven‑проект на Java.  
- Пошаговый код для **конвертации Numbers в PDF**, **конвертации Numbers в HTML**, **конвертации Numbers в JPG** и **конвертации Numbers в PNG**.  
- Когда выбирать каждый формат вывода для веб‑порталов, почтовых рабочих процессов или систем управления документами.  

## Быстрые ответы
- **Можно ли конвертировать Numbers в PDF с помощью Java?** Да — создайте экземпляр `Viewer` и вызовите `PdfViewOptions`, чтобы получить готовый к сохранению PDF.  
- **Какой формат обеспечивает наибольший веб‑просмотр?** HTML, потому что он сохраняет таблицы, формулы и стили интерактивными.  
- **Нужна ли лицензия для продакшн?** Требуется коммерческая лицензия для любого не‑тестового развертывания.  
- **Поддерживается ли конвертация изображений?** Абсолютно — используйте `JpgViewOptions` или `PngViewOptions` для высококачественных снимков.  
- **Какая версия Java требуется?** Java 8+ и Maven для управления зависимостями.

## Предварительные требования
- Java Development Kit (JDK) 8 или более поздняя версия, установленная на вашем компьютере.  
- Maven для управления зависимостями и сборки проекта.  
- Базовое знакомство с вводом‑выводом файлов в Java, путями и обработкой исключений.  

## Настройка GroupDocs.Viewer для Java

### Установка с Maven
Добавьте репозиторий GroupDocs и зависимость Viewer в ваш `pom.xml`. Этот блок должен оставаться точно таким, как показано:

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
- **Бесплатная пробная версия:** Полный набор функций, без необходимости ввода данных кредитной карты.  
- **Временная лицензия:** Запросите ограниченный по времени ключ для расширенного тестирования.  
- **Полная покупка:** Получите бессрочную лицензию для коммерческого использования.

## Что такое класс Viewer?
`Viewer` — это основной движок GroupDocs.Viewer, который загружает документ и рендерит его в запрошенный формат вывода. Он абстрагирует работу с типами файлов, позволяя сосредоточиться на бизнес‑логике, а не на разборе внутренностей таблиц.

## Как конвертировать Numbers в HTML с помощью GroupDocs.Viewer для Java?

`HtmlViewOptions` задаёт параметры рендеринга HTML, такие как встраивание ресурсов или ссылка на внешние файлы.  
Загрузите файл Numbers, настройте параметры HTML и вызовите `viewer.view()`. Метод `HtmlViewOptions.forEmbeddedResources()` объединяет CSS и изображения непосредственно в HTML, что делает результат идеальным для встраивания в веб‑страницу без дополнительных ресурсов.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Почему это важно:** Встроенные ресурсы делают предварительный просмотр автономным, устраняя битые ссылки на изображения и упрощая развертывание через CDN.

## Как конвертировать Numbers в JPG с помощью GroupDocs.Viewer для Java?

`JpgViewOptions` настраивает вывод JPEG, позволяя регулировать качество и размер каждой отрисованной страницы.  
Вы можете превратить каждую страницу таблицы в снимок JPEG. Настройте параметр `quality`, чтобы сбалансировать размер файла и визуальное качество, что полезно, когда нужны лёгкие изображения для социальных сетей или рассылок.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Совет:** Для более быстрой обработки больших книг уменьшите качество до 70 % — визуальное влияние минимально, а размер файла резко снижается.

## Как конвертировать Numbers в PNG с помощью GroupDocs.Viewer для Java?

`PngViewOptions` настраивает вывод PNG, поддерживая сжатие без потерь и параметры разрешения для изображений высокого качества.  
PNG обеспечивает сжатие без потерь, сохраняет каждый пиксель точно как при рендеринге. Используйте свойство `resolution`, чтобы увеличить DPI, когда нужны графики, готовые к печати, для отчётов или PDF.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Профессиональный совет:** Установите `options.setResolution(300)` для вывода с высоким разрешением, который выглядит чётко на печатных страницах.

## Как конвертировать Numbers в PDF с помощью GroupDocs.Viewer для Java?

`PdfViewOptions` определяет параметры рендеринга PDF, включая встраивание шрифтов, сжатие и управление размером страниц.  
Объект `PdfViewOptions` позволяет встраивать шрифты, контролировать размер страниц и сохранять оригинальное расположение листов Numbers. Конверсия выполняется одним вызовом, создавая поисковый, не редактируемый PDF, идеальный для архивирования или соответствия требованиям.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Ключевая настройка:** Включите `options.setCompress(true)`, чтобы уменьшить размер PDF без потери качества, что важно для крупных хранилищ документов.

## Зачем использовать GroupDocs.Viewer для Java?

GroupDocs.Viewer поддерживает **более 100 форматов файлов**, включая Apple Numbers, и может рендерить таблицы с сотнями страниц без загрузки всего файла в память. Тесты показывают, что файл Numbers из 250 страниц конвертируется в PDF менее чем за 8 секунд на стандартном процессоре 2.5 ГГц, обеспечивая как скорость, так и надёжность для корпоративных конвейеров.

## Практические применения
- **Веб‑интеграция:** Рендер в HTML для интерактивного просмотрщика таблиц, работающего во всех браузерах без плагинов.  
- **Обмен контентом:** Конвертация в JPG/PNG для быстрых вставок изображений в рассылки, чаты или социальные ленты.  
- **Корпоративные DMS:** Используйте **конвертацию Numbers** в PDF для хранения не редактируемой, поисковой версии таблицы в целях соответствия требованиям и аудита.  

## Соображения по производительности
- **Управление ресурсами:** Всегда создавайте `Viewer` внутри блока try‑with‑resources (как показано), чтобы нативные ресурсы освобождались сразу.  
- **Большие книги:** Обрабатывайте постранично и передавайте вывод в поток, чтобы потребление памяти оставалось ниже 100 МБ, даже для файлов в 500 страниц.  
- **Потокобезопасность:** Создавайте отдельный экземпляр `Viewer` для каждого потока; класс не потокобезопасен, поэтому совместное использование одного экземпляра может вызвать состояния гонки.

## Распространённые подводные камни и устранение неполадок
- **Отсутствующие шрифты:** Если сгенерированный PDF выглядит иначе, убедитесь, что необходимые шрифты доступны на сервере, или встраивайте их с помощью `PdfViewOptions.setEmbedFonts(true)`.  
- **Пустые страницы:** Убедитесь, что файл Numbers не защищён паролем; в текущей версии GroupDocs.Viewer не расшифровывает защищённые книги.  
- **Ошибки нехватки памяти:** Для очень больших файлов включите `options.setPageCount(1)`, чтобы рендерить по одной странице и позже объединять результаты.

## Часто задаваемые вопросы

**В: Какие форматы файлов поддерживает GroupDocs.Viewer?**  
О: Более 100 форматов, включая DOCX, XLSX, PDF, HTML и Apple Numbers, с полными возможностями рендеринга для каждого.

**В: Как эффективно обрабатывать большие файлы Numbers?**  
О: Потоково конвертируйте постранично, используйте `options.setPageCount()` для ограничения использования памяти и рассмотрите сжатие выходного PDF.

**В: Можно ли использовать GroupDocs.Viewer в коммерческом проекте?**  
О: Да — приобретите коммерческую лицензию, чтобы снять ограничения пробной версии и получить поддержку уровня продакшн.

**В: Можно ли настроить качество выходных изображений?**  
О: Абсолютно. Настройте `JpgViewOptions.setQuality(int)` или `PngViewOptions.setResolution(int)` в соответствии с вашими требованиями к размеру и качеству.

**В: Где можно найти более продвинутые примеры использования?**  
О: Посетите [документацию GroupDocs](https://docs.groupdocs.com/viewer/java/) для подробных руководств, примеров проектов и деталей справочника API.

## Следующие шаги
Поэкспериментируйте с показанными выше параметрами, а затем изучите дополнительные настройки, такие как добавление водяных знаков в PDF, защита паролем или интеграция просмотрщика в сервис REST на Spring Boot. [Документация GroupDocs](https://docs.groupdocs.com/viewer/java/) предоставляет полный каталог функций, которые можно комбинировать.

## Ресурсы
- **Документация:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Документация GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Справочник API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Справочник API GroupDocs:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Скачать:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Приобрести лицензию:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Бесплатная пробная версия:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Временная лицензия:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Форум поддержки:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

## Связанные руководства

- [Как конвертировать Excel в HTML, JPG, PNG и PDF с помощью GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [Как конвертировать Excel в HTML и отобразить скрытые строки и столбцы в Java с помощью GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Руководство по рендерингу документов Java — конвертация файлов в HTML, PDF и изображения](/viewer/java/rendering-basics/)

---

**Последнее обновление:** 2026-08-25  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs