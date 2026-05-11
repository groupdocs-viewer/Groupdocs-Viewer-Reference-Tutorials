---
date: '2026-02-15'
description: Узнайте, как конвертировать PST в HTML и другие форматы, такие как JPG,
  PNG, PDF, используя GroupDocs.Viewer для Java. Это руководство охватывает все необходимые
  шаги и настройки.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Конвертировать PST в HTML, JPG, PNG, PDF с помощью GroupDocs.Viewer для Java
type: docs
url: /ru/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Преобразование PST в HTML, JPG, PNG, PDF с помощью GroupDocs.Viewer для Java

Ищете способ **конвертировать pst в html** или другие форматы, такие как JPG, PNG или PDF? С мощной библиотекой GroupDocs.Viewer для Java эта задача становится простой и эффективной. В этом руководстве вы узнаете, как преобразовать файлы Outlook PST/OST в веб‑дружественный HTML, изображения или единый PDF, делая ваши архивы электронной почты удобными для обмена и хранения.

![Преобразование PST/OST в HTML, JPG, PNG, PDF с помощью GroupDocs.Viewer для Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Что вы узнаете**
- Как настроить GroupDocs.Viewer для Java в проекте Maven.  
- Пошаговые инструкции по **java convert pst** файлы в HTML, JPG, PNG и PDF.  
- Советы по конфигурации для оптимальной производительности и типичные подводные камни.

## Быстрые ответы
- **Какая библиотека обрабатывает конвертацию PST?** GroupDocs.Viewer для Java.  
- **Можно ли напрямую конвертировать PST в PDF?** Да, используя `PdfViewOptions`.  
- **Нужна ли лицензия для продакшн?** Требуется действующая лицензия GroupDocs.  
- **Какая версия Java поддерживается?** JDK 8 или выше.  
- **Нужно ли вручную извлекать вложения?** Нет, просмотрщик рендерит их автоматически.

## Как конвертировать pst в html с помощью GroupDocs.Viewer для Java
Ниже представлено краткое описание процесса конвертации перед тем, как перейти к подробным примерам кода.

### Почему стоит выбрать GroupDocs.Viewer?
- **Высококачественное** отображение тела письма, вложений и форматирования.  
- **Множественные форматы вывода** (HTML, JPG, PNG, PDF) из единого API.  
- **Без внешних зависимостей** – всё работает внутри вашего Java‑приложения.

## Требования

- **GroupDocs.Viewer для Java** – версия 25.2 или новее.  
- **Java Development Kit (JDK)** – 8 или новее.  
- Maven для управления зависимостями.  
- Базовые знания Java и знакомство с Maven.

## Настройка GroupDocs.Viewer для Java

Добавьте репозиторий GroupDocs и зависимость в ваш `pom.xml`:

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
- **Бесплатная пробная версия** – исследуйте все функции без затрат.  
- **Временная лицензия** – при необходимости продлите период оценки.  
- **Полная лицензия** – требуется для продакшн‑развертываний.

### Базовая инициализация

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Руководство по реализации

В следующих разделах мы пошагово пройдем процесс рендеринга файлов PST/OST в каждый поддерживаемый формат.

### Рендеринг документов PST/OST в HTML

#### Шаг 1: Создание каталога вывода

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Шаг 2: Настройка параметров загрузки

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Шаг 3: Инициализация Viewer и рендеринг HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Рендеринг документов PST/OST в JPG

#### Шаг 1: Создание каталога вывода

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Шаг 2: Настройка параметров загрузки

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Шаг 3: Инициализация Viewer и рендеринг JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Рендеринг документов PST/OST в PNG

#### Шаг 1: Создание каталога вывода

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Шаг 2: Настройка параметров загрузки

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Шаг 3: Инициализация Viewer и рендеринг PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Рендеринг документов PST/OST в PDF

#### Шаг 1: Создание каталога вывода

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Шаг 2: Настройка параметров загрузки

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Шаг 3: Инициализация Viewer и рендеринг PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Практические применения

- **Архивирование электронной почты:** Преобразуйте большие архивы PST в поисковый HTML или PDF для соответствия требованиям.  
- **Системы управления документами:** Храните конвертированные файлы в системах, принимающих только PDF, PNG или JPG.  
- **Платформы совместной работы:** Делитесь конвертированными письмами в виде изображений в Slack или Teams.  
- **Юридическая проверка:** Предоставляйте судам версии PDF электронных доказательств.  
- **Стратегии резервного копирования:** Сохраняйте легковесные PNG или JPG‑снимки критически важных сообщений.

## Соображения по производительности

- **Управление ресурсами:** Переиспользуйте экземпляры `Viewer` при обработке нескольких файлов, чтобы снизить нагрузку.  
- **Настройка памяти:** Регулируйте `loadOptions.setResourceLoadingTimeout` в зависимости от возможностей сервера.  
- **Асинхронная обработка:** Переносите конвертацию в фоновые потоки для более отзывчивого UI.  

## Часто задаваемые вопросы

**В: Как **convert pst to pdf** с тем же кодом?**  
О: Используйте `PdfViewOptions`, как показано в разделе рендеринга PDF; остальная часть кода остаётся неизменной.

**В: Может ли GroupDocs.Viewer работать с зашифрованными PST‑файлами?**  
О: Да, задайте пароль через `LoadOptions.setPassword("yourPassword")` перед рендерингом.

**В: В чём разница между **java convert pst** в PNG и JPG?**  
О: PNG сохраняет без потерь, идеально подходит для скриншотов, тогда как JPG обеспечивает меньший размер файлов для предварительного просмотра писем.

**В: Есть ли способ **how to convert pst** файлов пакетно?**  
О: Оберните логику рендеринга в цикл, проходящий по каталогу PST‑файлов; переиспользуйте одну и ту же конфигурацию `Viewer` для каждого файла.

## Заключение

Теперь у вас есть полное, готовое к использованию в продакшн, руководство по **convert pst to html**, JPG, PNG и PDF с помощью GroupDocs.Viewer для Java. Следуя приведённым шагам, вы сможете интегрировать конвертацию электронной почты в любой Java‑ориентированный рабочий процесс, улучшить доступность и удовлетворить требования к соответствию.

---

**Последнее обновление:** 2026-02-15  
**Тестировано с:** GroupDocs.Viewer для Java 25.2  
**Автор:** GroupDocs  

---