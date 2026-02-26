---
date: '2026-02-26'
description: تعرّف على كيفية إنشاء تقرير المشروع وعرض تفاصيل ملفات MS Project باستخدام
  GroupDocs.Viewer لجافا. مثالي للمطورين ومديري المشاريع والمحللين.
keywords:
- MS Project viewing
- Java GroupDocs.Viewer
- extracting project information
title: كيفية إنشاء تقرير مشروع من ملفات MS Project في Java باستخدام GroupDocs.Viewer
type: docs
url: /ar/java/file-formats-support/mastering-ms-project-viewing-groupdocs-java/
weight: 1
---

# كيفية إنشاء تقرير مشروع من ملفات MS Project باستخدام GroupDocs.Viewer للغة Java

## المقدمة

إن إنشاء تقرير مشروع من ملف MS Project هو حاجة شائعة لمديري المشاريع والمطورين على حد سواء. في هذا الدليل ستتعرف على كيفية تمكين **GroupDocs.Viewer للغة Java** لك من **إنشاء بيانات تقرير المشروع** و**عرض تفاصيل ملف MS Project** بسرعة وأمان. سنستعرض الإعداد، مقتطفات الشيفرة، وحالات الاستخدام الواقعية حتى تتمكن من بناء لوحات معلومات بصرية اليوم.

![MS Project Viewing with GroupDocs.Viewer for Java](/viewer/file‑formats-support/ms-project-viewing.png)

بنهاية هذا الدليل ستتمكن من:

- إعداد GroupDocs.Viewer للغة Java في مشروع Maven.  
- استرجاع معلومات العرض التي تشكل العمود الفقري لتقرير المشروع.  
- تكوين خيارات التحميل للملفات المحمية بكلمة مرور.  

هيا نبدأ ونحوّل طريقة تعاملنا مع بيانات MS Project!

## إجابات سريعة
- **ماذا يعني “إنشاء تقرير مشروع” هنا؟** استخراج بيانات تعريفية رئيسية للمشروع (تواريخ، عدد المهام، إلخ) لتغذية أدوات التقارير.  
- **ما المكتبة المطلوبة؟** GroupDocs.Viewer للغة Java (الإصدار 25.2 أو أحدث).  
- **هل يمكنني عرض ملف MS Project بدون ترخيص؟** النسخة التجريبية المجانية تعمل للتقييم، لكن الترخيص مطلوب للإنتاج.  
- **كيف أتعامل مع الملفات المحمية بكلمة مرور؟** استخدم `LoadOptions` لتزويد كلمة المرور عند إنشاء الـ `Viewer`.  
- **ما إصدار Java المدعوم؟** JDK 8 أو أحدث.

## ما هو “إنشاء تقرير مشروع” باستخدام GroupDocs.Viewer؟
إن إنشاء تقرير مشروع يعني استخراج معلومات منظمة—مثل تواريخ البدء/الانتهاء، عدد المهام، وتخصيص الموارد—من مستند MS Project. يوفر GroupDocs.Viewer كائن `ProjectManagementViewInfo` يحتوي على كل هذه التفاصيل، مما يسهل إدخالها في لوحات التقارير أو تصديرها إلى صيغ أخرى.

## لماذا عرض تفاصيل ملف MS Project باستخدام GroupDocs.Viewer؟
- **السرعة:** عرض واستخراج البيانات دون الحاجة إلى تثبيت Microsoft Project.  
- **الأمان:** خيارات التحميل تسمح بفتح الملفات المحمية بكلمة مرور بأمان.  
- **متعدد المنصات:** يعمل على أي بيئة متوافقة مع Java، من سطح المكتب إلى السحابة.  

## المتطلبات المسبقة

قبل أن نبدأ، تأكد من وجود ما يلي:

1. **المكتبات والاعتمادات**  
   - مكتبة GroupDocs.Viewer للغة Java (الإصدار 25.2 أو أحدث).  
   - Maven مثبت لإدارة الاعتمادات.  

2. **إعداد البيئة**  
   - بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
   - JDK 8 أو أعلى.  

3. **المعرفة المسبقة**  
   - مهارات أساسية في Java وMaven.  
   - إلمام بصيغ ملفات MS Project (مفيد لكن غير ضروري).  

## إعداد GroupDocs.Viewer للغة Java

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

لإتاحة جميع الوظائف، اختر أحد خيارات الترخيص التالية:

- **نسخة تجريبية مجانية** – جرب جميع المميزات دون الحاجة إلى بطاقة ائتمان.  
- **ترخيص مؤقت** – وصول ممتد لفترات التقييم.  
- **ترخيص كامل** – استخدام جاهز للإنتاج مع دعم غير محدود.  

