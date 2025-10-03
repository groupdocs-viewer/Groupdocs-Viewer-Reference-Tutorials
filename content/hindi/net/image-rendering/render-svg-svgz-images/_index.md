---
"description": ".NET के लिए GroupDocs.Viewer का उपयोग करके SVG और SVGZ चित्र रेंडर करना सीखें। वेक्टर ग्राफ़िक्स को आसानी से HTML, JPG, PNG और PDF में बदलें।"
"linktitle": "SVG और SVGZ छवियाँ प्रस्तुत करें"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "SVG और SVGZ छवियाँ प्रस्तुत करें"
"url": "/hi/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# SVG और SVGZ छवियाँ प्रस्तुत करें

## परिचय
इस ट्यूटोरियल में, हम आपको GroupDocs.Viewer for .NET का उपयोग करके SVG और SVGZ इमेज रेंडर करने की प्रक्रिया के बारे में मार्गदर्शन करेंगे। GroupDocs.Viewer for .NET एक शक्तिशाली दस्तावेज़ रेंडरिंग API है जो डेवलपर्स को उनके .NET अनुप्रयोगों में विभिन्न दस्तावेज़ स्वरूपों को रेंडर करने में सक्षम बनाता है। SVG और SVGZ वेक्टर ग्राफ़िक्स के लिए उपयोग किए जाने वाले लोकप्रिय छवि प्रारूप हैं, और GroupDocs.Viewer for .NET के साथ, आप उन्हें HTML, JPG, PNG और PDF जैसे विभिन्न आउटपुट स्वरूपों में आसानी से रेंडर कर सकते हैं।

![.NET के लिए GroupDocs.Viewer के साथ SVG और SVGZ छवियाँ प्रस्तुत करें](/viewer/image-rendering/render-svg-and-svgz-images.png)

## आवश्यक शर्तें
आरंभ करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ स्थापित और सेट अप हैं:
1. .NET के लिए GroupDocs.Viewer: .NET के लिए GroupDocs.Viewer को डाउनलोड करें और इंस्टॉल करें [यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास .NET विकास के लिए कार्यशील विकास परिवेश है, जैसे कि Visual Studio.
3. नमूना SVGZ फ़ाइल: परीक्षण के लिए एक नमूना SVGZ फ़ाइल तैयार रखें।

## नामस्थान आयात करें
कोड में आगे बढ़ने से पहले, आइए आवश्यक नेमस्पेस आयात करें:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## चरण 1: SVGZ को HTML में प्रस्तुत करें
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## चरण 2: SVGZ को JPG में प्रस्तुत करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## चरण 3: SVGZ को PNG में प्रस्तुत करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## चरण 4: SVGZ को PDF में प्रस्तुत करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने .NET के लिए GroupDocs.Viewer का उपयोग करके SVG और SVGZ छवियों को प्रस्तुत करना सीखा है। बस कुछ सरल चरणों के साथ, आप SVGZ छवियों को HTML, JPG, PNG और PDF जैसे विभिन्न आउटपुट स्वरूपों में परिवर्तित कर सकते हैं, जिससे उन्हें विभिन्न वातावरणों में सुलभ और देखने योग्य बनाया जा सकता है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या GroupDocs.Viewer अन्य छवि प्रारूपों को प्रस्तुत कर सकता है?
हां, GroupDocs.Viewer PNG, JPEG, BMP, TIFF, GIF, आदि सहित विभिन्न छवि प्रारूपों को प्रस्तुत करने का समर्थन करता है।
### क्या GroupDocs.Viewer .NET कोर के साथ संगत है?
हां, GroupDocs.Viewer .NET फ्रेमवर्क और .NET कोर दोनों के साथ संगत है।
### क्या मैं रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
हां, GroupDocs.Viewer व्यापक रेंडरिंग विकल्प प्रदान करता है जिससे आप अपनी आवश्यकताओं के अनुसार आउटपुट को अनुकूलित कर सकते हैं।
### क्या GroupDocs.Viewer को किसी तृतीय-पक्ष निर्भरता की आवश्यकता है?
नहीं, GroupDocs.Viewer एक स्टैंडअलोन एपीआई है और दस्तावेजों को प्रस्तुत करने के लिए किसी तीसरे पक्ष की निर्भरता की आवश्यकता नहीं है।
### क्या परीक्षण के लिए कोई परीक्षण संस्करण उपलब्ध है?
हां, आप GroupDocs.Viewer का निःशुल्क परीक्षण संस्करण यहां से डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/) खरीदारी करने से पहले इसकी विशेषताओं का मूल्यांकन करें।