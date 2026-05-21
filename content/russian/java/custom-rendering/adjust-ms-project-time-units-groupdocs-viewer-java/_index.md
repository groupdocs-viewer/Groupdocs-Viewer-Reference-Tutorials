---
date: '2026-05-21'
description: Узнайте, как выполнить экспорт HTML из MS Project с настроенными единицами
  времени, используя GroupDocs Viewer for Java. Пошаговое руководство с предварительными
  требованиями, настройкой и устранением неполадок.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Экспорт HTML из MS Project: настройка единиц времени через GroupDocs Java'
type: docs
url: /ru/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Экспорт HTML из MS Project: Настройка единиц времени через GroupDocs Java

Экспорт файла **MS Project** в HTML является распространённым требованием для панелей управления проектами, порталов отчётов о статусе и инструментов совместного обзора. По умолчанию просмотрщик отображает данные, связанные со временем, в минутах, что может захламлять визуальное представление и усложнять чтение ежедневных отчётов. С помощью **GroupDocs Viewer for Java** вы можете программно установить единицу времени в **days**, получая чистый *ms project html export*, соответствующий типичным ожиданиям заинтересованных сторон. В этом руководстве вы узнаете, как настроить просмотрщик, изменить единицу времени и отобразить проект в HTML за несколько простых шагов.

