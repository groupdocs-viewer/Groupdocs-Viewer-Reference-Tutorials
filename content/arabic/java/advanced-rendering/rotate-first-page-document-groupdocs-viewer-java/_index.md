---
date: '2026-03-29'
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

# تدوير الصفحة 90 درجة باستخدام GroupDocs Viewer for Java

عندما تحتاج إلى **تدوير الصفحة 90 درجة** في مستند—سواء كان PDF أو ملف Word أو جدول بيانات—فإن القيام بذلك برمجياً يوفر الوقت ويقضي على الأخطاء اليدوية. في هذا الدليل المتقدم سنستعرض الخطوات الدقيقة لتدوير الصفحة الأولى من أي مستند مدعوم باستخدام **GroupDocs Viewer for Java**. في النهاية، ستحصل على مقتطف قابل لإعادة الاستخدام يمكنك إدراجه في مشاريعك الخاصة.  
سنناقش أيضاً لماذا يعتبر تدوير الصفحات في Java مهمًا، والسيناريوهات الشائعة التي يبرز فيها هذا الأسلوب، وكيفية الحفاظ على العملية خفيفة الوزن.

![تدوير الصفحة الأولى من مستند باستخدام GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## إجابات سريعة
- **ماذا يعني “rotate page 90 degrees”؟** يقوم بتدوير الصفحة المحددة باتجاه عقارب الساعة ربع دورة.  
- **أي مكتبة تتعامل مع التدوير؟** توفر GroupDocs Viewer for Java طريقة `rotatePage`.  
- **هل يمكنني تدوير صفحات PDF باستخدام Java؟** نعم—استخدم نفس استدعاء `rotatePage`؛ يعمل مع PDF و DOCX و XLSX وغيرها.  
- **هل أحتاج إلى ترخيص؟** الإصدار التجريبي المجاني يكفي للتطوير؛ يتطلب الترخيص المدفوع للإنتاج.  
- **هل العملية مستهلكة للذاكرة؟** ليس كذلك عندما تقوم بإغلاق كائن `Viewer` فورًا؛ راجع نصائح الأداء أدناه.

## ما هو “rotate page 90 degrees”؟
تدوير الصفحة 90 درجة يعيد توجيه الصفحة من وضعية portrait إلى landscape (أو العكس) دون تعديل المحتوى الأساسي. هذا مفيد بشكل خاص للعروض التقديمية، وطباعة الرسومات التي تحتاج إلى وضعية landscape فقط، أو تصحيح المستندات الممسوحة التي تم التقاطها بشكل جانبي.

## لماذا يتم تدوير الصفحات برمجياً باستخدام GroupDocs Viewer for Java؟
يقوم GroupDocs Viewer بتجريد التعقيدات المتعلقة بمعالجة العشرات من صيغ الملفات. يتيح لك تطبيق التحولات على مستوى الصفحة—مثل التدوير—مع الحفاظ على الملف الأصلي دون تعديل. الواجهة البرمجية (API) سلسة، آمنة للخطوط المتعددة، وتعمل على أي بيئة تشغيل Java 8+، مما يجعلها خيارًا موثوقًا لأتمتة على مستوى المؤسسات.

## المتطلبات المسبقة

- **GroupDocs.Viewer for Java** (الإصدار الأخير)
- **JDK 8** أو أحدث
- **Maven** (أو Gradle) لإدارة التبعيات
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse
- إلمام أساسي بـ Java I/O

## إعداد GroupDocs.Viewer for Java

أضف مستودع GroupDocs والاعتماد إلى ملف `pom.xml`. هذا المقتطف لم يتغير عن الدرس الأصلي:

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
- **الإصدار التجريبي المجاني** – تحميل من موقع GroupDocs.  
- **رخصة مؤقتة** – اطلبها إذا كنت بحاجة إلى فترة تقييم ممتدة.  
- **رخصة كاملة** – شراء للاستخدام في بيئات الإنتاج.

### تهيئة Viewer الأساسية
الكود التالي يوضح الطريقة الأدنى لإنشاء كائن `Viewer`. احتفظ به كما هو موضح:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## كيفية تدوير صفحة PDF في Java باستخدام GroupDocs Viewer
على الرغم من أن الواجهة البرمجية (API) تعمل عبر العديد من الصيغ، فإن PDF هو الأكثر شيوعًا لاستخدام تدوير الصفحات. يتم استخدام نفس طريقة `rotatePage`، لذا كل ما عليك هو توجيه الـ Viewer إلى ملف PDF وتحديد رقم الصفحة.

## تنفيذ خطوة بخطوة: تدوير الصفحة الأولى 90 درجة

### 1. استيراد الحزم المطلوبة
تتيح لك هذه الاستيرادات الوصول إلى خيارات عرض PDF وتعداد Rotation.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. تحديد مواقع الإخراج وإنشاء Viewer
استبدل مسارات العناصر النائبة بمسارات الدلائل الفعلية الخاصة بك.

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
طريقة `rotatePage` تأخذ رقم الصفحة (مبني على 1) وقيمة تعداد `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. عرض المستند
أخيرًا، استدعِ `view` لتوليد ملف PDF المدور.

```java
viewer.view(viewOptions);
```

#### كيف يعمل
- **PdfViewOptions** يحدد للـ Viewer إخراج ملف PDF.  
- **rotatePage(int, Rotation)** يدور فقط الصفحة التي تحددها، مع ترك باقي الصفحات دون تعديل.  
- الطريقة تدعم `ON_90_DEGREE` و `ON_180_DEGREE` و `ON_270_DEGREE`.

## المشكلات الشائعة والحلول

| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| **FileNotFoundException** | مسار غير صحيح أو مجلد مفقود | تحقق من وجود `YOUR_OUTPUT_DIRECTORY` و `YOUR_DOCUMENT_DIRECTORY` وأنهما قابلان للقراءة. |
| **Unsupported file format** | محاولة تدوير صيغة غير مدعومة من قبل Viewer | تحقق من صفحة [GroupDocs Viewer supported formats] |
| **No rotation visible** | استخدام رقم صفحة غير صحيح (مبني على 0) | تذكر أن `rotatePage` يستخدم فهرسة **مبنية على 1**. |
| **Out‑of‑memory errors on large docs** | عرض العديد من الملفات الكبيرة في خيط واحد | معالجة المستندات بشكل متسلسل أو استخدام مجموعة خيوط ذات تزامن محدود. |

## التطبيقات العملية

1. **تعديلات العرض التقديمي** – تحويل شريحة portrait إلى landscape مباشرة.  
2. **تصحيح المستندات بالجملة** – أتمتة إصلاح ملفات PDF الممسوحة التي تم التقاطها بشكل جانبي.  
3. **إخراج جاهز للطباعة** – التأكد من طباعة الرسومات landscape بشكل صحيح على ورق موجه portrait.

## نصائح الأداء

- **إغلاق الموارد فورًا** – كتلة `try‑with‑resources` تقوم تلقائيًا بتحرير كائن `Viewer`.  
- **معالجة دفعات** – عند التعامل مع العديد من الملفات، أعد استخدام كائن `Viewer` واحد لكل خيط لتقليل الحمل.  
- **مراقبة الذاكرة** – بالنسبة للمستندات التي تزيد عن 100 MB، فكر في بث الإخراج إلى القرص بدلاً من الاحتفاظ به في الذاكرة.

## الأسئلة المتكررة

**س: هل يمكنني تدوير صفحات متعددة في آن واحد؟**  
ج: نعم—استدعِ `rotatePage()` لكل رقم صفحة تحتاج إلى تدويره.

**س: هل هناك طريقة للتراجع عن التدوير بعد العرض؟**  
ج: ليس مباشرة. ستحتاج إلى عرض المستند مرة أخرى دون خيارات التدوير.

**س: أي صيغ ملفات تدعم تدوير الصفحات في GroupDocs Viewer؟**  
ج: DOCX، PDF، PPTX، XLSX، والعديد من الصيغ الأخرى المذكورة في الوثائق الرسمية.

**س: كيف يمكنني تدوير الصفحات في مجموعة من المستندات تلقائيًا؟**  
ج: ضع الكود داخل حلقة تت iterates over مجموعة من مسارات الملفات، وتطبق نفس منطق `rotatePage` على كل منها.

**س: ما هي أفضل الممارسات للتعامل مع الأخطاء أثناء التدوير؟**  
ج: احط استخدام Viewer بكتلة `try‑catch`، سجّل الاستثناء، واختياريًا استمر في معالجة الملف التالي.

## الموارد

- **الوثائق**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **تحميل**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **شراء**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **إصدار تجريبي مجاني**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **رخصة مؤقتة**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **الدعم**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-03-29  
**تم الاختبار مع:** GroupDocs Viewer 25.2 for Java  
**المؤلف:** GroupDocs