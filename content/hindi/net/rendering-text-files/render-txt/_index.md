---
title: टेक्स्ट फ़ाइलें प्रस्तुत करें (.txt)
linktitle: टेक्स्ट फ़ाइलें प्रस्तुत करें (.txt)
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके टेक्स्ट फ़ाइलों के कई प्रारूपों में निर्बाध रूपांतरण का अन्वेषण करें। अपनी दस्तावेज़ प्रबंधन क्षमताओं को सहजता से बढ़ाएँ।
type: docs
weight: 10
url: /hi/net/rendering-text-files/render-txt/
---
## परिचय
दस्तावेज़ प्रबंधन और हेरफेर के क्षेत्र में, .NET के लिए GroupDocs.Viewer एक शक्तिशाली उपकरण के रूप में उभरता है, जो विभिन्न दस्तावेज़ प्रारूपों को कुशलतापूर्वक प्रस्तुत करने के लिए ढेर सारी कार्यक्षमताएँ प्रदान करता है। यह आलेख टेक्स्ट फ़ाइलों (.txt) को कई प्रारूपों में प्रस्तुत करने के लिए .NET के लिए GroupDocs.Viewer का उपयोग करने की जटिलताओं पर प्रकाश डालता है। चाहे आपका लक्ष्य टेक्स्ट फ़ाइलों को HTML, JPG, PNG, या PDF में परिवर्तित करना हो, GroupDocs.Viewer आपको इन कार्यों को निर्बाध रूप से पूरा करने के लिए आवश्यक टूल से लैस करता है।
## आवश्यक शर्तें
रूपांतरण प्रक्रिया में गहराई से उतरने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
### 1. .NET के लिए GroupDocs.Viewer की स्थापना
 सुनिश्चित करें कि आपके विकास परिवेश में .NET के लिए GroupDocs.Viewer स्थापित है। आप आवश्यक फ़ाइलें यहां से डाउनलोड कर सकते हैं[वेबसाइट](https://releases.groupdocs.com/viewer/net/).
### 2. .NET फ्रेमवर्क से बुनियादी परिचय
.NET फ्रेमवर्क की बुनियादी बातों से खुद को परिचित करें, जिसमें एक प्रोजेक्ट कैसे स्थापित करें और अपने कोडबेस के भीतर लाइब्रेरी का उपयोग कैसे करें।
### 3. नमूना पाठ फ़ाइलें
नमूना टेक्स्ट फ़ाइलें (.txt) तैयार करें जिन्हें आप कनवर्ट करना चाहते हैं। ये फ़ाइलें रूपांतरण प्रक्रिया के लिए इनपुट के रूप में काम करेंगी।

## नामस्थान आयात करें
रूपांतरण प्रक्रिया में उतरने से पहले, अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करना सुनिश्चित करें। यह आपको .NET के लिए GroupDocs.Viewer द्वारा प्रदान की गई कार्यक्षमताओं तक निर्बाध रूप से पहुंचने की अनुमति देता है।
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
आइए रूपांतरण प्रक्रिया में प्रभावी ढंग से आपका मार्गदर्शन करने के लिए प्रत्येक उदाहरण को कई चरणों में विभाजित करें:

## चरण 1: HTML आउटपुट पथ को परिभाषित करें
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
HTML आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें।
## चरण 2: टेक्स्ट फ़ाइलों को मल्टी-पेज HTML में प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 त्वरित करें ए`Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट। कॉन्फ़िगर`HtmlViewOptions` एम्बेडेड संसाधनों के लिए और टेक्स्ट फ़ाइल को बहु-पृष्ठ HTML में प्रस्तुत करना।
## चरण 3: सिंगल-पेज HTML आउटपुट पथ को परिभाषित करें
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
एकल-पृष्ठ HTML आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें।
## चरण 4: टेक्स्ट फ़ाइलों को एकल-पृष्ठ HTML में प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 त्वरित करें ए`Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट। कॉन्फ़िगर`HtmlViewOptions` एम्बेडेड संसाधनों और सेट के लिए`RenderToSinglePage` सच करने के लिए. टेक्स्ट फ़ाइल को एकल-पृष्ठ HTML में प्रस्तुत करें।
## चरण 5: JPG आउटपुट पथ को परिभाषित करें
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
JPG आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें।
## चरण 6: टेक्स्ट फ़ाइलों को JPG में प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 त्वरित करें ए`Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट। कॉन्फ़िगर`JpgViewOptions` आउटपुट पथ के लिए और टेक्स्ट फ़ाइल को JPG प्रारूप में प्रस्तुत करें।
## चरण 7: पीएनजी आउटपुट पथ को परिभाषित करें
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
पीएनजी आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें।
## चरण 8: टेक्स्ट फ़ाइलों को पीएनजी में प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 त्वरित करें ए`Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट। कॉन्फ़िगर`PngViewOptions` आउटपुट पथ के लिए और टेक्स्ट फ़ाइल को पीएनजी प्रारूप में प्रस्तुत करें।
## चरण 9: पीडीएफ आउटपुट पथ को परिभाषित करें
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
पीडीएफ आउटपुट फ़ाइल के लिए पूरा पथ निर्दिष्ट करें।
## चरण 10: टेक्स्ट फ़ाइलों को पीडीएफ में प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 त्वरित करें ए`Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट। कॉन्फ़िगर`PdfViewOptions` आउटपुट पथ के लिए और टेक्स्ट फ़ाइल को पीडीएफ प्रारूप में प्रस्तुत करें।

## निष्कर्ष
अंत में, .NET के लिए GroupDocs.Viewer डेवलपर्स को टेक्स्ट फ़ाइलों को HTML, JPG, PNG और PDF सहित विभिन्न स्वरूपों में आसानी से प्रस्तुत करने का अधिकार देता है। इस आलेख में उल्लिखित चरण-दर-चरण मार्गदर्शिका का पालन करके, आप दस्तावेज़ प्रबंधन क्षमताओं को बढ़ाते हुए GroupDocs.Viewer को अपने .NET अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या .NET के लिए GroupDocs.Viewer .NET फ्रेमवर्क के सभी संस्करणों के साथ संगत है?
हां, .NET के लिए GroupDocs.Viewer को .NET फ्रेमवर्क संस्करणों की एक विस्तृत श्रृंखला के साथ संगत होने के लिए डिज़ाइन किया गया है, जो विकास में बहुमुखी प्रतिभा और लचीलेपन को सुनिश्चित करता है।
### प्रश्न: क्या मैं प्रस्तुत दस्तावेज़ों के आउटपुट स्वरूप को अनुकूलित कर सकता हूँ?
बिल्कुल! GroupDocs.Viewer व्यापक अनुकूलन विकल्प प्रदान करता है, जिससे डेवलपर्स को उनकी प्राथमिकताओं और आवश्यकताओं के अनुसार प्रस्तुत दस्तावेज़ों की उपस्थिति को अनुकूलित करने की अनुमति मिलती है।
### प्रश्न: क्या .NET के लिए GroupDocs.Viewer का कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप उपलब्ध निःशुल्क परीक्षण तक पहुंच कर .NET के लिए GroupDocs.Viewer की कार्यक्षमताओं का पता लगा सकते हैं।[वेबसाइट]( https://releases.groupdocs.com/).
### प्रश्न: मैं .NET के लिए GroupDocs.Viewer से सहायता कैसे प्राप्त कर सकता हूं या सहायता कैसे प्राप्त कर सकता हूं?
 .NET के लिए GroupDocs.Viewer के संबंध में किसी भी पूछताछ, सहायता या सहायता के लिए, आप उपलब्ध समर्पित सहायता फ़ोरम पर जा सकते हैं[यहाँ](https://forum.groupdocs.com/c/viewer/9).
### प्रश्न: क्या मैं .NET के लिए GroupDocs.Viewer का अस्थायी लाइसेंस खरीद सकता हूँ?
हां, अस्थायी लाइसेंस खरीद के लिए उपलब्ध हैं, जो उपयोगकर्ताओं को विशिष्ट अवधि के लिए .NET के लिए GroupDocs.Viewer का उपयोग करने में लचीलापन और सुविधा प्रदान करते हैं।