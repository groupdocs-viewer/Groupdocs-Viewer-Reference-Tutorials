---
"description": "इस व्यापक के साथ .NET के लिए GroupDocs.Viewer का उपयोग करके Visio आंकड़े प्रस्तुत करना सीखें। अपने .NET अनुप्रयोगों में दस्तावेज़ देखने की क्षमताओं को बढ़ाएँ।"
"linktitle": "विज़ियो आंकड़े रेंडर करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "विज़ियो आंकड़े रेंडर करें"
"url": "/hi/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
type: docs
---
# विज़ियो आंकड़े रेंडर करें

## परिचय
आज के डिजिटल युग में, दस्तावेज़ रेंडरिंग विभिन्न अनुप्रयोगों में महत्वपूर्ण भूमिका निभाता है। चाहे वह किसी वेबसाइट पर दस्तावेज़ प्रदर्शित करना हो या उन्हें विभिन्न स्वरूपों में परिवर्तित करना हो, कुशल रेंडरिंग आवश्यक है। GroupDocs.Viewer for .NET .NET अनुप्रयोगों के भीतर दस्तावेज़ों को देखने और उनमें हेरफेर करने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में, हम GroupDocs.Viewer for .NET का उपयोग करके Visio आकृतियों को रेंडर करने में गहराई से जाएँगे, प्रक्रिया को सरल चरणों में तोड़ेंगे।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. वातावरण सेटअप: सुनिश्चित करें कि आपके पास .NET विकास के लिए कार्यशील वातावरण है।
2. .NET के लिए GroupDocs.Viewer: से .NET के लिए GroupDocs.Viewer डाउनलोड और इंस्टॉल करें [लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/).
3. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा के मूल सिद्धांतों से स्वयं को परिचित कराएं।
4. नमूना Visio दस्तावेज़: रेंडरिंग के लिए एक नमूना Visio दस्तावेज़ तैयार रखें।

## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, आवश्यक नामस्थानों को आयात करके प्रारंभ करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. HTML में रेंडर करना
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
- आउटपुट निर्देशिका: वह निर्देशिका निर्धारित करें जहां प्रस्तुत HTML को सहेजा जाएगा।
- पृष्ठ फ़ाइल पथ प्रारूप: HTML पृष्ठ के लिए पथ प्रारूप निर्दिष्ट करें.
- व्यूअर आरंभीकरण: व्यूअर ऑब्जेक्ट को Visio दस्तावेज़ के पथ के साथ आरंभ करें।
- HTML दृश्य विकल्प: HTML प्रस्तुत करने के लिए विकल्प कॉन्फ़िगर करें.
- विज़ियो रेंडरिंग विकल्प: विज़ियो रेंडरिंग के लिए विशिष्ट विकल्प सेट करें, जैसे केवल आकृतियाँ और आकृति की चौड़ाई रेंडर करना।
## 2. JPG में रेंडर करना
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
- HTML में रेंडरिंग के समान, JPG प्रारूप में रेंडरिंग के लिए विकल्प कॉन्फ़िगर करें।
## 3. पीएनजी में रेंडरिंग
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
- PNG प्रारूप में रेंडरिंग के लिए कॉन्फ़िगरेशन JPG रेंडरिंग के समान पैटर्न का अनुसरण करता है।
## 4. पीडीएफ में रेंडर करना
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
- पीडीएफ में प्रस्तुत करने के लिए, पीडीएफ प्रारूप के लिए विशिष्ट विकल्प कॉन्फ़िगर करें।

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए GroupDocs.Viewer का उपयोग करके Visio आंकड़े रेंडर करने का तरीका खोजा है। चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने .NET अनुप्रयोगों में दस्तावेज़ रेंडरिंग क्षमताओं को सहजता से एकीकृत कर सकते हैं, जिससे उपयोगकर्ता अनुभव और उत्पादकता में वृद्धि होगी।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं विज़ियो आकृतियों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
हां, GroupDocs.Viewer for .NET रेंडरिंग को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है, जिसमें आकृति की चौड़ाई, केवल आंकड़े रेंडर करना और बहुत कुछ शामिल है।
### क्या GroupDocs.Viewer for .NET बड़े पैमाने पर दस्तावेज़ रेंडरिंग के लिए उपयुक्त है?
निश्चित रूप से, GroupDocs.Viewer for .NET को बड़े पैमाने पर दस्तावेज़ रेंडरिंग को कुशलतापूर्वक संभालने के लिए अनुकूलित किया गया है।
### क्या GroupDocs.Viewer Visio के अलावा अन्य दस्तावेज़ प्रारूपों का समर्थन करता है?
हां, GroupDocs.Viewer पीडीएफ, माइक्रोसॉफ्ट ऑफिस, ऑटोकैड और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं GroupDocs.Viewer को वेब अनुप्रयोगों में एकीकृत कर सकता हूं?
हां, दस्तावेज़ देखने और हेरफेर के लिए GroupDocs.Viewer को वेब अनुप्रयोगों में सहजता से एकीकृत किया जा सकता है।
### क्या खरीदने से पहले जांच के लिए कोई परीक्षण संस्करण उपलब्ध है?
हां, आप निशुल्क परीक्षण का लाभ उठा सकते हैं [वेबसाइट](https://releases.groupdocs.com/) .NET के लिए GroupDocs.Viewer की क्षमताओं का परीक्षण करने के लिए।