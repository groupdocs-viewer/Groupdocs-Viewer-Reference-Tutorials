---
"description": "कुशल दस्तावेज़ देखने के लिए Groupdocs.Viewer for .NET को अपने .NET प्रोजेक्ट में एकीकृत करें।"
"linktitle": "रद्दीकरण टोकन के साथ रेंडर रद्द करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "रद्दीकरण टोकन के साथ रेंडर रद्द करें"
"url": "/hi/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# रद्दीकरण टोकन के साथ रेंडर रद्द करें

## परिचय
.NET के लिए Groupdocs.Viewer एक शक्तिशाली उपकरण है जिसे .NET अनुप्रयोगों के भीतर दस्तावेज़ देखने और प्रसंस्करण को सरल बनाने के लिए डिज़ाइन किया गया है। चाहे आप PDF, Microsoft Office दस्तावेज़ या अन्य सामान्य प्रारूपों के साथ काम कर रहे हों, यह लाइब्रेरी आपके .NET प्रोजेक्ट में दस्तावेज़ देखने की क्षमताओं को सहजता से एकीकृत करने के लिए मजबूत कार्यक्षमता प्रदान करती है।
## आवश्यक शर्तें
.NET के लिए Groupdocs.Viewer के एकीकरण में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ मौजूद हैं:
1. स्थापना: दिए गए लिंक से .NET लाइब्रेरी के लिए Groupdocs.Viewer डाउनलोड करें और स्थापित करें। [लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/).
   
2. लाइसेंस: यहाँ से लाइसेंस प्राप्त करें [ग्रुपडॉक्स](https://purchase.groupdocs.com/buy) लाइब्रेरी की पूरी क्षमता को अनलॉक करने के लिए। वैकल्पिक रूप से, आप एक निःशुल्क परीक्षण के साथ शुरुआत कर सकते हैं [अस्थायी लाइसेंस](https://purchase.groupdocs.com/temporary-license/).
   
3. विकास परिवेश: सुनिश्चित करें कि आपके पास एक संगत विकास परिवेश स्थापित है, जिसमें Visual Studio या आपकी पसंद का कोई अन्य .NET IDE शामिल है।

## नामस्थान आयात करें
.NET के लिए Groupdocs.Viewer का प्रभावी ढंग से उपयोग करने के लिए, आपको अपने प्रोजेक्ट में आवश्यक नेमस्पेस आयात करने की आवश्यकता है। इन चरणों का पालन करें:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

अब, बेहतर समझ और कार्यान्वयन के लिए दिए गए उदाहरण को कई चरणों में विभाजित करें:
## चरण 1: आउटपुट निर्देशिका परिभाषित करें
```csharp
string outputDirectory = "Your Document Directory";
```
यह चरण उस निर्देशिका को सेट करता है जहां प्रस्तुत दस्तावेज़ पृष्ठ संग्रहीत किए जाएंगे।
## चरण 2: पृष्ठ फ़ाइल पथ प्रारूप निर्धारित करें
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
यहां, हम अलग-अलग दस्तावेज़ पृष्ठों के फ़ाइल पथों के लिए प्रारूप परिभाषित करते हैं।
## चरण 3: CancellationTokenSource आरंभ करें
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource का उपयोग CancellationToken इंस्टैंस उत्पन्न करने के लिए किया जाता है, जिनका उपयोग एसिंक्रोनस संचालन को रद्द करने के लिए किया जा सकता है।
## चरण 4: कैंसलेशन टोकन प्राप्त करें
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
यह चरण CancellationTokenSource से टोकन प्राप्त करता है, जिसका उपयोग रेंडरिंग ऑपरेशन को रद्द करने के लिए किया जाएगा।
## चरण 5: दस्तावेज़ पृष्ठ प्रस्तुत करें
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
यहाँ, हम Task.Run() का उपयोग करके दस्तावेज़ पृष्ठों को एसिंक्रोनस रूप से रेंडर करना आरंभ करते हैं। निर्दिष्ट दस्तावेज़ फ़ाइल (SAMPLE_DOCX) के साथ Viewer इंस्टेंस बनाया जाता है, और रेंडरिंग विकल्प कॉन्फ़िगर किए जाते हैं। फिर Viewer क्लास की View विधि का उपयोग करके रेंडरिंग प्रक्रिया आरंभ की जाती है।
## चरण 6: रेंडर टाइमआउट सेट करें
```csharp
cancellationTokenSource.CancelAfter(10);
```
यह चरण रेंडरिंग ऑपरेशन के लिए 10 मिलीसेकंड का टाइमआउट सेट करता है। यदि ऑपरेशन इस टाइमआउट से अधिक हो जाता है, तो यह स्वचालित रूप से रद्द हो जाएगा।
## चरण 7: सफलता संदेश प्रदर्शित करें
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
अंत में, एक सफलता संदेश प्रदर्शित होता है जो यह दर्शाता है कि दस्तावेज़ सफलतापूर्वक प्रस्तुत हो गया है।

## निष्कर्ष
इस ट्यूटोरियल में, हमने आपके प्रोजेक्ट में .NET के लिए Groupdocs.Viewer को एकीकृत करने की मूल बातें बताई हैं। ऊपर बताए गए चरणों का पालन करके, आप अपने .NET अनुप्रयोगों में दस्तावेज़ देखने की क्षमताओं को सहजता से शामिल कर सकते हैं, जिससे उपयोगकर्ता अनुभव और उत्पादकता में वृद्धि होगी।
## अक्सर पूछे जाने वाले प्रश्न
### क्या Groupdocs.Viewer for .NET सभी दस्तावेज़ प्रारूपों के साथ संगत है?
.NET के लिए Groupdocs.Viewer पीडीएफ, माइक्रोसॉफ्ट ऑफिस दस्तावेज़, चित्र, और अधिक सहित दस्तावेज़ स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं प्रस्तुत दस्तावेज़ पृष्ठों के स्वरूप को अनुकूलित कर सकता हूँ?
हां, आप रेंडरिंग प्रक्रिया के विभिन्न पहलुओं को अनुकूलित कर सकते हैं, जिसमें पृष्ठ का आकार, गुणवत्ता, वॉटरमार्किंग आदि शामिल हैं।
### क्या Groupdocs.Viewer for .NET को इंटरनेट कनेक्टिविटी की आवश्यकता है?
नहीं, Groupdocs.Viewer for .NET आपके .NET वातावरण में स्थानीय रूप से संचालित होता है और दस्तावेज़ देखने के लिए इंटरनेट कनेक्टिविटी की आवश्यकता नहीं होती है।
### क्या Groupdocs.Viewer for .NET के लिए तकनीकी सहायता उपलब्ध है?
हां, तकनीकी सहायता उपलब्ध है [ग्रुपडॉक्स फ़ोरम](https://forum.groupdocs.com/c/viewer/9), जहां आप प्रश्न पूछ सकते हैं, समस्याओं की रिपोर्ट कर सकते हैं और समुदाय के साथ बातचीत कर सकते हैं।
### क्या मैं खरीदने से पहले .NET के लिए Groupdocs.Viewer आज़मा सकता हूं?
हां, आप दिए गए का उपयोग करके एक नि: शुल्क परीक्षण के साथ शुरू कर सकते हैं [परीक्षण संस्करण](https://releases.groupdocs.com/).