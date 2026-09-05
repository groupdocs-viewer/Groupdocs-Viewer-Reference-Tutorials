---
date: '2026-09-05'
description: كيفية استخراج metadata باستخدام GroupDocs Viewer for Java، الحصول على
  page count في Java، ومعاينة المستندات بكفاءة في تطبيقاتك.
keywords:
- how to extract metadata
- how to preview document
- get page count java
- metadata extraction java
lastmod: '2026-09-05'
og_description: كيفية استخراج metadata باستخدام GroupDocs Viewer for Java—retrieve
  page count، view options، وتمكين fast document preview في Java apps. Supports 50+
  formats و large files.
og_image_alt: Guide showing metadata extraction and view info using GroupDocs Viewer
  for Java
og_title: كيفية استخراج metadata باستخدام GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-05'
  description: How to extract metadata with GroupDocs Viewer for Java, get page count
    Java, and preview documents efficiently in your applications.
  headline: How to extract metadata with GroupDocs Viewer for Java
  type: TechArticle
- description: How to extract metadata with GroupDocs Viewer for Java, get page count
    Java, and preview documents efficiently in your applications.
  name: How to extract metadata with GroupDocs Viewer for Java
  steps:
  - name: '**Document management systems:** Auto‑populate metadata fields (page count,
      format) when users upload files, enabling efficient search and categorisation.'
    text: '**Document management systems:** Auto‑populate metadata fields (page count,
      format) when users upload files, enabling efficient search and categorisation.'
  - name: '**Fast preview features:** Build a lightweight **how to preview document**
      component that shows the first page or thumbnail without a full render.'
    text: '**Fast preview features:** Build a lightweight **how to preview document**
      component that shows the first page or thumbnail without a full render.'
  - name: '**Analytics & reporting:** Collect page‑count statistics across your repository
      to forecast storage needs and monitor usage trends.'
    text: '**Analytics & reporting:** Collect page‑count statistics across your repository
      to forecast storage needs and monitor usage trends.'
  type: HowTo
- questions:
  - answer: It tells the API which view format (HTML, PDF, image) you want metadata
      for, allowing you to **extract document metadata** efficiently.
    question: What is the purpose of `ViewInfoOptions` in GroupDocs Viewer for Java?
  - answer: Yes, it supports over 50 formats—including Word, Excel, PowerPoint, and
      common image types—making it ideal for **metadata extraction java** projects.
    question: Can I use GroupDocs Viewer for Java with file types other than PDF?
  - answer: Retrieve only metadata (using `getViewInfo`) and close the `Viewer` immediately;
      this approach processes multi‑hundred‑page files using under 10 MB of RAM.
    question: How do I handle very large documents without exhausting memory?
  - answer: A free trial is available for evaluation, but a commercial license is
      mandatory for any production deployment.
    question: Is a license required for production use?
  - answer: Incorrect file paths and missing Maven dependencies are the top issues.
      Verify the document location and ensure the `groupdocs-viewer` artifact is correctly
      added to your `pom.xml`.
    question: What are the most common errors when implementing this feature?
  type: FAQPage
tags:
- metadata extraction
- document preview
- GroupDocs Viewer
- Java document processing
title: كيفية استخراج metadata باستخدام GroupDocs Viewer for Java
type: docs
url: /ar/java/advanced-rendering/groupdocs-viewer-java-document-views/
weight: 1
---

# كيفية استخراج البيانات الوصفية باستخدام GroupDocs Viewer للـ Java

في هذا الدرس ستتعلم **كيفية استخراج البيانات الوصفية** من مجموعة واسعة من أنواع المستندات باستخدام GroupDocs Viewer للـ Java. بنهاية الدليل ستتمكن من استرجاع عدد الصفحات، اكتشاف صيغ العرض المدعومة، وبناء ميزات **معاينة المستند** خفيفة الوزن دون تصيير الملف بالكامل. هذا النهج مفيد بشكل خاص عندما تحتاج إلى **الحصول على عدد الصفحات java** بسرعة أو التعامل مع مستندات كبيرة بطريقة فعّالة في الذاكرة.

![استرجاع معلومات عرض المستند والرؤى باستخدام GroupDocs.Viewer للـ Java](/viewer/advanced-rendering/retrieve-document-view-information-and-insights-java.png)

**Viewer** هو الفئة الأساسية التي تمثل مستندًا وتوفر طرقًا للتصيير واستخراج البيانات الوصفية.  
`getViewInfo` تُعيد كائن `ViewInfo` يحتوي على بيانات وصفية مثل عدد الصفحات وأنواع العرض المدعومة.

