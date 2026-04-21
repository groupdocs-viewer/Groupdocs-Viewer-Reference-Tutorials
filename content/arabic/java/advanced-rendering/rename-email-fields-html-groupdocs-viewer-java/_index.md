---
date: '2026-03-24'
description: تعلم كيفية تحويل البريد الإلكتروني إلى HTML وإعادة تسمية حقول البريد
  الإلكتروني باستخدام GroupDocs Viewer for Java. يوضح هذا الدليل طريقة عرض البريد
  الإلكتروني كـ HTML مع رؤوس مخصصة.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: تحويل البريد الإلكتروني إلى HTML وإعادة تسمية الحقول – GroupDocs Viewer Java
type: docs
url: /ar/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# تحويل البريد الإلكتروني إلى HTML وإعادة تسمية الحقول – GroupDocs Viewer Java

إذا كنت بحاجة إلى **convert email to HTML** مع إعطاء رؤوس البريد الإلكتروني مظهرًا مخصصًا، فأنت في المكان الصحيح. في هذا الدرس سنستعرض الخطوات الدقيقة لإعادة تسمية حقول البريد الإلكتروني، **convert email to HTML**، وتخصيص رؤوس البريد باستخدام GroupDocs.Viewer for Java. في النهاية ستحصل على تمثيل HTML نظيف بأسماء الرؤوس التي تفضلها، مما يجعل المخرجات أسهل للقراءة والتكامل مع تطبيقاتك.

