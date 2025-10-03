---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके HTML, JPG, PNG, और PDF में FODG और ODG छवियों को प्रस्तुत करना सीखें। अपने दस्तावेज़ प्रबंधन को बेहतर बनाएँ।"
"linktitle": "FODG और ODG छवियाँ प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "FODG और ODG छवियाँ प्रस्तुत करें"
"url": "/hi/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# FODG और ODG छवियाँ प्रस्तुत करें

## परिचय
सॉफ़्टवेयर डेवलपमेंट की दुनिया में, दस्तावेज़ प्रारूपों का कुशल संचालन सर्वोपरि है। GroupDocs.Viewer for .NET एक शक्तिशाली उपकरण है जिसे .NET अनुप्रयोगों के भीतर FODG और ODG छवियों को प्रस्तुत करने की प्रक्रिया को सरल बनाने के लिए डिज़ाइन किया गया है। यह ट्यूटोरियल आपको GroupDocs.Viewer for .NET का उपयोग करके इन छवियों को विभिन्न स्वरूपों, जैसे HTML, JPG, PNG और PDF में प्रस्तुत करने के लिए आवश्यक चरणों के माध्यम से मार्गदर्शन करेगा।

![.NET के लिए GroupDocs.Viewer के साथ FODG और ODG छवियाँ प्रस्तुत करें](/viewer/image-rendering/render-fodg-and--odg-images.png)

## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. .NET के लिए GroupDocs.Viewer: .NET के लिए GroupDocs.Viewer को डाउनलोड करें और इंस्टॉल करें [यहाँ](https://releases.groupdocs.com/viewer/net/).
2. .NET फ्रेमवर्क: सुनिश्चित करें कि आपके सिस्टम पर .NET फ्रेमवर्क स्थापित है।
3. C# का बुनियादी ज्ञान: C# प्रोग्रामिंग भाषा से परिचित होना उपयोगी होगा।

## नामस्थान आयात करें
कार्यान्वयन शुरू करने से पहले, आवश्यक नामस्थान आयात करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## चरण 1: आउटपुट निर्देशिका सेट करें
```csharp
string outputDirectory = "Your Document Directory";
```
प्रतिस्थापित करें `"Your Document Directory"` उस निर्देशिका पथ के साथ जहां आप रेंडर की गई छवियों को सहेजना चाहते हैं।
## चरण 2: HTML में रेंडर करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
यह चरण FODG छवि को HTML प्रारूप में प्रस्तुत करता है।
## चरण 3: JPG में रेंडर करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
यहां, FODG छवि को JPG प्रारूप में प्रस्तुत किया गया है।
## चरण 4: PNG में रेंडर करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
यह चरण FODG छवि को PNG प्रारूप में परिवर्तित करता है।
## चरण 5: पीडीएफ में रेंडर करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
अंततः, FODG छवि को PDF प्रारूप में प्रस्तुत किया जाता है।

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए GroupDocs.Viewer का उपयोग करके FODG और ODG छवियों को विभिन्न स्वरूपों में रेंडर करने का तरीका खोजा है। इन चरणों का पालन करके, आप अपने .NET अनुप्रयोगों में दस्तावेज़ रेंडरिंग क्षमताओं को सहजता से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या GroupDocs.Viewer for .NET .NET फ्रेमवर्क के सभी संस्करणों के साथ संगत है?
.NET के लिए GroupDocs.Viewer नवीनतम सहित .NET फ्रेमवर्क संस्करणों की एक विस्तृत श्रृंखला के साथ संगत है।
### क्या मैं .NET के लिए GroupDocs.Viewer के साथ दस्तावेजों को एसिंक्रोनस रूप से प्रस्तुत कर सकता हूं?
हां, GroupDocs.Viewer for .NET बेहतर प्रदर्शन के लिए अतुल्यकालिक रेंडरिंग क्षमताएं प्रदान करता है।
### क्या GroupDocs.Viewer for .NET एन्क्रिप्टेड दस्तावेज़ों को प्रस्तुत करने का समर्थन करता है?
हां, GroupDocs.Viewer for .NET उचित डिक्रिप्शन कुंजियों के साथ एन्क्रिप्टेड दस्तावेज़ों को प्रस्तुत करने का समर्थन करता है।
### क्या .NET के लिए GroupDocs.Viewer के साथ रेंडरिंग आउटपुट को कस्टमाइज़ करना संभव है?
बिल्कुल, GroupDocs.Viewer for .NET आपकी आवश्यकताओं के अनुसार रेंडरिंग आउटपुट को तैयार करने के लिए विभिन्न अनुकूलन विकल्प प्रदान करता है।
### क्या मैं .NET के लिए GroupDocs.Viewer का उपयोग करके दूरस्थ संग्रहण स्थानों से दस्तावेज़ प्रस्तुत कर सकता हूँ?
हां, GroupDocs.Viewer for .NET स्थानीय और दूरस्थ भंडारण स्थानों दोनों से दस्तावेज़ प्रस्तुत करने का समर्थन करता है।