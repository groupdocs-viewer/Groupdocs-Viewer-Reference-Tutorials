---
date: '2026-02-05'
description: تعلم كيفية الحصول على viewinfo واسترجاع هياكل ملفات الأرشيف جافا باستخدام
  GroupDocs.Viewer. يغطي هذا الدليل الإعداد، أمثلة الشيفرة، وحالات الاستخدام الواقعية.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: كيفية الحصول على ViewInfo واسترجاع هياكل الأرشيف في جافا
type: docs
url: /ar/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# كيفية الحصول على ViewInfo واسترجاع هياكل الأرشيف في Java

إدارة ملفات الأرشيف بفعالية تتطلب فهماً واضحاً لبنيتها. في هذا الدرس ستتعلم **كيفية الحصول على viewinfo** لأي أرشيف وتعرف كيف يساعدك في التعامل مع **نوع ملف الأرشيف java**. سنستعرض إعداد GroupDocs.Viewer، استخراج معلومات العرض، وقراءة هياكل المجلدات بشكل متكرر حتى تتمكن من دمج الحل في المشاريع الحقيقية.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**ما ستتعلمه**
- إعداد وتكوين GroupDocs.Viewer للـ Java.  
- طرق **الحصول على viewinfo** من الأرشيفات.  
- تقنيات قراءة وعرض هيكل المجلدات لملف الأرشيف.  
- تطبيقات عملية واعتبارات الأداء عند استخدام GroupDocs.Viewer في مشاريع Java.

## إجابات سريعة
- **ماذا يوفر “viewinfo”؟** يعيد نوع الملف، عدد الصفحات، وقوائم مجلدات الأرشيف.  
- **ما هي الأرشيفات المدعومة؟** ZIP، RAR، TAR، وغيرها من الصيغ الشائعة.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.  
- **هل يمكنني معالجة أرشيفات كبيرة؟** نعم – استخدم البث وإدارة الذاكرة المناسبة كما هو موضح لاحقاً.  
- **هل Maven مطلوب؟** Maven هو الطريقة الموصى بها لإدارة تبعية GroupDocs.Viewer.

## ما هو “كيفية الحصول على viewinfo”؟
`getViewInfo` هي طريقة في واجهة GroupDocs.Viewer API تستخرج البيانات الوصفية عن مستند أو أرشيف دون عرض المحتوى بالكامل. بالنسبة للأرشيفات، تكشف عن شجرة المجلدات الداخلية، مما يتيح لك تحديد الأجزاء التي تريد عرضها أو معالجتها لاحقاً.

## لماذا نسترجع هياكل نوع ملف الأرشيف Java؟
فهم التخطيط الداخلي لـ **نوع ملف الأرشيف java** (مثل ZIP، RAR) يتيح لك:
- تحديد الملفات المطلوبة بسرعة دون استخراج كل شيء.  
- بناء خطوط أنابيب آلية تعالج فقط المجلدات الفرعية ذات الصلة.  
- دمج تنقل الأرشيف في أنظمة إدارة المحتوى أو أنظمة استيعاب البيانات.

## المتطلبات المسبقة

- **Java Development Kit (JDK):** الإصدار 8 أو أحدث.  
- **Maven:** لإدارة التبعيات والبناء.  
- **معرفة أساسية بـ Java:** الفهم العام لمفاهيم OOP مفيد لكنه ليس إلزامياً.

تحتاج أيضاً إلى الوصول إلى مكتبة GroupDocs.Viewer، والتي يمكنك إضافتها إلى مشروع Maven كما هو موضح أدناه.

## إعداد GroupDocs.Viewer للـ Java

### تكوين Maven

أضف المستودع والتبعيات إلى ملف `pom.xml` الخاص بك.

**المستودعات:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**التبعيات:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### الحصول على الترخيص

- **نسخة تجريبية:** حمّل نسخة تجريبية من موقع GroupDocs.  
- **ترخيص مؤقت:** اطلب مفتاحاً مؤقتاً للتقييم قصير المدة.  
- **ترخيص كامل:** اشترِ ترخيصاً تجارياً لاستخدام غير محدود في الإنتاج.

بمجرد أن تكون المكتبة على مسار الفئة (classpath)، يمكنك بدء كتابة الشيفرة.

## دليل التنفيذ

### كيفية الحصول على ViewInfo لملفات الأرشيف

ستوضح هذه الفقرة الخطوات الدقيقة لاستدعاء `getViewInfo` وقراءة شجرة المجلدات.

