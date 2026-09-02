---
date: '2026-08-30'
description: تعلم كيفية تحويل DWG إلى PNG، وتعيين لون الخلفية في Java، وتخصيص حجم
  الصورة باستخدام GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: تحويل DWG إلى PNG باستخدام GroupDocs.Viewer for Java مع ضبط عرض الصورة
  المخصص ولون الخلفية. يقدم هذا الدليل إعدادًا خطوة بخطوة، مقتطفات كود، ونصائح لاستكشاف
  الأخطاء وإصلاحها.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: تحويل DWG إلى PNG بحجم مخصص ولون خلفية في Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: كيفية تحويل DWG إلى PNG بحجم مخصص ولون خلفية باستخدام GroupDocs.Viewer for
  Java
type: docs
url: /ar/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# كيفية تحويل DWG إلى PNG بحجم مخصص ولون خلفية باستخدام GroupDocs.Viewer للـ Java

في هذا البرنامج التعليمي ستتعلم **كيفية تحويل DWG إلى PNG** مع التحكم في أبعاد الإخراج ولون الخلفية، باستخدام GroupDocs.Viewer للـ Java. سواء كنت بحاجة إلى تضمين رسومات CAD في تقرير، أو إنشاء صور مصغرة لبوابة ويب، أو أتمتة عملية التحويل على دفعات، فإن الخطوات أدناه تمنحك التحكم الكامل في المظهر البصري لكل ملف PNG.

## إجابات سريعة
- **ماذا يعني “تحويل DWG إلى PNG”؟** هو عملية تحويل ملف CAD بصيغة DWG إلى صورة PNG عبر الكود، مع الحفاظ على تفاصيل المتجهات كبيكسلات نقطية.  
- **هل يمكنني تعيين عرض مخصص؟** نعم – استدعِ `CadOptions.forRenderingByWidth(int width)` لتحديد عرض البكسل الدقيق الذي تحتاجه.  
- **كيف يمكنني تغيير لون الخلفية؟** استخدم `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` قبل عملية العرض.  
- **ما المكتبة المطلوبة؟** GroupDocs.Viewer للـ Java (الإصدار 25.2 أو أحدث).  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت أو الكامل يزيل حدود التقييم ويفتح إمكانية العرض غير المحدودة.

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## ما هو GroupDocs.Viewer للـ Java؟
GroupDocs.Viewer للـ Java هو واجهة برمجة تطبيقات (API) من جانب الخادم تقوم بتحويل أكثر من 150 صيغة ملف—بما في ذلك ملفات CAD—إلى صور أو ملفات PDF أو HTML. يعمل دون الحاجة إلى أي برنامج طرف ثالث مثل AutoCAD، مما يجعله مثالياً للخطوط الآلية.

## كيفية تحويل DWG إلى PNG بحجم مخصص ولون خلفية؟
حمّل ملف DWG باستخدام كائن `Viewer`، واضبط `CadOptions` للعرض المطلوب ولون الخلفية، ثم استدعِ `viewer.view` مع `PngViewOptions`. تدير هذه العملية ذات الثلاث خطوات إدخال/إخراج الملف، والعرض، وتسمية الناتج في عملية واحدة فعّالة من حيث الذاكرة.

Viewer هو الصنف الأساسي الذي يحمل المستند ويقوم بالعرض.  
CadOptions يضبط إعدادات CAD الخاصة مثل عرض الصورة ولون الخلفية.  
PngViewOptions يحدد صيغة الإخراج PNG ونمط تسمية الصفحات المعروضة.

يمكنك الآن عرض أي رسم DWG إلى PNG بالعرض الذي تحدده بالضبط، ويمكنك اختيار أي لون خلفية صلب (أو شفاف) ليتماشى مع علامتك التجارية أو سمة واجهة المستخدم.

