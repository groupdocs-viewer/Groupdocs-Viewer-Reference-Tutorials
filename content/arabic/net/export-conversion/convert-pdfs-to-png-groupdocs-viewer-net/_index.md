---
"date": "2025-04-25"
"description": "تعرّف على كيفية تحويل صفحات PDF إلى صور PNG مع الحفاظ على أبعادها الأصلية باستخدام GroupDocs.Viewer لـ .NET. يغطي هذا الدليل الإعداد والتكوين وأفضل الممارسات."
"title": "تحويل ملفات PDF إلى PNG بالحجم الأصلي باستخدام GroupDocs.Viewer لـ .NET"
"url": "/ar/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
---

# تحويل ملفات PDF إلى PNG بالحجم الأصلي باستخدام GroupDocs.Viewer لـ .NET

## مقدمة

يُعد تحويل ملفات PDF إلى صور PNG مع الحفاظ على حجم الصفحة الأصلي أمرًا ضروريًا لرقمنة المستندات أو إعداد محتوى الويب بجودة عالية. سيرشدك هذا البرنامج التعليمي إلى كيفية استخدام GroupDocs.Viewer لـ .NET لعرض صفحات PDF كملفات PNG، مع الحفاظ على أبعادها الأصلية.

![تحويل ملفات PDF إلى PNG بالحجم الأصلي باستخدام GroupDocs.Viewer لـ .NET](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**ما سوف تتعلمه:**
- كيفية إعداد وتكوين GroupDocs.Viewer لـ .NET في مشروعك
- عملية خطوة بخطوة لتحويل ملفات PDF إلى صور PNG مع الحفاظ على أحجام الصفحات
- خيارات التكوين الرئيسية وأفضل الممارسات لتحقيق الأداء الأمثل

بنهاية هذا البرنامج التعليمي، ستتمكن من دمج هذه الوظيفة في تطبيقاتك بسلاسة. لنبدأ بالمتطلبات الأساسية اللازمة للبدء.

## المتطلبات الأساسية

قبل تنفيذ GroupDocs.Viewer لـ .NET في مشروعك، تأكد من توفر المتطلبات التالية:

### المكتبات والإصدارات المطلوبة
- **GroupDocs.Viewer لـ .NET**:الإصدار 25.3.0 أو أحدث.

### متطلبات إعداد البيئة
- بيئة تطوير متوافقة مثل Visual Studio.
- فهم أساسي لبرمجة C#.

### متطلبات المعرفة
- المعرفة بإدارة حزمة NuGet.
- بعض الخبرة في العمل مع ملفات PDF ومعالجة الصور في تطبيقات .NET.

بمجرد توفر هذه المتطلبات الأساسية، يمكننا المتابعة لإعداد GroupDocs.Viewer لـ .NET.

## إعداد GroupDocs.Viewer لـ .NET

لبدء استخدام GroupDocs.Viewer لـ .NET، اتبع خطوات التثبيت أدناه:

### التثبيت عبر وحدة تحكم NuGet Package Manager
افتح مشروعك في Visual Studio واستخدم الأمر التالي:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### التثبيت عبر .NET CLI
بدلاً من ذلك، يمكنك تثبيته باستخدام .NET CLI باستخدام هذا الأمر:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### خطوات الحصول على الترخيص
1. **نسخة تجريبية مجانية**: قم بتنزيل النسخة التجريبية من [تنزيلات GroupDocs](https://releases.groupdocs.com/viewer/net/).
2. **رخصة مؤقتة**:احصل على ترخيص مؤقت لاستكشاف الميزات الكاملة في [صفحة الترخيص المؤقت](https://purchase.groupdocs.com/temporary-license/).
3. **شراء**:للاستخدام الموسع، قم بشراء ترخيص من خلال [صفحة الشراء](https://purchase.groupdocs.com/buy).

### التهيئة والإعداد الأساسي
لتهيئة GroupDocs.Viewer لـ .NET في مشروع C# الخاص بك، اتبع الخطوات التالية:
1. استيراد مساحات الأسماء الضرورية:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. قم بإعداد المسارات لملف PDF المدخل ودليل الإخراج.
3. تهيئة `Viewer` مع المسار إلى مستند المصدر الخاص بك، كما هو موضح في هذا المقطع:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## دليل التنفيذ
يتناول هذا القسم تنفيذ عرض صفحات PDF كصور PNG مع الحفاظ على حجمها الأصلي.

### تحويل صفحات PDF إلى PNG بحجم الصفحة الأصلي
#### ملخص
تتيح لك هذه الميزة تحويل كل صفحة من مستند PDF إلى صورة PNG، مع الحفاظ على أبعادها الأصلية. تُعد هذه الميزة مفيدة بشكل خاص للتطبيقات التي تتطلب تمثيلًا بصريًا دقيقًا للمستندات.

##### الخطوة 1: إعداد المسارات وتهيئة العارض
إنشاء متغيرات لمسار PDF المدخل ودليل الإخراج:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
تهيئة `Viewer` الفئة مع مسار المستند المصدر الخاص بك:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // سوف تستمر كتلة التعليمات البرمجية في الخطوة التالية
}
```
##### الخطوة 2: تكوين PngViewOptions
إنشاء مثيل لـ `PngViewOptions`، تحديد نمط تسمية الملف للصور الناتجة:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
قم بتكوين خيارات العارض لعرض كل صفحة بحجمها الأصلي:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### الخطوة 3: عرض صفحات المستند
اتصل بـ `View` الطريقة الخاصة بك `Viewer` على سبيل المثال، تمرير خيارات العرض المُهيأة:
```csharp
viewer.View(viewOptions);
```
### نصائح استكشاف الأخطاء وإصلاحها
- تأكد من صحة المسارات ووجود الدلائل.
- تأكد من أن لديك الأذونات اللازمة للقراءة من أدلة الإدخال والكتابة إلى أدلة الإخراج.

## التطبيقات العملية
1. **رقمنة المستندات**:تحويل مستندات PDF الأرشيفية إلى صور رقمية لتسهيل الوصول إليها وتوزيعها.
2. **بوابات الويب**:عرض معاينات المستندات على مواقع الويب دون الحاجة إلى قارئي PDF.
3. **أنظمة إدارة المحتوى (CMS)**:التكامل مع منصات CMS لإدارة وعرض كميات كبيرة من محتوى PDF بكفاءة.

## اعتبارات الأداء
لتحسين أداء تطبيقك باستخدام GroupDocs.Viewer لـ .NET:
- قم بالحد من استخدام الذاكرة عن طريق معالجة المستندات على شكل أجزاء إذا كنت تتعامل مع ملفات كبيرة.
- استخدم الطرق غير المتزامنة عندما يكون ذلك ممكنًا لتجنب حظر الخيوط أثناء العرض.
- تخلص من `Viewer` الحالات فورًا بعد الاستخدام لتحرير الموارد.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية عرض صفحات PDF كصور PNG مع الحفاظ على أحجامها الأصلية باستخدام GroupDocs.Viewer لـ .NET. تناولنا إعداد بيئتك، وتكوين الخيارات اللازمة لتحقيق أفضل النتائج، واستكشاف التطبيقات العملية لهذه الوظيفة.

وتتضمن الخطوات التالية تجربة خيارات العرض الأخرى المتوفرة في GroupDocs.Viewer أو دمجها في مشاريع أكبر لتحسين إمكانيات إدارة المستندات.

## قسم الأسئلة الشائعة
1. **ما هي أفضل طريقة للتعامل مع ملفات PDF الكبيرة باستخدام GroupDocs.Viewer؟**
   - قم بمعالجة المستندات في أجزاء أصغر واستخدم طرقًا غير متزامنة للحفاظ على الأداء.
2. **هل يمكنني تخصيص أسماء ملفات PNG الناتجة؟**
   - نعم، عن طريق تحديد نمط التسمية في `PngViewOptions`.
3. **هل من الممكن عرض صفحات محددة فقط؟**
   - بالتأكيد، يمكنك تكوين `PageNumbers` في `PngViewOptions` لتحديد الصفحات التي سيتم عرضها.
4. **كيف أتعامل مع الترخيص لـ GroupDocs.Viewer؟**
   - تتضمن الخيارات إصدارًا تجريبيًا مجانيًا، أو ترخيصًا مؤقتًا، أو شراء ترخيص كامل.
5. **هل يمكن استخدام هذا الإعداد في تطبيقات الويب؟**
   - نعم، إنه مناسب لعرض ملفات PDF من جانب الخادم في ASP.NET Core وأطر عمل الويب الأخرى المستندة إلى .NET.

## موارد
- [التوثيق](https://docs.groupdocs.com/viewer/net/)
- [مرجع واجهة برمجة التطبيقات](https://reference.groupdocs.com/viewer/net/)
- [تنزيل GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [شراء الترخيص](https://purchase.groupdocs.com/buy)
- [نسخة تجريبية مجانية](https://releases.groupdocs.com/viewer/net/)
- [رخصة مؤقتة](https://purchase.groupdocs.com/temporary-license/)
- [منتدى الدعم](https://forum.groupdocs.com/c/viewer/9)