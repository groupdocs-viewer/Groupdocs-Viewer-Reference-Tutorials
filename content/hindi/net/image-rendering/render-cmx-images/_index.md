---
title: सीएमएक्स छवियाँ प्रस्तुत करें
linktitle: सीएमएक्स छवियाँ प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके आसानी से CMX छवियों को विभिन्न प्रारूपों में प्रस्तुत करना सीखें। अपना दस्तावेज़ प्रबंधन बढ़ाएँ.
weight: 13
url: /hi/net/image-rendering/render-cmx-images/
---

# सीएमएक्स छवियाँ प्रस्तुत करें

## परिचय
दस्तावेज़ प्रबंधन और हेरफेर के क्षेत्र में, विभिन्न प्रारूपों से छवियों को प्रस्तुत करना एक महत्वपूर्ण कार्य है। .NET के लिए GroupDocs.Viewer CMX छवियों को HTML, JPG, PNG और PDF जैसे विभिन्न प्रारूपों में प्रस्तुत करने के लिए व्यापक कार्यक्षमता प्रदान करके इस प्रक्रिया को सरल बनाता है। यह ट्यूटोरियल आपको .NET के लिए GroupDocs.Viewer का उपयोग करके CMX छवियों को प्रस्तुत करने की चरण-दर-चरण प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
1.  .NET लाइब्रेरी के लिए GroupDocs.Viewer: .NET लाइब्रेरी के लिए GroupDocs.Viewer को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास परिवेश: .NET फ्रेमवर्क के साथ एक कार्यशील विकास परिवेश स्थापित करें।
3. सीएमएक्स छवि फ़ाइल: एक सीएमएक्स छवि फ़ाइल प्राप्त करें जिसे आप प्रस्तुत करना चाहते हैं।

## नामस्थान आयात करना
आगे बढ़ने से पहले, अपने .NET एप्लिकेशन में GroupDocs.Viewer कार्यक्षमताओं तक पहुंचने के लिए आवश्यक नेमस्पेस आयात करना सुनिश्चित करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## HTML को प्रतिपादन
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- आउटपुट निर्देशिका को परिभाषित करें: वह निर्देशिका सेट करें जहाँ आप प्रस्तुत HTML फ़ाइलों को संग्रहीत करना चाहते हैं।
- फ़ाइल पथ प्रारूप निर्दिष्ट करें: आउटपुट HTML फ़ाइलों के लिए प्रारूप परिभाषित करें।
- इंस्टेंटिएट व्यूअर ऑब्जेक्ट: सीएमएक्स छवि फ़ाइल के साथ व्यूअर क्लास का एक उदाहरण बनाएं।
- HTML रेंडरिंग विकल्प: HTML रेंडरिंग विकल्प कॉन्फ़िगर करें, जैसे संसाधन एम्बेड करना।
- CMX को HTML में प्रस्तुत करें: CMX छवि को HTML में प्रस्तुत करने के लिए व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें।
## JPG को प्रतिपादन
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- आउटपुट निर्देशिका को परिभाषित करें: प्रस्तुत JPG फ़ाइलों को संग्रहीत करने के लिए निर्देशिका सेट करें।
- फ़ाइल पथ प्रारूप निर्दिष्ट करें: आउटपुट JPG फ़ाइलों के लिए प्रारूप परिभाषित करें।
- इंस्टेंटिएट व्यूअर ऑब्जेक्ट: सीएमएक्स छवि फ़ाइल के साथ व्यूअर क्लास का एक उदाहरण बनाएं।
- JPG रेंडरिंग विकल्प: JPG रेंडरिंग विकल्प कॉन्फ़िगर करें।
- सीएमएक्स को जेपीजी में प्रस्तुत करें: सीएमएक्स छवि को जेपीजी में प्रस्तुत करने के लिए व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें।
## पीएनजी को प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- आउटपुट निर्देशिका को परिभाषित करें: प्रस्तुत पीएनजी फ़ाइलों को संग्रहीत करने के लिए निर्देशिका सेट करें।
- फ़ाइल पथ प्रारूप निर्दिष्ट करें: आउटपुट पीएनजी फ़ाइलों के लिए प्रारूप परिभाषित करें।
- इंस्टेंटिएट व्यूअर ऑब्जेक्ट: सीएमएक्स छवि फ़ाइल के साथ व्यूअर क्लास का एक उदाहरण बनाएं।
- पीएनजी रेंडरिंग विकल्प: पीएनजी रेंडरिंग विकल्प कॉन्फ़िगर करें।
- सीएमएक्स को पीएनजी में प्रस्तुत करें: सीएमएक्स छवि को पीएनजी में प्रस्तुत करने के लिए व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें।
## पीडीएफ को प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- आउटपुट निर्देशिका को परिभाषित करें: प्रस्तुत पीडीएफ फ़ाइल को संग्रहीत करने के लिए निर्देशिका सेट करें।
- फ़ाइल पथ प्रारूप निर्दिष्ट करें: आउटपुट पीडीएफ फ़ाइल के लिए प्रारूप परिभाषित करें।
- इंस्टेंटिएट व्यूअर ऑब्जेक्ट: सीएमएक्स छवि फ़ाइल के साथ व्यूअर क्लास का एक उदाहरण बनाएं।
- पीडीएफ रेंडरिंग विकल्प: पीडीएफ रेंडरिंग विकल्प कॉन्फ़िगर करें।
- सीएमएक्स को पीडीएफ में प्रस्तुत करें: सीएमएक्स छवि को पीडीएफ में प्रस्तुत करने के लिए व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें।

## निष्कर्ष
अंत में, .NET के लिए GroupDocs.Viewer CMX छवियों को विभिन्न प्रारूपों में निर्बाध रूप से प्रस्तुत करने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप दस्तावेज़ प्रबंधन दक्षता को बढ़ाते हुए, आसानी से अपने .NET अनुप्रयोगों में CMX छवि रेंडरिंग क्षमताओं को एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं CMX छवि के विशिष्ट पृष्ठ प्रस्तुत कर सकता हूँ?
हां, आप रेंडरिंग विकल्पों में पेज नंबर निर्दिष्ट करके विशिष्ट पेज रेंडर कर सकते हैं।
### क्या .NET के लिए GroupDocs.Viewer सभी .NET फ़्रेमवर्क के साथ संगत है?
हां, .NET के लिए GroupDocs.Viewer .NET कोर और .NET फ्रेमवर्क सहित कई .NET फ्रेमवर्क के साथ संगत है।
### क्या GroupDocs.Viewer एन्क्रिप्टेड CMX छवियों को प्रस्तुत करने का समर्थन करता है?
हाँ, GroupDocs.Viewer उचित डिक्रिप्शन कुंजियों के साथ एन्क्रिप्टेड CMX छवियों को प्रस्तुत करने का समर्थन करता है।
### क्या मैं विभिन्न आउटपुट स्वरूपों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
बिल्कुल, GroupDocs.Viewer आपकी आवश्यकताओं के आधार पर रेंडरिंग मापदंडों को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### क्या GroupDocs.Viewer समर्थन के लिए कोई सामुदायिक मंच है?
 हां, आप सहायता मांग सकते हैं और सहायता मंच पर GroupDocs.Viewer समुदाय से जुड़ सकते हैं[यहाँ](https://forum.groupdocs.com/c/viewer/9).