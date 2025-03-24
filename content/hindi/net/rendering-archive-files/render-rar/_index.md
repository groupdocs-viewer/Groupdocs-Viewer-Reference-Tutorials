---
title: RAR पुरालेख प्रस्तुत करें
linktitle: RAR पुरालेख प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके RAR अभिलेखों को HTML, JPG, PNG, या PDF स्वरूपों में प्रस्तुत करना सीखें। RAR अभिलेखागार की सामग्री को आसानी से देखें और साझा करें।
weight: 13
url: /hi/net/rendering-archive-files/render-rar/
---

# RAR पुरालेख प्रस्तुत करें

## परिचय
RAR अभिलेखागार कई फ़ाइलों और फ़ोल्डरों को एक ही कंटेनर में संपीड़ित और संग्रहीत करने के लिए एक लोकप्रिय प्रारूप है। इन अभिलेखों की सामग्री को देखने या साझा करने के लिए RAR अभिलेखों को HTML, JPG, PNG, या PDF जैसे विभिन्न स्वरूपों में प्रस्तुत करना आवश्यक हो सकता है। इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए GroupDocs.Viewer का उपयोग करके RAR आर्काइव्स को कैसे प्रस्तुत किया जाए।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. .NET के लिए GroupDocs.Viewer: .NET लाइब्रेरी के लिए GroupDocs.Viewer इंस्टॉल करें[लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/).
2. नमूना RAR संग्रह: रेंडरिंग के लिए एक नमूना RAR संग्रह तैयार रखें।

## नामस्थान आयात करें
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## चरण 1: आउटपुट डायरेक्टरी को परिभाषित करें
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: HTML पर प्रस्तुत करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 3: JPG में प्रस्तुत करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 4: पीएनजी को प्रस्तुत करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 5: पीडीएफ में प्रस्तुत करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## निष्कर्ष
.NET के लिए GroupDocs.Viewer के साथ RAR अभिलेखों को विभिन्न प्रारूपों में प्रस्तुत करना सरल बना दिया गया है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप आसानी से RAR अभिलेखागार को HTML, JPG, PNG, या PDF प्रारूपों में परिवर्तित कर सकते हैं, जिससे उनकी सामग्री को आसानी से देखने और साझा करने में सक्षम बनाया जा सकता है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या .NET के लिए GroupDocs.Viewer एन्क्रिप्टेड RAR अभिलेखागार को संभाल सकता है?
हां, .NET के लिए GroupDocs.Viewer एन्क्रिप्टेड RAR अभिलेखागार को रेंडर करने का समर्थन करता है, बशर्ते कि रेंडरिंग प्रक्रिया के दौरान आवश्यक पासवर्ड प्रदान किए जाएं।
### क्या प्रस्तुत दस्तावेज़ों के आउटपुट स्वरूप को अनुकूलित करना संभव है?
बिल्कुल! .NET के लिए GroupDocs.Viewer व्यापक अनुकूलन विकल्प प्रदान करता है जो उपयोगकर्ताओं को उनकी प्राथमिकताओं के अनुसार प्रदान किए गए दस्तावेज़ों की उपस्थिति को अनुकूलित करने की अनुमति देता है।
### क्या .NET के लिए GroupDocs.Viewer RAR के अलावा अन्य संग्रह प्रारूपों को प्रस्तुत करने का समर्थन करता है?
हां, .NET के लिए GroupDocs.Viewer ZIP, TAR, 7z और अन्य सहित विभिन्न संग्रह प्रारूपों को प्रस्तुत करने का समर्थन करता है।
### क्या मैं अपने वेब एप्लिकेशन में .NET के लिए GroupDocs.Viewer को एकीकृत कर सकता हूँ?
निश्चित रूप से! .NET के लिए GroupDocs.Viewer एपीआई प्रदान करता है जो डेस्कटॉप और वेब अनुप्रयोगों दोनों में एकीकरण के लिए उपयुक्त है।
### क्या .NET के लिए GroupDocs.Viewer का कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप .NET के लिए GroupDocs.Viewer के निःशुल्क परीक्षण का लाभ उठा सकते हैं[वेबसाइट](https://releases.groupdocs.com/).