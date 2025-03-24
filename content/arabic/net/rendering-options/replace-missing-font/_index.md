---
title: استبدال الخط المفقود
linktitle: استبدال الخط المفقود
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية استبدال الخطوط المفقودة في مستندات .NET بسهولة باستخدام GroupDocs.Viewer. ضمان تقديم دقيق مع خطوات بسيطة.
weight: 20
url: /ar/net/rendering-options/replace-missing-font/
---
## مقدمة
في عالم تطوير .NET، تعد المعالجة الفعالة للمستندات أمرًا بالغ الأهمية. يوفر GroupDocs.Viewer for .NET حلاً قويًا لعرض تنسيقات المستندات المختلفة داخل تطبيقات .NET الخاصة بك. في هذا البرنامج التعليمي، سنستكشف كيفية استخدام GroupDocs.Viewer لـ .NET لاستبدال الخطوط المفقودة في المستندات. سواء كنت تتعامل مع ملفات PDF، أو عروض PowerPoint التقديمية، أو مستندات Word، فإن GroupDocs.Viewer يبسط العملية، مما يضمن عرض مستنداتك بدقة، حتى عندما تكون الخطوط مفقودة.
## المتطلبات الأساسية
قبل الغوص في هذا البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. GroupDocs.Viewer لـ .NET: قم بتنزيل وتثبيت مكتبة GroupDocs.Viewer من موقع الويب](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: قم بإعداد بيئة تطوير .NET، مثل Visual Studio.
3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# وإطار عمل .NET.

## استيراد مساحات الأسماء
في كود C# الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى وظائف GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

الآن، دعونا نستعرض عملية استبدال الخطوط المفقودة في المستندات باستخدام GroupDocs.Viewer لـ .NET.
## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
قم بتعيين الدليل حيث سيتم حفظ صفحات المستند المقدمة.
## الخطوة 2: تحديد تنسيق مسار ملف الصفحة
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
حدد التنسيق لتسمية ملفات HTML المخرجة. في هذا المثال، سيتم حفظ كل صفحة كملف HTML مع اصطلاح التسمية "page_{page_number}.لغة البرمجة".
## الخطوة 3: تهيئة كائن العارض
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
قم بتهيئة مثيل جديد لفئة Viewer، وتمرير المسار إلى ملف المستند (في هذه الحالة، عرض تقديمي لـ PowerPoint مع خطوط مفقودة) كمعلمة.
## الخطوة 4: قم بتعيين خيارات عرض HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
قم بإنشاء مثيل لـ HtmlViewOptions وقم بتكوينه لتضمين الموارد داخل مخرجات HTML. حدد اسم الخط الافتراضي لاستخدامه كبديل للخطوط المفقودة.
## الخطوة 5: تقديم الوثيقة
```csharp
viewer.View(options);
```
استدعاء طريقة العرض لكائن العارض، وتمرير خيارات عرض HTML. سيؤدي هذا إلى عرض صفحات المستند باستخدام الخيارات المحددة.
## الخطوة 6: عرض مسار الإخراج
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
قم بطباعة رسالة تشير إلى نجاح عرض المستند وتوفير المسار حيث يتم حفظ ملفات HTML الناتجة.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية استخدام GroupDocs.Viewer لـ .NET لاستبدال الخطوط المفقودة في المستندات. باتباع هذه الخطوات، يمكنك التأكد من عرض مستنداتك بدقة، حتى في حالة عدم توفر خطوط معينة. يعمل GroupDocs.Viewer على تبسيط العملية، مما يسمح لك بالتركيز على إنشاء تطبيقات .NET قوية دون القلق بشأن مشكلات توافق الخطوط.
## الأسئلة الشائعة
### هل يستطيع GroupDocs.Viewer التعامل مع أنواع أخرى من المشكلات المتعلقة بالخط؟
نعم، يوفر GroupDocs.Viewer العديد من الوظائف المتعلقة بالخط، بما في ذلك استبدال الخط واكتشاف الخط.
### هل يتوافق GroupDocs.Viewer مع جميع أطر عمل .NET؟
يدعم GroupDocs.Viewer نطاقًا واسعًا من أطر عمل .NET، بما في ذلك .NET Core و.NET Standard.
### هل يمكنني تخصيص استبدال الخط الافتراضي في GroupDocs.Viewer؟
بالتأكيد، يمكنك تحديد أي خط من اختيارك كبديل افتراضي للخطوط المفقودة.
### هل يدعم GroupDocs.Viewer المعالجة المجمعة للمستندات؟
نعم، يتيح لك GroupDocs.Viewer معالجة مستندات متعددة في وقت واحد، مما يجعله مثاليًا لسيناريوهات المعالجة المجمعة.
### أين يمكنني العثور على مزيد من المساعدة أو الدعم بخصوص GroupDocs.Viewer؟
 يمكنك زيارة منتدى GroupDocs.Viewer[هنا](https://forum.groupdocs.com/c/viewer/9) لأي مساعدة أو استفسارات الدعم.