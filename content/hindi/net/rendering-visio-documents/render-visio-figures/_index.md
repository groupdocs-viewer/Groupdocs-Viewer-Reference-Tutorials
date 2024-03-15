---
title: विसियो आंकड़े प्रस्तुत करें
linktitle: विसियो आंकड़े प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: इस विस्तृत जानकारी के साथ .NET के लिए GroupDocs.Viewer का उपयोग करके Visio आंकड़े प्रस्तुत करना सीखें। अपने .NET अनुप्रयोगों में दस्तावेज़ देखने की क्षमताएँ बढ़ाएँ।
type: docs
weight: 10
url: /hi/net/rendering-visio-documents/render-visio-figures/
---
## परिचय
आज के डिजिटल युग में, दस्तावेज़ प्रतिपादन विभिन्न अनुप्रयोगों में महत्वपूर्ण भूमिका निभाता है। चाहे किसी वेबसाइट पर दस्तावेज़ प्रदर्शित करना हो या उन्हें विभिन्न प्रारूपों में परिवर्तित करना हो, कुशल प्रतिपादन आवश्यक है। .NET के लिए GroupDocs.Viewer .NET अनुप्रयोगों के भीतर दस्तावेज़ों को देखने और उनमें हेरफेर करने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम .NET के लिए GroupDocs.Viewer का उपयोग करके Visio आंकड़े प्रस्तुत करने में गहराई से उतरेंगे, इस प्रक्रिया को सरल चरणों में विभाजित करेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:
1. पर्यावरण सेटअप: सुनिश्चित करें कि आपके पास .NET विकास के लिए कार्य वातावरण है।
2.  .NET के लिए GroupDocs.Viewer: .NET के लिए GroupDocs.Viewer को डाउनलोड और इंस्टॉल करें।[लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/).
3. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा की बुनियादी बातों से खुद को परिचित करें।
4. नमूना Visio दस्तावेज़: रेंडरिंग के लिए एक नमूना Visio दस्तावेज़ तैयार रखें।

## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, आवश्यक नामस्थान आयात करके प्रारंभ करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. HTML को रेंडर करना
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- आउटपुट निर्देशिका: उस निर्देशिका को परिभाषित करें जहां प्रस्तुत HTML सहेजा जाएगा।
- पृष्ठ फ़ाइल पथ प्रारूप: HTML पृष्ठ के लिए पथ प्रारूप निर्दिष्ट करें।
- व्यूअर इनिशियलाइज़ेशन: Visio दस्तावेज़ के पथ के साथ व्यूअर ऑब्जेक्ट को इनिशियलाइज़ करें।
- HTML दृश्य विकल्प: HTML प्रस्तुत करने के लिए विकल्पों को कॉन्फ़िगर करें।
- Visio रेंडरिंग विकल्प: Visio रेंडरिंग के लिए विशिष्ट विकल्प सेट करें, जैसे केवल आंकड़े और चित्र की चौड़ाई प्रस्तुत करना।
## 2. JPG को प्रतिपादन
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- HTML में रेंडरिंग के समान, JPG प्रारूप में रेंडरिंग के लिए विकल्पों को कॉन्फ़िगर करें।
## 3. पीएनजी को प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- पीएनजी प्रारूप में रेंडरिंग के लिए कॉन्फ़िगरेशन JPG रेंडरिंग के समान पैटर्न का अनुसरण करता है।
## 4. पीडीएफ को प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- पीडीएफ को प्रस्तुत करने के लिए, पीडीएफ प्रारूप के लिए विशिष्ट विकल्पों को कॉन्फ़िगर करें।

## निष्कर्ष
इस ट्यूटोरियल में, हमने पता लगाया है कि .NET के लिए GroupDocs.Viewer का उपयोग करके Visio आंकड़े कैसे प्रस्तुत किए जाएं। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप उपयोगकर्ता अनुभव और उत्पादकता को बढ़ाते हुए दस्तावेज़ रेंडरिंग क्षमताओं को अपने .NET अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं Visio आंकड़ों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
हां, .NET के लिए GroupDocs.Viewer रेंडरिंग को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है, जिसमें चित्र की चौड़ाई, केवल आंकड़े प्रस्तुत करना और बहुत कुछ शामिल है।
### क्या .NET के लिए GroupDocs.Viewer बड़े पैमाने पर दस्तावेज़ प्रस्तुत करने के लिए उपयुक्त है?
बिल्कुल, .NET के लिए GroupDocs.Viewer को बड़े पैमाने पर दस्तावेज़ रेंडरिंग को कुशलतापूर्वक संभालने के लिए अनुकूलित किया गया है।
### क्या GroupDocs.Viewer Visio के अलावा अन्य दस्तावेज़ प्रारूपों का समर्थन करता है?
हां, GroupDocs.Viewer पीडीएफ, माइक्रोसॉफ्ट ऑफिस, ऑटोकैड और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं GroupDocs.Viewer को वेब अनुप्रयोगों में एकीकृत कर सकता हूँ?
हाँ, GroupDocs.Viewer को दस्तावेज़ देखने और हेरफेर के लिए वेब अनुप्रयोगों में सहजता से एकीकृत किया जा सकता है।
### क्या खरीदने से पहले परीक्षण के लिए कोई परीक्षण संस्करण उपलब्ध है?
हाँ, आप नि:शुल्क परीक्षण का लाभ उठा सकते हैं[वेबसाइट](https://releases.groupdocs.com/) .NET के लिए GroupDocs.Viewer की क्षमताओं का परीक्षण करने के लिए।