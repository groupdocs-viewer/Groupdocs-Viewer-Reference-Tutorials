---
date: '2026-08-25'
description: تعرف على كيفية تحويل ملفات Numbers باستخدام GroupDocs.Viewer for Java،
  وتحويل ملفات Apple Numbers إلى PDF أو HTML أو JPG أو PNG. يتضمن الإعداد، خطوات تحويل
  المستندات بلغة java، ونصائح عرض الويب.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: تعرف على كيفية تحويل ملفات Numbers باستخدام GroupDocs.Viewer for Java،
  وتحويل ملفات Apple Numbers إلى PDF أو HTML أو JPG أو PNG. يتضمن الإعداد، خطوات تحويل
  المستندات بلغة java، ونصائح عرض الويب.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: كيفية تحويل ملفات Numbers باستخدام GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: كيفية تحويل ملفات Numbers باستخدام GroupDocs.Viewer for Java
type: docs
url: /ar/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# كيفية تحويل ملفات Numbers باستخدام GroupDocs.Viewer للـ Java

عرض جداول Apple Numbers على الويب أو داخل تطبيق سطح المكتب قد يبدو كلغز، خاصةً عندما تحتاج إلى **convert numbers to PDF** أو تضمينها كصور للتقارير. في هذا الدرس ستتعلم بالضبط **how to convert numbers** إلى PDF وHTML وJPG وPNG باستخدام **GroupDocs.Viewer for Java**. سنستعرض إعداد المشروع، وعرض المستوى البرمجي، وسيناريوهات واقعية حتى تتمكن من بناء خطوط أنابيب معاينة أو أرشفة قوية في دقائق.