## لماذا تعيين لون خلفية مخصص؟
تعيين لون الخلفية يضمن أن صورة PNG المعروضة تندمج بسلاسة مع عناصر واجهة المستخدم المحيطة، ويتجنب الهوامش البيضاء غير المرغوبة، ويمكنه إبراز تفاصيل الرسم التي قد تُفقد على خلفية بيضاء افتراضية. يدعم GroupDocs.Viewer أي `java.awt.Color`، بما في ذلك قيم RGB المخصصة، مما يمنحك تحكمًا دقيقًا على مستوى البكسل.

java.awt.Color تمثل قيمة لون تُستخدم في رسم الخلفيات.

## المتطلبات المسبقة

- **Java Development Kit (JDK) 8+** – تستهدف الواجهة Java 8 وما فوق.  
- **Maven** – لإدارة الاعتمادات.  
- **IDE** – IntelliJ IDEA أو Eclipse أو أي محرر تفضله.  
- **معرفة أساسية بمعالجة ملفات Java** – لقراءة ملفات DWG المصدر وكتابة مخرجات PNG.

## إعداد GroupDocs.Viewer للـ Java
أضف مستودع GroupDocs واعتماد Viewer إلى ملف `pom.xml` الخاص بـ Maven:

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

### الحصول على الترخيص
احصل على مفتاح ترخيص مؤقت أو كامل من بوابة GroupDocs وضع ملف `license.lic` في مجلد موارد المشروع. يزيل هذا حد التقييم المكوّن من 20 صفحة ويفتح إمكانية العرض بدقة كاملة.

### التهيئة الأساسية والإعداد
أنشئ كائن `Viewer` يشير إلى المجلد الذي يحتوي على ملفات DWG الخاصة بك:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## الميزة 1: عرض رسومات CAD بحجم صورة مخصص ولون خلفية

### كيفية تغيير لون خلفية CAD
لتغيير لون خلفية CAD، اضبط كائن CadOptions قبل العرض. حدد العرض المطلوب باستخدام `forRenderingByWidth` وطبق الخلفية الجديدة باستخدام `setBackgroundColor`. ثم يولد المشاهد (viewer) صور PNG تعكس اللون المحدد، مما يضمن نمطًا بصريًا متسقًا عبر جميع ملفات الإخراج.

#### تنفيذ خطوة بخطوة

##### استيراد الحزم المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### إعداد دليل الإخراج وتنسيق مسار الملف
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### تهيئة المشاهد بخيارات عرض مخصصة
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**شرح المعلمات**  
- `PngViewOptions` – يحدد صيغة الإخراج PNG ونمط تسمية الصفحات.  
- `forRenderingByWidth(int width)` – يجبر المعرّف على إنتاج صورة يكون عرضها مساويًا لقيمة البكسل المحددة؛ يتم تعديل الارتفاع بنسبة تناسبية.  
- `setBackgroundColor(Color color)` – يستبدل القماش الأبيض الافتراضي باللون الذي تختاره، محسنًا التناسق البصري عبر الأصول المولدة.

#### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من وجود مجلد الإخراج؛ استخدم `Files.createDirectories(outputDir)` إذا لم يكن موجودًا.  
- تحقق من صحة مسار ملف الإدخال وأن التطبيق يمتلك أذونات القراءة.

## الميزة 2: تعيين لون الخلفية في خيارات العرض

### كيفية تعيين لون خلفية PNG
يتضمن تعيين لون خلفية PNG إنشاء مثيل `Color` وتعيينه إلى `CadOptions` قبل العرض. يضمن ذلك أن كل صورة PNG مُولدة تستخدم الخلفية المحددة، متطابقةً مع إرشادات علامتك التجارية أو سمة واجهة المستخدم. يمكنك استخدام الثوابت المعرفة مسبقًا أو تعريف قيم RGB مخصصة للتحكم الدقيق.

java.awt.Color تمثل قيمة لون تُستخدم في رسم الخلفيات.

#### تنفيذ خطوة بخطوة

##### استيراد الحزم المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### تكوين خيارات العرض مع لون الخلفية
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**خيارات التكوين الرئيسية**  
- اضبط `forRenderingByWidth(int width)` لأبعاد مختلفة، مثل 800 px للصور المصغرة على الويب أو 1920 px للطباعة عالية الدقة.  
- استخدم أي ثابت `Color` معرف مسبقًا (مثل `Color.LIGHT_GRAY`) أو أنشئ مثيلًا مخصصًا بـ `new Color(r, g, b)` للحصول على تحكم دقيق في العلامة التجارية.  