![إعادة تسمية حقول البريد الإلكتروني عند تحويل الرسائل إلى HTML باستخدام GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### ما ستتعلمه
- كيفية استخدام GroupDocs.Viewer for Java لـ **convert email to HTML**.  
- تقنيات **rename email fields** مثل “From”، “To”، “Sent”، و “Subject”.  
- أفضل الممارسات لإعداد Maven والترخيص.  
- سيناريوهات واقعية حيث **customizing email headers** تضيف قيمة.

## إجابات سريعة
- **ما معنى “convert email to HTML”؟** يعني ذلك تحويل ملف بريد إلكتروني (MSG/EML) إلى مستند HTML جاهز للويب.  
- **ما المكتبة التي تتعامل مع التحويل؟** GroupDocs.Viewer for Java (v25.2+).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني تغيير أي اسم رأس؟** نعم، يمكن إعادة تعيين أي رأس بريد إلكتروني قياسي عبر `fieldTextMap`.  
- **هل المخرجات HTML أم موارد مدمجة؟** يمكنك اختيار الموارد المدمجة للحصول على ملف واحد مكتمل.

## ما هو “convert email to HTML” في سياق GroupDocs.Viewer؟
يعني تحويل البريد الإلكتروني إلى HTML أخذ ملف بريد إلكتروني خام وإنتاج صفحة HTML تعرض نص الرسالة مع بيانات التعريف الخاصة به. عندما تقوم أيضًا **rename email fields**، يتم استبدال التسميات الافتراضية (مثل “From”) بنص مخصص (مثل “Sender”)، مما يساعدك على مطابقة المصطلحات المؤسسية أو تحسين اتساق واجهة المستخدم.

## لماذا تحويل البريد الإلكتروني إلى HTML وإعادة تسمية حقول البريد؟
- **Consistent branding:** مواءمة المخرجات مع لغة مؤسستك.  
- **Improved searchability:** يمكن فهرسة الرؤوس المخصصة بفعالية أكبر في أنظمة الأرشفة.  
- **Better UI integration:** تخصيص مقتطف HTML ليتناسب بسلاسة مع البوابات الإلكترونية أو لوحات الدعم.

## المتطلبات المسبقة

### المكتبات المطلوبة، الإصدارات، والاعتماديات
- **GroupDocs.Viewer for Java** – الإصدار 25.2 أو أحدث.  
- **Java Development Kit (JDK)** – الإصدار 8+.

### متطلبات إعداد البيئة
- **Maven** لإدارة الاعتماديات.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse أو VS Code.

### متطلبات المعرفة
سيساعدك الإلمام الأساسي بـ Java و Maven على المتابعة بسرعة.

## إعداد GroupDocs.Viewer for Java

### تكوين Maven
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

### خطوات الحصول على الترخيص
- **Free Trial:** تحميل نسخة تجريبية مجانية من [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Temporary License:** الحصول على ترخيص مؤقت لاستكشاف جميع الميزات دون قيود عبر [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase:** للاستخدام المستمر، فكر في شراء ترخيص عبر [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### التهيئة الأساسية والإعداد
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
قم بتعديل مسار الملف للإشارة إلى ملف `.msg` الخاص بك.

## كيفية تحويل البريد الإلكتروني إلى HTML وإعادة تسمية الحقول – خطوة بخطوة

### 1. إعداد مسار دليل الإخراج
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*استبدل `"YOUR_OUTPUT_DIRECTORY"` بالمجلد الذي تريد حفظ ملفات HTML فيه.*

### 2. تعريف تنسيق مسار ملف الصفحة
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` سيُستبدل برقم الصفحة أثناء العرض.*

### 3. إنشاء خريطة لحقول البريد الإلكتروني إلى أسماء جديدة
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*هنا نقوم بتغيير التسميات الافتراضية إلى تسميات مخصصة.*

### 4. تكوين خيارات عرض HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` يجمع CSS/JS داخل HTML، بينما `setFieldTextMap` يطبق أسماء الرؤوس المخصصة.*

### 5. تحويل البريد الإلكتروني إلى HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*استبدل `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` بالمسار الفعلي لملف MSG الخاص بك.*

#### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من أن دليل الإخراج قابل للكتابة.  
- تحقق من وجود ملف MSG المدخل وأن المسار صحيح.  
- استخدم نفس إصدار GroupDocs.Viewer (25.2) كما هو مُعلن في Maven.

## التطبيقات العملية
1. **Custom Email Reports:** مواءمة رؤوس البريد مع المصطلحات المؤسسية لتقارير أوضح.  
2. **Email Archiving Systems:** تحسين قابلية البحث باستخدام أسماء رؤوس موحدة.  
3. **Customer Support Platforms:** عرض التذاكر برؤوس مخصصة لتجربة أفضل للوكيل.

## اعتبارات الأداء
- تخلص من كائنات `Viewer` باستخدام try‑with‑resources لتحرير الذاكرة بسرعة.  
- قم بملف الأداء للدفعات الكبيرة وفكّر في معالجة الرسائل عبر تدفقات متوازية إذا لزم الأمر.

## الخلاصة
أنت الآن تعرف **كيفية تحويل البريد الإلكتروني إلى HTML** مع **إعادة تسمية حقول البريد** و**تخصيص رؤوس البريد** باستخدام GroupDocs.Viewer for Java. تمنحك هذه التقنية تحكمًا كاملاً في عرض بيانات تعريف البريد في مخرجات HTML.

### الخطوات التالية
- جرّب خريطة حقول إضافية (مثل CC، BCC).  
- استكشف صيغ عرض أخرى مثل PDF أو PNG.  
- زر [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) للحصول على رؤى أعمق حول API.

## الأسئلة المتكررة

**س: هل يعمل هذا النهج مع صيغ بريد إلكتروني أخرى مثل EML؟**  
ج: نعم، يدعم GroupDocs.Viewer كلًا من ملفات MSG و EML؛ نفس منطق تعيين الحقول ينطبق.

**س: هل يمكنني إخراج HTML دون موارد مدمجة؟**  
ج: يمكنك استخدام `HtmlViewOptions.forExternalResources(...)` إذا كنت تفضّل ملفات CSS/JS منفصلة.

**س: ما الإصدار الذي تم اختبار GroupDocs.Viewer عليه؟**  
ج: تم اختبار الكود مع GroupDocs.Viewer **25.2**.

**س: هل يمكن تغيير الخط أو نمط الرؤوس المخصصة؟**  
ج: يمكن تطبيق الأنماط عبر CSS بعد العرض، أو يمكنك حقن CSS مخصص باستخدام `HtmlViewOptions.getResourcesPath()`.

**س: كيف يمكنني برمجيًا استرجاع مسار ملف HTML المُولد؟**  
ج: يتبع مسار الملف النمط المحدد في `pageFilePathFormat`؛ يمكنك بناؤه باستخدام `String.format` مع رقم الصفحة.

## الموارد
- **Documentation:** أدلة شاملة متوفرة على [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** معلومات تفصيلية عن API يمكن العثور عليها في [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Download GroupDocs.Viewer:** احصل على أحدث إصدار عبر [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**آخر تحديث:** 2026-03-24  
**تم الاختبار مع:** GroupDocs.Viewer 25.2  
**المؤلف:** GroupDocs