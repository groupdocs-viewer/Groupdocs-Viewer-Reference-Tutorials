---
date: '2026-09-30'
description: تعلم كيفية تدوير الصفحة 90 درجة في Java باستخدام GroupDocs Viewer، بما
  في ذلك الإعداد، الكود، ونصائح الأداء.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: تدوير الصفحة 90 درجة في Java باستخدام GroupDocs Viewer. دليل خطوة
  بخطوة، نصائح الأداء، وحالات استخدام واقعية للمطورين.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: تدوير الصفحة 90 درجة باستخدام GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: تدوير الصفحة 90 درجة باستخدام GroupDocs Viewer for Java
type: docs
url: /ar/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تدوير الصفحة 90 درجة باستخدام GroupDocs Viewer for Java

إذا كنت بحاجة إلى **تدوير الصفحة 90 درجة** في مستند—سواء كان PDF أو ملف Word أو جدول بيانات—فإن القيام بذلك برمجياً في Java يوفر الوقت، يزيل الأخطاء اليدوية، ويسمح لك بدمج العملية في خطوط أنابيب آلية. في هذا الدليل المتقدم ستتعلم كيفية تدوير الصفحة الأولى من أي مستند مدعوم باستخدام **GroupDocs Viewer for Java**، ولماذا هذه القدرة مهمة في المشاريع الواقعية، وكيفية الحفاظ على العملية خفيفة الوزن وكفء في الذاكرة.

