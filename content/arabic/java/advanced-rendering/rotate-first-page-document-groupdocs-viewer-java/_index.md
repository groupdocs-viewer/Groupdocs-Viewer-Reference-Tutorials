---
date: '2026-01-18'
description: تعلم كيفية تدوير الصفحة 90 درجة في جافا باستخدام GroupDocs Viewer، بما
  في ذلك الإعداد، الكود، ونصائح الأداء.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: تدوير الصفحة 90 درجة باستخدام GroupDocs Viewer لجافا
type: docs
url: /ar/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# تدوير الصفحة 90 درجة باستخدام GroupDocs Viewer للـ Java

عندما تحتاج إلى **rotate page 90 degrees** في مستند—سواء كان PDF أو ملف Word أو جدول بيانات—فإن القيام بذلك برمجياً يوفر الوقت ويقضي على الأخطاء اليدوية. في هذا الدليل المتقدم سنستعرض الخطوات الدقيقة لتدوير الصفحة الأولى من أي مستند مدعوم باستخدام **GroupDocs Viewer for Java**. في النهاية ستحصل على مقطع شفرة قابل لإعادة الاستخدام يمكنك إدراجه في مشاريعك.

![تدوير الصفحة الأولى من مستند باستخدام GroupDocs.Viewer للـ Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## إجابات سريعة
- **ماذا يعني “rotate page 90 degrees”?** إنه يدير الصفحة المحددة باتجاه عقارب الساعة ربع دورة.  
- **أي مكتبة تتعامل مع التدوير؟** يوفر GroupDocs Viewer for Java طريقة `rotatePage`.  
- **هل يمكنني تدوير صفحات PDF باستخدام Java؟** نعم—استخدم نفس استدعاء `rotatePage`؛ يعمل مع PDF و DOCX و XLSX وغيرها.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتطوير؛ يتطلب الترخيص المدفوع للإنتاج.  
- **هل العملية مستهلكة للذاكرة؟** لا عندما تغلق كائن `Viewer` بسرعة؛ راجع نصائح الأداء أدناه.

## ما هو “rotate page 90 degrees”؟
تدوير الصفحة 90 درجة يعيد توجيه الصفحة من وضعية عمودية إلى أفقية (أو العكس) دون تعديل المحتوى الأساسي. هذا مفيد بشكل خاص للعروض التقديمية، وطباعة الرسومات الأفقية فقط، أو تصحيح المستندات الممسوحة التي تم التقاطها بشكل جانبي.

## لماذا نقوم بتدوير الصفحات باستخدام GroupDocs Viewer للـ Java؟
يقوم GroupDocs Viewer بتجريد التعقيدات المتعلقة بمعالجة العشرات من صيغ الملفات. يتيح لك تطبيق التحولات على مستوى الصفحة—مثل التدوير—مع الحفاظ على الملف الأصلي دون تعديل. الواجهة البرمجية (API) سلسة، آمنة للخطوط المتعددة، وتعمل على أي بيئة تشغيل Java 8+.

## المتطلبات المسبقة

- **GroupDocs.Viewer for Java** (الإصدار الأحدث)
- **JDK 8** أو أحدث
- **Maven** (أو Gradle) لإدارة الاعتمادات
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse
- إلمام أساسي بمدخلات/مخرجات Java

## إعداد GroupDocs.Viewer للـ Java

أضف مستودع GroupDocs والاعتماد إلى ملف `pom.xml` الخاص بك. هذا المقتطف يبقى كما هو من الدرس الأصلي:

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
- **ترخيص مؤقت** – اطلبه إذا كنت بحاجة إلى فترة تقييم ممتدة.  
- **ترخيص كامل** – اشترِه للنشر في بيئة الإنتاج.

### تهيئة Viewer الأساسية
الكود التالي يوضح الطريقة الأدنى لإنشاء كائن `Viewer`. احتفظ به تماماً كما هو موضح:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## تنفيذ خطوة بخطوة: تدوير الصفحة الأولى 90 درجة

### 1. استيراد الحزم المطلوبة
هذه الاستيرادات تمنحك الوصول إلى خيارات عرض PDF وتعداد (enum) التدوير.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. تحديد مواقع الإخراج وإنشاء Viewer
استبدل مسارات العنصر النائب (placeholder) بأدلةك الفعلية.

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
طريقة `rotatePage` تأخذ رقم الصفحة (مبني على 1) وقيمة من تعداد `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. عرض المستند
أخيراً، استدعِ `view` لإنشاء ملف PDF المدور.

```java
viewer.view(viewOptions);
```

#### كيف يعمل
- **PdfViewOptions** يخبر Viewer بإنتاج ملف PDF.  
- **rotatePage(int, Rotation)** يدور فقط الصفحة التي تحددها، مع ترك البقية دون تعديل.  
- الطريقة تدعم `ON_90_DEGREE`، `ON_180_DEGREE`، و `ON_270_DEGREE`.

## المشكلات الشائعة والحلول

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| **FileNotFoundException** | مسار غير صحيح أو مجلد مفقود | تحقق من وجود `YOUR_OUTPUT_DIRECTORY` و `YOUR_DOCUMENT_DIRECTORY` وأنهما قابلان للقراءة. |
| **Unsupported file format** | محاولة تدوير صيغة غير مدعومة من قبل Viewer | تحقق من صفحة [GroupDocs Viewer supported formats]. |
| **No rotation visible** | استخدام رقم صفحة خاطئ (مبني على 0) | تذكر أن `rotatePage` يستخدم الفهرسة **مبنية على 1**. |
| **Out‑of‑memory errors on large docs** | عرض العديد من الملفات الكبيرة في خيط واحد | عالج المستندات تسلسلياً أو استخدم مجموعة خيوط (thread pool) ذات تزامن محدود. |

## تطبيقات عملية

1. **تعديلات العروض التقديمية** – تحويل شريحة عمودية إلى أفقية مباشرة.  
2. **تصحيح المستندات بالجملة** – أتمتة إصلاح ملفات PDF الممسوحة التي تم التقاطها بشكل جانبي.  
3. **إخراج جاهز للطباعة** – ضمان طباعة الرسومات الأفقية بشكل صحيح على ورق موجه عمودياً.

## نصائح الأداء

- **إغلاق الموارد بسرعة** – كتلة `try‑with‑resources` تقوم تلقائياً بتحرير كائن `Viewer`.  
- **معالجة دفعات** – عند التعامل مع ملفات متعددة، أعد استخدام كائن `Viewer` واحد لكل خيط لتقليل الحمل.  
- **مراقبة الذاكرة** – للمستندات التي تزيد عن 100 ميغابايت، فكر في تدفق الإخراج إلى القرص بدلاً من الاحتفاظ به في الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني تدوير صفحات متعددة في آن واحد؟**  
ج: نعم—استدعِ `rotatePage()` لكل رقم صفحة تحتاج إلى تدويره.

**س: هل هناك طريقة للتراجع عن التدوير بعد العرض؟**  
ج: ليس مباشرة. سيتعين عليك عرض المستند مرة أخرى دون خيارات التدوير.

**س: أي صيغ الملفات تدعم تدوير الصفحات في GroupDocs Viewer؟**  
ج: DOCX، PDF، PPTX، XLSX، والعديد من الصيغ الأخرى المذكورة في الوثائق الرسمية.

**س: كيف يمكنني تدوير الصفحات في مجموعة من المستندات تلقائياً؟**  
ج: ضع الكود داخل حلقة تتنقل عبر مجموعة من مسارات الملفات، وتطبق منطق `rotatePage` نفسه على كل منها.

**س: ما هي أفضل الممارسات للتعامل مع الأخطاء أثناء التدوير؟**  
ج: احط استخدام Viewer بكتلة `try‑catch`، سجّل الاستثناء، ويمكنك اختياراً متابعة معالجة الملف التالي.

## الموارد

- **الوثائق**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **تحميل**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **شراء**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **نسخة تجريبية مجانية**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **ترخيص مؤقت**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **الدعم**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-01-18  
**تم الاختبار مع:** GroupDocs Viewer 25.2 للـ Java  
**المؤلف:** GroupDocs  

---