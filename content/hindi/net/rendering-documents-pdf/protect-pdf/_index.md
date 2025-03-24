---
title: प्रस्तुत पीडीएफ को पासवर्ड से सुरक्षित रखें
linktitle: प्रस्तुत पीडीएफ को पासवर्ड से सुरक्षित रखें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए Groupdocs.Viewer का उपयोग करके आसानी से अपने रेंडर किए गए PDF को पासवर्ड से सुरक्षित रखें। अपने दस्तावेज़ सुरक्षित और गोपनीय रखें.
weight: 12
url: /hi/net/rendering-documents-pdf/protect-pdf/
---
## परिचय
इस ट्यूटोरियल में, आप सीखेंगे कि रेंडर किए गए पीडीएफ को पासवर्ड से सुरक्षित करने के लिए .NET के लिए Groupdocs.Viewer का उपयोग कैसे करें। सुरक्षा उपायों को जोड़कर, आप गोपनीयता और अखंडता सुनिश्चित करते हुए अपने पीडीएफ दस्तावेज़ों तक पहुंच को नियंत्रित कर सकते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:
1.  .NET लाइब्रेरी के लिए Groupdocs.Viewer: लाइब्रेरी को डाउनलोड और इंस्टॉल करें[वेबसाइट](https://releases.groupdocs.com/viewer/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास .NET विकास के लिए एक कार्यशील विकास परिवेश स्थापित है।

## नामस्थान आयात करें
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## चरण 1: आउटपुट निर्देशिका और फ़ाइल पथ को परिभाषित करें
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## चरण 2: व्यूअर ऑब्जेक्ट को आरंभ करें और सुरक्षा विकल्प सेट करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## चरण 3: पीडीएफ व्यू विकल्प सेट करें
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## चरण 4: सुरक्षा विकल्पों के साथ दस्तावेज़ प्रस्तुत करें
```csharp
    viewer.View(options);
}
```
## चरण 5: प्रस्तुत दस्तावेज़ की जाँच करें
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
इन चरणों का पालन करके, आप .NET के लिए Groupdocs.Viewer का उपयोग करके रेंडर किए गए PDF को पासवर्ड से सुरक्षित कर सकते हैं। यह सुनिश्चित करता है कि आपके दस्तावेज़ सुरक्षित रहें और केवल अधिकृत उपयोगकर्ताओं के लिए ही पहुंच योग्य हों।

## निष्कर्ष
गोपनीयता और अखंडता बनाए रखने के लिए पीडीएफ दस्तावेजों को सुरक्षित रखना आवश्यक है। .NET के लिए Groupdocs.Viewer के साथ, आप संवेदनशील जानकारी तक पहुंच को नियंत्रित करते हुए, आसानी से पासवर्ड के साथ रेंडर किए गए PDF को सुरक्षित कर सकते हैं।

## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं विभिन्न स्तरों की अनुमतियों के साथ पीडीएफ़ की सुरक्षा कर सकता हूँ?
हां, आप पीडीएफ को पासवर्ड से सुरक्षित रखते हुए देखने, प्रिंट करने, कॉपी करने आदि के लिए अलग-अलग अनुमतियां निर्दिष्ट कर सकते हैं।
### क्या Groupdocs.Viewer विभिन्न फ़ाइल स्वरूपों के साथ संगत है?
बिल्कुल! Groupdocs.Viewer DOCX, XLSX, PPTX, PDF और अन्य सहित फ़ाइल स्वरूपों की एक विस्तृत श्रृंखला को प्रस्तुत करने का समर्थन करता है।
### क्या मैं Groupdocs.Viewer को अपने मौजूदा .NET एप्लिकेशन में एकीकृत कर सकता हूँ?
निश्चित रूप से! Groupdocs.Viewer .NET अनुप्रयोगों में निर्बाध एकीकरण के लिए एपीआई प्रदान करता है, जो मजबूत दस्तावेज़ देखने की क्षमता प्रदान करता है।
### क्या Groupdocs.Viewer क्लाउड स्टोरेज सेवाओं के लिए समर्थन प्रदान करता है?
हाँ, Groupdocs.Viewer ड्रॉपबॉक्स, Google ड्राइव और Amazon S3 जैसी लोकप्रिय क्लाउड स्टोरेज सेवाओं के साथ एकीकरण का समर्थन करता है, जिससे आप क्लाउड में संग्रहीत दस्तावेज़ों को प्रस्तुत कर सकते हैं।
### क्या Groupdocs.Viewer के लिए कोई परीक्षण संस्करण उपलब्ध है?
 हां, आप निःशुल्क परीक्षण संस्करण तक पहुंच कर Groupdocs.Viewer के साथ शुरुआत कर सकते हैं[वेबसाइट](https://releases.groupdocs.com/).