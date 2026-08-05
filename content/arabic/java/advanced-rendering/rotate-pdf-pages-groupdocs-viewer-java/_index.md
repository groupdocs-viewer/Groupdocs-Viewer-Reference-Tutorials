---
date: '2026-04-04'
description: تعلم كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer للغة Java.
  يغطي هذا الدليل خطوة بخطوة إعداد Maven، وتدوير PDF بزاوية 90 درجة، وحل المشكلات.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
title: كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer للغة Java
type: docs
url: /ar/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer للغة Java

يمكن أن يكون تدوير صفحات محددة داخل ملف PDF أمرًا أساسيًا لتنسيق المستندات، إصلاح الصور الممسوحة ضوئيًا، أو تعديل شرائح العرض. **في هذا الدليل ستتعلم كيفية تدوير صفحات PDF محددة برمجيًا باستخدام GroupDocs.Viewer**، سواء كنت بحاجة إلى تدوير PDF بزاوية 90 درجة، عكس قسم كامل، أو معالجة صفحات متعددة في استدعاء واحد.

![تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer للغة Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**ما ستتعلمه**
- إعداد GroupDocs.Viewer في مشروع Java الخاص بك (بما في ذلك تكوين Maven لـ GroupDocs Viewer)
- تدوير صفحات PDF محددة برمجيًا (تدوير pdf 90 درجة، 180 درجة، إلخ)
- التكوينات الرئيسية للاستخدام الأمثل
- استكشاف الأخطاء الشائعة وإصلاحها أثناء التنفيذ

## إجابات سريعة
- **ما المكتبة التي يمكنها تدوير صفحات PDF في Java؟** GroupDocs.Viewer for Java.  
- **هل يمكنني تدوير صفحة واحدة بزاوية 90 درجة؟** Yes, use `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.  
- **هل أحتاج إلى ترخيص للتطوير؟** A temporary license is available for free trial.  
- **هل Maven مطلوب؟** Maven is the recommended way to manage GroupDocs dependencies.  
- **كيف أقوم بعرض الصفحات المدورة؟** Use `HtmlViewOptions` and call `viewer.view(...)`.

## المتطلبات المسبقة

### المكتبات والاعتمادات المطلوبة
- مجموعة تطوير جافا (JDK) 8 أو أحدث.
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.
- Maven لإدارة الاعتمادات.

### متطلبات إعداد البيئة
1. **تكوين Maven** – أضف GroupDocs.Viewer إلى ملف `pom.xml` الخاص بك.  
2. **الحصول على الترخيص** – احصل على ترخيص مؤقت من GroupDocs. زر [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) أو قدم طلبًا للحصول على ترخيص مؤقت على صفحة [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## إعداد GroupDocs.Viewer للغة Java

لدمج GroupDocs.Viewer في مشروع Java الخاص بك باستخدام Maven، قم بتحديث ملف `pom.xml` الخاص بك:

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

### التهيئة الأساسية والإعداد
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer
### نظرة عامة
يمنحك تدوير صفحات PDF المحددة تحكمًا دقيقًا في عرض المستند دون تعديل الملف الأصلي.

### الخطوة 1: تكوين تدوير الصفحة
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### الخطوة 2: تهيئة Viewer وعرضه
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### المعلمات والتكوين
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` حيث خيارات التدوير هي `ON_90_DEGREE`، `ON_180_DEGREE`، `ON_270_DEGREE`.  
- **HtmlViewOptions** – يتعامل مع تحويل PDF إلى HTML مع الحفاظ على التخطيط والموارد المدمجة.  
- **pdf to html java** – الفئة هي جزء من نفس الـ API وتضمن تمثيلًا بصريًا دقيقًا.

## لماذا تدوير صفحات PDF محددة؟
- **Document Alignment** – تصحيح اتجاه العقود أو الفواتير الممسوحة ضوئيًا.  
- **Presentation Tweaks** – تعديل الشرائح التي تم تصديرها كملف PDF.  
- **Archival Consistency** – توحيد اتجاه الصفحات أثناء الرقمنة الجماعية.

## المشكلات الشائعة والحلول (استكشاف أخطاء تدوير PDF)
- **Incorrect Paths** – تحقق من أن `YOUR_DOCUMENT_DIRECTORY` و `YOUR_OUTPUT_DIRECTORY` موجودان ويمكن الوصول إليهما.  
- **Missing Dependencies** – تأكد من أن إحداثيات Maven تتطابق مع أحدث نسخة من GroupDocs.Viewer.  
- **License Restrictions** – قم بتطبيق الترخيص المؤقت بشكل صحيح؛ وإلا قد يتم تعطيل بعض الميزات.  
- **Memory Spikes** – قم بعرض ملفات PDF الكبيرة على دفعات أصغر أو زد حجم ذاكرة JVM.

## التطبيقات العملية

### حالات الاستخدام الواقعية
1. **Document Alignment** – تدوير المستندات الممسوحة لضمان الاتجاه الرقمي الصحيح.  
2. **Presentation Adjustments** – تعديل شرائح العرض داخل ملفات PDF قبل المشاركة.  
3. **Archival Workflows** – ضبط اتجاه المستندات التاريخية تلقائيًا أثناء الرقمنة.

### إمكانيات التكامل
اجمع GroupDocs.Viewer مع أنظمة إدارة المحتوى القائمة على Java، البوابات المؤسسية، أو واجهات برمجة التطبيقات المخصصة التي تتطلب عرض PDF في الوقت الفعلي.

## اعتبارات الأداء
- **Resource Management** – احرص دائمًا على إغلاق كائن `Viewer` لتحرير مقابض الملفات والذاكرة.  
- **Java Memory Management** – راقب استخدام الذاكرة عند معالجة ملفات PDF الكبيرة؛ فكر في تدفق الصفحات بدلاً من تحميل الملف بالكامل.  
- **Best Practices** – خزن HTML المعروض مؤقتًا للمستندات التي يتم الوصول إليها بشكل متكرر لتقليل وقت المعالجة.

## الخلاصة
يغطي هذا الدليل **كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer في Java**، بدءًا من إعداد Maven إلى عرض الصفحات المدورة ومعالجة المشكلات الشائعة. جرّب ميزات إضافية مثل إضافة العلامات المائية، تحويل الصيغ، أو المعالجة الدفعية لتوسيع سير عمل المستندات الخاص بك.

**الخطوات التالية:** استكشف قدرات أخرى لـ GroupDocs.Viewer مثل تحويل PDF إلى PNG، إضافة العلامات المائية، أو التكامل مع مزودي التخزين السحابي.

## قسم الأسئلة المتكررة
- **Troubleshooting Rotation Issues** – تحقق من صحة أرقام الصفحات ومعلمات التدوير.  
- **Handling Large PDF Files** – عالج الصفحات على دفعات وراقب استهلاك الذاكرة.  
- **Licensing Requirements** – استخدم ترخيصًا مؤقتًا للتطوير؛ اشترِ ترخيصًا كاملًا للإنتاج.  
- **Rotating Multiple Pages** – استدعِ `rotatePage` بشكل متكرر بأرقام صفحات وزوايا مختلفة.  
- **Integration with Java Libraries** – يعمل GroupDocs.Viewer بسلاسة مع Spring Boot، Jakarta EE، وغيرها من أطر Java.

## الأسئلة المتكررة

**س: هل يمكنني تدوير جميع صفحات PDF مرة واحدة؟**  
ج: نعم. قم بالتكرار عبر أرقام الصفحات واستدعِ `rotatePage(page, Rotation.ON_90_DEGREE)` لكل صفحة.

**س: هل يؤثر التدوير على ملف PDF الأصلي؟**  
ج: لا. يتم تطبيق التدوير فقط أثناء عملية العرض؛ يبقى ملف PDF المصدر دون تغيير.

**س: ماذا لو كان PDF محميًا بكلمة مرور؟**  
ج: قدم كلمة المرور عند إنشاء كائن `Viewer`: `new Viewer(path, password)`.

**س: كيف أقوم بتصحيح خطأ “null pointer” عند إعداد HtmlViewOptions؟**  
ج: تأكد من وجود دليل الإخراج وأن `pageFilePathFormat` يتم حله بشكل صحيح.

**س: هل هناك طريقة لتدوير الصفحات عند التحويل إلى صيغ أخرى (مثل PNG)؟**  
ج: نعم. استخدم نفس إعداد `rotatePage` مع خيارات العرض المناسبة للصيغة المستهدفة.

## الموارد
- **التوثيق**: [توثيق GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API**: [مرجع API لـ GroupDocs](https://reference.groupdocs.com/viewer/java/)  
- **التنزيل**: [صفحة تنزيل GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **الشراء**: [خيارات شراء GroupDocs](https://purchase.groupdocs.com/buy)  
- **تجربة مجانية**: [تجربة مجانية لـ GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **ترخيص مؤقت**: [طلب ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/)  
- **الدعم**: [منتدى دعم GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-04-04  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs