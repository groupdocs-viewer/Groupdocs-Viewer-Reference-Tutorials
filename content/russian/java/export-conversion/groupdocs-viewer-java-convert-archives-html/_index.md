---
date: '2026-02-23'
description: Узнайте, как установить количество элементов на страницу, внедрять ресурсы
  в HTML и пакетно конвертировать архивы в одностраничный или многостраничный HTML
  с помощью GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Установить количество элементов на странице: конвертировать архивы в HTML
  с помощью GroupDocs.Viewer Java'
type: docs
url: /ru/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Установить количество элементов на страницу: Конвертация архивов в HTML с помощью GroupDocs.Viewer Java

Конвертация архивных файлов, таких как ZIP или RAR, в веб‑дружественный HTML часто требуется, когда нужно поделиться документами или просмотреть их непосредственно в браузере. В этом руководстве вы узнаете, **как установить количество элементов на страницу** при рендеринге архивов, как встроить ресурсы HTML для автономного вывода и как эффективно выполнять пакетную конвертацию архивов с помощью GroupDocs.Viewer Java.

![Конвертация архивов в HTML с помощью GroupDocs.Viewer для Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Быстрые ответы
- **Что контролирует параметр «установить количество элементов на страницу»?** Он определяет, сколько файлов или папок из архива будет отображаться на каждой сгенерированной HTML‑странице.  
- **Можно ли встроить изображения и CSS непосредственно в HTML?** Да — используйте опцию `forEmbeddedResources` для встраивания ресурсов в HTML.  
- **Возможна ли пакетная конвертация?** Абсолютно; вы можете перебрать коллекцию архивов и отрисовать каждый с одинаковыми настройками.  
- **Нужен ли Maven для использования GroupDocs.Viewer?** Да, добавьте зависимость `maven groupdocs viewer`, как показано ниже.  
- **Какие форматы вывода поддерживаются?** Доступны как одностраничный HTML Java, так и многостраничный HTML Java.

## Что такое «установить количество элементов на страницу» в GroupDocs.Viewer?
Параметр **set items per page** относится к настройкам рендеринга архивов. Он указывает просмотровщику, сколько записей архива (файлов или папок) должно отображаться на каждой HTML‑странице при генерации многостраничного HTML‑документа. Регулирование этого значения помогает сбалансировать размер страниц и скорость навигации, особенно для больших архивов.

## Почему встраивать ресурсы HTML?
Встраивание ресурсов (изображений, CSS, шрифтов) непосредственно в HTML‑файл создаёт единый, переносимый документ, который можно открыть без внешних файлов. Это удобно для вложений в письмах, офлайн‑просмотра или встраивания вывода в другие веб‑страницы.

## Требования

- **Необходимые библиотеки:** GroupDocs.Viewer версии 25.2 или новее.  
- **Среда:** Установленный и настроенный Java Development Kit (JDK).  
- **Знания:** Базовый Java и управление зависимостями Maven.  

## Настройка Maven для GroupDocs Viewer

Добавьте репозиторий GroupDocs и зависимость viewer в ваш `pom.xml`:

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
GroupDocs.Viewer предлагает **ссылку на бесплатную пробную версию**, временную лицензию или полную покупку. Выберите вариант, соответствующий срокам вашего проекта.

### Базовая инициализация
После настройки Maven подключите viewer в ваш код:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Как отрисовать архивы в одностраничный HTML

### Шаг 1: Определить каталог вывода
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Шаг 2: Задать имя файла для одностраничного вывода
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Шаг 3: Инициализировать Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Шаг 4: Настроить параметры рендеринга (встроить ресурсы HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Шаг 5: Выполнить рендеринг в один файл
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Как отрисовать архивы в многостраничный HTML и установить количество элементов на страницу

### Шаг 1: Повторно использовать каталог вывода
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Шаг 2: Задать формат имени файлов для нескольких страниц
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Шаг 3: Снова инициализировать Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Шаг 4: Настроить параметры многостраничного вывода (встроить ресурсы HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Шаг 5: Установить количество элементов на страницу (ключевое действие)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Практические применения

- **Системы управления документами:** Добавьте возможность предварительного просмотра архивов без установки дополнительных просмотрщиков.  
- **Веб‑порталы:** Предоставьте пользователям быстрый способ изучения комплектных документов без загрузки.  
- **Инструменты совместной работы:** Позвольте командам проверять общие архивы непосредственно в браузере.

## Соображения по производительности

- **Управление ресурсами:** Следите за использованием памяти; при больших пакетах рассмотрите настройку сборщика мусора JVM.  
- **Пакетная конвертация архивов:** Перебирайте список архивных файлов и вызывайте одну и ту же логику рендеринга для максимальной пропускной способности.  
- **Стратегия кэширования:** Сохраняйте отрендеренный HTML в кэше, если один и тот же архив часто запрашивается.

## Часто задаваемые вопросы

**Q: Что такое GroupDocs.Viewer Java?**  
A: Универсальная библиотека для рендеринга документов — включая архивы — в такие форматы, как HTML, PDF и изображения.

**Q: Как получить бесплатную пробную версию GroupDocs.Viewer?**  
A: Перейдите по [ссылке на бесплатную пробную версию](https://releases.groupdocs.com/viewer/java/), чтобы скачать и протестировать.

**Q: Можно ли конвертировать другие типы документов, кроме архивов?**  
A: Да, viewer поддерживает PDF, Word, Excel и многие другие форматы.

**Q: Что делать, если рендеринг работает медленно?**  
A: Уменьшите количество элементов на страницу, включите потоковую передачу или обрабатывайте архивы небольшими партиями.

**Q: Где можно получить помощь или поддержку?**  
A: Обратитесь через [форум поддержки](https://forum.groupdocs.com/c/viewer/9).

**Q: Можно ли встроить CSS и изображения напрямую в HTML?**  
A: Абсолютно — используйте `HtmlViewOptions.forEmbeddedResources`, как показано в примерах.

**Q: Как выполнить пакетную конвертацию папки с архивами?**  
A: Пройдитесь по каждому файлу в цикле `for`, применяя одинаковую конфигурацию `Viewer` и `HtmlViewOptions` для каждой итерации.

## Ресурсы

- **Документация:** Узнайте больше о возможностях в [документации GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Справочник API:** Изучите полный API на странице [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Скачать:** Получите последние бинарные файлы со [страницы загрузки](https://releases.groupdocs.com/viewer/java/).  
- **Покупка и лицензирование:** Ознакомьтесь с вариантами на [странице покупки](https://purchase.groupdocs.com/buy).  
- **Поддержка и сообщество:** Присоединяйтесь к обсуждениям на [форуме GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Last Updated:** 2026-02-23  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs