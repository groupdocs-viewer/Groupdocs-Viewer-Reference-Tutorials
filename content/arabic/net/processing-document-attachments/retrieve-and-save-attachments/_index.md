---
"description": "أدر مرفقات المستندات بكفاءة داخل تطبيقات .NET باستخدام GroupDocs.Viewer. استرجع المرفقات واحفظها بسهولة."
"linktitle": "استرداد مرفقات المستندات وحفظها"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "استرداد مرفقات المستندات وحفظها"
"url": "/ar/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
type: docs
---
# استرداد مرفقات المستندات وحفظها

## مقدمة
في العصر الرقمي، تُعدّ معالجة المستندات بكفاءة أمرًا بالغ الأهمية للشركات والأفراد على حد سواء. سواءً كان الأمر يتعلق بإدارة رسائل البريد الإلكتروني، أو عرض العقود، أو الوصول إلى التقارير، فإن وجود أداة موثوقة لعرض المستندات أمرٌ بالغ الأهمية. يبرز GroupDocs.Viewer لـ .NET كحلٍّ فعّال، يُمكّن المستخدمين من عرض مختلف تنسيقات المستندات والتفاعل معها بسهولة ويسر مباشرةً من داخل تطبيقات .NET الخاصة بهم.

![استرداد مرفقات المستندات وحفظها باستخدام GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## المتطلبات الأساسية
قبل الخوض في استخدام GroupDocs.Viewer لـ .NET لاسترجاع مرفقات المستندات وحفظها، تأكد من أن لديك المتطلبات الأساسية التالية:
1. بيئة التشغيل: بيئة عمل تم إعدادها باستخدام إطار عمل .NET.
2. التثبيت: تم تنزيل مكتبة GroupDocs.Viewer لـ .NET وتثبيتها. يمكنك الوصول إلى المكتبة من [رابط التحميل](https://releases.groupdocs.com/viewer/net/).
3. الفهم الأساسي: الإلمام بلغة البرمجة C#.
4. مصدر المستند: الوصول إلى مستند نموذجي مع المرفقات لأغراض العرض التوضيحي.

## استيراد مساحات الأسماء
لبدء استخدام GroupDocs.Viewer لـ .NET لاسترداد مرفقات المستندات وحفظها، قم باستيراد المساحات الأساسية الضرورية:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## الخطوة 1: تحديد دليل الإخراج
```csharp
string outputDirectory = "Your Document Directory";
```
قم بتحديد الدليل الذي تريد حفظ المرفقات المستردة من المستند فيه.
## الخطوة 2: إنشاء كائن العارض
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
إنشاء كائن العارض باستخدام المسار إلى المستند الذي يحتوي على المرفقات.
## الخطوة 3: استرداد المرفقات
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
استرجاع قائمة المرفقات الموجودة في المستند.
## الخطوة 4: حفظ المرفقات
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
قم بتكرار كل مرفق، وحدد مسار الملف، ثم احفظ المرفق في الدليل المحدد.
## الخطوة 5: عرض رسالة النجاح
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
عرض رسالة نجاح تشير إلى نجاح حفظ المرفقات مع مسار الدليل.

## خاتمة
يُسهّل دمج GroupDocs.Viewer لـ .NET في سير عمل معالجة المستندات عملية إدارة المرفقات، مما يوفر الكفاءة والراحة. باتباع الدليل المفصل الموضح أعلاه، يمكن للمستخدمين استرداد مرفقات المستندات وحفظها بسلاسة داخل تطبيقات .NET الخاصة بهم.
## الأسئلة الشائعة
### هل يمكن لـ GroupDocs.Viewer لـ .NET التعامل مع تنسيقات المستندات المختلفة؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF، ومستندات Microsoft Office، والصور، والمزيد.
### هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من [هنا](https://releases.groupdocs.com/).
### كيف يمكنني الحصول على تراخيص مؤقتة لـ GroupDocs.Viewer لـ .NET؟
يمكن الحصول على التراخيص المؤقتة من [هذا الرابط](https://purchase.groupdocs.com/temporary-license/).
### أين يمكنني العثور على الوثائق الخاصة بـ GroupDocs.Viewer لـ .NET؟
التوثيق الشامل متاح [هنا](https://tutorials.groupdocs.com/viewer/net/).
### ما هي خيارات الدعم المتوفرة لـ GroupDocs.Viewer لـ .NET؟
يمكنك طلب المساعدة من منتدى المجتمع [هنا](https://forum.groupdocs.com/c/viewer/9).