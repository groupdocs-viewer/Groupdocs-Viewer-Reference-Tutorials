---
title: विशिष्ट CAD प्रारूप प्रस्तुत करें (CF2)
linktitle: विशिष्ट CAD प्रारूप प्रस्तुत करें (CF2)
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए Groupdocs.Viewer का उपयोग करके CF2 जैसे विशिष्ट CAD प्रारूपों को HTML, JPG, PNG और PDF में प्रस्तुत करना सीखें।
weight: 12
url: /hi/net/rendering-cad-drawings/render-specific-cad-formats/
---

# विशिष्ट CAD प्रारूप प्रस्तुत करें (CF2)

## परिचय
इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए Groupdocs.Viewer का उपयोग करके विशिष्ट CAD प्रारूपों को कैसे प्रस्तुत किया जाए। Groupdocs.Viewer एक शक्तिशाली दस्तावेज़ व्यूअर एपीआई है जो डेवलपर्स को किसी भी बाहरी सॉफ़्टवेयर इंस्टॉलेशन की आवश्यकता के बिना अपने अनुप्रयोगों में 170 से अधिक दस्तावेज़ प्रकार प्रदर्शित करने की अनुमति देता है। विशेष रूप से, हम CAD प्रारूपों जैसे CF2 को HTML, JPG, PNG और PDF जैसे विभिन्न आउटपुट प्रारूपों में प्रस्तुत करने पर ध्यान केंद्रित करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
- आपके सिस्टम पर विज़ुअल स्टूडियो स्थापित है।
-  .NET SDK के लिए Groupdocs.Viewer। आप इसे यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.groupdocs.com/viewer/net/).
- C# प्रोग्रामिंग भाषा का बुनियादी ज्ञान।
## नामस्थान आयात करें
सबसे पहले, आइए CAD प्रारूपों को प्रस्तुत करने के लिए आवश्यक आवश्यक नामस्थान आयात करें।
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
अब, आइए प्रत्येक उदाहरण को कई चरणों में तोड़ें:
## CF2 को HTML में प्रस्तुत करें
### चरण 1: आउटपुट निर्देशिका को परिभाषित करें जहां प्रस्तुत HTML सहेजा जाएगा।
```csharp
string outputDirectory = "Your Document Directory";
```
### चरण 2: HTML आउटपुट के लिए फ़ाइल पथ प्रारूप को परिभाषित करें।
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### चरण 3: व्यूअर ऑब्जेक्ट को प्रारंभ करें और इनपुट CF2 फ़ाइल निर्दिष्ट करें।
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // यदि आवश्यक हो तो अतिरिक्त रेंडरिंग विकल्प सेट करें
    // विकल्प.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 को JPG में प्रस्तुत करें
### चरण 1: JPG आउटपुट के लिए फ़ाइल पथ प्रारूप को परिभाषित करें।
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### चरण 2: व्यूअर ऑब्जेक्ट को प्रारंभ करें और इनपुट CF2 फ़ाइल निर्दिष्ट करें।
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // यदि आवश्यक हो तो अतिरिक्त रेंडरिंग विकल्प सेट करें
    // विकल्प.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 को PNG में प्रस्तुत करें

### चरण 1: पीएनजी आउटपुट के लिए फ़ाइल पथ प्रारूप को परिभाषित करें।
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### चरण 2: व्यूअर ऑब्जेक्ट को प्रारंभ करें और इनपुट CF2 फ़ाइल निर्दिष्ट करें।
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // यदि आवश्यक हो तो अतिरिक्त रेंडरिंग विकल्प सेट करें
    // विकल्प.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 को पीडीएफ में प्रस्तुत करें
### चरण 1: पीडीएफ आउटपुट के लिए फ़ाइल पथ प्रारूप को परिभाषित करें।
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### चरण 2: व्यूअर ऑब्जेक्ट को प्रारंभ करें और इनपुट CF2 फ़ाइल निर्दिष्ट करें।
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // यदि आवश्यक हो तो अतिरिक्त रेंडरिंग विकल्प सेट करें
    // विकल्प.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा कि .NET के लिए Groupdocs.Viewer का उपयोग करके CF2 जैसे विशिष्ट CAD प्रारूपों को कैसे प्रस्तुत किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप दस्तावेज़ रेंडरिंग क्षमताओं को अपने .NET अनुप्रयोगों में आसानी से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Groupdocs.Viewer CF2 के अलावा अन्य CAD प्रारूप प्रस्तुत कर सकता है?
हां, Groupdocs.Viewer DWG, DXF, DGN और अन्य सहित CAD प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या Groupdocs.Viewer वेब अनुप्रयोगों में दस्तावेज़ प्रस्तुत करने के लिए उपयुक्त है?
बिल्कुल, Groupdocs.Viewer को सीधे ब्राउज़र में दस्तावेज़ प्रस्तुत करने के लिए वेब अनुप्रयोगों में सहजता से एकीकृत किया जा सकता है।
### क्या Groupdocs.Viewer को रेंडरिंग के लिए किसी बाहरी निर्भरता की आवश्यकता है?
नहीं, Groupdocs.Viewer एक स्टैंडअलोन एपीआई है और इसके लिए किसी बाहरी निर्भरता या सॉफ़्टवेयर इंस्टॉलेशन की आवश्यकता नहीं है।
### क्या मैं अपनी आवश्यकताओं के अनुसार रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
हां, Groupdocs.Viewer विभिन्न रेंडरिंग विकल्प प्रदान करता है जिन्हें आपकी विशिष्ट आवश्यकताओं को पूरा करने के लिए अनुकूलित किया जा सकता है।
### क्या Groupdocs.Viewer के लिए कोई परीक्षण संस्करण उपलब्ध है?
 हाँ, आप Groupdocs.Viewer का निःशुल्क परीक्षण संस्करण प्राप्त कर सकते हैं[यहाँ](https://releases.groupdocs.com/).