---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके टेक्स्ट फ़ाइलों को कई प्रारूपों में सहज रूप से परिवर्तित करने का अन्वेषण करें। अपनी दस्तावेज़ प्रबंधन क्षमताओं को सहजता से बढ़ाएँ।"
"linktitle": "टेक्स्ट फ़ाइलें (.txt) प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "टेक्स्ट फ़ाइलें (.txt) प्रस्तुत करें"
"url": "/hi/net/rendering-text-files/render-txt/"
"weight": 10
---

# टेक्स्ट फ़ाइलें (.txt) प्रस्तुत करें

## परिचय
दस्तावेज़ प्रबंधन और हेरफेर के क्षेत्र में, GroupDocs.Viewer for .NET एक शक्तिशाली उपकरण के रूप में उभरता है, जो विभिन्न दस्तावेज़ स्वरूपों को कुशलतापूर्वक प्रस्तुत करने के लिए कई प्रकार की कार्यक्षमताएँ प्रदान करता है। यह लेख टेक्स्ट फ़ाइलों (.txt) को कई स्वरूपों में प्रस्तुत करने के लिए GroupDocs.Viewer for .NET का उपयोग करने की पेचीदगियों पर प्रकाश डालता है। चाहे आप टेक्स्ट फ़ाइलों को HTML, JPG, PNG या PDF में बदलना चाहते हों, GroupDocs.Viewer आपको इन कार्यों को सहजता से पूरा करने के लिए आवश्यक टूल से लैस करता है।
## आवश्यक शर्तें
रूपांतरण प्रक्रिया में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
### 1. .NET के लिए GroupDocs.Viewer की स्थापना
सुनिश्चित करें कि आपके विकास परिवेश में GroupDocs.Viewer for .NET स्थापित है। आप आवश्यक फ़ाइलें यहाँ से डाउनलोड कर सकते हैं [वेबसाइट](https://releases.groupdocs.com/viewer/net/).
### 2. .NET फ्रेमवर्क से बुनियादी परिचितता
.NET फ्रेमवर्क की मूल बातों से खुद को परिचित कराएं, जिसमें प्रोजेक्ट को सेटअप करना और अपने कोडबेस के भीतर लाइब्रेरीज़ का उपयोग करना शामिल है।
### 3. नमूना पाठ फ़ाइलें
नमूना पाठ फ़ाइलें (.txt) तैयार करें जिन्हें आप परिवर्तित करना चाहते हैं। ये फ़ाइलें रूपांतरण प्रक्रिया के लिए इनपुट के रूप में काम करेंगी।

## नामस्थान आयात करें
रूपांतरण प्रक्रिया में गोता लगाने से पहले, अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करना सुनिश्चित करें। यह आपको .NET के लिए GroupDocs.Viewer द्वारा प्रदान की गई कार्यक्षमताओं तक सहजता से पहुँचने की अनुमति देता है।
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
आइए प्रत्येक उदाहरण को कई चरणों में विभाजित करें ताकि आपको रूपांतरण प्रक्रिया में प्रभावी रूप से मार्गदर्शन मिल सके:

## चरण 1: HTML आउटपुट पथ परिभाषित करें
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
HTML आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें.
## चरण 2: टेक्स्ट फ़ाइलों को मल्टी-पेज HTML में प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
एक उदाहरण बनाना `Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट कॉन्फ़िगर करें। `HtmlViewOptions` एम्बेडेड संसाधनों के लिए और पाठ फ़ाइल को बहु-पृष्ठ HTML में प्रस्तुत करना।
## चरण 3: एकल-पृष्ठ HTML आउटपुट पथ परिभाषित करें
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
एकल-पृष्ठ HTML आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें.
## चरण 4: टेक्स्ट फ़ाइलों को एकल-पृष्ठ HTML में प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
एक उदाहरण बनाना `Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट कॉन्फ़िगर करें। `HtmlViewOptions` एम्बेडेड संसाधनों और सेट के लिए `RenderToSinglePage` true पर सेट करें। टेक्स्ट फ़ाइल को एकल-पृष्ठ HTML में प्रस्तुत करें।
## चरण 5: JPG आउटपुट पथ परिभाषित करें
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
JPG आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें.
## चरण 6: टेक्स्ट फ़ाइलों को JPG में रेंडर करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
एक उदाहरण बनाना `Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट कॉन्फ़िगर करें। `JpgViewOptions` आउटपुट पथ के लिए और पाठ फ़ाइल को JPG प्रारूप में प्रस्तुत करें।
## चरण 7: PNG आउटपुट पथ परिभाषित करें
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
PNG आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें.
## चरण 8: टेक्स्ट फ़ाइलों को PNG में रेंडर करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
एक उदाहरण बनाना `Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट कॉन्फ़िगर करें। `PngViewOptions` आउटपुट पथ के लिए और पाठ फ़ाइल को PNG प्रारूप में प्रस्तुत करें।
## चरण 9: पीडीएफ आउटपुट पथ परिभाषित करें
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
पीडीएफ आउटपुट फ़ाइल के लिए पूर्ण पथ निर्दिष्ट करें।
## चरण 10: टेक्स्ट फ़ाइलों को पीडीएफ में रेंडर करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
एक उदाहरण बनाना `Viewer` टेक्स्ट फ़ाइल के पथ के साथ ऑब्जेक्ट कॉन्फ़िगर करें। `PdfViewOptions` आउटपुट पथ के लिए और पाठ फ़ाइल को पीडीएफ प्रारूप में प्रस्तुत करें।

## निष्कर्ष
अंत में, GroupDocs.Viewer for .NET डेवलपर्स को HTML, JPG, PNG और PDF सहित विभिन्न स्वरूपों में आसानी से टेक्स्ट फ़ाइलों को प्रस्तुत करने की शक्ति देता है। इस लेख में बताए गए चरण-दर-चरण मार्गदर्शिका का पालन करके, आप अपने .NET अनुप्रयोगों में GroupDocs.Viewer को सहजता से एकीकृत कर सकते हैं, दस्तावेज़ प्रबंधन क्षमताओं को बढ़ा सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### प्रश्न: क्या GroupDocs.Viewer for .NET .NET फ्रेमवर्क के सभी संस्करणों के साथ संगत है?
हां, .NET के लिए GroupDocs.Viewer को .NET फ्रेमवर्क संस्करणों की एक विस्तृत श्रृंखला के साथ संगत होने के लिए डिज़ाइन किया गया है, जो विकास में बहुमुखी प्रतिभा और लचीलापन सुनिश्चित करता है।
### प्रश्न: क्या मैं प्रस्तुत दस्तावेजों के आउटपुट स्वरूप को अनुकूलित कर सकता हूँ?
बिल्कुल! GroupDocs.Viewer व्यापक अनुकूलन विकल्प प्रदान करता है, जिससे डेवलपर्स को उनके ट्यूटोरियल और आवश्यकताओं के अनुसार प्रस्तुत दस्तावेजों की उपस्थिति को दर्जी करने की अनुमति मिलती है।
### प्रश्न: क्या .NET के लिए GroupDocs.Viewer का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप .NET के लिए GroupDocs.Viewer की कार्यक्षमताओं का पता लगाने के लिए उपलब्ध नि: शुल्क परीक्षण का उपयोग कर सकते हैं [वेबसाइट]( https://releases.groupdocs.com/).
### प्रश्न: मैं .NET के लिए GroupDocs.Viewer से सहायता कैसे प्राप्त कर सकता हूं?
.NET के लिए GroupDocs.Viewer के संबंध में किसी भी पूछताछ, समर्थन या सहायता के लिए, आप सुलभ समर्पित समर्थन मंच पर जा सकते हैं [यहाँ](https://forum.groupdocs.com/c/viewer/9).
### प्रश्न: क्या मैं .NET के लिए GroupDocs.Viewer का अस्थायी लाइसेंस खरीद सकता हूं?
हां, अस्थायी लाइसेंस खरीद के लिए उपलब्ध हैं, जो उपयोगकर्ताओं को विशिष्ट अवधि के लिए .NET के लिए GroupDocs.Viewer का उपयोग करने में लचीलापन और सुविधा प्रदान करते हैं।