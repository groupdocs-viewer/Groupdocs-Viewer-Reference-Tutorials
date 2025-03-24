---
title: पंक्ति और स्तंभ शीर्षक प्रस्तुत करें
linktitle: पंक्ति और स्तंभ शीर्षक प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET में दस्तावेज़ देखने की क्षमता बढ़ाएँ! .NET के लिए GroupDocs.Viewer का उपयोग करके पंक्ति और स्तंभ शीर्षकों को प्रस्तुत करना सीखें। HTML, JPG, PNG और PDF आउटपुट का अन्वेषण करें।
weight: 18
url: /hi/net/spreadsheet-rendering-options/render-row-column-headings/
---
## परिचय
क्या आप .NET अनुप्रयोगों में अपने दस्तावेज़ देखने के अनुभव को बेहतर बनाना चाहते हैं? .NET के लिए GroupDocs.Viewer के साथ, आप अपनी स्प्रेडशीट फ़ाइलों से पंक्ति और स्तंभ शीर्षकों को निर्बाध रूप से प्रस्तुत कर सकते हैं। इस ट्यूटोरियल में, हम आपको HTML, JPG, PNG और PDF जैसे विभिन्न आउटपुट स्वरूपों का उपयोग करके पंक्ति और स्तंभ शीर्षकों को प्रस्तुत करने की प्रक्रिया में मार्गदर्शन करेंगे।
## आवश्यक शर्तें
इससे पहले कि हम ट्यूटोरियल में उतरें, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- .NET लाइब्रेरी के लिए GroupDocs.Viewer स्थापित किया गया।
- परीक्षण प्रयोजनों के लिए एक नमूना XLSX फ़ाइल।
- C# और .NET विकास का कार्यसाधक ज्ञान।
## नामस्थान आयात करें
अपने C# कोड में, सुनिश्चित करें कि आप GroupDocs.Viewer का उपयोग करने के लिए आवश्यक नेमस्पेस आयात करते हैं:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. आउटपुट डायरेक्टरी सेट करें
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 2. HTML को प्रस्तुत करें
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 3. JPG को प्रस्तुत करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 4. पीएनजी को प्रस्तुत करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## 5. पीडीएफ में प्रस्तुत करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "output.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHeadings = true;
    viewer.View(options, 1, 2, 3);
}
```
## निष्कर्ष
बधाई हो! आपने .NET के लिए GroupDocs.Viewer का उपयोग करके अपनी स्प्रैडशीट से पंक्ति और स्तंभ शीर्षकों को सफलतापूर्वक प्रस्तुत किया है। अपने एप्लिकेशन की आवश्यकताओं के अनुरूप विभिन्न आउटपुट स्वरूपों के साथ प्रयोग करें।
## अक्सर पूछे जाने वाले प्रश्नों
### प्रश्न: क्या मैं प्रस्तुत दस्तावेज़ों के लिए आउटपुट निर्देशिका को अनुकूलित कर सकता हूँ?
 उ: हां, आप अपनी वांछित आउटपुट निर्देशिका को उस कोड में सेट कर सकते हैं जहां`outputDirectory` परिवर्तनशील परिभाषित किया गया है।
### प्रश्न: क्या GroupDocs.Viewer अन्य स्प्रेडशीट प्रारूपों के साथ संगत है?
उत्तर: हां, GroupDocs.Viewer XLS, XLSX, CSV और अन्य सहित विभिन्न स्प्रेडशीट प्रारूपों का समर्थन करता है।
### प्रश्न: मैं रेंडरिंग प्रक्रिया के दौरान अपवादों को कैसे संभाल सकता हूं?
ए: आप अपवादों को संभालने और उपयोगकर्ता को उचित संदेश लॉग या प्रदर्शित करने के लिए ट्राई-कैच ब्लॉक लागू कर सकते हैं।
### प्रश्न: क्या मेरे एप्लिकेशन में GroupDocs.Viewer का उपयोग करने के लिए कोई लाइसेंसिंग आवश्यकताएं हैं?
उत्तर: हाँ, आपको एक वैध लाइसेंस की आवश्यकता है। आप परीक्षण उद्देश्यों के लिए एक अस्थायी लाइसेंस प्राप्त कर सकते हैं या उत्पादन के लिए पूर्ण लाइसेंस खरीद सकते हैं।
### प्रश्न: मुझे अतिरिक्त सहायता या सामुदायिक चर्चाएँ कहाँ मिल सकती हैं?
 ए: पर जाएँ[GroupDocs.Viewer फ़ोरम](https://forum.groupdocs.com/c/viewer/9) समर्थन और चर्चा के लिए.