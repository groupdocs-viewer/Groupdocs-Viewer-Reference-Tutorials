---
date: '2026-03-29'
description: Узнайте, как создать HTML‑просмотр MPP с помощью GroupDocs Viewer на
  Java, отображая проектные документы по временным интервалам с пошаговым кодом.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Создать HTML‑просмотр MPP с помощью GroupDocs Viewer (Java)
type: docs
url: /ru/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Как использовать GroupDocs Viewer для отображения проектных документов по временным интервалам в Java

В этом руководстве вы узнаете, как **create html view mpp** с GroupDocs Viewer для Java, позволяя отображать только те части файла Microsoft Project, которые попадают в определённый временной интервал. Мы пройдём настройку Maven, конфигурацию кода и реальные сценарии, чтобы вы могли встраивать точные представления временных шкал непосредственно в свои приложения.

![Отображение проектных документов по временным интервалам с GroupDocs.Viewer для Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Быстрые ответы
- **Что делает эта функция?** Она отображает только часть файла Microsoft Project, которая находится между датой начала и датой окончания.  
- **Какой формат вывода используется?** HTML с встроенными ресурсами, идеально подходит для веб‑интеграции.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; полная лицензия требуется для продакшн.  
- **Можно ли изменить диапазон дат во время выполнения?** Да — отрегулируйте значения `setStartDate` и `setEndDate` в параметрах рендеринга.  
- **Поддерживается ли это во всех версиях Java?** Работает с Java 8+ при условии использования GroupDocs.Viewer 25.2 или новее.

## Как создать html view mpp для проектных документов
GroupDocs Viewer может преобразовывать файлы Microsoft Project (`.mpp`, `.mpt`) в HTML‑страницы. Настраивая даты начала и окончания в параметрах рендеринга, вы ограничиваете вывод нужным временным отрезком, что уменьшает размер файлов и ускоряет загрузку страниц.

## Что означает «How to Use GroupDocs» в данном контексте?
GroupDocs Viewer — это Java‑библиотека, преобразующая более 100 форматов файлов в веб‑дружественные представления. Когда вы **how to use GroupDocs** для проектных файлов, вы получаете возможность извлекать, визуализировать и делиться данными расписания без необходимости установки Microsoft Project на клиенте.

## Зачем отображать проектные документы по временным интервалам?
- **Целевая аналитика:** Показать только интересующую фазу (например, Q3 2024).  
- **Производительность:** Меньший объём HTML‑вывода означает более быструю загрузку страниц.  
- **Интеграция:** Встраивание представлений временных шкал в панели мониторинга, порталы отчётности или пользовательские инструменты управления проектами.  

## Требования
- **GroupDocs.Viewer for Java** версии 25.2 или выше.  
- Java Development Kit (JDK) 8 или новее.  
- IDE, например IntelliJ IDEA или Eclipse.  
- Базовые знания Maven.  

## Настройка GroupDocs.Viewer для Java

### Зависимость Maven

Добавьте репозиторий и зависимость в ваш `pom.xml`:

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

1. **Бесплатная пробная версия** – Скачайте пробную версию со [страницы загрузки GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Временная лицензия** – Получите временную лицензию для расширенного тестирования по [этой ссылке](https://purchase.groupdocs.com/temporary-license/).  
3. **Покупка** – Для неограниченного использования в продакшн приобретите лицензию на [странице покупки GroupDocs](https://purchase.groupdocs.com/buy).  

### Базовая инициализация Viewer

Следующий фрагмент кода показывает, как создать экземпляр `Viewer`, указывающий на файл Microsoft Project (`.mpp`):

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

Создайте папку, в которой будут сохраняться сгенерированные HTML‑страницы:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Почему?* Организация отрендеренных файлов упрощает их обслуживание через веб‑сервер или встраивание в пользовательский интерфейс.

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

*Почему?* `ProjectManagementViewInfo` предоставляет даты начала и окончания расписания, которые позже вы используете для ограничения области рендеринга.

### 4. Настройте параметры HTML‑рендеринга (генерация HTML из проекта)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Почему?* Установка `StartDate` и `EndDate` сообщает GroupDocs генерировать данные **generate html view mpp** только в этом диапазоне.

### 5. Выполните процесс рендеринга

```java
viewer.view(viewOptions);
```

*Почему?* Этот вызов создаёт серию автономных HTML‑страниц, представляющих выбранный временной отрезок вашего расписания проекта.

## Распространённые ошибки и устранение неполадок
- **Неправильные пути к файлам** – Убедитесь, что исходный файл `.mpp` и каталог вывода существуют.  
- **Неподдерживаемый тип файла** – Убедитесь, что документ имеет поддерживаемый формат Project (например, `.mpp`, `.mpt`).  
- **Ошибки лицензии** – Пробная лицензия может накладывать ограничения на рендеринг; перейдите на полную лицензию для неограниченного использования.  

## Практические применения
1. **Анализ временной шкалы проекта** – Показать заинтересованным сторонам только текущую фазу.  
2. **Автоматизированная отчётность** – Генерировать HTML‑отчёты с ограничением по времени для еженедельных обновлений статуса.  
3. **Интеграция с панелями мониторинга** – Встраивание отрендеренных страниц в BI‑инструменты или пользовательские порталы.  
4. **Архивирование** – Сохранить веб‑дружественный снимок расписания проекта для будущего использования.  

## Советы по производительности
- Используйте опцию *embedded resources*, чтобы каждая HTML‑страница была автономной, уменьшая количество HTTP‑запросов.  
- Для очень больших проектов рассмотрите рендеринг небольшими датными блоками, чтобы снизить использование памяти.  
- Удаляйте временные файлы после их использования, чтобы избежать накопления на диске.  

## Заключение
Теперь вы знаете, **how to use GroupDocs** Viewer для рендеринга проектных документов в определённом временном интервале и **generate HTML from project** данные в Java. Эта возможность упрощает визуализацию временных шкал, повышает эффективность отчётности и плавно интегрируется с современными веб‑приложениями.

### Следующие шаги
- Изучите дополнительные возможности Viewer, такие как водяные знаки, защита паролем или пользовательское стилизование CSS.  
- Объедините этот конвейер рендеринга с REST API для предоставления запросных представлений временных шкал.  

## Часто задаваемые вопросы

**В: Какие форматы файлов поддерживает GroupDocs.Viewer?**  
О: GroupDocs.Viewer поддерживает широкий спектр форматов, включая Microsoft Project (MPP), PDF, Word, Excel, PowerPoint и многие другие.

**В: Как начать работу с бесплатной пробной версией GroupDocs.Viewer?**  
О: Вы можете скачать пробную версию по [ссылке](https://releases.groupdocs.com/viewer/java/).

**В: Можно ли рендерить документы без встраивания ресурсов?**  
О: Да, вы можете выбрать другой вариант HTML‑представления, который ссылается на внешние ресурсы вместо их встраивания.

**В: Что делать, если мой документ слишком большой для рендеринга?**  
О: Рассмотрите возможность разбить документ на более мелкие части или рендерить только необходимый диапазон дат, как показано выше.

**В: Как обрабатывать ошибки рендеринга?**  
О: Проверьте все настройки конфигурации, убедитесь, что у вас есть действующая лицензия, и обратитесь к документации GroupDocs для получения подробных кодов ошибок.

## Ресурсы
- **Документация**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Ссылка на API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Скачать**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Покупка**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **Бесплатная пробная версия**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **Временная лицензия**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Поддержка**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)  

---

**Последнее обновление:** 2026-03-29  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs  

---