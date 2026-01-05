---
date: '2026-01-05'
description: تعلم كيفية إعادة تسمية حقول البريد الإلكتروني، وتحويل البريد الإلكتروني
  إلى HTML، وتخصيص رؤوس البريد الإلكتروني باستخدام GroupDocs.Viewer للغة Java.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: كيفية إعادة تسمية حقول البريد الإلكتروني عند تحويل الرسائل إلى HTML باستخدام
  GroupDocs.Viewer Java
type: docs
url: /ar/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# كيفية إعادة تسمية حقول البريد الإلكتروني عند عرض رسائل البريد إلى HTML باستخدام GroupDocs.Viewer Java

هل تتساءل **كيف تعيد تسمية حقول البريد الإلكتروني** أثناء تحويل بريد إلكتروني إلى HTML؟ في هذا الدليل سنستعرض الخطوات الدقيقة لإعادة تسمية حقول البريد الإلكتروني، **تحويل البريد الإلكتروني إلى HTML**، و**تخصيص رؤوس البريد الإلكتروني** باستخدام GroupDocs.Viewer للغة Java. في النهاية ستحصل على تمثيل HTML نظيف بأسماء رؤوس مفضلة لديك، مما يجعل المخرجات أسهل في القراءة والتكامل مع تطبيقاتك.

