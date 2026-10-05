---
date: '2026-10-05'
description: تعلم كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer for Java.
  يقدّم هذا الدليل خطوة بخطوة إعداد Maven، وتدوير PDF بزاوية 90 درجة، وحل المشكلات.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer for Java. تعلم كيفية
  تدوير PDF بزاوية 90 درجة، وتكوين Maven، وحل المشكلات الشائعة في دليل مختصر.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer for Java
type: docs
url: /ar/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer للـ Java

يمكن أن يكون تدوير صفحات محددة داخل ملف PDF أمرًا ضروريًا لتنسيق المستندات، إصلاح الصور الممسوحة ضوئيًا، أو تعديل شرائح العرض. **في هذا الدليل ستتعلم كيفية تدوير صفحات PDF محددة برمجيًا باستخدام GroupDocs.Viewer**، سواء كنت بحاجة إلى تدوير PDF بزاوية 90 درجة، أو عكس قسم كامل، أو معالجة صفحات متعددة في استدعاء واحد.

![تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer للـ Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer للـ Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**ما ستتعلمه**
- إعداد GroupDocs.Viewer في مشروع Java الخاص بك (بما في ذلك تكوين Maven لـ GroupDocs Viewer)
- تدوير صفحات PDF محددة برمجيًا (تدوير pdf 90 درجة، 180 درجة، إلخ)
- التكوينات الرئيسية للاستخدام الأمثل
- استكشاف المشكلات الشائعة أثناء التنفيذ

## إجابات سريعة
- **ما المكتبة التي يمكنها تدوير صفحات PDF في Java؟** GroupDocs.Viewer for Java توفر دعم تدوير مدمج دون أدوات خارجية.  
- **هل يمكنني تدوير صفحة واحدة بزاوية 90 درجة؟** نعم – استدعِ `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` على كائن الـ viewer.  
- **هل أحتاج إلى ترخيص للتطوير؟** الترخيص المؤقت مجاني للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل Maven مطلوب؟** Maven هو مدير الاعتماديات الموصى به، لكن يمكنك أيضًا استخدام Gradle أو تضمين JAR يدويًا.  
- **كيف يمكنني عرض الصفحات المدورة؟** استخدم `HtmlViewOptions` مع `viewer.view(documentPath, viewOptions)` للحصول على مخرجات HTML تعكس التدوير.

## ما هو تدوير صفحات PDF المحددة؟
`rotate specific pdf pages` تشير إلى القدرة على تغيير اتجاه صفحات فردية داخل مستند PDF مع ترك باقي الملف دون تعديل. يتم تنفيذ هذه العملية أثناء وقت العرض، لذا يبقى ملف PDF الأصلي دون تغيير.

## لماذا تدوير صفحات PDF المحددة؟
يمكنك تدوير صفحة واحدة في أقل من 0.05 ثانية على خادم افتراضي من فئة الخوادم المعتادة، مما يتيح معاينة فورية للمستندات الممسوحة، عروض الشرائح، أو الفواتير متعددة الصفحات التي تحتوي على مسحات غير موجهة بشكل صحيح. يزيل هذا التحكم الدقيق الحاجة إلى أدوات ما بعد المعالجة المكلفة ويقلل الجهد اليدوي بنسبة تصل إلى 70 % في مشاريع الرقمنة واسعة النطاق.

## المتطلبات المسبقة

### المكتبات والاعتماديات المطلوبة
- Java Development Kit (JDK) 8 أو أحدث.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
- Maven لإدارة الاعتماديات.

### متطلبات إعداد البيئة
1. **Maven configuration** – أضف GroupDocs.Viewer إلى ملف `pom.xml` الخاص بك.  
2. **License acquisition** – احصل على ترخيص مؤقت من GroupDocs. زر [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) أو قدّم طلبًا للحصول على ترخيص مؤقت عبر [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## إعداد GroupDocs.Viewer للـ Java

لدمج GroupDocs.Viewer في مشروع Java باستخدام Maven، حدّث ملف `pom.xml` الخاص بك:

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
`Viewer` هو الفئة الأساسية التي تقوم بتحميل المستند وتنسيق عمليات العرض. بعد إنشاء نسخة يمكنك استدعاء طرق مثل `view` أو `rotatePage`.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer
تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer يتضمن عمليتين رئيسيتين: أولاً، تحديد التدوير المطلوب لكل صفحة مستهدفة باستخدام طريقة `rotatePage`، وثانيًا، عرض المستند باستخدام `HtmlViewOptions` بحيث ينعكس التدوير في الناتج. يحافظ هذا النهج على ملف PDF الأصلي دون تغيير مع تقديم HTML موجه بشكل صحيح.

### الخطوة 1: تكوين تدوير الصفحة
`rotatePage` هي طريقة تقبل فهرس صفحة يبدأ من الصفر وقيمة من تعداد `Rotation`. يوفر التعداد ثلاث خيارات: `ON_90_DEGREE`، `ON_180_DEGREE`، و`ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### الخطوة 2: تهيئة الـ viewer والعرض
`HtmlViewOptions` يتحكم في عملية تحويل PDF إلى HTML. يحافظ على التخطيط، الخطوط، والموارد المدمجة مع تطبيق أي تدوير قمت بتكوينه.  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### المعلمات والتكوين
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` حيث خيارات التدوير هي `ON_90_DEGREE`، `ON_180_DEGREE`، `ON_270_DEGREE`.  
- **HtmlViewOptions** – يتعامل مع تحويل pdf‑to‑html مع الحفاظ على التخطيط والموارد المدمجة.  
- **pdf to html java** – الفئة جزء من نفس الـ API وتضمن تمثيلًا بصريًا دقيقًا.

## المشكلات الشائعة والحلول (استكشاف أخطاء تدوير PDF)
- **Incorrect paths** – تحقق من أن `YOUR_DOCUMENT_DIRECTORY` و`YOUR_OUTPUT_DIRECTORY` موجودان ويمكن الوصول إليهما.  
- **Missing dependencies** – تأكد من أن إحداثيات Maven تتطابق مع أحدث نسخة من GroupDocs.Viewer (حالياً 25.2).  
- **License restrictions** – طبّق الترخيص المؤقت بشكل صحيح؛ وإلا قد تُعطَّل بعض الميزات.  
- **Memory spikes** – عالج ملفات PDF الكبيرة على دفعات أصغر أو زد حجم heap الخاص بـ JVM.

## التطبيقات العملية

### حالات الاستخدام الواقعية
1. **Document alignment** – تدوير العقود الممسوحة للحصول على توجيه رقمي صحيح.  
2. **Presentation adjustments** – تعديل شرائح العروض داخل ملفات PDF قبل المشاركة.  
3. **Archival workflows** – ضبط اتجاه المستندات التاريخية تلقائيًا أثناء عملية الرقمنة.

### إمكانيات التكامل
اجمع GroupDocs.Viewer مع أنظمة إدارة المحتوى المبنية على Java، البوابات المؤسسية، أو واجهات برمجة التطبيقات المخصصة التي تتطلب عرض PDF في الوقت الفعلي.

## اعتبارات الأداء
- **Resource management** – أغلق دائمًا نسخة `Viewer` لتحرير مقابض الملفات والذاكرة.  
- **Java memory management** – راقب استهلاك heap عند معالجة ملفات PDF الكبيرة؛ فكر في تدفق الصفحات بدلاً من تحميل الملف بالكامل.  
- **Best practices** – خزن HTML المُعرض مؤقتًا للمستندات التي تُستدعى بشكل متكرر لتقليل زمن المعالجة بنسبة تصل إلى 60 %.

## الخلاصة
غطى هذا الدرس **كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer في Java**، بدءًا من إعداد Maven إلى عرض الصفحات المدورة ومعالجة المشكلات الشائعة. جرّب ميزات إضافية مثل إضافة العلامات المائية، تحويل الصيغ، أو المعالجة الدفعية لتوسيع سير عمل المستندات الخاص بك.

**الخطوات التالية:** استكشف قدرات أخرى في GroupDocs.Viewer مثل تحويل PDF إلى PNG، إضافة العلامات المائية، أو التكامل مع مزودي التخزين السحابي.

## قسم الأسئلة المتكررة
- **Troubleshooting rotation issues** – تحقق من صحة أرقام الصفحات ومعلمات التدوير.  
- **Handling large PDF files** – عالج الصفحات على دفعات وراقب استهلاك الذاكرة.  
- **Licensing requirements** – استخدم ترخيصًا مؤقتًا للتطوير؛ واشترِ ترخيصًا كاملًا للإنتاج.  
- **Rotating multiple pages** – استدعِ `rotatePage` بشكل متكرر مع أرقام صفحات وزوايا مختلفة.  
- **Integration with Java libraries** – يعمل GroupDocs.Viewer بسلاسة مع Spring Boot، Jakarta EE، وغيرها من أطر Java.

## الأسئلة الشائعة

**س: هل يمكنني تدوير جميع صفحات PDF مرة واحدة؟**  
ج: نعم. كرّر حلقة عبر أرقام الصفحات واستدعِ `rotatePage(page, Rotation.ON_90_DEGREE)` لكل صفحة.

**س: هل يؤثر التدوير على ملف PDF الأصلي؟**  
ج: لا. يُطبق التدوير فقط أثناء عملية العرض؛ يبقى ملف PDF المصدر دون تغيير.

**س: ماذا لو كان PDF محميًا بكلمة مرور؟**  
ج: قدّم كلمة المرور عند إنشاء نسخة `Viewer`: `new Viewer(path, password)`.

**س: كيف يمكنني تصحيح خطأ “null pointer” عند إعداد HtmlViewOptions؟**  
ج: تأكد من وجود دليل الإخراج وأن `pageFilePathFormat` يُحلّ بشكل صحيح.

**س: هل هناك طريقة لتدوير الصفحات عند التحويل إلى صيغ أخرى (مثل PNG)؟**  
ج: نعم. استخدم نفس تكوين `rotatePage` مع خيارات العرض المناسبة للصيغة المستهدفة.

## الموارد
- **توثيق GroupDocs Viewer**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API لـ GroupDocs**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **صفحة تنزيل GroupDocs**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **خيارات شراء GroupDocs**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **تجربة مجانية لـ GroupDocs**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **طلب ترخيص مؤقت**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **منتدى دعم GroupDocs**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-10-05  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs

## دروس ذات صلة

- [دليل Java: عرض الصفحات المحددة باستخدام GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [عرض PDF في Java باستخدام GroupDocs Viewer - فواصل الصفحات](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [GroupDocs Viewer Java - عرض HTML متجاوب](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)