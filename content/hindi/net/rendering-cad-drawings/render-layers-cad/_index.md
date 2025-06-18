---
"description": ".NET के लिए GroupDocs.Viewer के साथ .NET अनुप्रयोगों में CAD आरेखण को सहजता से रेंडर करें। रेंडरिंग विकल्पों का अन्वेषण करें, परतें कस्टमाइज़ करें, और बहुत कुछ।"
"linktitle": "CAD चित्रों में परतें प्रस्तुत करना"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "CAD चित्रों में परतें प्रस्तुत करना"
"url": "/hi/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
---

# CAD चित्रों में परतें प्रस्तुत करना

## परिचय
GroupDocs.Viewer for .NET एक शक्तिशाली उपकरण है जो डेवलपर्स को अपने .NET अनुप्रयोगों में दस्तावेज़ रेंडरिंग क्षमताओं को सहजता से एकीकृत करने में सक्षम बनाता है। चाहे आपको CAD ड्रॉइंग, PDF, Microsoft Office दस्तावेज़, या अधिक रेंडर करने की आवश्यकता हो, GroupDocs.Viewer एक व्यापक समाधान प्रदान करता है।
## आवश्यक शर्तें
.NET के लिए GroupDocs.Viewer का उपयोग करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
- C# प्रोग्रामिंग भाषा की बुनियादी समझ।
- आपके मशीन पर .NET विकास वातावरण स्थापित करें।
- .NET के लिए GroupDocs.Viewer स्थापित। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/viewer/net/).
- ट्यूटोरियल के लिए .NET दस्तावेज़ के लिए GroupDocs.Viewer तक पहुंच, जो यहां पाया जा सकता है [यहाँ](https://tutorials.groupdocs.com/viewer/net/).

## नामस्थान आयात करें
.NET के लिए GroupDocs.Viewer का उपयोग शुरू करने के लिए, आपको अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करने होंगे। इन चरणों का पालन करें:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

आइये दिए गए उदाहरण को कई चरणों में विभाजित करें:
## चरण 1: आउटपुट निर्देशिका परिभाषित करें
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: पृष्ठ फ़ाइल पथ प्रारूप निर्धारित करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## चरण 3: व्यूअर ऑब्जेक्ट को आरंभ करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // कोड ब्लॉक जारी है...
}
```
## चरण 4: HTML दृश्य विकल्प सेट करें
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## चरण 5: CAD परतें परिभाषित करें
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## चरण 6: दस्तावेज़ प्रस्तुत करें
```csharp
viewer.View(options);
```
## चरण 7: आउटपुट रेंडर किए गए दस्तावेज़ का स्थान
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## निष्कर्ष
.NET के लिए GroupDocs.Viewer के साथ, आपके .NET अनुप्रयोगों में CAD आरेखण को रेंडर करना एक सहज प्रक्रिया बन जाती है। इस गाइड में बताए गए चरणों का पालन करके, आप आसानी से अपने प्रोजेक्ट में दस्तावेज़ रेंडरिंग क्षमताओं को एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या GroupDocs.Viewer सभी प्रकार के CAD चित्रों के साथ संगत है?
हां, GroupDocs.Viewer DWG और DXF सहित CAD ड्राइंग प्रारूपों की एक विस्तृत श्रृंखला को प्रस्तुत करने का समर्थन करता है।
### क्या मैं CAD चित्रों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
बिल्कुल, GroupDocs.Viewer विभिन्न अनुकूलन विकल्प प्रदान करता है, जैसे आउटपुट प्रारूपों को प्रस्तुत करने या सेट करने के लिए परतें निर्दिष्ट करना।
### क्या GroupDocs.Viewer को दस्तावेज़ों को प्रस्तुत करने के लिए इंटरनेट कनेक्शन की आवश्यकता होती है?
नहीं, GroupDocs.Viewer इंटरनेट कनेक्शन की आवश्यकता के बिना स्थानीय रूप से रेंडरिंग करता है।
### क्या .NET के लिए GroupDocs.Viewer के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
हां, आप .NET के लिए GroupDocs.Viewer के निःशुल्क परीक्षण का उपयोग कर सकते हैं [यहाँ](https://releases.groupdocs.com/).
### मुझे .NET के लिए GroupDocs.Viewer का समर्थन कहां से मिल सकता है?
किसी भी तकनीकी सहायता या प्रश्नों के लिए, आप GroupDocs.Viewer फ़ोरम पर जा सकते हैं [यहाँ](https://forum.groupdocs.com/c/viewer/9).