![إعادة تسمية حقول البريد الإلكتروني عند تحويل رسائل البريد إلى HTML باستخدام GroupDocs.Viewer للغة Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### ما ستتعلمه
- كيفية استخدام GroupDocs.Viewer للغة Java **لتحويل البريد الإلكتروني إلى HTML**.  
- تقنيات **إعادة تسمية حقول البريد الإلكتروني** مثل “From”، “To”، “Sent”، و “Subject”.  
- أفضل الممارسات لإعداد Maven والترخيص.  
- سيناريوهات واقعية حيث **تخصيص رؤوس البريد الإلكتروني** يضيف قيمة.

## إجابات سريعة
- **ماذا يعني “how to rename email”؟** يشير إلى ربط أسماء رؤوس البريد الإلكتروني الافتراضية بتسميات مخصصة أثناء العرض.  
- **أي مكتبة تتعامل مع التحويل؟** GroupDocs.Viewer للغة Java (v25.2+).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني تغيير أي اسم رأس؟** نعم، يمكن إعادة تعيين أي رأس بريد إلكتروني قياسي عبر `fieldTextMap`.  
- **هل المخرجات HTML أم موارد مدمجة؟** يمكنك اختيار الموارد المدمجة للحصول على ملف واحد مستقل.

## ما هو “How to Rename Email” في سياق GroupDocs.Viewer؟
إعادة تسمية حقول البريد الإلكتروني تعني استبدال التسميات الافتراضية (مثل “From”) بنص مخصص (مثل “Sender”) عند عرض البريد الإلكتروني إلى HTML. هذا مفيد لتوافق المخرجات مع المصطلحات المؤسسية أو تحسين قابلية القراءة للمستخدم النهائي.

## لماذا تحويل البريد الإلكتروني إلى HTML وتخصيص رؤوس البريد الإلكتروني؟
- **العلامة التجارية المتسقة:** مطابقة لغة مؤسستك عبر جميع الاتصالات.  
- **تحسين قابلية البحث:** يمكن فهرسة الرؤوس المخصصة بشكل أكثر فعالية في أنظمة الأرشفة.  
- **تكامل واجهة المستخدم الأفضل:** تخصيص مقطع HTML ليتناسب بسلاسة مع البوابات الإلكترونية أو لوحات الدعم.

## المتطلبات المسبقة

### المكتبات المطلوبة والإصدارات والاعتمادات
- **GroupDocs.Viewer للغة Java** – الإصدار 25.2 أو أحدث.  
- **مجموعة تطوير جافا (JDK)** – الإصدار 8+.

### متطلبات إعداد البيئة
- **Maven** لإدارة الاعتمادات.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse أو VS Code.

### المتطلبات المعرفية
سيساعدك الإلمام الأساسي بـ Java و Maven على المتابعة بسرعة.

## إعداد GroupDocs.Viewer للغة Java

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
- **نسخة تجريبية مجانية:** تحميل نسخة تجريبية مجانية من [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **ترخيص مؤقت:** الحصول على ترخيص مؤقت لاستكشاف جميع الميزات دون قيود عبر [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **شراء:** للاستخدام المستمر، فكر في شراء ترخيص عبر [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

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

## دليل التنفيذ

### إعادة تسمية حقول البريد الإلكتروني – خطوة بخطوة

#### 1. إعداد مسار دليل الإخراج
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*استبدل `"YOUR_OUTPUT_DIRECTORY"` بالمجلد الذي تريد حفظ ملفات HTML فيه.*

#### 2. تعريف تنسيق مسار ملف الصفحة
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*سيتم استبدال `{0}` برقم الصفحة أثناء العرض.*

#### 3. إنشاء خريطة لحقول البريد الإلكتروني إلى أسماء جديدة
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

#### 4. تكوين خيارات عرض HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` يجمع ملفات CSS/JS داخل HTML، بينما `setFieldTextMap` يطبق أسماء الرؤوس المخصصة.*

#### 5. عرض البريد الإلكتروني إلى HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*استبدل `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` بالمسار الفعلي لملف MSG الخاص بك.*

#### نصائح استكشاف الأخطاء وإصلاحها
- تحقق من أن دليل الإخراج قابل للكتابة.  
- تأكد من وجود ملف MSG المدخل والمسار صحيح.  
- استخدم نفس إصدار GroupDocs.Viewer (25.2) كما هو مُعلن في Maven.

## التطبيقات العملية
1. **تقارير بريد إلكتروني مخصصة:** مواءمة رؤوس البريد الإلكتروني مع المصطلحات المؤسسية لتقارير أوضح.  
2. **أنظمة أرشفة البريد الإلكتروني:** تحسين قابلية البحث باستخدام أسماء رؤوس موحدة.  
3. **منصات دعم العملاء:** عرض التذاكر بتسميات رؤوس مخصصة لتجربة أفضل للوكيل.

## اعتبارات الأداء
- تخلص من كائنات `Viewer` باستخدام try‑with‑resources لتحرير الذاكرة بسرعة.  
- قم بملف تعريف الدفعات الكبيرة وفكر في معالجة الرسائل الإلكترونية عبر تدفقات متوازية إذا لزم الأمر.

## الخاتمة
أنت الآن تعرف **كيفية إعادة تسمية حقول البريد الإلكتروني** أثناء **تحويل البريد الإلكتروني إلى HTML** و**تخصيص رؤوس البريد الإلكتروني** باستخدام GroupDocs.Viewer للغة Java. تمنحك هذه التقنية التحكم الكامل في عرض بيانات تعريف البريد الإلكتروني في مخرجات HTML.

### الخطوات التالية
- جرّب خريطة حقول إضافية (مثل CC، BCC).  
- استكشف صيغ عرض أخرى مثل PDF أو PNG.  
- زر [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) للحصول على رؤى أعمق حول API.

## قسم الأسئلة المتكررة
1. **هل يمكنني إعادة تسمية جميع رؤوس البريد الإلكتروني باستخدام هذه الطريقة؟**  
   - نعم، يمكنك ربط أي رأس بريد إلكتروني قياسي باسم جديد وفقًا لمتطلباتك.  
2. **هل يمكن استخدام GroupDocs.Viewer بدون ترخيص؟**  
   - تتوفر نسخة تجريبية للاختبار، لكن النسخة الكاملة تتطلب ترخيصًا صالحًا.  
3. **كيف يمكنني التعامل مع حجم كبير من الرسائل الإلكترونية بكفاءة باستخدام GroupDocs.Viewer؟**  
   - فكر في المعالجة الدفعية وتحسين موارد النظام لإدارة مجموعات بيانات أكبر بفعالية.  
4. **هل يمكن دمج هذا الحل في تطبيق Java موجود؟**  
   - بالتأكيد، التكامل سهل باستخدام اعتمادات Maven.  
5. **أين يمكنني العثور على الدعم إذا واجهت مشاكل؟**  
   - زر [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) للمجتمع والمساعدة الرسمية.

## الأسئلة المتكررة
**س: هل يعمل هذا النهج مع صيغ بريد إلكتروني أخرى مثل EML؟**  
ج: نعم، يدعم GroupDocs.Viewer كل من ملفات MSG و EML؛ نفس منطق ربط الحقول ينطبق.

**س: هل يمكنني إخراج HTML بدون موارد مدمجة؟**  
ج: يمكنك استخدام `HtmlViewOptions.forExternalResources(...)` إذا كنت تفضل ملفات CSS/JS منفصلة.

**س: ما هو إصدار GroupDocs.Viewer الذي تم اختباره؟**  
ج: تم اختبار الكود مع GroupDocs.Viewer **25.2**.

**س: هل يمكن تغيير الخط أو نمط الرؤوس المخصصة؟**  
ج: يمكن تطبيق التنسيق عبر CSS بعد العرض، أو يمكنك حقن CSS مخصص باستخدام `HtmlViewOptions.getResourcesPath()`.

**س: كيف يمكنني استرجاع مسار ملف HTML المُولد برمجيًا؟**  
ج: يتبع مسار الملف النمط المحدد في `pageFilePathFormat`؛ يمكنك بناؤه باستخدام `String.format` مع رقم الصفحة.

## الموارد
- **التوثيق:** أدلة شاملة متاحة على [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **مرجع API:** يمكن العثور على معلومات مفصلة حول API على [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **تحميل GroupDocs.Viewer:** احصل على أحدث إصدار عبر [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**آخر تحديث:** 2026-01-05  
**تم الاختبار مع:** GroupDocs.Viewer 25.2  
**المؤلف:** GroupDocs  

---