---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके CAD ड्रॉइंग में एकल लेआउट रेंडर करना सीखें। अपने .NET अनुप्रयोगों में सहज एकीकरण के लिए आसान कदम।"
"linktitle": "CAD चित्रों में एकल लेआउट प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "CAD चित्रों में एकल लेआउट प्रस्तुत करें"
"url": "/hi/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
---

# CAD चित्रों में एकल लेआउट प्रस्तुत करें

## परिचय
.NET विकास के क्षेत्र में, CAD आरेखण को संभालना और देखना एक सामान्य आवश्यकता है। GroupDocs.Viewer for .NET .NET अनुप्रयोगों के भीतर CAD आरेखण रेंडर करने के लिए एक व्यापक समाधान प्रदान करके इस कार्य को सरल बनाता है। इस ट्यूटोरियल में, हम GroupDocs.Viewer for .NET का उपयोग करके CAD आरेखण में एकल लेआउट रेंडर करने में तल्लीन होंगे।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क की बुनियादी समझ।
- आपके सिस्टम पर Visual Studio स्थापित है.
- GroupDocs.Viewer for .NET लाइब्रेरी डाउनलोड की गई और आपके प्रोजेक्ट में ट्यूटोरियल। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/viewer/net/).
- CAD फ़ाइल स्वरूपों और उनकी संरचनाओं से परिचित होना।

## नामस्थान आयात करें
सबसे पहले, GroupDocs.Viewer कार्यक्षमताओं तक पहुँचने के लिए अपने C# कोड में आवश्यक नामस्थान आयात करें।

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## चरण 1: आउटपुट निर्देशिका परिभाषित करें
वह निर्देशिका निर्दिष्ट करें जहां आप प्रस्तुत आउटपुट को सहेजना चाहते हैं।
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: पृष्ठ फ़ाइल पथ प्रारूप निर्धारित करें
प्रत्येक रेंडर किए गए पृष्ठ के फ़ाइल पथ के लिए प्रारूप निर्धारित करें.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## चरण 3: व्यूअर ऑब्जेक्ट को इंस्टैंशिएट करें
GroupDocs.Viewer द्वारा प्रदान किए गए Viewer वर्ग का एक उदाहरण बनाएँ.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## चरण 4: HTML दृश्य विकल्प कॉन्फ़िगर करें
एम्बेडेड संसाधनों के साथ HTML आउटपुट प्रस्तुत करने के लिए विकल्प कॉन्फ़िगर करें।
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## चरण 5: CAD लेआउट नाम निर्दिष्ट करें
उस CAD लेआउट का नाम निर्दिष्ट करें जिसे आप रेंडर करना चाहते हैं।
```csharp
options.CadOptions.LayoutName = "Model";
```
## चरण 6: CAD ड्राइंग प्रस्तुत करें
निर्दिष्ट विकल्पों के साथ Viewer ऑब्जेक्ट की View विधि को लागू करें।
```csharp
viewer.View(options);
```
## चरण 7: सफलता संदेश प्रदर्शित करें
स्रोत दस्तावेज़ के सफल प्रस्तुतीकरण के बारे में उपयोगकर्ता को सूचित करें।
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## निष्कर्ष
CAD ड्रॉइंग को रेंडर करना, खास तौर पर लेआउट के साथ काम करते समय, एक कठिन काम हो सकता है। हालाँकि, GroupDocs.Viewer for .NET के साथ, प्रक्रिया सहज और कुशल हो जाती है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपने .NET अनुप्रयोगों के भीतर CAD ड्रॉइंग में एक लेआउट को आसानी से रेंडर कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं .NET के लिए GroupDocs.Viewer का उपयोग करके एक साथ कई लेआउट प्रस्तुत कर सकता हूं?
हां, .NET के लिए GroupDocs.Viewer CAD चित्रों से कई लेआउट प्रस्तुत करने का समर्थन करता है।
### क्या GroupDocs.Viewer विभिन्न CAD फ़ाइल स्वरूपों के साथ संगत है?
निश्चित रूप से, GroupDocs.Viewer CAD फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है, जिसमें DWG, DXF, DGN और बहुत कुछ शामिल है।
### क्या मैं CAD चित्रों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
हां, GroupDocs.Viewer आपकी आवश्यकताओं के अनुसार रेंडरिंग सेटिंग्स को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### क्या .NET के लिए GroupDocs.Viewer के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
हां, आप उपलब्ध निःशुल्क परीक्षण के साथ GroupDocs.Viewer की सुविधाओं का पता लगा सकते हैं [यहाँ](https://releases.groupdocs.com/).
### मुझे .NET के लिए GroupDocs.Viewer का समर्थन कहां से मिल सकता है?
किसी भी प्रश्न या सहायता के लिए, आप GroupDocs.Viewer फ़ोरम पर जा सकते हैं [यहाँ](https://forum.groupdocs.com/c/viewer/9).