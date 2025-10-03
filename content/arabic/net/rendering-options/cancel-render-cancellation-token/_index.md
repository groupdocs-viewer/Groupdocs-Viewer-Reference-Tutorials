---
"description": "قم بدمج Groupdocs.Viewer لـ .NET بسلاسة في مشاريع .NET الخاصة بك لعرض المستندات بكفاءة."
"linktitle": "إلغاء العرض باستخدام رمز الإلغاء"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "إلغاء العرض باستخدام رمز الإلغاء"
"url": "/ar/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# إلغاء العرض باستخدام رمز الإلغاء

## مقدمة
Groupdocs.Viewer لـ .NET أداة فعّالة مصممة لتبسيط عرض المستندات ومعالجتها ضمن تطبيقات .NET. سواء كنت تتعامل مع ملفات PDF أو مستندات Microsoft Office أو غيرها من التنسيقات الشائعة، توفر هذه المكتبة وظائف فعّالة لدمج إمكانيات عرض المستندات بسلاسة في مشاريع .NET الخاصة بك.
## المتطلبات الأساسية
قبل الغوص في تكامل Groupdocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
1. التثبيت: قم بتنزيل وتثبيت مكتبة Groupdocs.Viewer لـ .NET من الدليل المقدم [رابط التحميل](https://releases.groupdocs.com/viewer/net/).
   
2. الترخيص: الحصول على ترخيص من [مجموعة المستندات](https://purchase.groupdocs.com/buy) للاستفادة القصوى من إمكانيات المكتبة. أو يمكنك البدء بفترة تجريبية مجانية باستخدام [رخصة مؤقتة](https://purchase.groupdocs.com/temporary-license/).
   
3. بيئة التطوير: تأكد من إعداد بيئة تطوير متوافقة، بما في ذلك Visual Studio أو أي .NET IDE آخر من اختيارك.

## استيراد مساحات الأسماء
للاستفادة من Groupdocs.Viewer لـ .NET بفعالية، عليك استيراد مساحات الأسماء اللازمة إلى مشروعك. اتبع الخطوات التالية:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

الآن، دعونا نقسم المثال المقدم إلى خطوات متعددة لتحقيق فهم وتنفيذ أفضل:
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
تحدد هذه الخطوة الدليل الذي سيتم تخزين صفحات المستند المعروض فيه.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
هنا، نقوم بتحديد تنسيق مسارات الملفات لصفحات المستند الفردية.
## الخطوة 3: تهيئة CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
يتم استخدام CancellationTokenSource لإنشاء مثيلات CancellationToken التي يمكن استخدامها لإلغاء العمليات غير المتزامنة.
## الخطوة 4: الحصول على رمز الإلغاء
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
تعمل هذه الخطوة على استرداد الرمز من CancellationTokenSource، والذي سيتم استخدامه لإلغاء عملية العرض.
## الخطوة 5: عرض صفحات المستند
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
هنا، نبدأ عرض صفحات المستندات بشكل غير متزامن باستخدام Task.Run(). يتم إنشاء مثيل Viewer بملف المستند المحدد (SAMPLE_DOCX)، ويتم تكوين خيارات العرض. ثم تبدأ عملية العرض باستخدام دالة View من فئة Viewer.
## الخطوة 6: تعيين مهلة العرض
```csharp
cancellationTokenSource.CancelAfter(10);
```
تحدد هذه الخطوة مهلة زمنية قدرها ١٠ ميلي ثانية لعملية العرض. في حال تجاوز هذه المهلة، سيتم إلغاؤها تلقائيًا.
## الخطوة 7: عرض رسالة النجاح
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
وأخيرًا، يتم عرض رسالة نجاح تشير إلى أن عرض المستند قد تم بنجاح.

## خاتمة
في هذا البرنامج التعليمي، تناولنا أساسيات دمج Groupdocs.Viewer لـ .NET في مشاريعك. باتباع الخطوات الموضحة أعلاه، يمكنك دمج إمكانيات عرض المستندات بسلاسة في تطبيقات .NET، مما يُحسّن تجربة المستخدم والإنتاجية.
## الأسئلة الشائعة
### هل Groupdocs.Viewer لـ .NET متوافق مع كافة تنسيقات المستندات؟
يدعم Groupdocs.Viewer لـ .NET مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF، ومستندات Microsoft Office، والصور، والمزيد.
### هل يمكنني تخصيص مظهر صفحات المستند المقدمة؟
نعم، يمكنك تخصيص جوانب مختلفة من عملية العرض، بما في ذلك حجم الصفحة والجودة والعلامة المائية والمزيد.
### هل يتطلب Groupdocs.Viewer لـ .NET اتصالاً بالإنترنت؟
لا، يعمل Groupdocs.Viewer لـ .NET محليًا ضمن بيئة .NET الخاصة بك ولا يتطلب اتصالاً بالإنترنت لعرض المستندات.
### هل يتوفر الدعم الفني لـ Groupdocs.Viewer لـ .NET؟
نعم، الدعم الفني متاح من خلال [منتدى Groupdocs](https://forum.groupdocs.com/c/viewer/9)حيث يمكنك طرح الأسئلة والإبلاغ عن المشكلات والتفاعل مع المجتمع.
### هل يمكنني تجربة Groupdocs.Viewer لـ .NET قبل الشراء؟
نعم، يمكنك البدء بفترة تجريبية مجانية باستخدام الخدمة المقدمة [نسخة تجريبية](https://releases.groupdocs.com/).