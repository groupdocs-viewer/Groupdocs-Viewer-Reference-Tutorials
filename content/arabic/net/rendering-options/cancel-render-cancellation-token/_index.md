---
title: قم بإلغاء العرض باستخدام رمز الإلغاء
linktitle: قم بإلغاء العرض باستخدام رمز الإلغاء
second_title: GroupDocs.Viewer .NET API
description: قم بدمج Groupdocs.Viewer لـ .NET بسلاسة في مشاريع .NET الخاصة بك لعرض المستندات بكفاءة.
weight: 11
url: /ar/net/rendering-options/cancel-render-cancellation-token/
---

# قم بإلغاء العرض باستخدام رمز الإلغاء

## مقدمة
يعد Groupdocs.Viewer for .NET أداة قوية مصممة لتبسيط عرض المستندات ومعالجتها داخل تطبيقات .NET. سواء كنت تتعامل مع ملفات PDF، أو مستندات Microsoft Office، أو التنسيقات الشائعة الأخرى، توفر هذه المكتبة وظائف قوية لدمج إمكانات عرض المستندات بسلاسة في مشاريع .NET الخاصة بك.
## المتطلبات الأساسية
قبل الغوص في تكامل Groupdocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
1.  التثبيت: قم بتنزيل وتثبيت Groupdocs.Viewer لمكتبة .NET من الملف المتوفر[رابط التحميل](https://releases.groupdocs.com/viewer/net/).
   
2.  الترخيص: الحصول على ترخيص من[مستندات جماعية](https://purchase.groupdocs.com/buy) لفتح الإمكانات الكاملة للمكتبة. وبدلاً من ذلك، يمكنك البدء بتجربة مجانية باستخدام[ترخيص مؤقت](https://purchase.groupdocs.com/temporary-license/).
   
3. بيئة التطوير: تأكد من إعداد بيئة تطوير متوافقة، بما في ذلك Visual Studio أو أي .NET IDE آخر من اختيارك.

## استيراد مساحات الأسماء
للاستفادة من Groupdocs.Viewer لـ .NET بشكل فعال، تحتاج إلى استيراد مساحات الأسماء الضرورية إلى مشروعك. اتبع الخطوات التالية:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

الآن، دعنا نقسم المثال المقدم إلى خطوات متعددة لفهم وتنفيذ أفضل:
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
تقوم هذه الخطوة بتعيين الدليل حيث سيتم تخزين صفحات المستند المعروضة.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
هنا، نحدد تنسيق مسارات الملفات لصفحات المستندات الفردية.
## الخطوة 3: تهيئة CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
يتم استخدام CancellationTokenSource لإنشاء مثيلات CancellationToken التي يمكن استخدامها لإلغاء العمليات غير المتزامنة.
## الخطوة 4: الحصول على CancelToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
تسترد هذه الخطوة الرمز المميز من CancellationTokenSource، والذي سيتم استخدامه لإلغاء عملية العرض.
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
هنا، نبدأ في عرض صفحات المستند بشكل غير متزامن باستخدام Task.Run(). يتم إنشاء مثيل العارض باستخدام ملف المستند المحدد (SAMPLE_DOCX)، ويتم تكوين خيارات العرض. تبدأ عملية العرض بعد ذلك باستخدام طريقة العرض لفئة العارض.
## الخطوة 6: تعيين مهلة العرض
```csharp
cancellationTokenSource.CancelAfter(10);
```
تحدد هذه الخطوة مهلة قدرها 10 مللي ثانية لعملية العرض. إذا تجاوزت العملية هذه المهلة، فسيتم إلغاؤها تلقائيًا.
## الخطوة 7: عرض رسالة النجاح
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
وأخيرًا، يتم عرض رسالة نجاح تشير إلى أنه تم تقديم المستند بنجاح.

## خاتمة
في هذا البرنامج التعليمي، قمنا بتغطية أساسيات دمج Groupdocs.Viewer لـ .NET في مشاريعك. باتباع الخطوات الموضحة أعلاه، يمكنك دمج إمكانيات عرض المستندات في تطبيقات .NET الخاصة بك بسلاسة، مما يعزز تجربة المستخدم والإنتاجية.
## الأسئلة الشائعة
### هل يتوافق Groupdocs.Viewer for .NET مع كافة تنسيقات المستندات؟
يدعم Groupdocs.Viewer for .NET نطاقًا واسعًا من تنسيقات المستندات، بما في ذلك PDF ومستندات Microsoft Office والصور والمزيد.
### هل يمكنني تخصيص مظهر صفحات المستندات المعروضة؟
نعم، يمكنك تخصيص جوانب مختلفة من عملية العرض، بما في ذلك حجم الصفحة والجودة والعلامة المائية والمزيد.
### هل يتطلب Groupdocs.Viewer for .NET اتصالاً بالإنترنت؟
لا، يعمل Groupdocs.Viewer for .NET محليًا ضمن بيئة .NET الخاصة بك ولا يتطلب الاتصال بالإنترنت لعرض المستندات.
### هل يتوفر الدعم الفني لـ Groupdocs.Viewer لـ .NET؟
 نعم، الدعم الفني متوفر من خلال[منتدى المستندات الجماعية](https://forum.groupdocs.com/c/viewer/9)حيث يمكنك طرح الأسئلة والإبلاغ عن المشكلات والتفاعل مع المجتمع.
### هل يمكنني تجربة Groupdocs.Viewer لـ .NET قبل الشراء؟
 نعم، يمكنك البدء بالإصدار التجريبي المجاني باستخدام البرنامج المقدم[نسخه تجريبيه](https://releases.groupdocs.com/).