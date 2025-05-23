---
title: कस्टम फ़ॉन्ट्स के साथ प्रस्तुत करें
linktitle: कस्टम फ़ॉन्ट्स के साथ प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके कस्टम फ़ॉन्ट के साथ दस्तावेज़ प्रस्तुत करना सीखें। दृश्य प्रस्तुतियों को सहजता से बढ़ाएं।
weight: 18
url: /hi/net/rendering-options/render-custom-fonts/
---

# कस्टम फ़ॉन्ट्स के साथ प्रस्तुत करें

## परिचय
.NET विकास के क्षेत्र में, GroupDocs.Viewer विभिन्न प्रारूपों के दस्तावेज़ों को प्रस्तुत करने के लिए एक शक्तिशाली समाधान प्रदान करता है। अपनी कई क्षमताओं के बीच, GroupDocs.Viewer आपके अनुप्रयोगों में वैयक्तिकरण और लचीलेपन की एक परत जोड़ते हुए, कस्टम फ़ॉन्ट के साथ दस्तावेज़ों को प्रस्तुत करने में सक्षम बनाता है।
## आवश्यक शर्तें
.NET के लिए GroupDocs.Viewer का उपयोग करके कस्टम फ़ॉन्ट के साथ दस्तावेज़ प्रस्तुत करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
### 1. .NET के लिए GroupDocs.Viewer स्थापित करें
.NET के लिए GroupDocs.Viewer का उपयोग करने के लिए, आपको इसे अपने विकास परिवेश में स्थापित करना होगा। आप दिए गए लिंक से आवश्यक पैकेज डाउनलोड कर सकते हैं:
[.NET के लिए GroupDocs.Viewer डाउनलोड करें](https://releases.groupdocs.com/viewer/net/)
### 2. फ़ॉन्ट्स प्राप्त करें
दस्तावेज़ों को प्रस्तुत करने के लिए आप जो कस्टम फ़ॉन्ट उपयोग करना चाहते हैं उसे तैयार करें। सुनिश्चित करें कि ये फ़ॉन्ट आपके एप्लिकेशन वातावरण में पहुंच योग्य हैं।
### 3. एक विकास वातावरण स्थापित करें
अपने सिस्टम पर एक कार्यशील .NET विकास वातावरण स्थापित करें। सुनिश्चित करें कि आपके पास आवश्यक उपकरण और ढाँचे स्थापित हैं।
### 4. C# और .NET की बुनियादी समझ
ट्यूटोरियल के साथ प्रभावी ढंग से पालन करने के लिए C# प्रोग्रामिंग भाषा और .NET फ्रेमवर्क की बुनियादी बातों से खुद को परिचित करें।

## नामस्थान आयात करें
.NET के लिए GroupDocs.Viewer का उपयोग करके कस्टम फ़ॉन्ट के साथ दस्तावेज़ प्रस्तुत करने के लिए, आपको अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करने की आवश्यकता है।

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Fonts;
using GroupDocs.Viewer.Options;
```

## चरण 1: फ़ॉन्ट स्रोत सेट करें
सबसे पहले, दस्तावेज़ों को प्रस्तुत करने के लिए उपयोग किए जाने वाले फ़ॉन्ट स्रोतों को परिभाषित करें। यह चरण सुनिश्चित करता है कि GroupDocs.Viewer कस्टम फ़ॉन्ट तक पहुंच सकता है।
```csharp
FontSettings.SetFontSources(
    new FolderFontSource(Utils.FontsPath, Fonts.SearchOption.TopFolderOnly));
```
## चरण 2: आउटपुट डायरेक्टरी को परिभाषित करें
वह निर्देशिका निर्दिष्ट करें जहाँ आप प्रस्तुत दस्तावेज़ों को सहेजना चाहते हैं।
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 3: पृष्ठ फ़ाइल पथ स्वरूप को परिभाषित करें
रेंडर किए गए दस्तावेज़ पृष्ठों वाली आउटपुट HTML फ़ाइलों के नामकरण के लिए प्रारूप सेट करें।
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## चरण 4: कस्टम फ़ॉन्ट्स के साथ दस्तावेज़ प्रस्तुत करें
 दस्तावेज़ को कस्टम फ़ॉन्ट के साथ प्रस्तुत करने के लिए GroupDocs.Viewer API का उपयोग करें। प्रतिस्थापित करें`TestFiles.MISSING_FONT_ODG` आपके दस्तावेज़ के पथ के साथ।
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_ODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## चरण 5: आउटपुट निर्देशिका प्रदर्शित करें
उपयोगकर्ता को उस स्थान के बारे में सूचित करें जहां प्रस्तुत दस्तावेज़ पृष्ठ सहेजे गए हैं।
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया कि .NET के लिए GroupDocs.Viewer का उपयोग करके कस्टम फ़ॉन्ट के साथ दस्तावेज़ों को कैसे प्रस्तुत किया जाए। चरण-दर-चरण मार्गदर्शिका का पालन करके और दिए गए उदाहरण का लाभ उठाकर, आप अपने .NET अनुप्रयोगों में दस्तावेज़ों की दृश्य प्रस्तुति को बढ़ा सकते हैं।
## पूछे जाने वाले प्रश्न
### प्रश्न: क्या मैं वेब अनुप्रयोगों में .NET के लिए GroupDocs.Viewer का उपयोग करके कस्टम फ़ॉन्ट के साथ दस्तावेज़ प्रस्तुत कर सकता हूँ?
हाँ, .NET के लिए GroupDocs.Viewer को कस्टम फ़ॉन्ट के साथ दस्तावेज़ प्रस्तुत करने के लिए डेस्कटॉप और वेब अनुप्रयोगों दोनों में एकीकृत किया जा सकता है।
### प्रश्न: क्या .NET के लिए GroupDocs.Viewer विभिन्न दस्तावेज़ प्रारूपों के साथ संगत है?
बिल्कुल! GroupDocs.Viewer पीडीएफ, माइक्रोसॉफ्ट ऑफिस फ़ाइलों, छवियों और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### प्रश्न: क्या उपयोग किए जा सकने वाले कस्टम फ़ॉन्ट के प्रकारों पर कोई सीमाएँ हैं?
जब तक कस्टम फ़ॉन्ट एप्लिकेशन वातावरण में पहुंच योग्य हैं, .NET के लिए GroupDocs.Viewer बिना किसी सीमा के उन फ़ॉन्ट के साथ दस्तावेज़ प्रस्तुत कर सकता है।
### प्रश्न: क्या मैं प्रस्तुत दस्तावेज़ों के आउटपुट स्वरूप को अनुकूलित कर सकता हूँ?
हां, .NET के लिए GroupDocs.Viewer HTML, छवि प्रारूप और पीडीएफ सहित आउटपुट प्रारूप को अनुकूलित करने के विकल्प प्रदान करता है।
### प्रश्न: क्या .NET के लिए GroupDocs.Viewer डेवलपर्स के लिए समर्थन और दस्तावेज़ीकरण प्रदान करता है?
निश्चित रूप से! GroupDocs, GroupDocs.Viewer का प्रभावी ढंग से उपयोग करने में डेवलपर्स की सहायता के लिए व्यापक दस्तावेज़ीकरण, समर्थन के लिए फ़ोरम और संसाधन प्रदान करता है।