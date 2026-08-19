---
date: '2026-08-19'
description: تعلم كيفية تحويل cdr إلى html، بالإضافة إلى jpg، png، و pdf، باستخدام
  GroupDocs.Viewer for Java. يتضمن الإعداد، أمثلة الكود، ونصائح الأداء.
keywords:
- convert cdr to html
- convert cdr to pdf
- convert cdr to jpg
- convert cdr to png
- java convert coreldraw
lastmod: '2026-08-19'
og_description: تعلم كيفية تحويل cdr إلى html، jpg، png، و pdf باستخدام GroupDocs.Viewer
  for Java. دليل خطوة بخطوة يتضمن الإعداد، مقتطفات الكود، وأفضل ممارسات الأداء.
og_image_alt: Guide showing conversion of CorelDRAW CDR files to HTML, JPG, PNG, and
  PDF using GroupDocs.Viewer for Java
og_title: تحويل cdr إلى html، jpg، png، pdf باستخدام GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  headline: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  type: TechArticle
- description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  name: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  steps:
  - name: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
    text: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Basic Java knowledge** – to understand the code snippets.'
    text: '**Basic Java knowledge** – to understand the code snippets.'
  type: HowTo
- questions:
  - answer: Yes. Load the file with a `Viewer` instance that accepts a password parameter
      (see the API docs).
    question: Can I convert password‑protected CDR files?
  - answer: No hard limit, but very large files may require more memory; consider
      processing page‑by‑page.
    question: Is there a limit on the number of pages that can be converted at once?
  - answer: When using `HtmlViewOptions.forEmbeddedResources`, fonts are embedded
      as Base64, ensuring consistent rendering across browsers.
    question: Does the HTML output include embedded fonts?
  - answer: '`JpgViewOptions` provides a `setQuality(int)` method where you can specify
      a value from 1‑100.'
    question: How do I control JPEG quality?
  - answer: Absolutely—GroupDocs.Viewer is platform‑agnostic as long as the JDK is
      installed.
    question: Can I convert CDR files on a Linux server?
  type: FAQPage
tags:
- convert cdr
- groupdocs.viewer
- java file conversion
- coreldraw cdr
- document rendering
title: تحويل cdr إلى html، jpg، png، pdf باستخدام GroupDocs.Viewer Java
type: docs
url: /ar/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# تحويل cdr إلى html، jpg، png، pdf باستخدام GroupDocs.Viewer Java

إذا كنت بحاجة إلى **تحويل cdr إلى html** (أو إلى JPG، PNG، و PDF) بسرعة وبشكل موثوق، فقد وصلت إلى الدرس المناسب. في هذا الدليل سنستعرض كل ما تحتاجه—من تثبيت GroupDocs.Viewer لجافا إلى تحويل ملفات CorelDRAW (CDR) إلى صفحات HTML صديقة للويب، صور عالية الجودة، وملفات PDF قابلة للقراءة عالميًا. في النهاية، ستتمكن من دمج هذه التحويلات في أي تطبيق جافا ببضع أسطر من الشيفرة فقط.

