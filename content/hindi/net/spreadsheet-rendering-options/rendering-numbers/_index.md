---
"description": "Numbers फ़ाइलों को सहजता से रेंडर करने में Groupdocs.Viewer for .NET की शक्ति का अन्वेषण करें। HTML, JPG, PNG, और PDF में आसानी से कनवर्ट करें।"
"linktitle": "संख्याएँ प्रस्तुत करना"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "संख्याएँ प्रस्तुत करना"
"url": "/hi/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# संख्याएँ प्रस्तुत करना

## परिचय
.NET के लिए Groupdocs.Viewer का उपयोग करके Numbers फ़ाइलों को रेंडर करने के इस चरण-दर-चरण ट्यूटोरियल में आपका स्वागत है। चाहे आप एक अनुभवी डेवलपर हों या शुरुआती, यह मार्गदर्शिका आपको Numbers दस्तावेज़ों को विभिन्न स्वरूपों में परिवर्तित करने की प्रक्रिया से परिचित कराएगी। .NET के लिए Groupdocs.Viewer एक शक्तिशाली उपकरण है जो आपको अपने .NET अनुप्रयोगों में दस्तावेज़ देखने की क्षमताओं को सहजता से एकीकृत करने की अनुमति देता है।
## आवश्यक शर्तें
ट्यूटोरियल में शामिल होने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
- C# और .NET विकास का कार्यसाधक ज्ञान।
- .NET लाइब्रेरी के लिए Groupdocs.Viewer स्थापित। आप इसे डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/viewer/net/).
- आपका दस्तावेज़ निर्देशिका पथ जहाँ आउटपुट फ़ाइलें सहेजी जाएंगी.
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में, सुनिश्चित करें कि आप Groupdocs.Viewer लाइब्रेरी का उपयोग करने के लिए आवश्यक नेमस्पेस आयात करें:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## चरण 1: आउटपुट निर्देशिका सेट करें
रेंडरिंग शुरू करने से पहले, आउटपुट डायरेक्टरी को परिभाषित करें जहाँ कनवर्ट की गई फ़ाइलें सहेजी जाएँगी। "आपकी दस्तावेज़ निर्देशिका" को वास्तविक पथ से बदलें:
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: मल्टी-पेज HTML में रेंडर करें
Numbers फ़ाइल को बहु-पृष्ठ HTML में परिवर्तित करने के लिए निम्नलिखित कोड का उपयोग करें:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 3: JPG में रेंडर करें
निम्नलिखित कोड के साथ Numbers फ़ाइल को JPG प्रारूप में बदलें:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 4: PNG में रेंडर करें
निम्नलिखित कोड का उपयोग करके Numbers फ़ाइल को PNG प्रारूप में बदलें:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 5: पीडीएफ में रेंडर करें
अंत में, निम्नलिखित कोड का उपयोग करके Numbers फ़ाइल को PDF प्रारूप में परिवर्तित करें:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
बधाई हो! आपने .NET के लिए Groupdocs.Viewer का उपयोग करके Numbers फ़ाइलों को विभिन्न प्रारूपों में सफलतापूर्वक प्रस्तुत किया है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Groupdocs.Viewer का उपयोग करके Numbers फ़ाइलों को रेंडर करने की मूल बातें कवर की हैं। यह शक्तिशाली लाइब्रेरी आपके .NET अनुप्रयोगों में दस्तावेज़ों को देखने और परिवर्तित करने के लिए सहज एकीकरण प्रदान करती है।
## पूछे जाने वाले प्रश्न
### क्या मैं अन्य दस्तावेज़ प्रकारों के साथ .NET के लिए Groupdocs.Viewer का उपयोग कर सकता हूं?
हां, Groupdocs.Viewer Word, Excel, PDF, आदि सहित दस्तावेज़ स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या परीक्षण प्रयोजनों के लिए कोई अस्थायी लाइसेंस उपलब्ध है?
हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं [यहाँ](https://purchase.groupdocs.com/temporary-license/) परीक्षण के लिए.
### मैं .NET के लिए Groupdocs.Viewer हेतु समर्थन कहां पा सकता हूं?
दौरा करना [ग्रुपडॉक्स.व्यूअर फोरम](https://forum.groupdocs.com/c/viewer/9) सहायता और चर्चा के लिए।
### मैं .NET के लिए Groupdocs.Viewer का पूर्ण संस्करण कैसे खरीदूं?
आप पूर्ण संस्करण खरीद सकते हैं [यहाँ](https://purchase.groupdocs.com/buy).
### क्या कोई निःशुल्क परीक्षण संस्करण उपलब्ध है?
हां, आप निःशुल्क परीक्षण संस्करण का उपयोग कर सकते हैं [यहाँ](https://releases.groupdocs.com/).