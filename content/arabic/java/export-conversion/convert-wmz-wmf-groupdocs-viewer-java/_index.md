---
date: '2026-02-18'
description: تعلم كيفية تحويل ملفات WMZ و WMF إلى PDF وHTML وJPG وPNG باستخدام GroupDocs
  Viewer للغة Java. يغطي هذا الدليل GroupDocs Viewer Java وتحويل الرسومات المتجهة
  باستخدام Java.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: كيفية تحويل WMZ إلى PDF وصيغ أخرى باستخدام GroupDocs Viewer للـ Java
type: docs
url: /ar/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# كيفية تحويل WMZ إلى PDF وصيغ أخرى باستخدام GroupDocs Viewer for Java

تحويل ملفات WMZ (Web Metafile) و WMF (Windows Metafile) إلى صيغ أكثر قابلية للوصول—خاصةً **convert WMZ to PDF**—يمكن أن يكون صعبًا لأن هذه الصيغ الرسومية المتجهة تخزن تعليمات الرسم بدلاً من بيانات البكسل. باستخدام **GroupDocs Viewer for Java**، يمكنك عرض مستندات WMZ/WMF إلى HTML، JPG، PNG، **PDF**، وصيغ شائعة أخرى ببضع أسطر من الشيفرة.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

في هذا الدرس ستتعلم كيفية إعداد المكتبة، عرض ملفات WMZ/WMF إلى الإخراج المطلوب، ومعالجة المشكلات الشائعة. في النهاية، ستكون قادرًا على دمج **groupdocs viewer java** في تطبيقات Java الخاصة بك لـ **java convert vector graphics** بسرعة وبشكل موثوق.

## إجابات سريعة
- **ما الصيغ التي يمكن تحويل WMZ/WMF إليها؟** HTML، JPG، PNG، و PDF مدعومة بالكامل.  
- **هل أحتاج إلى ترخيص للتطوير؟** نسخة تجريبية مجانية تكفي للاختبار؛ الترخيص التجاري يزيل حدود التقييم.  
- **ما نسخة Java المطلوبة؟** يوصى بـ Java 8 أو أحدث.  
- **هل يمكنني عرض صفحات محددة فقط؟** نعم، يمكنك تحديد نطاقات الصفحات في خيارات العرض.  
- **هل استهلاك الذاكرة مشكلة للملفات الكبيرة؟** استخدم try‑with‑resources واعرض الصفحات المطلوبة فقط للحفاظ على انخفاض الذاكرة.

## ما هو “convert WMZ to PDF”؟
تحويل WMZ إلى PDF يعني أخذ ملف WMZ القائم على المتجهات وتحويله إلى نقطية (أو الحفاظ على بيانات المتجه) داخل حاوية PDF. PDF قابل للعرض والبحث والطباعة عالميًا، مما يجعله مثاليًا لأرشفة ومشاركة رسومات WMZ.

## لماذا نستخدم GroupDocs Viewer for Java لتحويل الرسومات المتجهة؟
- **دقة عالية**: المكتبة تحافظ على جودة الرسم الأصلية، سواءً صدرت إلى PDF أو PNG.  
- **عدم وجود تبعيات خارجية**: لا حاجة لمكتبات Windows الأصلية؛ كل شيء يعمل على أي منصة تحتوي على JDK.  
- **واجهة برمجة تطبيقات بسيطة**: مثيل واحد من `Viewer` واستدعاء واحد لـ `view` يتعامل مع كامل عملية التحويل.  
- **قابل للتوسع**: يعمل بنفس الكفاءة لأيقونات صفحة واحدة ورسومات تقنية متعددة الصفحات.

## المتطلبات المسبقة

### المكتبات المطلوبة
- **GroupDocs.Viewer for Java** – محرك العرض الأساسي.  
- مجموعة تطوير Java (JDK) 8+.

### إعداد البيئة
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.  
- Maven لإدارة التبعيات (أو Gradle إذا كنت تفضل).

### المتطلبات المعرفية
- الإلمام بملفات الإدخال/الإخراج في Java (`java.nio.file.Path`).  
- فهم أساسي لكيفية عرض محتوى عارض المستندات.

## إعداد GroupDocs.Viewer for Java

أضف المستودع والتبعيات إلى ملف `pom.xml` الخاص بك:

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

