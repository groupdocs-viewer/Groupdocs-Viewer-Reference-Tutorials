---
date: '2026-08-30'
description: GroupDocs.Viewer for Java के साथ DWG को PNG में कैसे कनवर्ट करें, Java
  में background color सेट करें, और image size को कस्टमाइज़ करें, यह सीखें।
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: GroupDocs.Viewer for Java का उपयोग करके DWG को PNG में कनवर्ट करें,
  जबकि custom image width और background color सेट किया जाए। यह गाइड स्टेप‑बाय‑स्टेप
  सेटअप, कोड स्निपेट्स, और ट्रबलशूटिंग टिप्स प्रदान करता है।
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Java में custom size और background color के साथ DWG को PNG में कनवर्ट करें
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: GroupDocs.Viewer for Java का उपयोग करके DWG को PNG में custom size और background
  color के साथ कैसे कनवर्ट करें
type: docs
url: /hi/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# DWG को PNG में कस्टम आकार और बैकग्राउंड रंग के साथ GroupDocs.Viewer for Java का उपयोग करके कैसे बदलें

इस ट्यूटोरियल में आप सीखेंगे **DWG को PNG में कैसे बदलें** जबकि आउटपुट आयाम और बैकग्राउंड रंग को नियंत्रित किया जा रहा है, GroupDocs.Viewer for Java का उपयोग करके। चाहे आपको रिपोर्ट में CAD ड्रॉइंग्स एम्बेड करनी हों, वेब पोर्टल के लिए थंबनेल बनाना हो, या बैच रेंडरिंग को ऑटोमेट करना हो, नीचे दिए गए चरण प्रत्येक PNG फ़ाइल की दृश्य उपस्थिति पर पूर्ण नियंत्रण प्रदान करते हैं।

## त्वरित उत्तर
- **DWG को PNG में बदलना क्या मतलब है?** यह प्रक्रिया है जिसमें DWG CAD फ़ाइल को कोड के माध्यम से PNG इमेज में बदला जाता है, वेक्टर विवरण को रास्टर पिक्सेल के रूप में संरक्षित किया जाता है।  
- **क्या मैं कस्टम चौड़ाई सेट कर सकता हूँ?** हाँ – `CadOptions.forRenderingByWidth(int width)` को कॉल करके आप आवश्यक सटीक पिक्सेल चौड़ाई निर्धारित कर सकते हैं।  
- **बैकग्राउंड रंग कैसे बदलें?** रेंडरिंग से पहले `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` का उपयोग करें।  
- **कौन सी लाइब्रेरी आवश्यक है?** GroupDocs.Viewer for Java (संस्करण 25.2 या नया)।  
- **क्या मुझे लाइसेंस चाहिए?** एक अस्थायी या पूर्ण लाइसेंस मूल्यांकन सीमाओं को हटाता है और असीमित रेंडरिंग सक्षम करता है।

