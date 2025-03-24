---
title: .NET के लिए GroupDocs.Viewer के साथ प्रिंट क्षेत्र प्रस्तुत करें
linktitle: प्रिंट क्षेत्र प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का अन्वेषण करें और विभिन्न दस्तावेज़ प्रारूपों में प्रिंट क्षेत्रों को सहजता से प्रस्तुत करें। अभी निशुल्क परीक्षण आज़माएं! #GroupDocs.Viewer
weight: 17
url: /hi/net/spreadsheet-rendering-options/render-print-areas/
---
## परिचय
आपके दस्तावेज़ों में प्रिंट क्षेत्रों को प्रस्तुत करने के लिए .NET के लिए GroupDocs.Viewer का लाभ उठाने पर इस व्यापक मार्गदर्शिका में आपका स्वागत है। यदि आप एक .NET डेवलपर हैं जो दस्तावेज़ रेंडरिंग के लिए एक मजबूत समाधान ढूंढ रहे हैं, तो आप सही जगह पर हैं। इस ट्यूटोरियल में, हम आपको GroupDocs.Viewer का उपयोग करके प्रिंट क्षेत्रों को प्रस्तुत करने की प्रक्रिया के बारे में बताएंगे, जिससे आपके अनुप्रयोगों में एक सहज अनुभव सुनिश्चित होगा।
## आवश्यक शर्तें
ट्यूटोरियल में जाने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें हैं:
- C# और .NET विकास का कार्यसाधक ज्ञान।
-  .NET के लिए GroupDocs.Viewer स्थापित। आप इसे डाउनलोड कर सकते हैं[यहाँ](https://releases.groupdocs.com/viewer/net/).
- आपकी निर्दिष्ट दस्तावेज़ निर्देशिका में एक नमूना दस्तावेज़ (उदाहरण के लिए, "SAMPLE.XLSX")।
## नामस्थान आयात करें
उचित कार्यान्वयन के लिए अपने C# कोड में आवश्यक नामस्थान आयात करना सुनिश्चित करें:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## चरण 1: दस्तावेज़ निर्देशिका सेट करें
प्रस्तुत HTML पृष्ठों के लिए आउटपुट निर्देशिका निर्दिष्ट करके प्रारंभ करें:
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: पृष्ठ फ़ाइल पथ स्वरूप को परिभाषित करें
आउटपुट निर्देशिका और पृष्ठ संख्या के लिए प्लेसहोल्डर को मिलाकर, पृष्ठ फ़ाइल पथों के लिए एक प्रारूप बनाएं:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## चरण 3: GroupDocs.Viewer को प्रारंभ करें
अपने नमूना दस्तावेज़ के पथ के साथ व्यूअर वर्ग को त्वरित करें:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## चरण 4: HTML दृश्य विकल्प कॉन्फ़िगर करें
HTML दृश्य विकल्प कॉन्फ़िगर करें, पृष्ठ फ़ाइल पथ प्रारूप निर्दिष्ट करें और प्रिंट क्षेत्रों को प्रस्तुत करने के लिए विकल्प सक्षम करें:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## चरण 5: दस्तावेज़ प्रस्तुत करें
 का आह्वान करें`View` निर्दिष्ट विकल्पों के साथ दस्तावेज़ प्रस्तुत करने की विधि:
```csharp
viewer.View(options);
```
## चरण 6: सफलता संदेश प्रदर्शित करें
एक सफलता संदेश प्रिंट करें, जो दर्शाता है कि स्रोत दस्तावेज़ सफलतापूर्वक प्रस्तुत किया गया है:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## निष्कर्ष
बधाई हो! आपने अपने दस्तावेज़ों में प्रिंट क्षेत्रों को प्रस्तुत करने के लिए .NET के लिए GroupDocs.Viewer का उपयोग करना सफलतापूर्वक सीख लिया है। यह शक्तिशाली टूल आपके .NET अनुप्रयोगों में दस्तावेज़ रेंडरिंग के लिए नई संभावनाओं को खोलता है।
## पूछे जाने वाले प्रश्न
### क्या GroupDocs.Viewer विभिन्न दस्तावेज़ प्रारूपों के साथ संगत है?
 हाँ, GroupDocs.Viewer PDF, DOCX, XLSX और अन्य सहित दस्तावेज़ स्वरूपों की एक विस्तृत श्रृंखला का समर्थन करता है। को देखें[प्रलेखन](https://tutorials.groupdocs.com/viewer/net/) पूरी सूची के लिए.
### क्या मैं खरीदारी करने से पहले GroupDocs.Viewer आज़मा सकता हूँ?
 बिल्कुल! आप नि:शुल्क परीक्षण के साथ टूल का पता लगा सकते हैं[यहाँ](https://releases.groupdocs.com/).
### मुझे किसी भी मुद्दे के लिए समर्थन कहां मिल सकता है या सहायता मिल सकती है?
 दौरा करना[GroupDocs.Viewer फ़ोरम](https://forum.groupdocs.com/c/viewer/9)समुदाय से जुड़ने और सहायता प्राप्त करने के लिए।
### क्या कोई अस्थायी लाइसेंस विकल्प उपलब्ध है?
 हां, आप अस्थायी लाइसेंस प्राप्त कर सकते हैं[यहाँ](https://purchase.groupdocs.com/temporary-license/).
### मैं .NET के लिए GroupDocs.Viewer कहाँ से खरीद सकता हूँ?
 आप अपनी खरीदारी कर सकते हैं[यहाँ](https://purchase.groupdocs.com/buy).