للحصول على إرشادات الترخيص خطوة بخطوة، زر صفحة [شراء GroupDocs](https://purchase.groupdocs.com/buy).

### التهيئة الأساسية

بعد إضافة الاعتماد، يمكنك إنشاء كائن `Viewer` بتمرير مسار ملف MS Project الخاص بك.

## دليل التنفيذ

### استرجاع معلومات العرض لمستند MS Project

هذه الميزة تستخرج البيانات الأساسية التي تحتاجها لإنشاء محتوى **تقرير المشروع**.

#### الخطوة 1: تحديد مسار المستند

حدد مكان وجود ملف MS Project الخاص بك:

```java
String documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP";
```

#### الخطوة 2: تهيئة ViewInfoOptions

قم بتكوين الخيارات لطلب معلومات عرض بنمط HTML:

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
```

#### الخطوة 3: استرجاع وطباعة تفاصيل المشروع

أنشئ كائن `Viewer`، احصل على `ProjectManagementViewInfo`، واطبع الحقول الرئيسية التي تشكل تقرير مشروع نموذجي:

```java
try (Viewer viewer = new Viewer(documentPath)) {
    ProjectManagementViewInfo info = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);

    System.out.println("Document type: " + info.getFileType());
    System.out.println("Pages count: " + info.getPages().size());
    System.out.println("Project start date: " + info.getStartDate());
    System.out.println("Project end date: " + info.getEndDate());
}
```

**شرح**  
- `getViewInfo(viewInfoOptions)` يجلب البيانات الوصفية بناءً على الخيارات المقدمة.  
- كائن `info` المرتجع يحتوي على نوع الملف، عدد الصفحات، والتواريخ المهمة—وهي بالضبط العناصر التي تحتاجها لإنشاء بيانات **تقرير المشروع**.

### إعداد تكوين GroupDocs.Viewer

إذا كانت ملفات MS Project محمية بكلمة مرور، سيتعين عليك تزويد كلمة المرور عبر خيارات التحميل.

#### الخطوة 1: تكوين Load Options

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setPassword("your_password_if_needed");
```

#### الخطوة 2: تهيئة Viewer مع Load Options

مرّر `loadOptions` عند إنشاء كائن `Viewer`:

```java
try (Viewer viewer = new Viewer(documentPath, loadOptions)) {
    // Viewer is now ready for use with the specified document and options.
}
```

**شرح**  
`LoadOptions` يتيح لك تعريف معلمات إضافية مثل كلمات المرور، مما يضمن الوصول الآمن إلى الملفات المحمية.

## تطبيقات عملية

1. **لوحات معلومات إدارة المشاريع** – إدخال التواريخ وعدد المهام المستخرجة في لوحات معلومات实时 لأصحاب المصلحة.  
2. **التقارير الآلية** – تكرار عملية القراءة عبر ملفات `.mpp` متعددة، إنشاء تقارير ملخصة، وإرسالها بالبريد الإلكتروني تلقائيًا.  
3. **دمج مع أنظمة CRM** – دمج جداول المشروع مع بيانات العملاء لتحسين توقعات التسليم.

## اعتبارات الأداء

- **إدارة الذاكرة** – استخدم `try‑with‑resources` (كما هو موضح) لضمان إغلاق كائن `Viewer` بسرعة.  
- **التخزين المؤقت** – احفظ معلومات العرض المتكررة في ذاكرة مؤقتة لتفادي قراءات الملف المتكررة.  
- **المراقبة** – راقب استهلاك الذاكرة في JVM عند معالجة مشاريع كبيرة واضبط حجم الـ heap وفقًا لذلك.

## المشكلات الشائعة والحلول

| المشكلة | السبب | الحل |
|-------|-------|----------|
| خطأ `File not found` | مسار `documentPath` غير صحيح | تحقق من المسار المطلق أو النسبي وتأكد من وجود الملف. |
| عدم إرجاع بيانات للتواريخ | نسخة MS Project غير مدعومة | حدّث إلى أحدث إصدار من GroupDocs.Viewer أو حوّل الملف إلى صيغة مدعومة. |
| OutOfMemoryError في ملفات كبيرة | heap JVM غير كافٍ | زد قيمة العلم `-Xmx` أو عالج الملف على دفعات باستخدام خيارات الصفحات. |

## الأسئلة المتكررة

**س: ما هو GroupDocs.Viewer للغة Java؟**  
ج: هو مكتبة Java تقوم بعرض واستخراج المعلومات من أكثر من 100 صيغة ملف، بما في ذلك مستندات MS Project.

**س: كيف أتعامل مع ملفات MS Project المحمية بكلمة مرور؟**  
ج: استخدم الفئة `LoadOptions` لتعيين كلمة المرور قبل إنشاء كائن `Viewer`.

**س: هل يمكنني استخدام GroupDocs.Viewer في مشاريع تجارية؟**  
ج: نعم، بمجرد الحصول على ترخيص مناسب من GroupDocs.

**س: ما هي الأخطاء الشائعة عند استرجاع معلومات العرض؟**  
ج: مسارات ملفات غير صحيحة، استخدام نسخة مكتبة قديمة، أو محاولة قراءة ميزات MS Project غير مدعومة.

**س: كيف يمكن تحسين الأداء مع ملفات MS Project الكبيرة؟**  
ج: نفّذ التخزين المؤقت، أعد استخدام كائنات `Viewer` عندما يكون ذلك آمنًا، واضبط إعدادات الذاكرة في JVM.

## موارد
- [توثيق GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)  
- [مرجع API](https://reference.groupdocs.com/viewer/java/)  
- [تحميل GroupDocs.Viewer للغة Java](https://releases.groupdocs.com/viewer/java/)  
- [شراء ترخيص](https://purchase.groupdocs.com/buy)  
- [نسخة تجريبية مجانية](https://releases.groupdocs.com/viewer/java/)  
- [طلب ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/)  
- [منتدى دعم GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-02-26  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 للغة Java  
**المؤلف:** GroupDocs