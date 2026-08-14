---
date: '2026-06-30'
description: تعلم كيفية استرجاع وحفظ مرفقات المستند بفعالية في تطبيقات Java باستخدام
  java file output stream وواجهة برمجة التطبيقات القوية GroupDocs.Viewer API.
keywords:
- java file output stream
- how to save attachment
- GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  headline: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  name: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  steps:
  - name: '**Create a Viewer Instance**'
    text: '**Create a Viewer Instance**'
  - name: '**Retrieve Attachments**'
    text: '**Retrieve Attachments**'
  - name: '**Understanding Parameters and Methods**'
    text: '**Understanding Parameters and Methods**'
  - name: '**Define the Output Directory**'
    text: '**Define the Output Directory**'
  - name: '**Save Attachments**'
    text: '**Save Attachments**'
  - name: '**Explain Parameters and Methods**'
    text: '**Explain Parameters and Methods**'
  - name: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
    text: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
  - name: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
    text: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
  - name: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
    text: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown earlier; the repository URL and version
      are all you need for a quick start.
    question: How do I install GroupDocs.Viewer in my Java project?
  - answer: It supports 50+ input and output formats—including PDF, DOCX, PPTX, MSG,
      and many image types—so most common business files are covered.
    question: Can GroupDocs.Viewer handle all document types?
  - answer: Verify that the output path is correct, the directory exists, and your
      process has write permissions. Also ensure you’re using `FileOutputStream` correctly
      as shown.
    question: What if I encounter errors while saving attachments?
  - answer: Yes, a valid GroupDocs.Viewer license is required for production deployments.
      A free trial is available for evaluation.
    question: Is a license required for production use?
  - answer: Using `java file output stream` with buffered I/O efficiently handles
      large binaries; monitor memory usage and consider streaming in chunks for files
      larger than 200 MB.
    question: Does this approach work with large attachment files?
  type: FAQPage
title: كيفية استرجاع وحفظ مرفقات المستند باستخدام java file output stream مع GroupDocs.Viewer
  for Java
type: docs
url: /ar/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# كيفية استرجاع وحفظ مرفقات المستند باستخدام java file output stream مع GroupDocs.Viewer for Java

## المقدمة

هل تبحث عن استخراج وإدارة مرفقات المستندات برمجياً في تطبيقات Java الخاصة بك باستخدام **java file output stream**؟ مع تزايد إدارة المستندات الرقمية، من الضروري وجود أدوات تُسهّل هذه العمليات بفعالية. نقدم لكم GroupDocs.Viewer for Java—الحل المثالي لاسترجاع وحفظ مرفقات المستندات بسهولة.

