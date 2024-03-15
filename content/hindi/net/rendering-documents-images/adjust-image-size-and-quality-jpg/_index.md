---
title: छवि आकार और गुणवत्ता समायोजित करें (जेपीजी)
linktitle: छवि आकार और गुणवत्ता समायोजित करें (जेपीजी)
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए Groupdocs.Viewer का उपयोग करके JPEG प्रारूप में छवि आकार और गुणवत्ता को अनुकूलित करना सीखें। अपने दस्तावेज़ देखने के अनुभव को बेहतर बनाएँ।
type: docs
weight: 11
url: /hi/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## परिचय
.NET के लिए Groupdocs.Viewer एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को दस्तावेज़ देखने की कार्यक्षमता को उनके .NET अनुप्रयोगों में सहजता से एकीकृत करने में सक्षम बनाता है। दस्तावेज़ देखने के अनुप्रयोगों में एक सामान्य आवश्यकता छवियों के आकार और गुणवत्ता को समायोजित करने की क्षमता है, खासकर जेपीईजी (जेपीजी) छवियों के साथ काम करते समय। इस ट्यूटोरियल में, हम आपको .NET के लिए Groupdocs.Viewer का उपयोग करके छवि आकार और गुणवत्ता को समायोजित करने की प्रक्रिया के बारे में बताएंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1. C# प्रोग्रामिंग भाषा की बुनियादी समझ।
2. आपके सिस्टम पर विज़ुअल स्टूडियो स्थापित है।
3.  .NET लाइब्रेरी के लिए Groupdocs.Viewer स्थापित। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.groupdocs.com/viewer/net/).

## नामस्थान आयात करें
सबसे पहले, आपको अपने C# कोड में आवश्यक नामस्थान आयात करना होगा। ये नेमस्पेस Groupdocs.Viewer के साथ काम करने के लिए आवश्यक कक्षाओं और विधियों तक पहुंच प्रदान करते हैं।
## चरण 1: नामस्थान आयात करें
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

अब, आइए बेहतर समझ के लिए दिए गए उदाहरण कोड को कई चरणों में तोड़ें।
## चरण 2: आउटपुट निर्देशिका और पृष्ठ फ़ाइल पथ प्रारूप सेट करें
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
इस चरण में, हम आउटपुट निर्देशिका निर्दिष्ट करते हैं जहां प्रदान की गई छवियां सहेजी जाएंगी और प्रत्येक पृष्ठ छवि के फ़ाइल पथ के लिए प्रारूप को परिभाषित करेंगे।
## चरण 3: व्यूअर आरंभ करें और JPG व्यू विकल्प कॉन्फ़िगर करें
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
यहां, हम व्यूअर ऑब्जेक्ट को देखे जाने वाले दस्तावेज़ के पथ के साथ प्रारंभ करते हैं। फिर, हम JpgViewOptions का एक उदाहरण बनाते हैं और JPEG छवियों के लिए वांछित चौड़ाई और ऊंचाई निर्धारित करते हैं।
## चरण 4: स्रोत दस्तावेज़ प्रस्तुत करें
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
अंत में, हम एक संदेश प्रिंट करते हैं जो स्रोत दस्तावेज़ के सफल प्रतिपादन और उस स्थान को दर्शाता है जहां आउटपुट छवियां सहेजी गई हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Groupdocs.Viewer का उपयोग करके JPEG छवियों के आकार और गुणवत्ता को कैसे समायोजित किया जाए। ऊपर बताए गए चरणों का पालन करके, आप आसानी से इस कार्यक्षमता को अपने .NET अनुप्रयोगों में शामिल कर सकते हैं, जिससे उपयोगकर्ताओं को अनुकूलित छवि देखने का अनुभव प्राप्त होगा।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं छवि गुणवत्ता भी समायोजित कर सकता हूँ?
हाँ, आप JpgViewOptions में गुणवत्ता गुण सेट करके छवि गुणवत्ता को समायोजित कर सकते हैं।
### .NET के लिए Groupdocs.Viewer द्वारा कौन से दस्तावेज़ प्रारूप समर्थित हैं?
.NET के लिए Groupdocs.Viewer DOCX, PDF, PPTX, XLSX और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या .NET के लिए Groupdocs.Viewer .NET कोर के साथ संगत है?
हां, .NET के लिए Groupdocs.Viewer पारंपरिक .NET फ्रेमवर्क के साथ-साथ .NET कोर के साथ संगत है।
### क्या मैं आउटपुट फ़ाइल नामकरण प्रारूप को अनुकूलित कर सकता हूँ?
हाँ, आप कोड में pageFilePathFormat वैरिएबल को संशोधित करके आउटपुट फ़ाइल नामकरण प्रारूप को अनुकूलित कर सकते हैं।
### क्या .NET के लिए Groupdocs.Viewer दस्तावेज़ एनोटेशन का समर्थन करता है?
हाँ, .NET के लिए Groupdocs.Viewer टेक्स्ट हाइलाइटिंग, अंडरलाइनिंग और टिप्पणी सहित दस्तावेज़ एनोटेशन के लिए व्यापक समर्थन प्रदान करता है।