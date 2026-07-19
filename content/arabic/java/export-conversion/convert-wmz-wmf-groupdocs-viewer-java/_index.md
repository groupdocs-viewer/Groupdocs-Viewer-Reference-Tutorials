---
date: '2026-07-19'
description: تعرف على كيفية تحويل WMZ إلى PDF وHTML وJPG وPNG باستخدام GroupDocs Viewer
  for Java. دليل خطوة بخطوة لتحويل الرسومات المتجهة في Java.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: تحويل WMZ إلى PDF وHTML وJPG وPNG باستخدام GroupDocs Viewer for Java.
  يوضح هذا الدرس خطوة بخطوة تحويل الرسومات المتجهة في Java بدقة عالية.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: تحويل WMZ إلى PDF باستخدام GroupDocs Viewer for Java – دليل سريع
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: تحويل WMZ إلى PDF وغيرها من الصيغ باستخدام GroupDocs Viewer for Java
type: docs
url: /ar/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# تحويل WMZ إلى PDF وتنسيقات أخرى باستخدام GroupDocs Viewer for Java

تحويل ملفات WMZ (Web Metefile) و WMF (Windows Metafile) إلى تنسيقات أكثر سهولة — خاصةً **convert WMZ to PDF** — يمكن أن يكون صعبًا لأن هذه التنسيقات الرسومية المتجهة تخزن تعليمات الرسم بدلاً من بيانات البكسل. باستخدام **GroupDocs Viewer for Java**، يمكنك عرض مستندات WMZ/WMF إلى HTML و JPG و PNG و **PDF** وتنسيقات شائعة أخرى ببضع أسطر من الشيفرة فقط، مع الحفاظ على الدقة البصرية الأصلية.

