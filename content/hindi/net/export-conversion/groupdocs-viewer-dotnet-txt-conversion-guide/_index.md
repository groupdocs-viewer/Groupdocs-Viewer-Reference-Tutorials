---
"date": "2025-04-25"
"description": "इस व्यापक गाइड के साथ .NET के लिए GroupDocs.Viewer का उपयोग करके TXT फ़ाइलों को HTML, JPG, PNG और PDF जैसे कई प्रारूपों में परिवर्तित करना सीखें।"
"title": "GroupDocs.Viewer .NET का उपयोग करके TXT को HTML, JPG, PNG, PDF में रूपांतरित करें एक संपूर्ण गाइड"
"url": "/hi/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
type: docs
---
# GroupDocs.Viewer .NET के साथ TXT को एकाधिक प्रारूपों में कनवर्ट करें

## परिचय

क्या आप टेक्स्ट दस्तावेज़ों को HTML, JPG, PNG, या PDF जैसे विभिन्न प्रारूपों में आसानी से परिवर्तित करना चाहते हैं? दस्तावेज़ रूपांतरणों का प्रबंधन चुनौतीपूर्ण हो सकता है, खासकर जब कई पृष्ठों या विशिष्ट प्रारूप आवश्यकताओं से निपटना हो। **.NET के लिए GroupDocs.Viewer** TXT फ़ाइलों को विविध आउटपुट प्रारूपों में प्रस्तुत करने की प्रक्रिया को सरल बनाता है, जिससे यह सुनिश्चित होता है कि आपका डेटा सुलभ और दृश्यमान रूप से आकर्षक है।

![.NET के लिए GroupDocs.Viewer के साथ TXT को HTML, JPG, PNG, PDF में कनवर्ट करें](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

इस गाइड में, हम यह जानेंगे कि .NET के लिए GroupDocs.Viewer का उपयोग करके TXT दस्तावेज़ों को मल्टी-पेज HTML, सिंगल-पेज HTML, JPG, PNG और PDF में कैसे बदला जाए। अंत में, आप इसमें महारत हासिल कर लेंगे:
- GroupDocs.Viewer के साथ C# का उपयोग करके TXT फ़ाइलों को परिवर्तित करना
- आपकी आवश्यकताओं के लिए विभिन्न रेंडरिंग विकल्पों को क्रियान्वित करना
- रूपांतरण के दौरान प्रदर्शन को अनुकूलित करना

आइये, आपके दस्तावेज़ रूपांतरण चुनौतियों को हल करने के लिए आगे बढ़ें।

## आवश्यक शर्तें

शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित चीजें तैयार हैं:
- **विकास पर्यावरण**: विज़ुअल स्टूडियो 2019 या बाद का संस्करण.
- **.NET फ्रेमवर्क**: संस्करण 4.6.1 या उच्चतर.
- **.NET लाइब्रेरी के लिए GroupDocs.Viewer**:
  - NuGet पैकेज मैनेजर कंसोल के माध्यम से: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - .NET CLI का उपयोग करना: `dotnet add package GroupDocs.Viewer --version 25.3.0`

आसानी से सीखने के लिए C# प्रोग्रामिंग और .NET में बुनियादी फ़ाइल संचालन से परिचित होना अनुशंसित है।

## .NET के लिए GroupDocs.Viewer सेट अप करना

### इंस्टालेशन

आरंभ करने के लिए, स्थापित करें **ग्रुपडॉक्स.व्यूअर** अपनी पसंदीदा पैकेज मैनेजर का उपयोग करके लाइब्रेरी खोलें:

#### NuGet पैकेज मैनेजर कंसोल
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET सीएलआई
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### लाइसेंसिंग

आप एक से शुरू कर सकते हैं **मुफ्त परीक्षण** या प्राप्त करें **अस्थायी लाइसेंस** मूल्यांकन सीमाओं के बिना .NET के लिए GroupDocs.Viewer की पूर्ण क्षमताओं का पता लगाने के लिए:
- मुफ्त परीक्षण: [यहां से डाउनलोड करें](https://releases.groupdocs.com/viewer/net/)
- अस्थायी लाइसेंस: [यहां अनुरोध करें](https://purchase.groupdocs.com/temporary-license/)

निरंतर उपयोग के लिए, सीधे लाइसेंस खरीदने पर विचार करें [ग्रुपडॉक्स](https://purchase.groupdocs.com/buy).

### मूल आरंभीकरण

अपने प्रोजेक्ट में GroupDocs.Viewer सेट अप करने के लिए:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// TXT फ़ाइल पथ के साथ व्यूअर ऑब्जेक्ट को आरंभ करें।
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // आपका रेंडरिंग कोड यहां जाएगा.
}
```

## कार्यान्वयन मार्गदर्शिका

अब, आइए प्रत्येक सुविधा पर गहराई से विचार करें और देखें कि आप उन्हें कैसे क्रियान्वित कर सकते हैं।

### TXT दस्तावेज़ को बहु-पृष्ठ HTML में प्रस्तुत करें

#### अवलोकन
यह सुविधा TXT दस्तावेज़ को बहु-पृष्ठ HTML प्रारूप में परिवर्तित करने का प्रदर्शन करती है। टेक्स्ट फ़ाइल का प्रत्येक पृष्ठ एम्बेडेड संसाधनों के साथ एक अलग HTML फ़ाइल के रूप में प्रस्तुत किया जाता है।

#### चरण 1: व्यूअर सेटअप करें

एक बनाने के `Viewer` आपके स्रोत TXT फ़ाइल के लिए ऑब्जेक्ट:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// एक नमूना पाठ फ़ाइल के साथ व्यूअर को आरंभ करें.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // चरण 2 पर जारी रखें...
```

#### चरण 2: HTML दृश्य विकल्प कॉन्फ़िगर करें

स्थापित करना `HtmlViewOptions` प्रत्येक पृष्ठ को अलग से प्रस्तुत करने के लिए:

```csharp
// बहु-पृष्ठ रेंडरिंग के लिए HTML दृश्य विकल्प सेट करें.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// दस्तावेज़ को बहु-पृष्ठ HTML के रूप में प्रस्तुत करें.
viewer.View(options);
}
```

**स्पष्टीकरण**: द `ForEmbeddedResources()` विधि यह सुनिश्चित करती है कि छवियाँ और शैलियाँ जैसे संसाधन सीधे HTML फ़ाइल में एम्बेड किए जाएँ, जिससे आसान साझाकरण की सुविधा मिलती है।

### TXT दस्तावेज़ को एकल पृष्ठ HTML में प्रस्तुत करें

#### अवलोकन
TXT दस्तावेज़ को एकल HTML पृष्ठ में परिवर्तित करें, यह उन दस्तावेज़ों के लिए आदर्श है जिन्हें एक सतत वेबपेज के रूप में प्रदर्शित करने की आवश्यकता होती है।

#### चरण 1: व्यूअर सेटअप करें

आरंभ करें `Viewer` वस्तु:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// किसी भिन्न टेक्स्ट फ़ाइल के लिए एक नया व्यूअर इंस्टैंस आरंभ करें.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // चरण 2 पर जारी रखें...
```

#### चरण 2: एकल पृष्ठ HTML विकल्प कॉन्फ़िगर करें

कॉन्फ़िगर `HtmlViewOptions` एकल-पृष्ठ सेटिंग सक्षम होने पर:

```csharp
// एकल HTML पृष्ठ में रेंडरिंग के लिए विकल्प सेट करें.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// एकल HTML पृष्ठ के रूप में प्रस्तुत करें.
viewer.View(options);
}
```

**स्पष्टीकरण**: द `RenderToSinglePage` संपत्ति यह सुनिश्चित करती है कि संपूर्ण सामग्री एक पृष्ठ पर प्रस्तुत की जाए।

### TXT दस्तावेज़ को JPG में प्रस्तुत करें

#### अवलोकन
यह सुविधा आपको किसी पाठ दस्तावेज़ को JPEG छवि में परिवर्तित करने की अनुमति देती है, जो दृश्य प्रस्तुतियों या संग्रहण उद्देश्यों के लिए उपयोगी है।

#### चरण 1: व्यूअर सेटअप करें

खुद को तैयार करें `Viewer` वस्तु:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// एक नमूना फ़ाइल के साथ व्यूअर को आरंभ करें.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // चरण 2 पर जारी रखें...
```

#### चरण 2: JPG दृश्य विकल्प कॉन्फ़िगर करें

स्थापित करना `JpgViewOptions` छवि रेंडरिंग के लिए:

```csharp
// JPG छवि के रूप में प्रस्तुत करने के लिए विकल्प सेट करें.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// दस्तावेज़ को JPEG फ़ाइल के रूप में प्रस्तुत करें.
viewer.View(options);
}
```

**स्पष्टीकरण**: द `JpgViewOptions` क्लास यह निर्दिष्ट करता है कि आपके दस्तावेज़ के प्रत्येक पृष्ठ को JPEG प्रारूप में कैसे प्रस्तुत और सहेजा जाए।

### TXT दस्तावेज़ को PNG में प्रस्तुत करें

#### अवलोकन
किसी टेक्स्ट दस्तावेज़ को PNG प्रारूप में परिवर्तित करें, पारदर्शिता समर्थन के साथ उच्च गुणवत्ता वाली छवि आउटपुट प्रदान करें।

#### चरण 1: व्यूअर सेटअप करें

आरंभ करें `Viewer` वस्तु:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// अपनी TXT फ़ाइल के लिए एक व्यूअर इंस्टैंस बनाएँ.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // चरण 2 पर जारी रखें...
```

#### चरण 2: PNG दृश्य विकल्प कॉन्फ़िगर करें

स्थापित करना `PngViewOptions`:

```csharp
// PNG छवि के रूप में प्रस्तुत करने के लिए दृश्य विकल्प सेट करें.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// दस्तावेज़ को PNG प्रारूप में प्रस्तुत करें.
viewer.View(options);
}
```

**स्पष्टीकरण**: द `PngViewOptions` क्लास प्रत्येक पृष्ठ को पारदर्शिता के साथ प्रस्तुत करने की अनुमति देता है, जिससे यह स्तरित ग्राफिक्स के लिए उपयुक्त हो जाता है।

### TXT दस्तावेज़ को PDF में प्रस्तुत करें

#### अवलोकन
यह सुविधा पाठ्य दस्तावेजों को सार्वभौमिक रूप से सुलभ पीडीएफ प्रारूप में परिवर्तित करने के लिए एकदम उपयुक्त है।

#### चरण 1: व्यूअर सेटअप करें

खुद को तैयार करें `Viewer` वस्तु:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// अपनी नमूना पाठ फ़ाइल के लिए एक व्यूअर इंस्टैंस आरंभ करें.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // चरण 2 पर जारी रखें...
```

#### चरण 2: PDF दृश्य विकल्प कॉन्फ़िगर करें

स्थापित करना `PdfViewOptions`:

```csharp
// PDF दस्तावेज़ के रूप में प्रस्तुत करने के लिए दृश्य विकल्प सेट करें.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// दस्तावेज़ को PDF फ़ाइल में प्रस्तुत करें.
viewer.View(options);
}
```

**स्पष्टीकरण**: द `PdfViewOptions` क्लास निर्दिष्ट करता है कि आप अपनी TXT फ़ाइलों को PDF दस्तावेज़ों के रूप में कैसे परिवर्तित और सहेज सकते हैं।

## निष्कर्ष

.NET के लिए GroupDocs.Viewer के साथ, टेक्स्ट दस्तावेज़ों को विभिन्न स्वरूपों में परिवर्तित करना सरल है। इस गाइड में C# का उपयोग करके TXT फ़ाइलों को बहु-पृष्ठ HTML, एकल-पृष्ठ HTML, JPG, PNG और PDF में बदलना शामिल है। चाहे आप दस्तावेज़ की पहुँच या संगतता को बढ़ाना चाहते हों, ये विधियाँ मज़बूत समाधान प्रदान करती हैं।

अधिक सहायता या अधिक उन्नत सुविधाओं के लिए, देखें [आधिकारिक GroupDocs.Viewer दस्तावेज़](https://docs.groupdocs.com/viewer/net/). हैप्पी कोडिंग!