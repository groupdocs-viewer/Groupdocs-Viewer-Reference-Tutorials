---
date: '2026-09-15'
description: تعلم كيفية تحويل eml إلى html مع تنسيق تاريخ ووقت مخصص وإزاحة timezone
  offset باستخدام GroupDocs.Viewer for Java — مثالي لأرشفة البريد الإلكتروني وبوابات
  الدعم.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: تحويل eml إلى html مع تنسيق تاريخ ووقت مخصص وإزاحة timezone offset
  باستخدام GroupDocs.Viewer for Java. اتبع هذا الدليل خطوة بخطوة للحصول على عرض دقيق
  للبريد الإلكتروني.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: تحويل eml إلى html مع تنسيق تاريخ ووقت مخصص في java باستخدام GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: تحويل eml إلى html مع تنسيق تاريخ ووقت مخصص في java باستخدام GroupDocs.Viewer
type: docs
url: /ar/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحويل eml إلى html مع تاريخ ووقت مخصص في java باستخدام GroupDocs.Viewer

في أنظمة الدعم والأرشفة الحديثة، **تحويل eml إلى html** بسرعة مع الحفاظ على الطوابع الزمنية الدقيقة أمر ضروري. يوضح هذا البرنامج التعليمي كيفية تحويل بريد EML إلى HTML، وتطبيق **تنسيق تاريخ ووقت مخصص**، وتعيين **إزاحة المنطقة الزمنية** باستخدام GroupDocs.Viewer للغة Java. في النهاية ستحصل على مقطع شفرة قابل لإعادة الاستخدام ينتج عروض بريد إلكتروني دقيقة وجاهزة للويب لأي سير عمل **تحويل البريد الإلكتروني إلى html**.

