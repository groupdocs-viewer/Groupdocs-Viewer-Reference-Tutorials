---
date: '2026-02-02'
description: تعرّف على كيفية استرجاع مرفقات المستندات وحفظها بكفاءة في تطبيقات Java
  باستخدام تدفق إخراج ملفات Java وواجهة برمجة التطبيقات القوية GroupDocs.Viewer.
keywords:
- GroupDocs.Viewer Java
- retrieve document attachments Java
- save document attachments GroupDocs
title: كيفية استرجاع وحفظ مرفقات المستند باستخدام تدفق إخراج ملف جافا مع GroupDocs.Viewer
  لجافا
type: docs
url: /ar/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# كيفية استرجاع وحفظ مرفقات المستند باستخدام java file output stream مع GroupDocs.Viewer للـ Java

## مقدمة

هل تبحث عن استخراج وإدارة مرفقات المستندات برمجيًا في تطبيقات Java الخاصة بك باستخدام **java file output stream**؟ مع تزايد إدارة المستندات الرقمية، من الضروري وجود أدوات تُبسط هذه العمليات بكفاءة. نقدم لك GroupDocs.Viewer للـ Java—الحل المثالي لاسترجاع وحفظ مرفقات المستندات بسهولة.

![استرجاع وحفظ مرفقات المستند باستخدام GroupDocs.Viewer للـ Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

في هذا الدرس، سنستكشف كيف يمكنك الاستفادة من قوة GroupDocs.Viewer لاسترجاع المرفقات من المستندات وحفظها في الدليل الذي ترغب به. باتباع الخطوات ستحصل على مهارات عملية في إدارة بيانات المستند بفعالية داخل بيئة Java.

## إجابات سريعة
- **ماذا يفعل java file output stream؟** (؟**ني تحديد مجلد الإخراج؟** نعم—استخدم `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص المدفوع مطلوب للإنتاج.  
- **هل هذه الطريقة آمنة في بيئة متعددة الخيوط؟** أنشئ نسخة منفصلة من `Viewer` لكل خيط أو قم بمزامنة الوصول.

## ما هو java file output stream؟
`java.io.FileOutputStream` هو صفّ أساسي في Java يكتب البايتات الخام إلى ملف. إنه الخيار المثالي عندما تحتاج إلى حفظ محتوى ثنائي مثل مرفقات البريد الإلكتروني، الصور، أو أي بيانات غير نصية مستخرجة من مستند.

## لماذا نستخدم java file output stream مع GroupDocs.Viewer؟
- **معالجة مباشرة للبيانات الثنائية** – لا حاجة للتحويلات الوسيطة؛ يتم كتابة بايتات المرفق كما هي بالضبط في الملف الأصلي.  
- **الأداء** – الكتابة المتدفقة تقلل من استهلاك الذاكرة، خاصةً للمرفقات الكبيرة.  
- **البساطة** – تتكامل الواجهة البرمجية بسلاسة مع Java I/O القياسي، مما يجعل الشيفرة سهلة القراءة والصيانة.

## المتطلبات المسبقة
- **المكتبات والاعتمادات المطلوبة**: أضف مكتبة GroupDocs.Viewer إلى مشروعك (انظر مقتطف Maven أدناه).  
- **إعداد البيئة**: بيئة تطوير Java (IntelliJ IDEA، Eclipse، إلخ) مع JDK 8+ مثبت.  
- **المتطلبات المعرفية**: الإلمام بـ Java I/O، خاصةً `FileOutputStream`، واستخدام Maven الأساسي.

## إعداد GroupDocs.Viewer للـ Java
لبدء استخدام GroupDocs.Viewer API في مشروعك، تحتاج إلى تثبيته عبر Maven. أضف التكوين التالي إلى ملف `pom.xml` الخاص بك:

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

### التهيئة الأساسية والإعداد
بمجرد إضافة GroupDocs.Viewer كاعتماد في مشروعك، قم بتهيئته في تطبيق Java الخاص بك. إليك الطريقة:

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

هذه الإعدادات الأساسية تُهيئ GroupDocs.Viewer وتجهزه لاسترجاع المرفقات.

## دليل التنفيذ

### استرجاع المرفقات باستخدام java file output stream
دعنا نفصل كيفية استرجاع المرفقات باستخدام GroupDocs.Viewer. تتيح لك هذه الميزة استخراج بيانات الميتا لكل مرفق موجود في مستندك.

#### نظرة عامة
استرجاع المرفقات يتضمن الوصول إلى طريقة `getAttachments`، التي تُعيد قائمة من كائنات ` **إنشاء كائن Viewer**  
 مع مسار المستند الخاص بك:

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

3. **فهم المعاملات والطرق**  
   - `Viewer`: يأخذ مسار ملف أو تدفق إلى المستند.  
   - `getAttachments()`: تُسترجع قائمة بالملفات المرفقة، وتوفر تفاصيل مثل الأسماء.

### حفظ مرفقات المستند إلى دليل
الآن بعد أن تعلمت كيفية استرجاع المرفقات، لنقم بحفظها إلى الدليل الذي ترغب به باستخدام GroupDocs.Viewer API و **java file output stream**.

#### نظرة عامة
تتضمن هذه الميزة حفظ كل ملف مرفق تم استرجاعه إلى دليل إخراج محدد.

#### خطوات التنفيذ
1. **تحديد دليل الإخراج**  
   قم بإعداد مسار `outputDirectory` حيث سيتم حفظ الملفات:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **حفظ المرفقات**  
   استخدم حلقة لحفظ كل مرفق باستخدام طريقة `saveAttachment`:

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

3. **شرح المعاملات والطرق**  
   - `saveAttachment`: يأخذ كائن `Attachment` وتدفق إخراج ملف لحفظ المرفق.  
   - `FileOutputStream`: يدير كتابة البيانات إلى الملفات باستخدام دلالات **java file output stream**.

### نصائح استكشاف الأخطاء وإصلاحها
- **الاعتمادات المفقودة**: تأكد من إضافة جميع اعتمادات Maven بشكل صحيح.  
- **أخطاء مسار الملف**: تحقق مرة أخرى من المسارات لكل من المستندات وأدلة الإخراج.  
- **أذونات الوصول**: تحقق من أن تطبيقك يمتلك أذونات القراءة/الكتابة اللازمة.

## التطبيقات العملية
استخدام GroupDocs.Viewer في Java يمكن أن يكون ذا قيمة عالية عبر سيناريوهات متعددة:

1. **عملاء البريد الإلكتروني** – استخراج المرفقات تلقائيًا من أرشيف البريد الإلكتروني للمعالجة أو الأرشفة.  
2. **أنظمة إدارة المستندات** – تحسين DMS عبر استرجاع وتنظيم الملفات المرفقة.  
3. **الأقسام القانونية** – استخراج المرفقات المتعلقة بالأدلة من المستندات القانونية بأمان.

إمكانيات التكامل مع CRM، ERP، أو محركات سير العمل المخصصة يمكن أن تُسهل عمليات الأعمال أكثر، مما يجعل معالجة المرفقات سلسة عبر الأقسام.

## اعتبارات الأداء
لتحسين الأداء عند استخدام GroupDocs.Viewer:

-دم تدفقات مؤقتة للملفات الكبيرة وأغلق الموارد فورًا.  
- **إدارة الذاكرة** – حرّر كائنات `Viewer` بسرعة (try‑with‑resources) لتجنب تسقات.

## الخلاصة output stream** مع GroupDocs.View إدارة بيانات المستند، مما يجعلها أداة أساسية للمطورين الذين يعملون مع المستندات الرقمية.

لتوسيع استكشافك لقدرات GroupDocs.Viewer، جرّب ميزاته الأخرى—مثل عرض الصفحات، تحويل الصيغ، أو استخراج النص. إذا كان لديك أسئلة أو تحتاج إلى دعم، لا تتسer في مشروع Java الخاص بي؟**  
ج: أضف اعتماد Maven المعروض سابقًا؛ عنوان المستودع والإصدار هما كل ما تحتاجه للبدء السريع.

**س: هل يستطيع GroupDocs.Viewer معالجة جميع أنواع المستندات؟**  
ج: يدعم مجموعة واسعة من الصيغ (PDF، DOCX، MSG، إل إذا واجهت أخ مسار الإخراج، وجود الدليل،.

**س: هل يلزم وجود ترخيص للاستخدام في بيئة الإنتاج؟**  
ج: نعم، يلزم وجود ترخيص GroupDocs.Viewer صالح للنشر في بيئات الإنتاج. تتوفر نسخة تجريبية مجانية للتقييم.

**س: هل/O مؤقت يضمن معالجة فعّالة للملفات الثنائية الكبيرة. راقب استهلاك الذاكرة وفكّر في التدفق على أجزاء إذا لزم الأمر.

---

**آخر تحديث:** 2026-02-02  
**تم الاختبار مع:** GroupDocs