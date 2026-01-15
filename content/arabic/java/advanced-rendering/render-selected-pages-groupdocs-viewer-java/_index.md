---
date: '2026-01-15'
description: تعلم كيفية عرض الصفحات وإنشاء HTML من مستند باستخدام GroupDocs.Viewer
  للغة Java. يغطي هذا الدليل الإعداد والتكوين والتكامل العملي.
keywords:
- render selected pages GroupDocs.Viewer Java
- GroupDocs Viewer for Java setup
- render HTML with embedded resources
title: كيفية عرض الصفحات باستخدام GroupDocs.Viewer لجافا
type: docs
url: /ar/java/advanced-rendering/render-selected-pages-groupdocs-viewer-java/
weight: 1
---

# كيفية عرض الصفحات باستخدام GroupDocs.Viewer للـ Java

عرض أقسام معينة فقط من مستند في تطبيق الويب الخاص بك قد يكون تحديًا. في هذا البرنامج التعليمي ستكتشف **كيفية عرض الصفحات** بكفاءة، وتحويلها إلى ملفات HTML ذاتية الاحتواء يمكن تضمينها مباشرةً في واجهة المستخدم الخاصة بك. سواء كنت تحتاج إلى إظهار مقتطف من عقد أو فصل واحد من كتاب دراسي، فإن الخطوات أدناه ستقودك عبر العملية الكاملة باستخدام GroupDocs.Viewer للـ Java.

هل أنت مستعد لتحسين تطبيقك؟ لنبدأ بالتأكد من أن إعدادك صحيح.

## إجابات سريعة
- **ما معنى “render pages”?** تحويل الصفحات المحددة من المستند إلى صيغة قابلة للعرض مثل HTML.  
- **ما الصيغة التي يتم إنشاؤها؟** HTML مع موارد مدمجة (صور، CSS، خطوط).  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية تعمل للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني اختيار صفحات غير متتالية؟** نعم – حدد أي أرقام صفحات تحتاجها.  
- **هل يُنصح باستخدام التخزين المؤقت؟** بالتأكيد، التخزين المؤقت للـ HTML المُعرض يقلل من زمن التحميل للصفحات التي تُستدعى بشكل متكرر.

![عرض الصفحات المحددة من مستند باستخدام GroupDocs.Viewer للـ Java](/viewer/advanced-rendering/render-selected-pages-of-a-document-java.png)

### ما ستتعلمه
- إعداد GroupDocs.Viewer في بيئة Java الخاصة بك  
- عرض صفحات مستند محددة باستخدام Viewer API  
- تكوين خيارات عرض HTML لعرض مثالي  
- حالات استخدام عملية وسيناريوهات التكامل  

## ما هو عرض الصفحات المحددة؟
يعني عرض الصفحات المحددة استخراج الصفحات التي تحددها فقط من مستند المصدر (DOCX، PDF، PPT، إلخ) وتحويلها إلى صيغة يمكن عرضها في متصفح الويب. يقلل هذا النهج من استهلاك النطاق الترددي، ويسرّع تحميل الصفحة، ويحسّن تجربة المستخدم النهائية من خلال إظهار المحتوى ذي الصلة فقط.

## لماذا يتم إنشاء HTML من مستند؟
إنشاء HTML من مستند يمنحك تمثيلًا خفيفًا وغير مرتبط بمنصة يعمل عبر المتصفحات دون الحاجة إلى عارضين خارجيين أو مكوّنات إضافية. تضمين الموارد مباشرةً داخل ملف HTML (صور، خطوط، CSS) يبسط عملية النشر ويقضي على مشاكل المصدر المتقاطع.

## المتطلبات المسبقة

تأكد من أن إعداد التطوير الخاص بك يلبي هذه المتطلبات:

1. **المكتبات المطلوبة** – تضمين GroupDocs.Viewer للـ Java (الإصدار 25.2 أو أحدث) في مشروعك.  
2. **البيئة** – JDK 8 أو أعلى؛ بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
3. **المعرفة** – برمجة Java أساسية وإدارة تبعيات Maven.  

## إعداد GroupDocs.Viewer للـ Java

### التثبيت عبر Maven

أضف المستودع والاعتماد إلى ملف `pom.xml` الخاص بك:

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
- **نسخة تجريبية مجانية** – استكشاف جميع الميزات دون تكلفة.  
- **ترخيص مؤقت** – تمديد الاختبار بعد فترة التجربة.  
- **شراء كامل** – مطلوب لتطبيقات الإنتاج.  

#### التهيئة الأساسية والإعداد

```java
import com.groupdocs.viewer.Viewer;

public class DocumentViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
            // Your rendering logic here
        }
    }
}
```

