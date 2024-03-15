---
title: छवि प्रतिपादन के लिए पाठ निर्देशांक प्राप्त करें
linktitle: छवि प्रतिपादन के लिए पाठ निर्देशांक प्राप्त करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके छवि रेंडरिंग के लिए टेक्स्ट निर्देशांक निकालना सीखें। अपनी दस्तावेज़ प्रसंस्करण क्षमताओं को सहजता से बढ़ाएँ।
type: docs
weight: 12
url: /hi/net/rendering-documents-images/get-text-coordinates-image/
---
## परिचय
.NET के लिए GroupDocs.Viewer एक शक्तिशाली दस्तावेज़ रेंडरिंग एपीआई है जो डेवलपर्स को पीडीएफ, माइक्रोसॉफ्ट ऑफिस और कई अन्य स्वरूपों में दस्तावेज़ों को निर्बाध रूप से प्रस्तुत करने की अनुमति देता है। इसकी प्रमुख कार्यक्षमताओं में से एक सटीक छवि प्रतिपादन के लिए पाठ निर्देशांक निकालने की क्षमता है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यकताएँ हैं:
1.  .NET के लिए GroupDocs.Viewer: से नवीनतम संस्करण डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास परिवेश: .NET फ्रेमवर्क समर्थन के साथ अपना पसंदीदा IDE सेट करें।
3. दस्तावेज़ फ़ाइलें: परीक्षण उद्देश्यों के लिए नमूना दस्तावेज़ फ़ाइलें तैयार रखें।

## नामस्थान आयात करना
कोडिंग प्रक्रिया में उतरने से पहले, आइए .NET के लिए GroupDocs.Viewer की कार्यक्षमताओं तक पहुंचने के लिए आवश्यक नेमस्पेस आयात करें।
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## चरण 1: GroupDocs.Viewer को प्रारंभ करें
जिस दस्तावेज़ फ़ाइल को आप संसाधित करना चाहते हैं, उसके साथ GroupDocs.Viewer ऑब्जेक्ट को प्रारंभ करके प्रारंभ करें।
```csharp
using (Viewer viewer = new Viewer("path/to/your/document"))
{
    // आपका कोड यहां जाता है
}
```
## चरण 2: जानकारी देखें
इसके बाद, छवि रेंडरिंग के लिए पाठ निर्देशांक सहित दस्तावेज़ की दृश्य जानकारी पुनः प्राप्त करें।
```csharp
ViewInfoOptions options = ViewInfoOptions.ForPngView(true);
ViewInfo viewInfo = viewer.GetViewInfo(options);
```
## चरण 3: पृष्ठों के माध्यम से पुनरावृति करें
पाठ पंक्तियों, शब्दों और वर्णों तक पहुँचने के लिए दस्तावेज़ के प्रत्येक पृष्ठ को दोहराएँ।
```csharp
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($"Page: {page.Number}");
    Console.WriteLine("Text lines/words/characters:");
    foreach (Line line in page.Lines)
    {
        Console.WriteLine(line);
        foreach (Word word in line.Words)
        {
            Console.WriteLine("\t" + word);
            foreach (Character character in word.Characters)
                Console.WriteLine("\t\t" + character);
        }
    }
}
```
## चरण 4: पाठ निर्देशांक निकालें
सटीक छवि प्रतिपादन की सुविधा के लिए पाठ निर्देशांक निकालें।
```csharp
// पाठ निर्देशांक निष्कर्षण के लिए आपका कोड यहां जाता है
```

## निष्कर्ष
अंत में, .NET के लिए GroupDocs.Viewer का उपयोग करके छवि प्रतिपादन के लिए पाठ निर्देशांक के निष्कर्षण में महारत हासिल करने से आपकी दस्तावेज़ प्रसंस्करण क्षमताओं में काफी वृद्धि हो सकती है। इस ट्यूटोरियल का अनुसरण करके, आपने इस कार्य को कुशलतापूर्वक पूरा करने के लिए आवश्यक कदम सीख लिए हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या .NET के लिए GroupDocs.Viewer सभी दस्तावेज़ प्रारूपों के साथ संगत है?
.NET के लिए GroupDocs.Viewer पीडीएफ, माइक्रोसॉफ्ट ऑफिस और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं .NET के लिए GroupDocs.Viewer को अपने मौजूदा .NET एप्लिकेशन में एकीकृत कर सकता हूँ?
हाँ, .NET के लिए GroupDocs.Viewer को आपके .NET अनुप्रयोगों में निर्बाध रूप से एकीकृत करने के लिए डिज़ाइन किया गया है।
### क्या .NET के लिए GroupDocs.Viewer पाठ निर्देशांक निकालने के लिए समर्थन प्रदान करता है?
हां, जैसा कि इस ट्यूटोरियल में दिखाया गया है, .NET के लिए GroupDocs.Viewer टेक्स्ट निर्देशांक निकालने के लिए कार्यक्षमता प्रदान करता है।
### मुझे .NET के लिए GroupDocs.Viewer के लिए अतिरिक्त दस्तावेज़ और समर्थन कहां मिल सकता है?
 आप दस्तावेज़ तक पहुंच सकते हैं और GroupDocs.Viewer फ़ोरम से सहायता प्राप्त कर सकते हैं[यहाँ](https://forum.groupdocs.com/c/viewer/9).
### क्या .NET के लिए GroupDocs.Viewer का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप GroupDocs वेबसाइट से निःशुल्क परीक्षण का लाभ उठा सकते हैं[यहाँ](https://releases.groupdocs.com/).