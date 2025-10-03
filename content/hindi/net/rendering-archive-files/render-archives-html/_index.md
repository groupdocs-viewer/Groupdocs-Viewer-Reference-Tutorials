---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके HTML पृष्ठों पर अभिलेखागार प्रस्तुत करना सीखें। अपने .NET अनुप्रयोगों में दस्तावेज़ देखने की क्षमताओं को आसानी से एकीकृत करें।"
"linktitle": "अभिलेखों को एकल या एकाधिक HTML पृष्ठों में प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "अभिलेखों को एकल या एकाधिक HTML पृष्ठों में प्रस्तुत करें"
"url": "/hi/net/rendering-archive-files/render-archives-html/"
"weight": 12
type: docs
---
# अभिलेखों को एकल या एकाधिक HTML पृष्ठों में प्रस्तुत करें

## परिचय
GroupDocs.Viewer for .NET एक शक्तिशाली दस्तावेज़ रेंडरिंग लाइब्रेरी है जो डेवलपर्स को अपने .NET अनुप्रयोगों में दस्तावेज़ देखने की क्षमताओं को आसानी से एकीकृत करने की अनुमति देता है। चाहे आपको एकल या एकाधिक HTML पृष्ठों पर अभिलेखागार प्रस्तुत करने की आवश्यकता हो, यह ट्यूटोरियल आपको चरण दर चरण प्रक्रिया के माध्यम से मार्गदर्शन करेगा।
## आवश्यक शर्तें
इस ट्यूटोरियल में आगे बढ़ने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. .NET के लिए GroupDocs.Viewer: सुनिश्चित करें कि आपके प्रोजेक्ट में लाइब्रेरी स्थापित है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास वातावरण: .NET विकास के लिए एक कार्यशील विकास वातावरण स्थापित करें।
3. दस्तावेज़ निर्देशिका: एक निर्देशिका तैयार करें जहाँ आपके दस्तावेज़ संग्रहीत हों।
4. C# की बुनियादी समझ: C# प्रोग्रामिंग भाषा की बुनियादी बातों से स्वयं को परिचित कराएं।

## नामस्थान आयात करें
अपने C# कोड में, आवश्यक नामस्थानों को आयात करना सुनिश्चित करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

.NET के लिए GroupDocs.Viewer का उपयोग करके एकल या एकाधिक HTML पृष्ठों पर संग्रह प्रस्तुत करने के लिए इन चरणों का पालन करें:
## चरण 1: आउटपुट निर्देशिका सेट करें
वह निर्देशिका निर्धारित करें जहां आप रेंडर किए गए HTML पृष्ठों को सहेजना चाहते हैं:
```csharp
string outputDirectory = "Your Document Directory";
```
## चरण 2: फ़ाइल पथ प्रारूप निर्धारित करें
HTML पेजों के लिए फ़ाइल पथ प्रारूप निर्दिष्ट करें। एकल-पृष्ठ रेंडरिंग के लिए:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
बहु-पृष्ठ रेंडरिंग के लिए:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## चरण 3: एकल पृष्ठ HTML में रेंडर करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## चरण 4: एकाधिक पृष्ठों पर HTML रेंडर करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; // प्रति पृष्ठ आइटम सेट करें
    viewer.View(options);
}
```
## चरण 5: आउटपुट जांचें
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## निष्कर्ष
.NET के लिए GroupDocs.Viewer का उपयोग करके HTML पृष्ठों पर अभिलेखागार प्रस्तुत करना एक सीधी प्रक्रिया है। इस ट्यूटोरियल में बताए गए चरणों का पालन करके, आप अपने .NET अनुप्रयोगों में दस्तावेज़ देखने की क्षमताओं को सहजता से एकीकृत कर सकते हैं।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं अभिलेखों के अतिरिक्त अन्य दस्तावेज़ प्रारूप भी प्रस्तुत कर सकता हूँ?
हां, GroupDocs.Viewer पीडीएफ, DOCX, XLSX, PPTX, और अधिक सहित दस्तावेज़ प्रारूपों की एक विस्तृत श्रृंखला का समर्थन करता है।
### क्या GroupDocs.Viewer डेस्कटॉप और वेब अनुप्रयोगों दोनों के लिए उपयुक्त है?
बिल्कुल, GroupDocs.Viewer का उपयोग डेस्कटॉप और वेब अनुप्रयोगों दोनों में सहजता से किया जा सकता है।
### क्या GroupDocs.Viewer दर्शक इंटरफ़ेस के लिए अनुकूलन विकल्प प्रदान करता है?
हां, आप अपनी आवश्यकताओं के अनुसार व्यूअर इंटरफ़ेस को अनुकूलित कर सकते हैं।
### क्या मैं GroupDocs.Viewer के साथ दस्तावेजों को एसिंक्रोनस रूप से प्रस्तुत कर सकता हूं?
हां, GroupDocs.Viewer बेहतर प्रदर्शन के लिए अतुल्यकालिक रेंडरिंग क्षमताएं प्रदान करता है।
### क्या GroupDocs.Viewer दस्तावेज़ एनोटेशन का समर्थन करता है?
हां, GroupDocs.Viewer उपयोगकर्ताओं को दस्तावेज़ एनोटेशन को कुशलतापूर्वक देखने और प्रबंधित करने की अनुमति देता है।