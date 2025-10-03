---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके CDR छवियों को HTML, JPG, PNG और PDF में रेंडर करना सीखें। इस ट्यूटोरियल के साथ आसानी से CorelDRAW फ़ाइलों को कनवर्ट करें।"
"linktitle": "सीडीआर छवियाँ प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "सीडीआर छवियाँ प्रस्तुत करें"
"url": "/hi/net/image-rendering/render-cdr-images/"
"weight": 12
type: docs
---
# सीडीआर छवियाँ प्रस्तुत करें

## परिचय
इस ट्यूटोरियल में, हम आपको .NET के लिए GroupDocs.Viewer का उपयोग करके CDR (CorelDRAW) इमेज रेंडर करने की प्रक्रिया के बारे में मार्गदर्शन करेंगे। CDR एक फ़ाइल प्रारूप है जो मुख्य रूप से CorelDRAW, एक वेक्टर ग्राफ़िक्स संपादक से जुड़ा है। GroupDocs.Viewer के साथ, आप आसानी से CDR फ़ाइलों को HTML, JPG, PNG और PDF जैसे विभिन्न स्वरूपों में परिवर्तित कर सकते हैं।

![.NET के लिए GroupDocs.Viewer के साथ CDR छवियाँ प्रस्तुत करें](/viewer/image-rendering/render-cdr-images.png)

## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. .NET के लिए GroupDocs.Viewer: सुनिश्चित करें कि आपने .NET के लिए GroupDocs.Viewer स्थापित किया है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/viewer/net/).
2. दस्तावेज़ निर्देशिका: एक निर्देशिका तैयार करें जहाँ आप रेंडर की गई छवियों को सहेजना चाहते हैं।
3. C# का बुनियादी ज्ञान: कोड उदाहरणों को समझने के लिए C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।
## नामस्थान आयात करें
कोड उदाहरणों में जाने से पहले, अपनी C# फ़ाइल में आवश्यक नामस्थान आयात करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
अब, आइए प्रत्येक उदाहरण को कई चरणों में विभाजित करें:
## HTML में रेंडर करना
1. आउटपुट निर्देशिका को परिभाषित करें जहां आप रेंडर की गई HTML फ़ाइलों को सहेजना चाहते हैं:
```csharp
string outputDirectory = "Your Document Directory";
```
2. HTML फ़ाइलों के लिए फ़ाइल पथ प्रारूप निर्दिष्ट करें:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. CDR फ़ाइल को HTML में प्रस्तुत करने के लिए Viewer वर्ग का उपयोग करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## JPG में प्रस्तुत करना
1. JPG फ़ाइलों के लिए फ़ाइल पथ प्रारूप परिभाषित करें:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. CDR फ़ाइल को JPG में प्रस्तुत करने के लिए Viewer वर्ग का उपयोग करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## PNG में रेंडर करना
1. PNG फ़ाइलों के लिए फ़ाइल पथ प्रारूप परिभाषित करें:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. CDR फ़ाइल को PNG में प्रस्तुत करने के लिए Viewer वर्ग का उपयोग करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## पीडीएफ में प्रस्तुत करना
1. पीडीएफ के लिए फ़ाइल पथ प्रारूप परिभाषित करें:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. CDR फ़ाइल को PDF में प्रस्तुत करने के लिए Viewer वर्ग का उपयोग करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. वैकल्पिक रूप से, आप रेंडरिंग विकल्प निर्दिष्ट कर सकते हैं या अतिरिक्त पैरामीटर पास करके विशिष्ट पृष्ठों को रेंडर कर सकते हैं `viewer.View()` तरीका।
## निष्कर्ष
.NET के लिए GroupDocs.Viewer का उपयोग करके HTML, JPG, PNG और PDF जैसे विभिन्न स्वरूपों में CDR छवियों को प्रस्तुत करना एक सीधी प्रक्रिया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपनी आवश्यकताओं के आधार पर CDR फ़ाइलों को कुशलतापूर्वक विभिन्न स्वरूपों में परिवर्तित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या GroupDocs.Viewer for .NET CDR फ़ाइलों के सभी संस्करणों के साथ संगत है?
GroupDocs.Viewer for .NET CorelDRAW के विभिन्न संस्करणों द्वारा बनाई गई CDR फ़ाइलों के प्रतिपादन का समर्थन करता है।
### क्या मैं रेंडर की गई फ़ाइलों के आउटपुट को अनुकूलित कर सकता हूँ?
हां, GroupDocs.Viewer for .NET आउटपुट को अनुकूलित करने के लिए विभिन्न विकल्प प्रदान करता है, जैसे छवि गुणवत्ता समायोजित करना, वॉटरमार्क सेट करना आदि।
### क्या .NET के लिए GroupDocs.Viewer को किसी बाहरी निर्भरता की आवश्यकता है?
नहीं, GroupDocs.Viewer for .NET एक स्टैंडअलोन लाइब्रेरी है और दस्तावेज़ों को प्रस्तुत करने के लिए किसी बाहरी निर्भरता की आवश्यकता नहीं है।
### क्या .NET के लिए GroupDocs.Viewer का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप .NET के लिए GroupDocs.Viewer का एक निःशुल्क परीक्षण संस्करण यहां से डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/).
### मुझे .NET के लिए GroupDocs.Viewer का समर्थन कहां से मिल सकता है?
आप GroupDocs.Viewer समुदाय फ़ोरम से सहायता प्राप्त कर सकते हैं [यहाँ](https://forum.groupdocs.com/c/viewer/9).