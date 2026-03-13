---
date: '2026-01-28'
description: تعلم كيفية تعديل وحدات الوقت في MS Project باستخدام GroupDocs Viewer
  Java. قم بتبسيط عملية عرض مستندات مشروعك بكفاءة ودقة.
keywords:
- GroupDocs.Viewer Java
- MS Project time units adjustment
- render MS Project files
title: 'كيفية تعديل وحدات الوقت في MS Project باستخدام GroupDocs Viewer Java - دليل
  خطوة بخطوة'
type: docs
url: /ar/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# كيفية تعديل وحدات الوقت في MS Project باستخدام groupdocs viewer java: دليل خطوة بخطوة

## المقدمة
هل سئمت من تعديل وحدات الوقت يدويًا في مستندات MS Project قبل تحويلها إلى صيغة HTML؟ قد تكون العملية مرهقة وعرضة للأخطاء، خاصةً عند التعامل مع مشاريع كبيرة. باستخدام **groupdocs viewer java**، يمكنك تعديل إعدادات وحدة الوقت برمجيًا بسهولة، مما يضمن الدقة والكفاءة.

![تعديل وحدات الوقت في MS Project باستخدام GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

في هذا الدليل، سنوضح كيفية تغيير وحدات الوقت في مستندات MS Project إلى أيام باستخدام groupdocs viewer java. بنهاية هذا الشرح، ستكون قادرًا على:
- إعداد بيئتك لتحويل ملفات MS Project باستخدام GroupDocs.Viewer.
- تعديل وحدات الوقت لإدارة المشروع مباشرةً في الكود.
- دمج هذه التعديلات بسلاسة في تطبيقك.

قبل أن نبدأ، دعنا نتأكد من أن لديك كل ما تحتاجه للانطلاق!

## إجابات سريعة
- **ما المكتبة التي تتعامل مع تحويل MS Project؟** groupdocs viewer java  
- **ما وحدة الوقت التي يمكن تعيينها؟** أيام (via `TimeUnit.DAYS`)  
- **هل أحتاج إلى ترخيص؟** يتوفر ترخيص تجريبي أو مؤقت؛ يلزم ترخيص دائم للإنتاج.  
- **ما هو بيئة التطوير المتكاملة (IDE) الأنسب؟** أي IDE جافا (IntelliJ IDEA، Eclipse) يدعم Maven.  
- **هل Maven مطلوب؟** نعم، Maven يبسط إدارة التبعيات لـ groupdocs viewer java.  

## ما هو groupdocs viewer java؟
groupdocs viewer java هو مجموعة تطوير برمجيات (SDK) لجافا تمكن المطورين من تحويل مجموعة واسعة من صيغ المستندات — بما في ذلك ملفات MS Project — إلى صيغ صديقة للويب مثل HTML أو الصور. فهو يُجَرد تعقيدات تحليل الملفات، مما يتيح لك التركيز على منطق الأعمال.

## لماذا تعديل وحدات الوقت باستخدام groupdocs viewer java؟
تغيير وحدة الوقت من الإعداد الافتراضي (غالبًا الدقائق) إلى أيام يجعل الناتج المحوَّل أكثر قابلية للقراءة لأصحاب المصلحة، ويتماشى مع وتيرة التقارير المعتادة، ويقلل من الفوضى البصرية في تقارير HTML. هذا يكون ذا قيمة خاصة عند دمج جداول زمنية للمشاريع في لوحات التحكم أو إنشاء ملخصات حالة يومية.

## المتطلبات المسبقة
### المكتبات والتبعيات المطلوبة
- مكتبة **groupdocs viewer java** (الإصدار 25.2 أو أحدث).  
- تثبيت Maven على جهازك لإدارة التبعيات.  
- فهم أساسي لبرمجة جافا.  

### متطلبات إعداد البيئة
تأكد من أن بيئة التطوير لديك مُعدة بـ JDK (Java Development Kit) وIDE مثل IntelliJ IDEA أو Eclipse يدعم مشاريع Maven.

### المتطلبات المعرفية
الإلمام الأساسي بصياغة جافا، ومعالجة الملفات في جافا، والعمل مع تبعيات Maven سيكون مفيدًا. ومع ذلك، يهدف هذا الدليل إلى جعل العملية واضحة لجميع مستويات المهارة.

## إعداد groupdocs viewer java
لبدء استخدام groupdocs viewer java، أضفه كاعتماد في ملف `pom.xml` الخاص بمشروعك:

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
تقدم groupdocs نسخة تجريبية مجانية من مكتباتها، مما يتيح لك استكشاف الميزات قبل الشراء أو طلب ترخيص مؤقت:
- **نسخة تجريبية مجانية**: زر [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) لتنزيل المكتبة والبدء في استخدامها.  
- **ترخيص مؤقت**: للاختبار الموسع، اطلب [ترخيصًا مؤقتًا](https://purchase.groupdocs.com/temporary-license/).  
- **شراء**: إذا قررت أن groupdocs.viewer java مناسب لمشروعك، اشترِه مباشرةً من [صفحة الشراء](https://purchase.groupdocs.com/buy).  

### التهيئة الأساسية والإعداد
بعد إضافة الاعتماد في `pom.xml` الخاص بـ Maven، يمكنك البدء بالبرمجة. قم بتهيئة كائن Viewer مع مسار ملف MS Project الخاص بك واستعد للتحويل.

## دليل التنفيذ
سنستعرض كيفية تعديل وحدات الوقت لمستندات MS Project باستخدام groupdocs viewer java. سنقسم العملية إلى خطوات واضحة.

### نظرة عامة على الميزة: تعديل وحدات الوقت في مستندات MS Project
تتيح هذه الميزة تغيير إعداد وحدة الوقت لإدارة المشروع من الإعداد الافتراضي (عادةً الدقائق) إلى أيام، مما يجعل HTML الناتج أكثر ملاءمة للعرض والتقارير.

#### الخطوة 1: تحديد دليل الإخراج وتنسيق مسار ملف الصفحة
أولاً، حدد المكان الذي سيتم فيه تخزين ملفات HTML المحوَّلة:

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

استخدم هذا الدليل لحل مسارات الملفات ديناميكيًا لكل صفحة من مستند MS Project الخاص بك:

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

#### الخطوة 2: تهيئة خيارات العرض
أنشئ خيارات العرض مع الموارد المضمنة، والتي تسمح لك بتحديد كيفية عرض المشروع وتحويله:

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

#### الخطوة 3: تعديل إعداد وحدة الوقت
حدد أن وحدة الوقت لإدارة المشروع يجب أن تكون أيام، وهو ما يكون غالبًا أكثر ملاءمة للعروض والتقارير:

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

#### الخطوة 4: تحويل مستند MS Project
أخيرًا، استخدم فئة Viewer لتحويل المستند باستخدام خيارات العرض المحددة:

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من أن مسار دليل الإخراج محدد بشكل صحيح وقابل للكتابة.  
- تحقق من أن مسار ملف MS Project صحيح ومتاح.  
- إذا ظهرت مشكلات في التحويل، تحقق من أي استثناءات تُرمى من قبل فئة Viewer.  

## التطبيقات العملية
إليك بعض حالات الاستخدام الواقعية حيث يكون تعديل وحدات الوقت في مستندات MS Project مفيدًا بشكل خاص:
1. **تقارير المشروع** – غالبًا ما يفضل أصحاب المصلحة الملخصات اليومية على التفاصيل الدقيقة بالدقائق.  
2. **التكامل مع لوحات التحكم** – تضمين الجداول الزمنية في لوحات الأعمال التي تتطلب دقة على مستوى اليوم.  
3. **التحديثات الآلية** – الأنظمة التي تحتاج إلى تحديث حالات المشروع يوميًا تلقائيًا.  

## اعتبارات الأداء
عند التعامل مع ملفات MS Project الكبيرة، ضع في اعتبارك ما يلي لتحقيق أداء مثالي:
- استخدم الموارد المضمنة بشكل مقتصد إذا كانت أجزاء معينة من المستند مطلوبة بشكل متكرر.  
- راقب استخدام الذاكرة عند التعامل مع عدة مشاريع أو مشاريع كبيرة جدًا في آن واحد.  
- استفد من جمع القمامة في جافا بفعالية لإدارة تخصيص الموارد وإلغاء تخصيصها.  

## الخلاصة
لقد تعلمت الآن كيفية تعديل وحدات الوقت في MS Project باستخدام groupdocs viewer java. تُسهل هذه الميزة عملية تحويل مستندات المشروع، مما يجعلها أكثر قابلية للوصول وأسهل في دمجها مع الأنظمة الأوسع.  

فكر في استكشاف قدرات أخرى لـ groupdocs viewer java لتعزيز حلول إدارة المستندات لديك. هل أنت مستعد للخطوة التالية؟ جرّب تنفيذ هذا الحل في مشروعك القادم!  

## قسم الأسئلة المتكررة
**1. ما هو استخدام GroupDocs.Viewer for Java؟**  
GroupDocs.Viewer for Java يسمح للمطورين بتحويل المستندات إلى صيغ مختلفة، بما في ذلك ملفات MS Project، إلى صيغ HTML أو صور لأغراض العرض.

**2. هل يمكنني استخدام GroupDocs.Viewer لأنواع مستندات أخرى؟**  
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من صيغ المستندات بخلاف MS Project، مثل ملفات PDF، ومستندات Word، وجداول البيانات.

**3. كيف أتعامل مع الترخيص لـ GroupDocs.Viewer؟**  
تقدم GroupDocs خيارات ترخيص متعددة، بما في ذلك النسخ التجريبية المجانية، والترخيص المؤقت للاختبار الموسع، والترخيص الدائم عند الشراء.

**4. ماذا أفعل إذا واجهت أخطاءً عند تحويل ملفات مشروعي؟**  
تحقق من مسارات الملفات، وتأكد من أن لديك صلاحية كتابة في دليل الإخراج، وراجع أي استثناءات تُرمى من قبل GroupDocs.Viewer للحصول على إرشادات حل المشكلات.

**5. هل يمكنني تخصيص طريقة تحويل المستندات باستخدام GroupDocs.Viewer؟**  
بالطبع! يوفر GroupDocs.Viewer مجموعة من الخيارات لتخصيص التحويل، بما في ذلك ضبط وحدات الوقت للمشاريع، واختيار الموارد التي سيتم تضمينها، والمزيد.

## الموارد
- [التوثيق](https://docs.groupdocs.com/viewer/java/)  
- [مرجع API](https://reference.groupdocs.com/viewer/java/)  
- [تحميل GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [شراء ترخيص](https://purchase.groupdocs.com/buy)  

**آخر تحديث:** 2026-01-28  
**تم الاختبار مع:** groupdocs viewer java 25.2  
**المؤلف:** GroupDocs