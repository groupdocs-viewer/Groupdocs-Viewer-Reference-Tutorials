---
"date": "2025-04-24"
"description": "تعرّف على كيفية تحويل ملفات Excel إلى HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer Java. يغطي هذا الدليل الإعداد وخيارات العرض والتطبيقات العملية."
"title": "كيفية استخدام GroupDocs.Viewer Java لتحويل ملفات Excel إلى HTML/JPG/PNG/PDF - دليل خطوة بخطوة"
"url": "/ar/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
"weight": 1
---

# كيفية استخدام GroupDocs.Viewer Java لتحويل ملفات Excel إلى HTML/JPG/PNG/PDF: دليل خطوة بخطوة

## مقدمة

يُعد تحويل بيانات جداول البيانات إلى صيغ متنوعة مثل HTML وJPG وPNG وPDF، مع الحفاظ على تفاصيل مهمة مثل عناوين الصفوف والأعمدة، أمرًا ضروريًا في العديد من الحالات. سواء كنت تُنشئ تقارير، أو تُشارك معلومات مع الجهات المعنية، أو تُدمج جداول البيانات في تطبيقات الويب، فإن تحويل جداول بيانات Excel يُعدّ متطلبًا أساسيًا. سيُرشدك هذا الدليل إلى كيفية تسهيل GroupDocs.Viewer Java لهذه المهام ودقتها.

**ما سوف تتعلمه:**
- إعداد GroupDocs.Viewer واستخدامه لـ Java
- تحويل ملفات Excel إلى تنسيقات HTML وJPG وPNG وPDF
- تكوين الخيارات لتضمين عناوين الصفوف والأعمدة في مخرجاتك
- التطبيقات العملية للوثائق المقدمة

دعونا نبدأ بالمتطلبات الأساسية اللازمة قبل أن نتعمق في التنفيذ.

## المتطلبات الأساسية

قبل عرض جداول البيانات باستخدام GroupDocs.Viewer Java، تأكد من أن لديك:

### المكتبات والتبعيات المطلوبة

قم بإعداد GroupDocs.Viewer لجافا باستخدام Maven. إليك كيفية تضمينه في مشروعك:

**إعداد Maven:**
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

### إعداد البيئة
- تأكد من تثبيت Java Development Kit (JDK).
- استخدم IDE مثل IntelliJ IDEA أو Eclipse لتسهيل التطوير.

### متطلبات المعرفة
- المعرفة ببرمجة جافا
- فهم أساسي لـ Maven لإدارة التبعيات

بعد وضع هذه المتطلبات الأساسية في مكانها، فلننتقل إلى إعداد GroupDocs.Viewer لـ Java والبدء في تنفيذ الميزات.

## إعداد GroupDocs.Viewer لـ Java

GroupDocs.Viewer لجافا هي مكتبة متعددة الاستخدامات تتيح لك عرض المستندات بتنسيقات متنوعة. إليك كيفية البدء:

### معلومات التثبيت
كما ذكرنا، استخدم Maven لإضافة GroupDocs.Viewer كاعتماد في مشروعك `pom.xml` ملف.

### خطوات الحصول على الترخيص
1. **نسخة تجريبية مجانية:** قم بتنزيل النسخة التجريبية من [النسخة التجريبية المجانية من GroupDocs](https://releases.groupdocs.com/viewer/java/).
2. **رخصة مؤقتة:** احصل على ترخيص مؤقت لمزيد من الميزات من [ترخيص GroupDocs المؤقت](https://purchase.groupdocs.com/temporary-license/).
3. **شراء:** للحصول على الوصول الكامل والدعم، قم بشراء ترخيص من [شراء GroupDocs](https://purchase.groupdocs.com/buy).

### التهيئة الأساسية
بمجرد التثبيت، يمكنك تهيئة GroupDocs.Viewer باستخدام:
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // الكود الخاص بك هنا لاستخدام العارض
        }
    }
}
```
يؤدي هذا إلى تهيئة البيئة الخاصة بك وإعدادك لعرض المستندات.

## دليل التنفيذ

دعونا نقوم بتحليل كل ميزة واستكشاف كيفية تنفيذها بالتفصيل.

### تحويل جدول البيانات إلى HTML
**ملخص:** تحويل جداول بيانات Excel إلى تنسيق HTML مع الحفاظ على عناوين الصفوف والأعمدة للعروض التقديمية أو التقارير على الويب.

#### التنفيذ خطوة بخطوة:
##### 1. استيراد المكتبات المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### 2. تعيين دليل الإخراج
قم بتحديد المكان الذي سيتم تخزين الملفات المقدمة فيه.
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
##### 3. تهيئة العارض وتكوين الخيارات
استخدم GroupDocs.Viewer لعرض المستند:
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // تمكين عرض عناوين الصفوف والأعمدة في جدول البيانات.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // عرض الصفحات من 1 إلى 3.
}
```
**توضيح:** ال `HtmlViewOptions` تُستخدم الفئة لتكوين مخرجات HTML. الإعداد `setRenderHeadings(true)` يضمن أن تكون عناوين الصفوف والأعمدة مرئية في HTML المقدم.

