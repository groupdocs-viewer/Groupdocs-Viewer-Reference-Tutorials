---
date: '2026-02-05'
description: Узнайте, как получить viewinfo и извлекать структуры файлов типа Java‑архивов
  с помощью GroupDocs.Viewer. В этом руководстве рассматриваются настройка, примеры
  кода и реальные примеры использования.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Как получить ViewInfo и извлечь структуры архива в Java
type: docs
url: /ru/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Как получить ViewInfo и извлечь структуру архива в Java

Эффективное управление архивными файлами требует чёткого понимания их структуры. В этом руководстве вы узнаете **как получить viewinfo** для любого архива и увидите, как это помогает работать с **java archive file type**. Мы пройдём настройку GroupDocs.Viewer, извлечение информации о представлении и рекурсивное чтение иерархии папок, чтобы вы могли интегрировать решение в реальные проекты.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**Что вы узнаете**
- Настройка и конфигурация GroupDocs.Viewer для Java.  
- Методы **получения viewinfo** из архивов.  
- Приёмы чтения и отображения структуры папок архивного файла.  
- Практические применения и соображения по производительности при использовании GroupDocs.Viewer в Java‑проектах.

## Быстрые ответы
- **Что предоставляет “viewinfo”?** Возвращает тип файла, количество страниц и список папок архива.  
- **Какие архивы поддерживаются?** ZIP, RAR, TAR и другие распространённые форматы.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; для продакшна требуется коммерческая лицензия.  
- **Можно ли обрабатывать большие архивы?** Да — используйте потоковую передачу и правильное управление памятью, как показано ниже.  
- **Требуется ли Maven?** Maven — рекомендуемый способ управления зависимостями GroupDocs.Viewer.

## Что такое “how to get viewinfo”?
`getViewInfo` — метод API GroupDocs.Viewer, который извлекает метаданные о документе или архиве без полного рендеринга содержимого. Для архивов он раскрывает внутреннее дерево папок, позволяя решить, какие части рендерить или обрабатывать дальше.

## Почему стоит извлекать структуры файлов типа **java archive file type**?
Понимание внутреннего расположения **java archive file type** (например, ZIP, RAR) позволяет вам:
- Быстро находить нужные файлы без полной распаковки.  
- Создавать автоматизированные конвейеры, обрабатывающие только релевантные подпапки.  
- Интегрировать навигацию по архиву в системы управления контентом или процессы ingest‑а данных.

## Предварительные требования

- **Java Development Kit (JDK):** версия 8 или новее.  
- **Maven:** для управления зависимостями и сборкой.  
- **Базовые знания Java:** знакомство с ООП будет полезным, но не является обязательным.

Вам также нужен доступ к библиотеке GroupDocs.Viewer, которую можно добавить в Maven‑проект, как показано ниже.

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

### Приобретение лицензии

- **Бесплатная пробная версия:** скачайте её с сайта GroupDocs.  
- **Временная лицензия:** запросите временный ключ для краткосрочной оценки.  
- **Полная лицензия:** приобретите коммерческую лицензию для неограниченного использования в продакшне.

После того как библиотека окажется в classpath, можно приступать к кодированию.

## Руководство по реализации

### Как получить ViewInfo для архивных файлов

В этом разделе показаны точные шаги вызова `getViewInfo` и чтения иерархии папок.

#### Инициализация Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Получение информации о представлении

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Отображение структуры папок

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Рекурсивное чтение папок

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

Эта функция фокусируется на выводе структуры папок архивного файла. Она похожа на первую, но подчёркивает рекурсивное исследование.

#### Настройка параметров ViewInfo

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Рекурсивное исследование

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Практические применения

1. **Управление данными:** Быстро организуйте большие наборы данных, понимая структуру архивов.  
2. **Автоматическая обработка файлов:** Пакетно обрабатывайте архивные файлы без полной их распаковки.  
3. **Интеграция с CMS:** Улучшите системы управления контентом за счёт навигации по архиву «на лету».

## Соображения по производительности

- **Оптимизация использования памяти:** Обрабатывайте папки по одной и своевременно закрывайте экземпляр `Viewer`.  
- **Следите за обновлениями:** Используйте последнюю версию GroupDocs.Viewer и актуальные релизы JDK для повышения производительности.

## Распространённые проблемы и решения

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| `NullPointerException` при чтении папок | `viewInfo.getFolders()` возвращает null для пустых каталогов | Проверяйте значение на null или пустой список перед итерацией. |
| Медленная обработка огромных ZIP‑файлов | Весь архив загружается в память | Используйте потоковые опции, доступные в более новых версиях GroupDocs. |
| Лицензия не найдена | Неправильный путь к файлу лицензии | Поместите файл лицензии в корень приложения или задайте `License.setLicense("path/to/license.json")`. |

## Часто задаваемые вопросы

**В: Что такое GroupDocs.Viewer?**  
О: Это мощная Java‑библиотека для рендеринга документов, включая архивы, в форматы HTML, изображение и PDF.

**В: Можно ли использовать GroupDocs.Viewer с другими языками программирования?**  
О: Да, GroupDocs предлагает SDK для разных платформ, но в этом руководстве рассматривается реализация на Java.

**В: Как обрабатывать большие архивные файлы?**  
О: Применяйте эффективные практики управления памятью и, при необходимости, разбивайте архивы на части.

**В: Какие типы архивов поддерживает GroupDocs.Viewer?**  
О: Поддерживаются различные форматы, включая ZIP, RAR, TAR и другие.

**В: Есть ли ограничение на размер обрабатываемых архивов?**  
О: Ограничения зависят от ресурсов вашей системы. Тестируйте в целевой среде, чтобы определить практические пределы.

**В: Работает ли “how to get viewinfo” с архивами, защищёнными паролем?**  
О: Да, пароль можно передать через `ArchiveOptions.setPassword("yourPassword")` перед вызовом `getViewInfo`.

## Заключение

Следуя этому руководству, вы теперь знаете **как получить viewinfo** для любого поддерживаемого архива и как обходить его иерархию папок с помощью GroupDocs.Viewer для Java. Эти приёмы позволяют создавать более умные конвейеры обработки данных, улучшать интеграцию с CMS и уверенно работать с большими коллекциями архивных файлов. Далее изучайте рендеринг отдельных файлов из архива или их конвертацию в PDF/HTML с помощью других возможностей Viewer.

---

**Последнее обновление:** 2026-02-05  
**Тестировано с:** GroupDocs.Viewer 25.2 для Java  
**Автор:** GroupDocs  

**Ресурсы**
- **Документация:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API‑справочник:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Скачать GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Приобрести лицензию:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Бесплатная пробная версия и временная лицензия:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)