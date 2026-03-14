---
date: '2026-02-23'
description: Узнайте, как конвертировать IGS в PDF, HTML, JPG и PNG с помощью GroupDocs.Viewer
  для Java. Следуйте этому пошаговому руководству с готовыми к запуску примерами кода.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Конвертировать IGS в PDF, HTML, JPG и PNG с помощью GroupDocs.Viewer Java
type: docs
url: /ru/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

:** GroupDocs"

Now ensure we keep markdown formatting: headings, lists, code placeholders.

Also note the note about "For Russian, ensure proper RTL formatting if needed" - not needed.

Now produce final translated markdown.

Check for any missed shortcodes: there are none besides CODE_BLOCK placeholders. Ensure they remain.

Now craft final answer.# Конвертировать IGS в PDF, HTML, JPG и PNG с помощью GroupDocs.Viewer Java

Если вам нужно **convert IGS to PDF** (или в HTML, JPG, PNG) напрямую из Java‑приложения, вы попали по адресу. В этом руководстве мы пройдем всё необходимое — от настройки библиотеки до рендеринга 3‑D модели в формате, подходящем вашему проекту. Вы увидите, почему GroupDocs.Viewer — надёжный выбор для быстрых, надёжных конвертаций, и получите готовый код, который можно внедрить в своё решение.

![Конвертировать файлы IGS в HTML, JPG, PNG и PDF с помощью GroupDocs.Viewer для Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Быстрые ответы
- **Can I convert IGS to PDF with Java?** Да, используя `PdfViewOptions` из GroupDocs.Viewer.  
- **Which output formats are supported?** HTML, JPG, PNG и PDF.  
- **Do I need a license for production?** Требуется коммерческая лицензия; доступна бесплатная пробная версия для тестирования.  
- **What Java version is required?** JDK 8 или выше.  
- **Is Maven the only way to add the library?** Нет, можно также использовать Gradle или вручную добавить JAR.  

## Что такое “convert IGS to PDF”?
Конвертация IGS (нейтрального формата файлов для 3‑D CAD‑данных) в PDF означает преобразование сложной 3‑D модели в статичный, широко просматриваемый документ. Это полезно для обмена дизайнами с заинтересованными сторонами, у которых нет CAD‑инструментов.

## Почему использовать GroupDocs.Viewer для конвертации IGS?
- **Zero‑code CAD rendering** – библиотека берёт на себя тяжёлую работу по разбору формата IGS.  
- **Multiple output options** – один вызов API может генерировать HTML, JPG, PNG или PDF.  
- **Cross‑platform** – работает на любой ОС, поддерживающей Java.  
- **Performance‑focused** – быстрый рендеринг даже для больших сборок.  

## Требования
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** установлен и настроен в вашей IDE (IntelliJ IDEA, Eclipse, NetBeans и т.д.)  
- Базовые знания Maven (необязательно, но рекомендуется)  

## Настройка GroupDocs.Viewer для Java

### Maven‑зависимость
Добавьте репозиторий GroupDocs и зависимость Viewer в ваш `pom.xml`:

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
GroupDocs.Viewer предлагает:
- **Free trial** – ограниченное использование, отлично подходит для быстрых тестов.  
- **Temporary license** – полный набор функций на короткий период оценки.  
- **Commercial license** – неограниченное использование в продакшене.  

### Базовая инициализация Viewer
Ниже показан фрагмент кода, демонстрирующий создание экземпляра `Viewer`, указывающего на ваш IGS‑файл:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Рендеринг IGS в HTML

### Как конвертировать IGS в HTML?
HTML‑вывод предоставляет интерактивный, удобный для браузера просмотр 3‑D модели.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Key point:** `HtmlViewOptions.forEmbeddedResources()` встраивает все необходимые ресурсы (CSS, изображения) непосредственно в HTML‑файл, делая его портативным.

## Рендеринг IGS в JPG

### Как конвертировать IGS в JPG?
JPG‑изображения идеальны для миниатюр или быстрых превью.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Вы можете настроить `JpgViewOptions` для управления разрешением и качеством сжатия.

## Рендеринг IGS в PNG

### Как конвертировать IGS в PNG?
PNG поддерживает прозрачность, что удобно для наложения модели на разные фоны.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Экспериментируйте с `PngViewOptions`, чтобы найти оптимальный баланс между размером файла и визуальной точностью.

## Рендеринг IGS в PDF

### Как конвертировать IGS в PDF?
PDF — основной формат для обмена детальной документацией по дизайну. Этот раздел непосредственно отвечает на основной запрос **convert IGS to PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` позволяет управлять макетом страниц, качеством изображений и встраиванием шрифтов.

## Практические применения
- **Web portals** – встраивание HTML‑рендеренных моделей непосредственно в конфигураторы продуктов.  
- **Marketing assets** – генерация изображений JPG/PNG высокого разрешения для брошюр.  
- **Technical documentation** – включение PDF‑рендеров CAD‑моделей в пользовательские руководства.  
- **Quality assurance** – автоматическое создание миниатюр для больших пакетов файлов IGS.  

## Распространённые проблемы и решения

| Проблема | Решение |
|----------|---------|
| **Папка вывода не найдена** | Проверьте путь, переданный в `Path outputDirectory`, и убедитесь, что процесс Java имеет права на запись. |
| **Пустые страницы в PDF** | Убедитесь, что файл IGS не повреждён; сначала попробуйте открыть его в CAD‑просмотрщике. |
| **Медленный рендеринг больших сборок** | Увеличьте размер кучи JVM (`-Xmx2g` или больше) и при необходимости рассмотрите рендеринг постранично с использованием `viewer.getPageCount()`. |
| **Отсутствуют шрифты в PDF** | Используйте `PdfViewOptions` для встраивания необходимых шрифтов или установите недостающие шрифты на сервере. |

## Часто задаваемые вопросы

**Q: Можно ли конвертировать несколько файлов IGS за один запуск?**  
A: Да. Пройдите в цикле список путей к файлам и вызовите соответствующий метод `view` для каждого.

**Q: Можно ли настроить размер страницы PDF?**  
A: Конечно. `PdfViewOptions` предоставляет `setPageSize(PageSize.A4)` и аналогичные методы.

**Q: Нужна ли отдельная лицензия для каждого формата вывода?**  
A: Нет. Одна лицензия GroupDocs.Viewer покрывает все поддерживаемые форматы.

**Q: Какой максимальный размер файла IGS, после которого ухудшается производительность?**  
A: Библиотека обрабатывает файлы размером до нескольких сотен мегабайт, но для очень больших моделей может потребоваться выделить больше памяти JVM.

**Q: Можно ли отрендерить только определённый вид или ориентацию?**  
A: GroupDocs.Viewer рендерит вид по умолчанию. Для пользовательских ориентаций предварительно обработайте файл IGS в CAD‑инструменте перед конвертацией.

---

**Последнее обновление:** 2026-02-23  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs