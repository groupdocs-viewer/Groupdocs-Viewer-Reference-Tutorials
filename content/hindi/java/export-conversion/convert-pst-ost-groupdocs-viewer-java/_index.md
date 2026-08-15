---
date: '2026-07-19'
description: GroupDocs.Viewer for Java का उपयोग करके PST को HTML और JPG, PNG, PDF
  जैसे अन्य फ़ॉर्मैट में बदलना सीखें। यह गाइड सभी आवश्यक चरणों और कॉन्फ़िगरेशन को
  कवर करता है।
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: GroupDocs.Viewer for Java का उपयोग करके PST को HTML में तेज़ी से बदलें।
  चरण‑दर‑चरण सीखें कि कैसे JPG, PNG, और PDF में भी निर्यात किया जाए, एक production‑ready
  guide में।
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: GroupDocs.Viewer for Java के साथ PST को HTML में बदलें – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: GroupDocs.Viewer for Java का उपयोग करके PST को HTML, JPG, PNG, PDF में बदलें
type: docs
url: /hi/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer for Java का उपयोग करके PST को HTML, JPG, PNG, PDF में बदलें

क्या आप **convert pst to html** या JPG, PNG, या PDF जैसे अन्य फ़ॉर्मेट में बदलने की तलाश में हैं? शक्तिशाली GroupDocs.Viewer for Java लाइब्रेरी के साथ, यह कार्य सरल और कुशल है। इस ट्यूटोरियल में आप सीखेंगे कि Outlook PST/OST फ़ाइलों को वेब‑फ़्रेंडली HTML, इमेज फ़ाइलों, या एकल PDF में कैसे रेंडर किया जाए, जिससे आपके ईमेल आर्काइव को साझा करना और संग्रहित करना आसान हो जाता है।

![GroupDocs.Viewer for Java के साथ PST/OST को HTML, JPG, PNG, PDF में बदलें](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[GroupDocs.Viewer for Java के साथ PST/OST को HTML, JPG, PNG, PDF में बदलें](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**आप क्या सीखेंगे**
- Maven प्रोजेक्ट में GroupDocs.Viewer for Java को सेट अप करने का तरीका।  
- HTML, JPG, PNG, और PDF में **java convert pst** फ़ाइलों को बदलने के लिए चरण‑दर‑चरण निर्देश।  
- सर्वोत्तम प्रदर्शन और सामान्य समस्याओं के लिए कॉन्फ़िगरेशन टिप्स।

## त्वरित उत्तर
- **PST रूपांतरण को कौन सी लाइब्रेरी संभालती है?** GroupDocs.Viewer for Java.  
- **क्या मैं PST को सीधे PDF में बदल सकता हूँ?** हाँ, `PdfViewOptions` का उपयोग करके।  
- **क्या उत्पादन के लिए लाइसेंस आवश्यक है?** एक वैध GroupDocs लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण समर्थित है?** JDK 8 या उससे ऊपर।  
- **क्या मुझे अटैचमेंट्स को मैन्युअली निकालना पड़ेगा?** नहीं, व्यूअर उन्हें स्वचालित रूप से रेंडर करता है।

## GroupDocs.Viewer for Java क्या है?
GroupDocs.Viewer for Java एक सर्वर‑साइड API है जो 100 से अधिक दस्तावेज़ और ईमेल फ़ॉर्मेट लोड करता है और उन्हें बाहरी सॉफ़्टवेयर के बिना HTML, इमेज, या PDF आउटपुट में रेंडर करता है। यह PST फ़ाइलों को 2 GB तक प्रोसेस करता है जबकि मेमोरी उपयोग 200 MB से कम रखता है।

## GroupDocs.Viewer for Java का उपयोग करके pst को html में कैसे बदलें?
`new Viewer("source.pst")` के साथ PST फ़ाइल लोड करें, आउटपुट फ़ोल्डर की ओर इशारा करने के लिए `HtmlViewOptions` को कॉन्फ़िगर करें, और `viewer.view(htmlOptions)` को कॉल करें। API स्वचालित रूप से PST के भीतर सभी संदेशों पर इटररेट करता है और एक व्यवस्थित HTML हायरार्की उत्पन्न करता है।

### GroupDocs.Viewer क्यों चुनें?
- **उच्च‑गुणवत्ता रेंडरिंग** – ईमेल सामग्री का 99.9 % (रिच‑टेक्स्ट बॉडीज़, टेबल्स, और एम्बेडेड इमेजेज सहित) सटीक रूप से पुन: उत्पन्न किया जाता है।  
- **एकाधिक आउटपुट फ़ॉर्मेट** – एक API कॉल HTML, JPG, PNG, या PDF उत्पन्न कर सकता है, जिसमें 50+ एक्सपोर्ट विकल्प शामिल हैं।  
- **शून्य बाहरी निर्भरताएँ** – Outlook, Exchange Server, या थर्ड‑पार्टी कन्वर्टर्स की आवश्यकता नहीं; सब कुछ आपके Java रनटाइम के भीतर चलता है।

## पूर्वापेक्षाएँ
- **GroupDocs.Viewer for Java** – संस्करण 25.2 या बाद का।  
- **Java Development Kit (JDK)** – 8 या नया।  
- निर्भरता प्रबंधन के लिए Maven।  
- बुनियादी Java ज्ञान और Maven से परिचितता।

## GroupDocs.Viewer for Java सेट अप करना
`Viewer` GroupDocs.Viewer for Java में मुख्य क्लास है जो दस्तावेज़ लोड करता है और चुने हुए फ़ॉर्मेट में रेंडर करता है। अपने `pom.xml` में GroupDocs रिपॉज़िटरी और डिपेंडेंसी जोड़ें:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### लाइसेंस प्राप्ति
- **Free trial** – बिना लागत के सभी फीचर एक्सप्लोर करें।  
- **Temporary license** – आवश्यकता पड़ने पर मूल्यांकन समय बढ़ाएँ।  
- **Full license** – प्रोडक्शन डिप्लॉयमेंट्स के लिए आवश्यक।

### बेसिक इनिशियलाइज़ेशन
`Viewer` इंस्टेंस हल्के होते हैं; आप कई फ़ाइलों के लिए एक ही इंस्टेंस को पुन: उपयोग करके ऑब्जेक्ट‑क्रिएशन ओवरहेड को कम कर सकते हैं।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## इम्प्लीमेंटेशन गाइड
निम्नलिखित सेक्शन आपको PST/OST फ़ाइलों को प्रत्येक समर्थित फ़ॉर्मेट में रेंडर करने की प्रक्रिया दिखाते हैं।

### PST/OST दस्तावेज़ को HTML में रेंडर करना

#### चरण 1: आउटपुट डायरेक्टरी सेट अप करें
एक फ़ोल्डर निर्धारित करें जहाँ HTML पेज लिखे जाएंगे। GroupDocs प्रत्येक ईमेल के लिए एक सब‑फ़ोल्डर बनाता है ताकि एसेट्स व्यवस्थित रहें।

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### चरण 2: लोड ऑप्शन्स कॉन्फ़िगर करें
`LoadOptions` आपको पासवर्ड हैंडलिंग, रिसोर्स‑लोडिंग टाइमआउट, और चयनात्मक पेज रेंडरिंग निर्दिष्ट करने देता है। 30 सेकंड का टाइमआउट सेट करना अधिकांश सर्वर वातावरण में अच्छा काम करता है।

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### चरण 3: HTML व्यू ऑप्शन्स निर्धारित करें
`HtmlViewOptions` आउटपुट फ़ोल्डर, रिसोर्स हैंडलिंग, और HTML कन्वर्ज़न के लिए वैकल्पिक CSS सेटिंग्स निर्दिष्ट करता है।

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### चरण 4: व्यूअर को इनिशियलाइज़ करें और HTML रेंडर करें
`Viewer` ऑब्जेक्ट बनाएं, PST फ़ाइल पाथ पास करें, और `HtmlViewOptions` के साथ `view` को कॉल करें। API स्वचालित रूप से PST के भीतर सभी संदेशों पर इटररेट करता है और एक व्यवस्थित HTML हायरार्की उत्पन्न करता है।

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### PST/OST दस्तावेज़ को JPG में रेंडर करना

#### चरण 1: आउटपुट डायरेक्टरी सेट अप करें
JPG स्नैपशॉट्स के लिए एक समर्पित फ़ोल्डर बनाएं; प्रत्येक ईमेल उसकी लंबाई के आधार पर एक या अधिक इमेज फ़ाइलों में बदल जाएगा।

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### चरण 2: लोड ऑप्शन्स कॉन्फ़िगर करें
HTML के लिए उपयोग किए गए वही `LoadOptions` यहाँ पुन: उपयोग किए जा सकते हैं, जिससे फ़ॉर्मेट्स में पासवर्ड हैंडलिंग सुसंगत रहती है।

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### चरण 3: JPG व्यू ऑप्शन्स निर्धारित करें
`JpgViewOptions` इमेज रेज़ोल्यूशन, क्वालिटी, और JPEG कन्वर्ज़न के लिए आउटपुट फ़ोल्डर को नियंत्रित करता है।

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### चरण 4: व्यूअर को इनिशियलाइज़ करें और JPG रेंडर करें
`viewer.view(jpgOptions)` का उपयोग करके वेब प्रीव्यू के लिए तैयार हाई‑क्वालिटी JPEG फ़ाइलें जनरेट करें।

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### PST/OST दस्तावेज़ को PNG में रेंडर करना

#### चरण 1: आउटपुट डायरेक्टरी सेट अप करें
PNG आउटपुट तब उपयोगी होता है जब आपको आर्काइविंग या OCR प्रोसेसिंग के लिए लॉसलेस क्वालिटी चाहिए।

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### चरण 2: लोड ऑप्शन्स कॉन्फ़िगर करें
पासवर्ड और टाइमआउट कॉन्फ़िगरेशन के अलावा कोई अतिरिक्त सेटिंग्स आवश्यक नहीं हैं।

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### चरण 3: PNG व्यू ऑप्शन्स निर्धारित करें
`PngViewOptions` आपको ट्रांसपेरेंट बैकग्राउंड और लॉसलेस PNG इमेजेज के लिए आउटपुट फ़ोल्डर सेट करने देता है।

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### चरण 4: व्यूअर को इनिशियलाइज़ करें और PNG रेंडर करें
`viewer.view(pngOptions)` को इंस्टैंशिएट करके प्रत्येक ईमेल के PNG स्नैपशॉट बनाएं।

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### PST/OST दस्तावेज़ को PDF में रेंडर करना

#### चरण 1: आउटपुट डायरेक्टरी सेट अप करें
PST प्रति एकल PDF फ़ाइल कानूनी‑रिव्यू वर्कफ़्लो को सरल बनाती है और स्टोरेज ओवरहेड को कम करती है।

CODE_BLOCK_PLACEHOLDER_14_END

#### चरण 2: लोड ऑप्शन्स कॉन्फ़िगर करें
PDF में कन्वर्ट करते समय, आप `setEmbedFonts(true)` को एनेबल करना चाह सकते हैं ताकि किसी भी मशीन पर विज़ुअल फ़िडेलिटी सुनिश्चित हो।

CODE_BLOCK_PLACEHOLDER_15_END

#### चरण 3: PDF व्यू ऑप्शन्स निर्धारित करें
`PdfViewOptions` आपको कॉम्प्रेशन लेवल चुनने, फ़ॉन्ट एम्बेड करने, और PDF कन्वर्ज़न के लिए आउटपुट फ़ाइल नाम सेट करने देता है।

CODE_BLOCK_PLACEHOLDER_16_END

#### चरण 4: व्यूअर को इनिशियलाइज़ करें और PDF रेंडर करें
`PdfViewOptions` बनाएं, वैकल्पिक रूप से कॉम्प्रेशन लेवल चुनें, और `viewer.view(pdfOptions)` को कॉल करें। API सभी ईमेल को एक सर्चेबल PDF दस्तावेज़ में मर्ज कर देता है।

CODE_BLOCK_PLACEHOLDER_17_END

## व्यावहारिक उपयोग
- **ईमेल आर्काइविंग:** बड़े PST आर्काइव को कंप्लायंस के लिए सर्चेबल HTML या PDF में बदलें।  
- **डॉक्यूमेंट मैनेजमेंट सिस्टम्स:** कन्वर्टेड फ़ाइलों को ऐसे सिस्टम में स्टोर करें जो केवल PDF, PNG, या JPG स्वीकार करते हैं।  
- **कोलैबोरेशन प्लेटफ़ॉर्म:** Slack या Teams में इमेज के रूप में कन्वर्टेड ईमेल शेयर करें।  
- **लीगल रिव्यू:** कोर्ट को ईमेल साक्ष्य के PDF संस्करण प्रदान करें।  
- **बैकअप स्ट्रैटेजी:** महत्वपूर्ण संदेशों के हल्के PNG या JPG स्नैपशॉट रखें।

## प्रदर्शन संबंधी विचार
- **रिसोर्स मैनेजमेंट:** कई फ़ाइलों को प्रोसेस करते समय `Viewer` इंस्टेंस को पुन: उपयोग करें ताकि ओवरहेड कम हो।  
- **मेमोरी ट्यूनिंग:** सर्वर क्षमता के आधार पर `loadOptions.setResourceLoadingTimeout` को समायोजित करें।  
- **असिंक्रोनस प्रोसेसिंग:** रिस्पॉन्सिव UI के लिए कन्वर्ज़न को बैकग्राउंड थ्रेड्स में ऑफ़लोड करें।

## अक्सर पूछे जाने वाले प्रश्न
**Q: मैं उसी कोड बेस के साथ **convert pst to pdf** कैसे करूँ?**  
A: PDF रेंडरिंग सेक्शन में दिखाए अनुसार `PdfViewOptions` का उपयोग करें; बाकी कोड समान रहता है।

**Q: क्या GroupDocs.Viewer एन्क्रिप्टेड PST फ़ाइलों को संभाल सकता है?**  
A: हाँ, रेंडर करने से पहले `LoadOptions.setPassword("yourPassword")` के माध्यम से पासवर्ड प्रदान करें।

**Q: **java convert pst** को PNG बनाम JPG में बदलने में क्या अंतर है?**  
A: PNG लॉसलेस क्वालिटी रखता है, स्क्रीनशॉट के लिए आदर्श, जबकि JPG ईमेल प्रीव्यू के लिए छोटे फ़ाइल आकार प्रदान करता है।

**Q: क्या **how to convert pst** फ़ाइलों को बल्क में करने का कोई तरीका है?**  
A: रेंडरिंग लॉजिक को लूप में रखें जो PST फ़ाइलों की डायरेक्टरी पर इटररेट करे; प्रत्येक फ़ाइल के लिए वही `Viewer` कॉन्फ़िगरेशन पुन: उपयोग करें।

**Q: क्या API 1 GB से बड़ी PST फ़ाइलों को कन्वर्ट करने का समर्थन करता है?**  
A: हाँ, GroupDocs.Viewer डेटा को स्ट्रीम करता है और पूरी आर्काइव को मेमोरी में लोड किए बिना 2 GB तक की फ़ाइलों को प्रोसेस कर सकता है।

## निष्कर्ष
अब आपके पास GroupDocs.Viewer for Java का उपयोग करके **convert pst to html**, JPG, PNG, और PDF में बदलने के लिए एक पूर्ण, प्रोडक्शन‑रेडी गाइड है। ऊपर दिए गए चरणों का पालन करके आप ईमेल कन्वर्ज़न को किसी भी Java‑आधारित वर्कफ़्लो में इंटीग्रेट कर सकते हैं, एक्सेसिबिलिटी सुधार सकते हैं, और कंप्लायंस आवश्यकताओं को पूरा कर सकते हैं।

---

**अंतिम अपडेट:** 2026-07-19  
**टेस्टेड विथ:** GroupDocs.Viewer for Java 25.2  
**लेखक:** GroupDocs

## संबंधित ट्यूटोरियल
- [GroupDocs.Viewer for Java का उपयोग करके NSF को PDF, HTML, JPG, PNG में बदलें](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – GroupDocs.Viewer for Java का उपयोग करके ODF को HTML, JPG, PNG, PDF में बदलें](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [GroupDocs.Viewer for Java का उपयोग करके DOCX को HTML में कैसे बदलें: चरण‑दर‑चरण गाइड](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)