![कस्टम आकार और बैकग्राउंड रंग के साथ PNG में CAD ड्रॉइंग्स रेंडर करें GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## GroupDocs.Viewer for Java क्या है?
GroupDocs.Viewer for Java एक सर्वर‑साइड API है जो 150 से अधिक फ़ाइल फ़ॉर्मेट—जिसमें CAD फ़ाइलें भी शामिल हैं—को इमेज, PDF, या HTML में रेंडर करता है। यह AutoCAD जैसे किसी भी थर्ड‑पार्टी सॉफ़्टवेयर की आवश्यकता के बिना काम करता है, जिससे यह ऑटोमेटेड पाइपलाइन के लिए आदर्श बनता है।

## कस्टम आकार और बैकग्राउंड रंग के साथ DWG को PNG में कैसे बदलें?
DWG फ़ाइल को `Viewer` इंस्टेंस के साथ लोड करें, इच्छित चौड़ाई और बैकग्राउंड के लिए `CadOptions` को कॉन्फ़िगर करें, और अंत में `viewer.view` को `PngViewOptions` के साथ कॉल करें। यह तीन‑स्टेप प्रक्रिया फ़ाइल I/O, रेंडरिंग, और आउटपुट नामकरण को एक ही मेमोरी‑कुशल ऑपरेशन में संभालती है।

Viewer वह मुख्य क्लास है जो दस्तावेज़ को लोड करता है और रेंडरिंग करता है।  
CadOptions CAD‑विशिष्ट सेटिंग्स जैसे इमेज चौड़ाई और बैकग्राउंड रंग को कॉन्फ़िगर करता है।  
PngViewOptions रेंडर किए गए पृष्ठों के लिए PNG आउटपुट फ़ॉर्मेट और नामकरण पैटर्न को परिभाषित करता है।

अब आप किसी भी DWG ड्रॉइंग को बिल्कुल वही चौड़ाई वाले PNG में रेंडर कर सकते हैं जो आप निर्दिष्ट करते हैं, और आप अपने ब्रांड या UI थीम से मेल खाने के लिए कोई भी ठोस रंग (या ट्रांसपेरेंट) बैकग्राउंड चुन सकते हैं।

## कस्टम बैकग्राउंड रंग क्यों सेट करें?
बैकग्राउंड रंग सेट करने से रेंडर किया गया PNG आसपास के UI तत्वों के साथ सहजता से मिल जाता है, अनचाहे सफेद मार्जिन से बचाता है, और ड्रॉइंग विवरण को उजागर कर सकता है जो डिफ़ॉल्ट सफेद कैनवास पर खो जाते। GroupDocs.Viewer किसी भी `java.awt.Color` को सपोर्ट करता है, जिसमें कस्टम RGB मान भी शामिल हैं, जिससे आपको पिक्सेल‑परफेक्ट नियंत्रण मिलता है।

java.awt.Color वह रंग मान दर्शाता है जिसका उपयोग बैकग्राउंड रेंडरिंग के लिए किया जाता है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK) 8+** – API Java 8 और उससे ऊपर को लक्षित करता है।  
- **Maven** – डिपेंडेंसी मैनेजमेंट के लिए।  
- **IDE** – IntelliJ IDEA, Eclipse, या कोई भी एडिटर जो आप पसंद करते हैं।  
- **Basic Java file‑handling knowledge** – स्रोत DWG फ़ाइलें पढ़ने और PNG आउटपुट लिखने के लिए।

## GroupDocs.Viewer for Java सेटअप करना
अपने Maven `pom.xml` में GroupDocs रिपॉजिटरी और Viewer डिपेंडेंसी जोड़ें:

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
GroupDocs पोर्टल से एक अस्थायी या पूर्ण लाइसेंस कुंजी प्राप्त करें और `license.lic` फ़ाइल को अपने प्रोजेक्ट रिसोर्सेज फ़ोल्डर में रखें। यह 20‑पेज मूल्यांकन सीमा को हटाता है और फुल‑रेज़ोल्यूशन रेंडरिंग को अनलॉक करता है।

### बेसिक इनिशियलाइज़ेशन और सेटअप
एक `Viewer` इंस्टेंस बनाएं जो आपके DWG फ़ाइलों वाले फ़ोल्डर की ओर इशारा करता हो:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## फ़ीचर 1: कस्टम इमेज आकार और बैकग्राउंड रंग के साथ CAD ड्रॉइंग्स रेंडर करना
### CAD बैकग्राउंड रंग कैसे बदलें
CAD बैकग्राउंड रंग बदलने के लिए, रेंडरिंग से पहले CadOptions ऑब्जेक्ट को कॉन्फ़िगर करें। `forRenderingByWidth` के साथ इच्छित चौड़ाई सेट करें और `setBackgroundColor` का उपयोग करके नया बैकग्राउंड लागू करें। फिर Viewer ऐसे PNG इमेज बनाता है जो निर्दिष्ट रंग को दर्शाते हैं, जिससे सभी आउटपुट फ़ाइलों में सुसंगत विज़ुअल स्टाइल सुनिश्चित होती है।

