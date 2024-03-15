---
title: تعيين الترخيص المقنن
linktitle: تعيين الترخيص المقنن
second_title: GroupDocs.Viewer .NET API
description: قم بتحسين تطبيقات .NET الخاصة بك باستخدام GroupDocs.Viewer لعرض المستندات بسلاسة. يمكنك بسهولة دمج وظائف عرض المستندات في مشاريعك.
type: docs
weight: 12
url: /ar/net/getting-started/set-metered-license/
---
## مقدمة
في عالم تطوير .NET، يعد دمج إمكانات عرض المستندات القوية في تطبيقاتك أمرًا ضروريًا لتحسين تجربة المستخدم ووظائفه. يقدم GroupDocs.Viewer for .NET حلاً قويًا لدمج وظائف عرض المستندات بسهولة في مشاريع .NET الخاصة بك. سواء كنت تعمل مع ملفات PDF أو مستندات Microsoft Office أو تنسيقات صور متنوعة، فإن GroupDocs.Viewer يبسط عملية عرض هذه المستندات وعرضها داخل تطبيقاتك.
## المتطلبات الأساسية
قبل الغوص في تنفيذ GroupDocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
### 1. قم بتثبيت GroupDocs.Viewer لـ .NET
 للبدء، ستحتاج إلى تنزيل GroupDocs.Viewer وتثبيته لـ .NET. يمكنك العثور على رابط التحميل[هنا](https://releases.groupdocs.com/viewer/net/). اتبع تعليمات التثبيت المتوفرة لإعداد المكتبة ضمن بيئة التطوير الخاصة بك.
### 2. الحصول على الترخيص المقنن
من أجل الاستفادة من GroupDocs.Viewer لـ .NET، تحتاج إلى الحصول على ترخيص مقنن. يسمح لك هذا الترخيص بالتحكم في استخدام واجهة برمجة التطبيقات (API) الخاصة بك ومراقبتها بناءً على حصص محددة مسبقًا. اتبع الخطوات أدناه لإعداد الترخيص المقنن الخاص بك:

## استيراد مساحات الأسماء
أولاً، تأكد من استيراد مساحات الأسماء الضرورية للوصول إلى الوظائف التي يوفرها GroupDocs.Viewer لـ .NET:
```csharp
using System;
```

الآن، دعونا نقسم رمز المثال المقدم إلى خطوات متعددة:
## الخطوة 1: الإعلان عن المفاتيح العامة والخاصة
قم بتعريف المتغيرات لتخزين مفاتيحك العامة والخاصة:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 تأكد من الاستبدال`"YOUR_PUBLIC_KEY"` و`"YOUR_PRIVATE_KEY"` بمفاتيحك الفعلية.
## الخطوة 2: تعيين الترخيص المقنن
تحقق من توفير المفتاح العام. إذا لم يكن الأمر كذلك، فاطلب من المستخدم تعيين المفاتيح:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://buy.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## الخطوة 3: تهيئة الكائن المُقاس وتعيين الترخيص
قم بتهيئة الكائن المقنن وقم بتعيين الترخيص المقنن باستخدام مفاتيحك العامة والخاصة:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## الخطوة 4: رسالة التأكيد
عرض رسالة تأكيد تشير إلى أنه تم ضبط الترخيص بنجاح:
```csharp
Console.WriteLine("License set successfully.");
```

## خاتمة
في الختام، يوفر GroupDocs.Viewer for .NET حلاً شاملاً لدمج وظائف عرض المستندات في تطبيقات .NET الخاصة بك. باتباع الخطوات الموضحة، يمكنك بسهولة إعداد ترخيص محدود والبدء في الاستفادة من إمكانيات GroupDocs.Viewer داخل مشروعاتك.
## الأسئلة الشائعة
### س: أين يمكنني العثور على وثائق GroupDocs.Viewer لـ .NET؟
 يمكنك العثور على الوثائق[هنا](https://reference.groupdocs.com/viewer/net/).
### س: هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer لـ .NET؟
 نعم، يمكنك الوصول إلى النسخة التجريبية المجانية[هنا](https://releases.groupdocs.com/).
### س: كيف يمكنني الحصول على تراخيص مؤقتة لأغراض الاختبار؟
 يمكن الحصول على تراخيص مؤقتة[هنا](https://purchase.groupdocs.com/temporary-license/).
### س: أين يمكنني طلب الدعم أو طرح الأسئلة المتعلقة بـ GroupDocs.Viewer لـ .NET؟
 يمكنك طلب الدعم وطرح الأسئلة في منتدى GroupDocs.Viewer[هنا](https://forum.groupdocs.com/c/viewer/9).
### س: أين يمكنني شراء ترخيص GroupDocs.Viewer لـ .NET؟
 يمكنك شراء ترخيص[هنا](https://purchase.groupdocs.com/buy).