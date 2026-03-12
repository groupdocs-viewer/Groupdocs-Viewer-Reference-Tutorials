---
date: '2026-01-18'
description: تعلم كيفية تدوير صفحات PDF باستخدام GroupDocs.Viewer للغة Java. يغطي
  هذا الدليل خطوة بخطوة إعداد Maven، وتدوير الصفحات (بما في ذلك تدوير PDF 90 درجة)،
  وحل المشكلات.
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: كيفية تدوير صفحات PDF باستخدام GroupDocs.Viewer في Java – دليل شامل
type: docs
url: /ar/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# كيفية تدوير صفحات PDF باستخدام GroupDocs.Viewer في Java

يمكن أن يكون تدوير صفحات محددة داخل ملف PDF أمرًا أساسيًا لتنسيق المستندات أو تعديل شرائح العرض. **في هذا الدليل ستتعلم كيفية تدوير pdf** صفحات برمجيًا باستخدام GroupDocs.Viewer، سواء كنت بحاجة إلى تدوير pdf 90 درجة، أو عكس قسم كامل، أو معالجة صفحات متعددة في استدعاء واحد.

![تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer للـ Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**ما ستتعلمه:**
- إعداد GroupDocs.Viewer في مشروع Java الخاص بك (بما في ذلك تكوين Maven GroupDocs Viewer)
- تدوير صفحات PDF محددة برمجيًا (rotate pdf 90 degrees، 180 degrees، إلخ)
- التكوينات الأساسية للاستخدام الأمثل
- استكشاف الأخطاء الشائعة أثناء التنفيذ

## إجابات سريعة
- **ما المكتبة التي يمكنها تدوير صفحات PDF في Java؟** GroupDocs.Viewer for Java.
- **هل يمكنني تدوير صفحة واحدة بمقدار 90 درجة؟** نعم، استخدم `rotatePage(pageNumber, Rotation.ON_90_DEGREE)`.
- **هل أحتاج إلى ترخيص للتطوير؟** ترخيص مؤقت متاح لتجربة مجانية.
- **هل Maven مطلوب؟** Maven هو الطريقة الموصى بها لإدارة تبعيات GroupDocs.
- **كيف أقوم بعرض الصفحات المدورة؟** استخدم `HtmlViewOptions` واستدعِ `viewer.view(...)`.

## المتطلبات المسبقة

### المكتبات والتبعيات المطلوبة

للبدء، تأكد من وجود:
- مجموعة أدوات تطوير Java (JDK) الإصدار 8 أو أحدث مثبتة على جهازك.
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.
- Maven لإدارة تبعيات المشروع.

### متطلبات إعداد البيئة

1. **تكوين Maven**: أضف GroupDocs.Viewer إلى مشروع Maven الخاص بك عن طريق تضمين المستودعات والتبعيات اللازمة في ملف `pom.xml`.
2. **الحصول على الترخيص**: احصل على ترخيص مؤقت من GroupDocs، مما يتيح لك استكشاف جميع الميزات دون قيود أثناء التطوير. زر [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) أو قدّم طلبًا للحصول على ترخيص مؤقت عبر [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## إعداد GroupDocs.Viewer للـ Java

لدمج GroupDocs.Viewer في مشروع Java باستخدام Maven، حدّث ملف `pom.xml` الخاص بك:

**تكوين Maven**  
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

قم بتهيئة GroupDocs.Viewer بتحديد دليل المستندات ومسارات الإخراج:

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## دليل التنفيذ

### تدوير صفحات محددة باستخدام GroupDocs.Viewer

**نظرة عامة:** تدوير صفحات PDF محددة لتحسين عرض المستند.

#### الخطوة 1: تكوين تدوير الصفحات

قم بتدوير الصفحة الأولى بمقدار 90 درجة والثانية بمقدار 180 درجة باستخدام `HtmlViewOptions`:

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### الخطوة 2: تهيئة Viewer وعرض الصفحات

أنشئ كائن `Viewer` مع المستند الخاص بك وقم بعرض الصفحات المحددة:

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### المعلمات والتكوين

- **Rotation**: استخدم `rotatePage` مع أرقام الصفحات وزوايا التدوير. الزوايا المتاحة: `ON_90_DEGREE`، `ON_180_DEGREE`، `ON_270_DEGREE`.
- **HtmlViewOptions**: يضبط تحويل صفحات PDF إلى HTML، مع ضمان تضمين الموارد المدمجة.
- **pdf to html java**: تتولى فئة `HtmlViewOptions` تحويل PDF‑to‑HTML مع الحفاظ على التخطيط.

#### نصائح استكشاف الأخطاء (troubleshoot pdf rotation)

- تحقق من المسارات إلى المستند ودلائل الإخراج.
- افحص وجود تبعيات مفقودة أو إصدارات مكتبة غير صحيحة.
- تأكد من تطبيق الترخيص بشكل صحيح إذا ظهرت قيود ميزات أثناء التجربة.
- إذا لاحظت ارتفاعًا مفاجئًا في استهلاك الذاكرة، ففكّر في عرض الصفحات على دفعات أصغر (rotate multiple pdf pages gradually).

## التطبيقات العملية

### حالات الاستخدام الواقعية
1. **محاذاة المستندات** – تدوير المستندات الممسوحة ضوئيًا للحصول على الاتجاه الرقمي الصحيح.
2. **تعديلات العروض** – تعديل شرائح العروض داخل ملفات PDF قبل المشاركة.
3. **سير عمل الأرشفة** – ضبط اتجاه المستندات التاريخية تلقائيًا أثناء الرقمنة.

### إمكانات التكامل
دمج GroupDocs.Viewer مع أنظمة إدارة المستندات القائمة على Java، أو منصات المحتوى، أو حلول المؤسسات المخصصة التي تتطلب قدرات عرض ديناميكية.

## اعتبارات الأداء

- **إدارة الموارد**: أغلق كائن `Viewer` لتحرير الموارد.
- **إدارة ذاكرة Java**: راقب استهلاك الذاكرة عند عرض مستندات كبيرة واستخدم هياكل بيانات فعّالة.
- **أفضل الممارسات**: استفد من التخزين المؤقت للمستندات أو الصفحات التي يتم الوصول إليها بشكل متكرر.

## الخلاصة

غطى هذا الدليل **كيفية تدوير pdf** صفحات باستخدام GroupDocs.Viewer في Java، بدءًا من إعداد البيئة وحتى التطبيقات العملية. جرّب وظائف إضافية مثل إضافة العلامات المائية أو تحويل المستندات إلى صيغ مختلفة.

**الخطوات التالية:** استكشف المزيد من ميزات GroupDocs.Viewer لتعزيز قدرات معالجة المستندات لديك.

## قسم الأسئلة المتكررة

### أسئلة شائعة
1. **استكشاف مشاكل التدوير**: تأكد من صحة أرقام الصفحات ومعلمات التدوير.
2. **معالجة ملفات PDF الكبيرة**: عالج المستندات الكبيرة بفعالية مع إدارة الموارد المناسبة.
3. **متطلبات الترخيص**: استخدم ترخيصًا مؤقتًا للتطوير؛ اشترِ ترخيصًا كاملاً للإنتاج.
4. **تدوير صفحات متعددة**: استدعِ `rotatePage` عدة مرات بأرقام وزوايا مختلفة.
5. **التكامل مع مكتبات Java**: دمج GroupDocs.Viewer بسلاسة داخل تطبيقات أو أطر عمل أكبر.

## الأسئلة المتكررة

**س: هل يمكنني تدوير جميع صفحات PDF مرة واحدة؟**  
ج: نعم. قم بعمل حلقة عبر أرقام الصفحات واستدعِ `rotatePage(page, Rotation.ON_90_DEGREE)` لكل صفحة.

**س: هل يؤثر التدوير على ملف PDF الأصلي؟**  
ج: لا. يتم تطبيق التدوير فقط أثناء عملية العرض؛ يبقى ملف PDF المصدر دون تغيير.

**س: ماذا لو كان PDF محميًا بكلمة مرور؟**  
ج: قدم كلمة المرور عند إنشاء كائن `Viewer`: `new Viewer(path, password)`.

**س: كيف يمكنني تصحيح خطأ “null pointer” عند إعداد HtmlViewOptions؟**  
ج: تأكد من وجود دليل الإخراج وأن `pageFilePathFormat` يتم حله بشكل صحيح.

**س: هل هناك طريقة لتدوير الصفحات عند التحويل إلى صيغ أخرى (مثل PNG)؟**  
ج: استخدم نفس تكوين `rotatePage` مع خيارات العرض المناسبة للصيغة المستهدفة.

## الموارد
- **التوثيق**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)
- **مرجع API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **التنزيل**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **الشراء**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)
- **التجربة المجانية**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **الترخيص المؤقت**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **الدعم**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-01-18  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs