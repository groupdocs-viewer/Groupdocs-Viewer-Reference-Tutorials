---
title: قم بتعيين الترخيص من الدفق
linktitle: قم بتعيين الترخيص من الدفق
second_title: GroupDocs.Viewer .NET API
description: قم بتحسين تطبيقات .NET الخاصة بك باستخدام GroupDocs.Viewer لعرض المستندات بسلاسة. اتبع دليلنا خطوة بخطوة وقم بدمج إمكانات عرض المستندات القوية دون عناء.
type: docs
weight: 11
url: /ar/net/getting-started/set-license-from-stream/
---
## مقدمة
هل تتطلع إلى تمكين تطبيقات .NET الخاصة بك من خلال إمكانيات عرض المستندات المتقدمة؟ يقدم GroupDocs.Viewer for .NET حلاً شاملاً لدمج وظائف عرض المستندات في مشروعاتك بسلاسة. في هذا البرنامج التعليمي، سنتعمق في عملية الاستفادة من GroupDocs.Viewer لـ .NET لإثراء تطبيقاتك بإمكانيات قوية لعرض المستندات. 
## المتطلبات الأساسية
قبل أن نتعمق في عملية التكامل، تأكد من توفر المتطلبات الأساسية التالية:
1. المعرفة الأساسية بتطوير .NET: يعد الإلمام بـ C# و.NET Framework ضروريًا للمتابعة مع هذا البرنامج التعليمي.
   
2.  GroupDocs.Viewer لحزمة .NET: تأكد من تنزيل وتثبيت GroupDocs.Viewer لحزمة .NET. يمكنك الحصول عليه من[رابط التحميل](https://releases.groupdocs.com/viewer/net/).
3.  الوصول إلى وثائق GroupDocs: احتفظ بملف[توثيق](https://reference.groupdocs.com/viewer/net/) مفيد للرجوع إليه أثناء عملية التكامل.

## استيراد مساحات الأسماء
للبدء، قم باستيراد مساحات الأسماء الضرورية إلى تطبيق .NET الخاص بك. اتبع الخطوات التالية:
### الخطوة 1: افتح مشروع .NET الخاص بك.
تأكد من فتح مشروع .NET الخاص بك في بيئة التطوير المفضلة لديك.
### الخطوة 2: إضافة مساحة الاسم GroupDocs.Viewer.
في ملف التعليمات البرمجية الخاص بك، قم بإضافة مساحة الاسم التالية للوصول إلى وظائف GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## قم بتعيين الترخيص من الدفق
تتضمن الخطوة التالية تعيين الترخيص من الدفق. اتبع هذه الخطوات التفصيلية:
### الخطوة 1: تحديد دليل الإخراج.
قم بتعيين الدليل الذي سيتم تخزين مستنداتك فيه عن طريق تحديد دليل الإخراج:
```csharp
string outputDirectory = "Your Document Directory";
```
### الخطوة 2: التحقق من وجود ملف الترخيص.
تحقق من وجود ملف الترخيص في دليل المشروع الخاص بك:
```csharp
if (File.Exists(Utils.LicensePath))
```
### الخطوة 3: تعيين الترخيص.
إذا كان ملف الترخيص موجودًا، فقم بتعيين الترخيص باستخدام الدفق المقدم:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### الخطوة 4: التعامل مع غياب الترخيص.
إذا لم يتم العثور على ملف الترخيص، قم بتقديم تعليمات للحصول على ترخيص:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://buy.groupdocs.com/temporary-license.");
}
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية دمج GroupDocs.Viewer لـ .NET في تطبيقاتك. باستخدام هذه الأداة القوية، يمكنك الآن بسهولة عرض تنسيقات المستندات المختلفة ضمن مشروعات .NET الخاصة بك، مما يعزز تجربة المستخدم والإنتاجية.
## الأسئلة الشائعة
### هل أحتاج إلى ترخيص لاستخدام GroupDocs.Viewer لـ .NET؟
نعم، أنت بحاجة إلى ترخيص لاستخدام GroupDocs.Viewer لـ .NET. يمكنك الحصول على ترخيص مؤقت أو دائم من موقع GroupDocs على الويب.
### هل يمكنني دمج GroupDocs.Viewer في تطبيق ASP.NET الخاص بي؟
قطعاً! يتكامل GroupDocs.Viewer for .NET بسلاسة مع كل من تطبيقات سطح المكتب والويب، بما في ذلك ASP.NET.
### ما تنسيقات المستندات التي يدعمها GroupDocs.Viewer؟
يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF وMicrosoft Office (Word وExcel وPowerPoint) والصور والمزيد.
### هل GroupDocs.Viewer متوافق مع .NET Core؟
نعم، إن GroupDocs.Viewer for .NET متوافق مع كل من .NET Framework و.NET Core.
### هل يمكنني تخصيص واجهة العارض وفقًا لموضوع تطبيقي؟
نعم، يوفر GroupDocs.Viewer خيارات تخصيص واسعة النطاق، مما يسمح لك بتخصيص واجهة العارض لتتناسب مع سمة التطبيق الخاص بك بسلاسة.