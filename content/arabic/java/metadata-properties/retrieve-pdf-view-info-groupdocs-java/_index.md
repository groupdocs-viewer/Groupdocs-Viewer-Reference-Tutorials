---
date: '2026-04-13'
description: تعلم كيفية استخراج عدد صفحات ملفات PDF وغيرها من بيانات التعريف مثل نوع
  المستند والأذونات باستخدام GroupDocs.Viewer للغة Java. اتبع هذا الدليل خطوة بخطوة
  لتعزيز قدرات معالجة المستندات في تطبيقك.
keywords:
- extract pdf page count
- read pdf document type
- retrieve pdf metadata java
title: استخراج عدد صفحات PDF والبيانات الوصفية عبر GroupDocs.Viewer Java
type: docs
url: /ar/java/metadata-properties/retrieve-pdf-view-info-groupdocs-java/
weight: 1
---

# استخراج عدد صفحات PDF والبيانات الوصفية عبر GroupDocs.Viewer Java

مرحبًا بكم في هذا الدليل الشامل حول **extract pdf page count** ومعلومات العرض الأخرى من مستند PDF باستخدام مكتبة GroupDocs.Viewer في Java. إذا كنت بحاجة إلى قراءة نوع مستند PDF برمجيًا، أو الحصول على أذوناته، أو ببساطة عدّ صفحاته، فأنت في المكان الصحيح.

![استرجاع بيانات PDF الوصفية والخصائص باستخدام GroupDocs.Viewer للـ Java](/viewer/metadata-properties/retrievepdf-metadata-and-properties-java.png)

## إجابات سريعة
- **ما الذي يمكنني استرجاعه؟** عدد صفحات PDF، نوع المستند، وأذونات الطباعة.  
- **أي مكتبة؟** GroupDocs.Viewer للـ Java (الإصدار 25.2).  
- **هل أحتاج إلى ترخيص؟** نسخة تجريبية مجانية تعمل للاختبار؛ الترخيص التجاري مطلوب للإنتاج.  
- **إصدار Java المدعوم؟** Java 8 أو أعلى.  
- **كم عدد أسطر الكود؟** أقل من 20 سطرًا للحصول على معلومات العرض الكاملة.

## ما ستتعلمه
- فهم كيف يتيح GroupDocs.Viewer للـ Java وظيفة عرض المستندات.  
- إعداد بيئتك لاستخدام GroupDocs.Viewer مع Java.  
- استرجاع وطباعة معلومات العرض من ملف PDF، بما في ذلك **extract pdf page count**.  
- استكشاف التطبيقات العملية واعتبارات الأداء.

## لماذا استخراج عدد صفحات PDF والبيانات الوصفية الأخرى؟
معرفة عدد الصفحات، نوع المستند، والأذونات يساعدك على:
1. **عرض ملخصات مختصرة** في أنظمة إدارة المحتوى.  
2. **فرض الأمان** عن طريق التحقق مما إذا كان الطباعة مسموحًا بها قبل العرض.  
3. **تحسين استخدام الموارد** بتحميل الصفحات المطلوبة فقط.

## المتطلبات المسبقة
- **المكتبات والاعتمادات**: GroupDocs.Viewer للـ Java (مضافة عبر Maven).  
- **البيئة**: Java 8 أو أحدث مثبت على جهاز التطوير الخاص بك.  
- **قاعدة المعرفة**: برمجة Java الأساسية ومعرفة Maven.

## إعداد GroupDocs.Viewer للـ Java

### تكوين Maven
Add the repository and dependency to your `pom.xml`:

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
يمكنك البدء بنسخة تجريبية مجانية أو الحصول على ترخيص مؤقت لاستكشاف جميع ميزات GroupDocs.Viewer. للاستخدام طويل الأمد، يُنصح بشراء ترخيص.

## كيفية استخراج عدد صفحات PDF باستخدام GroupDocs.Viewer في Java

### الخطوة 1: تكوين `ViewInfoOptions`
```java
// Create ViewInfoOptions for HTML view, which is necessary for retrieving view info
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
```
*لماذا*: `ViewInfoOptions` يخبر الـ Viewer أي تمثيل تحتاجه. استخدام `forHtmlView()` يجهز المحرك لإرجاع البيانات الوصفية المفيدة لتصيير HTML، بما في ذلك عدد الصفحات.