#### تهيئة الـ Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### استرجاع معلومات العرض

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### عرض هيكل المجلدات

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### قراءة المجلدات بشكل متكرر

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### الميزة 2: استرجاع هيكل مجلدات الأرشيف

تركّز هذه الميزة على طباعة هيكل المجلدات لملف الأرشيف. وهي مشابهة للميزة الأولى لكن مع التركيز على الاستكشاف المتكرر.

#### إعداد خيارات View Info

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### الاستكشاف المتكرر

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## تطبيقات عملية

1. **إدارة البيانات:** تنظيم مجموعات البيانات الكبيرة بسرعة عبر فهم هياكل الأرشيف.  
2. **معالجة الملفات الآلية:** معالجة دفعات من الملفات المؤرشفة دون استخراجها بالكامل.  
3. **دمج CMS:** تحسين أنظمة إدارة المحتوى بتنقل الأرشيف أثناء التشغيل.

## اعتبارات الأداء

- **تحسين استخدام الذاكرة:** عالج المجلدات مستوىً بمستوى وأغلق كائن `Viewer` فور الانتهاء.  
- **ابقَ محدثاً:** استخدم أحدث إصدار من GroupDocs.Viewer وإصدارات JDK للحصول على تحسينات الأداء.

## المشكلات الشائعة والحلول

| المشكلة | سبب حدوثه | الحل |
|-------|----------------|-----|
| `NullPointerException` عند قراءة المجلدات | `viewInfo.getFolders()` تُعيد null للمجلدات الفارغة | تحقق من كون القائمة null أو فارغة قبل التكرار. |
| معالجة بطيئة لملفات ZIP الضخمة | يتم تحميل الأرشيف بالكامل في الذاكرة | استخدم خيارات البث المتاحة في إصدارات GroupDocs الأحدث. |
| الترخيص غير موجود | مسار ملف الترخيص غير صحيح | ضع ملف الترخيص في جذر التطبيق أو اضبط `License.setLicense("path/to/license.json")`. |

## الأسئلة المتكررة

**س: ما هو GroupDocs.Viewer؟**  
ج: هو مكتبة Java قوية لعرض المستندات، بما في ذلك الأرشيفات، إلى صيغ مثل HTML، صورة، وPDF.

**س: هل يمكنني استخدام GroupDocs.Viewer مع لغات برمجة أخرى؟**  
ج: نعم، تقدم GroupDocs مجموعات تطوير (SDKs) لمنصات متعددة، لكن هذا الدرس يركز على تنفيذ Java.

**س: كيف أتعامل مع ملفات الأرشيف الكبيرة؟**  
ج: استخدم ممارسات إدارة الذاكرة الفعّالة، وفكّ الأرشيف إلى أجزاء أصغر إذا لزم الأمر.

**س: ما هي أنواع الأرشيف التي يدعمها GroupDocs.Viewer؟**  
ج: يدعم مجموعة متنوعة من الصيغ بما فيها ZIP، RAR، TAR، وغيرها.

**س: هل هناك حد لحجم الأرشيفات التي يمكنني معالجتها؟**  
ج: الحدود تعتمد على موارد النظام لديك. اختبر في بيئتك المستهدفة لتحديد الحدود العملية.

**س: هل تعمل “كيفية الحصول على viewinfo” مع الأرشيفات المحمية بكلمة مرور؟**  
ج: نعم، يمكنك تمرير كلمة المرور عبر `ArchiveOptions.setPassword("yourPassword")` قبل استدعاء `getViewInfo`.

## الخلاصة

باتباعك لهذا الدليل، أصبحت الآن تعرف **كيفية الحصول على viewinfo** لأي أرشيف مدعوم وكيفية استكشاف شجرة مجلداته باستخدام GroupDocs.Viewer للـ Java. تمنحك هذه التقنيات القدرة على بناء خطوط معالجة بيانات أذكى، تحسين تكامل أنظمة إدارة المحتوى، والتعامل بثقة مع مجموعات كبيرة من الملفات المؤرشفة. بعد ذلك، استكشف عرض الملفات الفردية من الأرشيف أو تحويلها إلى PDF/HTML باستخدام ميزات Viewer الأخرى.

---

**آخر تحديث:** 2026-02-05  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 للـ Java  
**المؤلف:** GroupDocs  

**الموارد**
- **التوثيق:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **مرجع API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **تحميل GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **شراء الترخيص:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **نسخة تجريبية وترخيص مؤقت:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)