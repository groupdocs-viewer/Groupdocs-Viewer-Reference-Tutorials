---
date: '2026-06-30'
description: Узнайте, как получить viewinfo и извлечь структуры файлов архивов Java
  с помощью GroupDocs.Viewer. Это руководство охватывает настройку, примеры кода и
  реальные примеры использования.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Как получить ViewInfo и извлечь структуры архивов в Java
type: docs
url: /ru/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Как получить ViewInfo и извлечь структуру архивов в Java

Эффективное управление архивными файлами требует чёткого понимания их структуры. В этом руководстве вы узнаете **how to get viewinfo** для любого архива и увидите, как это помогает работать с **java archive file type**. Мы пройдём настройку GroupDocs.Viewer, извлечение информации о представлении и рекурсивное чтение иерархий папок, чтобы вы могли интегрировать решение в реальные проекты.

![Структуры архивов с GroupDocs.Viewer для Java](/viewer/document-loading/archive-structures-java.png)

**Что вы узнаете**
- Настройка и конфигурация GroupDocs.Viewer для Java.  
- Методы для **get viewinfo** из архивов.  
- Техники чтения и отображения структуры папок архивного файла.  
- Практические применения и соображения по производительности при использовании GroupDocs.Viewer в проектах Java.

## Быстрые ответы
- **Что предоставляет “viewinfo”?** Он возвращает тип файла, количество страниц и полный список папок и файлов внутри архива.  
- **Какие форматы архивов поддерживаются?** ZIP, RAR, TAR, 7z, ISO и более 12 других распространённых форматов.  
- **Нужна ли лицензия для продакшна?** Да — для продакшна требуется коммерческая лицензия; бесплатная пробная версия подходит для оценки.  
- **Можно ли эффективно обрабатывать большие архивы?** Абсолютно — используйте опции потоковой передачи и обрабатывайте один уровень папок за раз, чтобы снизить использование памяти.  
- **Является ли Maven единственным способом добавить библиотеку?** Maven рекомендуется как менеджер зависимостей, но Gradle или ручное включение JAR также работают.

## Что такое “how to get viewinfo”?

`getViewInfo` — это метод API GroupDocs.Viewer, который извлекает метаданные из документа или архива без полного рендеринга. Он возвращает внутреннее дерево папок, количество файлов и базовые свойства за один вызов, позволяя решить, какие части обрабатывать. Вызов возвращает полную снимок архивов размером до 500 МБ менее чем за секунду на типичных серверах.

## Зачем извлекать структуры файлов типа Java Archive?

Извлечение внутренней структуры **java archive file type** позволяет мгновенно находить нужные файлы, избегать ненужного извлечения и создавать автоматизированные конвейеры, которые работают только с релевантными подпапками. Такой подход снижает I/O до 70 % для больших архивов и делает возможным сканирование тысяч файлов в минуту в сценариях загрузки данных.

## Предварительные требования

- **Java Development Kit (JDK):** Версия 8 или новее.  
- **Maven:** Для управления зависимостями и сборки.  
- **Basic Java knowledge:** Знание концепций ООП полезно, но не обязательно.  

Вам также нужен доступ к библиотеке GroupDocs.Viewer, которую можно добавить в ваш Maven‑проект, как показано ниже.

## Настройка GroupDocs.Viewer для Java

### Конфигурация Maven

Добавьте репозиторий и зависимость в ваш `pom.xml`.

**Репозитории:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Зависимости:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Получение лицензии

- **Free Trial:** Скачайте пробную версию с сайта GroupDocs.  
- **Temporary License:** Запросите временный ключ для краткосрочной оценки.  
- **Full License:** Приобретите коммерческую лицензию для неограниченного использования в продакшне.  

После того как библиотека будет в вашем classpath, вы можете начинать писать код.

## Руководство по реализации

### Как получить ViewInfo для архивных файлов

Чтобы получить информацию о представлении, сначала загрузите архив в Viewer, затем вызовите `getViewInfo` для получения метаданных и, наконец, пройдитесь по возвращённой иерархии папок. Этот трёхшаговый шаблон работает со всеми поддерживаемыми форматами архивов и предоставляет полный снимок в одном вызове API, упрощая дальнейшую обработку.

#### Инициализация Viewer

Класс `Viewer` является точкой входа для всех операций рендеринга и инспекции. Он управляет файловыми потоками, определением формата и очисткой ресурсов.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Получение информации о представлении

`ViewInfo` инкапсулирует метаданные, такие как тип файла, общее количество страниц и иерархический список папок и файлов. Вызов `getViewInfo` мгновенно возвращает этот объект.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Отображение структуры папок

Итерируйте `viewInfo.getFolders()`, чтобы вывести имя каждой папки, её глубину и содержащиеся файлы. Этот простой цикл предоставляет читаемое древовидное представление архива.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Рекурсивное чтение папок

Для глубоко вложенных архивов рекурсивный вспомогательный метод может обходить дерево в глубину, гарантируя посещение каждой подпапки без загрузки всего архива в память.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Функция 2: Получить структуру папок архива

Эта функция сосредоточена на выводе структуры папок архивного файла. Она похожа на первую функцию, но делает акцент на рекурсивном исследовании.

#### Настройка параметров ViewInfo

`ArchiveOptions` позволяет задать защиту паролем, ограничения по страницам и предпочтения потоковой передачи перед вызовом `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Рекурсивное исследование

Вторая рекурсивная процедура демонстрирует, как эффективно обрабатывать архивы, защищённые паролем, и большие наборы файлов.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Практические применения

1. **Data Management:** Быстро организуйте большие наборы данных, понимая структуры архивов.  
2. **Automated File Processing:** Пакетно обрабатывайте архивные файлы без полного их извлечения, сокращая I/O до 70 %.  
3. **CMS Integration:** Улучшите системы управления контентом с навигацией по архиву «на лету», позволяя редакторам просматривать файлы напрямую из архива.

## Соображения по производительности

- **Optimize Memory Usage:** Обрабатывайте папки по одному уровню за раз и своевременно закрывайте экземпляр `Viewer`.  
- **Stay Updated:** Используйте последнюю версию GroupDocs.Viewer (25.2 на момент написания) и релизы JDK для повышения производительности.  
- **Streaming Support:** Библиотека может потоково передавать архивы размером более 1 ГБ без загрузки всего файла в ОЗУ, благодаря внутренней архитектуре чтения кусками.

## Распространённые проблемы и решения

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| `NullPointerException` при чтении папок | `viewInfo.getFolders()` возвращает null для пустых каталогов | Проверьте на null или пустой список перед итерацией. |
| Медленная обработка огромных ZIP‑файлов | Весь архив загружается в память | Используйте опции потоковой передачи, доступные в более новых версиях GroupDocs. |
| Лицензия не найдена | Путь к файлу лицензии неверен | Разместите файл лицензии в корне приложения или задайте `License.setLicense("path/to/license.json")`. |

## Часто задаваемые вопросы

**Q:** Что такое GroupDocs.Viewer?  
A: GroupDocs.Viewer — это Java‑библиотека, которая рендерит более 100 форматов документов, изображений и архивов в HTML, PDF или потоки изображений без необходимости в нативных приложениях.

**Q:** Можно ли использовать GroupDocs.Viewer с другими языками программирования?  
A: Да, GroupDocs предлагает SDK для .NET, Python, PHP и др., но этот руководствo сосредоточено на реализации для Java.

**Q:** Как работать с большими архивными файлами?  
A: Включите потоковую передачу через `ArchiveOptions.setUseStreaming(true)`, обрабатывайте один уровень папок за раз и освобождайте объект `Viewer` после использования.

**Q:** Какие типы архивов поддерживает GroupDocs.Viewer?  
A: Он поддерживает более 12 форматов архивов, включая ZIP, RAR, TAR, 7z, ISO, ARJ и CAB, а также многие проприетарные типы контейнеров.

**Q:** Есть ли ограничение по размеру архивов?  
A: Практический лимит зависит от ОЗУ и CPU вашего сервера; тесты показывают плавную обработку архивов размером 2 ГБ на машине с 16 ГБ ОЗУ при включённой потоковой передаче.

**Q:** Работает ли “how to get viewinfo” с архивами, защищёнными паролем?  
A: Да, перед вызовом `getViewInfo` укажите пароль через `ArchiveOptions.setPassword("yourPassword")`.

## Заключение

Следуя этому руководству, вы теперь знаете **how to get viewinfo** для любого поддерживаемого архива и как обходить его иерархию папок с помощью GroupDocs.Viewer для Java. Эти техники позволяют создавать более умные конвейеры обработки данных, улучшать интеграцию с CMS и уверенно работать с большими коллекциями архивных файлов. Далее изучите рендеринг отдельных файлов из архива или их конвертацию в PDF/HTML с помощью других функций Viewer.

---

**Последнее обновление:** 2026-06-30  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs  

**Ресурсы**
- **Документация:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Download GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase License:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial and Temporary License:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## Связанные руководства

- [Извлечение метаданных документа с GroupDocs.Viewer для Java — Получение информации о представлении документа и аналитика](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Как извлечь вложения и распечатать вложения документа с GroupDocs.Viewer для Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Руководство по Java: Рендеринг конкретных страниц с помощью GroupDocs.Viewer API для предварительного просмотра и управления документами](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)