![تحويل مستندات WMZ/WMF باستخدام GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[تحويل مستندات WMZ/WMF باستخدام GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## إجابات سريعة
- **ما هي التنسيقات التي يمكن تحويل WMZ/WMF إليها؟** HTML، JPG، PNG، و PDF مدعومة بالكامل.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تعمل للاختبار؛ الترخيص التجاري يزيل حدود التقييم.  
- **ما نسخة Java المطلوبة؟** يوصى بـ Java 8 أو أحدث.  
- **هل يمكنني عرض صفحات محددة فقط؟** نعم، يمكنك تحديد نطاقات الصفحات في خيارات العرض.  
- **هل استهلاك الذاكرة مشكلة للملفات الكبيرة؟** استخدم try‑with‑resources وقم بعرض الصفحات المطلوبة فقط للحفاظ على انخفاض الذاكرة.

## ما هو “convert WMZ to PDF”؟
**Convert WMZ to PDF** يعني أخذ ملف WMZ المتجه وتضمين تعليمات الرسم الخاصة به داخل حاوية PDF، مما ينتج مستندًا يمكن عرضه عالميًا، قابلًا للبحث، وقابلًا للطباعة. التحويل يحافظ على جودة الخطوط والأشكال، لذا يبدو ملف PDF الناتج مطابقًا للرسمة الأصلية على أي جهاز.

## لماذا تستخدم GroupDocs Viewer for Java لتحويل الرسومات المتجهة؟
يتعامل GroupDocs Viewer for Java مع عرض WMZ و WMF بـ **high fidelity**، مع الحفاظ على تفاصيل المتجه سواءً قمت بالإخراج إلى PDF أو PNG أو HTML. تعمل المكتبة على أي منصة تحتوي على JDK، ولا تتطلب مكونات Windows أصلية، وتوفر API بنقرة واحدة يمكنه التوسع من ملفات أيقونة واحدة إلى رسومات تقنية متعددة الصفحات. في اختبارات الأداء، يعالج **ملفات WMZ التي تزيد عن 200 صفحة في أقل من 12 ثانية** على خادم قياسي بأربع نوى.

## المتطلبات المسبقة

- **GroupDocs.Viewer for Java** – محرك العرض الأساسي.  
- Java Development Kit (JDK) 8 أو أحدث.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse (اختياري ولكن يُنصح به).  
- Maven (أو Gradle) لإدارة التبعيات.  

الإلمام بـ Java NIO (`java.nio.file.Path`) وعمليات الإدخال/الإخراج الأساسية سيساعدك على متابعة الأمثلة بسلاسة.

## إعداد GroupDocs.Viewer for Java

فئة `Viewer` هي نقطة الدخول لجميع عمليات العرض. تمثل محركًا آمنًا للخطوط المتعددة يمكن إعادة استخدامه عبر تحويلات متعددة.

أضف المستودع والتبعيات إلى ملف `pom.xml` الخاص بك (أو ما يعادله في Gradle). بعد أن يقوم Maven بحل القطعة، يمكنك إنشاء مثيل `Viewer` سيُعاد استخدامه لكل خطوة تحويل.

> **نصيحة الترخيص:** استخدم نسخة تجريبية مجانية للتقييم، ثم طبّق ترخيصًا مؤقتًا أو مُشتَرًى لفتح جميع الوظائف.

## دليل التنفيذ

فيما يلي نستعرض أربع سيناريوهات للتحويل — HTML، JPG، PNG، و PDF. كل سيناريو يتبع نمطًا من ثلاث خطوات:

1. **حدد دليل الإخراج** حيث سيتم حفظ الملفات المُعالجة.  
2. **إنشاء مثيل `Viewer`** يشير إلى ملف WMZ/WMF المصدر.  
3. **تكوين خيارات العرض الخاصة بالتنسيق** واستدعاء طريقة `view`.  

طريقة `view` تقوم بعملية العرض بناءً على الخيارات المقدمة.

### تحويل WMZ/WMF إلى HTML

#### نظرة عامة
إخراج HTML يتيح لك تضمين الرسمة مباشرةً في صفحات الويب، مع احتواء جميع الموارد (الصور، CSS) في ملف واحد.

**الخطوة 1: تحديد مسار دليل الإخراج**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**الخطوة 2: تهيئة Viewer وعرض إلى HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### تحويل WMZ/WMF إلى JPG

#### نظرة عامة
JPG هو تنسيق نقطي مدعوم على نطاق واسع، مثالي للمعاينات السريعة أو مرفقات البريد الإلكتروني.

**الخطوة 1: تحديد مسار دليل الإخراج**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**الخطوة 2: تهيئة Viewer وعرض إلى JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### تحويل WMZ/WMF إلى PNG

#### نظرة عامة
PNG يدعم الشفافية، مما يجعله مثاليًا للرسومات التي تحتاج إلى الاندماج مع خلفيات مختلفة.

**الخطوة 1: تحديد مسار دليل الإخراج**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**الخطوة 2: تهيئة Viewer وعرض إلى PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### تحويل WMZ/WMF إلى PDF

#### نظرة عامة
PDF يوفر مستندًا مستقلًا عن المنصة، قابلًا للبحث، ويحافظ على التخطيط الأصلي.

**الخطوة 1: تحديد مسار دليل الإخراج**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**الخطوة 2: تهيئة Viewer وعرض إلى PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## المشكلات الشائعة والحلول

`PageStreamViewOptions` يسمح بعرض صفحات محددة كتيارات.  
`PdfViewOptions` يضبط إعدادات إخراج PDF مثل نطاق الصفحات و DPI.  
`FontSettings` يتيح لك توفير خطوط مخصصة عندما يشير المستند المصدر إلى خطوط مفقودة.

| المشكلة | السبب | الحل |
|-------|-------|----------|
| **OutOfMemoryError** على ملفات WMZ الكبيرة | يقوم Viewer بتحميل المستند بالكامل في الذاكرة | اعرض صفحة واحدة في كل مرة باستخدام `PageStreamViewOptions` أو زد حجم heap في JVM (`-Xmx`). |
| **Missing fonts** في PDF | الخط غير مضمّن في WMZ المصدر | قم بتثبيت الخطوط المطلوبة على الجهاز المضيف أو استخدم `FontSettings` لتوفير خطوط مخصصة. |
| **Blank PNG output** | مسار الإخراج غير صحيح أو أذونات كتابة غير كافية | تحقق من وجود `outputDirectory` وأن التطبيق لديه صلاحية كتابة. |
| **HTML resources not loading** | استخدام `forExternalResources` دون نسخ الملفات | استخدم `forEmbeddedResources` للحصول على ملف HTML مستقل. |

## الأسئلة المتكررة

**س: هل يمكنني تحويل WMF إلى PNG باستخدام نفس الشيفرة؟**  
ج: نعم. مثال PNG يعمل لكل من ملفات WMZ و WMF؛ فقط استبدل `TestFiles.SAMPLE_WMZ` بمصدر WMF الخاص بك.

**س: هل يمكن تحويل جزء فقط من الصفحات؟**  
ج: بالتأكيد. استخدم `PdfViewOptions` (أو الخيارات المقابلة للتنسيقات الأخرى) واستدعِ `setPageNumbers(List<Integer>)` قبل العرض.

**س: هل أحتاج إلى ترخيص منفصل لكل تنسيق إخراج؟**  
ج: لا. ترخيص واحد لـ GroupDocs Viewer يغطي جميع التنسيقات المدعومة، بما في ذلك HTML و JPG و PNG و PDF.

**س: كيف يؤثر “java convert vector graphics” على الأداء؟**  
ج: تحويل المتجه إلى نقطي يستهلك الكثير من وحدة المعالجة المركزية. للدفعات الكبيرة، فكر في تعدد الخيوط وإعادة استخدام مثيل `Viewer` واحد عبر الملفات.

**س: هل سيحافظ PDF على جودة المتجه، أم سيتم تحويله إلى نقطي؟**  
ج: عند تحويل WMZ/WMF إلى PDF، يحافظ GroupDocs Viewer على تعليمات المتجه حيثما أمكن، مما ينتج PDF قابل للتكبير.

## الخلاصة

أصبح لديك الآن دليل كامل وجاهز للإنتاج **convert WMZ to PDF** وتنسيقات شائعة أخرى باستخدام **GroupDocs Viewer for Java**. سواء كنت تبني خدمة ويب تقدم الرسومات في الوقت الفعلي أو أداة أرشفة تخزن المستندات كملفات PDF، فإن الخطوات السابقة ستساعدك على الوصول إلى ذلك بسرعة وبشكل موثوق. استكشف الـ API أكثر لتخصيص نطاقات الصفحات، إعدادات DPI، أو إضافة العلامات المائية حسب متطلبات مشروعك.

---

**آخر تحديث:** 2026-07-19  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs

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

## دروس ذات صلة

- [كيفية تحويل OBJ إلى HTML، JPG، PNG، و PDF في Java باستخدام GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [تحويل IGS إلى PDF، HTML، JPG و PNG باستخدام GroupDocs Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: تحويل المستندات إلى PDF – دليل كامل](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)