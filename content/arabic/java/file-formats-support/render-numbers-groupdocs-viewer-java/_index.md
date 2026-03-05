---
date: '2026-03-05'
description: تعلم كيفية تحويل الأرقام إلى PDF وغيرها من الصيغ مثل HTML وJPG وPNG باستخدام
  GroupDocs.Viewer للغة Java. يغطي هذا الدليل الإعداد وتقنيات العرض والتطبيقات العملية.
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: تحويل ملفات Numbers إلى PDF باستخدام GroupDocs.Viewer للـ Java
type: docs
url: /ar/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# تحويل ملفات Numbers إلى PDF (وبصيغ أخرى) باستخدام GroupDocs.Viewer للـ Java

عرض مستندات Apple Numbers على الويب أو في تطبيقات سطح المكتب يمكن أن يكون صعبًا، خاصةً عندما تحتاج إلى **convert numbers to pdf** أو تضمينها كصور. في هذا البرنامج التعليمي سنستعرض كيفية استخدام **GroupDocs.Viewer for Java** لتحويل ملفات Numbers إلى HTML، JPG، PNG، **وPDF**—مما يمنحك خيارات مرنة للمشاركة، والمعاينة، أو أرشفة جداول البيانات الخاصة بك.

![Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### ما ستتعلمه
- كيفية إعداد GroupDocs.Viewer في مشروع Java يعتمد على Maven  
- كود خطوة بخطوة لـ **convert numbers to pdf**, **convert numbers to html**, و **convert numbers to jpg**  
- سيناريوهات واقعية حيث تضيف تحويل المستندات قيمة إلى بوابات الويب، وتدفقات العمل عبر البريد الإلكتروني، وتكاملات DMS  

## إجابات سريعة
- **هل يمكنني تحويل Numbers إلى PDF باستخدام Java؟** نعم، باستخدام `PdfViewOptions` في GroupDocs.Viewer.  
- **ما هو أفضل تنسيق للمعاينة على الويب؟** HTML يوفر التجربة الأكثر تفاعلية.  
- **هل أحتاج إلى ترخيص للاستخدام في الإنتاج؟** يتطلب ترخيص تجاري للنشر غير التجريبي.  
- **هل يدعم تحويل الصور؟** بالطبع—استخدم `JpgViewOptions` أو `PngViewOptions` للحصول على صور عالية الجودة.  
- **ما نسخة Java المطلوبة؟** Java 8+ و Maven لإدارة التبعيات.  

## المتطلبات المسبقة
- Java Development Kit (JDK) 8 أو أعلى مثبت.  
- Maven لإدارة التبعيات.  
- إلمام أساسي بـ I/O للملفات في Java والمسارات.  

## إعداد GroupDocs.Viewer للـ Java

### التثبيت باستخدام Maven
أضف المستودع والاعتماد إلى ملف `pom.xml`. يجب أن يبقى هذا الجزء كما هو بالضبط:

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
- **Free Trial:** تقييم جميع الميزات بدون تكلفة.  
- **Temporary License:** طلب مفتاح مؤقت للمدة المحدودة للاختبار الموسع.  
- **Purchase:** الحصول على ترخيص كامل للمشاريع التجارية.  

## عرض مستند Numbers إلى HTML  
*حالة الاستخدام: تضمين جدول بيانات مباشرةً في صفحة ويب.*

### الخطوة 1: تهيئة Viewer وتكوين خيارات HTML
فيما يلي الكود الدقيق الذي ستنفذه. الشروح تشرح كل سطر، ولكن **لا تقم بتعديل كتلة الكود**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **لماذا هذا مهم:** `HtmlViewOptions.forEmbeddedResources()` يجمع CSS والصور داخل HTML، مما يجعله مثاليًا للمعاينات السريعة على الويب.

## عرض مستند Numbers إلى JPG  
*مفيد لمشاركة لقطة من جدول بيانات على وسائل التواصل الاجتماعي أو في البريد الإلكتروني.*

### الخطوة 1: إعداد Viewer وخيارات JPG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **نصيحة:** اضبط جودة الصورة عبر `options.setQuality(int)` إذا كنت بحاجة إلى ملفات أصغر.

## عرض مستند Numbers إلى PNG  
*مثالي عندما تحتاج إلى صورة غير مضغوطة وعالية الدقة للتقارير.*

### الخطوة 1: تهيئة وتكوين خيارات PNG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **نصيحة احترافية:** استخدم `options.setResolution(int)` للتحكم في DPI للصور الجاهزة للطباعة.

## عرض مستند Numbers إلى PDF  
*الهدف الأساسي للعديد من المطورين: **convert numbers to pdf** للأرشفة أو التوزيع.*

### الخطوة 1: إعداد Viewer لتحويل PDF
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **التكوين الرئيسي:** `PdfViewOptions` يتيح لك تضمين الخطوط والتحكم في حجم الصفحة، مما يضمن أن يكون الناتج مطابقًا لمتطلبات العلامة التجارية الخاصة بك.

## تطبيقات عملية
- **Web Integration:** تحويل إلى HTML لعرض جدول بيانات تفاعلي على موقعك.  
- **Content Sharing:** تحويل إلى JPG/PNG لتضمين صور سريعة في النشرات الإخبارية أو الدردشة.  
- **Enterprise DMS:** استخدم **convert numbers to pdf** لتخزين نسخة غير قابلة للتعديل وقابلة للبحث من جدول البيانات.  

## اعتبارات الأداء
- **Resource Management:** دائمًا أغلق `Viewer` داخل كتلة try‑with‑resources (كما هو موضح) لتحرير الموارد الأصلية بسرعة.  
- **Large Files:** بالنسبة لملفات Numbers الضخمة، فكر في معالجة كل صفحة على حدة وبث النتائج لتجنب استهلاك الذاكرة العالي.  
- **Thread Safety:** أنشئ نسخة منفصلة من `Viewer` لكل خيط؛ الفئة غير آمنة للاستخدام المتعدد الخيوط.  

## الخلاصة
أصبح لديك الآن مجموعة أدوات كاملة لـ **convert numbers to pdf**، بالإضافة إلى HTML، JPG، و PNG، باستخدام GroupDocs.Viewer للـ Java. تتيح لك هذه الإمكانيات بناء خطوط أنابيب مستندات مرنة—سواءً كنت تزود بوابة ويب، أو تولد تقارير، أو تؤرشف جداول البيانات.

### الخطوات التالية
استكشف خيارات التخصيص الإضافية في [وثائق GroupDocs](https://docs.groupdocs.com/viewer/java/) وجرب دمج هذه الميزات في تطبيقاتك الخاصة.

## قسم الأسئلة المتكررة

**Q1: ما هي صيغ الملفات التي يدعمها GroupDocs.Viewer؟**  
A1: يدعم مجموعة واسعة من صيغ المستندات بما في ذلك DOCX، XLSX، PDF، وأكثر.

**Q2: كيف يمكنني التعامل مع ملفات Numbers الكبيرة بكفاءة؟**  
A2: استخدم تقنيات إدارة الذاكرة في Java وحسّن الكود الخاص بك للتعامل بفعالية مع أحجام الملفات الكبيرة.

**Q3: هل يمكن استخدام GroupDocs.Viewer في مشروع تجاري؟**  
A4: نعم، ولكن ستحتاج إلى شراء ترخيص للاستخدام التجاري.

**Q4: هل يمكن تخصيص جودة الصور الناتجة؟**  
A5: بالتأكيد. يمكنك تعديل الإعدادات داخل `JpgViewOptions` و `PngViewOptions`.

**Q5: أين يمكنني العثور على أمثلة استخدام متقدمة؟**  
A5: زر [مرجع API](https://reference.groupdocs.com/viewer/java/) للحصول على وثائق مفصلة.

## الأسئلة المتكررة

**Q: كيف يمكنني تحويل ملف Numbers إلى PDF دون فقدان التنسيق؟**  
A: استخدم `PdfViewOptions` كما هو موضح أعلاه؛ يقوم العارض بالحفاظ على التخطيط، الخطوط، وأنماط الخلايا تلقائيًا.

**Q: هل يمكنني تحويل جدول بيانات إلى صورة في استدعاء واحد؟**  
A: نعم، `JpgViewOptions` أو `PngViewOptions` تقوم بالتحويل في خطوة واحدة، مما يتيح لك تحديد الدقة والجودة.

**Q: هل هناك طريقة لمعالجة عدة ملفات Numbers دفعة واحدة؟**  
A: ضع منطق الـ Viewer داخل حلقة، وأعد تهيئة `Viewer` لكل ملف، واكتب كل ناتج إلى مجلد منفصل.

**Q: هل أحتاج إلى ترخيص منفصل لكل صيغة إخراج؟**  
A: لا، ترخيص واحد من GroupDocs.Viewer يغطي جميع الصيغ المدعومة.

**Q: ما نسخة GroupDocs.Viewer المطلوبة لهذه الميزات؟**  
A: الأمثلة تستهدف الإصدار 25.2، الذي يتضمن دعمًا كاملاً لتحويل Numbers إلى PDF/HTML/Image.

## الموارد
- **الوثائق:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **مرجع API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **تحميل:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **شراء الترخيص:** [Buy a License](https://purchase.groupdocs.com/buy)
- **تجربة مجانية:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)
- **ترخيص مؤقت:** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **منتدى الدعم:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-03-05  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 للـ Java  
**المؤلف:** GroupDocs