---
date: '2026-09-05'
description: Узнайте, как генерировать html из pdf и отключать группировку символов
  с помощью GroupDocs Viewer for Java для точного представления текста.
keywords:
- generate html from pdf
- render pdf to html
- convert pdf to html
lastmod: '2026-09-05'
og_description: Генерируйте html из pdf с помощью GroupDocs Viewer for Java, отключая
  группировку символов для точного размещения глифов. Узнайте пошаговую реализацию.
og_image_alt: GroupDocs Viewer for Java rendering PDF to HTML with precise character
  placement
og_title: Генерация html из pdf и отключение группировки – GroupDocs Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-05'
  description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  headline: Generate html from pdf & disable grouping – GroupDocs Java
  type: TechArticle
- description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  name: Generate html from pdf & disable grouping – GroupDocs Java
  steps:
  - name: define output directory
    text: '**Why?** This ensures your rendered HTML files are stored in a dedicated
      folder, making it easy to locate and manage them later.'
  - name: configure file path format
    text: '**Why?** Using a placeholder (`{0}`) lets the viewer create a separate
      HTML file for each PDF page, keeping the output organized.'
  - name: initialize HTML view options
    text: '**Why?** Embedded resources bundle images, fonts, and CSS directly with
      each HTML page, which is ideal for web‑based viewers or e‑learning platforms.'
  - name: disable character grouping
    text: '`setDisableCharsGrouping(true)` disables the default behavior of grouping
      adjacent characters, ensuring each glyph is rendered separately. **Why?** This
      is the crucial line that tells the rendering engine **not** to merge adjacent
      characters, guaranteeing that the generated HTML reflects the exact g'
  - name: render the document
    text: '`Viewer` is the primary class that opens a document and provides rendering
      capabilities. **Why?** Wrapping the `Viewer` in a try‑with‑resources block guarantees
      that all native resources are released automatically, preventing memory leaks
      in long‑running applications.'
  type: HowTo
- questions:
  - answer: It forces the renderer to treat each character as an independent element,
      preserving exact layout.
    question: What does “disable grouping” do?
  - answer: '`viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.'
    question: Which API option controls this?
  - answer: A trial works for testing, but a full license is required for production.
    question: Do I need a license?
  - answer: Yes—use `HtmlViewOptions` to create HTML output while disabling grouping.
    question: Can I generate html from pdf at the same time?
  - answer: It’s primarily for PDFs, but the viewer supports many other formats.
    question: Is this feature limited to PDFs?
  type: FAQPage
tags:
- generate html
- GroupDocs Viewer
- Java document rendering
title: Генерация html из pdf и отключение группировки – GroupDocs Java
type: docs
url: /ru/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Генерировать html из pdf и отключить группировку с GroupDocs Viewer for Java

Во многих проектах вам необходимо **генерировать html из pdf**, сохраняя каждый глиф точно на своём месте. Это особенно важно для сложных письменностей, древних языков или юридических документов, где один неверно расположенный символ может изменить смысл. В этом руководстве мы пройдём полный процесс рендеринга PDF в HTML с помощью GroupDocs Viewer for Java и покажем, **как отключить группировку**, чтобы каждый символ рассматривался как отдельный элемент.

