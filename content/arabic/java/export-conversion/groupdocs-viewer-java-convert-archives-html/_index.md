---
date: '2026-02-23'
description: تعلم كيفية ضبط عدد العناصر في كل صفحة، وتضمين موارد HTML، وتحويل الأرشيفات
  دفعة واحدة إلى HTML صفحة واحدة أو متعددة الصفحات باستخدام GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'تعيين عدد العناصر في الصفحة: تحويل الأرشيفات إلى HTML باستخدام GroupDocs.Viewer
  Java'
type: docs
url: /ar/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# تعيين عدد العناصر في الصفحة: تحويل الأرشيفات إلى HTML باستخدام GroupDocs.Viewer Java

تحويل ملفات الأرشيف مثل ZIP أو RAR إلى HTML صديق للويب هو حاجة متكررة عندما تريد مشاركة أو مراجعة المستندات مباشرة في المتصفح. في هذا الدليل ستتعلم **كيفية تعيين عدد العناصر في الصفحة** أثناء عرض الأرشيفات، وكيفية تضمين موارد HTML لإنتاج ملف مستقل، وكيفية تحويل الأرشيفات دفعةً بكفاءة باستخدام GroupDocs.Viewer Java.

![تحويل الأرشيفات إلى HTML باستخدام GroupDocs.Viewer للـ Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## إجابات سريعة
- **ما الذي يتحكم فيه “تعيين عدد العناصر في الصفحة”؟** يحدد عدد الملفات أو المجلدات من الأرشيف التي تظهر في كل صفحة HTML مُولدة.  
- **هل يمكنني تضمين الصور وCSS مباشرة في HTML؟** نعم – استخدم خيار `forEmbeddedResources` لتضمين موارد HTML.  
- **هل التحويل الدفعي ممكن؟** بالتأكيد؛ يمكنك التكرار على مجموعة من الأرشيفات وعرض كل واحدة بالإعدادات نفسها.  
- **هل أحتاج إلى Maven لاستخدام GroupDocs.Viewer؟** نعم، أضف تبعية `maven groupdocs viewer` كما هو موضح أدناه.  
- **ما صيغ الإخراج المدعومة؟** كل من HTML صفحة واحدة Java وHTML متعدد الصفحات Java متاحان.

## ما هو “تعيين عدد العناصر في الصفحة” في GroupDocs.Viewer؟
إعداد **تعيين عدد العناصر في الصفحة** يخص خيارات عرض الأرشيف. يخبر العارض عدد إدخالات الأرشيف (ملفات أو مجلدات) التي يجب عرضها في كل صفحة HTML عند إنشاء مستند HTML متعدد الصفحات. تعديل هذه القيمة يساعدك على موازنة حجم الصفحة وسرعة التنقل، خاصةً مع الأرشيفات الكبيرة.

## لماذا يتم تضمين موارد HTML؟
تضمين الموارد (الصور، CSS، الخطوط) مباشرة داخل ملف HTML يخلق مستندًا واحدًا محمولًا يمكن فتحه دون ملفات خارجية. هذا مثالي لمرفقات البريد الإلكتروني، العرض دون اتصال، أو تضمين الناتج في صفحات ويب أخرى.

## المتطلبات المسبقة

- **المكتبات المطلوبة:** تضمّن GroupDocs.Viewer الإصدار 25.2 أو أحدث.  
- **البيئة:** تثبيت وتكوين Java Development Kit (JDK).  
- **المعرفة:** أساسيات Java وإدارة تبعيات Maven.  

## إعداد Maven لـ GroupDocs Viewer

أضف مستودع GroupDocs وتبعية العارض إلى ملف `pom.xml` الخاص بك:

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
يقدم GroupDocs.Viewer **رابط تجربة مجانية**، ترخيصًا مؤقتًا، أو خيار شراء كامل. اختر ما يناسب جدول مشروعك.

### التهيئة الأساسية
بعد إعداد Maven، استدعِ العارض في الكود الخاص بك:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## كيفية عرض الأرشيفات إلى HTML صفحة واحدة

### الخطوة 1: تحديد دليل الإخراج
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### الخطوة 2: تعيين اسم الملف للإخراج صفحة واحدة
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### الخطوة 3: تهيئة العارض
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### الخطوة 4: تكوين خيارات العرض (تضمين موارد HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### الخطوة 5: العرض كصفحة واحدة
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## كيفية عرض الأرشيفات إلى HTML متعدد الصفحات وتعيين عدد العناصر في الصفحة

### الخطوة 1: إعادة استخدام دليل الإخراج
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### الخطوة 2: تحديد صيغة اسم الملف للصفحات المتعددة
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### الخطوة 3: تهيئة العارض مرة أخرى
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### الخطوة 4: تكوين خيارات متعددة الصفحات (تضمين موارد HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### الخطوة 5: تعيين عدد العناصر في الصفحة (الكلمة المفتاحية الأساسية في الإجراء)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## تطبيقات عملية

- **أنظمة إدارة المستندات:** إضافة وظيفة معاينة الأرشيف دون تثبيت عارضين إضافيين.  
- **بوابات الويب:** تقديم طريقة سريعة للمستخدمين لاستكشاف المستندات المجمعة دون تحميل.  
- **أدوات التعاون:** تمكين الفرق من فحص الأرشيفات المشتركة مباشرة في المتصفح.

## اعتبارات الأداء

- **إدارة الموارد:** راقب استهلاك الذاكرة؛ فكر في ضبط جامع القمامة (GC) للـ JVM للدفعات الكبيرة.  
- **تحويل الأرشيفات دفعةً:** كرّر عبر قائمة ملفات الأرشيف واستدعِ منطق العرض نفسه لتعظيم الإنتاجية.  
- **استراتيجية التخزين المؤقت:** احفظ HTML المُعرض في ذاكرة مؤقتة إذا تم الوصول إلى نفس الأرشيف بشكل متكرر.

## الأسئلة المتكررة

**س: ما هو GroupDocs.Viewer Java؟**  
ج: مكتبة متعددة الاستخدامات لعرض المستندات—بما في ذلك الأرشيفات—إلى صيغ مثل HTML، PDF، والصور.

**س: كيف يمكنني الحصول على تجربة مجانية من GroupDocs.Viewer؟**  
ج: زر [رابط التجربة المجانية](https://releases.groupdocs.com/viewer/java/) للتحميل والاختبار.

**س: هل يمكنني تحويل أنواع مستندات أخرى غير الأرشيفات؟**  
ج: نعم، يدعم العارض ملفات PDF، Word، Excel، والعديد من الصيغ الأخرى.

**س: ماذا أفعل إذا كان العرض بطيئًا؟**  
ج: قلل عدد العناصر في الصفحة، فعّل البث، أو عالج الأرشيفات على دفعات أصغر.

**س: أين يمكنني الحصول على المساعدة أو الدعم؟**  
ج: تواصل عبر [منتدى الدعم](https://forum.groupdocs.com/c/viewer/9).

**س: هل يمكن تضمين CSS والصور مباشرة في HTML؟**  
ج: بالتأكيد—استخدم `HtmlViewOptions.forEmbeddedResources` كما هو موضح في الأمثلة.

**س: كيف أقوم بتحويل دفعة من مجلد يحتوي على أرشيفات؟**  
ج: كرّر عبر كل ملف باستخدام حلقة `for`، مع تطبيق نفس تكوين `Viewer` و`HtmlViewOptions` لكل تكرار.

## موارد

- **التوثيق:** تعمّق في الوظائف عبر [توثيق GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **مرجع API:** استكشف الـ API الكامل على [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **التحميل:** احصل على أحدث الحزم من [صفحة التحميل](https://releases.groupdocs.com/viewer/java/).  
- **الشراء والترخيص:** راجع الخيارات على [صفحة الشراء](https://purchase.groupdocs.com/buy).  
- **الدعم والمجتمع:** انضم إلى المناقشات على [منتدى GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**آخر تحديث:** 2026-02-23  
**تم الاختبار مع:** GroupDocs.Viewer 25.2  
**المؤلف:** GroupDocs