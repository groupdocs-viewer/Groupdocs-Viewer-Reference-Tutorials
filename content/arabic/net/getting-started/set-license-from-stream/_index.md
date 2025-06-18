---
"description": "حسّن تطبيقات .NET لديك باستخدام GroupDocs.Viewer لعرض مستندات سلس. اتبع دليلنا خطوة بخطوة ودمج إمكانيات عرض مستندات فعّالة بكل سهولة."
"linktitle": "تعيين الترخيص من البث"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تعيين الترخيص من البث"
"url": "/ar/net/getting-started/set-license-from-stream/"
"weight": 11
---

# تعيين الترخيص من البث

## مقدمة
هل ترغب في تعزيز تطبيقات .NET الخاصة بك بإمكانيات عرض مستندات متقدمة؟ يوفر GroupDocs.Viewer for .NET حلاً شاملاً لدمج وظائف عرض المستندات بسلاسة في مشاريعك. في هذا البرنامج التعليمي، سنتعمق في عملية الاستفادة من GroupDocs.Viewer for .NET لإثراء تطبيقاتك بإمكانيات عرض مستندات فعّالة. 

![تعيين الترخيص من Stream باستخدام GroupDocs.Viewer لـ .NET](/viewer/getting-started/set-license-from-stream.png)

## المتطلبات الأساسية
قبل أن نتعمق في عملية التكامل، تأكد من توفر المتطلبات الأساسية التالية:
1. المعرفة الأساسية بتطوير .NET: المعرفة بـ C# وإطار عمل .NET أمر ضروري لمتابعة هذا البرنامج التعليمي.
   
2. حزمة GroupDocs.Viewer لـ .NET: تأكد من تنزيل وتثبيت حزمة GroupDocs.Viewer لـ .NET. يمكنك الحصول عليها من [رابط التحميل](https://releases.groupdocs.com/viewer/net/).
3. الوصول إلى وثائق GroupDocs: احتفظ بـ [التوثيق](https://tutorials.groupdocs.com/viewer/net/) مفيد للدروس التعليمية أثناء عملية التكامل.

## استيراد مساحات الأسماء
للبدء، استورد مساحات الأسماء اللازمة إلى تطبيق .NET الخاص بك. اتبع الخطوات التالية:
### الخطوة 1: افتح مشروع .NET الخاص بك.
تأكد من فتح مشروع .NET الخاص بك في بيئة التطوير المفضلة لديك.
### الخطوة 2: إضافة مساحة اسم GroupDocs.Viewer.
في ملف التعليمات البرمجية الخاص بك، أضف مساحة الأسماء التالية للوصول إلى وظائف GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## تعيين الترخيص من البث
الخطوة التالية هي إعداد الترخيص من مصدر مُحدد. اتبع الخطوات المُفصلة التالية:
### الخطوة 1: تحديد دليل الإخراج.
قم بتعيين الدليل الذي سيتم تخزين مستنداتك فيه عن طريق تحديد دليل الإخراج:
```csharp
string outputDirectory = "Your Document Directory";
```
### الخطوة 2: التحقق من وجود ملف الترخيص.
تحقق مما إذا كان ملف الترخيص موجودًا في دليل المشروع الخاص بك:
```csharp
if (File.Exists(Utils.LicensePath))
```
### الخطوة 3: تعيين الترخيص.
إذا كان ملف الترخيص موجودًا، فقم بتعيين الترخيص باستخدام التدفق المقدم:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### الخطوة 4: التعامل مع غياب الترخيص.
إذا لم يتم العثور على ملف الترخيص، قم بتقديم التعليمات للحصول على ترخيص:
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
تهانينا! لقد نجحت في تعلم كيفية دمج GroupDocs.Viewer لـ .NET في تطبيقاتك. باستخدام هذه الأداة الفعّالة، يمكنك الآن عرض تنسيقات مستندات متنوعة بسهولة ضمن مشاريع .NET الخاصة بك، مما يُحسّن تجربة المستخدم والإنتاجية.
## الأسئلة الشائعة
### هل أحتاج إلى ترخيص لاستخدام GroupDocs.Viewer لـ .NET؟
نعم، تحتاج إلى ترخيص لاستخدام GroupDocs.Viewer لـ .NET. يمكنك الحصول على ترخيص مؤقت أو دائم من موقع GroupDocs الإلكتروني.
### هل يمكنني دمج GroupDocs.Viewer في تطبيق ASP.NET الخاص بي؟
بالتأكيد! يتكامل GroupDocs.Viewer لـ .NET بسلاسة مع تطبيقات سطح المكتب والويب، بما في ذلك ASP.NET.
### ما هي تنسيقات المستندات التي يدعمها GroupDocs.Viewer؟
يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF، وMicrosoft Office (Word، Excel، PowerPoint)، والصور، والمزيد.
### هل GroupDocs.Viewer متوافق مع .NET Core؟
نعم، GroupDocs.Viewer لـ .NET متوافق مع كل من .NET Framework و.NET Core.
### هل يمكنني تخصيص واجهة العارض وفقًا لموضوع تطبيقي؟
نعم، يوفر GroupDocs.Viewer خيارات تخصيص واسعة النطاق، مما يسمح لك بتخصيص واجهة العارض لتتناسب مع موضوع تطبيقك بسلاسة.