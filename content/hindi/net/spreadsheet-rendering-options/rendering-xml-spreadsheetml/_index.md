---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके विभिन्न स्वरूपों में XML SpreadSheetML फ़ाइलों के निर्बाध रेंडरिंग का अन्वेषण करें। अपने अनुप्रयोगों में आसानी से एकीकृत करें।"
"linktitle": "XML रेंडरिंग स्प्रेडशीटएमएल"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "XML रेंडरिंग स्प्रेडशीटएमएल"
"url": "/hi/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
type: docs
---
# XML रेंडरिंग स्प्रेडशीटएमएल

## परिचय
.NET के लिए GroupDocs.Viewer की दुनिया में आपका स्वागत है! इस ट्यूटोरियल में, हम आपको GroupDocs.Viewer, एक शक्तिशाली .NET लाइब्रेरी का उपयोग करके आसानी से XML SpreadSheetML फ़ाइलों को रेंडर करने में मार्गदर्शन करेंगे। चाहे आप एक अनुभवी डेवलपर हों या अभी शुरुआत कर रहे हों, यह चरण-दर-चरण मार्गदर्शिका आपको आसानी से XML SpreadSheetML रेंडरिंग को अपने अनुप्रयोगों में एकीकृत करने में मदद करेगी।
## आवश्यक शर्तें
ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ निर्धारित हैं:
- .NET समर्थन वाला एक विकास वातावरण.
- GroupDocs.Viewer for .NET लाइब्रेरी स्थापित। आप इसे डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/viewer/net/).
- C# प्रोग्रामिंग की बुनियादी समझ.
## नामस्थान आयात करें
अपने C# प्रोजेक्ट में आवश्यक नामस्थानों को आयात करके शुरू करें। यह सुनिश्चित करता है कि आपके पास GroupDocs.Viewer द्वारा प्रदान की गई कार्यक्षमताओं तक पहुँच है।
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## चरण 1: अपनी दस्तावेज़ निर्देशिका सेट करें
अपने दस्तावेज़ निर्देशिका का पथ निर्धारित करें जहां आउटपुट सहेजा जाएगा।
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: आउटपुट फ़ाइल पथ निर्दिष्ट करें
HTML, JPG, PNG, और PDF आउटपुट फ़ाइलों के लिए पूर्ण पथ सेट करें।
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## चरण 3: लोड विकल्प निर्दिष्ट करें
फ़ाइल को सटीक रूप से प्रस्तुत करने के लिए फ़ाइल प्रकार को Excel 2003 XML SpreadSheetML के रूप में स्पष्ट रूप से निर्दिष्ट करें।
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## चरण 4: बहु-पृष्ठ HTML में रेंडर करें
XML SpreadSheetML फ़ाइल को बहु-पृष्ठ HTML दस्तावेज़ में प्रस्तुत करने के लिए HTML दृश्य विकल्पों का उपयोग करें।
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 5: JPG में रेंडर करें
निर्दिष्ट विकल्पों का उपयोग करके XML SpreadSheetML फ़ाइल को JPG छवि में प्रस्तुत करें।
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 6: PNG में रेंडर करें
इसी प्रकार, निर्दिष्ट विकल्पों के साथ फ़ाइल को PNG छवि में प्रस्तुत करें।
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## चरण 7: पीडीएफ में रेंडर करें
अंत में, निर्दिष्ट विकल्पों का उपयोग करके XML SpreadSheetML फ़ाइल को PDF दस्तावेज़ में प्रस्तुत करें।
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## निष्कर्ष
बधाई हो! आपने .NET के लिए GroupDocs.Viewer का उपयोग करके XML SpreadSheetML फ़ाइलों को रेंडर करना सफलतापूर्वक सीख लिया है। इस बहुमुखी लाइब्रेरी द्वारा प्रदान की गई अधिक सुविधाओं और विकल्पों की खोज करके अपने दस्तावेज़ देखने की क्षमताओं को बढ़ाएँ।
## पूछे जाने वाले प्रश्न
### क्या GroupDocs.Viewer अन्य फ़ाइल स्वरूपों के साथ संगत है?
हां, GroupDocs.Viewer पीडीएफ, वर्ड, एक्सेल और अन्य सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या मैं प्रस्तुत दस्तावेजों के स्वरूप को अनुकूलित कर सकता हूँ?
बिल्कुल! GroupDocs.Viewer विभिन्न अनुकूलन विकल्प प्रदान करता है, जिससे आप अपनी विशिष्ट आवश्यकताओं के अनुसार आउटपुट तैयार कर सकते हैं।
### मुझे अतिरिक्त सहायता और संसाधन कहां मिल सकते हैं?
दौरा करना [GroupDocs.व्यूअर फ़ोरम](https://forum.groupdocs.com/c/viewer/9) समुदाय के समर्थन के लिए और अन्वेषण करें [प्रलेखन](https://tutorials.groupdocs.com/viewer/net/) विस्तृत जानकारी के लिए.
### क्या कोई निःशुल्क परीक्षण उपलब्ध है?
हां, आप निःशुल्क परीक्षण का लाभ उठा सकते हैं [यहाँ](https://releases.groupdocs.com/).
### मैं अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूँ?
आप अस्थायी लाइसेंस प्राप्त कर सकते हैं [यहाँ](https://purchase.groupdocs.com/temporary-license/).