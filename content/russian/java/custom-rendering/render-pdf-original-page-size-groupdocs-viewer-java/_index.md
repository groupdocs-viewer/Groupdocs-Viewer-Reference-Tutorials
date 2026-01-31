---
date: '2026-01-31'
description: Узнайте, как преобразовать PDF в PNG на Java, сохраняя оригинальный размер
  страницы с помощью GroupDocs.Viewer. Включает советы по PDF‑в‑PNG на Java и устранение
  неполадок.
keywords:
- Render PDF Original Size
- GroupDocs Viewer Java API
- PDF Rendering with Java
title: Как отобразить PDF в оригинальном размере с помощью GroupDocs.Viewer для Java –
  Полное руководство
type: docs
url: /ru/java/custom-rendering/render-pdf-original-page-size-groupdocs-viewer-java/
weight: 1
---

# Как отобразить PDF в оригинальном размере с помощью GroupDocs.Viewer для Java

Отображение PDF **how to render pdf на любом устройстве. В этом руководстве вы узнаете, почему важно сохранять оригинальный размер страницы, как настроить GroupDocs.Viewer для Java и какие шаги выполнить, чтобы конвертировать PDF в PNG java без масштабирования. К концу вы сможете надёжно рендерить PDF в их оригинальном размере и избегать распространённых проблем при отладке рендеринга PDF.

![Отображение PDF в оригинальном размере с GroupDocs.Viewer для Java](/viewer/custom-rendering/render-pdfs-in-original-size.png)

## Быстрые ответы
- **Какая библиотека может конвертировать PDF в PNG на Java?** GroupDocs.Viewer for Java предоставляет простой API для pdf to png java конвертации.  
- **Как сохранить оригинальный размер страницы?** Включите `setRenderOriginalPageSize(true)` у объекта `PdfOptions`.  
- **Нужна ли лицензия для продакшн?** Да – для использования без пробного режима требуется постоянная или временная лицензия GroupDocs.  
- **Можно ли рендерить защищённые паролем PDF?** Да, просто передайте пароль при создании экземпляра `Viewer`.  
- **Какая версия Java требуется?** Поддерживается JDK 8 и выше.

## Что значит «рендерить PDF в оригинальном размере»?
При рендеринге PDF просмотрщик может либо масштабировать страницы под целевой формат, либо сохранять точные размеры, указанные в исходном файле. Рендеринг в оригинальном размере означает, что каждая страница экспортируется пиксель‑в‑пиксель, что критично для юридических документов, архивных материалов и любых сценариев, где точность макета не может быть компромиссическое соответствие так же, как при первоначальном представлении.  
- **Согласованность бренда:** Маркетинговые материалы сохраняют задуманный дизайн.  
- **Техническая точность:** Измерения, схемы и формы остаются пригодными после конвертации.  

## Предварительные требования
- **Java Development Kit (JDK):** Версия 8 или новее.  
- ** через Maven (см. ниже).  
- **IDE:** IntelliJ IDEA, Eclipse или любой совместимый с Java редактор.  

## Настройка GroupDocs.Viewer для Java

### Конфигурация Maven
Добавьте официальный репозиторий GroupDocs и зависимость Viewer в ваш `pom.xml`. *(Не изменяйте блок кода – он должен оставаться точно как показано.)*

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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

#### Приобретение лицензии
GroupDocs предлагает несколько вариантов лицензирования:
- **Бесплатная пробная лицензия:**  
- **Постояннаяально для продакшн‑развёртываний.

## Руководство по реализации

### Шаг 1: Инициализация GroupDocs.Viewer
Создайте экземпляр `Viewer` и настройте `PngViewOptions` для вывода PNG‑файлов. Важный вызов `viewOptions.getPdfOptions().setRenderOriginalPageSize(true);` указывает движку **установить оригинальный размер страницы**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

import java.nio.file.Path;

public class RenderOriginalPageSize {
    public static void main(String[] args) {
        // Define output directory path for rendered pages
        Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
        
        // Format for the output page file paths
        String pageFilePathFormat = "page_{0}.png";
        Path pageFilePath = outputDirectory.resolve(pageFilePathFormat);
        
        // Initialize PngViewOptions with the path format
        PngViewOptions viewOptions = new PngViewOptions(pageFilePath.toString());
        
        // Set option to render original page size for PDF documents
        viewOptions.getPdfOptions().setRenderOriginalPageSize(true);
        
        // Create a Viewer instance for the source PDF document
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF")) {
            // Render the PDF using the specified options
            viewer.view(viewOptions);
        }
    }
}
```

**Пояснение ключевых строк**  
- **Конфигурация пути:** Определяет, где будет сохранён каждый отрендеренный PNG.  
- **PngViewOptions:** Выбирает PNG в качестве формата вывода *т страницы PDF.

### Шаг 2: Запуск и проверка
Выполните метод `main`. После завершения откройте сгенерированные PNG‑файлы; они должны совпадать с оригинальными размерами страниц PDF пиксель‑в‑пиксель. Если изображения выглядят растянутыми, проверьте наличие `setRenderOriginalPageSize(true)` и используйтестранение неполадлам:** Убедитесь, что `outputDirectory` и путь к исходному PDF указаны абсолютными или корректно относительными к вашему проекту.  
- **Отсутствие лицензии:** Без действующей лицензии рендеринг может перейти в пробный режим с ограничением количества страниц.  
- **Ошибки «Out‑of‑memory» при больших PDF:** Увеличьте размер кучи JVM (`-Xmx2g` или больше) или включите ленивую загрузку страниц.  
- **Зашифрованные PDF:** Передайте пароль при создании экземпляра `Viewer`, чтобы избежать ошибок *pdf rendering troubleshooting*.

## Практические сценарии использования
1. **Цифровые архивы:** Сохранение исторических сканов без искажений.  
2. **Порталы юридических документов:** Предоставление судоустойчивых PDF, отображаемых точно как подано.  
3. **Платформы e‑Learning:** Конвертация учебников в изображения при сохранении макета.  
4. **Ав итогов после конвертации.

## Советы по производительности
- **Управление памятью:** Выделяйте достаточный объём кучи для больших документов.  
- **Ленивая загрузка:** По возможности рендерьте только нужные страницы, а не весь файл.  
- **Кеширование:** Храните отрендеренные PNG для часто запрашиваемых PDF, чтобы избежать повторной обработки.

## Часто задаваемые вопросы
 Spring Boot?**  
О: Зарегистрируйте `Viewer` как bean и внедрите его там, где необходимо; это позволит управ, отличные от PNG?**  
О: Да, GroupDocs.Viewer также поддерживает JPEG, SVG и конвертации PDF‑в‑HTML.

**В: Что делать, если процесс рендеринга завершается исключением?**  
О: Проверьте стек‑трейс на отсутствие путей к файлам или проблем с лицензией и убедитесь, что PDF не повреждён.

**В: Есть ли ограничение по размеру PDF, который можно рендерить?**  
О: Технически нет, но очень большие файлы могут потребовать увеличения памяти JVM и могут выиграть от разбиения на более мелкие части.

**В: Обрабатывает ли GroupDocs.Viewer защищённые паролем PDF?**  
О: Абсолютно – просто передайте пароль в конструктор `Viewer` или через объект `LoadOptions`.

## Ресурсы
- **Документация:** [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Справочник API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)  
- **Скачать GroupDocs.Viewer:** [Official Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Покупка и лицензирование:** [Buy GroupDocs Products](https://purchase.groupdocs.com/buy)  
- **Бесплатная пробная версия:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Временная лицензия:** [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Форум поддержки:** [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Последнее обновление:** 2026-01-31  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs  

---