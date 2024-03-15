---
title: संख्याओं का प्रतिपादन
linktitle: संख्याओं का प्रतिपादन
second_title: GroupDocs.Viewer .NET API
description: Numbers फ़ाइलों को निर्बाध रूप से प्रस्तुत करने में .NET के लिए Groupdocs.Viewer की शक्ति का अन्वेषण करें। आसानी से HTML, JPG, PNG और PDF में कनवर्ट करें।
type: docs
weight: 15
url: /hi/net/spreadsheet-rendering-options/rendering-numbers/
---
## परिचय
.NET के लिए Groupdocs.Viewer का उपयोग करके नंबर फ़ाइलों को प्रस्तुत करने के इस चरण-दर-चरण ट्यूटोरियल में आपका स्वागत है। चाहे आप एक अनुभवी डेवलपर हों या नौसिखिया, यह मार्गदर्शिका आपको नंबर दस्तावेज़ों को विभिन्न प्रारूपों में परिवर्तित करने की प्रक्रिया के बारे में बताएगी। .NET के लिए Groupdocs.Viewer एक शक्तिशाली उपकरण है जो आपको दस्तावेज़ देखने की क्षमताओं को अपने .NET अनुप्रयोगों में निर्बाध रूप से एकीकृत करने की अनुमति देता है।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- C# और .NET विकास का कार्यसाधक ज्ञान।
-  .NET लाइब्रेरी के लिए Groupdocs.Viewer स्थापित। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.groupdocs.com/viewer/net/).
- आपका दस्तावेज़ निर्देशिका पथ जहां आउटपुट फ़ाइलें सहेजी जाएंगी।
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
रेंडरिंग शुरू करने से पहले, आउटपुट निर्देशिका को परिभाषित करें जहां परिवर्तित फ़ाइलें सहेजी जाएंगी। "आपकी दस्तावेज़ निर्देशिका" को वास्तविक पथ से बदलें:
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: बहु-पृष्ठ HTML पर प्रस्तुत करें
Numbers फ़ाइल को बहु-पृष्ठ HTML में कनवर्ट करने के लिए निम्नलिखित कोड का उपयोग करें:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 3: JPG में प्रस्तुत करें
निम्नलिखित कोड के साथ नंबर फ़ाइल को JPG प्रारूप में बदलें:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 4: पीएनजी को प्रस्तुत करें
निम्नलिखित कोड का उपयोग करके नंबर फ़ाइल को पीएनजी प्रारूप में बदलें:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 5: पीडीएफ में प्रस्तुत करें
अंत में, निम्नलिखित कोड का उपयोग करके नंबर फ़ाइल को पीडीएफ प्रारूप में परिवर्तित करें:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
बधाई हो! आपने .NET के लिए Groupdocs.Viewer का उपयोग करके सफलतापूर्वक Numbers फ़ाइलों को विभिन्न स्वरूपों में प्रस्तुत किया है।
## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए Groupdocs.Viewer का उपयोग करके नंबर फ़ाइलों को प्रस्तुत करने की मूल बातें कवर कीं। यह शक्तिशाली लाइब्रेरी आपके .NET अनुप्रयोगों में दस्तावेज़ों को देखने और परिवर्तित करने के लिए सहज एकीकरण प्रदान करती है।
## पूछे जाने वाले प्रश्न
### क्या मैं अन्य दस्तावेज़ प्रकारों के साथ .NET के लिए Groupdocs.Viewer का उपयोग कर सकता हूँ?
हां, Groupdocs.Viewer वर्ड, एक्सेल, पीडीएफ और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या परीक्षण प्रयोजनों के लिए अस्थायी लाइसेंस उपलब्ध है?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.groupdocs.com/temporary-license/) परीक्षण के लिए।
### मुझे .NET के लिए Groupdocs.Viewer के लिए समर्थन कहां मिल सकता है?
 दौरा करना[ग्रुपडॉक्स.व्यूअर फोरम](https://forum.groupdocs.com/c/viewer/9) सहायता और चर्चा के लिए.
### मैं .NET के लिए Groupdocs.Viewer का पूर्ण संस्करण कैसे खरीदूं?
 आप पूर्ण संस्करण खरीद सकते हैं[यहाँ](https://purchase.groupdocs.com/buy).
### क्या कोई निःशुल्क परीक्षण संस्करण उपलब्ध है?
 हां, आप नि:शुल्क परीक्षण संस्करण का पता लगा सकते हैं[यहाँ](https://releases.groupdocs.com/).