---
title: कार्यपत्रकों के नाम प्राप्त करें
linktitle: कार्यपत्रकों के नाम प्राप्त करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer के जादू का अन्वेषण करें - दस्तावेज़ देखने को अपने अनुप्रयोगों में सहजता से एकीकृत करें। अभी निशुल्क परीक्षण आज़माएं!
type: docs
weight: 11
url: /hi/net/spreadsheet-rendering-options/get-worksheets-names/
---
## परिचय
.NET के लिए GroupDocs.Viewer की आकर्षक दुनिया में आपका स्वागत है! यदि आप एक डेवलपर या उत्साही हैं जो अपने .NET अनुप्रयोगों के भीतर शक्तिशाली दस्तावेज़ देखने की क्षमताओं की खोज करने के इच्छुक हैं, तो आप एक उपहार के लिए तैयार हैं। इस व्यापक गाइड में, हम GroupDocs.Viewer का उपयोग करके वर्कशीट नामों को पुनः प्राप्त करने की जटिलताओं के बारे में जानेंगे। तो, अपनी सीट बेल्ट बांधें और चलें इस रोमांचक यात्रा पर!
## आवश्यक शर्तें
इससे पहले कि हम कोडिंग के जादू में उतरें, आइए सुनिश्चित करें कि आपने सब कुछ सेट कर लिया है:
1.  .NET के लिए GroupDocs.Viewer इंस्टॉल करें: पर जाएं[लिंक को डाउनलोड करें](https://releases.groupdocs.com/viewer/net/).NET के लिए GroupDocs.Viewer का नवीनतम संस्करण प्राप्त करने के लिए। इसे अपने विकास परिवेश में निर्बाध रूप से एकीकृत करने के लिए इंस्टॉलेशन निर्देशों का पालन करें।
2. अपना दस्तावेज़ तैयार करें: सुनिश्चित करें कि आपके पास एक लक्षित दस्तावेज़ है, मान लें कि आपकी निर्दिष्ट दस्तावेज़ निर्देशिका में "file.xlsx" नामक एक एक्सेल फ़ाइल है।
## नामस्थान आयात करें
अब जब आपके पास पूर्वापेक्षाएँ मौजूद हैं, तो आइए आवश्यक नामस्थान आयात करके काम शुरू करें। यह सुनिश्चित करता है कि आपका एप्लिकेशन .NET के लिए GroupDocs.Viewer द्वारा प्रदान की गई कार्यक्षमताओं को पहचानता है और उनका उपयोग कर सकता है।
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. दस्तावेज़ निर्देशिका की स्थापना
```csharp
string outputDirectory = "Your Document Directory";
```
"आपकी दस्तावेज़ निर्देशिका" को उस निर्देशिका के पथ से बदलें जहां आपका लक्ष्य दस्तावेज़ स्थित है।
## 2. व्यूअर को प्रारंभ करना
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
इस चरण में, हम व्यूअर वर्ग का एक उदाहरण बनाते हैं, जो आपकी एक्सेल फ़ाइल को पथ प्रदान करता है।
## 3. सूचना विकल्प देखें कॉन्फ़िगर करना
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
यहां, हम HTML दृश्य उत्पन्न करने और स्प्रेडशीट रेंडरिंग के लिए अतिरिक्त विकल्प सेट करने के लिए ViewInfoOptions को कॉन्फ़िगर करते हैं।
## 4. दृश्य जानकारी पुनः प्राप्त करना
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
कॉन्फ़िगर किए गए विकल्पों के आधार पर दृश्य जानकारी पुनर्प्राप्त करने के लिए व्यूअर इंस्टेंस का उपयोग करें।
## 5. वर्कशीट नाम प्रदर्शित करना
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
पुनर्प्राप्त पृष्ठों के माध्यम से लूप करें और प्रत्येक वर्कशीट का नाम कंसोल पर प्रिंट करें।
## निष्कर्ष
बधाई हो! आपने .NET के लिए GroupDocs.Viewer का उपयोग करके वर्कशीट नाम लाने की प्रक्रिया को सफलतापूर्वक पार कर लिया है। यह आपके अनुप्रयोगों के भीतर दस्तावेज़ देखने की कार्यक्षमता को बढ़ाने के लिए असंख्य संभावनाओं को खोलता है।
## पूछे जाने वाले प्रश्न
### क्या मैं अन्य दस्तावेज़ प्रारूपों के साथ .NET के लिए GroupDocs.Viewer का उपयोग कर सकता हूँ?
बिल्कुल! GroupDocs.Viewer पीडीएफ, माइक्रोसॉफ्ट ऑफिस और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
 हां, आप हमारे साथ .NET के लिए GroupDocs.Viewer का पता लगा सकते हैं[मुफ्त परीक्षण](https://releases.groupdocs.com/).
### मुझे अतिरिक्त सहायता कहां मिल सकती है?
 की ओर जाएं[GroupDocs.Viewer फ़ोरम](https://forum.groupdocs.com/c/viewer/9) सामुदायिक समर्थन और चर्चा के लिए।
### क्या मैं अस्थायी लाइसेंस प्राप्त कर सकता हूँ?
 निश्चित रूप से! मिलने जाना[इस लिंक](https://purchase.groupdocs.com/temporary-license/) अपना अस्थायी लाइसेंस प्राप्त करने के लिए।
### क्या विस्तृत दस्तावेज़ीकरण संसाधन उपलब्ध हैं?
 बिल्कुल! इसकी जाँच पड़ताल करो[आधिकारिक दस्तावेज](https://reference.groupdocs.com/viewer/net/) गहन जानकारी और मार्गदर्शन के लिए।