![عرض رسائل البريد الإلكتروني مع تاريخ ووقت مخصص باستخدام GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## إجابات سريعة
- **هل يمكن لـ GroupDocs.Viewer تحويل EML إلى HTML؟** نعم – تقوم الـ API بتحويل ملفات EML مباشرة إلى HTML دون الحاجة إلى عملاء بريد خارجي.  
- **هل أحتاج إلى ترخيص للإنتاج؟** النسخة التجريبية مجانية للاختبار؛ الترخيص المدفوع مطلوب للنشر في بيئات الإنتاج.  
- **ما نسخة Java المدعومة؟** Java 8 أو أحدث مدعومة بالكامل.  
- **كيف يمكنني تغيير تنسيق التاريخ المعروض؟** استدعِ `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
- **هل يمكنني تعديل المنطقة الزمنية؟** نعم، استخدم `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## ما هو “تحويل eml إلى html”؟
`Convert eml to html` هو عملية تحويل ملف بريد EML إلى مستند HTML لعرضه في المتصفح. تحويل ملف EML إلى HTML يحول البريد الخام (بما في ذلك الرؤوس، الجسم، والمرفقات) إلى تنسيق صديق للويب يمكن للمتصفحات عرضه دون إضافات إضافية. هذا يسهل تضمين الرسائل في تطبيقات الويب، الأرشيفات، أو لوحات الدعم.

## لماذا نستخدم GroupDocs.Viewer لهذه المهمة؟
يدعم GroupDocs.Viewer **أكثر من 50 تنسيقًا للمدخلات والمخرجات**، بما في ذلك EML و MSG و PST و PDF، ويمكنه عرض رسائل بريد مئات الصفحات دون تحميل الملف بالكامل إلى الذاكرة. محركه الخالي من الاعتماديات يلغي الحاجة إلى Outlook أو محللات طرف ثالث، مما يمنحك تحكمًا كاملاً في **تنسيق التاريخ والوقت المخصص** و **إزاحة المنطقة الزمنية** مع الحفاظ على استهلاك منخفض للموارد.

## المتطلبات المسبقة
- GroupDocs.Viewer للغة Java ≥ 25.2  
- JDK 8+ وبيئة تطوير Java (IntelliJ IDEA، Eclipse، VS Code)  
- Maven لإدارة الاعتماديات  

## إعداد GroupDocs.Viewer للغة Java

### تكوين Maven
أضف مستودع GroupDocs واعتماد Viewer إلى ملف `pom.xml` الخاص بك.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### الحصول على الترخيص
ابدأ بنسخة تجريبية مجانية أو اطلب ترخيصًا مؤقتًا للاختبار الموسع. اشترِ ترخيصًا كاملًا للاستخدام في الإنتاج.

### التهيئة الأساسية
أنشئ كائن `Viewer` يشير إلى ملف EML الذي تريد تحويله.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## تحويل eml إلى html مع تاريخ ووقت مخصص في java

الخطوات التالية ترشدك إلى تحويل ملف EML إلى HTML مع تطبيق تنسيق تاريخ ووقت مخصص وإزاحة المنطقة الزمنية.

### الخطوة 1: إعداد دليل الإخراج ومسار الملف
حدد أين سيتم حفظ ملف HTML الناتج.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*شرح:* `Path.of()` ينشئ إشارة إلى المجلد الذي سيُحفظ فيه ملف HTML. `resolve()` يضيف اسم الملف.

### الخطوة 2: تهيئة المشاهد مع ملف البريد
أنشئ كائن `Viewer` للملف EML المستهدف.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*شرح:* كائن `Viewer` يشير إلى ملف EML الذي تريد تحويله.

### الخطوة 3: تكوين HtmlViewOptions
أنشئ كائن `HtmlViewOptions` يدمج الصور والموارد الأخرى مباشرةً في مخرجات HTML.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*شرح:* `forEmbeddedResources()` يدمج الصور والموارد الأخرى مباشرةً في مخرجات HTML.

### الخطوة 4: تعيين تنسيق تاريخ ووقت مخصص *(custom datetime java)*
`setDateTimeFormat` يحدد نمط التاريخ‑الوقت المستخدم عند عرض طوابع البريد.  
حدد النمط الذي سيُستخدم لجميع الطوابع الزمنية في HTML المُنتج.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*شرح:* هذا النمط يعرض الشهر، اليوم، السنة، الساعة، الدقيقة، علامة ص/م، وإزاحة المنطقة الزمنية (`zzz`).

### الخطوة 5: تعيين إزاحة المنطقة الزمنية *(timezone offset java)*
`setTimeZoneOffset` يحدد المنطقة الزمنية التي ستُطبق على جميع طوابع البريد.  
قم بضبط الطوابع الزمنية إلى المنطقة المطلوبة.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*شرح:* يضبط الطوابع الزمنية المعروضة إلى المنطقة المطلوبة. استبدل `"GMT+1"` بأي معرف منطقة صالح.

### كيفية ضبط منطقة زمنية للبريد في java
إذا احتجت إلى **ضبط منطقة زمنية للبريد** تتجاوز الإزاحات البسيطة—مثل التعامل مع التغييرات الصيفية—يمكنك الحصول على كائن `TimeZone` المناسب من API `java.util.TimeZone` باستخدام معرفات المناطق مثل `"Europe/Paris"` أو `"America/New_York"` وتمريره إلى `setTimeZoneOffset`. يضمن ذلك أن طوابع البريد دائمًا تعكس الوقت المحلي الصحيح.

### الخطوة 6: عرض المستند
نفّذ التحويل وأنتج ملف HTML النهائي.

```java
viewer.view(options);
```
*شرح:* ينفّذ التحويل، وينتج ملف HTML بإعدادات التاريخ‑الوقت المخصصة.

## كيف يؤثر تنسيق التاريخ والوقت المخصص على HTML المُنتج؟
يحدد تنسيق التاريخ والوقت المخصص كيفية ظهور كل طابع زمني في HTML المُولد، مما يؤثر على القابلية للقراءة والامتثال للمعايير المحلية. من خلال تحديد نمط مثل `"MMM dd, yyyy hh:mm a zzz"`، تضمن عرض كل تاريخ بشكل موحد، يتضمن اختصار الشهر، اليوم، السنة، الساعة، الدقيقة، علامة ص/م، وإزاحة المنطقة الزمنية الصريحة، وهو أمر حاسم لفرق الدعم العالمية.

## ما هي صيغ الملفات التي يدعمها GroupDocs.Viewer لعرض البريد؟
يمكن لـ GroupDocs.Viewer عرض ملفات **EML، MSG، PST، MBOX، و EMLX** إلى HTML، PDF، PNG، و JPEG. يدعم أكثر من 50 صيغة مستند وصورة، مما يتيح لك تحويل الرسائل إلى أي من مخرجات الويب الشائعة دون الحاجة إلى محولات إضافية.

## كيف يمكنني تحويل عدة ملفات eml دفعة واحدة؟
ضع جميع ملفات EML في دليل واحد، واستخدم حلقة `for` أو `foreach` لتكرار كل ملف، وأعد استخدام نفس كائن `HtmlViewOptions`، واستدعِ `viewer.view` لكل ملف. يقلل هذا النهج من إنشاء الكائنات ويُسرّع التحويلات الجماعية.

## نصائح استكشاف الأخطاء وإصلاحها
- **FileNotFoundException:** تحقق من المسارات المستخدمة في `Viewer` و `Path.of()`.  
- **طوابع زمنية غير صحيحة:** تأكد من أن معرف `TimeZone` يطابق المنطقة المستهدفة.  
- **صور مفقودة:** تأكد من استخدام `HtmlViewOptions.forEmbeddedResources()`؛ وإلا قد تُستبعد الموارد الخارجية.  

## تطبيقات عملية
1. **أرشفة البريد:** حفظ لقطات HTML قابلة للبحث للرسائل للامتثال للتدقيق.  
2. **بوابات دعم العملاء:** عرض التذاكر الواردة بأوقات محلية دقيقة للوكالات حول العالم.  
3. **توثيق قانوني:** إنتاج سجلات بريد إلكتروني جاهزة للمحاكم مع طوابع زمنية موحدة.  

## اعتبارات الأداء
- انشر على خادم مخصص للتحويلات الضخمة.  
- راقب استهلاك heap في Java؛ زد قيمة `-Xmx` إذا واجهت `OutOfMemoryError`.  
- خزن HTML المُحوّل مؤقتًا عندما يُطلب نفس البريد مرارًا لتقليل الحمل على المعالج.  

## الخلاصة
أصبح لديك الآن طريقة كاملة وجاهزة للإنتاج **لتحويل eml إلى html** مع تنسيق تاريخ ووقت مخصص وإزاحة منطقة زمنية باستخدام GroupDocs.Viewer للغة Java. تحسن هذه الحلول قابلية القراءة، وتضمن دقة الطوابع الزمنية، وتندمج بسلاسة في سير عمل الأرشفة أو الدعم أو الوثائق القانونية.

**الخطوات التالية:** استكشف خيارات Viewer الإضافية مثل حقن CSS مخصص، التقسيم إلى صفحات، أو التحويل إلى PDF لتخصيص المخرجات وفقًا لاحتياجات تطبيقك.

## الأسئلة المتكررة

**س: كيف أتعامل مع ملفات eml التي تحتوي على مرفقات؟**  
ج: تُدمج المرفقات تلقائيًا عند استخدام `HtmlViewOptions.forEmbeddedResources()`. يمكنك أيضًا استخراجها عبر API Viewer إذا احتجت ملفات منفصلة.

**س: هل يمكنني تغيير قالب HTML أو إضافة CSS مخصص؟**  
ج: نعم، بعد العرض يمكنك تعديل ملف HTML المُولد أو حقن CSS برمجيًا قبل الحفظ.

**س: هل يمكنني عرض عدة ملفات eml في دفعة واحدة؟**  
ج: غلف منطق العرض داخل حلقة وأعد استخدام نفس كائن `HtmlViewOptions` لكل ملف.

**س: ماذا لو احتجت دعم صيغ بريد أخرى مثل msg؟**  
ج: يدعم GroupDocs.Viewer أيضًا MSG و PST وغيرها من حاويات البريد—فقط غير امتداد الملف في مُنشئ `Viewer`.

**س: هل أحتاج إلى ترخيص منفصل لكل خادم؟**  
ج: الترخيص يكون حسب النشر؛ راجع دليل ترخيص GroupDocs لسيناريوهات الخوادم المتعددة.

## الموارد

- [الوثائق](https://docs.groupdocs.com/viewer/java/)
- [مرجع API](https://reference.groupdocs.com/viewer/java/)
- [التنزيل](https://releases.groupdocs.com/viewer/java/)
- [الشراء](https://purchase.groupdocs.com/buy)
- [نسخة تجريبية مجانية](https://releases.groupdocs.com/viewer/java/)
- [ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/)
- [منتدى الدعم](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-09-15  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 (Java)  
**المؤلف:** GroupDocs

## دروس ذات صلة

- [تحويل البريد الإلكتروني إلى HTML وإعادة تسمية الحقول – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – تحسين عرض البريد إلى PDF باستخدام GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Groupdocs Viewer Java Responsive Html Rendering](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}