#### स्टेप‑बाय‑स्टेप इम्प्लीमेंटेशन
##### आवश्यक पैकेज इम्पोर्ट करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### आउटपुट डायरेक्टरी और फ़ाइल‑पाथ फ़ॉर्मेट सेट करें
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### कस्टम रेंडरिंग विकल्पों के साथ Viewer इनिशियलाइज़ करें
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**पैरामीटर की व्याख्या**  
- `PngViewOptions` – PNG आउटपुट फ़ॉर्मेट और नामकरण पैटर्न को परिभाषित करता है।  
- `forRenderingByWidth(int width)` – रेंडरर को ऐसी इमेज बनाने के लिए मजबूर करता है जिसकी चौड़ाई प्रदान किए गए पिक्सेल मान से मेल खाती हो; ऊँचाई अनुपातिक रूप से स्केल होती है।  
- `setBackgroundColor(Color color)` – डिफ़ॉल्ट सफेद कैनवास को आपके चुने हुए रंग से ओवरराइट करता है, जिससे उत्पन्न एसेट्स में विज़ुअल कंसिस्टेंसी बेहतर होती है।

#### ट्रबलशूटिंग टिप्स
- सुनिश्चित करें कि आउटपुट फ़ोल्डर मौजूद है; यदि नहीं है तो `Files.createDirectories(outputDir)` का उपयोग करें।  
- इनपुट फ़ाइल पाथ सही है और एप्लिकेशन के पास पढ़ने की अनुमति है, यह सत्यापित करें।

## फ़ीचर 2: रेंडरिंग विकल्पों में बैकग्राउंड रंग सेट करना
### PNG बैकग्राउंड रंग कैसे सेट करें
PNG बैकग्राउंड रंग सेट करने में एक Color इंस्टेंस बनाना और रेंडरिंग से पहले इसे CadOptions को असाइन करना शामिल है। यह सुनिश्चित करता है कि प्रत्येक उत्पन्न PNG निर्दिष्ट बैकग्राउंड का उपयोग करे, जो आपके ब्रांड गाइडलाइन या UI थीम से मेल खाता हो। आप प्री‑डिफाइंड कॉन्स्टेंट्स का उपयोग कर सकते हैं या सटीक नियंत्रण के लिए कस्टम RGB मान परिभाषित कर सकते हैं।

java.awt.Color वह रंग मान दर्शाता है जिसका उपयोग बैकग्राउंड रेंडरिंग के लिए किया जाता है।

#### स्टेप‑बाय‑स्टेप इम्प्लीमेंटेशन
##### आवश्यक पैकेज इम्पोर्ट करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### बैकग्राउंड रंग के साथ रेंडरिंग विकल्प कॉन्फ़िगर करें
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**मुख्य कॉन्फ़िगरेशन विकल्प**  
- विभिन्न आयामों के लिए `forRenderingByWidth(int width)` को समायोजित करें, जैसे वेब थंबनेल के लिए 800 px या हाई‑रेज़ोल्यूशन प्रिंट के लिए 1920 px।  
- कोई भी प्री‑डिफाइंड `Color` कॉन्स्टेंट (जैसे `Color.LIGHT_GRAY`) उपयोग करें या सटीक ब्रांडिंग के लिए `new Color(r, g, b)` के साथ कस्टम इंस्टेंस बनाएं।

## व्यावहारिक अनुप्रयोग
### 1. इंजीनियरिंग दस्तावेज़ीकरण
कस्टम रेंडरिंग सुनिश्चित करता है कि प्रत्येक ड्रॉइंग कंपनी की स्टाइल गाइड का पालन करे, जिससे निर्यात के बाद मैन्युअल इमेज एडिटिंग समाप्त हो जाती है।

### 2. आर्किटेक्चरल विज़ुअलाइज़ेशन
ब्लूप्रिंट्स को ऐसे बैकग्राउंड के साथ प्रस्तुत करें जो स्लाइड डेक या क्लाइंट‑फेसिंग पोर्टल्स से मेल खाता हो, जिससे विज़ुअल कोहेज़न बेहतर हो।

### 3. मैन्युफैक्चरिंग प्रोटोटाइपिंग
PNG उत्पन्न करें तेज‑प्रोटोटाइप वर्कफ़्लो के लिए जहाँ डाउनस्ट्रीम टूल्स एक विशिष्ट इमेज आकार और बैकग्राउंड की अपेक्षा करते हैं।

### इंटीग्रेशन संभावनाएँ
इस रेंडरिंग पाइपलाइन को एक डॉक्यूमेंट‑मैनेजमेंट सिस्टम (जैसे SharePoint) के साथ जोड़ें ताकि जब भी कोई DWG फ़ाइल अपलोड हो, स्वचालित रूप से प्रीव्यू इमेज जेनरेट हो सके।

