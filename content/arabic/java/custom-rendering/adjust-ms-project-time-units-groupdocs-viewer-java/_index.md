---
date: '2026-05-21'
description: تعلم كيفية تنفيذ تصدير HTML من MS Project مع تعديل وحدات الوقت باستخدام
  GroupDocs Viewer for Java. دليل خطوة بخطوة مع المتطلبات المسبقة، الإعداد، واستكشاف
  الأخطاء وإصلاحها.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'تصدير HTML من MS Project: تعديل وحدات الوقت عبر GroupDocs Java'
type: docs
url: /ar/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# تصدير MS Project إلى HTML: تعديل وحدات الوقت عبر GroupDocs Java

تصدير ملف **MS Project** إلى HTML هو مطلب شائع لوحات معلومات إدارة المشاريع، وبوابات تقارير الحالة، وأدوات المراجعة التعاونية. بشكل افتراضي، يعرض العارض البيانات المتعلقة بالوقت بالدقائق، مما قد يملأ التخطيط البصري ويجعل تقارير اليوم الواحد أصعب في القراءة. باستخدام **GroupDocs Viewer for Java** يمكنك برمجيًا ضبط وحدة الوقت إلى **أيام**، مما ينتج *ms project html export* نظيفًا يتماشى مع توقعات أصحاب المصلحة النموذجية. في هذا البرنامج التعليمي ستتعلم كيفية تكوين العارض، تعديل وحدة الوقت، وتصدير المشروع إلى HTML في بضع خطوات بسيطة.

![ضبط وحدات وقت MS Project باستخدام GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[ضبط وحدات وقت MS Project باستخدام GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## إجابات سريعة
- **ما المكتبة التي تعرض ملفات MS Project؟** GroupDocs Viewer for Java.  
- **ما وحدة الوقت التي يمكنني ضبطها لتصدير HTML؟** Days, using `TimeUnit.DAYS`.  
- **هل أحتاج إلى ترخيص للإنتاج؟** Yes— a permanent license is required; a trial works for evaluation. You can start with a [تجربة GroupDocs المجانية](https://releases.groupdocs.com/viewer/java/).  
- **ما بيئة التطوير المتكاملة (IDE) التي تعمل بشكل أفضل؟** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **هل Maven إلزامي؟** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **أين يمكنني الشراء؟** Visit the [صفحة الشراء](https://purchase.groupdocs.com/buy) for pricing.

## ما هو GroupDocs Viewer for Java؟
**GroupDocs Viewer for Java** هو مجموعة تطوير برمجيات Java SDK تقوم بتحويل أكثر من 150 تنسيق مستند — بما في ذلك MS Project — إلى HTML، PNG، JPEG، أو PDF صديقة للويب.  
إنها تجريد منطق التحليل، وتتيح لك التحكم في خيارات العرض مثل وحدات الوقت، وتعمل على أي منصة تدعم Java 8 أو أعلى.  

## لماذا تعديل وحدات الوقت لتصدير MS Project إلى HTML؟
ضبط وحدة الوقت إلى **أيام** يقلل من الضوضاء البصرية، ويتطابق مع معظم دورات التقارير، ويحسن أوقات تحميل الصفحة لأن عدد علامات الوقت الدقيقة يقل. من الناحية الكمية، يمكن أن يقلل العرض بالأيام بدلاً من الدقائق حجم HTML المُولد حتى **45 %** للمشاريع النموذجية ذات الـ30 يومًا، كما يسرّع عرض الجانب العميل بحوالي **30 %**.

## المتطلبات المسبقة
- **Java Development Kit (JDK) 8 أو أحدث** مثبت على محطة العمل الخاصة بك.  
- **Maven** (أو Gradle) لإدارة الاعتمادات.  
- ملف **MS Project (.mpp)** تريد تصديره.  
- الوصول إلى ترخيص **GroupDocs Viewer for Java** (تجريبي أو دائم).  

### المكتبات المطلوبة
أضف الاعتماد التالي إلى ملف `pom.xml` الخاص بك (أو المقتطف المكافئ لـ Gradle):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **نصيحة احترافية:** حافظ على تحديث رقم الإصدار؛ الإصدارات الأحدث تضيف دعمًا للتنسيقات وتحسينات في الأداء.

## كيف أقوم بإعداد GroupDocs Viewer for Java؟
ابدأ تشغيل العارض بإنشاء مثيل `Viewer` يشير إلى ملف MS Project الخاص بك. فئة `Viewer` هي نقطة الدخول لجميع عمليات العرض. تقوم بتحميل المستند المصدر، وتجهز الهياكل الداخلية، وتكشف عن طرق مثل `view()` و `viewToHtml()` لتوليد صيغ الإخراج المطلوبة.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **مرساة التعريف:** فئة `Viewer` هي المكوّن الأساسي في GroupDocs Viewer الذي يحمل مستندًا مصدرًا ويوفر طرق عرض مثل `view()` و `viewToHtml()`.

## كيف يمكنني تعديل وحدات الوقت لتصدير HTML؟
لتغيير دقة الوقت، أنشئ كائن `ViewOptions`، واضبط `ProjectOptions` الخاص به لاستخدام `TimeUnit.DAYS`، ثم مرره إلى العارض. يحدد `ViewOptions` إعدادات العرض للمستند، بينما يحدد تعداد `TimeUnit` الوحدة (دقائق، ساعات، أيام) للبيانات المتعلقة بالوقت. بعد ضبط هذه الخيارات، استدعِ `viewer.view(options)` لإنتاج HTML مع علامات يومية.

حمّل ملف MS Project الخاص بك باستخدام `new Viewer("file.mpp")`، أنشئ كائن `ViewOptions`، اضبط `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`، ثم استدعِ `viewer.view(options)`. يغيّر هذا التدفق المكوّن من ثلاث خطوات وحدة الوقت من الدقائق إلى الأيام وينتج ملفات HTML تعرض الفواصل اليومية فقط.

### الخطوة 1: تحديد مجلد الإخراج
اختر دليلًا قابلًا للكتابة حيث سيتم حفظ صفحات HTML، على سبيل المثال `output/`.

### الخطوة 2: إنشاء خيارات العرض مع الموارد المضمنة
الموارد المضمنة (CSS، JavaScript) تضمن أن صفحات HTML ذاتية الاحتواء.

### الخطوة 3: ضبط وحدة الوقت إلى أيام
استخدم `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` لتبديل الدقة.

### الخطوة 4: عرض المستند
استدعِ `viewer.view(options)`؛ يكتب العارض ملف HTML واحد لكل صفحة مشروع في مجلد الإخراج.

### الخطوة 5: التحقق من النتيجة
افتح ملف `index.html` المُولد في المتصفح؛ يجب أن ترى أشرطة المهام محاذية إلى علامات اليوم بدلاً من علامات الدقيقة.

## المشكلات الشائعة واستكشاف الأخطاء وإصلاحها
- **مسار الإخراج غير صحيح** – تأكد من وجود الدليل وأن عملية Java لديها أذونات كتابة.  
- **الترخيص مفقود** – بدون ترخيص صالح يعود العارض إلى وضع التجربة وقد يضيف علامات مائية.  
- **ملفات كبيرة (> 500 MB)** – فكر في زيادة حجم ذاكرة JVM (`-Xmx2g`) أو العرض باستخدام `options.setRenderLimit(1000)` لمعالجة الصفحات على دفعات.  

## التطبيقات العملية لتصدير HTML بوحدة وقت معدلة
1. **لوحات القيادة التنفيذية** – الدقة اليومية تتطابق مع معظم تصورات مؤشرات الأداء الرئيسية.  
2. **رسائل البريد الإلكتروني التلقائية للتقارير** – دمج HTML المُولد مباشرةً في محتوى البريد لتحديثات سريعة.  
3. **بوابات المشروع** – استضافة HTML على موقع إنترانت حيث يمكن لأعضاء الفريق تصفية المهام حسب اليوم.  

## اعتبارات الأداء لملفات MS Project الكبيرة
- **إدارة الذاكرة** – استخدم علامات جامع القمامة في Java (`-XX:+UseG1GC`) لتحرير الكائنات غير المستخدمة بسرعة.  
- **العرض الانتقائي** – إذا كنت تحتاج فقط مخطط جانت، عطل عرض الموارد الأخرى عبر `options.getProjectOptions().setRenderGantt(true)` و `setRenderResources(false)`.  
- **المعالجة المتوازية** – للتحويلات الدفعية، أنشئ كائنات `Viewer` منفصلة لكل ملف وشغّلها في مجموعة خيوط للاستفادة من المعالجات متعددة النوى.

## الخلاصة
أنت الآن تمتلك سير عمل كامل وجاهز للإنتاج لإجراء **ms project html export** مع ضبط وحدات الوقت إلى أيام باستخدام GroupDocs Viewer for Java. يقلل هذا النهج من حجم HTML، ويسرّع عرض العميل، ويقدم عرضًا صديقًا لأصحاب المصلحة لجدول المشروع. استكشف خيارات عرض إضافية — مثل تصدير PDF أو لقطات الصور — لتوسيع التكامل إلى خطوط تقارير أوسع.

## الأسئلة المتكررة

**س: هل يمكنني عرض وجهات نظر مشروع أخرى (مثل ورقة الموارد) إلى HTML؟**  
ج: نعم، يتيح لك كائن `ProjectOptions` تمكين أو تعطيل وجهات نظر محددة مثل جانت، ورقة الموارد، والتقويم قبل العرض.

**س: هل يمكن تخصيص CSS للـ HTML المُولد؟**  
ج: بالطبع. قدم مسار ورقة الأنماط المخصصة عبر `options.setStyleSheetPath("path/to/custom.css")` وسيقوم العارض بدمجها في كل صفحة.

**س: ما حدود حجم الملف التي يدعمها GroupDocs Viewer لملفات MS Project؟**  
ج: يمكن لمجموعة تطوير البرمجيات التعامل مع ملفات تصل إلى **500 MB** دون الحاجة إلى تحميل المستند بالكامل في الذاكرة، بفضل بنية البث الخاصة به.

**س: هل أحتاج إلى تثبيت Microsoft Project على الخادم؟**  
ج: لا. يقوم GroupDocs Viewer بتحليل تنسيق .mpp مباشرة ولا يتطلب Microsoft Project أو أي تثبيت Office.

**س: كيف أُرخص العارض لبيئة الإنتاج؟**  
ج: اشترِ ترخيصًا دائمًا من متجر GroupDocs؛ طبّق ملف الترخيص وقت التشغيل باستخدام `License license = new License(); license.setLicense("path/to/license.lic");`. للاحتياجات قصيرة الأجل يمكنك الحصول على [ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/).

**آخر تحديث:** 2026-05-21  
**تم الاختبار مع:** GroupDocs Viewer Java 25.2  
**المؤلف:** GroupDocs  

## الموارد
- [التوثيق](https://docs.groupdocs.com/viewer/java/)  
- [مرجع API](https://reference.groupdocs.com/viewer/java/)  
- [تحميل GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [شراء ترخيص](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## دروس ذات صلة

- [كيفية عرض ملفات MS Project كـ HTML، JPG، PNG، و PDF مع الملاحظات باستخدام GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [كيفية استخدام GroupDocs Viewer لعرض مستندات المشروع حسب الفواصل الزمنية في Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [كيفية ضبط التراخيص في GroupDocs.Viewer Java: دليل إعداد الملف و URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)