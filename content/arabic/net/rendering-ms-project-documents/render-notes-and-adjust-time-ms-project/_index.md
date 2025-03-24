---
title: تقديم الملاحظات وضبط وحدات الوقت (MS Project)
linktitle: تقديم الملاحظات وضبط وحدات الوقت (MS Project)
second_title: GroupDocs.Viewer .NET API
description: إتقان عرض مستندات MS Project باستخدام GroupDocs.Viewer لـ .NET. قم بتدوين الملاحظات وضبط وحدات الوقت واستكشاف تنسيقات الإخراج المختلفة دون عناء.
weight: 11
url: /ar/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---

# تقديم الملاحظات وضبط وحدات الوقت (MS Project)

## مقدمة
GroupDocs.Viewer for .NET عبارة عن واجهة برمجة تطبيقات قوية لعرض المستندات تسمح للمطورين بعرض تنسيقات المستندات المختلفة ومعالجتها داخل تطبيقات .NET الخاصة بهم. في هذا البرنامج التعليمي، سنركز على تقديم الملاحظات وضبط وحدات الوقت خصيصًا لمستندات MS Project.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. GroupDocs.Viewer لـ .NET: تأكد من تنزيل وتثبيت GroupDocs.Viewer لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.groupdocs.com/viewer/net/).
2. بيئة التطوير: قم بإعداد بيئة التطوير المفضلة لديك بدعم .NET.
3. مستند مشروع MS: احصل على نموذج مستند مشروع MS جاهز للاختبار.
## استيراد مساحات الأسماء
أولاً، لنستورد مساحات الأسماء الضرورية للبدء في عرض مستندات MS Project:
## الخطوة 1: استيراد مساحات الأسماء
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
الآن بعد أن قمنا باستيراد مساحات الأسماء المطلوبة، فلنقسم كل مثال إلى خطوات متعددة لفهم شامل.
## تقديم وثيقة مشروع MS إلى HTML
لعرض مستند MS Project إلى تنسيق HTML مع تضمين الملاحظات، اتبع الخطوات التالية:
### الخطوة 2: تعيين دليل الإخراج وتنسيق الملف
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### الخطوة 3: تهيئة كائن العارض وتعيين الخيارات
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### الخطوة 4: تقديم المستند إلى HTML
```csharp
viewer.View(options);
```
## تقديم مستند مشروع MS إلى تنسيقات الصور
يمكنك أيضًا عرض مستندات MS Project بتنسيقات صور مثل JPG وPNG. إليك الطريقة:
### الخطوة 5: قم بتعيين دليل الإخراج وتنسيق الملف لـ JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### الخطوة 6: تهيئة كائن العارض وتعيين خيارات JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### الخطوة 7: تقديم المستند إلى JPG
```csharp
viewer.View(options);
```
كرر الخطوات المماثلة للعرض إلى PNG وتنسيقات الصور الأخرى.
## تقديم مستند مشروع MS إلى PDF
لتحويل مستند MS Project إلى تنسيق PDF، اتبع ما يلي:
### الخطوة 8: تعيين دليل الإخراج وتنسيق الملف لـ PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### الخطوة 9: تهيئة كائن العارض وتعيين خيارات PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### الخطوة 10: تقديم المستند إلى PDF
```csharp
viewer.View(options);
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية عرض مستندات MS Project وضبط وحدات الوقت باستخدام GroupDocs.Viewer لـ .NET. قم بدمج هذه المعرفة في مشاريعك لتعزيز إمكانيات عرض المستندات.
## الأسئلة الشائعة
### هل يمكنني عرض مستندات MS Project بتنسيقات أخرى غير HTML والصور وPDF؟
نعم، يدعم GroupDocs.Viewer for .NET العرض بتنسيقات مختلفة مثل DOCX وXLSX وPPTX والمزيد.
### هل هناك إصدار تجريبي متاح لـ GroupDocs.Viewer لـ .NET؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من[هنا](https://releases.groupdocs.com/).
### كيف يمكنني الحصول على ترخيص مؤقت لـ GroupDocs.Viewer لـ .NET؟
 يزور[هذا الرابط](https://purchase.groupdocs.com/temporary-license/) للحصول على ترخيص مؤقت.
### أين يمكنني العثور على وثائق GroupDocs.Viewer لـ .NET؟
 الرجوع إلى الوثائق[هنا](https://tutorials.groupdocs.com/viewer/net/).
### أين يمكنني طلب الدعم أو طرح الأسئلة المتعلقة بـ GroupDocs.Viewer لـ .NET؟
 يمكنك زيارة منتدى الدعم[هنا](https://forum.groupdocs.com/c/viewer/9).