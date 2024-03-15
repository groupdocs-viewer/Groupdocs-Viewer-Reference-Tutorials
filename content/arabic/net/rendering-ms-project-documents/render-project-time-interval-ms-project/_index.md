---
title: عرض الفاصل الزمني المحدد للمشروع (مشروع MS)
linktitle: عرض الفاصل الزمني المحدد للمشروع (مشروع MS)
second_title: GroupDocs.Viewer .NET API
description: قم بدمج GroupDocs.Viewer لـ .NET بسلاسة في تطبيقاتك لعرض المستندات بكفاءة. عزز الإنتاجية من خلال إمكانيات العرض المتنوعة.
type: docs
weight: 12
url: /ar/net/rendering-ms-project-documents/render-project-time-interval-ms-project/
---
## مقدمة
في مجال تطوير البرمجيات، تعد المعالجة والعرض الفعال لتنسيقات المستندات المختلفة أمرًا بالغ الأهمية. سواء كان الأمر يتعلق بعرض المستندات أو معالجتها، فإن امتلاك الأدوات المناسبة يمكن أن يؤدي إلى تحسين الإنتاجية وتبسيط العمليات بشكل كبير. يبرز GroupDocs.Viewer for .NET كحل متعدد الاستخدامات، حيث يوفر للمطورين القدرة على دمج إمكانات عرض المستندات بسلاسة في تطبيقات .NET الخاصة بهم.
## المتطلبات الأساسية
قبل الغوص في تكامل GroupDocs.Viewer لـ .NET، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. الإلمام ببرنامج .NET Framework
تأكد من أن لديك الفهم الأساسي لإطار عمل .NET، بما في ذلك لغة البرمجة C# وVisual Studio IDE.
### 2. تثبيت GroupDocs.Viewer لـ .NET
 قم بتنزيل وتثبيت GroupDocs.Viewer لـ .NET من[رابط التحميل](https://releases.groupdocs.com/viewer/net/). اتبع تعليمات التثبيت المتوفرة لإعداد المكتبة ضمن بيئة التطوير الخاصة بك.
### 3. الترخيص ساري المفعول أو الترخيص المؤقت
 الحصول على ترخيص ساري المفعول من[مستندات المجموعة](https://purchase.groupdocs.com/buy) أو الحصول على ترخيص مؤقت من[هنا](https://purchase.groupdocs.com/temporary-license/) للاستفادة من الوظائف الكاملة لـ GroupDocs.Viewer لـ .NET.
### 4. نموذج الوثيقة
احصل على نموذج مستند، مثل ملف MS Project، جاهز لاختبار وظيفة العرض.

## استيراد مساحات الأسماء
قم بدمج مساحات الأسماء الضرورية في مشروعك للوصول إلى الوظائف التي يوفرها GroupDocs.Viewer لـ .NET.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

دعنا نقسم مثال عرض فاصل زمني محدد لمشروع من ملف MS Project إلى خطوات متعددة:
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
حدد الدليل الذي سيتم حفظ صفحات HTML المعروضة فيه.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
قم بتعيين تنسيق مسار الملف لكل صفحة HTML معروضة.
## الخطوة 3: إنشاء كائن العارض
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
قم بإنشاء مثيل لفئة Viewer، وتمرير المسار إلى نموذج ملف MS Project.
## الخطوة 4: تكوين خيارات عرض HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
قم بتكوين خيارات عرض HTML للعرض، مع تحديد تنسيق الموارد المضمنة.
## الخطوة 5: استرداد معلومات عرض إدارة المشروع
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
استرجاع معلومات عرض إدارة المشروع لتحديد تاريخي البدء والانتهاء للمشروع.
## الخطوة 6: تعيين تاريخي البدء والانتهاء
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
قم بتعيين تاريخي البدء والانتهاء للفاصل الزمني للمشروع الذي سيتم عرضه.
## الخطوة 7: تقديم الوثيقة
```csharp
viewer.View(options);
```
ابدأ عملية العرض باستخدام الخيارات المحددة.
## الخطوة 8: عرض دليل الإخراج
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
قم بإعلام المستخدم بالعرض الناجح واعرض الدليل الذي تم حفظ الإخراج فيه.

## خاتمة
يمكّنك دمج GroupDocs.Viewer لـ .NET في مشاريعك من التعامل بكفاءة مع مهام عرض المستندات، مما يعزز تجربة المستخدم والإنتاجية. باتباع الدليل الموضح خطوة بخطوة، يمكنك دمج وظائف عرض المستندات بسلاسة في تطبيقات .NET الخاصة بك.
## الأسئلة الشائعة
### هل يتوافق GroupDocs.Viewer for .NET مع كافة تنسيقات المستندات؟
يدعم GroupDocs.Viewer for .NET نطاقًا واسعًا من تنسيقات المستندات، بما في ذلك Microsoft Office وPDF وCAD والمزيد.
### هل يمكنني تخصيص مظهر المستندات المقدمة؟
نعم، يمكنك تخصيص جوانب مختلفة من عملية العرض، مثل تخطيط الصفحة، والعلامة المائية، وتدوير الصفحة.
### هل GroupDocs.Viewer for .NET مناسب لتطبيقات الويب؟
بالتأكيد، يمكن دمج GroupDocs.Viewer for .NET بسلاسة في تطبيقات الويب لتوفير إمكانات عرض المستندات.
### هل يوفر GroupDocs.Viewer for .NET دعمًا لمنصات الأجهزة المحمولة؟
نعم، يدعم GroupDocs.Viewer for .NET الأنظمة الأساسية للأجهزة المحمولة، مما يسمح لك بإنشاء تطبيقات ذات ميزات سريعة الاستجابة لعرض المستندات.
### هل يوجد منتدى مجتمعي حيث يمكنني طلب المساعدة فيما يتعلق بـ GroupDocs.Viewer لـ .NET؟
 نعم يمكنك زيارة[منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) لطرح الأسئلة ومشاركة الأفكار والتفاعل مع المستخدمين والمطورين الآخرين.