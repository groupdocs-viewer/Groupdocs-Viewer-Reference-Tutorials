---
date: '2026-01-15'
description: تعرّف على كيفية استخدام GroupDocs Viewer لإنشاء HTML من مستندات المشروع
  ضمن فترات زمنية محددة. يغطي هذا الدليل الإعداد، والشفرة، وحالات الاستخدام الواقعية.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: كيفية استخدام GroupDocs Viewer لعرض مستندات المشروع حسب الفواصل الزمنية في
  جافا
type: docs
url: /ar/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# كيفية استخدام GroupDocs Viewer لتصوير مستندات المشروع بفواصل زمنية في Java

إذا كنت تبحث عن **كيفية استخدام GroupDocs** لتصوير جداول المشروع في نافذة زمنية محددة، فقد وصلت إلى المكان الصحيح. في هذا الدرس سنستعرض العملية بالكامل—من إعداد Maven إلى توليد HTML من مستندات المشروع—حتى تتمكن من دمج عروض الخط الزمني الدقيقة مباشرةً في تطبيقاتك.

![Render Project Documents by Time Intervals with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## إجابات سريعة
- **ما الذي تفعله الميزة؟** تقوم بتصوير الجزء فقط من ملف Microsoft Project الذي يقع بين تاريخ بدء وتاريخ انتهاء.  
- **ما هو تنسيق الإخراج المستخدم؟** HTML مع موارد مدمجة، مثالي للتكامل مع الويب.  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تكفي للتقييم؛ الترخيص الكامل مطلوب للإنتاج.  
- **هل يمكن تغيير نطاق التاريخ أثناء التشغيل؟** نعم—قم بتعديل قيم `setStartDate` و `setEndDate` في خيارات التصوير.  
- **هل يدعم جميع إصدارات Java؟** يعمل مع Java 8+ طالما أنك تستخدم GroupDocs.Viewer 25.2 أو أحدث.

## ما هو “كيفية استخدام GroupDocs” في هذا السياق؟
GroupDocs Viewer هي مكتبة Java تقوم بتحويل أكثر من 100 تنسيق ملف إلى تمثيلات صديقة للويب. عندما **تستخدم GroupDocs** لملفات المشروع، ستحصل على القدرة على استخراج، تصور، ومشاركة بيانات الجدول الزمني دون الحاجة إلى Microsoft Project على جانب العميل.

## لماذا نُصوّر مستندات المشروع بفواصل زمنية؟
- **تحليل مركّز:** إظهار فقط المرحلة التي تهمك (مثال: الربع الثالث 2024).  
- **الأداء:** حجم HTML أصغر يعني تحميل صفحات أسرع.  
- **التكامل:** دمج عروض الخط الزمني في لوحات التحكم، بوابات التقارير، أو أدوات إدارة المشاريع المخصصة.  

## المتطلبات المسبقة

- **GroupDocs.Viewer for Java** الإصدار 25.2 أو أعلى.  
- مجموعة تطوير Java (JDK) 8 أو أحدث.  
- بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse.  
- معرفة أساسية بـ Maven.  

## إعداد GroupDocs.Viewer for Java

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

1. **نسخة تجريبية مجانية** – حمّل نسخة تجريبية من [صفحة تنزيل GroupDocs](https://releases.groupdocs.com/viewer/java/).  
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

### 1. تعريف دليل الإخراج

أنشئ مجلدًا سيُحفظ فيه صفحات HTML المُولدة:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*لماذا؟* تنظيم الملفات المُصوَّرة يجعل من السهل خدمتها من خادم ويب أو دمجها في واجهة المستخدم.

### 2. تهيئة Viewer بملف المشروع الخاص بك

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*لماذا؟* تحميل المستند يُعدّ المحلل الداخلي ويجعل بيانات التعريف الخاصة بالمشروع متاحة.

### 3. استرجاع معلومات العرض لملفات المشروع

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*لماذا؟* `ProjectManagementViewInfo` يمنحك تواريخ بدء وانتهاء الجدول الزمني، والتي ستستخدمها لاحقًا لتحديد نطاق التصوير.

### 4. تكوين خيارات تصوير HTML (توليد HTML من المشروع)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*لماذا؟* ضبط `StartDate` و `EndDate` يخبر GroupDocs بـ **توليد HTML من بيانات المشروع** فقط داخل تلك النافذة الزمنية.

### 5. تنفيذ عملية التصوير

```java
viewer.view(viewOptions);
```

*لماذا؟* هذه الدعوة تُنتج سلسلة من صفحات HTML المستقلة التي تمثل الجزء الزمني المختار من جدول مشروعك.

## المشكلات الشائعة & استكشاف الأخطاء وإصلاحها

- **مسارات ملفات غير صحيحة** – تأكد من وجود كل من ملف `.mpp` المصدر ودليل الإخراج.  
- **نوع ملف غير مدعوم** – تأكد من أن المستند بتنسيق مشروع مدعوم (مثل `.mpp`، `.mpt`).  
- **أخطاء الترخيص** – قد تفرض نسخة تجريبية حدودًا على التصوير؛ انتقل إلى ترخيص كامل للاستخدام غير المحدود.  

## تطبيقات عملية

1. **تحليل خط الزمن للمشروع** – إظهار أصحاب المصلحة فقط للمرحلة الحالية.  
2. **تقارير آلية** – توليد تقارير HTML محدودة بالوقت لتحديثات الحالة الأسبوعية.  
3. **التكامل مع لوحات التحكم** – دمج الصفحات المصورة في أدوات ذكاء الأعمال أو البوابات المخصصة.  
4. **الأرشفة** – حفظ نسخة ويب صديقة من جدول المشروع للرجوع إليها مستقبلاً.  

## نصائح الأداء

- استخدم خيار *الموارد المدمجة* لجعل كل صفحة HTML مستقلة، مما يقلل طلبات HTTP.  
- للمشروعات الكبيرة جدًا، فكر في التصوير على قطع تاريخية أصغر للحفاظ على استهلاك الذاكرة منخفضًا.  
- احذف الملفات المؤقتة بعد تقديمها لتجنب تراكم البيانات على القرص.  

## الخلاصة

أنت الآن تعرف **كيفية استخدام GroupDocs** Viewer لتصوير مستندات المشروع ضمن فاصل زمني محدد و**توليد HTML من بيانات المشروع** في Java. هذه القدرة تُسهل تصور الخطوط الزمنية، تحسن كفاءة التقارير، وتندمج بسلاسة مع تطبيقات الويب الحديثة.

### الخطوات التالية
- استكشف ميزات Viewer الإضافية مثل إضافة العلامات المائية، حماية كلمة المرور، أو تنسيق CSS مخصص.  
- اجمع خط أنابيب التصوير هذا مع واجهة REST API لتقديم عروض الخط الزمني عند الطلب.  

## الأسئلة المتكررة

**س: ما هي صيغ الملفات التي يدعمها GroupDocs.Viewer؟**  
ج: يدعم GroupDocs.Viewer مجموعة واسعة من الصيغ بما فيها Microsoft Project (MPP)، PDF، Word، Excel، PowerPoint، والعديد غيرها.

**س: كيف أبدأ باستخدام نسخة تجريبية مجانية من GroupDocs.Viewer؟**  
ج: يمكنك تنزيل النسخة التجريبية من [هنا](https://releases.groupdocs.com/viewer/java/).

**س: هل يمكنني تصوير المستندات دون دمج الموارد؟**  
ج: نعم، يمكنك اختيار خيار عرض HTML مختلف يُشير إلى موارد خارجية بدلاً من دمجها.

**س: ماذا أفعل إذا كان المستند كبيرًا جدًا للتصوير؟**  
ج: فكر في تقسيم المستند إلى أقسام أصغر أو تصوير نطاق التاريخ المطلوب فقط، كما هو موضح أعلاه.

**س: كيف أتعامل مع أخطاء التصوير؟**  
ج: تحقق من جميع إعدادات التكوين، تأكد من وجود ترخيص صالح، واطلع على وثائق GroupDocs للحصول على رموز الأخطاء التفصيلية.

## موارد
- **التوثيق**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **مرجع API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **التنزيل**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **الشراء**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **نسخة تجريبية مجانية**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **ترخيص مؤقت**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **الدعم**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-01-15  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 for Java  
**المؤلف:** GroupDocs