---
date: '2026-03-16'
description: تعلم كيفية تحويل ملفات DWG إلى PNG بحجم مخصص ولون خلفية مخصص باستخدام
  GroupDocs.Viewer للغة Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: كيفية تحويل DWG إلى PNG بحجم مخصص ولون خلفية باستخدام GroupDocs.Viewer للـ
  Java
type: docs
url: /ar/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# كيف تقوم بتحويل DWG إلى PNG بحجم مخصص ولون خلفية باستخدام GroupDocs.Viewer للـ Java

إذا كنت تبحث عن **تحويل DWG إلى PNG** مع الحفاظ على التحكم الكامل في أبعاد الصورة وتنسيق الخلفية، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنرشدك إلى كيفية عرض ملفات CAD كصور PNG، وتخصيص العرض، وتغيير لون الخلفية بحيث يتطابق الناتج مع تقاريرك أو عروضك أو متطلبات معاينة الويب.

## إجابات سريعة
- **ماذا يعني “تحويل DWG إلى PNG”؟** هو عملية تحويل ملف CAD بصيغة DWG إلى صورة PNG باستخدام الكود.  
- **هل يمكنني تعيين عرض مخصص؟** نعم – استخدم `CadOptions.forRenderingByWidth(int width)`.  
- **كيف أغير لون الخلفية؟** استدعِ `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **ما المكتبة المطلوبة؟** GroupDocs.Viewer للـ Java (الإصدار 25.2 أو أحدث).  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت أو المشتراة يزيل حدود التقييم.

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## نظرة عامة على كيفية تحويل DWG إلى PNG
في هذا القسم نوسّع الهدف الأساسي: **كيفية تحويل DWG إلى PNG** مع التحكم في الحجم والخلفية. ستشاهد الإعداد الكامل، والكود الدقيق الذي تحتاجه، ونصائح عملية لتجنب الأخطاء الشائعة.

## ما ستتعلمه
- إعداد GroupDocs.Viewer للـ Java في مشروع Maven  
- **تحويل DWG إلى PNG** بأبعاد مخصصة  
- **تغيير لون خلفية CAD** أثناء العرض للحصول على مظهر مصقول  
- سيناريوهات واقعية حيث يضيف العرض المخصص قيمة  

## المتطلبات المسبقة

### المكتبات والاعتمادات المطلوبة
- مجموعة تطوير جافا (JDK) 8+  
- Maven لإدارة الاعتمادات  

### متطلبات إعداد البيئة
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse  
- معرفة أساسية بجافا  

### المتطلبات المعرفية
- الإلمام بالتعامل مع الملفات في جافا  

## إعداد GroupDocs.Viewer للـ Java
أضف مستودع GroupDocs والاعتماد إلى ملف `pom.xml` الخاص بـ Maven:

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
احصل على ترخيص مؤقت أو كامل لإزالة قيود التقييم.

### التهيئة الأساسية والإعداد
أنشئ كائن `Viewer` يشير إلى ملف CAD الخاص بك:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## الميزة 1: عرض رسومات CAD بحجم صورة مخصص ولون خلفية مخصص

### كيفية تغيير لون خلفية CAD
تتيح لك هذه الميزة **تحويل DWG إلى PNG** مع تحديد عرض مخصص وتطبيق لون خلفية جديد.

#### تنفيذ خطوة بخطوة

##### استيراد الحزم المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### إعداد دليل الإخراج وصيغة مسار الملف
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### تهيئة Viewer مع خيارات عرض مخصصة
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
- `PngViewOptions` – يحدد صيغة الإخراج والتسمية.  
- `forRenderingByWidth(int width)` – يضبط عرض الصورة المخصص.  
- `setBackgroundColor(Color color)` – **تعيين لون خلفية PNG** لتحسين التناسق البصري.

#### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من وجود مجلد الإخراج؛ أنشئه إذا لزم الأمر.  
- راجع مسار ملف الإدخال والأذونات مرة أخرى.  

## الميزة 2: تعيين لون الخلفية في خيارات العرض

### كيفية تعيين لون خلفية PNG
نركز هنا على خيار **set background color PNG** لضمان أن كل صورة مُصدرة تتطابق مع لوحة ألوان علامتك التجارية.

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
- عدّل `forRenderingByWidth(int width)` لأبعاد مختلفة.  
- استخدم أي ثابت `Color` أو أنشئ `new Color(r,g,b)` لخلفيات مخصصة.  

## تطبيقات عملية

### 1. وثائق الهندسة
يضمن العرض المخصص أن تتوافق الرسومات الهندسية مع دليل أسلوب الشركة.

### 2. تصور معماري
اعرض المخططات بخلفية نظيفة تتماشى مع عروض الشرائح.

### 3. نمذجة تصنيع
أنشئ PNG دقيقة لتدفقات عمل النماذج الأولية السريعة.

### إمكانيات التكامل
اجمع خط أنابيب العرض هذا مع أنظمة إدارة المستندات لأتمتة إنشاء الأصول البصرية.

## اعتبارات الأداء

### تحسين الأداء
- **المعالجة الدفعية:** عرض عدة ملفات CAD داخل حلقة.  
- **إدارة الموارد:** ضبط حجم heap في JVM للرسومات الكبيرة.

### إرشادات استخدام الموارد
راقب استهلاك المعالج والذاكرة؛ حرّر كائنات `Viewer` فور الانتهاء.

### أفضل الممارسات لإدارة الذاكرة في جافا
- استخدم try‑with‑resources (كما هو موضح) لإغلاق `Viewer` تلقائيًا.  
- تجنّب الاحتفاظ بكائنات `Path` الكبيرة لفترة أطول من الحاجة.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **مجلد الإخراج غير موجود** | أنشئ الدليل مسبقًا أو أضف `Files.createDirectories(outputDirectory);` |
| **صورة فارغة** | تأكد من تعيين `cadOptions.setBackgroundColor` بعد `forRenderingByWidth`. |
| **أخطاء نفاد الذاكرة** | زد قيمة خيار JVM `-Xmx` أو عالج الملفات على دفعات أصغر. |

## الأسئلة المتكررة

**س: هل يمكنني عرض صيغ CAD أخرى غير DWG؟**  
ج: نعم، يدعم GroupDocs.Viewer صيغ DXF، DWF، والعديد من صيغ CAD الأخرى.

**س: كيف أستخدم لون RGB مخصص بدلاً من ثابت مسبق؟**  
ج: أنشئ كائن `Color` جديد، مثال: `new Color(123, 45, 67)` ومرره إلى `setBackgroundColor`.

**س: هل يمكن عرض تخطيط أو طبقة محددة فقط؟**  
ج: يمكنك تحديد خيارات التخطيط أو الطبقة عبر `CadOptions` قبل استدعاء `viewer.view`.

**س: هل تدعم المكتبة خلفيات شفافة؟**  
ج: عيّن لون الخلفية إلى `new Color(0,0,0,0)` للحصول على شفافية كاملة إذا كان التنسيق المستهدف يدعم ذلك.

**س: ما هو الإصدار المطلوب من GroupDocs.Viewer؟**  
ج: يستخدم الدرس الإصدار 25.2، لكن الإصدارات الأحدث تحتفظ بنفس الـ API.

---

**آخر تحديث:** 2026-03-16  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 للـ Java  
**المؤلف:** GroupDocs