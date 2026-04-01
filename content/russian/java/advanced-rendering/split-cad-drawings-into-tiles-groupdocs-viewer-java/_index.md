---
date: '2026-04-01'
description: Узнайте, как разбивать CAD‑чертежи на плитки с помощью GroupDocs Viewer
  для Java, повышая производительность рендеринга и упрощая работу с большими файлами.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Как разбить CAD‑чертежи на плитки с помощью GroupDocs Viewer
type: docs
url: /ru/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Как разбить CAD‑чертежи на плитки с помощью GroupDocs Viewer

Если вы задаётесь вопросом, **как разбить CAD**‑файлы на более мелкие, удобные части, вы попали по адресу. В этом руководстве мы пройдём по точным шагам, необходимым для разбиения больших CAD‑чертежей на плитки с использованием **GroupDocs Viewer for Java**. К концу вы получите готовое решение, которое повышает скорость рендеринга, снижает потребление памяти и упрощает отображение чертежей в веб‑ или мобильных приложениях.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Быстрые ответы
- **Что достигается при «разбиении CAD»?** Он разбивает огромный чертеж на более мелкие изображения (плитки), которые загружаются быстрее и потребляют меньше памяти.  
- **Какой формат используется для плиток?** По умолчанию генерируются PNG‑файлы, но другие форматы поддерживаются через параметры Viewer.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшна требуется платная лицензия.  
- **Можно ли изменить размер плитки?** Да — отрегулируйте расчёты `tileWidth` и `tileHeight` в соответствии с вашими потребностями.  
- **Безопасен ли этот подход для многопоточности?** Рендеринг каждой плитки в отдельном экземпляре `Viewer` с использованием try‑with‑resources безопасен при параллельном выполнении.

## Что такое «разбиение CAD»?
Разбиение CAD подразумевает деление одного, часто огромного, CAD‑чертежа на несколько прямоугольных секций (плиток). Каждая плитка рендерится независимо, позволяя загружать только те части, которые действительно нужны пользователю — идеально для веб‑карт, порталов документов и мобильных просмотровщиков.

## Почему использовать GroupDocs Viewer для Java?
GroupDocs Viewer предоставляет готовую поддержку более чем 100 форматов файлов, включая DWG, DXF и DWF. Его API плиток позволяет задавать точные координаты, чтобы вы могли отрисовать именно нужную область без предварительной обработки всего файла. Это экономит процессорное время, уменьшает трафик и обеспечивает более плавный пользовательский опыт.

## Требования
- **Библиотеки**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Любой современный Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse или другая совместимая с Java IDE.  
- **Система сборки**: Maven (другие системы сборки работают, если добавить зависимость).  

## Настройка GroupDocs.Viewer для Java
Add the GroupDocs repository and dependency to your `pom.xml`:

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
GroupDocs Viewer offers a free trial license for evaluation:

- **Бесплатная пробная версия**: Перейдите к [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) для загрузки библиотеки.  
- **Временная лицензия**: Оформите её на странице [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Полная лицензия**: Приобретите производственную лицензию на странице [Purchase Page](https://purchase.groupdocs.com/buy).

### Базовая инициализация
Create a simple `Viewer` instance to verify that the library loads correctly:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Пошаговое руководство по разбиению CAD‑чертежей на плитки

### Шаг 1: Определите каталог вывода
Мы будем сохранять каждую плитку как отдельный PNG‑файл. Использование вспомогательного метода упрощает и делает логику пути переиспользуемой.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Шаг 2: Настройте параметры просмотра
Установите формат рендеринга в PNG и укажите просмотрщику не предзагружать каждую страницу (это экономит память).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Шаг 3: Рассчитайте размеры плиток
Сначала получаем исходную ширину и высоту чертежа, затем делим его на четыре равные квадранта.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Шаг 4: Отрендерите и сохраните плитки
Добавьте рассчитанные плитки в параметры рендеринга и позвольте `Viewer` сгенерировать PNG‑файлы.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Советы по устранению неполадок
- **Путь сборки** – Убедитесь, что JAR‑файлы GroupDocs находятся в classpath.  
- **Разрешения** – Папка вывода должна быть доступна для записи процессом Java.  
- **Исключения** – Если появляется `ViewerException`, дважды проверьте, что DWG‑файл не повреждён и что применена правильная лицензия.

## Распространённые сценарии использования плиток CAD
1. **Веб‑картография** – Загружайте только видимую часть плана этажа, когда пользователь перемещает/масштабирует карту.  
2. **Управление документами** – Храните каждую плитку отдельно для более быстрой генерации превью.  
3. **Мобильный просмотр** – Сократите трафик, загружая только те плитки, которые нужны для текущего экрана.

## Соображения по производительности
- **Размер плитки** – Большие плитки означают меньше файлов, но более медленный рендеринг; найдите баланс в зависимости от потребностей вашего UI.  
- **Мониторинг памяти** – Используйте инструменты профилирования Java (например, VisualVM), чтобы наблюдать за использованием кучи при обработке очень больших чертежей.  
- **Очистка ресурсов** – Паттерн try‑with‑resources, показанный выше, автоматически освобождает нативные ресурсы.

## Часто задаваемые вопросы

**Q: Можно ли разбивать другие типы файлов (PDF, изображения) на плитки тем же подходом?**  
A: Да. GroupDocs Viewer поддерживает множество форматов; вам просто нужно использовать соответствующий класс параметров (например, `PdfViewOptions`).

**Q: Как изменить качество выходного изображения?**  
A: Отрегулируйте `viewOptions.setResolution(int dpi)` или задайте параметры сжатия в объекте `PngOptions`.

**Q: Моё приложение выходит за пределы памяти при работе с очень большими DWG‑файлами — что делать?**  
A: Уменьшите размеры плиток, увеличьте размер кучи JVM (`-Xmx`) или рендерите плитки последовательно в отдельных экземплярах `Viewer`.

**Q: Можно ли рендерить плитки асинхронно?**  
A: Конечно. Оберните каждый вызов рендеринга плитки в `CompletableFuture` или используйте сервис исполнителей для параллелизации нагрузки.

**Q: Нужна ли отдельная лицензия для каждой плитки?**  
A: Нет. Одна действующая лицензия GroupDocs Viewer покрывает все операции рендеринга в вашем приложении.

## Ресурсы
- [Документация](https://docs.groupdocs.com/viewer/java/)
- [Справочник API](https://reference.groupdocs.com/viewer/java/)
- [Скачать GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Приобрести лицензию](https://purchase.groupdocs.com/buy)
- [Бесплатная пробная версия](https://releases.groupdocs.com/viewer/java/)
- [Временная лицензия](https://purchase.groupdocs.com/temporary-license/)
- [Форум поддержки](https://forum.groupdocs.com/c/viewer/9)

---

**Последнее обновление:** 2026-04-01  
**Тестировано с:** GroupDocs.Viewer 25.2 for Java  
**Автор:** GroupDocs  

---