---
date: '2026-03-29'
description: تعلم كيفية إنشاء عرض HTML لملفات MPP باستخدام GroupDocs Viewer في Java،
  وعرض مستندات المشروع وفق فواصل زمنية مع كود خطوة بخطوة.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: إنشاء عرض HTML لملف MPP باستخدام GroupDocs Viewer (Java)
type: docs
url: /ar/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# كيفية استخدام GroupDocs Viewer لعرض مستندات المشروع وفق فترات زمنية في Java

في هذا الدرس ستتعلم كيفية **create html view mpp** باستخدام GroupDocs Viewer for Java، مما يتيح لك عرض أجزاء فقط من ملف Microsoft Project التي تقع ضمن فترة زمنية محددة. سنستعرض إعداد Maven، تكوين الكود، وسيناريوهات واقعية حتى تتمكن من دمج عروض الخط الزمني الدقيقة مباشرةً في تطبيقاتك.

![عرض مستندات المشروع وفق فترات زمنية باستخدام GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## إجابات سريعة
- **ما الذي تفعله الميزة؟** تعرض فقط الجزء من ملف Microsoft Project الذي يقع بين تاريخ البدء وتاريخ الانتهاء.  
- **ما هو تنسيق الإخراج المستخدم؟** HTML مع موارد مدمجة، مثالي لتكامل الويب.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكنني تغيير نطاق التاريخ أثناء التشغيل؟** نعم—قم بتعديل قيم `setStartDate` و `setEndDate` في خيارات العرض.  
- **هل هذا مدعوم على جميع إصدارات Java؟** يعمل مع Java 8+ طالما تستخدم GroupDocs.Viewer 25.2 أو أحدث.

## كيفية إنشاء html view mpp لمستندات المشروع
يمكن لـ GroupDocs Viewer تحويل ملفات Microsoft Project (`.mpp`, `.mpt`) إلى صفحات HTML. من خلال تكوين تاريخ البدء وتاريخ الانتهاء في خيارات العرض، تقوم بتحديد الإخراج إلى الجزء الزمني الذي يهمك، مما يقلل حجم الملف ويسرع تحميل الصفحات.

## ما هو “How to Use GroupDocs” في هذا السياق؟
GroupDocs Viewer هي مكتبة Java تقوم بتحويل أكثر من 100 تنسيق ملف إلى تمثيلات صديقة للويب. عندما **how to use GroupDocs** لملفات المشروع، تحصل على القدرة على استخراج، تصور، ومشاركة بيانات الجدول الزمني دون الحاجة إلى Microsoft Project على جانب العميل.

## لماذا عرض مستندات المشروع وفق فترات زمنية؟
- **تحليل مركز:** عرض فقط المرحلة التي تهمك (مثال: الربع الثالث 2024).  
- **الأداء:** إخراج HTML أصغر يعني تحميل صفحات أسرع.  
- **التكامل:** دمج عروض الخط الزمني في لوحات التحكم، بوابات التقارير، أو أدوات إدارة المشاريع المخصصة.  

## المتطلبات المسبقة
- **GroupDocs.Viewer for Java** الإصدار 25.2 أو أعلى.  
- مجموعة تطوير Java (JDK) 8 أو أحدث.  
- بيئة تطوير متكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.  
- معرفة أساسية بـ Maven.  

## إعداد GroupDocs.Viewer لـ Java

### تبعية Maven
أضف المستودع والتبعية إلى ملف `pom.xml` الخاص بك:

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
1. **الإصدار التجريبي** – قم بتحميل نسخة تجريبية من [صفحة تنزيل GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **ترخيص مؤقت** – احصل على ترخيص مؤقت للاختبار الموسع عبر [هذا الرابط](https://purchase.groupdocs.com/temporary-license/).  
3. **الشراء** – للاستخدام الإنتاجي غير المحدود، اشترِ ترخيصًا من [صفحة شراء GroupDocs](https://purchase.groupdocs.com/buy).

### تهيئة Viewer الأساسية
المقتطف التالي يوضح كيفية إنشاء كائن `Viewer` يشير إلى ملف Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## دليل التنفيذ خطوة بخطوة

### 1. تحديد دليل الإخراج
أنشئ مجلدًا حيث سيتم حفظ صفحات HTML المولدة:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*لماذا؟* الحفاظ على تنظيم الملفات المولدة يجعل من السهل تقديمها من خادم ويب أو دمجها في واجهة المستخدم.

### 2. تهيئة Viewer بملف المشروع الخاص بك
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*لماذا؟* تحميل المستند يجهز المحلل الداخلي ويجعل بيانات التعريف الخاصة بالمشروع متاحة.

### 3. استرجاع معلومات العرض لملفات المشروع
```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*لماذا؟* `ProjectManagementViewInfo` يزودك بتواريخ بدء وانتهاء الجدول الزمني، والتي ستستخدمها لاحقًا لتحديد نطاق العرض.

### 4. تكوين خيارات عرض HTML (إنشاء HTML من المشروع)
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*لماذا؟* ضبط `StartDate` و `EndDate` يخبر GroupDocs بـ **generate html view mpp** البيانات فقط داخل تلك الفترة.

### 5. تنفيذ عملية العرض
```java
viewer.view(viewOptions);
```

*لماذا؟* هذه الدعوة تنتج سلسلة من صفحات HTML المستقلة التي تمثل الجزء الزمني المختار من جدول مشروعك.

## الأخطاء الشائعة & استكشاف الأخطاء وإصلاحها
- **مسارات ملفات غير صحيحة** – تحقق مرة أخرى من وجود كل من ملف `.mpp` المصدر ودليل الإخراج.  
- **نوع ملف غير مدعوم** – تأكد من أن المستند بتنسيق مشروع مدعوم (مثال: `.mpp`, `.mpt`).  
- **أخطاء الترخيص** – قد تفرض الترخيص التجريبي حدودًا على العرض؛ انتقل إلى ترخيص كامل للاستخدام غير المحدود.  

## التطبيقات العملية
1. **تحليل خط الزمن للمشروع** – عرض أصحاب المصلحة فقط للمرحلة الحالية.  
2. **تقارير مؤتمتة** – إنشاء تقارير HTML محدودة زمنياً لتحديثات الحالة الأسبوعية.  
3. **التكامل مع لوحات التحكم** – دمج الصفحات المولدة في أدوات ذكاء الأعمال أو البوابات المخصصة.  
4. **الأرشفة** – حفظ لقطة ويب صديقة لجدول المشروع للرجوع إليها مستقبلاً.  

## نصائح الأداء
- استخدم خيار *الموارد المدمجة* للحفاظ على كل صفحة HTML مستقلة، مما يقلل طلبات HTTP.  
- بالنسبة للمشاريع الكبيرة جدًا، فكر في العرض على أجزاء تاريخية أصغر للحفاظ على استهلاك الذاكرة منخفضًا.  
- نظّف الملفات المؤقتة بعد تقديمها لتجنب امتلاء القرص.  

## الخلاصة
أنت الآن تعرف **how to use GroupDocs** Viewer لعرض مستندات المشروع ضمن فترة زمنية محددة و **generate HTML from project** البيانات في Java. هذه القدرة تبسط تصورات الخط الزمني، تحسن كفاءة التقارير، وتندمج بسلاسة مع تطبيقات الويب الحديثة.

### الخطوات التالية
- استكشف ميزات Viewer الإضافية مثل إضافة العلامة المائية، حماية كلمة المرور، أو تنسيق CSS مخصص.  
- اجمع هذه العملية مع واجهة REST API لتقديم عروض الخط الزمني عند الطلب.  

## الأسئلة المتكررة

**س: ما هي صيغ الملفات التي يدعمها GroupDocs.Viewer؟**  
ج: يدعم GroupDocs.Viewer مجموعة واسعة من الصيغ بما في ذلك Microsoft Project (MPP)، PDF، Word، Excel، PowerPoint، والعديد غيرها.

**س: كيف أبدأ باستخدام النسخة التجريبية المجانية من GroupDocs.Viewer؟**  
ج: يمكنك تحميل النسخة التجريبية من [هنا](https://releases.groupdocs.com/viewer/java/).

**س: هل يمكنني عرض المستندات دون دمج الموارد؟**  
ج: نعم، يمكنك اختيار خيار عرض HTML مختلف يشير إلى موارد خارجية بدلاً من دمجها.

**س: ماذا لو كان مستندي كبيرًا جدًا للعرض؟**  
ج: فكر في تقسيم المستند إلى أقسام أصغر أو عرض نطاق التاريخ المطلوب فقط، كما هو موضح أعلاه.

**س: كيف أتعامل مع أخطاء العرض؟**  
ج: تحقق من جميع إعدادات التكوين، تأكد من أن لديك ترخيصًا صالحًا، واستشر وثائق GroupDocs للحصول على رموز الأخطاء التفصيلية.

## الموارد
- **الوثائق**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **التنزيل**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)  
- **الشراء**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **نسخة تجريبية مجانية**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)  
- **ترخيص مؤقت**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **الدعم**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-03-29  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs  

---