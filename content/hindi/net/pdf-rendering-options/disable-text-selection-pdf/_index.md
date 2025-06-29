---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके PDF में टेक्स्ट चयन को अक्षम करने का तरीका जानें। सहज एकीकरण के लिए हमारे चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"linktitle": "पीडीएफ में पाठ चयन अक्षम करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "पीडीएफ में पाठ चयन अक्षम करें"
"url": "/hi/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
---

# पीडीएफ में पाठ चयन अक्षम करें

## परिचय
GroupDocs.Viewer for .NET एक शक्तिशाली दस्तावेज़ रेंडरिंग API है जो डेवलपर्स को अपने .NET अनुप्रयोगों में दस्तावेज़ देखने की क्षमताओं को आसानी से एकीकृत करने की अनुमति देता है। GroupDocs.Viewer द्वारा प्रदान की जाने वाली प्रमुख कार्यक्षमताओं में से एक PDF दस्तावेज़ों में टेक्स्ट चयन को अक्षम करने की क्षमता है। यह सुविधा विशेष रूप से उन परिदृश्यों में उपयोगी है जहाँ आपको उपयोगकर्ताओं को संवेदनशील दस्तावेज़ों से टेक्स्ट कॉपी करने से रोकने की आवश्यकता होती है, जिससे दस्तावेज़ की सुरक्षा और अखंडता सुनिश्चित होती है।

![GroupDocs.Viewer .NET के साथ PDF में टेक्स्ट चयन अक्षम करें](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## आवश्यक शर्तें
इससे पहले कि हम .NET के लिए GroupDocs.Viewer का उपयोग करके PDF में पाठ चयन को अक्षम करने के बारे में चरण-दर-चरण मार्गदर्शिका में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. .NET के लिए GroupDocs.Viewer की स्थापना: सुनिश्चित करें कि आपने .NET के लिए GroupDocs.Viewer को डाउनलोड और इंस्टॉल किया है [लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/).
2. दस्तावेज़ निर्देशिका: एक निर्देशिका तैयार करें जहाँ आपके दस्तावेज़ संग्रहीत किए जाएँगे। PDF दस्तावेज़ को रेंडर करने के लिए आपको कोड स्निपेट में इस निर्देशिका को निर्दिष्ट करना होगा।

## नामस्थान आयात करें
सबसे पहले, आपको .NET के लिए GroupDocs.Viewer द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नामस्थानों को आयात करना होगा। यहाँ बताया गया है कि आप यह कैसे कर सकते हैं:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

अब, आइए .NET के लिए GroupDocs.Viewer का उपयोग करके एक पीडीएफ दस्तावेज़ में पाठ चयन को अक्षम करने की प्रक्रिया को कई चरणों में तोड़ दें:
## चरण 1: आउटपुट निर्देशिका निर्दिष्ट करें
```csharp
string outputDirectory = "Your Document Directory";
```
इस चरण में, प्रतिस्थापित करें `"Your Document Directory"` उस निर्देशिका पथ के साथ जहां आपका पीडीएफ दस्तावेज़ स्थित है।
## चरण 2: पृष्ठ फ़ाइल पथ प्रारूप निर्धारित करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
यह चरण रेंडर किए गए HTML पेजों के फ़ाइल पथों के लिए प्रारूप को परिभाषित करता है। PDF दस्तावेज़ का प्रत्येक पृष्ठ एक अनुक्रमिक पृष्ठ संख्या के साथ HTML फ़ाइल में परिवर्तित हो जाएगा।
## चरण 3: पाठ चयन अक्षम करके PDF दस्तावेज़ प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
प्रतिस्थापित करें `"Path to Your PDF Document"` आपकी PDF फ़ाइल के वास्तविक पथ के साथ। यह कोड स्निपेट एक आरंभ करता है `Viewer` ऑब्जेक्ट, संसाधनों को एम्बेड करने के लिए HTML दृश्य विकल्पों को कॉन्फ़िगर करता है, और सेटिंग द्वारा पाठ चयन को अक्षम करता है `RenderTextAsImage` संपत्ति को `true`.
## चरण 4: सफलता संदेश प्रदर्शित करें
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
पीडीएफ दस्तावेज़ को प्रस्तुत करने के बाद, यह चरण उस निर्देशिका के साथ एक सफलता संदेश प्रदर्शित करता है जहां प्रस्तुत HTML पृष्ठ संग्रहीत हैं।

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए GroupDocs.Viewer का उपयोग करके PDF दस्तावेज़ों में टेक्स्ट चयन को कैसे अक्षम किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप इस सुविधा को अपने .NET अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं, दस्तावेज़ सुरक्षा सुनिश्चित कर सकते हैं और उपयोगकर्ता अनुभव को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं रेंडर किए गए HTML पृष्ठों के लिए आउटपुट निर्देशिका को अनुकूलित कर सकता हूँ?
हां, आप कोई भी निर्देशिका पथ निर्दिष्ट कर सकते हैं जहां आप रेंडर किए गए HTML पृष्ठों को संग्रहीत करना चाहते हैं।
### क्या GroupDocs.Viewer for .NET .NET फ्रेमवर्क के विभिन्न संस्करणों के साथ संगत है?
हां, .NET के लिए GroupDocs.Viewer .NET कोर और .NET फ्रेमवर्क सहित .NET फ्रेमवर्क के विभिन्न संस्करणों के साथ संगत है।
### क्या पाठ चयन को अक्षम करने से PDF दस्तावेज़ की अन्य कार्यक्षमताएं प्रभावित होती हैं?
नहीं, टेक्स्ट चयन को अक्षम करने से केवल उपयोगकर्ता को दस्तावेज़ से टेक्स्ट का चयन करने और कॉपी करने से रोका जाता है। अन्य कार्यक्षमताएँ बरकरार रहती हैं।
### क्या मैं दस्तावेज़ को रेंडर करने के बाद पुनः पाठ चयन सक्षम कर सकता हूँ?
हां, आप बस सेटिंग करके पाठ चयन सक्षम कर सकते हैं `RenderTextAsImage` संपत्ति को `false` HTML दृश्य विकल्पों में.
### क्या .NET के लिए GroupDocs.Viewer का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप यहां से .NET के लिए GroupDocs.Viewer के निःशुल्क परीक्षण को एक्सेस कर सकते हैं [वेबसाइट](https://releases.groupdocs.com/).