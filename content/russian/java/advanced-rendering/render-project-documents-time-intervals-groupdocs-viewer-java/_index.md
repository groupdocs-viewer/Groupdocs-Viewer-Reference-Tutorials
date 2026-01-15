---
date: '2026-01-15'
description: Изучите, как использовать GroupDocs Viewer для генерации HTML из проектных
  документов в определённых временных интервалах. Это руководство охватывает настройку,
  код и реальные примеры использования.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Как использовать GroupDocs Viewer для отображения проектных документов по временным
  интервалам в Java
type: docs
url: /ru/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Как использовать GroupDocs Viewer для рендеринга проектных документов по временным интервалам в Java

Если вы ищете **как использовать GroupDocs**, чтобы отобразить графики проектов в определённом временном окне, вы попали по адресу. В этом руководстве мы пройдём весь процесс — от настройки Maven до генерации HTML из проектных документов — чтобы вы могли внедрять точные представления временных шкал непосредственно в свои приложения.

![Рендеринг проектных документов по временным интервалам с помощью GroupDocs.Viewer для Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Быстрые ответы
- **Что делает эта функция?** Она отображает только ту часть файла Microsoft Project, которая находится между датой начала и датой окончания.  
- **Какой формат вывода используется?** HTML с встроенными ресурсами, идеально подходит для веб‑интеграции.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; для продакшна требуется полная лицензия.  
- **Можно ли изменить диапазон дат во время выполнения?** Да — измените значения `setStartDate` и `setEndDate` в параметрах рендеринга.  
- **Поддерживается ли это во всех версиях Java?** Работает с Java 8+ при условии использования GroupDocs.Viewer 25.2 или новее.

## Что означает «How to Use GroupDocs» в этом контексте?
GroupDocs Viewer — это Java‑библиотека, которая преобразует более 100 форматов файлов в веб‑дружественные представления. Когда вы **как использовать GroupDocs** для проектных файлов, вы получаете возможность извлекать, визуализировать и делиться данными расписания без необходимости наличия Microsoft Project на клиентской стороне.

## Почему рендерить проектные документы с временными интервалами?
- **Сфокусированный анализ:** Показывать только ту фазу, которая вас интересует (например, Q3 2024).  
- **Производительность:** Меньший объём HTML‑вывода означает более быструю загрузку страниц.  
- **Интеграция:** Встраивать представления временной шкалы в панели мониторинга, порталы отчётности или кастомные инструменты управления проектами.  

## Предварительные требования
- **GroupDocs.Viewer for Java** версии 25.2 или выше.  
- Java Development Kit (JDK) 8 или новее.  
- IDE, например IntelliJ IDEA или Eclipse.  
- Базовые знания Maven.  

## Настройка GroupDocs.Viewer для Java

### Maven‑зависимость

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
1. **Free Trial** — Скачайте пробную версию со [страницы загрузки GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** — Получите временную лицензию для расширенного тестирования по [этой ссылке](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** — Для неограниченного использования в продакшн‑среде купите лицензию на [странице покупки GroupDocs](https://purchase.groupdocs.com/buy).

### Базовая инициализация Viewer

The following snippet shows how to create a `Viewer` instance that points to a Microsoft Project file (`.mpp`):

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

## Пошаговое руководство по реализации

### 1. Определите каталог вывода

Create a folder where the generated HTML pages will be saved:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Почему?* Организованное хранение отрендеренных файлов упрощает их обслуживание веб‑сервером или встраивание в пользовательский интерфейс.

### 2. Инициализируйте Viewer с вашим проектным файлом

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Почему?* Загрузка документа подготавливает внутренний парсер и делает доступными метаданные, специфичные для проекта.

### 3. Получите информацию о представлении для проектных файлов

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Почему?* `ProjectManagementViewInfo` предоставляет даты начала и окончания расписания, которые позже вы будете использовать для ограничения области рендеринга.

### 4. Настройте параметры HTML‑рендеринга (Генерация HTML из проекта)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Почему?* Установка `StartDate` и `EndDate` указывает GroupDocs **генерировать HTML из проекта** только в пределах указанного окна.

### 5. Выполните процесс рендеринга

```java
viewer.view(viewOptions);
```

*Почему?* Этот вызов создаёт серию автономных HTML‑страниц, представляющих выбранный временной отрезок вашего графика проекта.

## Распространённые ошибки и устранение неполадок
- **Incorrect file paths** — Проверьте, что исходный файл `.mpp` и каталог вывода существуют.  
- **Unsupported file type** — Убедитесь, что документ находится в поддерживаемом формате Project (например, `.mpp`, `.mpt`).  
- **License errors** — Пробная лицензия может накладывать ограничения на рендеринг; перейдите на полную лицензию для неограниченного использования.  

## Практические применения
1. **Project Timeline Analysis** — Показывать заинтересованным сторонам только текущую фазу.  
2. **Automated Reporting** — Генерировать HTML‑отчёты с привязкой к времени для еженедельных обновлений статуса.  
3. **Integration with Dashboards** — Встраивать отрендеренные страницы в BI‑инструменты или кастомные порталы.  
4. **Archival** — Сохранять веб‑дружественный снимок расписания проекта для будущего использования.  

## Советы по производительности
- Используйте опцию *embedded resources*, чтобы каждая HTML‑страница была автономной, уменьшая количество HTTP‑запросов.  
- Для очень больших проектов рассмотрите рендеринг небольшими датными блоками, чтобы снизить потребление памяти.  
- Удаляйте временные файлы после их использования, чтобы избежать накопления данных на диске.  

## Заключение

Теперь вы знаете **how to use GroupDocs** Viewer для рендеринга проектных документов в определённом временном интервале и **generate HTML from project** данные в Java. Эта возможность упрощает визуализацию временных шкал, повышает эффективность отчётности и плавно интегрируется с современными веб‑приложениями.

### Следующие шаги
- Изучите дополнительные функции Viewer, такие как водяные знаки, защита паролем или настройка CSS‑стилей.  
- Объедините этот конвейер рендеринга с REST API для предоставления временных представлений по запросу.  

## Часто задаваемые вопросы

**Q: Какие форматы файлов поддерживает GroupDocs.Viewer?**  
A: GroupDocs.Viewer поддерживает широкий спектр форматов, включая Microsoft Project (MPP), PDF, Word, Excel, PowerPoint и многие другие.

**Q: Как начать работу с бесплатной пробной версией GroupDocs.Viewer?**  
A: Вы можете скачать пробную версию по [ссылке](https://releases.groupdocs.com/viewer/java/).

**Q: Можно ли рендерить документы без встраивания ресурсов?**  
A: Да, можно выбрать другой вариант HTML‑просмотра, который ссылается на внешние ресурсы вместо их встраивания.

**Q: Что делать, если мой документ слишком велик для рендеринга?**  
A: Рассмотрите возможность разделения документа на более мелкие части или рендеринга только необходимого диапазона дат, как показано выше.

**Q: Как обрабатывать ошибки рендеринга?**  
A: Проверьте все настройки конфигурации, убедитесь, что у вас действующая лицензия, и обратитесь к документации GroupDocs для получения подробных кодов ошибок.

## Ресурсы
- **Документация**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Справочник API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Скачать**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Покупка**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Бесплатная пробная версия**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Временная лицензия**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Поддержка**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Последнее обновление:** 2026-01-15  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs