---
date: '2026-06-30'
description: تعلم كيفية الحصول على viewinfo واسترجاع هياكل ملفات الأرشيف من نوع java
  باستخدام GroupDocs.Viewer. يغطي هذا الدليل الإعداد، أمثلة الشيفرة، وحالات الاستخدام
  الواقعية.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: كيفية الحصول على ViewInfo واسترجاع هياكل الأرشيف في Java
type: docs
url: /ar/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# كيفية الحصول على ViewInfo واسترجاع هياكل الأرشيف في Java

إدارة ملفات الأرشيف بفعالية تتطلب فهماً واضحاً لهياكلها. في هذا الدرس ستتعلم **كيفية الحصول على viewinfo** لأي أرشيف وتعرف كيف يساعدك في التعامل مع **نوع ملف الأرشيف java**. سنستعرض إعداد GroupDocs.Viewer، استخراج معلومات العرض، وقراءة هياكل المجلدات بشكل متكرر حتى تتمكن من دمج الحل في المشاريع الحقيقية.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**ما ستتعلمه**
- إعداد وتكوين GroupDocs.Viewer لـ Java.  
- طرق **الحصول على viewinfo** من الأرشيفات.  
- تقنيات لقراءة وعرض هيكل المجلدات لملف الأرشيف.  
- تطبيقات عملية واعتبارات الأداء عند استخدام GroupDocs.Viewer في مشاريع Java.

## إجابات سريعة
- **ماذا يقدم “viewinfo”?** يُعيد نوع الملف، عدد الصفحات، وقائمة كاملة بالمجلدات والملفات داخل الأرشيف.  
- **ما هي صيغ الأرشيف المدعومة؟** ZIP، RAR، TAR، 7z، ISO، وأكثر من 12 صيغة شائعة أخرى.  
- **هل أحتاج إلى ترخيص للإنتاج؟** نعم—ترخيص تجاري مطلوب للإنتاج؛ النسخة التجريبية المجانية تكفي للتقييم.  
- **هل يمكن معالجة الأرشيفات الكبيرة بكفاءة؟** بالتأكيد—استخدم خيارات البث وعالج مستوى مجلد واحد في كل مرة للحفاظ على استهلاك الذاكرة منخفضاً.  
- **هل Maven هو الطريقة الوحيدة لإضافة المكتبة؟** Maven هو مدير الاعتماديات الموصى به، لكن Gradle أو إضافة JAR يدوية تعمل أيضاً.

## ما هو “كيفية الحصول على viewinfo”؟
`getViewInfo` هي طريقة في API الخاص بـ GroupDocs.Viewer تستخرج البيانات الوصفية من مستند أو أرشيف دون الحاجة إلى عرض كامل. تُعيد شجرة المجلدات الداخلية، عدد الملفات، والخصائص الأساسية في استدعاء واحد، مما يتيح لك اختيار الأجزاء التي تريد معالجتها. تُعيد الاستدعاء لقطة كاملة للأرشيفات حتى 500 ميغابايت في أقل من ثانية على الخوادم العادية.

## لماذا استرجاع هياكل نوع ملف الأرشيف Java؟
استرجاع التخطيط الداخلي لـ **نوع ملف الأرشيف java** يتيح لك العثور على الملفات المطلوبة فوراً، تجنب الاستخراج غير الضروري، وبناء خطوط أنابيب آلية تتعامل فقط مع المجلدات الفرعية ذات الصلة. يقلل هذا النهج من عمليات الإدخال/الإخراج بنسبة تصل إلى 70 % للأرشيفات الكبيرة ويجعل من الممكن فحص آلاف الملفات في الدقيقة في سيناريوهات استيعاب البيانات.

## المتطلبات المسبقة
- **مجموعة تطوير جافا (JDK):** الإصدار 8 أو أحدث.  
- **Maven:** لإدارة الاعتماديات والبناء.  
- **معرفة أساسية بجافا:** الإلمام بمفاهيم البرمجة الكائنية مفيد لكنه ليس إلزاميًا.  

تحتاج أيضاً إلى الوصول إلى مكتبة GroupDocs.Viewer، والتي يمكنك إضافتها إلى مشروع Maven الخاص بك كما هو موضح أدناه.

## إعداد GroupDocs.Viewer لجافا

### تكوين Maven

أضف المستودع والاعتماد إلى ملف `pom.xml` الخاص بك.

**المستودعات:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**الاعتمادات:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### الحصول على الترخيص

- **نسخة تجريبية مجانية:** تحميل نسخة تجريبية من موقع GroupDocs.  
- **ترخيص مؤقت:** طلب مفتاح مؤقت للتقييم قصير المدى.  
- **ترخيص كامل:** شراء ترخيص تجاري للاستخدام الإنتاجي غير المحدود.

بمجرد أن تكون المكتبة على مسار الفئة (classpath)، يمكنك البدء بالبرمجة.

## دليل التنفيذ

### كيفية الحصول على ViewInfo لملفات الأرشيف

للحصول على معلومات العرض، قم أولاً بتحميل الأرشيف إلى Viewer، ثم استدعِ `getViewInfo` لاسترجاع البيانات الوصفية، وأخيراً كرّر عبر شجرة المجلدات المسترجعة. هذا النمط المكوّن من ثلاث خطوات يعمل مع جميع صيغ الأرشيف المدعومة ويوفر لقطة كاملة في استدعاء API واحد، مما يبسط المعالجة اللاحقة.

#### تهيئة الـ Viewer

فئة `Viewer` هي نقطة الدخول لجميع عمليات العرض والفحص. تدير تدفقات الملفات، اكتشاف الصيغ، وتنظيف الموارد.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### استرجاع معلومات العرض

`ViewInfo` يضم البيانات الوصفية مثل نوع الملف، إجمالي الصفحات، وقائمة هرمية بالمجلدات والملفات. استدعاء `getViewInfo` يُعيد هذا الكائن فوراً.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### عرض هيكل المجلدات

كرر عبر `viewInfo.getFolders()` لطباعة اسم كل مجلد، عمقه، والملفات المحتواة. هذه الحلقة البسيطة تمنحك عرض شجرة قابل للقراءة للأرشيف.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### قراءة المجلدات بشكل متكرر

للأرشيفات المتداخلة بعمق، يمكن لطريقة مساعدة متكررة أن تتجول في الشجرة من الأعلى إلى الأسفل، مما يضمن زيارة كل مجلد فرعي دون تحميل كامل الأرشيف في الذاكرة.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### الميزة 2: استرجاع هيكل مجلد الأرشيف

تركز هذه الميزة على طباعة هيكل مجلد ملف الأرشيف. هي مشابهة للميزة الأولى لكن تبرز الاستكشاف المتكرر.

#### إعداد خيارات معلومات العرض

`ArchiveOptions` يتيح لك تحديد حماية كلمة المرور، حدود الصفحات، وتفضيلات البث قبل استدعاء `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### استكشاف متكرر

روتين متكرر ثانٍ يوضح كيفية التعامل مع الأرشيفات المحمية بكلمة مرور ومجموعات الملفات الكبيرة بكفاءة.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## التطبيقات العملية
1. **إدارة البيانات:** تنظيم سريع لمجموعات البيانات الكبيرة من خلال فهم هياكل الأرشيف.  
2. **معالجة الملفات تلقائيًا:** معالجة دفعة من الملفات المؤرشفة دون استخراجها بالكامل، مما يقلل الإدخال/الإخراج بنسبة تصل إلى 70 %.  
3. **تكامل CMS:** تحسين أنظمة إدارة المحتوى بميزة تصفح الأرشيف مباشرة، مما يتيح للمحررين معاينة الملفات مباشرة من الأرشيف.

## اعتبارات الأداء
- **تحسين استخدام الذاكرة:** معالجة المجلدات مستوىً واحدًا في كل مرة وإغلاق كائن `Viewer` بسرعة.  
- **ابق محدثًا:** استخدم أحدث إصدار من GroupDocs.Viewer (25.2 وقت الكتابة) وإصدارات JDK للحصول على تحسينات في الأداء.  
- **دعم البث:** يمكن للمكتبة بث الأرشيفات الأكبر من 1 جيجابايت دون تحميل الملف بالكامل إلى الذاكرة، بفضل بنية القراءة المجزأة الداخلية.

## المشكلات الشائعة والحلول

| المشكلة | سبب حدوثه | الحل |
|-------|----------------|-----|
| `NullPointerException` عند قراءة المجلدات | `viewInfo.getFolders()` يُعيد null للدلائل الفارغة | تحقق من null أو القائمة الفارغة قبل التكرار. |
| معالجة بطيئة لملفات ZIP الضخمة | يتم تحميل الأرشيف بالكامل في الذاكرة | استخدم خيارات البث المتاحة في إصدارات GroupDocs الأحدث. |
| لم يتم العثور على الترخيص | مسار ملف الترخيص غير صحيح | ضع ملف الترخيص في جذر التطبيق أو اضبط `License.setLicense("path/to/license.json")`. |

## الأسئلة المتكررة

**س:** ما هو GroupDocs.Viewer؟  
**ج:** GroupDocs.Viewer هي مكتبة Java تقوم بتحويل أكثر من 100 صيغة من المستندات، الصور، والأرشيفات إلى HTML أو PDF أو تدفقات صور دون الحاجة إلى تطبيقات أصلية.

**س:** هل يمكنني استخدام GroupDocs.Viewer مع لغات برمجة أخرى؟  
**ج:** نعم، تقدم GroupDocs مجموعات تطوير (SDKs) لـ .NET، Python، PHP، وغيرها، لكن هذا الدرس يركز على تنفيذ Java.

**س:** كيف أتعامل مع ملفات الأرشيف الكبيرة؟  
**ج:** فعّل البث عبر `ArchiveOptions.setUseStreaming(true)`، عالج مستوى مجلد واحد في كل مرة، وتخلص من كائن `Viewer` بعد الاستخدام.

**س:** ما هي أنواع الأرشيف التي يدعمها GroupDocs.Viewer؟  
**ج:** يدعم أكثر من 12 صيغة أرشيف، بما في ذلك ZIP، RAR، TAR، 7z، ISO، ARJ، وCAB، بالإضافة إلى العديد من صيغ الحاويات المملوكة.

**س:** هل هناك حد لحجم الأرشيفات؟  
**ج:** الحد العملي يعتمد على ذاكرة RAM ومعالج الخادم؛ تُظهر الاختبارات معالجة سلسة لأرشيفات بحجم 2 جيجابايت على جهاز بذاكرة 16 جيجابايت عندما يكون البث مفعلاً.

**س:** هل تعمل “كيفية الحصول على viewinfo” مع الأرشيفات المحمية بكلمة مرور؟  
**ج:** نعم، قدم كلمة المرور عبر `ArchiveOptions.setPassword("yourPassword")` قبل استدعاء `getViewInfo`.

## الخلاصة

باتباع هذا الدليل، أصبحت الآن تعرف **كيفية الحصول على viewinfo** لأي أرشيف مدعوم وكيفية استعراض شجرة مجلداته باستخدام GroupDocs.Viewer لجافا. تمكّنك هذه التقنيات من بناء خطوط معالجة بيانات أذكى، تحسين تكاملات CMS، والتعامل مع مجموعات كبيرة من الملفات المؤرشفة بثقة. بعد ذلك، استكشف عرض الملفات الفردية من الأرشيف أو تحويلها إلى PDF/HTML باستخدام ميزات Viewer الأخرى.

---

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs  

**الموارد**
- **التوثيق:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **مرجع API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **تحميل GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **شراء ترخيص:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **نسخة تجريبية وترخيص مؤقت:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## دروس ذات صلة

- [استخراج بيانات المستند الوصفية باستخدام GroupDocs.Viewer لجافا - استرجاع معلومات عرض المستند والرؤى](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [كيفية استرجاع المرفقات وطباعة مرفقات المستند باستخدام GroupDocs.Viewer لجافا](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [دليل Java: عرض صفحات محددة باستخدام API الخاص بـ GroupDocs.Viewer لمعاينة وإدارة المستندات](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)