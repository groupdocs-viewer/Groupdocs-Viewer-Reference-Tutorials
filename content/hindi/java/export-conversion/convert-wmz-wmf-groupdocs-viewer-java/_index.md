---
date: '2026-02-18'
description: GroupDocs Viewer for Java का उपयोग करके WMZ और WMF फ़ाइलों को PDF, HTML,
  JPG और PNG में कैसे परिवर्तित करें, सीखें। यह गाइड GroupDocs Viewer Java और Java
  में वेक्टर ग्राफ़िक्स को कनवर्ट करने को कवर करता है।
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: GroupDocs Viewer for Java का उपयोग करके WMZ को PDF और अन्य फ़ॉर्मैट में कैसे
  परिवर्तित करें
type: docs
url: /hi/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer for Java का उपयोग करके WMZ को PDF और अन्य फ़ॉर्मैट में कैसे बदलें

WMZ (Web Metafile) और WMF (Windows Metafile) फ़ाइलों को अधिक सुलभ फ़ॉर्मैट में बदलना—विशेषकर **convert WMZ to PDF**—कठिन हो सकता है क्योंकि ये वेक्टर ग्राफ़िक फ़ॉर्मैट ड्रॉइंग निर्देशों को स्टोर करते हैं, न कि पिक्सेल डेटा। **GroupDocs Viewer for Java** के साथ, आप WMZ/WMF दस्तावेज़ों को HTML, JPG, PNG, **PDF**, और अन्य लोकप्रिय फ़ॉर्मैट में केवल कुछ लाइनों के कोड से रेंडर कर सकते हैं।

![GroupDocs.Viewer for Java के साथ WMZ/WMF दस्तावेज़ों को बदलें](/viewer/export-conversion/convert-wmz-wmf-documents.png)

इस ट्यूटोरियल में आप सीखेंगे कि लाइब्रेरी को कैसे सेटअप करें, WMZ/WMF फ़ाइलों को इच्छित आउटपुट में रेंडर करें, और सामान्य समस्याओं को कैसे संभालें। अंत तक, आप **groupdocs viewer java** को अपने Java एप्लिकेशन में एकीकृत करके **java convert vector graphics** को तेज़ और विश्वसनीय तरीके से कर सकेंगे।

## त्वरित उत्तर
- **WMZ/WMF को किन फ़ॉर्मैट में बदला जा सकता है?** HTML, JPG, PNG, और PDF पूरी तरह समर्थित हैं।  
- **क्या विकास के लिए लाइसेंस चाहिए?** परीक्षण के लिए एक मुफ्त ट्रायल काम करता है; एक वाणिज्यिक लाइसेंस मूल्यांकन सीमाओं को हटा देता है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उसके बाद का संस्करण अनुशंसित है।  
- **क्या मैं केवल विशिष्ट पृष्ठों को रेंडर कर सकता हूँ?** हाँ, आप view options में पृष्ठ रेंज निर्दिष्ट कर सकते हैं।  
- **क्या बड़े फ़ाइलों के लिए मेमोरी उपयोग चिंता का विषय है?** मेमोरी को कम रखने के लिए try‑with‑resources का उपयोग करें और केवल आवश्यक पृष्ठों को रेंडर करें।

## “convert WMZ to PDF” क्या है?
WMZ को PDF में बदलना मतलब वेक्टर‑आधारित WMZ फ़ाइल को PDF कंटेनर के अंदर रास्टराइज़ करना (या उसके वेक्टर डेटा को संरक्षित करना) है। PDF सार्वभौमिक रूप से देखी जा सकती है, खोजी जा सकती है, और प्रिंट की जा सकती है, जिससे यह WMZ ग्राफ़िक्स को संग्रहित करने और साझा करने के लिए आदर्श बनती है।

## वेक्टर ग्राफ़िक्स को बदलने के लिए GroupDocs Viewer for Java का उपयोग क्यों करें?
- **उच्च सटीकता**: लाइब्रेरी मूल ड्रॉइंग गुणवत्ता को संरक्षित करती है, चाहे आप PDF या PNG में आउटपुट करें।  
- **शून्य बाहरी निर्भरताएँ**: मूल Windows लाइब्रेरी की आवश्यकता नहीं; सब कुछ JDK वाले किसी भी प्लेटफ़ॉर्म पर चलता है।  
- **सरल API**: एक `Viewer` इंस्टेंस और एकल `view` कॉल पूरी परिवर्तन प्रक्रिया को संभालते हैं।  
- **स्केलेबल**: यह सिंगल‑पेज आइकॉन और मल्टी‑पेज तकनीकी ड्रॉइंग दोनों के लिए समान रूप से काम करता है।

## पूर्वापेक्षाएँ

### आवश्यक लाइब्रेरीज़
- **GroupDocs.Viewer for Java** – मुख्य रेंडरिंग इंजन।  
- Java Development Kit (JDK) 8+।

### पर्यावरण सेटअप
- IntelliJ IDEA या Eclipse जैसे IDE।  
- निर्भरता प्रबंधन के लिए Maven (या यदि आप चाहें तो Gradle)।

### ज्ञान पूर्वापेक्षाएँ
- Java फ़ाइल I/O (`java.nio.file.Path`) से परिचित होना।  
- दस्तावेज़ व्यूअर्स कैसे कंटेंट रेंडर करते हैं, इसका बुनियादी समझ।

## GroupDocs.Viewer for Java सेटअप करना

`pom.xml` में रिपॉज़िटरी और निर्भरता जोड़ें:

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

> **लाइसेंस टिप:** मूल्यांकन के लिए एक मुफ्त ट्रायल उपयोग करें, फिर पूर्ण कार्यक्षमता अनलॉक करने के लिए एक अस्थायी या खरीदा हुआ लाइसेंस लागू करें।

एक बार निर्भरता हल हो जाने पर, आप एक `Viewer` इंस्टेंस बना सकते हैं जिसे प्रत्येक परिवर्तन चरण के लिए पुन: उपयोग किया जाएगा।

## कार्यान्वयन गाइड

हम चार परिवर्तन परिदृश्यों को देखेंगे: HTML, JPG, PNG, और PDF। प्रत्येक उदाहरण समान पैटर्न का अनुसरण करता है—एक आउटपुट पाथ परिभाषित करें, स्रोत WMZ फ़ाइल के साथ `Viewer` को इंस्टैंशिएट करें, उपयुक्त view options कॉन्फ़िगर करें, और `view` को कॉल करें।

### WMZ/WMF को HTML में रेंडर करना

#### अवलोकन
HTML आउटपुट आपको ग्राफ़िक को सीधे वेब पेजों में एम्बेड करने देता है, सभी संसाधन (इमेज, CSS) एक ही फ़ाइल में सम्मिलित होते हैं।

**चरण 1: आउटपुट डायरेक्टरी पाथ परिभाषित करें**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**चरण 2: Viewer को इनिशियलाइज़ करें और HTML में रेंडर करें**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### WMZ/WMF को JPG में रेंडर करना

#### अवलोकन
JPG एक व्यापक रूप से समर्थित रास्टर फ़ॉर्मैट है, त्वरित प्रीव्यू या ईमेल अटैचमेंट के लिए उपयुक्त।

**चरण 1: आउटपुट डायरेक्टरी पाथ परिभाषित करें**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**चरण 2: Viewer को इनिशियलाइज़ करें और JPG में रेंडर करें**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF को PNG में रेंडर करना

#### अवलोकन
PNG पारदर्शिता का समर्थन करता है, जिससे यह विभिन्न बैकग्राउंड के साथ मिलाने वाली ग्राफ़िक्स के लिए आदर्श बनता है।

**चरण 1: आउटपुट डायरेक्टरी पाथ परिभाषित करें**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**चरण 2: Viewer को इनिशियलाइज़ करें और PNG में रेंडर करें**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### WMZ/WMF को PDF में रेंडर करना

#### अवलोकन
PDF एक प्लेटफ़ॉर्म‑स्वतंत्र, खोज योग्य दस्तावेज़ प्रदान करता है जो मूल लेआउट को बनाए रखता है।

