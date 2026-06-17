---
date: '2026-06-05'
description: Узнайте, как конвертировать docx в jpeg с помощью GroupDocs Viewer for
  Java, охватывая настройку, конфигурацию и практический рендеринг изображений.
keywords:
- convert docx to jpeg
- convert word to image
- GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  headline: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  name: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  steps:
  - name: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
    text: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
  - name: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
    text: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
  - name: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
    text: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
  type: HowTo
- questions:
  - answer: '`DocumentSplitter` allows you to divide a large document into separate
      parts for easier processing. Split the source file into smaller sections using
      `DocumentSplitter` before rendering, or process pages in sequential batches
      to keep memory usage low.'
    question: How do I handle documents larger than 500 pages?
  - answer: Yes, replace `JpgViewOptions` with `PngViewOptions` and adjust the file‑path
      pattern accordingly.
    question: Can I output PNG instead of JPEG?
  - answer: A free trial license works for evaluation and development, but a commercial
      license is required for production deployments.
    question: Is a license mandatory for development builds?
  - answer: Absolutely. Pass the password to the `Viewer` constructor to unlock the
      document before rendering.
    question: Does the library support password‑protected DOCX files?
  - answer: GroupDocs.Viewer for Java is compatible with Java 8, 11, and 17.
    question: What Java versions are supported?
  type: FAQPage
title: Как конвертировать DOCX в JPEG с помощью GroupDocs Viewer for Java
type: docs
url: /ru/java/rendering-basics/groupdocs-viewer-java-render-docx-to-image/
weight: 1
---

# Преобразование DOCX в JPEG с помощью GroupDocs Viewer для Java

Преобразование **DOCX в JPEG** позволяет делиться страницами документов в виде легковесных изображений, которые отображаются одинаково во всех браузерах и почтовых клиентах. В этом руководстве вы узнаете, как использовать **GroupDocs.Viewer for Java**, чтобы превратить файл Word в изображения JPEG высокого качества, настроить размеры и эффективно управлять ресурсами.

![Отображение DOCX в изображение с помощью GroupDocs.Viewer for Java](/viewer/rendering-basics/render-docx-to-image.png)

[Отображение DOCX в изображение с помощью GroupDocs.Viewer for Java](/viewer/rendering-basics/render-docx-to-image.png)

## Быстрые ответы
- **Какой библиотекой осуществляется преобразование DOCX → JPEG?** GroupDocs.Viewer for Java.  
- **Сколько строк кода требуется?** Всего две строки для загрузки и рендеринга файла.  
- **Можно ли задать пользовательский размер изображения?** Да, с помощью `JpgViewOptions` можно задать ширину и высоту.  
- **Требуется ли лицензия для продакшн?** Необходима коммерческая лицензия; доступна бесплатная пробная версия.  
- **Работает ли он с большими документами?** Да, он обрабатывает файлы до 500 страниц, при этом потребление памяти не превышает 200 МБ.

## Что такое «преобразование docx в jpeg»?
Преобразование файла DOCX в JPEG создает одно изображение на каждую страницу, сохраняя оригинальное расположение, шрифты и графику. Каждый JPEG может отображаться в браузерах, встраиваться в электронные письма или использоваться как миниатюры. Этот формат легковесный, широко поддерживается и идеально подходит для предварительного просмотра документов без необходимости установки Microsoft Word или дополнительных плагинов.

## Почему стоит использовать GroupDocs Viewer для Java для этого преобразования?
GroupDocs.Viewer поддерживает **более 50 форматов ввода и вывода** и может рендерить документы до **500 страниц** менее чем за **2 секунды на страницу** на стандартном серверном оборудовании. API работает без установленного Microsoft Office, гарантируя сохранение макета и низкое потребление памяти.

## Предварительные требования
- **Java Development Kit** 8 или новее.  
- **Maven** для управления зависимостями (или ручное включение JAR).  
- **GroupDocs.Viewer for Java** библиотека (доступна для скачивания с официального сайта).  
- Базовое знакомство со структурой проекта Java.

## Настройка GroupDocs Viewer для Java

Чтобы добавить библиотеку в Maven‑проект, вставьте следующую зависимость в ваш `pom.xml`:

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
GroupDocs предлагает бесплатную пробную версию для ознакомления с функциями. Для длительного использования получите временную или приобретённую лицензию через их официальный сайт.

## Как преобразовать DOCX в JPEG?
Класс `Viewer` читает документ и предоставляет возможности рендеринга.  
`JpgViewOptions` настраивает параметры вывода JPEG, такие как размер, качество и именование файлов.

Для преобразования создайте экземпляр `Viewer`, указав путь к DOCX, создайте `JpgViewOptions`, указывающий на папку вывода, при необходимости задайте размеры и качество, и вызовите `viewer.view(options)`. Библиотека обрабатывает каждую страницу и сохраняет файл JPEG согласно указанному шаблону именования.

## Руководство по реализации

### Рендеринг DOCX в JPEG

Преобразуйте документ Word в изображения JPEG для предварительного просмотра или обмена.

#### Пошаговая реализация

**1. Настройка каталога вывода**  
Укажите папку, в которой будут сохраняться отрендеренные JPEG:

```java
import com.groupdocs.viewer.Viewer;

public class DocumentRenderer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
            // Configuration and rendering logic goes here
        }
    }
}
```

**2. Указание формата пути к файлу**  
Создайте шаблон именования, включающий номер страницы, например `page_{0}.jpg`:

```java
import java.nio.file.Path;

// Define output directory using Path API
Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("rendered_document");
```

**3. Настройка параметров изображения**  
`JpgViewOptions` позволяет задать ширину, высоту и качество. Например, 1024 × 768 пикселей при качестве 90 %:

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**4. Рендеринг документа**  
Используйте блок try‑with‑resources, чтобы экземпляр `Viewer` закрывался автоматически, освобождая нативные ресурсы и предотвращая утечки памяти:

```java
import com.groupdocs.viewer.options.JpgViewOptions;

// Create JpgViewOptions with specified path format
JpgViewOptions viewOptions = new JpgViewOptions(pageFilePathFormat);

// Set custom width and height for each image
viewOptions.setWidth(600);  // Image width in pixels
viewOptions.setHeight(800); // Image height in pixels
```

### Распространённые проблемы и решения
- **Проблемы с путём к файлу** – Убедитесь, что каталог вывода существует и приложение имеет права на запись.  
- **Управление памятью** – Для документов более 300 страниц рассмотрите обработку страниц пакетами и вызов `System.gc()` после каждого пакета.  
- **Неподдерживаемые элементы** – Некоторые продвинутые функции Word (например, встроенные макросы) игнорируются при рендеринге; они не влияют на визуальный результат.

## Практические применения
1. **Создание превью** – Показывайте миниатюры документов в системе управления контентом без необходимости полноэкранного просмотрщика.  
2. **Вложения в письма** – Встраивайте JPEG‑изображения постранично в письма, чтобы избежать ограничений по размеру вложений.  
3. **Отображение в вебе** – Рендерьте страницы как изображения для быстрой загрузки при низкой пропускной способности сети.

## Соображения по производительности
- **Управление ресурсами** – Всегда используйте try‑with‑resources для закрытия `Viewer`.  
- **Размеры изображения** – Меньшие размеры снижают использование ОЗУ; выбирайте минимальный размер, удовлетворяющий требованиям к качеству.  
- **Асинхронная обработка** – Для массовых преобразований запускайте задачи рендеринга в отдельном пуле потоков, чтобы UI оставался отзывчивым.

## Часто задаваемые вопросы

**В: Как обрабатывать документы более 500 страниц?**  
О: `DocumentSplitter` позволяет разделить большой документ на отдельные части для более простой обработки. Разделите исходный файл на более мелкие секции с помощью `DocumentSplitter` перед рендерингом или обрабатывайте страницы последовательными пакетами, чтобы снизить потребление памяти.

**В: Можно ли выводить PNG вместо JPEG?**  
О: Да, замените `JpgViewOptions` на `PngViewOptions` и соответственно измените шаблон пути к файлу.

**В: Обязательна ли лицензия для сборок разработки?**  
О: Бесплатная пробная лицензия подходит для оценки и разработки, но для продакшн‑развертываний требуется коммерческая лицензия.

**В: Поддерживает ли библиотека DOCX‑файлы, защищённые паролем?**  
О: Да. Передайте пароль в конструктор `Viewer`, чтобы разблокировать документ перед рендерингом.

**В: Какие версии Java поддерживаются?**  
О: GroupDocs.Viewer for Java совместим с Java 8, 11 и 17.

## Ресурсы
- **Документация**: [Документация GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Справочник API**: [Справочник API GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Скачать GroupDocs.Viewer**: [Страница загрузки](https://releases.groupdocs.com/viewer/java/)
- **Приобрести лицензию**: [Купить GroupDocs](https://purchase.groupdocs.com/buy)
- **Бесплатная пробная версия**: [Попробовать GroupDocs бесплатно](https://releases.groupdocs.com/viewer/java/)
- **Временная лицензия**: [Получить временную лицензию](https://purchase.groupdocs.com/temporary-license/)
- **Форум поддержки**: [Форум поддержки GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Последнее обновление:** 2026-06-05  
**Тестировано с:** GroupDocs.Viewer 23.12 for Java  
**Автор:** GroupDocs

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);
}
```

## Связанные руководства

- [Как преобразовать файлы DOCX в PNG с помощью GroupDocs.Viewer для Java](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)
- [Как преобразовать DOCX в HTML с помощью GroupDocs.Viewer для Java: пошаговое руководство](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Рендеринг файлов DOCX из InputStream в Java с использованием GroupDocs.Viewer](/viewer/java/rendering-basics/render-docx-from-inputstream-groupdocs-viewer-java/)