---
date: '2026-01-10'
description: تعلم كيفية تحويل ملفات EML إلى HTML مع تنسيق تاريخ ووقت مخصص وتعيين إزاحة
  المنطقة الزمنية في Java باستخدام GroupDocs.Viewer. مثالي لأرشفة البريد الإلكتروني
  وأنظمة الدعم.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: تحويل ملفات EML إلى HTML مع تاريخ ووقت مخصص في Java باستخدام GroupDocs.Viewer
type: docs
url: /ar/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# تحويل EML إلى HTML مع تاريخ ووقت مخصص في Java باستخدام GroupDocs.Viewer

## المقدمة

في عالمنا الرقمي السريع اليوم، القدرة على **تحويل EML إلى HTML** بسرعة وبصيغة تاريخ‑وقت صحيحة أمر أساسي للأرشفة، وبوابات الدعم، والامتثال القانوني. يشرح هذا الدليل كيفية عرض رسائل البريد الإلكتروني كملفات HTML مع تطبيق **صيغة تاريخ ووقت مخصصة** و**إزاحة المنطقة الزمنية** باستخدام GroupDocs.Viewer للـ Java. في النهاية، ستحصل على حل قابل لإعادة الاستخدام يحافظ على دقة وسهولة قراءة الطوابع الزمنية.

