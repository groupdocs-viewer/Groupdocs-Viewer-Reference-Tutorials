---
title: उपयोगकर्ता-परिभाषित मार्जिन के साथ HTML प्रस्तुत करें
linktitle: उपयोगकर्ता-परिभाषित मार्जिन के साथ HTML प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer का उपयोग करके .NET में कस्टम मार्जिन के साथ HTML को प्रस्तुत करना सीखें। दस्तावेज़ प्रस्तुतिकरण को सहजता से बढ़ाएँ।
weight: 11
url: /hi/net/rendering-web-documents/render-html-margins/
---

# उपयोगकर्ता-परिभाषित मार्जिन के साथ HTML प्रस्तुत करें

## परिचय
.NET विकास के दायरे में, उपयोगकर्ता-परिभाषित मार्जिन के साथ HTML को प्रस्तुत करना दृश्य रूप से आकर्षक दस्तावेज़ बनाने का एक महत्वपूर्ण पहलू है। चाहे वह किसी वेबसाइट के लिए मार्जिन समायोजित करना हो या प्रिंट लेआउट कॉन्फ़िगर करना हो, मार्जिन पर सटीक नियंत्रण सामग्री की समग्र प्रस्तुति को बढ़ाता है। इस ट्यूटोरियल में, हम इस कार्यक्षमता को निर्बाध रूप से प्राप्त करने के लिए .NET के लिए GroupDocs.Viewer का उपयोग करने के बारे में विस्तार से जानेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1.  .NET के लिए GroupDocs.Viewer: .NET लाइब्रेरी के लिए GroupDocs.Viewer इंस्टॉल करें। आप इसे यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.groupdocs.com/viewer/net/).
2. .NET वातावरण: .NET विकास के लिए कार्यशील वातावरण रखें।
3. HTML दस्तावेज़: एक HTML दस्तावेज़ तैयार करें जिसे आप कस्टम मार्जिन के साथ प्रस्तुत करना चाहते हैं।

## नामस्थान आयात करें
शुरू करने से पहले, आवश्यक नामस्थान आयात करना सुनिश्चित करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## चरण 1: आउटपुट निर्देशिका सेट करें
उस निर्देशिका को परिभाषित करें जहां आप रेंडर की गई फ़ाइलों को सहेजना चाहते हैं:
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: पृष्ठ फ़ाइल पथ स्वरूप को परिभाषित करें
प्रस्तुत पृष्ठों के फ़ाइल पथों के लिए प्रारूप सेट करें:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "html_render_margins_page_{0}.jpg");
```
## चरण 3: JPG रेंडरिंग के लिए मार्जिन समायोजित करें
HTML को JPG प्रारूप में प्रस्तुत करने के लिए मार्जिन कॉन्फ़िगर करें:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## चरण 4: पीएनजी रेंडरिंग के लिए मार्जिन समायोजित करें
इसी प्रकार, HTML को PNG प्रारूप में प्रस्तुत करने के लिए मार्जिन समायोजित करें:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```
## चरण 5: पीडीएफ रेंडरिंग के लिए मार्जिन समायोजित करें
पीडीएफ रेंडरिंग के लिए, तदनुसार मार्जिन सेट करें:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_HTML_file"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.WordProcessingOptions.LeftMargin = 40;
    options.WordProcessingOptions.RightMargin = 40;
    options.WordProcessingOptions.TopMargin = 40;
    options.WordProcessingOptions.BottomMargin = 40;
    viewer.View(options);
}
```

## निष्कर्ष
GroupDocs.Viewer का उपयोग करके .NET में HTML दस्तावेज़ों को प्रस्तुत करते समय मार्जिन को अनुकूलित करना डेवलपर्स को सामग्री की प्रस्तुति को सटीक रूप से तैयार करने की अनुमति देता है। इस ट्यूटोरियल का अनुसरण करके, आप आसानी से JPG, PNG, या PDF आउटपुट स्वरूपों के लिए मार्जिन समायोजित कर सकते हैं, जिससे आपके दस्तावेज़ों की दृश्य अपील और पठनीयता बढ़ सकती है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या .NET के लिए GroupDocs.Viewer विभिन्न HTML प्रारूपों के साथ संगत है?
GroupDocs.Viewer विभिन्न HTML दस्तावेज़ों के साथ अनुकूलता सुनिश्चित करते हुए, HTML प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं दस्तावेज़ सामग्री के आधार पर मार्जिन को गतिशील रूप से समायोजित कर सकता हूँ?
हां, आप दस्तावेज़ गुणों या उपयोगकर्ता प्राथमिकताओं के आधार पर प्रोग्रामेटिक रूप से मार्जिन समायोजित कर सकते हैं।
### क्या मार्जिन समायोजन पर कोई सीमाएँ हैं?
GroupDocs.Viewer मार्जिन समायोजन में लचीलापन प्रदान करता है, जिससे उचित सीमा के भीतर अनुकूलन की अनुमति मिलती है।
### क्या GroupDocs.Viewer JPG, PNG और PDF के अलावा अन्य आउटपुट स्वरूपों का समर्थन करता है?
हां, GroupDocs.Viewer TIFF, SVG और अन्य सहित विभिन्न प्रारूपों में रेंडरिंग का समर्थन करता है।
### मैं GroupDocs.Viewer से संबंधित अतिरिक्त सहायता कैसे प्राप्त कर सकता हूं या समस्याओं की रिपोर्ट कैसे कर सकता हूं?
 आप GroupDocs.Viewer फोरम पर जा सकते हैं[यहाँ](https://forum.groupdocs.com/c/viewer/9) समर्थन और चर्चा के लिए.