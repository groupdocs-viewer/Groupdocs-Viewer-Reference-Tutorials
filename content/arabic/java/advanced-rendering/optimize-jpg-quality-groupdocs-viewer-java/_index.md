---
date: '2026-03-05'
description: تعلم كيفية ضغط ملفات PDF في جافا عن طريق ضبط جودة JPG باستخدام GroupDocs.Viewer
  – طريقة بسيطة لضغط PDF في جافا، توازن بين حجم الملف وجودة الصورة.
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: كيفية ضغط ملفات PDF في Java – تحسين جودة JPG
type: docs
url: /ar/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# كيفية ضغط pdf في Java – تحسين جودة JPG

إن موازنة حجم الملف وجودة العرض البصرية تُعد تحديًا شائعًا عند العمل مع ملفات PDF. في هذا البرنامج التعليمي ستكتشف **كيفية ضغط pdf** عن طريق ضبط جودة صور JPG داخل مستندات PDF باستخدام GroupDocs.Viewer for Java. سنستعرض الإعداد، تنفيذ الشيفرة، والنصائح العملية حتى تتمكن من ضغط صور PDF بثقة دون التضحية بقراءة المحتوى.

![تحسين جودة JPG في ملفات PDF باستخدام GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## إجابات سريعة
- **ماذا يعني “reduce PDF size Java”?** ضبط جودة الصورة، الضغط، وإدارة الموارد لإنشاء ملفات PDF أصغر في تطبيقات Java.  
- **ما الإعداد الذي يتحكم في جودة JPG؟** `PdfViewOptions.setJpgQuality(byte quality)` حيث تتراوح القيمة من 0 (الأدنى) إلى 100 (الأعلى).  
- **هل يمكنني أيضًا تحويل PPTX إلى PDF في نفس العملية؟** نعم—فقط وجه `Viewer` إلى مصدر `.pptx` وستطبق نفس الخيارات.  
- **ما هو مستوى الجودة المعتاد للنشر على الويب؟** قيمة تقريبًا **50‑70** توفر توازنًا جيدًا لمعظم سيناريوهات الويب.  
- **هل أحتاج إلى ترخيص لهذه الميزة؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص الدائم مطلوب للاستخدام في الإنتاج.

## كيفية ضغط pdf في Java – نظرة عامة
تقليل حجم PDF في Java يتضمن تحسين الموارد داخل ملف PDF—وخاصة الصور—حتى يشغل الملف النهائي مساحة أقل ويُحمَّل بسرعة أكبر. من خلال خفض جودة JPG، تقوم فعليًا **بضغط صور PDF**، والتي غالبًا ما تشكل الجزء الأكبر من حجم المستند.

## ما هو “reduce PDF size Java”؟
تقليل حجم PDF في Java يتضمن تحسين الموارد داخل ملف PDF—وخاصة الصور—حتى يشغل الملف النهائي مساحة أقل ويُحمَّل بسرعة أكبر. من خلال خفض جودة JPG، تقوم فعليًا **بضغط صور PDF**، والتي غالبًا ما تشكل الجزء الأكبر من حجم المستند.

## لماذا ضبط جودة JPG باستخدام GroupDocs Viewer؟
- **تقليل كبير في الحجم**: خفض جودة الصورة يمكن أن يقلص ملفات PDF بنسبة 30‑70 % حسب الدقة الأصلية.  
- **تحويل بمرحلة واحدة**: لا حاجة لخطوة معالجة صورة منفصلة؛ يقوم GroupDocs بمعالجتها أثناء إنشاء PDF.  
- **المرونة**: يمكنك ضبط قيمة الجودة من نوع `byte` وفقًا لمتطلبات المشروع (مثل الطباعة عالية الجودة مقابل معاينة ويب خفيفة).  

## المتطلبات المسبقة
- **GroupDocs.Viewer for Java** الإصدار 25.2 أو أحدث.  
- مشروع Java يعتمد على Maven مع JDK 8 أو أحدث.  
- إلمام أساسي بـ Java ومعالجة PDF.  

## إعداد GroupDocs.Viewer for Java
أضف مستودع GroupDocs والاعتماد إلى ملف `pom.xml` الخاص بك:

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

> **نصيحة احترافية:** حافظ على تحديث الإصدار للاستفادة من تحسينات الأداء والخيارات الجديدة للضغط.

## دليل التنفيذ

### الخطوة 1: تحديد مسار دليل الإخراج
أنشئ فئة مساعدة تقوم بإنشاء مجلد الإخراج حيث سيتم حفظ ملف PDF.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class FeatureResolveOutputDirectoryPath {
    public static Path getOutputDirectoryPath(String subdirectory) {
        String directory = Paths.get("YOUR_OUTPUT_DIRECTORY", "AdjustQualityOfJpgImages", subdirectory).toString();
        
        try {
            return Paths.get(directory);
        } catch (IOException e) {
            throw new RuntimeException("Failed to create output directory.", e);
        }
    }
}
```

### الخطوة 2: تكوين `PdfViewOptions` بجودة JPG المطلوبة
حدد مستوى جودة JPG (0‑100) قبل عرض المستند.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class FeatureAdjustQualityOfJpgImages {
    public static void run() {
        Path outputDirectory = FeatureResolveOutputDirectoryPath.getOutputDirectoryPath("YOUR_DOCUMENT_DIRECTORY");
        Path filePath = outputDirectory.resolve("output.pdf");

        PdfViewOptions viewOptions = new PdfViewOptions(filePath);
        
        // Set desired JPG quality (0-100 scale)
        byte quality = 10;
        viewOptions.setJpgQuality(quality);

        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/source.pptx")) {
            viewer.view(viewOptions);
        }
    }
}
```

**شرح:**  
- `setJpgQuality(byte quality)` يخبر GroupDocs بكمية الضغط التي يجب تطبيقها على صور JPG. القيم الأقل تنتج ملفات أصغر ولكن قد تقلل من وضوح الصورة.  
- يستخدم المثال `source.pptx` لتوضيح **convert pptx to pdf** مع ضغط الصور في الوقت نفسه.  

### الخطوة 3: تشغيل الشيفرة والتحقق من النتيجة
نفّذ `FeatureAdjustQualityOfJpgImages.run()`. سيحتوي `output.pdf` المُنتج على صور JPG بالمستوى الجودة الذي حددته، مما يؤدي فعليًا إلى **ضغط صور PDF** وتقليل الحجم الكلي للملف.

## المشكلات الشائعة & استكشاف الأخطاء
- **مسار ملف غير صحيح:** تأكد من وجود مستند المصدر (`source.pptx`) بالنسبة إلى دليل العمل.  
- **أذونات غير كافية:** يجب أن يكون مجلد الإخراج قابلًا للكتابة؛ وإلا سيتم رمي `RuntimeException`.  
- **ملفات PDF كبيرة غير متوقعة:** تحقق من أن قيمة `quality` منخفضة بما يكفي لتحقيق أهداف الحجم المطلوبة.  

## تطبيقات عملية
1. **أرشفة المستندات:** ملفات PDF الأصغر توفر تكاليف التخزين وتحسن سرعات الاسترجاع.  
2. **النشر على الويب:** تحميل صفحات أسرع عندما تكون ملفات PDF مدمجة أو مرتبطة على المواقع.  
3. **مرفقات البريد الإلكتروني:** تلبية حدود الحجم عن طريق خفض جودة الصورة قبل الإرسال.  

## اعتبارات الأداء
- **معالجة دفعات:** بالنسبة لعدد كبير من المستندات، عالجها في خيوط متوازية مع مراقبة استهلاك الذاكرة.  
- **إعدادات الجودة المثالية:** استخدم جودة أعلى (80‑100) لملفات PDF الجاهزة للطباعة؛ ولمعاينات الويب، غالبًا ما تكفي 30‑50.  

## الخلاصة
أنت الآن تعرف **كيفية ضغط pdf** عن طريق ضبط جودة صورة JPG باستخدام GroupDocs.Viewer. جرّب مستويات جودة مختلفة، دمج الشيفرة في خطوط عملك الحالية، واستمتع بملفات PDF أسرع وأخف.

### الخطوات التالية
- اختبر إعدادات جودة مختلفة للعثور على النقطة المثالية لحالتك.  
- استكشف ميزات GroupDocs الإضافية مثل العلامة المائية أو حماية كلمة المرور.  

## قسم الأسئلة المتكررة
1. **كيف يؤثر ضبط جودة JPG على حجم الملف؟**  
   خفض الجودة يقلل من حجم الملف، مما يجعل مشاركة أو تخزين المستندات أسهل.  
2. **هل يمكنني ضبط جودة الصورة لتنسيقات غير JPG؟**  
   هذه الميزة تستهدف صور JPG داخل ملفات PDF فقط؛ ومع ذلك، يقدم GroupDocs.Viewer خيارات أخرى لتنسيقات مختلفة.  
3. **ما هو إعداد جودة JPG المثالي للاستخدام على الويب؟**  
   توازن حول 50‑70 غالبًا ما يوفر وضوحًا جيدًا مع حجم ملف منخفض مناسب لتطبيقات الويب.  
4. **هل يمكن أتمتة هذه العملية في سير عمل دفعي؟**  
   نعم، يمكنك دمج هذه الميزة في أنظمة مؤتمتة لمعالجة مستندات متعددة بكفاءة.  
5. **ماذا أفعل إذا لم يتم إنشاء ملف PDF الناتج كما هو متوقع؟**  
   تحقق من مسار مستند الإدخال وتأكد من تكوين جميع الاعتمادات بشكل صحيح.  

## الأسئلة المتكررة
**س:** *هل يمكنني استخدام هذه الطريقة لتحويل تنسيقات أخرى مثل DOCX إلى PDF مع تقليل الحجم؟*  
**ج:** بالتأكيد. إعداد `PdfViewOptions.setJpgQuality` يعمل مع أي تنسيق مصدر ينتج صور JPG في ملف PDF.  

**س:** *هل يؤثر تقليل جودة JPG على عرض النص؟*  
**ج:** لا. النص مبني على المتجهات ويظل واضحًا؛ فقط الصور النقطية تتأثر.  

**س:** *هل هناك طريقة لتعيين مستويات جودة مختلفة لصفحات مختلفة؟*  
**ج:** حاليًا يطبق GroupDocs إعداد جودة موحد لكل عملية تحويل. للتحكم في جودة كل صفحة، ستحتاج إلى معالجة PDF لاحقًا باستخدام مكتبة معالجة صور مخصصة.  

**س:** *هل أحتاج إلى ترخيص للنشر في بيئات الإنتاج؟*  
**ج:** نعم، يلزم وجود ترخيص صالح لـ GroupDocs.Viewer للاستخدام في الإنتاج. تتوفر نسخة تجريبية مجانية للتقييم.  

**س:** *كيف يمكنني التحقق من انخفاض الجودة الفعلي؟*  
**ج:** قارن أحجام الملفات قبل وبعد التحويل، وافتح ملف PDF لتفقد وضوح الصورة بصريًا.  

**الموارد**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)  

---

**آخر تحديث:** 2026-03-05  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs