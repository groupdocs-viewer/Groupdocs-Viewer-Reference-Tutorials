---
title: EMZ और EMF छवियाँ प्रस्तुत करें
linktitle: EMZ और EMF छवियाँ प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके EMZ और EMF छवियों को विभिन्न प्रारूपों में प्रस्तुत करना सीखें। डेवलपर्स के लिए अनुसरण करने में आसान ट्यूटोरियल।
weight: 14
url: /hi/net/image-rendering/render-emz-emf-images/
---

# EMZ और EMF छवियाँ प्रस्तुत करें

## परिचय

.NET के लिए GroupDocs.Viewer एक शक्तिशाली दस्तावेज़ रेंडरिंग एपीआई है जो डेवलपर्स को अपने .NET अनुप्रयोगों में EMZ (एन्हांस्ड विंडोज मेटाफ़ाइल) और EMF (एन्हांस्ड मेटाफ़ाइल) छवियों सहित विभिन्न दस्तावेज़ प्रकारों को प्रदर्शित करने की अनुमति देता है। इस ट्यूटोरियल में, हम यह पता लगाएंगे कि .NET के लिए GroupDocs.Viewer का उपयोग करके EMZ और EMF छवियों को HTML, JPG, PNG और PDF जैसे विभिन्न प्रारूपों में कैसे प्रस्तुत किया जाए।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित शर्तें हैं:

1.  .NET के लिए GroupDocs.Viewer: आप यहां से लाइब्रेरी डाउनलोड कर सकते हैं[यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास .NET विकास के लिए एक संगत विकास परिवेश स्थापित है।
3. नमूना EMZ/EMF छवियाँ: रेंडरिंग के लिए नमूना EMZ और EMF छवियाँ उपलब्ध हैं।

## नामस्थान आयात करें

कोड में गोता लगाने से पहले, आइए आवश्यक नामस्थान आयात करें:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

अब, आइए चरण-दर-चरण मार्गदर्शिका प्रारूप में प्रत्येक उदाहरण को कई चरणों में विभाजित करें:

## EMZ/EMF छवियाँ HTML में प्रस्तुत करना

### चरण 1: आउटपुट निर्देशिका सेट करें:
```csharp
string outputDirectory = "Your Document Directory";
```
 प्रतिस्थापित करें`"Your Document Directory"`उस पथ के साथ जहां आप प्रस्तुत HTML फ़ाइल को सहेजना चाहते हैं।

### चरण 2: पृष्ठ फ़ाइल पथ प्रारूप को परिभाषित करें:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
यह रेंडर की गई HTML फ़ाइल के लिए फ़ाइल पथ प्रारूप निर्दिष्ट करेगा।

### चरण 3: HTML पर प्रस्तुत करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 यह कोड आरंभ करता है`Viewer` नमूना EMZ छवि के साथ ऑब्जेक्ट और निर्दिष्ट विकल्पों का उपयोग करके इसे HTML प्रारूप में प्रस्तुत करता है।

## ईएमजेड/ईएमएफ छवियों को जेपीजी, पीएनजी और पीडीएफ में प्रस्तुत करना

JPG, PNG और PDF प्रारूपों में रेंडरिंग के लिए निम्नलिखित चरणों को दोहराएँ:

### चरण 1: पृष्ठ फ़ाइल पथ प्रारूप को परिभाषित करें:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
वांछित आउटपुट स्वरूप के अनुसार फ़ाइल नाम और एक्सटेंशन को समायोजित करें (`jpg`, `png` , या`pdf`).

### चरण 2: संबंधित प्रारूप में प्रस्तुत करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // आउटपुट स्वरूप (जेपीजी, पीएनजी, पीडीएफ) के अनुसार विकल्पों को समायोजित करें
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 प्रतिस्थापित करें`JpgViewOptions` साथ`PngViewOptions` या`PdfViewOptions` वांछित आउटपुट स्वरूप के आधार पर।

## निष्कर्ष

अंत में, .NET के लिए GroupDocs.Viewer .NET अनुप्रयोगों में विभिन्न प्रारूपों में EMZ और EMF छवियों को प्रस्तुत करने के लिए एक सहज समाधान प्रदान करता है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, डेवलपर्स आसानी से दस्तावेज़ रेंडरिंग क्षमताओं को अपने अनुप्रयोगों में एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: क्या GroupDocs.Viewer EMZ और EMF छवियों के अलावा अन्य दस्तावेज़ प्रारूप प्रस्तुत कर सकता है?
उत्तर: हां, GroupDocs.Viewer PDF, DOCX, PPTX, XLSX और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।

### प्रश्न: क्या .NET के लिए GroupDocs.Viewer का निःशुल्क परीक्षण उपलब्ध है?
 उत्तर: हाँ, आप नि:शुल्क परीक्षण का उपयोग कर सकते हैं[यहाँ](https://releases.groupdocs.com/).

### प्रश्न: क्या GroupDocs.Viewer डेवलपर्स के लिए सहायता प्रदान करता है?
 उत्तर: हाँ, GroupDocs इसके माध्यम से सहायता प्रदान करता है[मंच](https://forum.groupdocs.com/c/viewer/9) जहां डेवलपर्स प्रश्न पूछ सकते हैं और सहायता मांग सकते हैं।

### प्रश्न: क्या मैं .NET के लिए GroupDocs.Viewer का अस्थायी लाइसेंस खरीद सकता हूँ?
 उत्तर: हां, अस्थायी लाइसेंस खरीद के लिए उपलब्ध हैं[यहाँ](https://purchase.groupdocs.com/temporary-license/).

### प्रश्न: मुझे .NET के लिए GroupDocs.Viewer के लिए विस्तृत दस्तावेज़ कहां मिल सकते हैं?
 उत्तर: आप दस्तावेज़ का संदर्भ ले सकते हैं[यहाँ](https://tutorials.groupdocs.com/viewer/net/)एपीआई के उपयोग पर व्यापक मार्गदर्शन के लिए।