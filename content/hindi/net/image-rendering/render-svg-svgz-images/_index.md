---
title: SVG और SVGZ छवियाँ प्रस्तुत करें
linktitle: SVG और SVGZ छवियाँ प्रस्तुत करें
second_title: GroupDocs.Viewer .NET API
description: .NET के लिए GroupDocs.Viewer का उपयोग करके SVG और SVGZ छवियों को प्रस्तुत करना सीखें। वेक्टर ग्राफ़िक्स को आसानी से HTML, JPG, PNG और PDF में बदलें।
type: docs
weight: 16
url: /hi/net/image-rendering/render-svg-svgz-images/
---
## परिचय
इस ट्यूटोरियल में, हम .NET के लिए GroupDocs.Viewer का उपयोग करके SVG और SVGZ छवियों को प्रस्तुत करने की प्रक्रिया में आपका मार्गदर्शन करेंगे। .NET के लिए GroupDocs.Viewer एक शक्तिशाली दस्तावेज़ रेंडरिंग एपीआई है जो डेवलपर्स को अपने .NET अनुप्रयोगों में विभिन्न दस्तावेज़ प्रारूप प्रस्तुत करने में सक्षम बनाता है। एसवीजी और एसवीजीजेड वेक्टर ग्राफिक्स के लिए उपयोग किए जाने वाले लोकप्रिय छवि प्रारूप हैं, और .NET के लिए GroupDocs.Viewer के साथ, आप उन्हें आसानी से HTML, JPG, PNG और PDF जैसे विभिन्न आउटपुट स्वरूपों में प्रस्तुत कर सकते हैं।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित आवश्यक शर्तें स्थापित और सेटअप हैं:
1.  .NET के लिए GroupDocs.Viewer: .NET के लिए GroupDocs.Viewer को डाउनलोड और इंस्टॉल करें[यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास परिवेश: सुनिश्चित करें कि आपके पास .NET विकास के लिए एक कार्यशील विकास परिवेश है, जैसे विज़ुअल स्टूडियो।
3. नमूना SVGZ फ़ाइल: परीक्षण के लिए एक नमूना SVGZ फ़ाइल तैयार रखें।

## नामस्थान आयात करें
इससे पहले कि हम कोड में उतरें, आइए आवश्यक नामस्थान आयात करें:
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

## चरण 4: एसवीजीजेड को पीडीएफ में प्रस्तुत करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## निष्कर्ष
इस ट्यूटोरियल में, हमने सीखा है कि .NET के लिए GroupDocs.Viewer का उपयोग करके SVG और SVGZ छवियों को कैसे प्रस्तुत किया जाए। बस कुछ सरल चरणों के साथ, आप एसवीजीजेड छवियों को एचटीएमएल, जेपीजी, पीएनजी और पीडीएफ जैसे विभिन्न आउटपुट स्वरूपों में परिवर्तित कर सकते हैं, जिससे उन्हें विभिन्न वातावरणों में पहुंच योग्य और देखने योग्य बनाया जा सकता है।
## अक्सर पूछे जाने वाले प्रश्न
### क्या GroupDocs.Viewer अन्य छवि प्रारूप प्रस्तुत कर सकता है?
हां, GroupDocs.Viewer पीएनजी, जेपीईजी, बीएमपी, टीआईएफएफ, जीआईएफ और अन्य सहित विभिन्न छवि प्रारूपों को प्रस्तुत करने का समर्थन करता है।
### क्या GroupDocs.Viewer .NET कोर के साथ संगत है?
हाँ, GroupDocs.Viewer .NET Framework और .NET Core दोनों के साथ संगत है।
### क्या मैं रेंडरिंग विकल्पों को अनुकूलित कर सकता हूँ?
हाँ, GroupDocs.Viewer आपको अपनी आवश्यकताओं के अनुसार आउटपुट को अनुकूलित करने की अनुमति देते हुए व्यापक रेंडरिंग विकल्प प्रदान करता है।
### क्या GroupDocs.Viewer को किसी तृतीय-पक्ष निर्भरता की आवश्यकता है?
नहीं, GroupDocs.Viewer एक स्टैंडअलोन एपीआई है और दस्तावेज़ों को प्रस्तुत करने के लिए किसी तीसरे पक्ष की निर्भरता की आवश्यकता नहीं है।
### क्या परीक्षण के लिए कोई परीक्षण संस्करण उपलब्ध है?
हां, आप GroupDocs.Viewer का निःशुल्क परीक्षण संस्करण यहां से डाउनलोड कर सकते हैं[यहाँ](https://releases.groupdocs.com/) खरीदारी करने से पहले इसकी विशेषताओं का मूल्यांकन करें।