> **نصيحة الترخيص:** استخدم نسخة تجريبية مجانية للتقييم، ثم قم بتطبيق ترخيص مؤقت أو مُشتَرٍ لفتح جميع الوظائف.

بعد حل التبعيات، يمكنك إنشاء مثيل `Viewer` سيتم إعادة استخدامه في كل خطوة تحويل.

## دليل التنفيذ

سنستعرض أربع سيناريوهات للتحويل: HTML، JPG، PNG، و PDF. كل مثال يتبع نفس النمط—تحديد مسار الإخراج، إنشاء مثيل `Viewer` مع ملف WMZ المصدر، ضبط خيارات العرض المناسبة، واستدعاء `view`.

### عرض WMZ/WMF إلى HTML

#### نظرة عامة
إخراج HTML يتيح لك تضمين الرسمة مباشرةً في صفحات الويب، مع جميع الموارد (الصور، CSS) مدمجة في ملف واحد.

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

### عرض WMZ/WMF إلى JPG

#### نظرة عامة
JPG هو صيغة نقطية مدعومة على نطاق واسع، مثالية للمعاينات السريعة أو مرفقات البريد الإلكتروني.

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

### عرض WMZ/WMF إلى PNG

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

### عرض WMZ/WMF إلى PDF

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

| المشكلة | السبب | الحل |
|-------|-------|----------|
| **OutOfMemoryError** على ملفات WMZ الكبيرة | يقوم Viewer بتحميل المستند بالكامل في الذاكرة | اعرض صفحة واحدة في كل مرة باستخدام `PageStreamViewOptions` أو زد حجم heap للـ JVM (`-Xmx`). |
| **Missing fonts** في PDF | الخط غير مضمن في ملف WMZ المصدر | قم بتثبيت الخطوط المطلوبة على الجهاز المضيف أو استخدم `FontSettings` لتوفير خطوط مخصصة. |
| **Blank PNG output** | مسار إخراج غير صحيح أو أذونات كتابة غير كافية | تحقق من وجود `outputDirectory` وأن التطبيق يملك صلاحية الكتابة. |
| **HTML resources not loading** | استخدام `forExternalResources` دون نسخ الملفات | استخدم `forEmbeddedResources` للحصول على ملف HTML مستقل. |

## الأسئلة المتكررة

**س: هل يمكنني تحويل WMF إلى PNG باستخدام نفس الشيفرة؟**  
ج: نعم. مثال PNG يعمل لكل من ملفات WMZ و WMF؛ فقط استبدل `TestFiles.SAMPLE_WMZ` بمصدر WMF الخاص بك.

**س: هل يمكن تحويل جزء فقط من الصفحات؟**  
ج: بالتأكيد. استخدم `PdfViewOptions` (أو الخيارات المقابلة للصيغ الأخرى) واستدعِ `setPageNumbers(List<Integer>)` قبل العرض.

**س: هل أحتاج إلى ترخيص منفصل لكل صيغة إخراج؟**  
ج: لا. ترخيص واحد لـ GroupDocs Viewer يغطي جميع الصيغ المدعومة، بما في ذلك HTML، JPG، PNG، و PDF.

**س: كيف يؤثر “java convert vector graphics” على الأداء؟**  
ج: تحويل المتجه إلى نقطية يستهلك الكثير من وحدة المعالجة المركزية. للدفعات الكبيرة، فكر في تعدد الخيوط وإعادة استخدام مثيل `Viewer` واحد عبر الملفات.

**س: هل سيحافظ PDF على جودة المتجه أم سيتم تحويله إلى نقطية؟**  
ج: عند تحويل WMZ/WMF إلى PDF، يحافظ GroupDocs Viewer على تعليمات المتجه حيثما أمكن، مما ينتج PDF قابل للتكبير.

## الخلاصة

الآن لديك دليل كامل وجاهز للإنتاج **convert WMZ to PDF** وصيغ شائعة أخرى باستخدام **GroupDocs Viewer for Java**. سواءً كنت تبني خدمة ويب تقدم الرسومات في الوقت الفعلي أو أداة أرشفة تخزن المستندات كملفات PDF، فإن الخطوات السابقة ستساعدك على الوصول إلى ذلك بسرعة.

---

**آخر تحديث:** 2026-02-18  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs