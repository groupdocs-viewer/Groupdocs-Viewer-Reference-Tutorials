---
"description": "تعلّم كيفية استبدال الخطوط المفقودة في مستندات .NET بسهولة باستخدام GroupDocs.Viewer. تمتع بدقة عرض عالية بخطوات بسيطة."
"linktitle": "استبدال الخط المفقود"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "استبدال الخط المفقود"
"url": "/ar/net/rendering-options/replace-missing-font/"
"weight": 20
type: docs
---
# استبدال الخط المفقود

## مقدمة
في عالم تطوير .NET، تُعد معالجة المستندات بكفاءة أمرًا بالغ الأهمية. يوفر GroupDocs.Viewer لـ .NET حلاً فعالاً لعرض تنسيقات المستندات المختلفة داخل تطبيقات .NET. في هذا البرنامج التعليمي، سنستكشف كيفية استخدام GroupDocs.Viewer لـ .NET لاستبدال الخطوط المفقودة في المستندات. سواء كنت تتعامل مع ملفات PDF أو عروض PowerPoint التقديمية أو مستندات Word، يُبسط GroupDocs.Viewer العملية، ويضمن عرض مستنداتك بدقة، حتى في حالة عدم وجود خطوط.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. GroupDocs.Viewer لـ .NET: قم بتنزيل مكتبة GroupDocs.Viewer وتثبيتها من موقع الويب](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير .NET، مثل Visual Studio.
3. المعرفة الأساسية بلغة C#: الإلمام بلغة البرمجة C# وإطار عمل .NET.

## استيراد مساحات الأسماء
في كود C# الخاص بك، قم باستيراد المساحات الأساسية اللازمة للوصول إلى وظائف GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن، دعنا نستعرض عملية استبدال الخطوط المفقودة في المستندات باستخدام GroupDocs.Viewer لـ .NET.
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
قم بتعيين الدليل الذي سيتم حفظ صفحات المستند المعروض فيه.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
حدد صيغة تسمية ملفات HTML الناتجة. في هذا المثال، سيتم حفظ كل صفحة كملف HTML باستخدام الصيغة "page_{page_number}.html".
## الخطوة 3: تهيئة كائن العارض
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
قم بتهيئة مثيل جديد لفئة Viewer، وتمرير المسار إلى ملف المستند (في هذه الحالة، عرض تقديمي في PowerPoint يحتوي على خطوط مفقودة) كمعلمة.
## الخطوة 4: تعيين خيارات عرض HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
أنشئ مثيلًا لـ HtmlViewOptions وقم بتكوينه لتضمين الموارد في مُخرَجات HTML. حدد اسم خط افتراضيًا لاستخدامه كبديل للخطوط المفقودة.
## الخطوة 5: عرض المستند
```csharp
viewer.View(options);
```
استدعِ طريقة العرض لكائن العارض، مع تمرير خيارات عرض HTML. سيؤدي هذا إلى عرض صفحات المستند باستخدام الخيارات المحددة.
## الخطوة 6: عرض مسار الإخراج
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
اطبع رسالة تشير إلى نجاح عرض المستند وتوفير المسار الذي يتم حفظ ملفات HTML الناتجة فيه.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام GroupDocs.Viewer لـ .NET لاستبدال الخطوط المفقودة في المستندات. باتباع هذه الخطوات، يمكنك ضمان دقة عرض مستنداتك، حتى في حال عدم توفر بعض الخطوط. يُبسط GroupDocs.Viewer العملية، مما يتيح لك التركيز على بناء تطبيقات .NET قوية دون القلق بشأن مشاكل توافق الخطوط.
## الأسئلة الشائعة
### هل يمكن لـ GroupDocs.Viewer التعامل مع أنواع أخرى من المشكلات المتعلقة بالخطوط؟
نعم، يوفر GroupDocs.Viewer العديد من الوظائف المتعلقة بالخطوط، بما في ذلك استبدال الخطوط واكتشاف الخطوط.
### هل GroupDocs.Viewer متوافق مع كافة أطر عمل .NET؟
يدعم GroupDocs.Viewer مجموعة واسعة من أطر عمل .NET، بما في ذلك .NET Core و.NET Standard.
### هل يمكنني تخصيص استبدال الخط الافتراضي في GroupDocs.Viewer؟
بالتأكيد، يمكنك تحديد أي خط من اختيارك كبديل افتراضي للخطوط المفقودة.
### هل يدعم GroupDocs.Viewer المعالجة الدفعية للمستندات؟
نعم، يسمح لك GroupDocs.Viewer بمعالجة مستندات متعددة في وقت واحد، مما يجعله مثاليًا لسيناريوهات المعالجة الدفعية.
### أين يمكنني العثور على مزيد من المساعدة أو الدعم لـ GroupDocs.Viewer؟
يمكنك زيارة منتدى GroupDocs.Viewer [هنا](https://forum.groupdocs.com/c/viewer/9) لأي استفسارات حول المساعدة أو الدعم.