---
title: सीएचएम फ़ाइलें प्रस्तुत करें
linktitle: सीएचएम फ़ाइलें प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: GroupDocs.Viewer का उपयोग करके .NET में CHM फ़ाइलों को प्रस्तुत करना सीखें। सीएचएम को आसानी से HTML, JPG, PNG और PDF फॉर्मेट में बदलें।
weight: 10
url: /hi/net/rendering-web-documents/render-chm/
---
## परिचय
इस ट्यूटोरियल में, हम जानेंगे कि .NET के लिए GroupDocs.Viewer का उपयोग करके CHM (संकलित HTML सहायता) फ़ाइलों को कैसे प्रस्तुत किया जाए। .NET के लिए GroupDocs.Viewer एक शक्तिशाली दस्तावेज़ रेंडरिंग एपीआई है जो डेवलपर्स को किसी भी बाहरी सॉफ़्टवेयर इंस्टॉलेशन की आवश्यकता के बिना अपने .NET अनुप्रयोगों के भीतर 170 से अधिक दस्तावेज़ प्रकार प्रदर्शित करने की अनुमति देता है।

## आवश्यक शर्तें

इससे पहले कि हम सीएचएम फ़ाइलों को प्रस्तुत करना शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

### .NET के लिए GroupDocs.Viewer इंस्टॉल करना

 आरंभ करने के लिए, आपको .NET के लिए GroupDocs.Viewer इंस्टॉल करना होगा। आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं[ग्रुपडॉक्स वेबसाइट](https://releases.groupdocs.com/viewer/net/) या पैकेज मैनेजर कंसोल में निम्नलिखित कमांड चलाकर इसे NuGet पैकेज मैनेजर के माध्यम से इंस्टॉल करें:

```bash
Install-Package GroupDocs.Viewer
```

## नामस्थान आयात करना

अपने प्रोजेक्ट में आवश्यक नामस्थान आयात करना सुनिश्चित करें:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

आइए अब रेंडरिंग प्रक्रिया को कई चरणों में विभाजित करें:

## चरण 1: आउटपुट डायरेक्टरी को परिभाषित करें

उस निर्देशिका को परिभाषित करें जहां आप रेंडर की गई फ़ाइलों को सहेजना चाहते हैं:

```csharp
string outputDirectory = "Your Document Directory";
```

## चरण 2: HTML पर प्रस्तुत करें

CHM फ़ाइलों को HTML में प्रस्तुत करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // सभी सीएचएम सामग्री को एक पृष्ठ में परिवर्तित करने के लिए सत्य पर सेट करें

    viewer.View(options); //सभी पेज कनवर्ट करें
}
```

## चरण 3: JPG में प्रस्तुत करें

सीएचएम फ़ाइलों को जेपीजी छवियों में प्रस्तुत करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // केवल पेज 1, 2, 3 को कनवर्ट करें
}
```

## चरण 4: पीएनजी को प्रस्तुत करें

सीएचएम फ़ाइलों को पीएनजी छवियों में प्रस्तुत करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // केवल पेज 1, 2, 3 को कनवर्ट करें
}
```

## चरण 5: पीडीएफ में प्रस्तुत करें

सीएचएम फ़ाइलों को पीडीएफ दस्तावेज़ में प्रस्तुत करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //सभी पेज कनवर्ट करें
}
```

## चरण 6: आउटपुट जांचें

एक बार रेंडरिंग प्रक्रिया पूरी हो जाने पर, रेंडर की गई फ़ाइलों के लिए निर्दिष्ट आउटपुट निर्देशिका की जाँच करें:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## निष्कर्ष

.NET के लिए GroupDocs.Viewer का उपयोग करके CHM फ़ाइलों को प्रस्तुत करना एक सीधी प्रक्रिया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपने .NET अनुप्रयोगों के भीतर सीएचएम दस्तावेजों को एचटीएमएल, छवियों (जेपीजी, पीएनजी) और पीडीएफ जैसे विभिन्न प्रारूपों में कुशलतापूर्वक परिवर्तित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### Q1: क्या GroupDocs.Viewer CHM के अलावा अन्य दस्तावेज़ प्रारूप प्रस्तुत कर सकता है?

A1: हां, GroupDocs.Viewer PDF, DOCX, XLSX, PPTX और अन्य सहित 170 से अधिक दस्तावेज़ प्रारूपों को प्रस्तुत करने का समर्थन करता है।

### Q2: क्या GroupDocs.Viewer .NET कोर के साथ संगत है?

A2: हां, GroupDocs.Viewer पारंपरिक .NET फ्रेमवर्क के अलावा .NET कोर का भी समर्थन करता है।

### Q3: क्या मैं विभिन्न आउटपुट स्वरूपों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?

A3: हां, GroupDocs.Viewer रेंडरिंग प्रक्रिया को अनुकूलित करने के लिए विभिन्न विकल्प प्रदान करता है, जैसे पेज नंबर निर्दिष्ट करना, छवि गुणवत्ता सेट करना और आउटपुट पथ कॉन्फ़िगर करना।

### Q4: क्या GroupDocs.Viewer को दस्तावेज़ प्रस्तुत करने के लिए किसी बाहरी निर्भरता की आवश्यकता है?

A4: नहीं, GroupDocs.Viewer एक स्टैंडअलोन लाइब्रेरी है और इसके लिए किसी बाहरी निर्भरता या तृतीय-पक्ष सॉफ़्टवेयर इंस्टॉलेशन की आवश्यकता नहीं है।

### Q5: क्या GroupDocs.Viewer के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

 A5: हाँ, आप पर जाकर GroupDocs.Viewer का निःशुल्क परीक्षण प्राप्त कर सकते हैं[वेबसाइट](https://releases.groupdocs.com/).