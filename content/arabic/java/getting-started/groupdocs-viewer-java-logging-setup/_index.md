---
date: '2026-04-10'
description: تعلم كيفية تكوين التسجيل في GroupDocs.Viewer للغة Java، بما في ذلك كيفية
  إضافة مسجل وحدة التحكم ومسجل الملفات لتحسين عرض المستندات.
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: كيفية تكوين التسجيل في GroupDocs.Viewer لجافا
type: docs
url: /ar/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# كيفية تكوين التسجيل في GroupDocs.Viewer for Java

في هذا البرنامج التعليمي، ستتعلم **كيفية تكوين التسجيل** في GroupDocs.Viewer for Java، والذي يمنحك نظرة فورية على خط أنابيب عرض المستندات ويساعدك على استكشاف المشكلات بسرعة.

## الإجابات السريعة
- **ماذا يوفر التسجيل؟** رد فعل فوري على عمليات العرض وتفاصيل الأخطاء.  
- **أي مسجل يطبع إلى وحدة التحكم؟** `ConsoleLogger` (إضافة مسجل وحدة التحكم).  
- **أي مسجل يكتب إلى ملف؟** `FileLogger` (إضافة مسجل ملف).  
- **هل أحتاج إلى ترخيص لتفعيل التسجيل؟** لا، يعمل التسجيل مع كل من النسخ التجريبية والمرخصة.  
- **هل يمكنني تخصيص تنسيق السجل؟** نعم، عن طريق توسيع فئات المسجل.

## مقدمة
حسّن عملية عرض المستندات في تطبيقات Java باستخدام **GroupDocs.Viewer for Java**. يشرح هذا الدليل كيفية تكوين التسجيل إما إلى وحدة التحكم أو إلى ملف، مما يوفر رؤى حيوية حول كيفية عمل عرض المستندات.

![تسجيل وحدة التحكم والملف باستخدام GroupDocs.Viewer for Java](/viewer/getting-started/console-and-file-logging-java.png)

**نقاط التعلم الرئيسية:**
- تكوين التسجيل في GroupDocs.Viewer for Java.  
- تنفيذ أنظمة تسجيل تعتمد على وحدة التحكم والملف.  
- عرض المستندات إلى HTML مع موارد مدمجة باستخدام GroupDocs.Viewer.

## المتطلبات المسبقة
تأكد من وجود ما يلي:
1. **المكتبات المطلوبة:**  
   - مكتبة GroupDocs.Viewer for Java (الإصدار 25.2 أو أحدث).  

2. **متطلبات إعداد البيئة:**  
   - مجموعة تطوير جافا (JDK) مثبتة على نظامك.  
   - بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.  

3. **المتطلبات المعرفية:**  
   - فهم أساسي لبرمجة Java.  
   - إلمام بـ Maven لإدارة التبعيات.  

مع توفر هذه المتطلبات، أنت جاهز لإعداد GroupDocs.Viewer for Java!

## إعداد GroupDocs.Viewer for Java
لاستخدام GroupDocs.Viewer، أضفه كاعتماد في مشروعك باستخدام Maven. إليك الطريقة:

