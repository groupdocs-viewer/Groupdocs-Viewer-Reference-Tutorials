---
"date": "2025-04-25"
"description": "تعرف على كيفية تحويل ملفات TXT إلى تنسيقات متعددة مثل HTML وJPG وPNG وPDF باستخدام GroupDocs.Viewer لـ .NET باستخدام هذا الدليل الشامل."
"title": "تحويل TXT إلى HTML، JPG، PNG، PDF باستخدام GroupDocs.Viewer .NET - دليل كامل"
"url": "/ar/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
type: docs
---
# تحويل TXT إلى تنسيقات متعددة باستخدام GroupDocs.Viewer .NET

## مقدمة

هل ترغب في تحويل مستندات نصية إلى صيغ مختلفة مثل HTML أو JPG أو PNG أو PDF بسهولة؟ قد تكون إدارة تحويلات المستندات صعبة، خاصةً عند التعامل مع صفحات متعددة أو متطلبات تنسيق محددة. **GroupDocs.Viewer لـ .NET** يُبسط عملية تحويل ملفات TXT إلى تنسيقات إخراج متنوعة، مما يضمن إمكانية الوصول إلى بياناتك وجاذبيتها البصرية.

![تحويل TXT إلى HTML، JPG، PNG، PDF باستخدام GroupDocs.Viewer لـ .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

في هذا الدليل، سنستكشف كيفية استخدام GroupDocs.Viewer لـ .NET لتحويل مستندات TXT إلى HTML متعدد الصفحات، وHTML أحادي الصفحة، وJPG، وPNG، وPDF. في النهاية، ستتقن:
- تحويل ملفات TXT باستخدام C# مع GroupDocs.Viewer
- تنفيذ خيارات عرض مختلفة لتناسب احتياجاتك
- تحسين الأداء أثناء التحويلات

دعنا نتعمق في حل تحديات تحويل المستندات الخاصة بك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي جاهزًا:
- **بيئة التطوير**:Visual Studio 2019 أو أحدث.
- **إطار عمل .NET**:الإصدار 4.6.1 أو أعلى.
- **مكتبة GroupDocs.Viewer لـ .NET**:
  - عبر وحدة تحكم مدير الحزم NuGet: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - استخدام .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

من المستحسن أن تكون على دراية ببرمجة C# وعمليات الملفات الأساسية في .NET لتتمكن من المتابعة بسهولة.

## إعداد GroupDocs.Viewer لـ .NET

### تثبيت

للبدء، قم بتثبيت **عارض GroupDocs** المكتبة باستخدام مدير الحزم المفضل لديك:

#### وحدة تحكم مدير الحزم NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### الترخيص

يمكنك البدء بـ **نسخة تجريبية مجانية** أو الحصول على **رخصة مؤقتة** لاستكشاف الإمكانات الكاملة لـ GroupDocs.Viewer لـ .NET دون قيود التقييم:
- نسخة تجريبية مجانية: [التحميل هنا](https://releases.groupdocs.com/viewer/net/)
- رخصة مؤقتة: [اطلب هنا](https://purchase.groupdocs.com/temporary-license/)

للاستخدام المستمر، فكر في شراء ترخيص مباشرة من [مجموعة المستندات](https://purchase.groupdocs.com/buy).

### التهيئة الأساسية

لإعداد GroupDocs.Viewer في مشروعك:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// قم بتهيئة كائن العارض باستخدام مسار ملف TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // سيتم وضع كود العرض الخاص بك هنا.
}
```

## دليل التنفيذ

الآن، دعنا نتعمق في كل ميزة ونرى كيف يمكنك تنفيذها.

### تحويل مستند TXT إلى HTML متعدد الصفحات

#### ملخص
توضح هذه الميزة تحويل مستند TXT إلى صيغة HTML متعددة الصفحات. تُعرض كل صفحة من الملف النصي كملف HTML مستقل مع موارد مُضمنة.

#### الخطوة 1: إعداد العارض

إنشاء `Viewer` كائن لملف TXT المصدر الخاص بك:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// قم بتهيئة العارض باستخدام ملف نصي نموذجي.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // انتقل إلى الخطوة 2...
```

#### الخطوة 2: تكوين خيارات عرض HTML

يثبت `HtmlViewOptions` لعرض كل صفحة على حدة:

```csharp
// إعداد خيارات عرض HTML لعرض صفحات متعددة.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// عرض المستند بصيغة HTML متعددة الصفحات.
viewer.View(options);
}
```

**توضيح**: ال `ForEmbeddedResources()` تضمن الطريقة تضمين الموارد مثل الصور والأنماط مباشرة داخل ملف HTML، مما يسهل المشاركة.

### تحويل مستند TXT إلى صفحة HTML واحدة

#### ملخص
تحويل مستند TXT إلى صفحة HTML واحدة، وهو أمر مثالي للمستندات التي تحتاج إلى عرضها كصفحة ويب واحدة مستمرة.

#### الخطوة 1: إعداد العارض

تهيئة `Viewer` هدف:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// قم بإنشاء مثيل عارض جديد لملف نصي مختلف.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // انتقل إلى الخطوة 2...
```

#### الخطوة 2: تكوين خيارات HTML للصفحة الفردية

تكوين `HtmlViewOptions` مع تمكين إعداد الصفحة الفردية:

```csharp
// إعداد خيارات العرض في صفحة HTML واحدة.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// عرض كصفحة HTML واحدة.
viewer.View(options);
}
```

**توضيح**: ال `RenderToSinglePage` تضمن الخاصية عرض المحتوى بأكمله على صفحة واحدة.

### تحويل مستند TXT إلى JPG

#### ملخص
تتيح لك هذه الميزة تحويل مستند نصي إلى صورة JPEG، وهي مفيدة للعروض التقديمية المرئية أو لأغراض الأرشفة.

#### الخطوة 1: إعداد العارض

جهز نفسك `Viewer` هدف:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// قم بتهيئة العارض باستخدام ملف عينة.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // انتقل إلى الخطوة 2...
```

#### الخطوة 2: تكوين خيارات عرض JPG

يثبت `JpgViewOptions` لتقديم الصورة:

```csharp
// إعداد خيارات العرض كصورة JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// تقديم المستند كملف JPEG.
viewer.View(options);
}
```

**توضيح**: ال `JpgViewOptions` تحدد الفئة كيفية عرض كل صفحة من مستندك وحفظها بتنسيق JPEG.

### تحويل مستند TXT إلى PNG

#### ملخص
تحويل مستند نصي إلى تنسيق PNG، مما يوفر إخراج صورة عالية الجودة مع دعم الشفافية.

#### الخطوة 1: إعداد العارض

تهيئة `Viewer` هدف:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// قم بإنشاء مثيل عارض لملف TXT الخاص بك.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // انتقل إلى الخطوة 2...
```

#### الخطوة 2: تكوين خيارات عرض PNG

يثبت `PngViewOptions`:

```csharp
// إعداد خيارات العرض للعرض كصورة PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// تقديم المستند بتنسيق PNG.
viewer.View(options);
}
```

**توضيح**: ال `PngViewOptions` تتيح الفئة عرض كل صفحة بشفافية، مما يجعلها مناسبة للرسومات الطبقية.

### تحويل مستند TXT إلى PDF

#### ملخص
تعتبر هذه الميزة مثالية لتحويل المستندات النصية إلى تنسيق PDF يمكن الوصول إليه عالميًا.

#### الخطوة 1: إعداد العارض

جهز نفسك `Viewer` هدف:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// قم بإنشاء مثيل عارض لملف النص الخاص بك.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // انتقل إلى الخطوة 2...
```

#### الخطوة 2: تكوين خيارات عرض PDF

يثبت `PdfViewOptions`:

```csharp
// إعداد خيارات العرض للتقديم كمستند PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// تحويل المستند إلى ملف PDF.
viewer.View(options);
}
```

**توضيح**: ال `PdfViewOptions` تحدد الفئة كيفية تحويل ملفات TXT وحفظها كمستندات PDF.

## خاتمة

مع GroupDocs.Viewer لـ .NET، أصبح تحويل المستندات النصية إلى صيغ مختلفة أمرًا سهلاً. غطّى هذا الدليل تحويل ملفات TXT إلى HTML متعدد الصفحات، وHTML أحادي الصفحة، وJPG، وPNG، وPDF باستخدام C#. سواء كنت ترغب في تحسين إمكانية الوصول إلى المستندات أو توافقها، توفر هذه الطرق حلولاً فعّالة.

لمزيد من المساعدة أو الميزات الأكثر تقدمًا، راجع [الوثائق الرسمية لـ GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/).برمجة سعيدة!