## التطبيقات العملية

### 1. وثائق الهندسة
يضمن العرض المخصص أن كل رسم يلتزم بدليل أسلوب الشركة، مما يلغي الحاجة إلى تعديل الصور يدويًا بعد التصدير.

### 2. التصور المعماري
اعرض المخططات بخلفية تتطابق مع عروض الشرائح أو البوابات الموجهة للعملاء، محسنًا التماسك البصري.

### 3. نمذجة التصنيع
أنشئ PNGs لتدفقات عمل النماذج السريعة حيث تتوقع الأدوات اللاحقة حجم صورة محدد وخلفية معينة.

### إمكانيات التكامل
اجمع هذه الخطوة مع نظام إدارة المستندات (مثل SharePoint) لتوليد صور معاينة تلقائيًا كلما تم رفع ملف DWG.

## اعتبارات الأداء

### تحسين الأداء
- **Batch processing:** قم بعمل حلقة عبر دليل يحتوي على ملفات DWG وعرِض كل ملف على التوالي لتقليل تكاليف إحماء JVM.  
- **Resource management:** للرسومات الكبيرة (أكثر من 500 صفحة)، زد حجم ذاكرة JVM (`-Xmx2g`) أو عالج الملفات على دفعات أصغر لتجنب أخطاء الذاكرة.

### إرشادات استخدام الموارد
راقب استهلاك CPU والذاكرة باستخدام أدوات مثل VisualVM؛ حرّر كائنات `Viewer` فورًا باستخدام try‑with‑resources.

### أفضل الممارسات لإدارة ذاكرة Java
- استخدم try‑with‑resources (كما هو موضح) لإغلاق `Viewer` تلقائيًا.  
- تجنّب الاحتفاظ بكائنات `Path` الكبيرة بعد الانتهاء من استخدامها.  

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| مجلد الإخراج غير موجود | أنشئ الدليل مسبقًا أو أضف `Files.createDirectories(outputDirectory);` |
| صورة فارغة | تأكد من استدعاء `cadOptions.setBackgroundColor` بعد `forRenderingByWidth`. |
| أخطاء نفاد الذاكرة | زد خيار JVM `-Xmx` أو عالج الملفات على دفعات أصغر. |

## الأسئلة المتكررة

**س: هل يمكنني عرض صيغ CAD أخرى غير DWG؟**  
ج: نعم، يدعم GroupDocs.Viewer صيغ DXF و DWF والعديد من صيغ CAD الإضافية.

**س: كيف يمكنني استخدام لون RGB مخصص بدلاً من ثابت معرف مسبقًا؟**  
ج: أنشئ كائن `Color` جديد باستخدام `new Color(123, 45, 67)` ومرره إلى `setBackgroundColor`.

**س: هل من الممكن عرض تخطيط أو طبقة محددة فقط؟**  
ج: يمكنك تحديد خيارات التخطيط أو الطبقة عبر `CadOptions` قبل استدعاء `viewer.view`.

**س: هل تدعم المكتبة خلفيات شفافة؟**  
ج: اضبط لون الخلفية إلى `new Color(0,0,0,0)` للحصول على شفافية كاملة إذا كان تنسيق الإخراج يدعم ذلك.

**س: ما إصدار GroupDocs.Viewer المطلوب؟**  
ج: يستخدم هذا البرنامج التعليمي الإصدار 25.2، لكن الإصدارات الأحدث تحتفظ بنفس واجهة البرمجة.

---

**Last Updated:** 2026-08-30  
**Tested With:** GroupDocs.Viewer 25.2 للـ Java  
**Author:** GroupDocs

## دروس ذات صلة

- [groupdocs viewer dwg – كيفية عرض رسومات CAD محددة في Java باستخدام GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Render CAD Layers Java with GroupDocs.Viewer – دليل كامل](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [How to convert pdf to html and optimize image quality in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)