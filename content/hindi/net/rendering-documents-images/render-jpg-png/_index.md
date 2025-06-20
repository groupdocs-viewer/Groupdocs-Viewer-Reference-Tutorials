---
"description": "बेहतर उपयोगकर्ता अनुभव और उत्पादकता के लिए GroupDocs.Viewer का उपयोग करके .NET में JPG/PNG में दस्तावेज़ों को सहजता से प्रस्तुत करने का तरीका जानें।"
"linktitle": "दस्तावेज़ को JPGPNG में प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "दस्तावेज़ को JPGPNG में प्रस्तुत करें"
"url": "/hi/net/rendering-documents-images/render-jpg-png/"
"weight": 10
---

# दस्तावेज़ को JPGPNG में प्रस्तुत करें

## परिचय

.NET विकास की दुनिया में, विभिन्न अनुप्रयोगों के लिए दस्तावेज़ों को कुशलतापूर्वक संभालना आवश्यक है। चाहे आप कोई दस्तावेज़ प्रबंधन प्रणाली, ई-कॉमर्स प्लेटफ़ॉर्म या कोई सामग्री-समृद्ध अनुप्रयोग बना रहे हों, दस्तावेज़ों को सहजता से देखने की क्षमता महत्वपूर्ण है। यहीं पर GroupDocs.Viewer for .NET काम आता है, जो JPG और PNG जैसे विभिन्न स्वरूपों में दस्तावेज़ों को प्रस्तुत करने के लिए एक व्यापक समाधान प्रदान करता है।

## आवश्यक शर्तें

.NET के लिए GroupDocs.Viewer का उपयोग करने से पहले, आपको कुछ पूर्व-आवश्यकताएँ सुनिश्चित करनी होंगी:

1. .NET डेवलपमेंट एनवायरनमेंट: सुनिश्चित करें कि आपके पास अपनी मशीन पर काम करने वाला .NET डेवलपमेंट एनवायरनमेंट सेट अप है। इसमें .NET SDK इंस्टॉल होना भी शामिल है।

2. GroupDocs.Viewer लाइसेंस: GroupDocs.Viewer के लिए वैध लाइसेंस प्राप्त करें। आप या तो लाइसेंस खरीद सकते हैं या मूल्यांकन उद्देश्यों के लिए एक अस्थायी लाइसेंस का उपयोग कर सकते हैं।

3. स्थापना: दिए गए से .NET के लिए GroupDocs.Viewer डाउनलोड और इंस्टॉल करें [लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/).

4. दस्तावेज़ फ़ाइलें: दस्तावेज़ फ़ाइलें तैयार रखें जिन्हें आप प्रस्तुत करना चाहते हैं। GroupDocs.Viewer DOCX, PDF, PPT, और अधिक सहित विभिन्न स्वरूपों का समर्थन करता है।

## नामस्थान आयात करें

.NET के लिए GroupDocs.Viewer का उपयोग करके दस्तावेज़ों को प्रस्तुत करना शुरू करने के लिए, आपको अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करने होंगे। यह आपको लाइब्रेरी द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँचने की अनुमति देता है।

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

JPG या PNG प्रारूप में दस्तावेज़ प्रस्तुत करना .NET के लिए GroupDocs.Viewer के साथ एक सीधी प्रक्रिया है। इसे प्राप्त करने में आपकी सहायता के लिए नीचे एक चरण-दर-चरण मार्गदर्शिका दी गई है:

## चरण 1: आउटपुट निर्देशिका परिभाषित करें

सबसे पहले, वह निर्देशिका निर्धारित करें जहाँ आप रेंडर किए गए पृष्ठों को सहेजना चाहते हैं। यह निर्देशिका मौजूद होनी चाहिए और एप्लिकेशन द्वारा एक्सेस की जा सकने योग्य होनी चाहिए।

```csharp
string outputDirectory = "Your Document Directory";
```

## चरण 2: पृष्ठ फ़ाइल पथ प्रारूप निर्धारित करें

प्रत्येक रेंडर किए गए पृष्ठ के फ़ाइल पथ के लिए प्रारूप निर्दिष्ट करें। GroupDocs.Viewer प्रतिस्थापित करेगा `{0}` फ़ाइलों को सहेजते समय पृष्ठ संख्या के साथ।

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

## चरण 3: व्यूअर ऑब्जेक्ट को इंस्टैंशिएट करें

इसका एक उदाहरण बनाएं `Viewer` क्लास में उस दस्तावेज़ फ़ाइल का पथ प्रदान करें जिसे आप रेंडर करना चाहते हैं।

```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // रेंडरिंग के लिए कोड यहां दिया गया है
}
```

## चरण 4: रेंडरिंग विकल्प परिभाषित करें

अपनी आवश्यकताओं के अनुसार रेंडरिंग विकल्प निर्दिष्ट करें। JPG/PNG रेंडरिंग के लिए, आप उपयोग करेंगे `JpgViewOptions` या `PngViewOptions`.

```csharp
JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
```

## चरण 5: दस्तावेज़ प्रस्तुत करें

आह्वान करें `View` की विधि `Viewer` ऑब्जेक्ट और पहले बनाए गए रेंडरिंग विकल्पों को पास करें।

```csharp
viewer.View(options);
```

## चरण 6: परिणाम आउटपुट करें

एक बार रेंडरिंग प्रक्रिया पूरी हो जाने पर, आप उपयोगकर्ता को सफल रेंडरिंग के बारे में सूचित कर सकते हैं और वह निर्देशिका प्रदान कर सकते हैं जहां रेंडर किए गए पृष्ठ सहेजे गए हैं।

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## निष्कर्ष

निष्कर्ष में, GroupDocs.Viewer for .NET JPG और PNG सहित विभिन्न स्वरूपों में दस्तावेज़ों को रेंडर करने के लिए एक शक्तिशाली समाधान प्रदान करता है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपने .NET अनुप्रयोगों में दस्तावेज़ रेंडरिंग कार्यक्षमता को सहजता से एकीकृत कर सकते हैं, जिससे उपयोगकर्ता अनुभव और उत्पादकता में वृद्धि होगी।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न: क्या मैं .NET के लिए GroupDocs.Viewer का उपयोग करके DOCX के अलावा अन्य दस्तावेज़ प्रस्तुत कर सकता हूं?

A: हां, GroupDocs.Viewer पीडीएफ, पीपीटी, एक्सएलएस और अधिक सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।

### प्रश्न: क्या .NET के लिए GroupDocs.Viewer के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

उत्तर: हां, आप यहां से निःशुल्क परीक्षण डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/).

### प्रश्न: मैं मूल्यांकन प्रयोजनों के लिए अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?

उत्तर: आप अस्थायी लाइसेंस का अनुरोध कर सकते हैं [यहाँ](https://purchase.groupdocs.com/temporary-license/).

### प्रश्न: मैं .NET के लिए GroupDocs.Viewer के दस्तावेज़ कहां पा सकता हूं?

उत्तर: विस्तृत दस्तावेज उपलब्ध है [यहाँ](https://tutorials.groupdocs.com/viewer/net/).

### प्रश्न: मैं GroupDocs.Viewer for .NET से संबंधित सहायता कहां से प्राप्त कर सकता हूं या प्रश्न पूछ सकता हूं?

उत्तर: आप सहायता फ़ोरम पर जा सकते हैं [यहाँ](https://forum.groupdocs.com/c/viewer/9) सहायता के लिए.