![تدوير الصفحة الأولى من مستند باستخدام GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## إجابات سريعة
- **ما معنى “rotate page 90 degrees”؟** إنه يدير الصفحة المحددة باتجاه عقارب الساعة ربع دورة.  
- **أي مكتبة تتعامل مع التدوير؟** GroupDocs Viewer for Java توفر طريقة `rotatePage`.  
- **هل يمكنني تدوير صفحات PDF باستخدام Java؟** نعم—استخدم نفس استدعاء `rotatePage`؛ يعمل مع PDF، DOCX، XLSX، وأكثر.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تعمل للتطوير؛ الترخيص المدفوع مطلوب للإنتاج.  
- **هل العملية تستنزف الذاكرة؟** ليس إذا قمت بإغلاق كائن `Viewer` بسرعة؛ راجع نصائح الأداء أدناه.

## ما هو “rotate page 90 degrees”؟
تدوير الصفحة 90 درجة يعيد توجيه الصفحة من وضعية عمودية إلى أفقية (أو العكس) دون تغيير المحتوى الأساسي. هذا مفيد للعروض التقديمية، طباعة الرسومات الأفقية فقط، أو تصحيح المستندات الممسوحة التي تم التقاطها بشكل جانبي. يتم تطبيق التدوير أثناء عملية العرض، مما يترك الملف الأصلي دون تغيير.

## لماذا يتم تدوير الصفحات برمجياً باستخدام GroupDocs Viewer for Java؟
يدعم GroupDocs Viewer **أكثر من 50 تنسيقًا للإدخال والإخراج**—بما في ذلك PDF، DOCX، PPTX، XLSX، والعديد من أنواع الصور—وبالتالي يمكنك عرض أي مستند دون الحاجة إلى محولات خارجية. API سهل الاستخدام، آمن للخطوط المتعددة، ويعمل على أي بيئة تشغيل Java 8+، مما يجعله خيارًا موثوقًا لأتمتة على مستوى المؤسسات التي يجب أن تتعامل مع العشرات من أنواع الملفات بشكل ثابت.

## المتطلبات المسبقة
- GroupDocs Viewer for Java (الإصدار الأحدث)
- JDK 8 أو أحدث
- Maven (أو Gradle) لإدارة التبعيات
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse
- إلمام أساسي بـ Java I/O

## إعداد GroupDocs.Viewer for Java
أضف مستودع GroupDocs والاعتماد إلى ملف `pom.xml` الخاص بك. هذا المقتطف يبقى كما هو من البرنامج التعليمي الأصلي:

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
- **نسخة تجريبية مجانية** – تحميل من موقع GroupDocs.  
- **ترخيص مؤقت** – طلب إذا كنت بحاجة إلى فترة تقييم ممتدة.  
- **ترخيص كامل** – شراء للاستخدام في بيئات الإنتاج.

### تهيئة Viewer الأساسية
فئة `Viewer` هي نقطة الدخول التي تقوم بتحميل المستند وتوفر طرق العرض والتحويل. احتفظ بالكود كما هو موضح:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## كيفية تدوير صفحة PDF في Java باستخدام GroupDocs Viewer
حمّل الملف المستهدف باستخدام `Viewer`، حدد رقم الصفحة، واستدعِ `rotatePage`. تعمل الطريقة مع PDF، DOCX، PPTX، XLSX وأي تنسيق آخر يدعمه المكتبة. بعد التدوير، يمكنك عرض المستند إلى ملف PDF جديد أو بثه مباشرة إلى العميل، مع ضمان عدم تعديل الملف الأصلي.

## تنفيذ خطوة بخطوة: تدوير الصفحة الأولى 90 درجة

### 1. استيراد الحزم المطلوبة
`PdfViewOptions` يخبر Viewer بإنتاج ملف PDF، بينما يحدد تعداد `Rotation` الزاوية. كلا الفئتين تنتميان إلى الحزمة `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. تحديد مواقع الإخراج وإنشاء Viewer
استبدل مسارات العنصر النائب بمجلداتك الفعلية. مُنشئ `Viewer` يقبل كائن `File` يشير إلى المستند المصدر.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. تكوين خيارات عرض PDF وتطبيق التدوير
طريقة `rotatePage(int, Rotation)` تأخذ فهرس صفحة **مبني على 1** وقيمة تعداد `Rotation`. في هذا المثال نستخدم `Rotation.ON_90_DEGREE` لتدوير الصفحة الأولى باتجاه عقارب الساعة.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. عرض المستند
استدعاء `view` مع الخيارات المكوّنة يكتب ملف PDF المدور إلى مجلد الإخراج.

```java
viewer.view(viewOptions);
```

#### كيف يعمل
- **PdfViewOptions** يوجه Viewer لإنشاء ملف PDF كإخراج.  
- **rotatePage(int, Rotation)** يدور الصفحة المحددة فقط، ويترك باقي الصفحات دون تغيير.  
- الطريقة تدعم ثلاث ثوابت تدوير: `ON_90_DEGREE`، `ON_180_DEGREE`، و`ON_270_DEGREE`.

## المشكلات الشائعة والحلول
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| **FileNotFoundException** | مسار غير صحيح أو مجلد مفقود | تحقق من وجود `YOUR_OUTPUT_DIRECTORY` و`YOUR_DOCUMENT_DIRECTORY` وأنهما قابلان للقراءة. |
| **Unsupported file format** | محاولة تدوير تنسيق غير مدعوم من قبل Viewer | تحقق من صفحة [GroupDocs Viewer supported formats] |
| **No rotation visible** | استخدام رقم صفحة خاطئ (مبني على 0) | تذكر أن `rotatePage` يستخدم فهرسة **مبنية على 1**. |
| **Out‑of‑memory errors on large docs** | عرض العديد من الملفات الكبيرة في خيط واحد | معالجة المستندات بشكل متسلسل أو استخدام مجموعة خيوط ذات تزامن محدود. |

## التطبيقات العملية

1. **تعديلات العرض التقديمي** – تحويل شريحة عمودية إلى أفقية مباشرة للحصول على تأثير بصري أفضل.  
2. **تصحيح المستندات بالجملة** – أتمتة إصلاح ملفات PDF الممسوحة التي تم التقاطها جانبياً، مما يوفر ساعات من العمل اليدوي.  
3. **إخراج جاهز للطباعة** – ضمان طباعة الرسومات الأفقية بشكل صحيح على ورق موجه عمودياً دون الحاجة إلى تدوير يدوي في برنامج تشغيل الطابعة.

## نصائح الأداء

- **إغلاق الموارد بسرعة** – كتلة `try‑with‑resources` تقوم تلقائيًا بتحرير كائن `Viewer`، مما يحرر الذاكرة.  
- **المعالجة الدفعية** – إعادة استخدام كائن `Viewer` واحد لكل خيط لتقليل عبء التهيئة.  
- **مراقبة الذاكرة** – بالنسبة للمستندات التي تتجاوز 100 ميغابايت، قم ببث الإخراج إلى القرص بدلاً من الاحتفاظ بالملف بالكامل في الذاكرة؛ يمكن لـ GroupDocs Viewer معالجة ملفات بحجم 200 ميغابايت باستخدام أقل من 250 ميغابايت من الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني تدوير صفحات متعددة في آن واحد؟**  
ج: نعم—استدعِ `rotatePage()` لكل رقم صفحة تحتاج إلى تدويره، إما داخل حلقة أو عبر سلسلة من الاستدعاءات.

**س: هل هناك طريقة للتراجع عن التدوير بعد العرض؟**  
ج: ليس مباشرة. سيتعين عليك عرض المستند مرة أخرى دون خيارات التدوير.

**س: أي تنسيقات الملفات تدعم تدوير الصفحات في GroupDocs Viewer؟**  
ج: DOCX، PDF، PPTX، XLSX، والعديد من التنسيقات الأخرى المذكورة في الوثائق الرسمية.

**س: كيف يمكنني تدوير الصفحات في مجموعة من المستندات تلقائيًا؟**  
ج: ضع منطق التدوير داخل حلقة تت iterates over مجموعة من مسارات الملفات، وتطبق نفس إعداد `rotatePage` على كل ملف.

**س: ما هي الممارسة المثلى للتعامل مع الأخطاء أثناء التدوير؟**  
ج: احط استخدام Viewer بكتلة `try‑catch`، سجّل تفاصيل الاستثناء، واختياريًا استمر في معالجة الملف التالي لتجنب توقف الدفعة بأكملها بسبب فشل واحد.

## الموارد

- **الوثائق**: [توثيق GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API**: [مرجع GroupDocs API](https://reference.groupdocs.com/viewer/java/)  
- **تحميل**: [احصل على GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **شراء**: [شراء ترخيص](https://purchase.groupdocs.com/buy)  
- **نسخة تجريبية مجانية**: [جرب مجانًا](https://releases.groupdocs.com/viewer/java/)  
- **ترخيص مؤقت**: [طلب ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/)  
- **الدعم**: [منتدى GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-09-30  
**تم الاختبار مع:** GroupDocs Viewer 25.2 for Java  
**المؤلف:** GroupDocs

## دروس ذات صلة

- [كيفية تدوير صفحات PDF محددة باستخدام GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [تحميل مستند من URL في Java – درس GroupDocs.Viewer](/viewer/java/document-loading/)
- [عرض مستندات Groupdocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}