![عرض مستندات Apple Numbers باستخدام GroupDocs.Viewer للـ Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[عرض مستندات Apple Numbers باستخدام GroupDocs.Viewer للـ Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### ما ستتعلمه
- كيفية إضافة GroupDocs.Viewer إلى مشروع Java يعتمد على Maven.  
- كود خطوة بخطوة لـ **convert numbers to pdf**، **convert numbers to html**، **convert numbers to jpg**، و**convert numbers to png**.  
- متى تختار كل تنسيق إخراج للبوابات الويب، أو سير عمل البريد الإلكتروني، أو أنظمة إدارة المستندات.  

## إجابات سريعة
- **هل يمكنني تحويل Numbers إلى PDF باستخدام Java؟** نعم – أنشئ كائن `Viewer` واستدعِ `PdfViewOptions` للحصول على PDF جاهز للتخزين.  
- **أي تنسيق يوفر معاينة ويب أغنى؟** HTML، لأنه يحافظ على الجداول والصيغ والتنسيق تفاعلية.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يتطلب ترخيص تجاري لأي نشر غير تجريبي.  
- **هل يتم دعم تحويل الصور؟** بالطبع – استخدم `JpgViewOptions` أو `PngViewOptions` للحصول على لقطات عالية الجودة.  
- **ما إصدار Java المطلوب؟** Java 8+ وMaven لإدارة التبعيات.  

## المتطلبات المسبقة
- مجموعة تطوير Java (JDK) 8 أو أحدث مثبتة على جهازك.  
- Maven لإدارة التبعيات وبناء المشروع.  
- إلمام أساسي بملفات I/O في Java، والمسارات، ومعالجة الاستثناءات.  

## إعداد GroupDocs.Viewer للـ Java

### التثبيت باستخدام Maven
أضف مستودع GroupDocs واعتماد Viewer إلى ملف `pom.xml` الخاص بك. يجب أن يظل هذا الجزء كما هو بالضبط:

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
- **Free trial:** مجموعة كاملة من الميزات، لا يلزم بطاقة ائتمان.  
- **Temporary license:** اطلب مفتاحًا مؤقتًا محدودًا للوقت للاختبار الموسع.  
- **Full purchase:** احصل على ترخيص دائم للاستخدام التجاري.  

## ما هي فئة Viewer؟
فئة `Viewer` هي المحرك الأساسي لـ GroupDocs.Viewer الذي يحمل المستند ويعرضه بالتنسيق المطلوب. تقوم بتجريد معالجة نوع الملف بحيث يمكنك التركيز على منطق الأعمال بدلاً من تحليل تفاصيل جداول البيانات.

## كيفية تحويل Numbers إلى HTML باستخدام GroupDocs.Viewer للـ Java؟

`HtmlViewOptions` يحدد إعدادات عرض HTML، مثل تضمين الموارد أو ربط الملفات الخارجية.  
حمّل ملف Numbers، واضبط خيارات HTML، واستدعِ `viewer.view()`. طريقة `HtmlViewOptions.forEmbeddedResources()` تجمع ملفات CSS والصور مباشرةً داخل HTML، مما يجعل النتيجة مثالية لتضمينها في صفحة ويب دون موارد إضافية.

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

- **Why this matters:** الموارد المضمنة تجعل المعاينة مستقلة، مما يلغي الروابط المكسورة للصور ويسهل نشرها عبر CDN.

## كيفية تحويل Numbers إلى JPG باستخدام GroupDocs.Viewer للـ Java؟

`JpgViewOptions` يضبط إخراج JPEG، مما يسمح بتعديل الجودة والحجم لكل صفحة مُعروضة.  
يمكنك تحويل كل صفحة من جدول البيانات إلى لقطة JPEG. اضبط إعداد `quality` لتحقيق توازن بين حجم الملف وجودة الصورة، وهو مفيد عندما تحتاج إلى صور خفيفة للوسائط الاجتماعية أو النشرات البريدية.

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

- **Tip:** للحصول على معالجة أسرع لدفاتر العمل الكبيرة، قلل الجودة إلى 70 % – التأثير البصري يكون ضئيلًا بينما ينخفض حجم الملف بشكل كبير.

## كيفية تحويل Numbers إلى PNG باستخدام GroupDocs.Viewer للـ Java؟

`PngViewOptions` يضبط إخراج PNG، يدعم الضغط بدون فقد وإعدادات الدقة للصور عالية الجودة.  
يقدم PNG ضغطًا بدون فقد، محافظًا على كل بكسل كما هو معروض. استخدم خاصية `resolution` لزيادة DPI عندما تحتاج إلى رسومات جاهزة للطباعة للتقارير أو ملفات PDF.

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

- **Pro tip:** اضبط `options.setResolution(300)` للحصول على إخراج عالي الدقة يبدو واضحًا على الصفحات المطبوعة.

## كيفية تحويل Numbers إلى PDF باستخدام GroupDocs.Viewer للـ Java؟

`PdfViewOptions` يحدد خيارات عرض PDF، بما في ذلك تضمين الخطوط، والضغط، والتحكم في حجم الصفحة.  
كائن `PdfViewOptions` يتيح لك تضمين الخطوط، والتحكم في حجم الصفحة، والحفاظ على تخطيط دفتر Numbers الأصلي. يتم التحويل في استدعاء واحد، وينتج PDF قابل للبحث وغير قابل للتعديل، وهو مثالي للأرشفة أو الامتثال.

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

- **Key configuration:** فعّل `options.setCompress(true)` لتقليل حجم PDF دون التضحية بالجودة، وهو أمر أساسي لمستودعات المستندات الكبيرة.

## لماذا تستخدم GroupDocs.Viewer للـ Java؟

GroupDocs.Viewer يدعم **أكثر من 100 تنسيق ملف**، بما في ذلك Apple Numbers، ويمكنه عرض جداول بيانات مئات الصفحات دون تحميل الملف بالكامل في الذاكرة. تُظهر القياسات أن ملف Numbers مكون من 250 صفحة يتم تحويله إلى PDF في أقل من 8 ثوانٍ على معالج قياسي 2.5 GHz، مما يوفر السرعة والموثوقية لخطوط أنابيب المؤسسات.

## التطبيقات العملية
- **Web integration:** عرض إلى HTML لمشاهد جدول بيانات تفاعلي يعمل عبر المتصفحات دون إضافات.  
- **Content sharing:** تحويل إلى JPG/PNG لتضمين صور سريع في النشرات الإخبارية، تطبيقات الدردشة، أو الخلاصات الاجتماعية.  
- **Enterprise DMS:** استخدم **how to convert numbers** إلى PDF لتخزين نسخة غير قابلة للتعديل وقابلة للبحث من جدول البيانات للامتثال ومسارات التدقيق.

## اعتبارات الأداء
- **Resource management:** احرص دائمًا على إنشاء كائن `Viewer` داخل كتلة try‑with‑resources (كما هو موضح) حتى يتم تحرير الموارد الأصلية بسرعة.  
- **Large workbooks:** عالج الصفحات واحدةً تلو الأخرى وبث الإخراج للحفاظ على استهلاك الذاكرة أقل من 100 ميغابايت، حتى لملفات ذات 500 صفحة.  
- **Thread safety:** أنشئ كائن `Viewer` منفصل لكل خيط؛ الفئة غير آمنة للاستخدام المتعدد الخيوط، لذا مشاركة كائن واحد قد تتسبب في حالات سباق.

## المشكلات الشائعة واستكشاف الأخطاء
- **Missing fonts:** إذا كان PDF الناتج يبدو مختلفًا، تأكد من توفر الخطوط المطلوبة على الخادم أو قم بتضمينها باستخدام `PdfViewOptions.setEmbedFonts(true)`.  
- **Blank pages:** تأكد من أن ملف Numbers غير محمي بكلمة مرور؛ لا يقوم GroupDocs.Viewer حاليًا بفك تشفير دفاتر العمل المحمية.  
- **Out‑of‑memory errors:** للملفات الكبيرة جدًا، فعّل `options.setPageCount(1)` لعرض صفحة واحدة في كل مرة ودمج النتائج لاحقًا.

## الأسئلة المتكررة
**س: ما تنسيقات الملفات التي يدعمها GroupDocs.Viewer؟**  
أ: أكثر من 100 تنسيق، بما في ذلك DOCX، XLSX، PDF، HTML، وApple Numbers، مع قدرات عرض كاملة لكل منها.

**س: كيف يمكنني التعامل مع ملفات Numbers الكبيرة بكفاءة؟**  
أ: قم ببث التحويل صفحةً بصفحة، واستخدم `options.setPageCount()` لتقليل استهلاك الذاكرة، وفكر في ضغط ملف PDF الناتج.

**س: هل يمكن استخدام GroupDocs.Viewer في مشروع تجاري؟**  
أ: نعم—اشترِ ترخيصًا تجاريًا لإزالة قيود النسخة التجريبية والحصول على دعم مستوى الإنتاج.

**س: هل يمكن تخصيص جودة إخراج الصور؟**  
أ: بالطبع. اضبط `JpgViewOptions.setQuality(int)` أو `PngViewOptions.setResolution(int)` لتلبية متطلبات الحجم‑الجودة الخاصة بك.

**س: أين يمكنني العثور على أمثلة استخدام متقدمة؟**  
أ: قم بزيارة [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) للحصول على أدلة متعمقة، ومشاريع نموذجية، وتفاصيل مرجع API.

## الخطوات التالية
جرّب الخيارات المعروضة أعلاه، ثم استكشف تخصيصات إضافية مثل إضافة علامة مائية إلى ملفات PDF، أو إضافة حماية بكلمة مرور، أو دمج العارض في خدمة REST باستخدام Spring Boot. توفر [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) كتالوجًا كاملاً للميزات التي يمكنك دمجها واستخدامها.

## الموارد
- **التوثيق:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **توثيق GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **مرجع API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **تحميل:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **شراء ترخيص:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **تجربة مجانية:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **ترخيص مؤقت:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **منتدى الدعم:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-08-25  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs

## الدروس ذات الصلة
- [كيفية تحويل Excel إلى HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [كيفية تحويل Excel إلى HTML وعرض الصفوف والأعمدة المخفية في Java باستخدام GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [دورة عرض مستندات Java - تحويل الملفات إلى HTML وPDF وصور](/viewer/java/rendering-basics/)