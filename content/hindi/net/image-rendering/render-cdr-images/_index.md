---
title: सीडीआर छवियाँ प्रस्तुत करें
linktitle: सीडीआर छवियाँ प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके CDR छवियों को HTML, JPG, PNG और PDF में प्रस्तुत करना सीखें। इस ट्यूटोरियल के साथ आसानी से CorelDRAW फ़ाइलों को परिवर्तित करें।
weight: 12
url: /hi/net/image-rendering/render-cdr-images/
---
## परिचय
इस ट्यूटोरियल में, हम .NET के लिए GroupDocs.Viewer का उपयोग करके CDR (CorelDRAW) छवियों को प्रस्तुत करने की प्रक्रिया में आपका मार्गदर्शन करेंगे। सीडीआर एक फ़ाइल स्वरूप है जो मुख्य रूप से वेक्टर ग्राफ़िक्स संपादक CorelDRAW से संबद्ध है। GroupDocs.Viewer के साथ, आप CDR फ़ाइलों को HTML, JPG, PNG और PDF जैसे विभिन्न प्रारूपों में आसानी से परिवर्तित कर सकते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  .NET के लिए GroupDocs.Viewer: सुनिश्चित करें कि आपने .NET के लिए GroupDocs.Viewer स्थापित किया है। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.groupdocs.com/viewer/net/).
2. दस्तावेज़ निर्देशिका: एक निर्देशिका तैयार करें जहाँ आप प्रस्तुत छवियों को सहेजना चाहते हैं।
3. C# का बुनियादी ज्ञान: कोड उदाहरणों को समझने के लिए C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।
## नामस्थान आयात करें
कोड उदाहरणों पर विचार करने से पहले, अपनी C# फ़ाइल में आवश्यक नामस्थान आयात करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
अब, आइए प्रत्येक उदाहरण को कई चरणों में तोड़ें:
## HTML को प्रतिपादन
1. उस आउटपुट निर्देशिका को परिभाषित करें जहाँ आप प्रस्तुत HTML फ़ाइलों को सहेजना चाहते हैं:
```csharp
string outputDirectory = "Your Document Directory";
```
2. HTML फ़ाइलों के लिए फ़ाइल पथ प्रारूप निर्दिष्ट करें:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. सीडीआर फ़ाइल को HTML में प्रस्तुत करने के लिए व्यूअर क्लास का उपयोग करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## JPG को प्रतिपादन
1. JPG फ़ाइलों के लिए फ़ाइल पथ प्रारूप को परिभाषित करें:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. सीडीआर फ़ाइल को जेपीजी में प्रस्तुत करने के लिए व्यूअर क्लास का उपयोग करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## पीएनजी को प्रस्तुत करना
1. पीएनजी फ़ाइलों के लिए फ़ाइल पथ प्रारूप को परिभाषित करें:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. सीडीआर फ़ाइल को पीएनजी में प्रस्तुत करने के लिए व्यूअर क्लास का उपयोग करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## पीडीएफ को प्रस्तुत करना
1. पीडीएफ के लिए फ़ाइल पथ प्रारूप को परिभाषित करें:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. सीडीआर फ़ाइल को पीडीएफ में प्रस्तुत करने के लिए व्यूअर क्लास का उपयोग करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  वैकल्पिक रूप से, आप अतिरिक्त पैरामीटर पास करके रेंडरिंग विकल्प निर्दिष्ट कर सकते हैं या विशिष्ट पेज रेंडर कर सकते हैं`viewer.View()` तरीका।
## निष्कर्ष
.NET के लिए GroupDocs.Viewer का उपयोग करके HTML, JPG, PNG और PDF जैसे विभिन्न प्रारूपों में CDR छवियों को प्रस्तुत करना एक सीधी प्रक्रिया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपनी आवश्यकताओं के आधार पर सीडीआर फ़ाइलों को कुशलतापूर्वक विभिन्न प्रारूपों में परिवर्तित कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या .NET के लिए GroupDocs.Viewer CDR फ़ाइलों के सभी संस्करणों के साथ संगत है?
.NET के लिए GroupDocs.Viewer CorelDRAW के विभिन्न संस्करणों द्वारा बनाई गई CDR फ़ाइलों के रेंडरिंग का समर्थन करता है।
### क्या मैं रेंडर की गई फ़ाइलों के आउटपुट को कस्टमाइज़ कर सकता हूँ?
हां, .NET के लिए GroupDocs.Viewer आउटपुट को अनुकूलित करने के लिए विभिन्न विकल्प प्रदान करता है, जैसे छवि गुणवत्ता समायोजित करना, वॉटरमार्क सेट करना आदि।
### क्या .NET के लिए GroupDocs.Viewer को किसी बाहरी निर्भरता की आवश्यकता है?
नहीं, .NET के लिए GroupDocs.Viewer एक स्टैंडअलोन लाइब्रेरी है और दस्तावेज़ों को प्रस्तुत करने के लिए किसी बाहरी निर्भरता की आवश्यकता नहीं है।
### क्या .NET के लिए GroupDocs.Viewer का कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप .NET के लिए GroupDocs.Viewer का निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[यहाँ](https://releases.groupdocs.com/).
### मुझे .NET के लिए GroupDocs.Viewer के लिए समर्थन कहाँ से मिल सकता है?
 आप GroupDocs.Viewer समुदाय फ़ोरम से समर्थन प्राप्त कर सकते हैं[यहाँ](https://forum.groupdocs.com/c/viewer/9).