---
date: '2026-06-15'
description: Узнайте, как конвертировать Excel в PDF Java и разделять листы Excel
  по строкам и столбцам с помощью GroupDocs Viewer. Включает настройку, код и лучшие
  практики.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Конвертировать Excel в PDF Java и разделить листы по строкам и столбцам
type: docs
url: /ru/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Конвертировать Excel в PDF Java и разбить листы по строкам и столбцам (Java)

Большие рабочие книги Excel часто содержат больше данных, чем можно удобно отобразить на одном экране или печатной странице. **convert excel to pdf java** — распространённое требование, когда нужен статический, удобный для обмена формат, а **разделение листов Excel по строкам и столбцам** упрощает работу с данными в веб‑ или печатных макетах. В этом руководстве мы рассмотрим обе задачи с использованием **GroupDocs Viewer for Java**, покажем, как настроить разбиение на страницы, и объясним рекомендации по производительности и устранению неполадок.

![Разделить листы Excel по строкам и столбцам с помощью GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Разделить листы Excel по строкам и столбцам с помощью GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Быстрые ответы
- **Какая библиотека используется?** GroupDocs Viewer for Java.  
- **Можно ли разделять как по строкам, так и по столбцам?** Да — можно задать rows‑per‑page и columns‑per‑page одновременно.  
- **Нужна ли лицензия?** Пробная или временная лицензия подходит для разработки; для продакшн‑использования требуется полная лицензия.  
- **Какие форматы вывода поддерживаются?** Показан HTML (встроенные ресурсы); PDF можно сгенерировать с теми же параметрами.  
- **Требуется ли Maven?** Maven — рекомендуемый способ управления зависимостями.  
- **Можно ли также конвертировать Excel в PDF?** Конечно — просто замените `HtmlViewOptions` на `PdfViewOptions` и используйте те же настройки разбиения.

## Что такое «Как разделить Excel»?
Разделение листа Excel означает деление единственного листа на несколько страниц или файлов на основе фиксированного количества строк, столбцов или их комбинации. Эта техника полезна, когда необходимо создавать пагинированные отчёты, встраивать данные в веб‑страницы или генерировать печатные секции без загрузки всей книги сразу.

## Почему использовать GroupDocs Viewer for Java?
GroupDocs Viewer обрабатывает электронные таблицы за один проход и автоматически разбивает их на страницы, устраняя необходимость ручных расчётов. **Быстрый рендеринг обрабатывает книгу XLSX в 250 страниц менее чем за 2 секунды на типичном 2‑ядерном сервере**, и **библиотека поддерживает более 50 форматов ввода и вывода**, включая XLS, XLSX, CSV, PDF и HTML. Она работает на любой платформе, совместимой с JVM — Windows, Linux, macOS, Docker‑контейнерах или облачных безсерверных средах — так что её можно интегрировать где угодно, где живёт ваше Java‑приложение.

## Требования
- Java 17 или новее установлен.  
- IDE, например IntelliJ IDEA или Eclipse.  
- Maven для управления зависимостями.  
- Базовые знания Java и знакомство с работой с файлами Excel.

### Требуемые библиотеки, версии и зависимости
Добавьте репозиторий GroupDocs и зависимость viewer в ваш `pom.xml`:

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
Получите бесплатную пробную, временную лицензию или приобретите полную лицензию на сайте [GroupDocs](https://purchase.groupdocs.com/buy).

## Как конвертировать Excel в PDF Java?

Класс `Viewer` — основной компонент GroupDocs Viewer, который загружает документ и предоставляет методы рендеринга в различные форматы вывода. `SpreadsheetOptions` позволяет управлять настройками разбиения, такими как rows‑per‑page и columns‑per‑page для рендеринга таблиц.

Загрузите ваш Excel‑файл с помощью `new Viewer("source.xlsx")`, настройте `SpreadsheetOptions` для разбиения и вызовите `viewer.view(pdfOptions, stream)` — этот единственный вызов преобразует книгу в PDF, учитывая заданные ограничения по строкам/столбцам. Конверсия сохраняет формулы, изображения и стили ячеек, создавая точную PDF‑копию, готовую к распространению.

## Как разделить листы Excel по строкам

Разделение по строкам создаёт серию HTML‑страниц, каждая из которых содержит фиксированное количество строк (например, 15). Такой подход идеален для панелей, отображающих ограниченное число записей за один просмотр. Viewer сгенерирует отдельные HTML‑файлы, такие как `page_0.html`, `page_1.html` и т.д., каждый из которых содержит указанное количество строк. Это упрощает загрузку только необходимой части в веб‑интерфейсе, снижая трафик и время рендеринга.

### Определение якоря
`Viewer` — основной класс GroupDocs Viewer, который загружает документ и управляет рендерингом в выбранный формат вывода.

### Пошаговая реализация

#### Шаг 1: Настройка путей и инициализация Viewer
Сначала укажите, где будут сохраняться разделённые страницы, и создайте экземпляр `Viewer` для исходной книги.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Шаг 2: Настройка количества строк на страницу
Укажите Viewer, сколько строк должно быть на каждой странице.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Шаг 3: Рендеринг документа
Наконец, выполните рендеринг книги, используя заданные параметры.

```java
viewer.view(viewOptions);
```

## Как разделить листы Excel по строкам и столбцам

Иногда одной странице требуется показать матрицу строк **и** столбцов (например, 15 строк × 7 столбцов). Это даёт полный контроль над макетом каждой HTML‑страницы. Получающиеся страницы отображают прямоугольный блок ячеек, например строки 1‑15 и столбцы A‑G на первой странице, строки 16‑30 и столбцы H‑N на следующей. Такой разбор по сетке полезен для создания печатных отчётов, подходящих под стандартные размеры бумаги.

### Определение якоря
`SpreadsheetOptions` настраивает, сколько строк и столбцов будет отображаться на каждой сгенерированной странице.

### Пошаговая реализация

#### Шаг 1: Настройка путей и инициализация Viewer
Настройка аналогична примеру только для строк, меняется лишь имя файла.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Шаг 2: Настройка количества строк и столбцов на страницу
Укажите обе размерности, чтобы создать разбиение в виде сетки.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Шаг 3: Рендеринг документа
Выполните рендеринг, используя тот же вызов `view`.

```java
viewer.view(options);
```

## Практические применения
- **Generate Excel report Java**: Преобразовать большие финансовые модели в серию пагинированных HTML‑отчетов.  
- **GroupDocs Viewer Excel**: Встраивать разделённые страницы непосредственно в веб‑портал для интерактивного исследования данных.  
- **Render Excel HTML Java**: Обслуживать сгенерированные HTML‑страницы через servlet или Spring‑контроллер для быстрого клиентского рендеринга.  

## Соображения по производительности
- **Использование памяти** – Большие книги могут потреблять значительный heap; рассмотрите увеличение параметра JVM `-Xmx`.  
- **Размер чанка** – Выбирайте количество строк/столбцов, которое балансирует размер страницы и скорость рендеринга.  
- **Обновления версии** – Держите GroupDocs Viewer в актуальном состоянии, чтобы получать улучшения производительности; последняя версия 25.2 повышает скорость рендеринга до 30 % по сравнению с 24.x.  

## Распространённые проблемы и устранение неполадок
| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| `OutOfMemoryError` | Рендеринг очень большого листа с слишком большим количеством строк на страницу | Уменьшить `countRowsPerPage` или увеличить heap JVM |
| Пустые файлы вывода | Неправильный путь к файлу или отсутствие прав на запись | Проверьте, что `outputDirectory` существует и доступен для записи |
| HTML‑ресурсы не загружаются | Используется `forEmbeddedResources`, но файлы обслуживаются с другого базового URL | Обслуживайте всю папку вывода или переключитесь на `forExternalResources` |

## Часто задаваемые вопросы

**Q: Можно ли также конвертировать Excel в PDF?**  
A: Да. Замените `HtmlViewOptions` на `PdfViewOptions` и сохраните ту же конфигурацию `SpreadsheetOptions`.

**Q: Можно ли разделять на основе содержимого ячеек, а не фиксированных строк/столбцов?**  
A: Разделение по содержимому не реализовано в GroupDocs Viewer, но вы можете предварительно обработать книгу с помощью Apache POI, создав отдельные листы перед рендерингом.

**Q: Поддерживает ли GroupDocs Viewer старые форматы Excel (XLS)?**  
A: Абсолютно. Viewer работает с XLS, XLSX, CSV и другими форматами электронных таблиц.

**Q: Как встроить сгенерированный HTML в представление Spring MVC?**  
A: Обслуживайте папку вывода как статический ресурс и ссылаться на сгенерированные `page_0.html`, `page_1.html` и т.д. из шаблонов Thymeleaf или JSP.

**Q: Какая лицензия нужна для коммерческого развертывания?**  
A: Требуется полная производственная лицензия от GroupDocs; пробные лицензии предназначены только для оценки.

## Ресурсы
- **Документация**: [Документация GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Справочник API**: [Справочник API GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Скачать**: [Релизы GroupDocs Viewer Java](https://releases.groupdocs.com/viewer/java/)
- **Покупка**: [Купить лицензию GroupDocs](https://purchase.groupdocs.com/buy)
- **Бесплатная проба**: [Бесплатная проба GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Временная лицензия**: [Получить временную лицензию](https://purchase.groupdocs.com/temporary-license/)
- **Поддержка**: [Форум поддержки GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Последнее обновление:** 2026-06-15  
**Тестировано с:** GroupDocs Viewer 25.2 for Java  
**Автор:** GroupDocs  

## Связанные руководства

- [Отображение скрытых строк и столбцов в Java‑таблицах с использованием GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Пропуск рендеринга пустых строк в Java с помощью GroupDocs.Viewer: Руководство по производительности](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Полное руководство: Конвертировать Excel 2003 XML в HTML/JPG/PNG/PDF с помощью GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)