---
date: '2026-02-23'
description: تعلم كيفية تحويل ملفات IGS إلى PDF وHTML وJPG وPNG باستخدام GroupDocs.Viewer
  للغة Java. اتبع هذا الدليل خطوة بخطوة مع أمثلة شفرة جاهزة للتنفيذ.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: تحويل IGS إلى PDF وHTML وJPG وPNG باستخدام GroupDocs.Viewer Java
type: docs
url: /ar/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# تحويل IGS إلى PDF، HTML، JPG و PNG باستخدام GroupDocs.Viewer Java

إذا كنت بحاجة إلى **تحويل IGS إلى PDF** (أو إلى HTML، JPG، PNG) مباشرةً من تطبيق Java، فأنت في المكان الصحيح. في هذا الدليل سنستعرض كل ما تحتاجه — من إعداد المكتبة إلى عرض النموذج ثلاثي الأبعاد بالتنسيق الذي يناسب مشروعك. ستتعرف على سبب كون GroupDocs.Viewer خيارًا قويًا للتحويلات السريعة والموثوقة وستحصل على شفرة عملية يمكنك إدراجها في حلك الخاص.

![تحويل ملفات IGS إلى HTML، JPG، PNG، و PDF باستخدام GroupDocs.Viewer لـ Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## إجابات سريعة
- **هل يمكنني تحويل IGS إلى PDF باستخدام Java؟** نعم، باستخدام `PdfViewOptions` الخاصة بـ GroupDocs.Viewer.  
- **ما هي صيغ الإخراج المدعومة؟** HTML، JPG، PNG، و PDF.  
- **هل أحتاج إلى ترخيص للإنتاج؟** يلزم ترخيص تجاري؛ يتوفر تجربة مجانية للاختبار.  
- **ما نسخة Java المطلوبة؟** JDK 8 أو أعلى.  
- **هل Maven هو الطريقة الوحيدة لإضافة المكتبة؟** لا، يمكنك أيضًا استخدام Gradle أو إضافة JAR يدويًا.  

## ما هو “تحويل IGS إلى PDF”؟
تحويل IGS (صيغة ملف محايدة لبيانات CAD ثلاثية الأبعاد) إلى PDF يعني تحويل نموذج ثلاثي الأبعاد معقد إلى مستند ثابت يمكن عرضه على نطاق واسع. هذا مفيد لمشاركة التصاميم مع أصحاب المصلحة الذين لا يمتلكون أدوات CAD.

## لماذا تستخدم GroupDocs.Viewer لتحويلات IGS؟
- **عرض CAD بدون كتابة كود** – المكتبة تتولى المعالجة الثقيلة لتحليل صيغة IGS.  
- **خيارات إخراج متعددة** – استدعاء API واحد يمكنه إنتاج HTML أو JPG أو PNG أو PDF.  
- **متعدد المنصات** – يعمل على أي نظام تشغيل يدعم Java.  
- **مركز على الأداء** – عرض سريع حتى للتجميعات الكبيرة.  

## المتطلبات المسبقة
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** مثبت ومُعد في بيئة التطوير المتكاملة (IntelliJ IDEA، Eclipse، NetBeans، إلخ)  
- معرفة أساسية بـ Maven (اختياري لكن يُنصح به)  

## إعداد GroupDocs.Viewer لـ Java

### تبعية Maven
أضف مستودع GroupDocs وتبعيات Viewer إلى ملف `pom.xml` الخاص بك:

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
GroupDocs.Viewer offers:
- **تجربة مجانية** – استخدام محدود، مناسبة للاختبارات السريعة.  
- **ترخيص مؤقت** – مجموعة كاملة من الميزات لفترة تقييم قصيرة.  
- **ترخيص تجاري** – استخدام غير مقيد في الإنتاج.  

### تهيئة Viewer الأساسية
المقتطف أدناه يوضح كيفية إنشاء كائن `Viewer` يشير إلى ملف IGS الخاص بك:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## عرض IGS إلى HTML

### كيف يتم تحويل IGS إلى HTML؟
إخراج HTML يمنحك عرضًا تفاعليًا وصديقًا للمتصفح للنموذج ثلاثي الأبعاد.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**نقطة رئيسية:** `HtmlViewOptions.forEmbeddedResources()` يدمج جميع الموارد المطلوبة (CSS، الصور) مباشرةً في ملف HTML، مما يجعله قابلًا للنقل.

## عرض IGS إلى JPG

### كيف يتم تحويل IGS إلى JPG؟
صور JPG مثالية للصور المصغرة أو المعاينات السريعة.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

يمكنك تعديل `JpgViewOptions` للتحكم في الدقة وجودة الضغط.

## عرض IGS إلى PNG

### كيف يتم تحويل IGS إلى PNG؟
يدعم PNG الشفافية، وهو مفيد لتراكب النموذج على خلفيات مختلفة.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

جرّب `PngViewOptions` للحصول على أفضل توازن بين حجم الملف وجودة الصورة.

## عرض IGS إلى PDF

### كيف يتم تحويل IGS إلى PDF؟
PDF هو الصيغة المفضلة لمشاركة وثائق التصميم التفصيلية. يتناول هذا القسم مباشرة الكلمة المفتاحية الأساسية **تحويل IGS إلى PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` يتيح لك التحكم في تخطيط الصفحة، جودة الصورة، وما إذا كان سيتم تضمين الخطوط.

## تطبيقات عملية
- **بوابات الويب** – تضمين النماذج المعروضة بصيغة HTML مباشرةً في مكوّنات تكوين المنتجات.  
- **أصول التسويق** – إنشاء صور JPG/PNG عالية الدقة للكتيبات.  
- **الوثائق التقنية** – تضمين عروض PDF لنماذج CAD في أدلة المستخدم.  
- **ضمان الجودة** – أتمتة إنشاء الصور المصغرة لمجموعات كبيرة من ملفات IGS.  

## المشكلات الشائعة والحلول

| المشكلة | الحل |
|-------|----------|
| **مجلد الإخراج غير موجود** | تحقق من المسار الممرّر إلى `Path outputDirectory` وتأكد من أن عملية Java لديها أذونات كتابة. |
| **صفحات فارغة في PDF** | تأكد من أن ملف IGS غير تالف؛ حاول فتحه أولاً في عارض CAD. |
| **عرض بطيء للتجميعات الكبيرة** | زيادة حجم ذاكرة JVM (`-Xmx2g` أو أكثر) وفكّر في عرض الصفحات واحدةً تلو الأخرى باستخدام `viewer.getPageCount()` إذا لزم الأمر. |
| **خطوط مفقودة في PDF** | استخدم `PdfViewOptions` لتضمين الخطوط المطلوبة أو قم بتثبيت الخطوط المفقودة على الخادم. |

## الأسئلة المتكررة

**س: هل يمكنني تحويل عدة ملفات IGS في تشغيل واحد؟**  
ج: نعم. قم بالتكرار عبر قائمة مسارات الملفات واستدعِ طريقة `view` المناسبة لكل ملف.

**س: هل يمكن تخصيص حجم صفحة PDF؟**  
ج: بالتأكيد. `PdfViewOptions` توفر `setPageSize(PageSize.A4)` وغيرها من الطرق المشابهة.

**س: هل أحتاج إلى ترخيص منفصل لكل صيغة إخراج؟**  
ج: لا. ترخيص واحد لـ GroupDocs.Viewer يغطي جميع الصيغ المدعومة.

**س: ما هو الحد الأقصى لحجم ملف IGS قبل أن تتدهور الأداء؟**  
ج: المكتبة تتعامل مع ملفات تصل إلى عدة مئات من الميجابايت، لكن قد تحتاج إلى تخصيص المزيد من ذاكرة JVM للنماذج الكبيرة جدًا.

**س: هل يمكنني عرض منظور أو اتجاه محدد فقط؟**  
ج: يقوم GroupDocs.Viewer بعرض المنظر الافتراضي. للحصول على اتجاهات مخصصة، قم بمعالجة ملف IGS مسبقًا باستخدام أداة CAD قبل التحويل.

---

**آخر تحديث:** 2026-02-23  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 لـ Java  
**المؤلف:** GroupDocs