## परफ़ॉर्मेंस विचार
### परफ़ॉर्मेंस ऑप्टिमाइज़ करना
- **बैच प्रोसेसिंग:** DWG फ़ाइलों की डायरेक्टरी पर लूप चलाएँ और प्रत्येक को क्रमिक रूप से रेंडर करें ताकि JVM वार्म‑अप लागत को वितरित किया जा सके।  
- **रिसोर्स मैनेजमेंट:** बड़े ड्रॉइंग्स (500+ पेज) के लिए JVM हीप (`-Xmx2g`) बढ़ाएँ या मेमोरी त्रुटियों से बचने के लिए फ़ाइलों को छोटे बैच में प्रोसेस करें।

### रिसोर्स उपयोग दिशानिर्देश
CPU और मेमोरी उपयोग को VisualVM जैसे टूल्स से मॉनिटर करें; try‑with‑resources का उपयोग करके `Viewer` इंस्टेंस को तुरंत रिलीज़ करें।

### जावा मेमोरी मैनेजमेंट के लिए बेस्ट प्रैक्टिसेज
- try‑with‑resources (जैसा दिखाया गया है) का उपयोग करके `Viewer` को ऑटो‑क्लोज़ करें।  
- बड़े `Path` ऑब्जेक्ट्स को उनके तत्काल उपयोग के बाद रखे नहीं रखें।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| आउटपुट फ़ोल्डर नहीं मिला | डायरेक्टरी पहले से बनाएं या `Files.createDirectories(outputDirectory);` जोड़ें |
| खाली इमेज | `cadOptions.setBackgroundColor` को `forRenderingByWidth` के बाद कॉल किया गया है, यह सुनिश्चित करें। |
| आउट‑ऑफ़‑मेमोरी त्रुटियाँ | `-Xmx` JVM विकल्प बढ़ाएँ या फ़ाइलों को छोटे बैच में प्रोसेस करें। |

## अक्सर पूछे जाने वाले प्रश्न
**Q: क्या मैं DWG के अलावा अन्य CAD फ़ॉर्मेट रेंडर कर सकता हूँ?**  
A: हाँ, GroupDocs.Viewer DXF, DWF, और कई अतिरिक्त CAD फ़ॉर्मेट को सपोर्ट करता है।

**Q: प्री‑डिफाइंड कॉन्स्टेंट के बजाय कस्टम RGB रंग कैसे उपयोग करूँ?**  
A: `new Color(123, 45, 67)` के साथ एक नया `Color` इंस्टेंस बनाएं और इसे `setBackgroundColor` को पास करें।

**Q: क्या केवल एक विशिष्ट लेआउट या लेयर को रेंडर करना संभव है?**  
A: आप `viewer.view` कॉल करने से पहले `CadOptions` के माध्यम से लेआउट या लेयर विकल्प निर्दिष्ट कर सकते हैं।

**Q: क्या लाइब्रेरी ट्रांसपेरेंट बैकग्राउंड सपोर्ट करती है?**  
A: यदि आउटपुट फ़ॉर्मेट सपोर्ट करता है तो पूर्ण ट्रांसपेरेंसी के लिए बैकग्राउंड रंग को `new Color(0,0,0,0)` सेट करें।

**Q: कौन सा GroupDocs.Viewer संस्करण आवश्यक है?**  
A: इस ट्यूटोरियल में संस्करण 25.2 का उपयोग किया गया है, लेकिन नए रिलीज़ समान API सतह को बनाए रखते हैं।

---

**अंतिम अपडेट:** 2026-08-30  
**परीक्षण किया गया:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs

## संबंधित ट्यूटोरियल
- [groupdocs viewer dwg – जावा में GroupDocs.Viewer का उपयोग करके विशिष्ट CAD ड्रॉइंग्स कैसे रेंडर करें](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [GroupDocs.Viewer के साथ जावा में CAD लेयर्स रेंडर करें – एक पूर्ण गाइड](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [जावा में GroupDocs.Viewer के साथ PDF को HTML में कैसे बदलें और इमेज क्वालिटी ऑप्टिमाइज़ करें](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)