---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके CMX छवियों को विभिन्न स्वरूपों में आसानी से प्रस्तुत करना सीखें। अपने दस्तावेज़ प्रबंधन को बेहतर बनाएँ।"
"linktitle": "CMX छवियाँ प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "CMX छवियाँ प्रस्तुत करें"
"url": "/hi/net/image-rendering/render-cmx-images/"
"weight": 13
---

# CMX छवियाँ प्रस्तुत करें

## परिचय
दस्तावेज़ प्रबंधन और हेरफेर के क्षेत्र में, विभिन्न स्वरूपों से छवियों को प्रस्तुत करना एक महत्वपूर्ण कार्य है। .NET के लिए GroupDocs.Viewer CMX छवियों को HTML, JPG, PNG और PDF जैसे विभिन्न स्वरूपों में प्रस्तुत करने के लिए व्यापक कार्यक्षमता प्रदान करके इस प्रक्रिया को सरल बनाता है। यह ट्यूटोरियल आपको .NET के लिए GroupDocs.Viewer का उपयोग करके CMX छवियों को प्रस्तुत करने की चरण-दर-चरण प्रक्रिया के माध्यम से मार्गदर्शन करेगा।

![.NET के लिए GroupDocs.Viewer के साथ CMX छवियाँ प्रस्तुत करें](/viewer/image-rendering/render-cmx-images.png)

## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. .NET लाइब्रेरी के लिए GroupDocs.Viewer: .NET लाइब्रेरी के लिए GroupDocs.Viewer को डाउनलोड और इंस्टॉल करें [यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास पर्यावरण: .NET फ्रेमवर्क के साथ एक कार्यशील विकास पर्यावरण स्थापित करें।
3. CMX छवि फ़ाइल: वह CMX छवि फ़ाइल प्राप्त करें जिसे आप प्रस्तुत करना चाहते हैं।

## नामस्थान आयात करना
आगे बढ़ने से पहले, अपने .NET अनुप्रयोग में GroupDocs.Viewer कार्यक्षमताओं तक पहुँचने के लिए आवश्यक नामस्थानों को आयात करना सुनिश्चित करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## HTML में रेंडर करना
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- आउटपुट निर्देशिका निर्धारित करें: वह निर्देशिका निर्धारित करें जहां आप रेंडर की गई HTML फ़ाइलें संग्रहीत करना चाहते हैं।
- फ़ाइल पथ प्रारूप निर्दिष्ट करें: आउटपुट HTML फ़ाइलों के लिए प्रारूप परिभाषित करें।
- व्यूअर ऑब्जेक्ट का उदाहरण बनाएं: CMX छवि फ़ाइल के साथ व्यूअर क्लास का एक उदाहरण बनाएं।
- HTML रेंडरिंग विकल्प: HTML रेंडरिंग विकल्प कॉन्फ़िगर करें, जैसे संसाधन एम्बेड करना।
- CMX को HTML में प्रस्तुत करें: CMX छवि को HTML में प्रस्तुत करने के लिए व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें।
## JPG में प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- आउटपुट निर्देशिका परिभाषित करें: रेंडर की गई JPG फ़ाइलों को संग्रहीत करने के लिए निर्देशिका सेट करें।
- फ़ाइल पथ प्रारूप निर्दिष्ट करें: आउटपुट JPG फ़ाइलों के लिए प्रारूप परिभाषित करें।
- व्यूअर ऑब्जेक्ट का उदाहरण बनाएं: CMX छवि फ़ाइल के साथ व्यूअर क्लास का एक उदाहरण बनाएं।
- JPG रेंडरिंग विकल्प: JPG रेंडरिंग विकल्प कॉन्फ़िगर करें।
- CMX को JPG में प्रस्तुत करें: CMX छवि को JPG में प्रस्तुत करने के लिए व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें।
## PNG में रेंडर करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- आउटपुट निर्देशिका परिभाषित करें: प्रस्तुत PNG फ़ाइलों को संग्रहीत करने के लिए निर्देशिका सेट करें।
- फ़ाइल पथ प्रारूप निर्दिष्ट करें: आउटपुट PNG फ़ाइलों के लिए प्रारूप परिभाषित करें।
- व्यूअर ऑब्जेक्ट का उदाहरण बनाएं: CMX छवि फ़ाइल के साथ व्यूअर क्लास का एक उदाहरण बनाएं।
- PNG रेंडरिंग विकल्प: PNG रेंडरिंग विकल्प कॉन्फ़िगर करें.
- CMX को PNG में प्रस्तुत करें: CMX छवि को PNG में प्रस्तुत करने के लिए व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें।
## पीडीएफ में प्रस्तुत करना
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- आउटपुट निर्देशिका परिभाषित करें: प्रस्तुत PDF फ़ाइल को संग्रहीत करने के लिए निर्देशिका सेट करें।
- फ़ाइल पथ प्रारूप निर्दिष्ट करें: आउटपुट PDF फ़ाइल के लिए प्रारूप परिभाषित करें।
- व्यूअर ऑब्जेक्ट का उदाहरण बनाएं: CMX छवि फ़ाइल के साथ व्यूअर क्लास का एक उदाहरण बनाएं।
- पीडीएफ रेंडरिंग विकल्प: पीडीएफ रेंडरिंग विकल्प कॉन्फ़िगर करें।
- CMX को PDF में प्रस्तुत करें: CMX छवि को PDF में प्रस्तुत करने के लिए व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें।

## निष्कर्ष
अंत में, GroupDocs.Viewer for .NET विभिन्न स्वरूपों में CMX छवियों को सहजता से प्रस्तुत करने के लिए एक मजबूत समाधान प्रदान करता है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप आसानी से अपने .NET अनुप्रयोगों में CMX छवि रेंडरिंग क्षमताओं को एकीकृत कर सकते हैं, दस्तावेज़ प्रबंधन दक्षता को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं CMX छवि के विशिष्ट पृष्ठों को रेंडर कर सकता हूँ?
हां, आप रेंडरिंग विकल्पों में पृष्ठ संख्या निर्दिष्ट करके विशिष्ट पृष्ठों को रेंडर कर सकते हैं।
### क्या GroupDocs.Viewer for .NET सभी .NET फ्रेमवर्क के साथ संगत है?
हां, .NET के लिए GroupDocs.Viewer .NET कोर और .NET फ्रेमवर्क सहित कई .NET फ्रेमवर्क के साथ संगत है।
### क्या GroupDocs.Viewer एन्क्रिप्टेड CMX छवियों को प्रस्तुत करने का समर्थन करता है?
हां, GroupDocs.Viewer उचित डिक्रिप्शन कुंजियों के साथ एन्क्रिप्टेड CMX छवियों को प्रस्तुत करने का समर्थन करता है।
### क्या मैं विभिन्न आउटपुट प्रारूपों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
बिल्कुल, GroupDocs.Viewer आपकी आवश्यकताओं के आधार पर रेंडरिंग मापदंडों को अनुकूलित करने के लिए व्यापक विकल्प प्रदान करता है।
### क्या GroupDocs.Viewer समर्थन के लिए कोई सामुदायिक मंच है?
हां, आप सहायता प्राप्त कर सकते हैं और सहायता मंच पर GroupDocs.Viewer समुदाय से जुड़ सकते हैं [यहाँ](https://forum.groupdocs.com/c/viewer/9).