**चरण 1: आउटपुट डायरेक्टरी पाथ परिभाषित करें**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**चरण 2: Viewer को इनिशियलाइज़ करें और PDF में रेंडर करें**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## सामान्य समस्याएँ और समाधान

| समस्या | कारण | समाधान |
|-------|-------|----------|
| **OutOfMemoryError** बड़े WMZ फ़ाइलों पर | Viewer पूरे दस्तावेज़ को मेमोरी में लोड करता है | `PageStreamViewOptions` का उपयोग करके एक बार में एक पृष्ठ रेंडर करें या JVM हीप (`-Xmx`) बढ़ाएँ। |
| **Missing fonts** PDF में | फ़ॉन्ट स्रोत WMZ में एम्बेड नहीं है | होस्ट मशीन पर आवश्यक फ़ॉन्ट स्थापित करें या कस्टम फ़ॉन्ट प्रदान करने के लिए `FontSettings` का उपयोग करें। |
| **Blank PNG आउटपुट** | गलत आउटपुट पाथ या अपर्याप्त लिखने की अनुमति | `outputDirectory` मौजूद है और एप्लिकेशन को लिखने की अनुमति है, यह सत्यापित करें। |
| **HTML संसाधन लोड नहीं हो रहे हैं** | `forExternalResources` का उपयोग फ़ाइलें कॉपी किए बिना किया गया | स्वयं‑समाहित HTML फ़ाइल के लिए `forEmbeddedResources` का उपयोग करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं वही कोड उपयोग करके WMF को PNG में बदल सकता हूँ?**  
**उत्तर:** हाँ। PNG उदाहरण WMZ और WMF दोनों फ़ाइलों के लिए काम करता है; बस `TestFiles.SAMPLE_WMZ` को अपने WMF स्रोत से बदल दें।

**प्रश्न: क्या केवल पृष्ठों का एक उपसमुच्चय बदलना संभव है?**  
**उत्तर:** बिल्कुल। रेंडर करने से पहले `PdfViewOptions` (या अन्य फ़ॉर्मैट के लिए संबंधित विकल्प) का उपयोग करें और `setPageNumbers(List<Integer>)` कॉल करें।

**प्रश्न: क्या प्रत्येक आउटपुट फ़ॉर्मैट के लिए अलग लाइसेंस चाहिए?**  
**उत्तर:** नहीं। एक ही GroupDocs Viewer लाइसेंस सभी समर्थित फ़ॉर्मैट, जिसमें HTML, JPG, PNG, और PDF शामिल हैं, को कवर करता है।

**प्रश्न: “java convert vector graphics” प्रदर्शन को कैसे प्रभावित करता है?**  
**उत्तर:** वेक्टर‑से‑रास्टर परिवर्तन CPU‑गहन है। बड़े बैचों के लिए, मल्टी‑थ्रेडिंग और फ़ाइलों के बीच एक ही `Viewer` इंस्टेंस को पुन: उपयोग करने पर विचार करें।

**प्रश्न: क्या PDF वेक्टर गुणवत्ता को बनाए रखेगा, या यह रास्टराइज़ हो जाएगा?**  
**उत्तर:** WMZ/WMF को PDF में बदलते समय, GroupDocs Viewer जहाँ संभव हो वेक्टर निर्देशों को संरक्षित करता है, जिससे एक स्केलेबल PDF प्राप्त होता है।

## निष्कर्ष

अब आपके पास **convert WMZ to PDF** और अन्य सामान्य फ़ॉर्मैट को **GroupDocs Viewer for Java** का उपयोग करके बदलने के लिए एक पूर्ण, प्रोडक्शन‑रेडी गाइड है। चाहे आप एक वेब सेवा बना रहे हों जो ग्राफ़िक्स को ऑन‑द‑फ्लाई सर्व करती हो या एक आर्काइव टूल जो दस्तावेज़ों को PDF के रूप में संग्रहीत करता हो, ऊपर दिए गए चरण आपको जल्दी से लक्ष्य तक पहुँचने में मदद करेंगे।

---

**अंतिम अपडेट:** 2026-02-18  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs