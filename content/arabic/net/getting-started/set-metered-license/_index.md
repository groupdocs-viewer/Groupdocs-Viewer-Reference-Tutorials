---
"description": "حسّن تطبيقات .NET لديك باستخدام GroupDocs.Viewer لعرض مستندات سلس. أدمج وظائف عرض المستندات بسهولة في مشاريعك."
"linktitle": "تعيين ترخيص مقنن"
"second_title": "واجهة برمجة تطبيقات GroupDocs.Viewer .NET"
"title": "تعيين ترخيص مقنن"
"url": "/ar/net/getting-started/set-metered-license/"
"weight": 12
---

# تعيين ترخيص مقنن

## مقدمة
في عالم تطوير .NET، يُعدّ دمج إمكانيات عرض المستندات الفعّالة في تطبيقاتك أمرًا ضروريًا لتحسين تجربة المستخدم ووظائفه. يُقدّم GroupDocs.Viewer لـ .NET حلاًّ فعّالاً لدمج وظائف عرض المستندات بسلاسة في مشاريع .NET الخاصة بك. سواء كنت تعمل على ملفات PDF أو مستندات Microsoft Office أو تنسيقات صور مُختلفة، يُبسّط GroupDocs.Viewer عملية عرض هذه المستندات داخل تطبيقاتك.

![تعيين ترخيص مقنن باستخدام GroupDocs.Viewer لـ .NET](/viewer/getting-started/set-metered-license.png)

## المتطلبات الأساسية
قبل الغوص في تنفيذ GroupDocs.Viewer لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:
### 1. تثبيت GroupDocs.Viewer لـ .NET
للبدء، ستحتاج إلى تنزيل وتثبيت GroupDocs.Viewer لـ .NET. يمكنك العثور على رابط التنزيل. [هنا](https://releases.groupdocs.com/viewer/net/)اتبع تعليمات التثبيت المقدمة لإعداد المكتبة داخل بيئة التطوير الخاصة بك.
### 2. الحصول على ترخيص القياس
لاستخدام GroupDocs.Viewer لـ .NET، يجب عليك الحصول على ترخيص مُقيّد. يتيح لك هذا الترخيص التحكم في استخدام واجهة برمجة التطبيقات (API) ومراقبته بناءً على حصص مُحددة مسبقًا. اتبع الخطوات التالية لإعداد ترخيصك المُقيّد:

## استيراد مساحات الأسماء
أولاً، تأكد من استيراد المساحات الأساسية اللازمة للوصول إلى الوظائف التي يوفرها GroupDocs.Viewer لـ .NET:
```csharp
using System;
```

الآن، دعنا نقسم الكود المثال المقدم إلى خطوات متعددة:
## الخطوة 1: إعلان المفاتيح العامة والخاصة
أعلن عن المتغيرات لتخزين مفاتيحك العامة والخاصة:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
تأكد من الاستبدال `"YOUR_PUBLIC_KEY"` و `"YOUR_PRIVATE_KEY"` مع مفاتيحك الفعلية.
## الخطوة 2: تعيين الترخيص المقنن
تحقق من توفر المفتاح العام. إذا لم يكن كذلك، فاطلب من المستخدم تعيين المفاتيح:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://buy.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## الخطوة 3: تهيئة الكائن المقياس وتعيين الترخيص
قم بتهيئة الكائن المقياس وتعيين الترخيص المقياس باستخدام مفاتيحك العامة والخاصة:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## الخطوة 4: رسالة التأكيد
عرض رسالة تأكيد تشير إلى أنه تم تعيين الترخيص بنجاح:
```csharp
Console.WriteLine("License set successfully.");
```

## خاتمة
في الختام، يوفر GroupDocs.Viewer لـ .NET حلاً شاملاً لدمج وظائف عرض المستندات في تطبيقات .NET. باتباع الخطوات الموضحة، يمكنك بسهولة إعداد ترخيص محدود والبدء في الاستفادة من إمكانيات GroupDocs.Viewer في مشاريعك.
## الأسئلة الشائعة
### س: أين يمكنني العثور على الوثائق الخاصة بـ GroupDocs.Viewer لـ .NET؟
يمكنك العثور على الوثائق [هنا](https://tutorials.groupdocs.com/viewer/net/).
### س: هل هناك نسخة تجريبية مجانية متاحة لـ GroupDocs.Viewer لـ .NET؟
نعم، يمكنك الوصول إلى النسخة التجريبية المجانية [هنا](https://releases.groupdocs.com/).
### س: كيف يمكنني الحصول على تراخيص مؤقتة لأغراض الاختبار؟
يمكن الحصول على تراخيص مؤقتة [هنا](https://purchase.groupdocs.com/temporary-license/).
### س: أين يمكنني الحصول على الدعم أو طرح الأسئلة المتعلقة بـ GroupDocs.Viewer لـ .NET؟
يمكنك طلب الدعم وطرح الأسئلة على منتدى GroupDocs.Viewer [هنا](https://forum.groupdocs.com/c/viewer/9).
### س: أين يمكنني شراء ترخيص لـ GroupDocs.Viewer لـ .NET؟
يمكنك شراء ترخيص [هنا](https://purchase.groupdocs.com/buy).