## إجابات سريعة
- **ماذا يعني “استخراج بيانات وصفية للمستند”؟** استرجاع تفاصيل هيكلية (عدد الصفحات، خيارات العرض، بيانات خاصة بالصيغ) دون تصيير المحتوى بالكامل.  
- **أي طريقة توفر معلومات العرض؟** `viewer.getViewInfo(viewInfoOptions)`.  
- **هل يمكنني معاينة مستند دون تصيير كامل؟** نعم، باستخدام بيانات وصفية للعرض يمكنك بناء ميزة **معاينة المستند java** سريعة.  
- **هل هو مناسب للملفات الكبيرة؟** بالتأكيد—استخراج البيانات الوصفية يستخدم ذاكرة قليلة، مما يساعدك على **إدارة المستندات الكبيرة** بفعالية.  
- **هل أحتاج إلى ترخيص؟** النسخة التجريبية المجانية تكفي للتقييم؛ الترخيص التجاري مطلوب للإنتاج.

## كيفية استخراج البيانات الوصفية باستخدام GroupDocs Viewer للـ Java

حمّل مستندك باستخدام الفئة `Viewer` واستدعِ `getViewInfo` – هذا الاستدعاء الواحد يُعيد مجموعة كاملة من البيانات الوصفية للعرض، بما في ذلك عدد الصفحات، صيغ العرض المدعومة، وخيارات خاصة بالصيغ. العملية تقرأ فقط رأس الملف، لذا تعمل في ملليثانية حتى للملفات التي تحتوي على مئات الصفحات وتستهلك ذاكرة RAM أقل بكثير مقارنةً بالتصيير الكامل.

### ما هي فئة Viewer؟
الفئة `Viewer` هي المكوّن الأساسي في GroupDocs Viewer للـ Java الذي يمثل مستندًا ويوفر طرقًا للتصيير واستخراج البيانات الوصفية. جميع العمليات المتعلقة بالعرض تمر عبر هذا الكائن.

### لماذا نستخدم GroupDocs Viewer لاستخراج البيانات الوصفية؟
- **الأداء:** يسترجع البيانات الوصفية في أقل من 50 مللي ثانية لملفات PDF مكوّنة من 300 صفحة على خادم عادي، باستخدام أقل من 5 ميغابايت من RAM.  
- **تغطية الصيغ:** يدعم **أكثر من 50 صيغة إدخال وإخراج** (PDF، DOCX، XLSX، PPTX، HTML، الصور، إلخ).  
- **القابلية للتوسع:** يتيح لك **الحصول على عدد الصفحات java** فورًا، وهو مثالي للتحكم في ترقيم الصفحات في بوابات المستندات ذات النطاق الواسع.  
- **الأمان:** لا يتم تصيير المحتوى الحساس إلا إذا طلبت ذلك صراحةً، مما يقلل من سطح الهجوم.

## المتطلبات المسبقة
- **GroupDocs.Viewer للـ Java:** الإصدار 25.2 أو أحدث.  
- **مجموعة تطوير جافا (JDK):** الإصدار 8 أو أعلى.  
- بيئة تطوير متكاملة (IntelliJ IDEA، Eclipse، أو NetBeans) وMaven لإدارة التبعيات.  
- معرفة أساسية بجافا وإلمام بـ Maven.

## إعداد GroupDocs Viewer للـ Java
أضف المكتبة إلى ملف Maven `pom.xml` الخاص بك:

**تكوين Maven**

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
- **نسخة تجريبية مجانية:** تحميل من موقع GroupDocs لاستكشاف الميزات.  
- **ترخيص مؤقت:** الحصول على مفتاح محدود الزمن للاختبار الموسع.  
- **ترخيص تجاري:** الشراء للاستخدام الإنتاجي غير المحدود.

## دليل التنفيذ

### الحصول على معلومات عرض المستند
استرجاع تفاصيل شاملة خاصة بالعرض مثل عدد الصفحات وخيارات العرض المدعومة.

#### نظرة عامة
الهدف هو **استخراج البيانات الوصفية للمستند**—وبشكل محدد معلومات العرض التي تخبرك بعدد الصفحات الموجودة وأي صيغ تصيير مدعومة.

#### تنفيذ خطوة بخطوة
**1. تهيئة Viewer**  
Create a `Viewer` instance pointing at the target file:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ViewInfo;

