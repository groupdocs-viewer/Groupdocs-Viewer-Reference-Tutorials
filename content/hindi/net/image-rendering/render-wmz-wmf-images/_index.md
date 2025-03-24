---
title: WMZ और WMF छवियाँ प्रस्तुत करें
linktitle: WMZ और WMF छवियाँ प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके .NET अनुप्रयोगों में WMZ और WMF छवियों को आसानी से प्रस्तुत करें। दस्तावेज़ प्रसंस्करण क्षमताओं को आसानी से बढ़ाएं।
weight: 18
url: /hi/net/image-rendering/render-wmz-wmf-images/
---

# WMZ और WMF छवियाँ प्रस्तुत करें

## परिचय

सॉफ़्टवेयर विकास के क्षेत्र में, विभिन्न दस्तावेज़ प्रारूपों का कुशल संचालन और प्रतिपादन सर्वोपरि है। .NET के लिए GroupDocs.Viewer एक शक्तिशाली उपकरण है जो दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला के प्रतिपादन की सुविधा प्रदान करता है, जो .NET अनुप्रयोगों के भीतर निर्बाध एकीकरण और बेहतर उपयोगकर्ता अनुभव सुनिश्चित करता है। इसकी क्षमताओं में WMZ और WMF छवियों का प्रतिपादन शामिल है, यह कार्य अक्सर दस्तावेज़ प्रसंस्करण परिदृश्यों में सामने आता है।

## आवश्यक शर्तें

.NET के लिए GroupDocs.Viewer का उपयोग करके WMZ और WMF छवियों की रेंडरिंग प्रक्रिया में उतरने से पहले, कई आवश्यक शर्तें पूरी करनी होंगी:

1.  .NET के लिए GroupDocs.Viewer की स्थापना: दिए गए लिंक से .NET के लिए GroupDocs.Viewer को डाउनलोड और इंस्टॉल करके शुरुआत करें।[लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/). उचित सेटअप सुनिश्चित करने के लिए इंस्टॉलेशन निर्देशों का पालन करें।

2.  लाइसेंस का अधिग्रहण: .NET के लिए GroupDocs.Viewer का उपयोग करने के लिए, आपको एक लाइसेंस प्राप्त करने की आवश्यकता होगी। आप या तो अस्थायी लाइसेंस का विकल्प चुन सकते हैं[अस्थायी लाइसेंस पृष्ठ](https://purchase.groupdocs.com/temporary-license/) या से पूर्ण लाइसेंस खरीदें[खरीद पृष्ठ](https://purchase.groupdocs.com/buy).

3. .NET वातावरण से परिचित: रेंडरिंग प्रक्रिया को प्रभावी ढंग से लागू करने के लिए .NET फ्रेमवर्क और C# प्रोग्रामिंग भाषा की बुनियादी समझ आवश्यक है।

4.  आपके प्रोजेक्ट में एकीकरण: सुनिश्चित करें कि .NET के लिए GroupDocs.Viewer आपके .NET प्रोजेक्ट में ठीक से एकीकृत है। एकीकरण पर विस्तृत निर्देशों के लिए दस्तावेज़ देखें:[प्रलेखन](https://tutorials.groupdocs.com/viewer/net/).

## नामस्थान आयात करें

रेंडरिंग प्रक्रिया के साथ आगे बढ़ने से पहले, अपने C# कोड में आवश्यक नामस्थान आयात करना महत्वपूर्ण है। ये नामस्थान WMZ और WMF छवियों को प्रस्तुत करने के लिए आवश्यक कक्षाओं और विधियों तक पहुंच प्रदान करते हैं।

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

अब जब हमने आवश्यक शर्तें पूरी कर ली हैं और आवश्यक नामस्थान आयात कर लिए हैं, तो आइए रेंडरिंग प्रक्रिया को कई चरणों में तोड़ दें।

## चरण 1: WMZ छवि को HTML में प्रस्तुत करें

WMZ छवि को HTML प्रारूप में प्रस्तुत करने के लिए, इन चरणों का पालन करें:

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.html");

// एचटीएमएल के लिए
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

    viewer.View(options);
}
```

## चरण 2: WMZ छवि को JPG में प्रस्तुत करें

WMZ छवि को JPG प्रारूप में प्रस्तुत करने के लिए, निम्नानुसार आगे बढ़ें:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.jpg");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## चरण 3: WMZ छवि को PNG में प्रस्तुत करें

WMZ छवि को PNG प्रारूप में प्रस्तुत करने के लिए, इन निर्देशों का पालन करें:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.png");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## चरण 4: WMZ छवि को पीडीएफ में प्रस्तुत करें

WMZ छवि को पीडीएफ प्रारूप में प्रस्तुत करने के लिए, निम्नानुसार आगे बढ़ें:

```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "wmz_result.pdf");

using (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## निष्कर्ष

अंत में, .NET के लिए GroupDocs.Viewer .NET अनुप्रयोगों के भीतर WMZ और WMF छवियों को सहजता से प्रस्तुत करने के लिए एक व्यापक समाधान प्रदान करता है। इस ट्यूटोरियल में उल्लिखित चरणों का पालन करके, आप दस्तावेज़ प्रसंस्करण क्षमताओं को बढ़ाते हुए, अपनी परियोजनाओं में रेंडरिंग कार्यक्षमता को सहजता से एकीकृत कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या .NET के लिए GroupDocs.Viewer सभी .NET फ्रेमवर्क के साथ संगत है?

A1: .NET के लिए GroupDocs.Viewer .NET कोर और .NET फ्रेमवर्क सहित .NET फ्रेमवर्क की एक विस्तृत श्रृंखला के साथ संगत है।

### Q2: क्या मैं WMZ और WMF छवियों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?

A2: हां, .NET के लिए GroupDocs.Viewer छवियों को प्रस्तुत करने के लिए व्यापक अनुकूलन विकल्प प्रदान करता है, जिससे आप अपनी आवश्यकताओं के अनुसार आउटपुट को अनुकूलित कर सकते हैं।

### Q3: क्या .NET के लिए GroupDocs.Viewer के लिए तकनीकी सहायता उपलब्ध है?

 A3: हां, आप समर्पित माध्यम से .NET के लिए GroupDocs.Viewer के लिए तकनीकी सहायता तक पहुंच सकते हैं[सहयता मंच](https://forum.groupdocs.com/c/viewer/9).

### Q4: क्या .NET के लिए GroupDocs.Viewer मोबाइल उपकरणों पर दस्तावेज़ देखने का समर्थन करता है?

A4: हां, .NET के लिए GroupDocs.Viewer मोबाइल फोन और टैबलेट सहित विभिन्न उपकरणों पर इष्टतम प्रदर्शन सुनिश्चित करते हुए, उत्तरदायी दस्तावेज़ देखने की क्षमता प्रदान करता है।

### Q5: क्या मैं खरीदने से पहले .NET के लिए GroupDocs.Viewer आज़मा सकता हूँ?

 A5: हां, आप उपलब्ध निःशुल्क परीक्षण तक पहुंच कर .NET के लिए GroupDocs.Viewer की सुविधाओं का पता लगा सकते हैं[यहाँ](https://releases.groupdocs.com/).