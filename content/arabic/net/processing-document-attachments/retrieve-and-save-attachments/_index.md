---
title: استرداد وحفظ مرفقات المستندات
linktitle: استرداد وحفظ مرفقات المستندات
second_title: GroupDocs.Viewer .NET API
description: إدارة مرفقات المستندات بكفاءة داخل تطبيقات .NET باستخدام GroupDocs.Viewer. يمكنك استرداد المرفقات وحفظها دون أي متاعب.
type: docs
weight: 12
url: /ar/net/processing-document-attachments/retrieve-and-save-attachments/
---
## مقدمة
في العصر الرقمي، تعد المعالجة الفعالة للمستندات أمرًا بالغ الأهمية للشركات والأفراد على حدٍ سواء. سواء أكان الأمر يتعلق بإدارة رسائل البريد الإلكتروني، أو عرض العقود، أو الوصول إلى التقارير، فإن وجود أداة موثوقة لتصور المستندات أمر ضروري. يظهر GroupDocs.Viewer for .NET كحل قوي، يمكّن المستخدمين من عرض تنسيقات المستندات المختلفة والتفاعل معها بسهولة مباشرة من خلال تطبيقات .NET الخاصة بهم.
## المتطلبات الأساسية
قبل الخوض في استخدام GroupDocs.Viewer لـ .NET لاسترداد مرفقات المستندات وحفظها، تأكد من أن لديك المتطلبات الأساسية التالية:
1. بيئة التشغيل: بيئة عمل تم إعدادها باستخدام .NET Framework.
2.  التثبيت: تم تنزيل وتثبيت GroupDocs.Viewer لمكتبة .NET. يمكنك الوصول إلى المكتبة من[رابط التحميل](https://releases.groupdocs.com/viewer/net/).
3. الفهم الأساسي: الإلمام بلغة البرمجة C#.
4. مصدر الوثيقة: الوصول إلى نموذج مستند مع المرفقات لأغراض العرض التوضيحي.

## استيراد مساحات الأسماء
لبدء استخدام GroupDocs.Viewer لـ .NET لاسترداد مرفقات المستندات وحفظها، قم باستيراد مساحات الأسماء الضرورية:
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
حدد الدليل الذي تريد حفظ المرفقات المستردة من المستند فيه.
## الخطوة 2: إنشاء كائن العارض
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
قم بإنشاء كائن العارض بالمسار إلى المستند الذي يحتوي على مرفقات.
## الخطوة 3: استرداد المرفقات
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
استرداد قائمة المرفقات الموجودة في الوثيقة.
## الخطوة 4: حفظ المرفقات
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
قم بالتكرار خلال كل مرفق، وحدد مسار الملف، واحفظ المرفق في الدليل المحدد.
## الخطوة 5: عرض رسالة النجاح
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
عرض رسالة نجاح تشير إلى نجاح حفظ المرفقات مع مسار الدليل.

## خاتمة
يؤدي دمج GroupDocs.Viewer for .NET في سير عمل التعامل مع المستندات إلى تبسيط عملية إدارة المرفقات، مما يوفر الكفاءة والراحة. باتباع الدليل التفصيلي الموضح أعلاه، يمكن للمستخدمين استرداد مرفقات المستندات وحفظها بسهولة داخل تطبيقات .NET الخاصة بهم.
## الأسئلة الشائعة
### هل يستطيع GroupDocs.Viewer لـ .NET التعامل مع تنسيقات المستندات المختلفة؟
نعم، يدعم GroupDocs.Viewer مجموعة واسعة من تنسيقات المستندات، بما في ذلك PDF ومستندات Microsoft Office والصور والمزيد.
### هل تتوفر نسخة تجريبية مجانية من GroupDocs.Viewer لـ .NET؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية من[هنا](https://releases.groupdocs.com/).
### كيف يمكنني الحصول على تراخيص مؤقتة لـ GroupDocs.Viewer لـ .NET؟
 يمكن الحصول على التراخيص المؤقتة من[هذا الرابط](https://purchase.groupdocs.com/temporary-license/).
### أين يمكنني العثور على وثائق GroupDocs.Viewer لـ .NET؟
 الوثائق الشاملة متاحة[هنا](https://reference.groupdocs.com/viewer/net/).
### ما هي خيارات الدعم المتوفرة لـ GroupDocs.Viewer لـ .NET؟
 يمكنك طلب المساعدة من منتدى المجتمع[هنا](https://forum.groupdocs.com/c/viewer/9).