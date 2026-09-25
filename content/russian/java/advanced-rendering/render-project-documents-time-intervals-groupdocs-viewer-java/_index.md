---
date: '2026-09-25'
description: Узнайте, как создать html view mpp с GroupDocs Viewer for Java, отображая
  проектные документы по временным интервалам с step‑by‑step кодом.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Создайте html view mpp с GroupDocs Viewer for Java для отображения
  файлов Microsoft Project по определённым временным интервалам. Следуйте step‑by‑step
  настройке, лицензированию и code snippets для точной визуализации временной шкалы.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: Создать html view mpp с GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: Создать html view mpp с GroupDocs Viewer (Java)
type: docs
url: /ru/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Как использовать GroupDocs Viewer для рендеринга проектных документов по временным интервалам в Java

В этом руководстве вы узнаете, как **create html view mpp** с GroupDocs Viewer для Java, позволяя рендерить только те части файла Microsoft Project, которые находятся в заданном диапазоне дат начала и окончания. Мы пройдем настройку Maven, лицензирование и точные вызовы API, необходимые для встраивания точных представлений временной шкалы непосредственно в ваши приложения.

![Отображение проектных документов по временным интервалам с GroupDocs.Viewer для Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Для предварительного просмотра см. [Отображение проектных документов по временным интервалам с GroupDocs.Viewer для Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Быстрые ответы
- **Что делает эта функция?** Она рендерит только ту часть файла Microsoft Project, которая находится между датой начала и датой окончания.  
- **Какой формат вывода используется?** HTML с встроенными ресурсами, идеально подходит для веб‑интеграции.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; полная лицензия требуется для продакшна.  
- **Можно ли изменить диапазон дат во время выполнения?** Да — измените значения `setStartDate` и `setEndDate` в параметрах рендеринга.  
- **Поддерживается ли это во всех версиях Java?** Работает с Java 8+ при условии использования GroupDocs.Viewer 25.2 или новее.

## Что такое create html view mpp?
`create html view mpp` — процесс преобразования файла Microsoft Project (`.mpp` или `.mpt`) в набор HTML‑страниц, представляющих расписание. GroupDocs Viewer выполняет конвертацию на стороне сервера, поэтому вы можете отображать временную шкалу в любом браузере без установки Microsoft Project.

## Зачем рендерить проектные документы по временным интервалам?
Рендеринг только необходимого временного интервала уменьшает размер генерируемого HTML, ускоряет загрузку страниц и позволяет сосредоточиться на конкретной фазе проекта, которую нужно проанализировать. Такой целевой вид идеален для панелей мониторинга, отчетов о статусе или встраивания в пользовательские инструменты управления проектами, где полные данные проекта могут быть перегрузкой.

## Требования
- **GroupDocs.Viewer for Java** версии 25.2 или выше.  
- Java Development Kit (JDK) 8 или новее.  
- IDE, например IntelliJ IDEA или Eclipse.  
- Базовые знания Maven.  

## Настройка GroupDocs.Viewer для Java

### Зависимость Maven

Add the repository and dependency to your `pom.xml`:

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

### Шаги получения лицензии

1. **Бесплатная пробная версия** – Скачайте пробную версию со [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Временная лицензия** – Obtain a temporary license for extended testing via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).  
3. **Покупка** – For unrestricted production use, buy a license at the [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).  

## Базовая инициализация просмотрщика

`Viewer` — основной класс в GroupDocs.Viewer для Java, который загружает документ и предоставляет возможности рендеринга.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Получение информации о представлении для файлов проекта

`ProjectManagementViewInfo` предоставляет метаданные о файле Microsoft Project, включая общие даты начала и окончания расписания.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## Настройка параметров рендеринга HTML (генерация HTML из проекта)

`HtmlViewOptions` настраивает способ рендеринга HTML в GroupDocs, позволяя задать диапазон дат, встраивание ресурсов и настройку внешнего вида.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Выполнение процесса рендеринга

`viewer.render` выполняет конвертацию на основе предоставленных параметров и записывает полученные HTML‑файлы в целевую папку.

```java
viewer.view(viewOptions);
```

## Распространённые ошибки и устранение неполадок
- **Неправильные пути к файлам** – Убедитесь, что исходный файл `.mpp` и каталог вывода существуют.  
- **Неподдерживаемый тип файла** – Убедитесь, что документ имеет поддерживаемый формат Project (например, `.mpp`, `.mpt`).  
- **Ошибки лицензии** – Пробная лицензия может накладывать ограничения на рендеринг; перейдите на полную лицензию для неограниченного использования.  

## Практические применения
1. **Анализ временной шкалы проекта** – Показать заинтересованным сторонам только текущую фазу.  
2. **Автоматизированная отчетность** – Генерировать HTML‑отчеты с ограничением по времени для еженедельных обновлений статуса.  
3. **Интеграция с панелями мониторинга** – Встраивать отрендеренные страницы в BI‑инструменты или пользовательские порталы.  
4. **Архивирование** – Сохранять веб‑дружественный снимок расписания проекта для будущего использования.  

## Советы по производительности
- Используйте опцию *embedded resources*, чтобы каждая HTML‑страница была автономной, уменьшая количество HTTP‑запросов.  
- Для очень больших проектов рассматривайте рендеринг небольшими временными фрагментами, чтобы снизить использование памяти. Рендеринг однолетнего отрезка может уменьшить размер HTML до 80 % по сравнению с экспортом всего проекта, сокращая время загрузки с нескольких секунд до менее одной секунды на типичных серверах.  
- Очищайте временные файлы после их использования, чтобы избежать накопления данных на диске.  

## Заключение

Теперь вы знаете **how to use GroupDocs** Viewer для рендеринга проектных документов в пределах конкретного временного интервала и **generate HTML from project** данные в Java. Эта возможность упрощает визуализацию временных шкал, повышает эффективность отчетности и плавно интегрируется с современными веб‑приложениями.

### Следующие шаги
- Исследуйте дополнительные функции Viewer, такие как водяные знаки, защита паролем или пользовательская стилизация CSS.  
- Объедините этот конвейер рендеринга с REST API для предоставления временных представлений по запросу.  

## Часто задаваемые вопросы

**Q: Какие форматы файлов поддерживает GroupDocs.Viewer?**  
A: GroupDocs.Viewer поддерживает более 100 входных форматов, включая PDF, DOCX, XLSX, PPTX и файлы Microsoft Project, обеспечивая универсальную визуализацию документов.

**Q: Как начать работу с бесплатной пробной версией GroupDocs.Viewer?**  
A: Вы можете скачать пробную версию со [GroupDocs Viewer Java download page](https://releases.groupdocs.com/viewer/java/).

**Q: Можно ли рендерить документы без встраивания ресурсов?**  
A: Да, вы можете выбрать другой вариант HTML‑представления, который ссылается на внешние ресурсы вместо их встраивания.

**Q: Что делать, если мой документ слишком большой для рендеринга?**  
A: Рассмотрите возможность разделения документа на более мелкие части или рендеринга только необходимого диапазона дат, как показано выше.

**Q: Как обрабатывать ошибки рендеринга?**  
A: Проверьте все настройки конфигурации, убедитесь, что у вас есть действующая лицензия, и обратитесь к документации GroupDocs для получения подробных кодов ошибок.

## Ресурсы
- **Документация**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Справочник API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Скачать**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Купить**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Бесплатная пробная версия**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Временная лицензия**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Поддержка**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Последнее обновление:** 2026-09-25  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs  

---

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Связанные руководства

- [Как рендерить файлы MS Project в HTML, JPG, PNG и PDF с заметками с помощью GroupDocs.Viewer для Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Экспорт HTML из MS Project: настройка единиц времени через GroupDocs Java](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [Responsive Html Rendering в Groupdocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)