![استرجاع وحفظ مرفقات المستندات باستخدام GroupDocs.Viewer for Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

[استرجاع وحفظ مرفقات المستندات باستخدام GroupDocs.Viewer for Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

في هذا البرنامج التعليمي، سنستكشف كيفية الاستفادة من قوة GroupDocs.Viewer لاسترجاع المرفقات من المستندات وحفظها في الدليل الذي تختاره. باتباع الخطوات، ستحصل على مهارات عملية في إدارة بيانات المستند بفعالية داخل بيئة Java، وسترى بالضبط **how to save attachment** باستخدام `java file output stream` القياسي.

## إجابات سريعة
- **ما الذي يفعله java file output stream؟** يكتب تدفقات البايت مباشرة إلى الملفات، مما يتيح حفظ البيانات الثنائية (مثل المرفقات) على القرص.  
- **ما الـ API الذي يسترجع المرفقات؟** `Viewer.getAttachments()` يُعيد قائمة ببيانات تعريف المرفقات.  
- **هل يمكنني تحديد مجلد الإخراج؟** نعم—استخدم `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتقييم؛ الترخيص المدفوع مطلوب للإنتاج.  
- **هل هذا النهج آمن للخطوط المتعددة؟** أنشئ نسخة منفصلة من كائن `Viewer` لكل خيط أو قم بمزامنة الوصول.

## ما هو java file output stream؟
`java.io.FileOutputStream` هو فئة أساسية في Java تكتب البايتات الخام إلى ملف. إنها الخيار المثالي عندما تحتاج إلى حفظ محتوى ثنائي مثل مرفقات البريد الإلكتروني، الصور، أو أي بيانات غير نصية مستخرجة من مستند. تدعم كتابة الملفات الصغيرة والكبيرة بكفاءة ويمكن دمجها مع تدفقات مؤقتة لتحسين الأداء، مما يضمن تخزينًا موثوقًا للحمولات الثنائية على القرص.

## لماذا نستخدم java file output stream مع GroupDocs.Viewer؟
استخدام `java.io.FileOutputStream` مع GroupDocs.Viewer يسمح للمطورين بكتابة بايتات المرفقات مباشرة إلى القرص دون أي خطوات تحويل وسيطة، مما يحافظ على سلامة الملف الأصلي. يقلل هذا النهج من استهلاك الذاكرة، ويسرّع معالجة المرفقات الكبيرة، ويبسّط الشيفرة بالاعتماد على I/O القياسي في Java إلى جانب قدرات استخراج قوية من GroupDocs.Viewer.

- **معالجة ثنائية مباشرة** – لا حاجة لتحويلات وسيطة؛ تُكتب بايتات المرفق بالضبط كما هي في الملف الأصلي.  
- **الأداء** – الكتابة المتدفقة تقلل من استهلاك الذاكرة، خاصةً للمرفقات الكبيرة.  
- **البساطة** – يتكامل الـ API بسلاسة مع I/O القياسي في Java، مما يجعل الشيفرة سهلة القراءة والصيانة.

## المتطلبات المسبقة
- **المكتبات والاعتمادات المطلوبة**: أضف مكتبة GroupDocs.Viewer إلى مشروعك (انظر مقتطف Maven أدناه).  
- **إعداد البيئة**: بيئة تطوير Java (IntelliJ IDEA، Eclipse، إلخ) مع JDK 8+ مثبتة.  
- **المتطلبات المعرفية**: إلمام بـ Java I/O، خاصةً `FileOutputStream`، واستخدام أساسي لـ Maven.

## إعداد GroupDocs.Viewer للغة Java
لبدء استخدام API الخاص بـ GroupDocs.Viewer في مشروعك، تحتاج إلى تثبيته عبر Maven. أضف التكوين التالي إلى ملف `pom.xml` الخاص بك:

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

**خطوات الحصول على الترخيص:**
- **نسخة تجريبية مجانية**: ابدأ بنسخة تجريبية مجانية لاستكشاف الميزات.  
- **ترخيص مؤقت**: احصل على ترخيص مؤقت لفترة تقييم ممتدة.  
- **شراء**: للاستخدام في الإنتاج، ستحتاج إلى ترخيص مدفوع.

### الإعداد والتهيئة الأساسية
بعد إضافة GroupDocs.Viewer كاعتماد في مشروعك، قم بتهيئته في تطبيق Java الخاص بك. إليك الطريقة:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

هذه الإعدادات الأساسية تُهيئ GroupDocs.Viewer وتجهّزه لاسترجاع المرفقات.

## دليل التنفيذ

### استرجاع المرفقات باستخدام java file output stream
سنوضح كيفية استرجاع المرفقات باستخدام GroupDocs.Viewer. تتيح لك هذه الميزة استخراج بيانات التعريف لكل مرفق موجود في المستند.

#### نظرة عامة
يتضمن استرجاع المرفقات الوصول إلى طريقة `getAttachments`، التي تُعيد قائمة من كائنات `Attachment` تحتوي على تفاصيل مثل اسم الملف وحجمه. **Attachment** يمثل ملفًا مدمجًا داخل المستند الأصلي، مثل صورة أو ملف مضمّن.

#### خطوات التنفيذ
1. **إنشاء كائن Viewer**  
   `Viewer` هو الفئة الرئيسية في GroupDocs.Viewer التي تُحمّل وتعالج المستندات للعرض والاستخراج. قم بتهيئة فئة `Viewer` مع مسار المستند الخاص بك:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **استرجاع المرفقات**  
   استخدم طريقة `getAttachments`:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **فهم المعلمات والطرق**  
   - `Viewer`: يأخذ مسار ملف أو تدفق إلى المستند.  
   - `getAttachments()`: يسترجع قائمة بالملفات المرفقة، موفرًا تفاصيل مثل الأسماء.

### حفظ مرفقات المستند إلى دليل
الآن بعد أن تعلمت كيفية استرجاع المرفقات، لنقم بحفظها في الدليل الذي تختاره باستخدام API الخاص بـ GroupDocs.Viewer و **java file output stream**.

#### نظرة عامة
تتضمن هذه الميزة حفظ كل ملف مرفق تم استرجاعه إلى دليل إخراج محدد.

#### خطوات التنفيذ
1. **تحديد دليل الإخراج**  
   اضبط مسار `outputDirectory` حيث سيتم حفظ الملفات:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **حفظ المرفقات**  
   استخدم حلقة لحفظ كل مرفق باستخدام طريقة `saveAttachment`. **saveAttachment** تكتب المحتوى الثنائي لـ `Attachment` إلى `OutputStream` مُقدم.

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **شرح المعلمات والطرق**  
   - `saveAttachment`: يأخذ كائن `Attachment` وتدفق إخراج ملف لحفظ المرفق.  
   - `FileOutputStream`: يدير كتابة البيانات إلى الملفات باستخدام سلوكيات **java file output stream**.

## كيف تحفظ المرفق باستخدام java file output stream؟
حمّل كل كائن `Attachment`، افتح `FileOutputStream` للملف الهدف، وانقل بايتات المرفق مباشرة إلى القرص. يكتب هذا النهج الحمولة الثنائية الدقيقة دون أي تحويل ويضمن أن الملف المحفوظ يطابق المرفق الأصلي بايتًا لبايت. للمرفقات الكبيرة، غلف التدفق بـ `BufferedOutputStream` لتحسين معدل النقل وتقليل عمليات I/O. **BufferedOutputStream** يخفّض عدد عمليات الكتابة، مما يحسن الأداء للملفات الكبيرة.

### المشكلات الشائعة والحلول
- **الاعتمادات المفقودة**: تأكد من إضافة جميع اعتمادات Maven بشكل صحيح.  
- **أخطاء مسار الملف**: تحقق من صحة المسارات لكل من المستندات وأدلة الإخراج.  
- **أذونات الوصول**: تأكد من أن تطبيقك يمتلك أذونات القراءة/الكتابة اللازمة.

## التطبيقات العملية
يمكن أن يكون استخدام GroupDocs.Viewer في Java ذا قيمة كبيرة عبر سيناريوهات متعددة:

1. **عملاء البريد الإلكتروني** – استخراج المرفقات تلقائيًا من أرشيفات البريد للمعالجة أو الأرشفة.  
2. **أنظمة إدارة المستندات** – تحسين DMS عبر استرجاع وتنظيم الملفات المرفقة.  
3. **الأقسام القانونية** – استخراج مرفقات الأدلة من المستندات القانونية بأمان.

إمكانيات التكامل مع CRM، ERP، أو محركات سير العمل المخصصة يمكن أن تُبسط عمليات الأعمال أكثر، مما يجعل معالجة المرفقات سلسة عبر الأقسام.

## اعتبارات الأداء
لتحسين الأداء عند استخدام GroupDocs.Viewer:

- **تحسين معالجة الملفات** – استخدم تدفقات مؤقتة للملفات الكبيرة وأغلق الموارد فورًا.  
- **إدارة الذاكرة** – حرّر كائنات `Viewer` بسرعة (try‑with‑resources) لتجنب تسرب الذاكرة.  
- **الفائدة المكمّنة** – يمكن لـ GroupDocs.Viewer معالجة مستندات تصل إلى 500 ميغابايت والتعامل مع ما يصل إلى 200 مرفق لكل ملف مع الحفاظ على استهلاك الذاكرة تحت 150 ميغابايت على JVM قياسي بذاكرة 8 جيجابايت.

اتباع أفضل ممارسات Java سيعزز بشكل كبير كفاءة خط أنابيب معالجة المرفقات لديك.

## الخاتمة
لقد استكشفت الآن كيفية استرجاع وحفظ مرفقات المستندات باستخدام **java file output stream** مع GroupDocs.Viewer للغة Java. يبسط هذا الـ API القوي إدارة بيانات المستند، مما يجعله أداة أساسية للمطورين العاملين مع المستندات الرقمية. لاستكشاف المزيد من إمكانيات GroupDocs.Viewer، جرّب ميزاته الأخرى—مثل عرض الصفحات، تحويل الصيغ، أو استخراج النص. إذا كان لديك أسئلة أو تحتاج إلى دعم، لا تتردد في التواصل عبر الموارد الرسمية.

## الأسئلة المتكررة

**س: كيف أقوم بتثبيت GroupDocs.Viewer في مشروع Java الخاص بي؟**  
ج: أضف اعتماد Maven المعروض سابقًا؛ عنوان المستودع والإصدار كل ما تحتاجه للبدء بسرعة.

**س: هل يستطيع GroupDocs.Viewer التعامل مع جميع أنواع المستندات؟**  
ج: يدعم أكثر من 50 صيغة إدخال وإخراج—including PDF, DOCX, PPTX, MSG، والعديد من صيغ الصور—لذا يغطي معظم ملفات الأعمال الشائعة.

**س: ماذا أفعل إذا واجهت أخطاء أثناء حفظ المرفقات؟**  
ج: تحقق من صحة مسار الإخراج، وتأكد من وجود الدليل، وتأكد من أن عمليتك تملك أذونات الكتابة. كما يجب استخدام `FileOutputStream` كما هو موضح.

**س: هل يلزم وجود ترخيص للاستخدام في بيئة الإنتاج؟**  
ج: نعم، يتطلب الاستخدام في الإنتاج ترخيص GroupDocs.Viewer صالح. تتوفر نسخة تجريبية مجانية للتقييم.

**س: هل يعمل هذا النهج مع ملفات مرفقات كبيرة؟**  
ج: باستخدام **java file output stream** مع I/O مؤقت، يتم التعامل بفعالية مع الثنائيات الكبيرة؛ راقب استهلاك الذاكرة وفكّ التدفق إلى أجزاء للملفات التي تتجاوز 200 ميغابايت.

**آخر تحديث:** 2026-06-30  
**تم الاختبار مع:** GroupDocs.Viewer 25.2  
**المؤلف:** GroupDocs  

## دروس ذات صلة

- [كيفية استرجاع المرفقات وطباعة مرفقات المستند باستخدام GroupDocs.Viewer للغة Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [عرض مرفقات المستند بصيغة HTML باستخدام GroupDocs.Viewer Java: دليل خطوة بخطوة](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
- [معالج العرض المخصص Java – درس GroupDocs Viewer](/viewer/java/custom-rendering/)