### الخطوة 2: تهيئة `Viewer`
```java
try (Viewer viewer = new Viewer(pdfFilePath)) {
    // Retrieval and processing steps will be done here
}
```
*لماذا*: كائن `Viewer` مرتبط بمسار ملف PDF الخاص بك. تغليفه داخل كتلة try‑with‑resources يضمن تحرير الموارد الأصلية تلقائيًا.

### الخطوة 3: استرجاع معلومات العرض (البيانات الوصفية)
```java
// Retrieve view information from the document using the specified options
PdfViewInfo viewInfo = (PdfViewInfo) viewer.getViewInfo(viewInfoOptions);

// Output the retrieved view information
System.out.println("Document type is: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
System.out.println("Printing allowed: " + viewInfo.isPrintingAllowed());
```
*لماذا*: يقتطف هذا المقتطف **read pdf document type**، **extract pdf page count**، و **get pdf permissions java** في استدعاء واحد. كائن `PdfViewInfo` يحتوي على جميع البيانات التي تحتاجها للمعالجة اللاحقة.

### المشكلات الشائعة والنصائح
- **مسار ملف غير صحيح** → يطرح `FileNotFoundException`. تحقق مرة أخرى من المسار المطلق أو النسبي.  
- **عدم توافق الإصدارات** → تأكد من أن نسخة Maven (`25.2`) تتطابق مع مكتبة وقت التشغيل.  
- **ملفات PDF الكبيرة** → فكر في البث أو معالجة الصفحات على دفعات لتقليل استهلاك الذاكرة.

## التطبيقات العملية
يمكن دمج GroupDocs.Viewer في أنظمة مختلفة:
1. **أنظمة إدارة المحتوى** – استخراج البيانات الوصفية تلقائيًا من ملفات PDF المرفوعة للفهرسة.  
2. **سير عمل إدارة المستندات** – اتخاذ قرار السماح بالطباعة بناءً على علم `isPrintingAllowed`.  
3. **لوحات التحكم على الويب** – عرض معاينة حية لعدد الصفحات ونوع المستند دون تحميل الملف بالكامل.

## اعتبارات الأداء
- استخدم `ViewInfoOptions` فقط عندما تحتاج إلى البيانات الوصفية؛ تجنب استدعاء `getViewInfo` لكل طلب إذا كانت المعلومات مخزنة مؤقتًا.  
- راقب استهلاك الذاكرة، خاصةً مع ملفات PDF الكبيرة، وأغلق الـ `Viewer` بسرعة (كتلة try‑with‑resources تتعامل مع ذلك).

## الخاتمة
أنت الآن تعرف كيف **extract pdf page count**، قراءة نوع المستند، والحصول على الأذونات باستخدام GroupDocs.Viewer للـ Java. لا تتردد في تجربة `ViewInfoOptions` أخرى (مثل `forImageView`) لتناسب سيناريوهات التصيير المختلفة.

### الخطوات التالية
- استكشاف تصيير الصفحات إلى صور أو HTML باستخدام `viewer.view`.  
- دمج استخراج البيانات الوصفية مع قاعدة بيانات لبناء فهارس مستندات قابلة للبحث.

## قسم الأسئلة الشائعة
**س: كيف أبدأ بنسخة تجريبية مجانية؟**  
ج: زر [صفحة النسخة التجريبية لـ GroupDocs](https://releases.groupdocs.com/viewer/java/) للحصول على تعليمات حول الحصول على الترخيص المجاني الخاص بك.

**س: هل يمكن استخدام GroupDocs.Viewer في التطبيقات السحابية؟**  
ج: نعم، المكتبة تدعم بيئات مختلفة ويمكن دمجها في حلول سحابية.

**س: ماذا أفعل إذا واجهت خطأً في تصيير PDF؟**  
ج: تحقق من توافق المستند أو قم بتحديث إلى أحدث نسخة من GroupDocs.Viewer للحصول على دعم محسّن.

## الموارد
- **الوثائق**: [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API**: [GroupDocs Viewer API Reference](https://reference.groupdocs.com/viewer/java/)  
- **تحميل**: [GroupDocs Viewer Download Page](https://releases.groupdocs.com/viewer/java/)  
- **شراء**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **نسخة تجريبية**: [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **ترخيص مؤقت**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **الدعم**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-04-13  
**تم الاختبار مع:** GroupDocs.Viewer 25.2 للـ Java  
**المؤلف:** GroupDocs