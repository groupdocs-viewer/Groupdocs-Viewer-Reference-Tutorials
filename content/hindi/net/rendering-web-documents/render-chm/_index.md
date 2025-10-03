---
"description": "GroupDocs.Viewer का उपयोग करके .NET में CHM फ़ाइलों को रेंडर करना सीखें। CHM को HTML, JPG, PNG और PDF स्वरूपों में आसानी से रूपांतरित करें।"
"linktitle": "CHM फ़ाइलें रेंडर करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "CHM फ़ाइलें रेंडर करें"
"url": "/hi/net/rendering-web-documents/render-chm/"
"weight": 10
type: docs
---
# CHM फ़ाइलें रेंडर करें

## परिचय
इस ट्यूटोरियल में, हम .NET के लिए GroupDocs.Viewer का उपयोग करके CHM (संकलित HTML सहायता) फ़ाइलों को रेंडर करने का तरीका जानेंगे। GroupDocs.Viewer for .NET एक शक्तिशाली दस्तावेज़ रेंडरिंग API है जो डेवलपर्स को किसी बाहरी सॉफ़्टवेयर इंस्टॉलेशन की आवश्यकता के बिना अपने .NET अनुप्रयोगों के भीतर 170 से अधिक दस्तावेज़ प्रकार प्रदर्शित करने की अनुमति देता है।

## आवश्यक शर्तें

इससे पहले कि हम CHM फ़ाइलें रेंडर करना शुरू करें, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:

### .NET के लिए GroupDocs.Viewer स्थापित करना

आरंभ करने के लिए, आपको .NET के लिए GroupDocs.Viewer स्थापित करना होगा। आप लाइब्रेरी को यहां से डाउनलोड कर सकते हैं [ग्रुपडॉक्स वेबसाइट](https://releases.groupdocs.com/viewer/net/) या पैकेज मैनेजर कंसोल में निम्नलिखित कमांड चलाकर NuGet पैकेज मैनेजर के माध्यम से इसे स्थापित करें:

```bash
Install-Package GroupDocs.Viewer
```

## नामस्थान आयात करना

अपने प्रोजेक्ट में आवश्यक नामस्थानों को आयात करना सुनिश्चित करें:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

अब आइए रेंडरिंग प्रक्रिया को कई चरणों में विभाजित करें:

## चरण 1: आउटपुट निर्देशिका परिभाषित करें

वह निर्देशिका निर्धारित करें जहां आप रेंडर की गई फ़ाइलों को सहेजना चाहते हैं:

```csharp
string outputDirectory = "Your Document Directory";
```

## चरण 2: HTML में रेंडर करें

CHM फ़ाइलों को HTML में प्रस्तुत करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // सभी CHM सामग्री को एकल पृष्ठ में परिवर्तित करने के लिए true पर सेट करें

    viewer.View(options); // सभी पृष्ठ परिवर्तित करें
}
```

## चरण 3: JPG में रेंडर करें

CHM फ़ाइलों को JPG छवियों में प्रस्तुत करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // केवल पृष्ठ 1, 2, 3 को परिवर्तित करें
}
```

## चरण 4: PNG में रेंडर करें

CHM फ़ाइलों को PNG छवियों में प्रस्तुत करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // केवल पृष्ठ 1, 2, 3 को परिवर्तित करें
}
```

## चरण 5: पीडीएफ में रेंडर करें

CHM फ़ाइलों को PDF दस्तावेज़ में प्रस्तुत करने के लिए, निम्नलिखित कोड स्निपेट का उपयोग करें:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // सभी पृष्ठ परिवर्तित करें
}
```

## चरण 6: आउटपुट जांचें

एक बार रेंडरिंग प्रक्रिया पूरी हो जाने पर, रेंडर की गई फ़ाइलों के लिए निर्दिष्ट आउटपुट निर्देशिका की जाँच करें:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## निष्कर्ष

.NET के लिए GroupDocs.Viewer का उपयोग करके CHM फ़ाइलों को रेंडर करना एक सीधी प्रक्रिया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपने .NET अनुप्रयोगों के भीतर CHM दस्तावेज़ों को HTML, छवियों (JPG, PNG) और PDF जैसे विभिन्न स्वरूपों में कुशलतापूर्वक परिवर्तित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न

### प्रश्न 1: क्या GroupDocs.Viewer CHM के अलावा अन्य दस्तावेज़ प्रारूपों को प्रस्तुत कर सकता है?

A1: हां, GroupDocs.Viewer PDF, DOCX, XLSX, PPTX, और अधिक सहित 170 से अधिक दस्तावेज़ प्रारूपों को प्रस्तुत करने का समर्थन करता है।

### प्रश्न2: क्या GroupDocs.Viewer .NET कोर के साथ संगत है?

A2: हां, GroupDocs.Viewer पारंपरिक .NET फ्रेमवर्क के अलावा .NET कोर का समर्थन करता है।

### प्रश्न 3: क्या मैं विभिन्न आउटपुट प्रारूपों के लिए रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?

A3: हां, GroupDocs.Viewer रेंडरिंग प्रक्रिया को अनुकूलित करने के लिए विभिन्न विकल्प प्रदान करता है, जैसे पृष्ठ संख्या निर्दिष्ट करना, छवि गुणवत्ता सेट करना और आउटपुट पथ कॉन्फ़िगर करना।

### प्रश्न 4: क्या GroupDocs.Viewer को दस्तावेज़ प्रस्तुत करने के लिए किसी बाहरी निर्भरता की आवश्यकता होती है?

A4: नहीं, GroupDocs.Viewer एक स्टैंडअलोन लाइब्रेरी है और इसके लिए किसी बाहरी निर्भरता या तीसरे पक्ष के सॉफ़्टवेयर इंस्टॉलेशन की आवश्यकता नहीं है।

### प्रश्न 5: क्या GroupDocs.Viewer के लिए कोई निःशुल्क परीक्षण उपलब्ध है?

A5: हां, आप यहां जाकर GroupDocs.Viewer का निःशुल्क परीक्षण प्राप्त कर सकते हैं [वेबसाइट](https://releases.groupdocs.com/).