### تحويل جدول البيانات إلى JPG
**ملخص:** قم بتحويل جداول بيانات Excel إلى ملفات صور عالية الجودة (JPG) مع تضمين رؤوس الصفوف والأعمدة، وهي مثالية للعروض التقديمية المرئية أو المطبوعات.

#### التنفيذ خطوة بخطوة:
##### 1. استيراد المكتبات المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```
##### 2. تعيين دليل الإخراج
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```
##### 3. تهيئة العارض وتكوين الخيارات
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // تمكين عرض عناوين الصفوف والأعمدة في جدول البيانات.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // عرض الصفحات من 1 إلى 3.
}
```
**توضيح:** `JpgViewOptions` يتعامل مع إعدادات الصورة. `setRenderHeadings(true)` يضمن الخيار تضمين الرؤوس في إخراج JPG.

### تحويل جدول البيانات إلى PNG
**ملخص:** تحويل جداول Excel إلى تنسيق PNG مع الحفاظ على عناوين الصفوف والأعمدة، وهو مناسب لمخرجات الصور عالية الجودة.

#### التنفيذ خطوة بخطوة:
##### 1. استيراد المكتبات المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```
##### 2. تعيين دليل الإخراج
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 3. تهيئة العارض وتكوين الخيارات
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // تمكين عرض عناوين الصفوف والأعمدة في جدول البيانات.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // عرض الصفحات من 1 إلى 3.
}
```
**توضيح:** `PngViewOptions` يُستخدم لإعدادات PNG. مع `setRenderHeadings(true)`يتم تضمين الرؤوس في الصور الناتجة.

### تحويل جدول البيانات إلى PDF
**ملخص:** قم بتحويل جداول بيانات Excel إلى تنسيق PDF مع التأكد من إمكانية رؤية عناوين الصفوف والأعمدة، وهي مثالية لأرشفة المستندات أو مشاركتها.

#### التنفيذ خطوة بخطوة:
##### 1. استيراد المكتبات المطلوبة
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```
##### 2. تعيين دليل الإخراج
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```
##### 3. تهيئة العارض وتكوين الخيارات
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // تمكين عرض عناوين الصفوف والأعمدة في جدول البيانات.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // عرض الصفحات من 1 إلى 3.
}
```
**توضيح:** `PdfViewOptions` يقوم بتكوين إعدادات إخراج PDF. `setRenderHeadings(true)` يضمن الخيار ظهور الرؤوس في ملف PDF النهائي.

## التطبيقات العملية
فيما يلي بعض السيناريوهات الواقعية حيث يمكن تطبيق هذه الميزات:

1. **تقارير الأعمال:** قم بمشاركة التقارير التفصيلية مع أصحاب المصلحة عن طريق تحويل بيانات Excel إلى تنسيقات HTML أو PDF لسهولة نشرها وعرضها.
2. **التصور البياني للبيانات:** قم بتحويل جداول البيانات إلى تنسيقات صور مثل JPG أو PNG للعروض التقديمية، مع التأكد من أن العناوين توفر سياقًا للبيانات المرئية.
3. **أرشفة المستندات:** استخدم تحويل PDF لأرشفة المستندات بتنسيق يمكن الوصول إليه عالميًا، مع الحفاظ على جميع التفاصيل الضرورية مثل العناوين.