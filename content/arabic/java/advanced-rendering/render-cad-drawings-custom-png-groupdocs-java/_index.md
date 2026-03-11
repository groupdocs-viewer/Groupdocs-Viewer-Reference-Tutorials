---
date: '2026-01-08'
description: تعلم كيفية تحويل رسومات CAD إلى صور PNG عالية الجودة باستخدام أبعاد مخصصة
  وألوان خلفية مع GroupDocs.Viewer للغة Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: كيفية تحويل رسومات CAD إلى PNG بحجم مخصص ولون خلفية مخصص باستخدام GroupDocs.Viewer
  للـ Java
type: docs
url: /ar/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# كيفية تحويل رسومات CAD إلى PNG بحجم مخصص ولون خلفية باستخدام GroupDocs.Viewer للغة Java

هل تواجه صعوبة في تحويل رسومات CAD إلى صور عالية الجودة مع الحفاظ على الأبعاد المحددة والجمالية؟ في هذا الدرس سنوضح **how to render CAD** كملفات PNG بحجم مخصص ولون خلفية، حتى تحصل على المظهر الدقيق الذي تحتاجه للتقارير أو العروض التقديمية أو معاينات الويب.

## إجابات سريعة
- **ما معنى “how to render CAD”؟** يشير إلى تحويل ملفات CAD (مثل DWG) إلى صيغ صور مثل PNG باستخدام الكود.  
- **هل يمكنني ضبط عرض مخصص؟** نعم – استخدم `CadOptions.forRenderingByWidth(int width)`.  
- **كيف يمكنني تغيير الخلفية؟** استدعِ `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **ما المكتبة المطلوبة؟** GroupDocs.Viewer للغة Java (الإصدار 25.2 أو أحدث).  
- **هل أحتاج إلى ترخيص؟** الترخيص المؤقت أو المشتري يزيل حدود التقييم.

![Render CAD Drawings as PNG with Custom Size & Background Color with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## كيفية تحويل رسومات CAD – نظرة عامة
يتوسع هذا القسم في الهدف الأساسي: **how to render CAD** رسومات إلى ملفات PNG مع التحكم في الحجم والخلفية. سنستعرض الإعداد الكامل، مقتطفات الكود، والنصائح العملية.

## ما ستتعلمه
- إعداد GroupDocs.Viewer للغة Java في مشروعك  
- **Convert DWG to PNG** بأبعاد مخصصة  
- **Set background color PNG** أثناء التحويل للحصول على مظهر مصقول  
- سيناريوهات واقعية حيث يضيف التحويل المخصص قيمة  

## المتطلبات المسبقة

### المكتبات والاعتمادات المطلوبة
- مجموعة تطوير جافا (JDK) 8+  
- Maven لإدارة الاعتمادات  

### متطلبات إعداد البيئة
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse  
- معرفة أساسية بجافا  

### المتطلبات المعرفية
- الإلمام بالتعامل مع الملفات في جافا  

## إعداد GroupDocs.Viewer للغة Java
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
أنشئ مثيل `Viewer` يشير إلى ملف CAD الخاص بك:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## دليل التنفيذ

### الميزة 1: تحويل رسومات CAD بحجم صورة مخصص ولون خلفية

#### نظرة عامة
تتيح لك هذه الميزة **Convert DWG to PNG** مع تحديد عرض الصورة ولون الخلفية.

#### خطوات التنفيذ خطوة بخطوة

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

##### تهيئة Viewer بخيارات تحويل مخصصة
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
- `setBackgroundColor(Color color)` – **apply background color rendering** إلى PNG.

#### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من وجود مجلد الإخراج؛ أنشئه إذا لزم الأمر.  
- راجع مسار ملف الإدخال والأذونات.  

### الميزة 2: ضبط لون الخلفية في خيارات التحويل

#### نظرة عامة
نركز هنا على **set background color PNG** لتحسين التناسق البصري.

#### خطوات التنفيذ خطوة بخطوة

##### استيراد الحزم المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### تكوين خيارات التحويل مع لون الخلفية
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

**خيارات التكوين الأساسية**  
- عدل `forRenderingByWidth(int width)` لأبعاد مختلفة.  
- استخدم أي ثابت `Color` أو `new Color(r,g,b)` لخلفيات مخصصة.  

## التطبيقات العملية

### 1. وثائق الهندسة
يضمن التحويل المخصص توافق رسومات الهندسة مع دليل الأنماط المؤسسية.

### 2. تصور معماري
اعرض المخططات بخلفية نظيفة تتماشى مع عروض الشرائح.

### 3. نمذجة تصنيع
أنشئ PNG دقيقة لتدفقات عمل النمذجة السريعة.

### إمكانيات التكامل
ادمج خط أنابيب التحويل هذا مع أنظمة إدارة المستندات لأتمتة إنشاء الأصول البصرية.

## اعتبارات الأداء

### تحسين الأداء
- **المعالجة الدفعية:** تحويل عدة ملفات CAD داخل حلقة.  
- **إدارة الموارد:** ضبط حجم heap في JVM للرسومات الكبيرة.

### إرشادات استخدام الموارد
راقب استهلاك المعالج والذاكرة؛ حرر مثيلات `Viewer` فور الانتهاء.

### أفضل الممارسات لإدارة ذاكرة جافا
- استخدم try‑with‑resources (كما هو موضح) لإغلاق `Viewer` تلقائيًا.  
- تجنب الاحتفاظ بكائنات `Path` الكبيرة لفترة أطول من اللازم.

## المشكلات الشائعة والحلول
| المشكلة | الحل |
|-------|----------|
| **مجلد الإخراج غير موجود** | أنشئ الدليل مسبقًا أو أضف `Files.createDirectories(outputDirectory);` |
| **صورة فارغة** | تأكد من ضبط `cadOptions.setBackgroundColor` بعد `forRenderingByWidth`. |
| **أخطاء نفاد الذاكرة** | زد قيمة خيار JVM `-Xmx` أو عالج الملفات على دفعات أصغر. |

## الأسئلة المتكررة

**س: هل يمكنني تحويل صيغ CAD أخرى غير DWG؟**  
ج: نعم، يدعم GroupDocs.Viewer صيغ DXF، DWF، والعديد من صيغ CAD الأخرى.

**س: كيف أستخدم لون RGB مخصص بدلاً من ثابت مسبق؟**  
ج: أنشئ كائن `Color` جديد، مثال `new Color(123, 45, 67)` ومرره إلى `setBackgroundColor`.

**س: هل يمكنني تحويل تخطيط أو طبقة محددة فقط؟**  
ج: يمكنك تحديد خيارات التخطيط أو الطبقة عبر `CadOptions` قبل استدعاء `viewer.view`.

**س: هل تدعم المكتبة خلفيات شفافة؟**  
ج: اضبط لون الخلفية إلى `new Color(0,0,0,0)` للحصول على شفافية كاملة إذا كان التنسيق المستهدف يدعم ذلك.

**س: ما الإصدار المطلوب من GroupDocs.Viewer؟**  
ج: يستخدم الدرس الإصدار 25.2، لكن الإصدارات الأحدث تحتفظ بنفس الـ API.

## الخلاصة
أنت الآن تعرف **how to render CAD** رسومات إلى ملفات PNG بأبعاد مخصصة وألوان خلفية باستخدام GroupDocs.Viewer للغة Java. استخدم هذه التقنيات لإنشاء أصول بصرية احترافية للمهندسين، المعماريين، أو عمليات التصنيع.

### الخطوات التالية
- جرّب أبعاد صور وألوان مختلفة.  
- دمج كود التحويل في خدمة معالجة دفعات.  
- استكشف خيارات Viewer إضافية مثل تحويل PDF أو التحويل متعدد الصفحات.

---

**آخر تحديث:** 2026-01-08  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 للغة Java  
**المؤلف:** GroupDocs  

---