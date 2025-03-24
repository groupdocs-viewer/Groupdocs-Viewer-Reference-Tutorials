---
title: احصل على إحداثيات النص لعرض الصور
linktitle: احصل على إحداثيات النص لعرض الصور
second_title: GroupDocs.Viewer .NET API
description: تعرف على كيفية استخراج إحداثيات النص لعرض الصور باستخدام GroupDocs.Viewer لـ .NET. تعزيز قدرات معالجة المستندات الخاصة بك دون عناء.
weight: 12
url: /ar/net/rendering-documents-images/get-text-coordinates-image/
---

# احصل على إحداثيات النص لعرض الصور

## مقدمة
GroupDocs.Viewer for .NET عبارة عن واجهة برمجة تطبيقات قوية لعرض المستندات تتيح للمطورين عرض المستندات بتنسيقات مختلفة بسلاسة مثل PDF وMicrosoft Office وغير ذلك الكثير. إحدى وظائفه الرئيسية هي القدرة على استخراج إحداثيات النص لعرض الصورة بدقة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  GroupDocs.Viewer لـ .NET: قم بتنزيل أحدث إصدار وتثبيته من[هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: قم بإعداد IDE المفضل لديك مع دعم .NET Framework.
3. ملفات المستندات: اجعل ملفات المستندات النموذجية جاهزة لأغراض الاختبار.

## استيراد مساحات الأسماء
قبل الغوص في عملية الترميز، فلنستورد مساحات الأسماء الضرورية للوصول إلى وظائف GroupDocs.Viewer لـ .NET.
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## الخطوة 1: تهيئة GroupDocs.Viewer
ابدأ بتهيئة كائن GroupDocs.Viewer بملف المستند الذي تنوي معالجته.
```csharp
using (Viewer viewer = new Viewer("path/to/your/document"))
{
    // الكود الخاص بك يذهب هنا
}
```
## الخطوة 2: الحصول على معلومات العرض
بعد ذلك، قم باسترداد معلومات عرض المستند، بما في ذلك إحداثيات النص لعرض الصورة.
```csharp
ViewInfoOptions options = ViewInfoOptions.ForPngView(true);
ViewInfo viewInfo = viewer.GetViewInfo(options);
```
## الخطوة 3: التكرار عبر الصفحات
قم بالتكرار خلال كل صفحة من المستند للوصول إلى سطور النص والكلمات والأحرف.
```csharp
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($"Page: {page.Number}");
    Console.WriteLine("Text lines/words/characters:");
    foreach (Line line in page.Lines)
    {
        Console.WriteLine(line);
        foreach (Word word in line.Words)
        {
            Console.WriteLine("\t" + word);
            foreach (Character character in word.Characters)
                Console.WriteLine("\t\t" + character);
        }
    }
}
```
## الخطوة 4: استخراج إحداثيات النص
قم باستخراج إحداثيات النص لتسهيل عرض الصورة بدقة.
```csharp
// الكود الخاص بك لاستخراج إحداثيات النص موجود هنا
```

## خاتمة
في الختام، فإن إتقان استخراج إحداثيات النص لعرض الصور باستخدام GroupDocs.Viewer لـ .NET يمكن أن يعزز بشكل كبير قدرات معالجة المستندات لديك. باتباع هذا البرنامج التعليمي، تكون قد تعلمت الخطوات الأساسية لإنجاز هذه المهمة بكفاءة.
## الأسئلة الشائعة
### هل يتوافق GroupDocs.Viewer for .NET مع كافة تنسيقات المستندات؟
يدعم GroupDocs.Viewer for .NET نطاقًا واسعًا من تنسيقات المستندات، بما في ذلك PDF وMicrosoft Office والمزيد.
### هل يمكنني دمج GroupDocs.Viewer لـ .NET في تطبيق .NET الحالي الخاص بي؟
نعم، تم تصميم GroupDocs.Viewer for .NET للتكامل بسهولة مع تطبيقات .NET الخاصة بك.
### هل يوفر GroupDocs.Viewer for .NET الدعم لاستخراج إحداثيات النص؟
نعم، كما هو موضح في هذا البرنامج التعليمي، يوفر GroupDocs.Viewer for .NET وظيفة لاستخراج إحداثيات النص.
### أين يمكنني العثور على وثائق ودعم إضافيين لـ GroupDocs.Viewer لـ .NET؟
 يمكنك الوصول إلى الوثائق وطلب الدعم من منتدى GroupDocs.Viewer[هنا](https://forum.groupdocs.com/c/viewer/9).
### هل تتوفر نسخة تجريبية مجانية من GroupDocs.Viewer لـ .NET؟
 نعم، يمكنك الاستفادة من النسخة التجريبية المجانية من موقع GroupDocs[هنا](https://releases.groupdocs.com/).