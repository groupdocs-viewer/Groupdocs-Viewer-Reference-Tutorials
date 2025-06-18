---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके विभिन्न प्रारूपों में EMZ और EMF छवियों को प्रस्तुत करना सीखें। डेवलपर्स के लिए आसान-से-अनुसरण ट्यूटोरियल।"
"linktitle": "EMZ और EMF छवियाँ प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "EMZ और EMF छवियाँ प्रस्तुत करें"
"url": "/hi/net/image-rendering/render-emz-emf-images/"
"weight": 14
---

# EMZ और EMF छवियाँ प्रस्तुत करें

## परिचय

GroupDocs.Viewer for .NET एक शक्तिशाली दस्तावेज़ रेंडरिंग API है जो डेवलपर्स को उनके .NET अनुप्रयोगों में EMZ (एन्हांस्ड विंडोज मेटाफ़ाइल) और EMF (एन्हांस्ड मेटाफ़ाइल) छवियों सहित विभिन्न दस्तावेज़ प्रकारों को प्रदर्शित करने की अनुमति देता है। इस ट्यूटोरियल में, हम .NET के लिए GroupDocs.Viewer का उपयोग करके HTML, JPG, PNG और PDF जैसे विभिन्न स्वरूपों में EMZ और EMF छवियों को रेंडर करने का तरीका जानेंगे।

![.NET के लिए GroupDocs.Viewer के साथ EMZ और EMF छवियाँ प्रस्तुत करें](/viewer/image-rendering/render-emz-and-emf-images.png)

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

1. .NET के लिए GroupDocs.Viewer: आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास वातावरण: सुनिश्चित करें कि आपके पास .NET विकास के लिए एक संगत विकास वातावरण स्थापित है।
3. नमूना EMZ/EMF छवियाँ: रेंडरिंग के लिए नमूना EMZ और EMF छवियाँ उपलब्ध रखें।

## नामस्थान आयात करें

कोड में आगे बढ़ने से पहले, आइए आवश्यक नेमस्पेस आयात करें:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

अब, आइए प्रत्येक उदाहरण को चरण-दर-चरण मार्गदर्शिका प्रारूप में कई चरणों में विभाजित करें:

## EMZ/EMF छवियों को HTML में प्रस्तुत करना

### चरण 1: आउटपुट निर्देशिका सेट करें:
```csharp
string outputDirectory = "Your Document Directory";
```
प्रतिस्थापित करें `"Your Document Directory"` उस पथ के साथ जहाँ आप रेंडर की गई HTML फ़ाइल को सहेजना चाहते हैं.

### चरण 2: पृष्ठ फ़ाइल पथ प्रारूप परिभाषित करें:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
यह रेंडर की गई HTML फ़ाइल के लिए फ़ाइल पथ प्रारूप निर्दिष्ट करेगा।

### चरण 3: HTML में प्रस्तुत करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
यह कोड आरंभ करता है `Viewer` नमूना EMZ छवि के साथ ऑब्जेक्ट को जोड़ता है और निर्दिष्ट विकल्पों का उपयोग करके इसे HTML प्रारूप में प्रस्तुत करता है।

## EMZ/EMF छवियों को JPG, PNG, और PDF में प्रस्तुत करना

JPG, PNG, और PDF प्रारूपों में रेंडर करने के लिए निम्नलिखित चरणों को दोहराएँ:

### चरण 1: पृष्ठ फ़ाइल पथ स्वरूप परिभाषित करें:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
इच्छित आउटपुट प्रारूप के अनुसार फ़ाइल नाम और एक्सटेंशन समायोजित करें (`jpg`, `png`, या `pdf`).

### चरण 2: संबंधित प्रारूप में प्रस्तुत करें:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // आउटपुट प्रारूप (Jpg, Png, Pdf) के अनुसार विकल्प समायोजित करें
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
प्रतिस्थापित करें `JpgViewOptions` साथ `PngViewOptions` या `PdfViewOptions` वांछित आउटपुट प्रारूप के आधार पर.

## निष्कर्ष

अंत में, GroupDocs.Viewer for .NET .NET अनुप्रयोगों में विभिन्न स्वरूपों में EMZ और EMF छवियों को प्रस्तुत करने के लिए एक सहज समाधान प्रदान करता है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, डेवलपर्स आसानी से अपने अनुप्रयोगों में दस्तावेज़ रेंडरिंग क्षमताओं को एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: क्या GroupDocs.Viewer EMZ और EMF छवियों के अलावा अन्य दस्तावेज़ प्रारूपों को प्रस्तुत कर सकता है?
A: हां, GroupDocs.Viewer पीडीएफ, DOCX, PPTX, XLSX, और अधिक सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।

### प्रश्न: क्या .NET के लिए GroupDocs.Viewer के लिए कोई निःशुल्क परीक्षण उपलब्ध है?
उत्तर: हां, आप निःशुल्क परीक्षण का लाभ उठा सकते हैं [यहाँ](https://releases.groupdocs.com/).

### प्रश्न: क्या GroupDocs.Viewer डेवलपर्स के लिए समर्थन प्रदान करता है?
A: हां, ग्रुपडॉक्स इसके माध्यम से समर्थन प्रदान करता है [मंच](https://forum.groupdocs.com/c/viewer/9) जहां डेवलपर्स प्रश्न पूछ सकते हैं और सहायता प्राप्त कर सकते हैं।

### प्रश्न: क्या मैं .NET के लिए GroupDocs.Viewer का अस्थायी लाइसेंस खरीद सकता हूं?
उत्तर: हां, अस्थायी लाइसेंस खरीद के लिए उपलब्ध हैं [यहाँ](https://purchase.groupdocs.com/temporary-license/).

### प्रश्न: मैं GroupDocs.Viewer for .NET के लिए विस्तृत दस्तावेज़ कहां पा सकता हूं?
उत्तर: आप दस्तावेज़ देख सकते हैं [यहाँ](https://tutorials.groupdocs.com/viewer/net/) एपीआई के उपयोग पर व्यापक मार्गदर्शन के लिए कृपया देखें.