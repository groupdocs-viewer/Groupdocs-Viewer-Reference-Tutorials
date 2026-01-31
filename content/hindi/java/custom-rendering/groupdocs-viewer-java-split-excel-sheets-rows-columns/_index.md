---
date: '2026-01-31'
description: जावा में GroupDocs Viewer का उपयोग करके पंक्तियों और स्तंभों द्वारा Excel
  शीट्स को विभाजित करना सीखें। यह चरण-दर-चरण गाइड सेटअप, कोड और सर्वोत्तम प्रथाओं
  को कवर करता है।
keywords:
- split Excel sheets Java
- GroupDocs Viewer Java tutorial
- manageable data segments
title: कैसे एक्सेल शीट्स को पंक्तियों और स्तंभों द्वारा विभाजित करें (जावा)
type: docs
url: /hi/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Excel शीट्स को पंक्तियों और कॉलमों द्वारा विभाजित कैसे करें (Java)

बड़े Excel वर्कबुक या प्रिंट पेज पर आराम से दिखाया नहीं जा सकता। **How to split Excel** शी, पढ़ने योग्य भागों में विभाजित करने से केवल हो जाता है। इस गाइड में हम आपको **how to split worksheet** डेटा को पंक्तियों और कॉलमों द्वारा करके विभाजित करना दिखाएंगे, साथ ही Java में Excel रिपोर्ट जनरेट करने और Excel को HTML के रूप में रेंडर करने पर भी चर्चा करेंगे।

![Excel शीट्स को पंक्तियों और कॉलमों द्वारा विभाजित करें GroupDocs.Viewer for Java के साथ](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## त्वरित उत्तर
- **क्या लाइ  
- **क्या मैं प विभाजित कर सकता हूँ?** हाँ – आप rows‑per‑page और columns‑per‑page को साथ में परिभाषित कर सकते हैं।  
- **क्या लाइसेंस की आवश्यकता है?** विकास के लिए ट्रायल या टेम्पररी लाइसेंस काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन से आउटपुट फॉर्मेट समर्थित हैं?** HTML (एम्बेडेड रिसोर्सेज) दिखाया गया है; वही विकल्पों के साथ PDF भी जनरेट किया जा सकता है।  
- **क्या Maven आवश्यक है?** Maven निर्भरताओं को प्रबंधित करने का अनुशंसित तरीका है।

## “How to Split Excel” क्या है?
र्कशीट को निश्चित संख्या में पंक्तियों, कॉलमों या दोनों के आधार पर कई पेजों या फाइलों में बाँटना। यह तकनीक तब उपयोगी होती है जब आपको पेजिनेटेड रिपोर्ट बनानी हो, वेब पेज में डेटा एम्बेड करना हो, या पूरे वर्कबुक को एक बार लोड किए बिना प्रिंटेबल सेक्शन जनरेट करने हों।

## GroupDocs Viewer for Java क्यों उपयोग करें?
- **तेज़ रेंडरिंग** – XLSX, XLS, CSV और अन्य फॉर्मेट्स के लिए नेटिव सपोर्ट।  
- **इन‑बिल्ट पेजिनेशन** – मैन्युअल गणना की आवश्यकता नहीं।  
- **HTML या PDF आउटपुट** – वेब एप्लिकेशन या ऑफ़लाइन रिपोर्ट के लिए परफेक्ट।  
- **क्रॉस‑प्लेटफ़त पर्यावरण में काम करता है।

## पूर्वापेक्ष स्थापित हो।  
- IntelliJ IDEA या Eclipse जैसे IDE।  
- निर्भ Java ज्ञान और Excel फ़ाइल हैंडलिंग की परिचितता।

### आवश्यक लाइब्रेरीज़, संस्करण और निर्भरताएँ
अपने `pom.xml` में GroupDocs रिपॉज़िटरी और व्यूअर निर्भरता जोड़ें:

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

### लाइसेंस प्राप्त करना
[GroupDocs](https://purchase.groupdocs.com/buy) से एक मुफ्त ट्रायल, टेम्पररी लाइसेंस या पूर्ण लाइसेंस खरीदें।

## Excel शीट्स को पंक्तियों द्वारा विभाजित कैसे करें

### अवलोकन
पंक्तियों द्वारा विभाजन आपको एक श्रृंखला के HTML पेज बनाने की अनुमति देता है, जहाँ प्रत्येक पेज में निश्चित संख्या में पंबोर्ड के लिए आदर्श है जो प्रति चरण 1: पाथ सेट करें और व्यूअर को इनिशियलाइज़ करें
सबसे पहले, यह निर्धारित करें कि विभाजित पेज कहाँ सहेजे जाएंगे और स्रोत वर्कबुक के लिए एक `Viewer` इंस्टेंस बनाएं।

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### चरण 2: प्रति पेज पंक्तियों की संख्या कॉन्फ़िगर करें
व्यूअर को बताएं कि प्रत्येक पेज में कितनी पंक्तियाँ होनी चाहिए।

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### चरण 3: दस्तावेज़ रेंडर करें
अंत में, आपने जो विकल्प निर्धारित किए हैं, उनका उपयोग करके वर्कबुक को रेंडर करें।

```java
viewer.view(viewOptions);
```

## Excel शीट्स को पंक्तियों और कॉलमों द्वारा विभाजित कैसे करें

### अवलोकन
कभी‑कभी एक ही पेज में पंक्तियों **और** कॉलमों (जैसे, 15 पंक्तियाँ × 7 कॉलम) का मैट्रिक्स दिखाना आवश्यक होता है। यह प्रत्येक HTML पेज के लेआउट पर पूर्ण नियंत्रण देता है।

### चरण‑दर‑चरण कार्यान्वयन

#### चरण 1: पाथ सेट करें और व्यूअर को इनिशियलाइज़ियों‑केवल उदाहरण के समान है, केवल फ़ाइल नाम बदलता है।

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### चरण 2 करें
ग्रिड‑स्टाइल विभाजन बनाने के लिए दोनों आयाम निर्दिष्ट करें।

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### चरण 3: दस्तावेज़ रेंडर करें
उसी `view` कॉल का उपयोग करके रेंडर करें।

```java
viewer.view(options);
```

## व्यावहारिक अनुप्रयोग
- **Generate Excel report Java**: बड़े वित्तीय मॉडल को पेजिनेटेड HTML रिपोर्टों की श्रृंखला में बदलें।  
- **GroupDocs Viewer Excel**: विभाजित पेजों को सीधे वेब पोर्टल में एम्बेड करके इंटरैक्टिव डेटा एक्सप्लोरेशन प्रदान करें।  
- **Render Excel HTML Java**: तेज़ क्लाइंट करें।  

## प्रदर्शन संबंधी विचार
- **मेमोरी उपयोग** – बड़े वर्कबुक काफी हीप उपयोग कर सकते हैं; JVM `-Xmx` सेटिंग बढ़ाने पर विचार करें।  
- **चंक आकार** – पेज आकार और रेंडरिंग गति के बीच संतुलन बनाने के लिए पंक्तियों/कॉलमों की संख्या Viewer को अद्यतित रखें।

## सामान्य समस्याएँ और ट्रबलशूटिंग
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| `OutOfMemoryError` | बहुत बड़ीियों प्रति पेज के साथ रेंडर करनााएँ |
| खाली आउटपुट फ़ाइलें | फ़ाइल पाथ गलत या लिखने की अनुमति नहीं है | ` `forEmbeddedResources` का उपयोग किया गया लेकिन फ़ाइलें अलग बेस URL से सर्व की जा रही हैं |िच करें |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं HTML के बजाय PDF जनरेट कर सकता हूँ?**  
उत्तर: हाँ। `HtmlViewOptions` को `PdfViewOptions` से बदलें और वही `SpreadsheetOptions` कॉन्फ़िगरेशन रखें।

**प्रश्न: क्या स्थिर पंक्तियों/कॉलमों के बजाय सेल कंटेंट के आधार पर विभाजन संभव है?**  
उत्तर: कंटेंट‑आधारित विभाजन GroupDocs Viewer में बिल्ट‑इन नहीं है, लेकिन आप Apache POI के साथ वर्कबुक को प्री‑प्रोसेस करके अलग-अलग शीट बना सकते हैं, फिर रेंडर करें।

**प्रश्न: क्या GroupDocs Viewer पुराने Excel फॉर्मेट (XLS) को सपोर्ट करता है?**  
उत्तर: बिल्कुल। व्यूअर XLS, XLSX, CSV और अन्य स्प्रेडशीट फॉर्मेट को संभालता है।

**प्रश्न: मैं जनरेटेड HTML को Spring MVC व्यू में कैसे एम्बेड करूँ?**  
उत्तर: आउटपुट फ़ोल्डर को स्ट से `page_0.html`, `page_1.html` आदि को रेफ़रेंस करें।

**प्रश्न: व्यावसायिक डिप्लॉयमेंट के लिए मुझे कौन सा लाइसेंस चाहिए?**  
उत्तर: उत्पादन के लिए GroupDocs का पूर्ण प्रोडक्शन लाइसेंस आवश्यक है; ट्रायल लाइसेंस केवल मूल्यांकन के लिए है।

## संसाधन
- **डॉक्यूमेंटेशन**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API रेफ़रेंस**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **डाउनलोड**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)  
- **खरीदें**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)  
- **फ़्री ट्रायल**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **टेम्पररी लाइसेंस**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **सपोर्ट**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-01-31  
**टेस्टेड विथ:** GroupDocs Viewer 25.2 for Java  
**लेखक:** GroupDocs