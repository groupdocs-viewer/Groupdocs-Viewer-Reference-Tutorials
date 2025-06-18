---
"description": "دمج GroupDocs.Viewer لـ .NET بسلاسة في تطبيقاتك لعرض مستنداتك بكفاءة. حسّن إنتاجيتك مع إمكانيات عرض متعددة."
"linktitle": "عرض الفاصل الزمني للمشروع المحدد (MS Project)"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "عرض الفاصل الزمني للمشروع المحدد (MS Project)"
"url": "/ar/net/rendering-ms-project-documents/render-project-time-interval-ms-project/"
"weight": 12
---

# عرض الفاصل الزمني للمشروع المحدد (MS Project)

## مقدمة
في مجال تطوير البرمجيات، يُعدّ التعامل مع مختلف صيغ المستندات وعرضها بكفاءة أمرًا بالغ الأهمية. سواءً كان ذلك لعرض المستندات أو معالجتها، فإنّ امتلاك الأدوات المناسبة يُحسّن الإنتاجية ويُسهّل العمليات بشكل كبير. يتميّز GroupDocs.Viewer لـ .NET كحلٍّ متعدد الاستخدامات، حيث يُتيح للمطورين دمج إمكانيات عرض المستندات بسلاسة في تطبيقات .NET الخاصة بهم.
## المتطلبات الأساسية
قبل الغوص في تكامل GroupDocs.Viewer لـ .NET، تأكد من أن لديك المتطلبات الأساسية التالية:
### 1. الإلمام بـ .NET Framework
تأكد من أن لديك فهمًا أساسيًا لإطار عمل .NET، بما في ذلك لغة البرمجة C# وVisual Studio IDE.
### 2. تثبيت GroupDocs.Viewer لـ .NET
قم بتنزيل GroupDocs.Viewer لـ .NET وتثبيته من [رابط التحميل](https://releases.groupdocs.com/viewer/net/)اتبع تعليمات التثبيت المقدمة لإعداد المكتبة داخل بيئة التطوير الخاصة بك.
### 3. رخصة سارية المفعول أو رخصة مؤقتة
احصل على ترخيص صالح من [مجموعة المستندات](https://purchase.groupdocs.com/buy) أو الحصول على ترخيص مؤقت من [هنا](https://purchase.groupdocs.com/temporary-license/) للاستفادة من الوظائف الكاملة لـ GroupDocs.Viewer لـ .NET.
### 4. نموذج الوثيقة
قم بإعداد مستند نموذجي، مثل ملف MS Project، جاهزًا لاختبار وظيفة العرض.

## استيراد مساحات الأسماء
قم بدمج مساحات الأسماء الضرورية في مشروعك للوصول إلى الوظائف التي يوفرها GroupDocs.Viewer لـ .NET.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

دعنا نقسم مثال تقديم فترة زمنية محددة للمشروع من ملف MS Project إلى خطوات متعددة:
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
حدد الدليل الذي سيتم حفظ صفحات HTML المقدمة فيه.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
قم بتعيين تنسيق مسار الملف لكل صفحة HTML المقدمة.
## الخطوة 3: إنشاء كائن العارض
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
```
قم بإنشاء مثيل لفئة Viewer، وقم بتمرير المسار إلى ملف MS Project النموذجي.
## الخطوة 4: تكوين خيارات عرض HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
قم بتكوين خيارات عرض HTML للرسم، مع تحديد تنسيق الموارد المضمنة.
## الخطوة 5: استرداد معلومات عرض إدارة المشروع
```csharp
ProjectManagementViewInfo viewInfo = viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;
```
استرداد معلومات عرض إدارة المشروع لتحديد تواريخ بدء ونهاية المشروع.
## الخطوة 6: تعيين تواريخ البدء والانتهاء
```csharp
options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);
```
قم بتعيين تواريخ البداية والنهاية لفترة المشروع التي سيتم عرضها.
## الخطوة 7: عرض المستند
```csharp
viewer.View(options);
```
ابدأ عملية العرض باستخدام الخيارات المحددة.
## الخطوة 8: عرض دليل الإخراج
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
إعلام المستخدم بنجاح عملية العرض وعرض الدليل الذي تم حفظ الإخراج فيه.

## خاتمة
يُمكّنك دمج GroupDocs.Viewer لـ .NET في مشاريعك من إدارة مهام عرض المستندات بكفاءة، مما يُحسّن تجربة المستخدم والإنتاجية. باتباع الدليل المُفصّل المُقدّم، يُمكنك دمج وظائف عرض المستندات بسلاسة في تطبيقات .NET.
## الأسئلة الشائعة
### هل GroupDocs.Viewer لـ .NET متوافق مع كافة تنسيقات المستندات؟
يدعم GroupDocs.Viewer لـ .NET مجموعة واسعة من تنسيقات المستندات، بما في ذلك Microsoft Office، وPDF، وCAD، والمزيد.
### هل يمكنني تخصيص مظهر المستندات المقدمة؟
نعم، يمكنك تخصيص جوانب مختلفة من عملية العرض، مثل تخطيط الصفحة، والعلامة المائية، وتدوير الصفحة.
### هل GroupDocs.Viewer لـ .NET مناسب لتطبيقات الويب؟
بالتأكيد، يمكن دمج GroupDocs.Viewer لـ .NET بسلاسة في تطبيقات الويب لتوفير إمكانيات عرض المستندات.
### هل يوفر GroupDocs.Viewer لـ .NET الدعم للمنصات المحمولة؟
نعم، يدعم GroupDocs.Viewer لـ .NET المنصات المحمولة، مما يسمح لك بإنشاء تطبيقات ذات ميزات عرض مستندات مستجيبة.
### هل يوجد منتدى مجتمعي حيث يمكنني طلب المساعدة مع GroupDocs.Viewer لـ .NET؟
نعم يمكنك زيارة [منتدى GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) لطرح الأسئلة ومشاركة الأفكار والتفاعل مع المستخدمين والمطورين الآخرين.