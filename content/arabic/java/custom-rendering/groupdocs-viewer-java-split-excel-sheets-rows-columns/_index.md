---
date: '2026-06-15'
description: تعلم كيفية تحويل Excel إلى PDF باستخدام Java وتقسيم أوراق Excel حسب الصفوف
  والأعمدة باستخدام GroupDocs Viewer. يتضمن الإعداد، الكود، وأفضل الممارسات.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: تحويل Excel إلى PDF باستخدام Java وتقسيم الأوراق حسب الصفوف والأعمدة
type: docs
url: /ar/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# تحويل Excel إلى PDF Java وتقسيم الأوراق حسب الصفوف والأعمدة (Java)

غالبًا ما تحتوي دفاتر Excel الكبيرة على بيانات أكثر مما يمكن عرضه بشكل مريح على شاشة واحدة أو صفحة مطبوعة. **convert excel to pdf java** هو طلب شائع عندما تحتاج إلى تنسيق ثابت يمكن مشاركته، بينما **splitting Excel sheets by rows and columns** يجعل البيانات أسهل في الاستهلاك في تخطيطات الويب أو الطباعة. في هذا الدليل سنستعرض كلا المهمتين باستخدام **GroupDocs Viewer for Java**، ونوضح لك كيفية تكوين التقسيم إلى صفحات، ونشرح نصائح الممارسات الأفضل للأداء وحل المشكلات.

![Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Split Excel Sheets by Rows and Columns with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## إجابات سريعة
- **ما المكتبة المستخدمة؟** GroupDocs Viewer for Java.  
- **هل يمكنني التقسيم حسب كل من الصفوف والأعمدة؟** نعم – يمكنك تحديد rows‑per‑page و columns‑per‑page معًا.  
- **هل أحتاج إلى ترخيص؟** الترخيص التجريبي أو المؤقت يعمل للتطوير؛ الترخيص الكامل مطلوب للإنتاج.  
- **ما صيغ الإخراج المدعومة؟** يتم عرض HTML (الموارد المدمجة)؛ يمكن إنشاء PDF باستخدام نفس الخيارات.  
- **هل Maven مطلوب؟** Maven هو الطريقة الموصى بها لإدارة التبعيات.  
- **هل يمكنني أيضًا تحويل Excel إلى PDF؟** بالتأكيد – فقط استبدل `HtmlViewOptions` بـ `PdfViewOptions` وأعد استخدام نفس إعدادات التقسيم إلى صفحات.

## ما هو “How to Split Excel”؟
تقسيم ورقة Excel يعني تقسيم ورقة عمل واحدة إلى صفحات أو ملفات متعددة بناءً على عدد ثابت من الصفوف أو الأعمدة أو كليهما. هذه التقنية مفيدة عندما تحتاج إلى إنشاء تقارير مقسمة إلى صفحات، أو تضمين البيانات في صفحات الويب، أو إنشاء أقسام قابلة للطباعة دون تحميل دفتر العمل بالكامل مرة واحدة.

## لماذا تستخدم GroupDocs Viewer for Java؟
يعالج GroupDocs Viewer جداول البيانات في مرور واحد ويقسمها تلقائيًا إلى صفحات، مما يلغي الحاجة إلى حسابات يدوية. **Fast rendering processes a 250‑page XLSX workbook in under 2 seconds on a typical 2‑core server**, و**the library supports 50+ input and output formats**, بما في ذلك XLS و XLSX و CSV و PDF و HTML. يعمل على أي منصة متوافقة مع JVM — Windows و Linux و macOS وحاويات Docker أو بيئات الخادم غير المتصلة السحابية — بحيث يمكنك دمجه أينما كان تطبيق Java الخاص بك.

## المتطلبات المسبقة
- Java 17 أو أحدث مثبت.  
- IDE مثل IntelliJ IDEA أو Eclipse.  
- Maven لإدارة التبعيات.  
- معرفة أساسية بـ Java وإلمام بمعالجة ملفات Excel.

### المكتبات المطلوبة والإصدارات والتبعيات
أضف مستودع GroupDocs واعتماد Viewer إلى ملف `pom.xml` الخاص بك:

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
احصل على نسخة تجريبية مجانية، أو ترخيص مؤقت، أو اشترِ ترخيصًا كاملاً من [GroupDocs](https://purchase.groupdocs.com/buy).

## كيفية تحويل Excel إلى PDF Java؟

`Viewer` class هو المكوّن الأساسي في GroupDocs Viewer الذي يحمل المستند ويوفر طرق عرض لمختلف صيغ الإخراج. `SpreadsheetOptions` يسمح لك بالتحكم في إعدادات التقسيم إلى صفحات مثل rows‑per‑page و columns‑per‑page لتصوير جداول البيانات.

حمّل ملف Excel الخاص بك باستخدام `new Viewer("source.xlsx")`، قم بتكوين `SpreadsheetOptions` للتقسيم إلى صفحات، واستدعِ `viewer.view(pdfOptions, stream)` – هذا الاستدعاء الواحد يحول دفتر العمل إلى PDF مع احترام حدود الصفوف/الأعمدة التي حددتها. يحافظ التحويل على الصيغ، والصور، وأنماط الخلايا، مقدماً نسخة PDF دقيقة جاهزة للتوزيع.

## كيفية تقسيم أوراق Excel حسب الصفوف

إنشاء تقسيم حسب الصفوف يولد سلسلة من صفحات HTML، كل منها يحتوي على عدد ثابت من الصفوف (مثلاً 15). هذا النهج مثالي للوحة معلومات تعرض عددًا محدودًا من السجلات في كل عرض. سيولد المشاهد ملفات HTML منفصلة مثل `page_0.html`، `page_1.html`، إلخ، كل منها يحتوي على عدد الصفوف المحدد. هذا يجعل من السهل تحميل الجزء المطلوب فقط في واجهة الويب، مما يقلل من استهلاك النطاق الترددي ووقت التصوير.

### تعريف العنصر المرجعي
`Viewer` هو الفئة الأساسية في GroupDocs Viewer التي تحمل المستند وتنسق عملية العرض إلى صيغة الإخراج المختارة.

### تنفيذ خطوة بخطوة

#### الخطوة 1: إعداد المسارات وتهيئة الـ Viewer
أولاً، حدد مكان حفظ الصفحات المقسمة وأنشئ مثيل `Viewer` لدفتر العمل المصدر.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### الخطوة 2: تكوين عدد الصفوف لكل صفحة
أخبر الـ Viewer بعدد الصفوف التي يجب أن يحتويها كل صفحة.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### الخطوة 3: عرض المستند
أخيرًا، اعرض دفتر العمل باستخدام الخيارات التي حددتها.

```java
viewer.view(viewOptions);
```

## كيفية تقسيم أوراق Excel حسب الصفوف والأعمدة

أحيانًا تحتاج صفحة واحدة إلى عرض مصفوفة من الصفوف **والأعمدة** (مثلاً 15 صفًا × 7 أعمدة). يمنحك هذا تحكمًا كاملاً في تخطيط كل صفحة HTML. تعرض الصفحات الناتجة كتلة مستطيلة من الخلايا، على سبيل المثال الصفوف 1‑15 والأعمدة A‑G في الصفحة الأولى، الصفوف 16‑30 والأعمدة H‑N في الصفحة التالية. هذا التقسيم على شكل شبكة مفيد لإنشاء تقارير قابلة للطباعة تتناسب مع أحجام الورق القياسية.

### تعريف العنصر المرجعي
`SpreadsheetOptions` يحدد عدد الصفوف والأعمدة التي تظهر في كل صفحة مُولدة.

### تنفيذ خطوة بخطوة

#### الخطوة 1: إعداد المسارات وتهيئة الـ Viewer
الإعداد يطابق مثال الصفوف فقط، فقط اسم الملف يتغير.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### الخطوة 2: تكوين الصفوف والأعمدة لكل صفحة
حدد كلا البعدين لإنشاء تقسيم على شكل شبكة.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### الخطوة 3: عرض المستند
اعرض باستخدام نفس استدعاء `view`.

```java
viewer.view(options);
```

## تطبيقات عملية
- **Generate Excel report Java**: تحويل النماذج المالية الكبيرة إلى سلسلة من تقارير HTML مقسمة إلى صفحات.  
- **GroupDocs Viewer Excel**: تضمين الصفحات المقسمة مباشرةً في بوابة ويب لاستكشاف البيانات التفاعلي.  
- **Render Excel HTML Java**: تقديم صفحات HTML المولدة عبر servlet أو Spring controller لتصوير سريع على جانب العميل.  

## اعتبارات الأداء
- **Memory usage** – قد تستهلك دفاتر العمل الكبيرة كمية كبيرة من الذاكرة؛ فكر في زيادة إعداد JVM `-Xmx`.  
- **Chunk size** – اختر عدد الصفوف/الأعمدة الذي يوازن بين حجم الصفحة وسرعة العرض.  
- **Version updates** – حافظ على تحديث GroupDocs Viewer للاستفادة من تحسينات الأداء؛ الإصدار الأخير 25.2 يحسن سرعة العرض بنسبة تصل إلى 30 % مقارنةً بـ 24.x.

## المشكلات الشائعة وحلولها
| العَرَض | السبب المحتمل | الحل |
|---------|--------------|-----|
| `OutOfMemoryError` | عرض ورقة كبيرة جدًا مع عدد كبير من الصفوف لكل صفحة | قلل `countRowsPerPage` أو زد حجم الذاكرة JVM |
| ملفات إخراج فارغة | مسار ملف غير صحيح أو عدم وجود أذونات كتابة | تحقق من وجود `outputDirectory` وأنه قابل للكتابة |
| موارد HTML لا يتم تحميلها | استخدام `forEmbeddedResources` لكن تقديم الملفات من عنوان URL أساسي مختلف | قدّم مجلد الإخراج بالكامل أو بدّل إلى `forExternalResources` |

## الأسئلة المتكررة

**س: هل يمكنني إنشاء PDF بدلاً من HTML؟**  
ج: نعم. استبدل `HtmlViewOptions` بـ `PdfViewOptions` واحتفظ بنفس تكوين `SpreadsheetOptions`.

**س: هل يمكن التقسيم بناءً على محتوى الخلية بدلاً من الصفوف/الأعمدة الثابتة؟**  
ج: التقسيم المبني على المحتوى غير مدعوم في GroupDocs Viewer، لكن يمكنك معالجة دفتر العمل مسبقًا باستخدام Apache POI لإنشاء أوراق منفصلة قبل العرض.

**س: هل يدعم GroupDocs Viewer صيغ Excel القديمة (XLS)؟**  
ج: بالتأكيد. يدعم المشاهد صيغ XLS و XLSX و CSV وغيرها من صيغ جداول البيانات.

**س: كيف يمكنني تضمين HTML المولد في عرض Spring MVC؟**  
ج: قدّم مجلد الإخراج كموارد ثابتة وأشر إلى ملفات `page_0.html`، `page_1.html`، إلخ من قوالب Thymeleaf أو JSP الخاصة بك.

**س: ما الترخيص المطلوب للنشر التجاري؟**  
ج: يلزم الحصول على ترخيص إنتاج كامل من GroupDocs؛ الترخيص التجريبي مخصص للتقييم فقط.

## الموارد
- **الوثائق**: [توثيق GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **مرجع API**: [مرجع API لـ GroupDocs Viewer Java](https://reference.groupdocs.com/viewer/java/)
- **التنزيل**: [إصدارات GroupDocs Viewer Java](https://releases.groupdocs.com/viewer/java/)
- **الشراء**: [شراء ترخيص GroupDocs](https://purchase.groupdocs.com/buy)
- **نسخة تجريبية مجانية**: [تجربة GroupDocs المجانية](https://releases.groupdocs.com/viewer/java/)
- **ترخيص مؤقت**: [الحصول على ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/)
- **الدعم**: [منتدى دعم GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**آخر تحديث:** 2026-06-15  
**تم الاختبار مع:** GroupDocs Viewer 25.2 for Java  
**المؤلف:** GroupDocs  

---

## دروس ذات صلة

- [عرض الصفوف والأعمدة المخفية في جداول Java باستخدام GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [تخطي عرض الصفوف الفارغة في Java باستخدام GroupDocs.Viewer: دليل الأداء](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [دليل شامل: تحويل Excel 2003 XML إلى HTML/JPG/PNG/PDF باستخدام GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)