### إعداد Maven
أضف التكوين التالي في ملف `pom.xml` الخاص بك:
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
- **نسخة تجريبية مجانية:** قم بتنزيل نسخة تجريبية مجانية من [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **ترخيص مؤقت:** احصل على ترخيص مؤقت لإزالة قيود التقييم عبر [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **شراء:** للحصول على وصول كامل، فكر في شراء ترخيص عبر [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### التهيئة الأساسية
قم بتهيئة GroupDocs.Viewer بالنمط التالي:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

يشكل هذا الإعداد الأساس لتكوينات التسجيل الأكثر تعقيدًا.

## كيفية تكوين التسجيل
استكشف كيفية **إضافة مسجل وحدة التحكم** و **إضافة مسجل ملف** باستخدام GroupDocs.Viewer.

### الميزة 1: التسجيل إلى وحدة التحكم
#### نظرة عامة
يوفر التسجيل إلى وحدة التحكم رد فعل فوري في الطرفية الخاصة بك، وهو مفيد أثناء مراحل التطوير أو تصحيح الأخطاء.

#### الخطوات
##### الخطوة 1: استيراد الفئات المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### الخطوة 2: إعداد تكوين التسجيل
استخدم `ConsoleLogger` لتوجيه السجلات إلى وحدة التحكم.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**شرح**  
- **ConsoleLogger:** هذه الفئة توجه السجلات إلى وحدة التحكم، وتوفر عرضًا فوريًا للعمليات.  
- **HtmlViewOptions.forEmbeddedResources:** يولد HTML مع موارد مدمجة لكل صفحة، مثال على استخدام **html view options** بفعالية.

#### نصائح استكشاف الأخطاء وإصلاحها
تأكد من أن مسار المستند صحيح ويمكن الوصول إليه. تحقق من أن عبارات التسجيل مكوّنة بشكل مناسب في إعدادات وحدة التحكم.

### الميزة 2: التسجيل إلى ملف
#### نظرة عامة
يساعد التسجيل إلى ملف على الحفاظ على سجل دائم للعمليات، وهو مفيد للتدقيق أو التحليل بعد الحادث.

#### الخطوات
##### الخطوة 1: استيراد الفئات المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### الخطوة 2: إعداد تكوين التسجيل القائم على الملف
استخدم `FileLogger` لكتابة السجلات إلى ملف محدد.
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**شرح**  
- **FileLogger:** هذه الفئة توجه السجلات إلى ملف اسمه `output.log`.  
- **ViewerSettings with FileLogger:** يكوّن GroupDocs.Viewer ل**التقاط سجلات العارض** في ملف السجل المحدد.

#### نصائح استكشاف الأخطاء وإصلاحها
تأكد من أن الدليل الخاص بملف الإخراج قابل للكتابة. تحقق من أذونات الملف إذا فشل التسجيل.

## التطبيقات العملية
GroupDocs.Viewer يمكنه تعزيز إدارة المستندات وقدرات العرض:
1. **بوابات الويب:** عرض المستندات مباشرة للمستخدمين عبر الويب دون الحاجة إلى تنزيلها.  
2. **أنظمة المؤسسات:** دمج مع أدوات CRM لعرض العقود أو الاتفاقيات.  
3. **لوحات التحكم الداخلية:** توفير عروض قابلة للوصول للتقارير والعروض التقديمية داخل الشبكات الداخلية.

## اعتبارات الأداء وأفضل ممارسات تسجيل Java
عند استخدام GroupDocs.Viewer في Java، احرص على مراعاة النقاط التالية:
- **تحسين استخدام الموارد:** راقب استهلاك الذاكرة عند عرض مستندات كبيرة.  
- **إدارة ذاكرة Java:** استخدم try‑with‑resources للتنظيف التلقائي للموارد.  
- **تفصيل التسجيل:** اضبط مستويات المسجل (مثل INFO، DEBUG) لتحقيق توازن بين التفاصيل وتأثير الأداء—وهو جزء أساسي من **java logging best practices**.  

## الخلاصة
لقد تعلمت **كيفية تكوين التسجيل** في GroupDocs.Viewer for Java، سواء كنت تحتاج إلى عرض سريع في وحدة التحكم أو سجل ملف دائم. هذه القدرة لا تقدر بثمن لتصحيح الأخطاء، والمراقبة، وتدقيق تطبيقاتك. استكشف تكوينات إضافية، وجرب مسجلات مخصصة، ودمج GroupDocs.Viewer مع أنظمة أخرى لتعزيز المتانة.

هل أنت مستعد للارتقاء بمهارات التنفيذ إلى المستوى التالي؟ جرّب إعداد التسجيل في بيئات مختلفة ولاحظ كيف يعزز ذلك موثوقية تطبيقك!

## الموارد
- [التوثيق](https://docs.groupdocs.com/viewer/java/)
- [مرجع API](https://reference.groupdocs.com/viewer/java/)
- [تحميل](https://downloads.groupdocs.com/viewer/java/)

---

**آخر تحديث:** 2026-04-10  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs