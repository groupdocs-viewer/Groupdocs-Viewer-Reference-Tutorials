---
date: '2026-09-30'
description: Узнайте, как повернуть страницу на 90 градусов в Java с помощью GroupDocs
  Viewer, включая настройку, код и рекомендации по производительности.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Поверните страницу на 90 градусов в Java с помощью GroupDocs Viewer.
  Пошаговое руководство, рекомендации по производительности и реальные примеры использования
  для разработчиков.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Повернуть страницу на 90 градусов с помощью GroupDocs Viewer для Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Повернуть страницу на 90 градусов с помощью GroupDocs Viewer для Java
type: docs
url: /ru/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# Повернуть страницу на 90 градусов с помощью GroupDocs Viewer для Java

Если вам нужно **повернуть страницу на 90 градусов** в документе — будь то PDF, файл Word или таблица — выполнение этой операции программно на Java экономит время, устраняет ручные ошибки и позволяет встроить её в автоматизированные конвейеры. В этом продвинутом руководстве вы узнаете, как повернуть первую страницу любого поддерживаемого документа с помощью **GroupDocs Viewer for Java**, почему эта возможность важна в реальных проектах и как сохранить процесс лёгким и экономным по памяти.

![Повернуть первую страницу документа с помощью GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Быстрые ответы
- **Что означает “rotate page 90 degrees”?** Она поворачивает выбранную страницу по часовой стрелке на четверть оборота.  
- **Какая библиотека обрабатывает вращение?** GroupDocs Viewer for Java предоставляет метод `rotatePage`.  
- **Могу ли я вращать страницы PDF с помощью Java?** Да — используйте тот же вызов `rotatePage`; он работает с PDF, DOCX, XLSX и другими форматами.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшн требуется платная лицензия.  
- **Является ли операция ресурсоёмкой по памяти?** Нет, если своевременно закрывать экземпляр `Viewer`; см. советы по производительности ниже.

## Что такое “rotate page 90 degrees”?
Поворот страницы на 90 градусов переориентирует её из портретного в альбомный режим (или наоборот) без изменения содержимого. Это удобно для презентаций, печати только альбомных графиков или исправления отсканированных документов, снятых боком. Поворот применяется во время рендеринга, оригинальный файл остаётся неизменным.

## Почему вращать страницы программно с помощью GroupDocs Viewer for Java?
GroupDocs Viewer поддерживает **более 50 форматов ввода и вывода** — включая PDF, DOCX, PPTX, XLSX и многие типы изображений — поэтому вы можете рендерить любой документ без внешних конвертеров. API удобен, потокобезопасен и работает на любой среде Java 8+, что делает его надёжным выбором для корпоративной автоматизации, которая должна последовательно обрабатывать десятки типов файлов.

## Предварительные требования

- GroupDocs Viewer for Java (последняя версия)
- JDK 8 или новее
- Maven (или Gradle) для управления зависимостями
- IDE, например IntelliJ IDEA или Eclipse
- Базовое знакомство с Java I/O

## Настройка GroupDocs.Viewer для Java

Добавьте репозиторий GroupDocs и зависимость в ваш `pom.xml`. Этот фрагмент не изменён по сравнению с оригинальным руководством:

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
- **Free trial** – загрузить с сайта GroupDocs.  
- **Temporary license** – запросить, если нужен расширенный период оценки.  
- **Full license** – приобрести для продакшн-развёртываний.

### Базовая инициализация Viewer
Класс `Viewer` является точкой входа, загружает документ и предоставляет методы рендеринга и трансформации. Сохраните код точно как показано:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Как повернуть страницу PDF в Java с помощью GroupDocs Viewer
Загрузите целевой файл с помощью `Viewer`, укажите номер страницы и вызовите `rotatePage`. Метод работает с PDF, DOCX, PPTX, XLSX и любыми другими форматами, поддерживаемыми библиотекой. После вращения вы можете отрендерить документ в новый PDF или передать его напрямую клиенту, гарантируя, что оригинальный файл останется нетронутым.

## Пошаговая реализация: поворот первой страницы на 90 градусов

### 1. Импортировать необходимые пакеты
`PdfViewOptions` указывает Viewer выводить PDF‑файл, а перечисление `Rotation` задаёт угол. Оба класса находятся в пакете `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Определить пути вывода и создать Viewer
Замените пути‑заполнители вашими реальными каталогами. Конструктор `Viewer` принимает объект `File`, указывающий на исходный документ.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Настроить параметры PDF‑просмотра и применить вращение
Метод `rotatePage(int, Rotation)` принимает **1‑based** (нумерация с 1) индекс страницы и значение перечисления `Rotation`. В этом примере мы используем `Rotation.ON_90_DEGREE` для поворота первой страницы по часовой стрелке.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Рендерить документ
Вызов `view` с настроенными параметрами записывает повернутый PDF в папку вывода.

```java
viewer.view(viewOptions);
```

#### Как это работает
- **PdfViewOptions** указывает Viewer генерировать PDF‑файл вывода.  
- **rotatePage(int, Rotation)** вращает только указанную страницу, остальные остаются без изменений.  
- Метод поддерживает три константы вращения: `ON_90_DEGREE`, `ON_180_DEGREE` и `ON_270_DEGREE`.

## Распространённые проблемы и решения

| Симптом | Вероятная причина | Решение |
|---------|-------------------|---------|
| **FileNotFoundException** | Неправильный путь или отсутствующая папка | Убедитесь, что `YOUR_OUTPUT_DIRECTORY` и `YOUR_DOCUMENT_DIRECTORY` существуют и доступны для чтения. |
| **Unsupported file format** | Попытка вращения формата, не поддерживаемого Viewer | Проверьте страницу [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Используется неверный номер страницы (нумерация с 0) | Помните, что `rotatePage` использует индексацию **1‑based**. |
| **Out‑of‑memory errors on large docs** | Рендеринг большого количества крупных файлов в одном потоке | Обрабатывайте документы последовательно или используйте пул потоков с ограниченной параллельностью. |

## Практические применения

1. **Presentation adjustments** – Преобразовать портретный слайд в альбомный «на лету» для лучшего визуального эффекта.  
2. **Bulk document correction** – Автоматизировать исправление отсканированных PDF, снятых боком, экономя часы ручной работы.  
3. **Print‑ready output** – Обеспечить правильную печать альбомных графиков на портретной бумаге без ручного вращения в драйвере принтера.

## Советы по производительности

- **Close resources promptly** – Блок `try‑with‑resources` автоматически освобождает `Viewer`, освобождая память.  
- **Batch processing** – Переиспользуйте один экземпляр `Viewer` на поток, чтобы снизить накладные расходы инициализации.  
- **Monitor memory** – Для документов более 100 МБ потоките вывод на диск вместо удержания всего файла в памяти; GroupDocs Viewer может обрабатывать файлы размером 200 МБ, используя менее 250 МБ ОЗУ.

## Часто задаваемые вопросы

**Q: Можно ли вращать несколько страниц одновременно?**  
A: Да — вызывайте `rotatePage()` для каждого номера страницы, которую нужно вращать, либо в цикле, либо цепочкой вызовов.

**Q: Есть ли способ отменить вращение после рендеринга?**  
A: Не напрямую. Нужно отрендерить документ снова без параметров вращения.

**Q: Какие форматы файлов поддерживают вращение страниц в GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX и многие другие форматы, перечисленные в официальной документации.

**Q: Как автоматически вращать страницы в пакете документов?**  
A: Оберните логику вращения в цикл, который проходит по коллекции путей к файлам, применяя одинаковую конфигурацию `rotatePage` к каждому файлу.

**Q: Какова лучшая практика обработки ошибок во время вращения?**  
A: Поместите использование Viewer в блок `try‑catch`, журналируйте детали исключения и при желании продолжайте обработку следующего файла, чтобы один сбой не останавливал всю партию.

## Ресурсы

- **Документация**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free trial**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Последнее обновление:** 2026-09-30  
**Тестировано с:** GroupDocs Viewer 25.2 for Java  
**Автор:** GroupDocs

## Связанные руководства

- [Как повернуть отдельные страницы PDF с помощью GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Загрузка документа из URL в Java – руководство GroupDocs.Viewer](/viewer/java/document-loading/)
- [Виды документов Groupdocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)