## دليل التنفيذ

### عرض صفحات محددة كـ HTML مع موارد مدمجة

#### الخطوة 1: تكوين مسار الإخراج

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

- **شرح**: `outputDirectory` هو المكان الذي سيتم حفظ ملفات HTML المُولدة فيه.  
- **التسمية**: `page_{0}.html` ينشئ ملفًا منفصلًا لكل صفحة مُعرضة.

#### الخطوة 2: إعداد خيارات عرض HTML

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

- **شرح**: `forEmbeddedResources()` يجمع الصور، CSS، والخطوط داخل كل ملف HTML مباشرةً، مما يلغي الاعتماديات الخارجية.

#### الخطوة 3: عرض الصفحات المطلوبة

```java
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    viewer.view(viewOptions, 1, 3);
}
```

- **شرح**: طريقة `view()` تستقبل `HtmlViewOptions` وقائمة بأرقام الصفحات. في هذا المثال، يتم عرض الصفحة الأولى والثالثة فقط.

### نصائح استكشاف الأخطاء وإصلاحها
- تحقق من أن مسار الإخراج موجود وأن التطبيق يمتلك صلاحيات الكتابة.  
- تأكد من صحة مسار المستند وأن الملف غير تالف.  
- إذا واجهت أخطاء ترخيص، تأكد من وضع ملف ترخيص صالح بجوار تطبيقك.

## تطبيقات عملية

عرض الصفحات المحددة مفيد في العديد من السيناريوهات:

1. **المستندات القانونية** – عرض الفقرات ذات الصلة فقط من العقد.  
2. **المنصات التعليمية** – السماح للطلاب بمعاينة فصول محددة دون تحميل الكتاب بالكامل.  
3. **تقارير الأعمال** – تقديم ملخصات مختصرة لأصحاب المصلحة عبر عرض أقسام التقرير الرئيسية.

## اعتبارات الأداء

- **إدارة الذاكرة** – استخدم try‑with‑resources (كما هو موضح) لتحرير موارد Viewer بسرعة.  
- **التخزين المؤقت** – احفظ HTML المُعرض في ذاكرة مؤقتة (مثل Redis أو في الذاكرة) للصفحات التي تُستدعى بشكل متكرر.  
- **تقليل الموارد** – الموارد المدمجة تزيد حجم الملف قليلًا؛ فكر في ضغط مخرجات HTML إذا كان عرض النطاق الترددي مصدر قلق.

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **الملف غير موجود** | تحقق مرة أخرى من المسار المطلق/النسبي وتأكد من وجود الملف. |
| **نفاد الذاكرة للوثائق الكبيرة** | اعرض الصفحات المطلوبة فقط، أو زد حجم الذاكرة المخصصة للـ JVM (`-Xmx`). |
| **الصور مفقودة في HTML** | تحقق من استخدام `forEmbeddedResources`؛ وإلا سيتم حفظ الصور بشكل منفصل. |
| **خطأ في الترخيص** | ضع ملف `GroupDocs.Viewer.lic` صالح في جذر التطبيق أو حدد مساره برمجياً. |

## الأسئلة المتكررة

1. **ما هو GroupDocs.Viewer للـ Java؟**  
   مكتبة تمكّن من عرض أكثر من 90 تنسيق مستند (PDF، DOCX، PPT، إلخ) مباشرةً داخل تطبيقات Java.

2. **هل يمكنني عرض صفحات PDF باستخدام هذه الطريقة؟**  
   نعم – يدعم Viewer API ملفات PDF إلى جانب العديد من الصيغ الأخرى.

3. **كيف يمكنني التعامل مع المستندات الكبيرة بكفاءة؟**  
   اعرض الصفحات التي تحتاجها فقط واستخدم التخزين المؤقت لتجنب المعالجة المتكررة.

4. **ما فائدة تضمين الموارد في ملفات HTML؟**  
   ينتج ملف واحد ذاتي الاحتواء لكل صفحة، مما يبسط النشر ويقضي على الحاجة إلى تحميل موارد خارجية.

5. **أين يمكنني العثور على مزيد من المعلومات حول GroupDocs.Viewer للـ Java؟**  
   - **Documentation**: [GroupDocs.Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
   - **API Reference**: [API Reference Guide](https://reference.groupdocs.com/viewer/java/)  

## الموارد

- **Documentation**: [GroupDocs.Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [API Reference Guide](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [GroupDocs.Viewer Download Page](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy GroupDocs.Viewer](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-01-15  
**تم الاختبار مع:** GroupDocs.Viewer 25.2  
**المؤلف:** GroupDocs