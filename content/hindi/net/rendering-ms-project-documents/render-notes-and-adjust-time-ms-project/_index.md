---
"description": ".NET के लिए GroupDocs.Viewer के साथ MS Project दस्तावेज़ों को रेंडर करना सीखें। नोट्स रेंडर करें, समय इकाइयों को समायोजित करें, और विभिन्न आउटपुट फ़ॉर्मेट को आसानी से एक्सप्लोर करें।"
"linktitle": "नोट्स प्रस्तुत करें और समय इकाइयाँ समायोजित करें (MS प्रोजेक्ट)"
"second_title": "GroupDocs.Viewer .NET एपीआई"
"title": "नोट्स प्रस्तुत करें और समय इकाइयाँ समायोजित करें (MS प्रोजेक्ट)"
"url": "/hi/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# नोट्स प्रस्तुत करें और समय इकाइयाँ समायोजित करें (MS प्रोजेक्ट)

## परिचय
GroupDocs.Viewer for .NET एक शक्तिशाली दस्तावेज़ रेंडरिंग API है जो डेवलपर्स को उनके .NET अनुप्रयोगों के भीतर विभिन्न दस्तावेज़ स्वरूपों को देखने और हेरफेर करने की अनुमति देता है। इस ट्यूटोरियल में, हम विशेष रूप से MS Project दस्तावेज़ों के लिए नोट्स रेंडर करने और समय इकाइयों को समायोजित करने पर ध्यान केंद्रित करेंगे।
## आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित पूर्वापेक्षाएँ हैं:
1. .NET के लिए GroupDocs.Viewer: सुनिश्चित करें कि आपने .NET लाइब्रेरी के लिए GroupDocs.Viewer डाउनलोड और इंस्टॉल किया है। आप इसे यहाँ से डाउनलोड कर सकते हैं [यहाँ](https://releases.groupdocs.com/viewer/net/).
2. विकास वातावरण: .NET समर्थन के साथ अपना पसंदीदा विकास वातावरण सेट करें।
3. एमएस प्रोजेक्ट दस्तावेज़: परीक्षण के लिए एक नमूना एमएस प्रोजेक्ट दस्तावेज़ तैयार रखें।
## नामस्थान आयात करें
सबसे पहले, आइए MS प्रोजेक्ट दस्तावेज़ों को प्रस्तुत करने के लिए आवश्यक नेमस्पेस आयात करें:
## चरण 1: नामस्थान आयात करें
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
अब जबकि हमने आवश्यक नेमस्पेस आयात कर लिए हैं, तो आइए व्यापक समझ के लिए प्रत्येक उदाहरण को कई चरणों में विभाजित करें।
## MS प्रोजेक्ट दस्तावेज़ को HTML में प्रस्तुत करना
MS Project दस्तावेज़ को नोट्स सहित HTML प्रारूप में प्रस्तुत करने के लिए, इन चरणों का पालन करें:
### चरण 2: आउटपुट निर्देशिका और फ़ाइल स्वरूप सेट करें
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### चरण 3: व्यूअर ऑब्जेक्ट आरंभ करें और विकल्प सेट करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### चरण 4: दस्तावेज़ को HTML में प्रस्तुत करें
```csharp
viewer.View(options);
```
## MS प्रोजेक्ट दस्तावेज़ को छवि प्रारूप में प्रस्तुत करना
आप MS Project दस्तावेज़ों को JPG और PNG जैसे छवि प्रारूपों में भी प्रस्तुत कर सकते हैं। यहाँ बताया गया है कि कैसे:
### चरण 5: JPG के लिए आउटपुट निर्देशिका और फ़ाइल प्रारूप सेट करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### चरण 6: व्यूअर ऑब्जेक्ट को आरंभ करें और JPG विकल्प सेट करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### चरण 7: दस्तावेज़ को JPG में प्रस्तुत करें
```csharp
viewer.View(options);
```
PNG और अन्य छवि प्रारूपों में रेंडरिंग के लिए समान चरणों को दोहराएं।
## एमएस प्रोजेक्ट दस्तावेज़ को पीडीएफ में प्रस्तुत करना
MS प्रोजेक्ट दस्तावेज़ को PDF प्रारूप में प्रस्तुत करने के लिए, निम्नानुसार आगे बढ़ें:
### चरण 8: पीडीएफ के लिए आउटपुट डायरेक्टरी और फ़ाइल प्रारूप सेट करें
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### चरण 9: व्यूअर ऑब्जेक्ट आरंभ करें और PDF विकल्प सेट करें
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### चरण 10: दस्तावेज़ को PDF में प्रस्तुत करें
```csharp
viewer.View(options);
```

## निष्कर्ष
बधाई हो! आपने .NET के लिए GroupDocs.Viewer का उपयोग करके MS Project दस्तावेज़ों को रेंडर करना और समय इकाइयों को समायोजित करना सफलतापूर्वक सीख लिया है। दस्तावेज़ देखने की क्षमताओं को बढ़ाने के लिए इस ज्ञान को अपनी परियोजनाओं में शामिल करें।
## अक्सर पूछे जाने वाले प्रश्न
### क्या मैं MS प्रोजेक्ट दस्तावेज़ों को HTML, छवियों और PDF के अलावा अन्य प्रारूपों में प्रस्तुत कर सकता हूँ?
हां, .NET के लिए GroupDocs.Viewer DOCX, XLSX, PPTX, और अधिक जैसे विभिन्न प्रारूपों को प्रस्तुत करने का समर्थन करता है।
### क्या .NET के लिए GroupDocs.Viewer का कोई परीक्षण संस्करण उपलब्ध है?
हां, आप यहां से निःशुल्क परीक्षण प्राप्त कर सकते हैं [यहाँ](https://releases.groupdocs.com/).
### मैं .NET के लिए GroupDocs.Viewer हेतु अस्थायी लाइसेंस कैसे प्राप्त कर सकता हूं?
मिलने जाना [इस लिंक](https://purchase.groupdocs.com/temporary-license/) अस्थायी लाइसेंस प्राप्त करने के लिए।
### मैं .NET के लिए GroupDocs.Viewer के लिए दस्तावेज़ कहां पा सकता हूं?
दस्तावेज़ देखें [यहाँ](https://tutorials.groupdocs.com/viewer/net/).
### मैं GroupDocs.Viewer for .NET से संबंधित सहायता कहां प्राप्त कर सकता हूं या प्रश्न पूछ सकता हूं?
आप सहायता फ़ोरम पर जा सकते हैं [यहाँ](https://forum.groupdocs.com/c/viewer/9).