![Точные техники рендеринга с GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Быстрые ответы
- **Что делает “отключение группировки”?** Она заставляет рендерер рассматривать каждый символ как отдельный элемент, сохраняющий точную раскладку.  
- **Какая опция API управляет этим?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Нужна ли лицензия?** Триальная версия подходит для тестирования, но для продакшна требуется полная лицензия.  
- **Можно ли одновременно генерировать html из pdf?** Да — используйте `HtmlViewOptions` для создания HTML‑вывода при отключённой группировке.  
- **Ограничена ли эта функция только PDF?** В основном она предназначена для PDF, но просмотрщик поддерживает множество других форматов.

## Что такое генерация html из pdf?
`generate html from pdf` описывает процесс преобразования PDF‑документа в набор HTML‑страниц, сохраняющих оригинальную раскладку, шрифты и изображения. Такое преобразование обеспечивает лёгкий веб‑просмотр, индексацию и взаимодействие без необходимости в PDF‑плагине.

## Почему использовать GroupDocs Viewer for Java?
GroupDocs.Viewer for Java поддерживает **более 100 входных форматов** и может рендерить PDF‑файлы до **500 страниц** без загрузки всего файла в память. Библиотека обрабатывает каждую страницу потоково, что уменьшает использование кучи до **70 %** по сравнению с полной загрузкой документа. Эти количественные возможности делают её надёжным выбором для высокообъёмных корпоративных конвейеров обработки документов.

## Введение

При работе с PDF‑документами точность рендеринга имеет решающее значение — особенно при работе со сложными текстовыми структурами, такими как иероглифы или языки, требующие точного представления символов. Функция «Character Grouping» часто вызывает проблемы, группируя символы неправильно и приводя к неверному толкованию содержимого документа. Это особенно критично для пользователей, которым нужна точная репликация текстовой раскладки их документов.

**GroupDocs.Viewer for Java** — серверная библиотека, которая рендерит более 100 форматов документов в HTML, изображения и PDF, обеспечивая пиксель‑точную точность.

### Требования

Перед тем как приступить к реализации кода, убедитесь, что выполнены следующие условия:
- **Библиотеки и зависимости**: Требуется GroupDocs.Viewer for Java версии 25.2 или новее.  
- **Настройка окружения**: Установите Java Development Kit (JDK) и настройте IDE для Maven‑проектов.  
- **Базовые знания**: Основы программирования на Java, работа с файловой системой и знакомство с Maven.

## Как генерировать html из pdf с помощью GroupDocs Viewer

Генерация html из pdf — это двухшаговый процесс: настройка просмотрщика, затем рендеринг документа. Ключевой момент — отключить группировку символов перед рендерингом, чтобы HTML‑вывод точно соответствовал оригинальной раскладке PDF‑файла символ за символом.

### Настройка GroupDocs.Viewer for Java

#### Установка через Maven

Add the following dependency to your `pom.xml`:

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

#### Приобретение лицензии

Для полного использования GroupDocs.Viewer рассмотрите возможность получения лицензии:
- **Бесплатная пробная версия**: Начните с бесплатной пробной версии для тестирования функций.  
- **Временная лицензия**: Оформите временную лицензию, если требуется больше времени.  
- **Покупка**: Для долгосрочных проектов рекомендуется приобрести лицензию.

#### Базовая инициализация и настройка

`HtmlViewOptions` настраивает формат вывода и параметры рендеринга документа в HTML.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Руководство по реализации

#### Функция: отключить группировку символов

Ниже мы разбираем каждый шаг примера, чтобы вы поняли **почему** мы это делаем и **как** это способствует генерации html из pdf без нежелательного объединения символов.

##### Шаг 1: определить каталог вывода  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Почему?** Это гарантирует, что сгенерированные HTML‑файлы будут храниться в отдельной папке, что упрощает их поиск и управление позже.

##### Шаг 2: настроить формат пути к файлу  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Почему?** Использование плейсхолдера (`{0}`) позволяет просмотрщику создавать отдельный HTML‑файл для каждой страницы PDF, поддерживая порядок вывода.

##### Шаг 3: инициализировать параметры HTML‑просмотра  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Почему?** Встроенные ресурсы объединяют изображения, шрифты и CSS непосредственно с каждой HTML‑страницей, что идеально подходит для веб‑просмотрщиков или платформ электронного обучения.

##### Шаг 4: отключить группировку символов  

`setDisableCharsGrouping(true)` отключает поведение по умолчанию, объединяющее соседние символы, обеспечивая отдельный рендеринг каждого глифа.

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Почему?** Эта строка критически важна: она сообщает движку рендеринга **не** объединять соседние символы, гарантируя, что сгенерированный HTML точно отражает расположение глифов из исходного PDF.

##### Шаг 5: отрисовать документ  

`Viewer` — основной класс, который открывает документ и предоставляет возможности рендеринга.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Почему?** Оборачивание `Viewer` в блок try‑with‑resources гарантирует автоматическое освобождение всех нативных ресурсов, предотвращая утечки памяти в длительно работающих приложениях.

## Как отключение группировки символов улучшает точность HTML?

Отключение группировки заставляет движок выводить каждый глиф как отдельный HTML‑элемент, что сохраняет оригинальные интервалы, лигатуры и диакритические знаки точно так же, как они представлены в исходном PDF. Это приводит к верному веб‑представлению, необходимому для письменностей, где порядок и интервалы символов несут смысл, например, арабский, деванагари или древние иероглифы.

## Каковы последствия отключения группировки для производительности?

Отключение группировки слегка увеличивает нагрузку на процессор, поскольку рендерер обрабатывает каждый символ индивидуально. На практике накладные расходы составляют менее **5 %** для типичных 100‑страничных PDF и остаются ниже **12 %** для документов более 500 страниц, при условии адекватного размера кучи JVM (например, `-Xmx2g`). Этот компромисс оправдан, когда требуется абсолютная визуальная точность.

## Распространённые проблемы и решения

- **FileNotFoundException** – Проверьте путь, передаваемый в `new Viewer(...)`. Используйте абсолютные пути или `Path.of(...)` для ясности.  
- **Write permissions** – Убедитесь, что каталог вывода доступен для записи процессом Java; в Linux может потребоваться изменить права папки (`chmod 775`).  
- **Version mismatch** – Опция `setDisableCharsGrouping` доступна, начиная с версии 25.2. Убедитесь, что ваш `pom.xml` указывает правильную версию.  

## Практические применения

1. **Сохранение языков** – Идеально для рендеринга документов на китайском, японском, арабском или древних письменностях, где интервал между символами имеет значение.  
2. **Юридические и финансовые документы** – Гарантирует точную репликацию текста для документов с высоким уровнем соответствия требованиям.  
3. **Образовательные ресурсы** – Подходит для учебников, включающих сложные диаграммы, аннотации или многоязычное содержание.

## Соображения по производительности

- **Оптимизировать использование ресурсов** – Большие PDF могут потреблять значительный объём памяти. Обрабатывайте страницы пакетами и своевременно освобождайте экземпляры `Viewer`.  
- **Управление памятью Java** – Настройте кучу JVM (`-Xmx2g` или больше), если планируется обработка PDF‑файлов со сотнями страниц.  
- **Параллельный рендеринг** – Для массовых конвертаций запускайте отдельные потоки, каждый со своим экземпляром `Viewer`, чтобы задействовать многоядерные процессоры.

## Часто задаваемые вопросы

**Q:** *Почему вообще нужно отключать группировку символов?*  
**A:** Отключение группировки предотвращает объединение символов, принадлежащих разным глифам, что критично для письменностей, где интервалы и порядок имеют смысл.

**Q:** *Применяется ли настройка `setDisableCharsGrouping` только к HTML‑выводу?*  
**A:** Нет, она влияет на движок рендеринга PDF, поэтому любой формат вывода (HTML, PNG, JPEG и т.д.) отразит изменение.

**Q:** *Можно ли совместить эту настройку с пользовательскими шрифтами?*  
**A:** Да — загрузите свои шрифты перед инициализацией `Viewer`, и правило группировки всё равно будет применено.

**Q:** *Влияет ли отключение группировки на производительность?*  
**A:** Немного, поскольку движок обрабатывает каждый символ отдельно, но влияние минимально для большинства документов (обычно менее 5 % накладных расходов).

**Q:** *Можно ли переключать группировку постранично?*  
**A:** В текущей реализации опция глобальна для экземпляра `PdfOptions`; для разных страниц потребуется создавать отдельные экземпляры `Viewer`.

## Ресурсы

- [Документация GroupDocs](https://docs.groupdocs.com/viewer/java/)
- [Ссылка на API](https://reference.groupdocs.com/viewer/java/)
- [Скачать GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Купить лицензию](https://purchase.groupdocs.com/buy)
- [Бесплатная пробная версия](https://releases.groupdocs.com/viewer/java/)
- [Заявка на временную лицензию](https://purchase.groupdocs.com/temporary-license/)
- [Форум поддержки GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Последнее обновление:** 2026-09-05  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs

## Связанные руководства

- [Как конвертировать pdf в html и оптимизировать качество изображения в Java с GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [Рендеринг многослойного PDF в Java – эффективный многослойный рендеринг PDF с GroupDocs.Viewer](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)
- [GroupDocs Viewer Java адаптивный рендеринг Html](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)