![عرض رسائل البريد الإلكتروني مع تاريخ ووقت مخصص باستخدام GroupDocs.Viewer للـ Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**ما ستتعلمه**
- كيفية إعداد GroupDocs.Viewer في مشروع Java  
- كيفية عرض رسائل البريد الإلكتروني كملفات HTML مع الموارد المضمنة  
- كيفية **تخصيص صيغة التاريخ‑الوقت** لرسائل البريد الإلكتروني الخاصة بك (custom datetime format java)  
- كيفية **تعيين إزاحة المنطقة الزمنية** للحصول على طوابع زمنية صحيحة (set timezone offset java)  

## إجابات سريعة
- **هل يمكن لـ GroupDocs.Viewer تحويل EML إلى HTML؟** نعم، يقوم بتحويل ملفات EML مباشرة إلى HTML.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للاختبار؛ يلزم الحصول على ترخيص مدفوع للإنتاج.  
- **ما نسخة Java المطلوبة؟** Java 8 أو أحدث.  
- **كيف أغيّر صيغة التاريخ المعروضة؟** استخدم `options.getEmailOptions().setDateTimeFormat(...)`.  
- **هل يمكنني تعديل المنطقة الزمنية؟** نعم، باستخدام `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.

## ما هو “تحويل EML إلى HTML”؟
تحويل ملف EML إلى HTML يُحوِّل البريد الإلكتروني الخام (بما في ذلك الرؤوس، والمحتوى، والمرفقات) إلى صيغة صديقة للويب يمكن للمتصفحات عرضها دون إضافات. هذا يجعل من السهل تضمين رسائل البريد في تطبيقات الويب، أو الأرشيفات، أو لوحات الدعم.

## لماذا نستخدم GroupDocs.Viewer لهذه المهمة؟
- **عرض بدون تبعيات** – لا حاجة إلى Outlook أو محللات بريد خارجية.  
- **دعم مدمج للموارد المضمنة** (الصور، المرفقات).  
- **تحكم دقيق** في صيغة التاريخ‑الوقت ومعالجة المنطقة الزمنية.  

## المتطلبات المسبقة

- **GroupDocs.Viewer للـ Java** الإصدار 25.2 أو أحدث.  
- **مجموعة تطوير Java (JDK)** 8+ وبيئة تطوير متكاملة (IntelliJ IDEA، Eclipse، إلخ).  
- معرفة أساسية بـ Java وإلمام بـ Maven.

## إعداد GroupDocs.Viewer للـ Java

### تكوين Maven
أضف مستودع GroupDocs والاعتماد إلى ملف `pom.xml` الخاص بك:

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
ابدأ بنسخة تجريبية مجانية أو اطلب ترخيصًا مؤقتًا للاختبار الموسع. اشترِ ترخيصًا كاملًا للاستخدام في الإنتاج.

### التهيئة الأساسية
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## تحويل EML إلى HTML مع تاريخ ووقت مخصص في Java

الدليل التالي يوضح خطوة بخطوة كيفية **تحويل EML إلى HTML** مع تطبيق صيغة تاريخ‑وقت مخصصة وإزاحة المنطقة الزمنية.

### الخطوة 1: إعداد دليل الإخراج ومسار الملف
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*شرح:* `Path.of()` ينشئ إشارة إلى المجلد الذي سيُحفظ فيه ملف HTML. `resolve()` يضيف اسم الملف.

### الخطوة 2: تهيئة Viewer بملف البريد الإلكتروني
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*شرح:* كائن `Viewer` يشير إلى ملف EML الذي تريد تحويله.

### الخطوة 3: تكوين HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*شرح:* `forEmbeddedResources()` يدمج الصور والموارد الأخرى مباشرةً في مخرجات HTML.

### الخطوة 4: تعيين صيغة تاريخ‑وقت مخصصة *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*شرح:* هذا النمط يعرض الشهر، اليوم، السنة، الساعة، الدقيقة، علامة ص/م، وإزاحة المنطقة الزمنية (`zzz`).

### الخطوة 5: تعيين إزاحة المنطقة الزمنية *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*شرح:* يضبط الطوابع الزمنية المعروضة إلى المنطقة الزمنية المطلوبة. استبدل `"GMT+1"` بأي معرف منطقة صالح.

### الخطوة 6: عرض المستند
```java
viewer.view(options);
```
*شرح:* ينفّذ التحويل، وينتج ملف HTML بإعدادات التاريخ‑الوقت المخصصة.

## نصائح استكشاف الأخطاء وإصلاحها
- **FileNotFoundException:** تحقق مرة أخرى من المسارات المستخدمة في `Viewer` و `Path.of()`.  
- **طوابع زمنية غير صحيحة:** تأكد من أن معرف `TimeZone` يطابق المنطقة المستهدفة.  
- **الصور مفقودة:** تأكد من استخدام `HtmlViewOptions.forEmbeddedResources()`؛ وإلا قد لا تُضمّن الموارد الخارجية.

## تطبيقات عملية
1. **أرشفة البريد الإلكتروني:** حفظ لقطات HTML قابلة للبحث للرسائل للامتثال.  
2. **بوابات دعم العملاء:** عرض التذاكر الواردة بأوقات محلية دقيقة.  
3. **توثيق قانوني:** إنتاج سجلات بريد إلكتروني جاهزة للمحكمة مع طوابع زمنية موحدة.

## اعتبارات الأداء
- انشر على خادم مخصص للتحويلات الضخمة.  
- راقب استهلاك الذاكرة في Java؛ زد قيمة `-Xmx` إذا واجهت `OutOfMemoryError`.  
- خزن HTML المُحوَّل مؤقتًا عندما يُطلب نفس البريد الإلكتروني بشكل متكرر.

## الخاتمة
أصبح لديك الآن طريقة كاملة وجاهزة للإنتاج **لتحويل EML إلى HTML** مع صيغة تاريخ‑وقت مخصصة وإزاحة المنطقة الزمنية باستخدام GroupDocs.Viewer للـ Java. هذا يحسّن القابلية للقراءة، يضمن دقة الطوابع الزمنية، ويتكامل بسلاسة مع عمليات الأرشفة أو الدعم.

**الخطوات التالية:** استكشف خيارات Viewer إضافية مثل تنسيق CSS، التقسيم إلى صفحات، أو التحويل إلى PDF لتخصيص المخرجات وفق احتياجاتك.

## الأسئلة المتكررة

**س: كيف أتعامل مع ملفات EML التي تحتوي على مرفقات؟**  
ج: تُدمج المرفقات تلقائيًا عند استخدام `HtmlViewOptions.forEmbeddedResources()`. يمكنك أيضًا استخراجها عبر API الخاص بـ Viewer إذا لزم الأمر.

**س: هل يمكنني تغيير قالب HTML أو إضافة CSS مخصص؟**  
ج: نعم، بعد التحويل يمكنك تعديل ملف HTML المُولد أو حقن CSS برمجيًا قبل الحفظ.

**س: هل يمكنني عرض عدة ملفات EML دفعة واحدة؟**  
ج: ضع منطق التحويل داخل حلقة وأعد استخدام نفس كائن `HtmlViewOptions` لكل ملف.

**س: ماذا إذا احتجت لدعم صيغ بريد إلكتروني أخرى مثل MSG؟**  
ج: يدعم GroupDocs.Viewer أيضًا MSG، PST، وغيرها من حاويات البريد—فقط غير امتداد الملف في مُنشئ `Viewer`.

**س: هل أحتاج إلى ترخيص منفصل لكل خادم؟**  
ج: الترخيص يكون حسب النشر؛ راجع دليل ترخيص GroupDocs لسيناريوهات الخوادم المتعددة.

## موارد

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-01-10  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 (Java)  
**المؤلف:** GroupDocs  

---