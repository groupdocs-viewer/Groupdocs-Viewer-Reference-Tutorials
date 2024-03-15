---
title: एआई छवियाँ प्रस्तुत करें
linktitle: एआई छवियाँ प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके .NET अनुप्रयोगों में AI छवियों को सहजता से प्रस्तुत करना सीखें। निर्बाध एकीकरण के लिए हमारे चरण-दर-चरण ट्यूटोरियल का पालन करें।
type: docs
weight: 10
url: /hi/net/image-rendering/render-ai-images/
---
## परिचय
.NET के लिए GroupDocs.Viewer एक शक्तिशाली लाइब्रेरी है जो डेवलपर्स को उनके .NET अनुप्रयोगों के भीतर विभिन्न दस्तावेज़ प्रारूपों को सहजता से प्रस्तुत करने में सक्षम बनाता है। चाहे आपको एआई छवियां, पीडीएफ, या अन्य दस्तावेज़ प्रकार प्रदर्शित करने की आवश्यकता हो, GroupDocs.Viewer आपकी परियोजनाओं में निर्बाध एकीकरण के लिए कई आउटपुट स्वरूपों की पेशकश करते हुए प्रक्रिया को सरल बनाता है। यह ट्यूटोरियल .NET के लिए GroupDocs.Viewer का उपयोग करके चरण दर चरण AI छवियों को प्रस्तुत करने में आपका मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. विजुअल स्टूडियो: अपने सिस्टम पर विजुअल स्टूडियो आईडीई स्थापित करें।
2.  .NET के लिए GroupDocs.Viewer: .NET के लिए GroupDocs.Viewer को डाउनलोड और इंस्टॉल करें।[वेबसाइट](https://releases.groupdocs.com/viewer/net/).
3. C# का बुनियादी ज्ञान: कोड उदाहरणों को समझने के लिए C# प्रोग्रामिंग भाषा से परिचित होना आवश्यक है।

## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, .NET के लिए GroupDocs.Viewer की कार्यक्षमताओं तक पहुंचने के लिए आवश्यक नेमस्पेस आयात करें।

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

.NET के लिए GroupDocs.Viewer के साथ AI छवियों को प्रस्तुत करने में कई चरण शामिल हैं, प्रत्येक एक विशिष्ट आउटपुट प्रारूप को पूरा करता है। नीचे, हम स्पष्टता के लिए प्रक्रिया को अलग-अलग चरणों में विभाजित करेंगे।
## चरण 1: आउटपुट निर्देशिका निर्दिष्ट करें
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: HTML को रेंडर करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 3: जेपीजी को प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 4: पीएनजी को प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 5: पीडीएफ में प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## निष्कर्ष
.NET के लिए GroupDocs.Viewer .NET अनुप्रयोगों के भीतर AI छवियों और विभिन्न दस्तावेज़ प्रारूपों को प्रस्तुत करने के लिए एक सहज समाधान प्रदान करता है। इस ट्यूटोरियल में दिए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, डेवलपर्स आसानी से दस्तावेज़ रेंडरिंग क्षमताओं को अपनी परियोजनाओं में एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं AI छवियों को प्रस्तुत करते समय आउटपुट स्वरूप को अनुकूलित कर सकता हूँ?
हां, .NET के लिए GroupDocs.Viewer पेज आकार, छवि गुणवत्ता और बहुत कुछ सहित आउटपुट स्वरूप को अनुकूलित करने के लिए विभिन्न विकल्प प्रदान करता है।
### क्या परीक्षण प्रयोजनों के लिए कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप GroupDocs से निःशुल्क परीक्षण संस्करण डाउनलोड कर सकते हैं[वेबसाइट](https://releases.groupdocs.com/viewer/net/) खरीदारी करने से पहले लाइब्रेरी की विशेषताओं का मूल्यांकन करना।
### क्या GroupDocs.Viewer एन्क्रिप्टेड AI छवियों को प्रस्तुत करने का समर्थन करता है?
हां, .NET के लिए GroupDocs.Viewer उचित डिक्रिप्शन कुंजियों के साथ एन्क्रिप्टेड AI छवियों को प्रस्तुत करने का समर्थन करता है।
### क्या मैं सीधे यूआरएल से एआई छवियां प्रस्तुत कर सकता हूं?
हाँ, .NET के लिए GroupDocs.Viewer स्थानीय फ़ाइल पथ के बजाय URL पथ निर्दिष्ट करके URL से AI छवियों को प्रस्तुत करने की अनुमति देता है।
### क्या .NET के लिए GroupDocs.Viewer के लिए तकनीकी सहायता उपलब्ध है?
 हां, GroupDocs के माध्यम से तकनीकी सहायता उपलब्ध है[मंच](https://forum.groupdocs.com/c/viewer/9), जहां आप प्रश्न पूछ सकते हैं, मुद्दों की रिपोर्ट कर सकते हैं और समुदाय से सहायता मांग सकते हैं।