public class FeatureGetViewInfo {
    public static void main(String[] args) {
        // Specify the path to your input document.
        String filePath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF";
        
        // Initialize ViewInfoOptions for HTML view.
        ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();

        try (Viewer viewer = new Viewer(filePath)) {
            // Retrieve view information about the document using the specified options.
            ViewInfo info = viewer.getViewInfo(viewInfoOptions);
            
            // The info object now contains details like page count and available views.
        }
    }
}
```

**2. تكوين خيارات view‑info**  
- `ViewInfoOptions.forHtmlView()` – يجلب البيانات الوصفية الخاصة بـ HTML.  
- `ViewInfoOptions.forPdfView()` – يجلب البيانات الوصفية الخاصة بـ PDF.  
- `ViewInfoOptions.forImageView()` – يجلب البيانات الوصفية الخاصة بالصور المصغرة.

**3. استرجاع البيانات الوصفية**  
استدعِ `viewer.getViewInfo(viewInfoOptions)` للحصول على كائن `ViewInfo` يحتوي على عدد الصفحات، صيغ العرض المدعومة، وتفاصيل مفيدة أخرى.

#### كيفية الحصول على معلومات العرض لصيغ أخرى
استبدل طريقة المصنع (`forHtmlView()`) بـ `forPdfView()` أو `forImageView()` لاسترجاع البيانات الوصفية لملفات PDF أو معاينات مبنية على الصور على التوالي.

### الأخطاء الشائعة واستكشاف الأخطاء وإصلاحها
- **أخطاء عدم العثور على الملف:** تحقق مرة أخرى من المسار المطلق أو النسبي الذي تمرره إلى مُنشئ `Viewer`.  
- **فقدان مكونات Maven:** تأكد من حل تبعية `groupdocs-viewer`؛ شغّل `mvn clean install` إذا رأيت استثناءات *class not found*.  
- **معالجة المستندات الكبيرة:** استخدم try‑with‑resources لإغلاق `Viewer` تلقائيًا وتحرير الموارد الأصلية.

## التطبيقات العملية
1. **أنظمة إدارة المستندات:** تعبئة حقول البيانات الوصفية تلقائيًا (عدد الصفحات، الصيغة) عندما يرفع المستخدمون ملفات، مما يتيح بحثًا وتصنيفًا فعالًا.  
2. **ميزات المعاينة السريعة:** بناء مكوّن **كيفية معاينة المستند** خفيف الوزن يُظهر الصفحة الأولى أو الصورة المصغرة دون تصيير كامل.  
3. **التحليلات والتقارير:** جمع إحصاءات عدد الصفحات عبر مستودعك لتوقع احتياجات التخزين ومراقبة اتجاهات الاستخدام.

## اعتبارات الأداء
- تخلص من كائنات `Viewer` بسرعة (مثلاً عبر try‑with‑resources) لتحرير المقابض الأصلية.  
- استخرج البيانات الوصفية فقط عند الحاجة؛ تجنّب استدعاءات التصيير الكامل غير الضرورية للحفاظ على استهلاك الذاكرة منخفضًا، خاصةً في سيناريوهات **إدارة المستندات الكبيرة**.

## الأسئلة المتكررة

**س: ما هو هدف `ViewInfoOptions` في GroupDocs Viewer للـ Java؟**  
ج: يحدد للـ API صيغة العرض (HTML، PDF، صورة) التي تريد الحصول على البيانات الوصفية لها، مما يتيح لك **استخراج البيانات الوصفية للمستند** بكفاءة.

**س: هل يمكنني استخدام GroupDocs Viewer للـ Java مع أنواع ملفات غير PDF؟**  
ج: نعم، يدعم أكثر من 50 صيغة — بما في ذلك Word، Excel، PowerPoint، وأنواع الصور الشائعة — مما يجعله مثاليًا لمشاريع **استخراج البيانات الوصفية java**.

**س: كيف يمكنني التعامل مع مستندات ضخمة جدًا دون استنزاف الذاكرة؟**  
ج: استخرج فقط البيانات الوصفية (باستخدام `getViewInfo`) وأغلق `Viewer` فورًا؛ هذه الطريقة تعالج ملفات مئات الصفحات باستخدام أقل من 10 ميغابايت من RAM.

**س: هل يلزم الحصول على ترخيص للاستخدام في الإنتاج؟**  
ج: تتوفر نسخة تجريبية مجانية للتقييم، لكن الترخيص التجاري إلزامي لأي نشر إنتاجي.

**س: ما هي أكثر الأخطاء شيوعًا عند تنفيذ هذه الميزة؟**  
ج: مسارات الملفات غير الصحيحة وفقدان تبعيات Maven هي المشكلات الأكثر شيوعًا. تحقق من موقع المستند وتأكد من إضافة قطعة `groupdocs-viewer` بشكل صحيح إلى ملف `pom.xml` الخاص بك.

## الموارد
- **التوثيق:** [توثيق GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)  
- **مرجع API:** [مرجع GroupDocs API](https://reference.groupdocs.com/viewer/java/)  
- **التنزيل:** [إصدارات GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **الشراء:** [شراء ترخيص GroupDocs](https://purchase.groupdocs.com/buy)  
- **نسخة تجريبية مجانية:** [جرب GroupDocs نسخة تجريبية مجانية](https://releases.groupdocs.com/viewer/java/)  
- **ترخيص مؤقت:** [الحصول على ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/)  
- **الدعم:** [منتدى دعم GroupDocs](https://forum.groupdocs.com/c/viewer/9)

**آخر تحديث:** 2026-09-05  
**تم الاختبار مع:** GroupDocs.Viewer للـ Java 25.2  
**المؤلف:** GroupDocs

## دروس ذات صلة

- [استخراج عدد صفحات PDF والبيانات الوصفية عبر GroupDocs.Viewer Java](/viewer/java/metadata-properties/retrieve-pdf-view-info-groupdocs-java/)  
- [تحميل مستند من URL في Java – درس GroupDocs.Viewer](/viewer/java/document-loading/)  
- [كيفية استرجاع المرفقات في Java وطباعة مرفقات المستند باستخدام GroupDocs.Viewer للـ Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)