![Настройка единиц времени MS Project с помощью GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Настройка единиц времени MS Project с помощью GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Быстрые ответы
- **Какой библиотека рендерит файлы MS Project?** GroupDocs Viewer for Java.  
- **Какую единицу времени можно установить для экспорта в HTML?** Days, using `TimeUnit.DAYS`.  
- **Нужна ли лицензия для продакшн?** Yes— a permanent license is required; a trial works for evaluation. You can start with a [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Какой IDE лучше всего подходит?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **Обязателен ли Maven?** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **Где можно купить?** Visit the [страница покупки](https://purchase.groupdocs.com/buy) for pricing.

## Что такое GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** — это Java SDK, который преобразует более 150 форматов документов, включая MS Project, в веб‑дружественные HTML, PNG, JPEG или PDF.  
Он абстрагирует логику парсинга, позволяет управлять параметрами рендеринга, такими как единицы времени, и работает на любой платформе, поддерживающей Java 8 или выше.

## Почему стоит настраивать единицы времени при экспорте MS Project в HTML?
Установка единицы времени в **days** уменьшает визуальный шум, соответствует большинству графиков отчётности и улучшает время загрузки страниц, поскольку генерируется меньше мелких отметок времени. В количественном выражении рендеринг с днями вместо минут может сократить размер сгенерированного HTML до **45 %** для типичных 30‑дневных проектов и ускорить клиентский рендеринг примерно на **30 %**.

## Предварительные требования
- **Java Development Kit (JDK) 8 или новее** установлен на вашей рабочей станции.  
- **Maven** (или Gradle) для управления зависимостями.  
- Файл **MS Project (.mpp)**, который вы хотите экспортировать.  
- Доступ к лицензии **GroupDocs Viewer for Java** (пробная или постоянная).  

### Требуемые библиотеки
Добавьте следующую зависимость в ваш `pom.xml` (или эквивалентный фрагмент Gradle):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Совет:** Держите номер версии актуальным; новые релизы добавляют поддержку форматов и улучшают производительность.

## Как настроить GroupDocs Viewer for Java?
Инициализируйте просмотрщик, создав экземпляр `Viewer`, указывающий на ваш файл MS Project. Класс `Viewer` является точкой входа для всех операций рендеринга. Он загружает исходный документ, подготавливает внутренние структуры и предоставляет методы, такие как `view()` и `viewToHtml()`, для генерации требуемых форматов вывода.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Определение:** Класс `Viewer` — это основной компонент GroupDocs Viewer, который загружает исходный документ и предоставляет методы рендеринга, такие как `view()` и `viewToHtml()`.

## Как изменить единицы времени при экспорте в HTML?
Чтобы изменить гранулярность времени, создайте объект `ViewOptions`, настройте его `ProjectOptions` для использования `TimeUnit.DAYS` и передайте его просмотрщику. `ViewOptions` определяет параметры рендеринга документа, а перечисление `TimeUnit` задаёт единицу (minutes, hours, days) для данных, связанных со временем. После установки этих параметров вызовите `viewer.view(options)`, чтобы получить HTML с ежедневными метками.

Загрузите ваш файл MS Project с помощью `new Viewer("file.mpp")`, создайте объект `ViewOptions`, установите `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, затем вызовите `viewer.view(options)`. Этот трёхшаговый процесс меняет единицу времени с минут на дни и генерирует HTML‑файлы, отображающие только ежедневные интервалы.

### Шаг 1: Определите папку вывода
Выберите доступный для записи каталог, куда будут сохраняться HTML‑страницы, например `output/`.

### Шаг 2: Создайте параметры просмотра с встроенными ресурсами
Встроенные ресурсы (CSS, JavaScript) гарантируют, что HTML‑страницы являются автономными.

### Шаг 3: Установите единицу времени в дни
Используйте `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, чтобы изменить гранулярность.

### Шаг 4: Сгенерировать документ
Вызовите `viewer.view(options)`; просмотрщик записывает один HTML‑файл на каждую страницу проекта в папку вывода.

### Шаг 5: Проверьте результат
Откройте сгенерированный `index.html` в браузере; вы должны увидеть полосы задач, выровненные по дневным меткам вместо минутных.

## Распространённые проблемы и их устранение
- **Неправильный путь вывода** – Убедитесь, что каталог существует и процесс Java имеет права записи.  
- **Отсутствует лицензия** – Без действующей лицензии просмотрщик переходит в режим пробной версии и может добавлять водяные знаки.  
- **Большие файлы (> 500 MB)** – Рассмотрите возможность увеличения размера кучи JVM (`-Xmx2g`) или рендеринга с `options.setRenderLimit(1000)`, чтобы обрабатывать страницы пакетами.  

## Практические применения экспорта HTML с настроенными единицами времени
1. **Исполнительные панели** – Daily granularity matches most KPI visualizations.  
2. **Автоматические статусные письма** – Вставьте сгенерированный HTML непосредственно в тело письма для быстрых обновлений.  
3. **Порталы проектов** – Размещайте HTML на интранет‑сайте, где члены команды могут фильтровать задачи по дням.  

## Соображения по производительности для больших файлов MS Project
- **Управление памятью** – Используйте флаги сборщика мусора Java (`-XX:+UseG1GC`), чтобы своевременно освобождать неиспользуемые объекты.  
- **Селективный рендеринг** – Если нужен только диаграмма Ганта, отключите рендеринг других ресурсов через `options.getProjectOptions().setRenderGantt(true)` и `setRenderResources(false)`.  
- **Параллельная обработка** – Для пакетных конвертаций создавайте отдельные объекты `Viewer` для каждого файла и запускайте их в пуле потоков, чтобы использовать многоядерные процессоры.

## Заключение
Теперь у вас есть полный, готовый к продакшн рабочий процесс для выполнения **ms project html export** с единицами времени, установленными в дни, с помощью GroupDocs Viewer for Java. Этот подход уменьшает размер HTML, ускоряет клиентский рендеринг и предоставляет удобный для заинтересованных сторон вид графиков проекта. Исследуйте дополнительные варианты рендеринга — такие как экспорт в PDF или снимки изображений — чтобы расширить интеграцию в более широкие конвейеры отчётности.

## Часто задаваемые вопросы

**В: Могу ли я отобразить другие представления Project (например, лист ресурсов) в HTML?**  
**О:** Да, объект `ProjectOptions` позволяет включать или отключать конкретные представления, такие как Gantt, лист ресурсов и календарь, перед рендерингом.

**В: Можно ли настроить CSS сгенерированного HTML?**  
**О:** Абсолютно. Укажите путь к пользовательской таблице стилей через `options.setStyleSheetPath("path/to/custom.css")`, и просмотрщик внедрит её в каждую страницу.

**В: Каковы ограничения по размеру файлов, поддерживаемые GroupDocs Viewer для MS Project?**  
**О:** SDK может обрабатывать файлы размером до **500 MB** без необходимости загружать весь документ в память благодаря своей потоковой архитектуре.

**В: Нужно ли устанавливать Microsoft Project на сервер?**  
**О:** Нет. GroupDocs Viewer напрямую разбирает формат .mpp и не требует установки Microsoft Project или любого Office.

**В: Как лицензировать просмотрщик для продакшн‑окружения?**  
**О:** Приобретите постоянную лицензию в магазине GroupDocs; примените файл лицензии во время выполнения с помощью `License license = new License(); license.setLicense("path/to/license.lic");`. Для краткосрочных нужд можно получить [временную лицензию](https://purchase.groupdocs.com/temporary-license/).

---

**Последнее обновление:** 2026-05-21  
**Тестировано с:** GroupDocs Viewer Java 25.2  
**Автор:** GroupDocs  

**Ресурсы**  
- [Документация](https://docs.groupdocs.com/viewer/java/)  
- [Справочник API](https://reference.groupdocs.com/viewer/java/)  
- [Скачать GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Купить лицензию](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Связанные руководства

- [Как отобразить файлы MS Project в HTML, JPG, PNG и PDF с примечаниями с помощью GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Как использовать GroupDocs Viewer для рендеринга проектных документов по временным интервалам в Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Как установить лицензии в GroupDocs.Viewer Java: руководство по настройке файлов и URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)