![Render CDR Files with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

[Render CDR Files with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

## إجابات سريعة
- **ما المكتبة التي تحول CDR إلى HTML؟** GroupDocs.Viewer for Java.  
- **هل يمكنني أيضًا تحويل CDR إلى JPG، PNG، و PDF؟** نعم—استخدم نفس Viewer API مع خيارات عرض مختلفة.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية أو ترخيص مؤقت يعمل للاختبار؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما نسخة Java المطلوبة؟** JDK 8 أو أحدث.  
- **هل يدعم التحويل الجماعي؟** بالتأكيد—ما عليك سوى تكرار الملفات باستخدام نفس كائن Viewer.

## ما هو “convert cdr to html”؟
تحويل cdr إلى html يعني تحويل ملف CorelDRAW المتجه إلى ترميز HTML قياسي، مع إمكانية تضمين الصور والأنماط بحيث يمكن عرض التصميم مباشرةً في متصفح الويب دون الحاجة إلى برنامج التصميم الأصلي. العملية تحافظ على التخطيط الأصلي، الألوان، والأشكال المتجهة عن طريق تحويلها إلى عناصر SVG قابلة للتوسع أو صور نقطية مدمجة في HTML، مما يضمن تمثيلًا بصريًا دقيقًا عبر المتصفحات مع الحفاظ على حجم الملف منخفضًا.

## لماذا تحويل cdr إلى html، jpg، png، أو pdf؟
يمكنك تحويل مصدر CDR واحد إلى أربعة صيغ مدعومة على نطاق واسع، كل منها يخدم غرضًا مميزًا: HTML للمعاينة الفورية على الويب، JPG/PNG للصور النقطية، و PDF للمستندات القابلة للطباعة والأرشفة. هذه المرونة تتيح لك تقديم النوع الأنسب من الملفات لأي عميل، تقليل تكرار التخزين، وضمان استدامة أصولك المستقبلية.

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

1. **المكتبات والاعتمادات** – تم إضافة GroupDocs.Viewer إلى مشروع Maven الخاص بك.  
2. **مجموعة تطوير جافا (JDK)** – نسخة 8 أو أحدث مثبتة.  
3. **معرفة أساسية بجافا** – لفهم مقتطفات الشيفرة.

### المكتبات المطلوبة، الإصدارات، والاعتمادات

أضف تكوين Maven التالي إلى ملف `pom.xml` الخاص بك (بدون تعديل عن الدرس الأصلي):

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

### خطوات الحصول على الترخيص

GroupDocs.Viewer يقدم نسخة تجريبية مجانية، تراخيص مؤقتة للاختبار، أو خيارات شراء كاملة:

- **Free trial** – Download from the [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/).  
- **Temporary license** – Request one at the [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase** – Obtain a permanent license via the [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

## إعداد GroupDocs.Viewer لجافا

Viewer هو الفئة الأساسية التي تقوم بتحميل المستند وتوفر طرق العرض لجميع صيغ الإخراج المدعومة.

### التثبيت باستخدام Maven
مقتطف Maven أعلاه سيجلب جميع ملفات JAR المطلوبة تلقائيًا. فقط نفّذ `mvn clean install` بعد حفظ الملف.

### تهيئة الترخيص
`Viewer` هو الفئة الأساسية التي تقوم بتحميل المستند وتوفر طرق العرض لجميع صيغ الإخراج المدعومة. قم بتهيئة الترخيص قبل عرض أي مستندات:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## دليل التنفيذ

فيما يلي أمثلة خطوة بخطوة لكل صيغة إخراج. كتل الشيفرة مطابقة للدرس الأصلي؛ أضفنا فقط نصًا توضيحيًا حولها.

### كيفية تحويل cdr إلى html باستخدام GroupDocs.Viewer

حمّل ملف CDR واستدعِ API عرض HTML – هذا كل ما تحتاجه لإنشاء ترميز جاهز للويب. العملية تتطلب إعداد مسارات الملفات، إنشاء كائن `HtmlViewOptions`، ثم استدعاء `viewer.view()`. نمط الخطوتين هذا يعمل مع أي حجم مستند ويحافظ على دقة المتجهات.

#### تحويل مستند cdr إلى HTML
**نظرة عامة:** تحويل ملفات CDR إلى HTML صديق للويب لتسهيل المشاركة.

**الخطوة 1 – إعداد مسارات الملفات**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**الخطوة 2 – تهيئة viewer وعرضه**

HtmlViewOptions يضبط إعدادات عرض HTML، مما يتيح لك تضمين الموارد أو حفظها بشكل منفصل. الشيفرة التالية تعرض كل صفحة في ملف HTML منفصل مع تضمين الصور كسلاسل Base64.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### كيفية تحويل cdr إلى jpg باستخدام GroupDocs.Viewer

يمكنك إنتاج صور JPEG عالية الجودة من مصدر CDR في سطرين فقط من الشيفرة. أولًا، اضبط `JpgViewOptions` بالجودة المطلوبة، ثم استدعِ `viewer.view()`. هذا النهج مثالي للصور المصغرة، مرفقات البريد الإلكتروني، أو أي سيناريو يحتاج إلى صورة نقطية مدمجة.

#### تحويل مستند cdr إلى JPG
**نظرة عامة:** إنتاج صور JPEG عالية الجودة من مصدر CDR الخاص بك.

**الخطوة 1 – إعداد مسارات الملفات**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**الخطوة 2 – تهيئة viewer وعرضه**

JpgViewOptions يحدد إعدادات عرض JPEG، مثل جودة الضغط وتسمية المخرجات. المثال أدناه يحفظ كل صفحة كملف JPEG منفصل.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### كيفية تحويل cdr إلى png باستخدام GroupDocs.Viewer

إخراج PNG يمنحك صورًا نقطية غير مضغوطة، مثالية للأرشفة أو المعالجة الرسومية الإضافية. استخدم `PngViewOptions` للحفاظ على كل بكسل، ثم عرض المستند صفحة بصفحة.

#### تحويل مستند cdr إلى PNG
**نظرة عامة:** إنشاء صور PNG غير مضغوطة للأرشفة أو أغراض التصميم.

**الخطوة 1 – إعداد مسارات الملفات**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**الخطوة 2 – تهيئة viewer وعرضه**

PngViewOptions يحدد معلمات عرض PNG، بما في ذلك دعم الخلفيات الشفافة. الشيفرة تنشئ PNG لكل صفحة تلقائيًا.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### كيفية تحويل cdr إلى pdf باستخدام GroupDocs.Viewer

تحويل ملف CDR إلى PDF يمنحك مستندًا جاهزًا للطباعة وقابلًا للقراءة عالميًا. `PdfViewOptions` يتعامل مع تحويل المتجه إلى نقطي داخليًا، محافظًا على التخطيط والخطوط دون الحاجة إلى Adobe Illustrator.

#### تحويل مستند cdr إلى PDF
**نظرة عامة:** تحويل ملفات CDR إلى ملفات PDF قابلة للقراءة عالميًا.

**الخطوة 1 – إعداد مسارات الملفات**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**الخطوة 2 – تهيئة viewer وعرضه**

PdfViewOptions يتحكم في إنشاء PDF، مع تمكين تضمين الخطوط وتخصيص تخطيط الصفحات. المقتطف ينشئ ملف PDF واحد يحتوي على جميع الصفحات.

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## التطبيقات العملية

- **بوابات الويب:** استخدم تحويل HTML لتضمين تصاميم CDR مباشرةً على موقعك.  
- **معارض الصور:** نشر مخرجات JPG/PNG لمعارض سريعة التحميل أو كتالوجات المنتجات.  
- **مشاركة المستندات:** توفير ملفات PDF للعملاء الذين يحتاجون نسخة قابلة للطباعة ولا يمكن تعديلها.  
- **الأرشفة:** حفظ صيغ متعددة لضمان إمكانية الوصول في المستقبل بغض النظر عن تغيّر البرمجيات.  
- **التكامل عبر المنصات:** تمرير الملفات المولدة إلى خدمات لاحقة مثل OCR أو التحليلات أو أنظمة إدارة الأصول الرقمية.

## اعتبارات الأداء

- **تحرير كائنات Viewer فورًا** (كما هو موضح باستخدام try‑with‑resources) لتحرير الذاكرة.  
- **المعالجة الدفعية:** تكرار مجموعة من ملفات CDR باستخدام نفس إعداد Viewer لتقليل الحمل.  
- **تخصيص الموارد:** يمكن لـ GroupDocs.Viewer تحويل مستندات تصل إلى 500 صفحة دون تحميل الملف بالكامل في الذاكرة، لكن الرسومات المعقدة قد تستفيد من زيادة حجم الـ heap. راقب استهلاك المعالج والذاكرة أثناء التحويلات الكبيرة.

## المشكلات الشائعة ونصائح استكشاف الأخطاء

- **الخطوط المفقودة:** إذا كان المخرج يبدو مختلفًا، تأكد من توفر الخطوط المطلوبة على الخادم أو تضمينها عبر `PdfViewOptions`.  
- **الملفات الكبيرة:** بالنسبة لملفات CDR التي تتجاوز 200 ميغابايت، فكر في المعالجة صفحة بصفحة لتجنب `OutOfMemoryError`.  
- **جودة الصورة غير صحيحة:** اضبط قيمة `setQuality` في `JpgViewOptions` إذا كانت ملفات JPEG مضغوطة أكثر من اللازم.  
- **أخطاء الترخيص:** تحقق من صحة مسار ملف الترخيص وأن نسخة الترخيص تتطابق مع نسخة مكتبة Viewer.

## الخلاصة

لقد أظهرنا لك كيفية **تحويل cdr إلى html**، بالإضافة إلى JPG، PNG، و PDF، باستخدام GroupDocs.Viewer لجافا. باتباع مقتطفات الشيفرة المختصرة ونصائح الممارسات الأفضل، يمكنك دمج هذه التحويلات في أي سير عمل قائم على جافا، وتقديم مخرجات مرنة وعالية الجودة لمستخدميك.

### الخطوات التالية
- جرب خيارات العرض المتقدمة مثل أحجام الصفحات المخصصة أو العلامات المائية.  
- دمج خط أنابيب التحويل مع REST API لتقديم تحويل الملفات عند الطلب.  
- انضم إلى المجتمع واطرح أسئلتك في [GroupDocs Forum](https://forum.groupdocs.com/c/viewer).

## الأسئلة المتكررة

**س: هل يمكنني تحويل ملفات CDR المحمية بكلمة مرور؟**  
ج: نعم. حمّل الملف باستخدام كائن `Viewer` الذي يقبل معلمة كلمة المرور (انظر وثائق API).

**س: هل هناك حد لعدد الصفحات التي يمكن تحويلها في مرة واحدة؟**  
ج: لا يوجد حد صريح، لكن الملفات الكبيرة جدًا قد تحتاج إلى مزيد من الذاكرة؛ فكر في المعالجة صفحة بصفحة.

**س: هل يتضمن مخرج HTML خطوطًا مدمجة؟**  
ج: عند استخدام `HtmlViewOptions.forEmbeddedResources`، تُدمج الخطوط كـ Base64، مما يضمن عرضًا متسقًا عبر المتصفحات.

**س: كيف يمكنني التحكم في جودة JPEG؟**  
ج: `JpgViewOptions` يوفر طريقة `setQuality(int)` حيث يمكنك تحديد قيمة من 1 إلى 100.

**س: هل يمكنني تحويل ملفات CDR على خادم لينكس؟**  
ج: بالتأكيد—GroupDocs.Viewer مستقل عن النظام الأساسي طالما تم تثبيت JDK.

---

**آخر تحديث:** 2026-08-19  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs

## دروس ذات صلة

- [How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [How to Convert CF2 to PDF, HTML, JPG, PNG with GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-cf2-files-groupdocs-java/)
- [How to convert pdf to html and optimize image quality in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)