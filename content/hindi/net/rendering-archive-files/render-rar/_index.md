---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके RAR अभिलेखागार को HTML, JPG, PNG, या PDF प्रारूपों में प्रस्तुत करना सीखें। RAR अभिलेखागार की सामग्री को आसानी से देखें और साझा करें।"
"linktitle": "RAR अभिलेखागार प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "RAR अभिलेखागार प्रस्तुत करें"
"url": "/hi/net/rendering-archive-files/render-rar/"
"weight": 13
---

# RAR अभिलेखागार प्रस्तुत करें

## परिचय
RAR अभिलेखागार एकाधिक फ़ाइलों और फ़ोल्डरों को एक कंटेनर में संपीड़ित करने और संग्रहीत करने के लिए एक लोकप्रिय प्रारूप है। RAR अभिलेखागार को HTML, JPG, PNG, या PDF जैसे विभिन्न स्वरूपों में प्रस्तुत करना इन अभिलेखागार की सामग्री को देखने या साझा करने के लिए आवश्यक हो सकता है। इस ट्यूटोरियल में, हम .NET के लिए GroupDocs.Viewer का उपयोग करके RAR अभिलेखागार को प्रस्तुत करने का तरीका जानेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. .NET के लिए GroupDocs.Viewer: से .NET लाइब्रेरी के लिए GroupDocs.Viewer स्थापित करें [लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/).
2. नमूना RAR संग्रह: रेंडरिंग के लिए एक नमूना RAR संग्रह तैयार रखें।

## नामस्थान आयात करें
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## चरण 1: आउटपुट निर्देशिका परिभाषित करें
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: HTML में रेंडर करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 3: JPG में रेंडर करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 4: PNG में रेंडर करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 5: पीडीएफ में रेंडर करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## निष्कर्ष
RAR अभिलेखागार को विभिन्न स्वरूपों में प्रस्तुत करना GroupDocs.Viewer for .NET के साथ सरल बना दिया गया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप आसानी से RAR अभिलेखागार को HTML, JPG, PNG, या PDF स्वरूपों में परिवर्तित कर सकते हैं, जिससे उनकी सामग्री को आसानी से देखना और साझा करना संभव हो जाता है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या GroupDocs.Viewer for .NET एन्क्रिप्टेड RAR अभिलेखागार को संभाल सकता है?
हां, .NET के लिए GroupDocs.Viewer एन्क्रिप्टेड RAR अभिलेखागार को प्रस्तुत करने का समर्थन करता है बशर्ते कि रेंडरिंग प्रक्रिया के दौरान आवश्यक पासवर्ड प्रदान किए जाएं।
### क्या प्रस्तुत दस्तावेजों के आउटपुट स्वरूप को अनुकूलित करना संभव है?
बिल्कुल! GroupDocs.Viewer for .NET व्यापक अनुकूलन विकल्प प्रदान करता है जिससे उपयोगकर्ता अपने ट्यूटोरियल के अनुसार रेंडर किए गए दस्तावेज़ों की उपस्थिति को अनुकूलित कर सकते हैं।
### क्या GroupDocs.Viewer for .NET RAR के अलावा अन्य संग्रह प्रारूपों को प्रस्तुत करने का समर्थन करता है?
हां, .NET के लिए GroupDocs.Viewer ZIP, TAR, 7z और अधिक सहित विभिन्न संग्रह प्रारूपों को प्रस्तुत करने का समर्थन करता है।
### क्या मैं अपने वेब एप्लिकेशन में GroupDocs.Viewer for .NET को एकीकृत कर सकता हूं?
निश्चित रूप से! GroupDocs.Viewer for .NET डेस्कटॉप और वेब अनुप्रयोगों दोनों में एकीकरण के लिए उपयुक्त एपीआई प्रदान करता है।
### क्या .NET के लिए GroupDocs.Viewer का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप यहां से .NET के लिए GroupDocs.Viewer का निःशुल्क परीक्षण प्राप्त कर सकते हैं [वेबसाइट](https://releases.groupdocs.com/).