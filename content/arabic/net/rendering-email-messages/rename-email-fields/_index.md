---
title: إعادة تسمية حقول البريد الإلكتروني أثناء العرض
linktitle: إعادة تسمية حقول البريد الإلكتروني أثناء العرض
second_title: GroupDocs.Viewer .NET API
description: قم بتحسين تجربة عرض المستندات باستخدام GroupDocs.Viewer لـ .NET. عرض وتخصيص رسائل البريد الإلكتروني بسلاسة.
weight: 12
url: /ar/net/rendering-email-messages/rename-email-fields/
---
## مقدمة

في العصر الرقمي الحالي، تعد إدارة المستندات وعرضها بكفاءة أمرًا بالغ الأهمية للشركات والأفراد على حدٍ سواء. سواء كان الأمر يتعلق بالعقود أو التقارير أو رسائل البريد الإلكتروني، فإن القدرة على التنقل عبر هذه المستندات بسلاسة يمكن أن تعزز الإنتاجية بشكل كبير. هذا هو المكان الذي يلعب فيه GroupDocs.Viewer for .NET. تسمح هذه المكتبة القوية للمطورين بدمج إمكانيات عرض المستندات مباشرة في تطبيقات .NET الخاصة بهم، مما يوفر نطاقًا واسعًا من الميزات لعرض تنسيقات المستندات المختلفة.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي حول إعادة تسمية حقول البريد الإلكتروني أثناء العرض باستخدام GroupDocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:

1.  GroupDocs.Viewer لمكتبة .NET: قم بتنزيل وتثبيت GroupDocs.Viewer لمكتبة .NET من[هنا](https://releases.groupdocs.com/viewer/net/).

2. بيئة التطوير: تأكد من أن لديك بيئة تطوير مناسبة تم إعدادها لتطوير .NET، مثل Visual Studio.

3. الفهم الأساسي لـ C#: تعرف على أساسيات لغة البرمجة C# حيث سيتضمن البرنامج التعليمي مقتطفات من كود C#.

4. دليل المستندات: قم بإعداد دليل حيث يتم تخزين المستندات التي سيتم تقديمها.

## استيراد مساحات الأسماء

لكي تتمكن من استخدام وظائف GroupDocs.Viewer في تطبيق .NET الخاص بك، فإنك تحتاج إلى استيراد مساحات الأسماء الضرورية.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

لنقم الآن بتقسيم عملية إعادة تسمية حقول البريد الإلكتروني أثناء العرض باستخدام GroupDocs.Viewer لـ .NET إلى خطوات متعددة:

## الخطوة 1: تحديد دليل الإخراج

أولاً، حدد الدليل الذي سيتم حفظ صفحات HTML المعروضة فيه.

```csharp
string outputDirectory = "Your Document Directory";
```

## الخطوة 2: تحديد تنسيق مسار ملف الصفحة

حدد تنسيق مسارات الملفات لصفحات HTML المعروضة. سيتم حفظ كل صفحة كملف HTML منفصل.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## الخطوة 3: تهيئة كائن العارض

قم بإنشاء مثيل لفئة العارض وتمرير مسار المستند ليتم عرضه كمعلمة.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## الخطوة 4: تكوين خيارات عرض HTML

قم بتكوين خيارات عرض HTML، بما في ذلك تحديد تنسيق ملف الإخراج وإعداد تعيينات حقول البريد الإلكتروني.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## الخطوة 5: تقديم الوثيقة

قم باستدعاء طريقة العرض لكائن العارض، وقم بتمرير خيارات عرض HTML التي تم تكوينها.

```csharp
viewer.View(options);
```

## الخطوة 6: عرض رسالة النجاح

أبلغ المستخدم أنه تم تقديم المستند بنجاح.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## خاتمة

في الختام، يوفر GroupDocs.Viewer for .NET حلاً سلسًا لعرض المستندات داخل تطبيقات .NET. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة إعادة تسمية حقول البريد الإلكتروني أثناء العرض، مما يعزز سهولة القراءة وسهولة استخدام مستندات البريد الإلكتروني. بفضل واجهة برمجة التطبيقات البديهية والميزات الشاملة، يعمل GroupDocs.Viewer على تمكين المطورين من تبسيط عمليات عرض المستندات بشكل فعال.

## الأسئلة الشائعة

### س: هل يمكنني عرض المستندات بخلاف رسائل البريد الإلكتروني باستخدام GroupDocs.Viewer لـ .NET؟

ج: نعم، يدعم GroupDocs.Viewer عرض تنسيقات المستندات المختلفة بما في ذلك PDF ومستندات Microsoft Office والصور والمزيد.

### س: هل GroupDocs.Viewer متوافق مع .NET Core؟

ج: نعم، يدعم GroupDocs.Viewer .NET Core إلى جانب .NET Framework التقليدي.

### س: هل يمكنني تخصيص مظهر المستندات المقدمة؟

ج: بالتأكيد، يوفر GroupDocs.Viewer خيارات تخصيص واسعة النطاق للتحكم في مظهر وسلوك المستندات المقدمة.

### س: هل يدعم GroupDocs.Viewer تدفق المستندات؟

ج: نعم، يسمح GroupDocs.Viewer بتدفق المستندات مباشرة إلى متصفح العميل دون الحاجة إلى تخزينها على الخادم.

### س: هل GroupDocs.Viewer مناسب للتطبيقات على مستوى المؤسسة؟

ج: بالتأكيد، تم تصميم GroupDocs.Viewer لتلبية متطلبات التطبيقات على مستوى المؤسسة من خلال قابلية التوسع والموثوقية ومجموعة الميزات القوية.
