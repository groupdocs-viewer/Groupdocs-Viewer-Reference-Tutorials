---
title: पन्ने पलटें और घुमाएँ
linktitle: पन्ने पलटें और घुमाएँ
second_title: GroupDocs.Viewer .NET API
description: निर्बाध दस्तावेज़ रेंडरिंग, फ़्लिपिंग और रोटेशन के लिए अपने अनुप्रयोगों में .NET के लिए Groupdocs.Viewer को एकीकृत करने का तरीका जानें।
type: docs
weight: 12
url: /hi/net/rendering-options/flip-rotate-pages/
---
## परिचय
इस ट्यूटोरियल में, हम .NET के लिए Groupdocs.Viewer की कार्यक्षमताओं के बारे में विस्तार से जानेंगे, विशेष रूप से पृष्ठों को फ़्लिप करने और घुमाने पर ध्यान केंद्रित करेंगे। .NET के लिए Groupdocs.Viewer एक शक्तिशाली उपकरण है जिसे .NET अनुप्रयोगों के भीतर विभिन्न प्रारूपों में दस्तावेज़ प्रस्तुत करने के लिए डिज़ाइन किया गया है। चाहे आप दस्तावेज़ प्रबंधन प्रणाली विकसित कर रहे हों या दस्तावेज़ देखने की क्षमताओं को अपने सॉफ़्टवेयर में एकीकृत करने की आवश्यकता हो, .NET के लिए Groupdocs.Viewer एक कुशल समाधान प्रदान करता है।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ स्थापित हैं:
### .NET के लिए Groupdocs.Viewer इंस्टॉल करना
 .NET के लिए Groupdocs.Viewer का उपयोग करने के लिए, आपको NuGet पैकेज मैनेजर के माध्यम से पैकेज इंस्टॉल करना होगा। आप विस्तृत इंस्टालेशन निर्देश यहां पा सकते हैं[प्रलेखन](https://reference.groupdocs.com/viewer/net/).

## नामस्थान आयात करें
सुनिश्चित करें कि .NET के लिए Groupdocs.Viewer का प्रभावी ढंग से उपयोग करने के लिए आपके प्रोजेक्ट में आवश्यक नेमस्पेस आयात किए गए हैं।
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

आइए .NET के लिए Groupdocs.Viewer का उपयोग करके पृष्ठों को फ़्लिप करने और घुमाने की प्रक्रिया को सरल चरणों में विभाजित करें:
## चरण 1: आउटपुट निर्देशिका और फ़ाइल पथ सेट करें
उस निर्देशिका को परिभाषित करें जहां आप आउटपुट फ़ाइल को सहेजना चाहते हैं और आउटपुट फ़ाइल पथ निर्दिष्ट करें।
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## चरण 2: व्यूअर ऑब्जेक्ट को आरंभ करें
जिस दस्तावेज़ को आप देखना चाहते हैं उसका पथ पास करके व्यूअर वर्ग का एक उदाहरण बनाएं।
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## चरण 3: दृश्य विकल्प कॉन्फ़िगर करें
दृश्य विकल्प सेट करें, जैसे आउटपुट फ़ाइल स्वरूप निर्दिष्ट करना और पेज रोटेशन जैसी कोई अतिरिक्त सेटिंग्स।
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## चरण 4: दस्तावेज़ प्रस्तुत करें
व्यूअर ऑब्जेक्ट की व्यू विधि को लागू करें और व्यू विकल्प पास करें।
```csharp
viewer.View(viewOptions);
```
## चरण 5: सफलता संदेश प्रदर्शित करें
उपयोगकर्ता को सूचित करें कि दस्तावेज़ सफलतापूर्वक प्रस्तुत किया गया है और सत्यापन के लिए आउटपुट निर्देशिका निर्दिष्ट करें।
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## निष्कर्ष
अंत में, .NET के लिए Groupdocs.Viewer पृष्ठों को पलटने और घुमाने सहित दस्तावेजों को प्रस्तुत करने के लिए शक्तिशाली क्षमताएं प्रदान करता है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप इन सुविधाओं को अपने .NET अनुप्रयोगों में सहजता से एकीकृत कर सकते हैं, जिससे आपके उपयोगकर्ताओं के लिए दस्तावेज़ देखने का अनुभव बेहतर हो जाएगा।
## अक्सर पूछे जाने वाले प्रश्न
### क्या .NET के लिए Groupdocs.Viewer सभी दस्तावेज़ प्रारूपों के साथ संगत है?
हां, .NET के लिए Groupdocs.Viewer DOCX, PDF, PPTX और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं पृष्ठों को पलटने और घुमाने के अलावा देखने के विकल्पों को अनुकूलित कर सकता हूँ?
बिल्कुल, .NET के लिए Groupdocs.Viewer दस्तावेज़ देखने के लिए विभिन्न अनुकूलन विकल्प प्रदान करता है, जिससे आप अपनी आवश्यकताओं के अनुसार अनुभव को अनुकूलित कर सकते हैं।
### क्या .NET के लिए Groupdocs.Viewer का निःशुल्क परीक्षण उपलब्ध है?
 हाँ, आप पर जाकर .NET के लिए Groupdocs.Viewer के निःशुल्क परीक्षण का लाभ उठा सकते हैं[वेबसाइट](https://releases.groupdocs.com/).
### मैं .NET के लिए Groupdocs.Viewer के लिए समर्थन कैसे प्राप्त कर सकता हूँ?
 आप सहायता मांग सकते हैं और इसके माध्यम से समुदाय से जुड़ सकते हैं[Groupdocs.व्यूअर फ़ोरम](https://forum.groupdocs.com/c/viewer/9).
### मैं .NET के लिए Groupdocs.Viewer के लिए अस्थायी लाइसेंस कहां से प्राप्त कर सकता हूं?
 .NET के लिए Groupdocs.Viewer के लिए अस्थायी लाइसेंस यहां से प्राप्त किया जा सकता है[खरीद पृष्ठ](https://purchase.groupdocs.com/temporary-license/).