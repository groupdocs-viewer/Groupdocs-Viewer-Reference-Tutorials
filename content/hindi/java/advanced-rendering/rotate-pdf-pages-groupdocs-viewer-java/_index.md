---
date: '2026-04-04'
description: GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को घुमाना सीखें।
  यह चरण‑दर‑चरण गाइड Maven सेटअप, PDF को 90 डिग्री घुमाना, और समस्या निवारण को कवर
  करता है।
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
title: GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को कैसे घुमाएँ
type: docs
url: /hi/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को कैसे घुमाएँ

PDF के भीतर विशिष्ट पृष्ठों को घुमाना दस्तावेज़ों को संरेखित करने, स्कैन की गई छवियों को ठीक करने, या प्रस्तुति स्लाइड्स को समायोजित करने के लिए आवश्यक हो सकता है। **इस गाइड में आप सीखेंगे कि GroupDocs.Viewer के साथ प्रोग्रामेटिकली विशिष्ट pdf पृष्ठों को कैसे घुमाएँ**, चाहे आपको pdf को 90 डिग्री घुमाना हो, पूरी सेक्शन को उलटना हो, या एक ही कॉल में कई पृष्ठों को संभालना हो।

![GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को घुमाएँ](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**आप क्या सीखेंगे**
- अपने Java प्रोजेक्ट में GroupDocs.Viewer सेटअप करना (Maven GroupDocs Viewer कॉन्फ़िगरेशन सहित)
- प्रोग्रामेटिकली विशिष्ट PDF पृष्ठों को घुमाना (pdf को 90 डिग्री, 180 डिग्री आदि घुमाएँ)
- सर्वोत्तम उपयोग के लिए प्रमुख कॉन्फ़िगरेशन
- कार्यान्वयन के दौरान सामान्य समस्याओं का निवारण

## त्वरित उत्तर
- **Java में PDF पृष्ठों को घुमाने वाली लाइब्रेरी कौन सी है?** GroupDocs.Viewer for Java.  
- **क्या मैं एक पृष्ठ को 90 डिग्री घुमा सकता हूँ?** हाँ, `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` का उपयोग करें।  
- **क्या विकास के लिए लाइसेंस चाहिए?** एक अस्थायी लाइसेंस मुफ्त ट्रायल के लिए उपलब्ध है।  
- **क्या Maven आवश्यक है?** Maven GroupDocs निर्भरताओं को प्रबंधित करने का अनुशंसित तरीका है।  
- **घुमाए गए पृष्ठों को कैसे रेंडर करें?** `HtmlViewOptions` का उपयोग करें और `viewer.view(...)` को कॉल करें।

## आवश्यकताएँ

### आवश्यक लाइब्रेरी और निर्भरताएँ
- Java Development Kit (JDK) 8 या बाद का।  
- IntelliJ IDEA या Eclipse जैसे IDE।  
- निर्भरताओं के प्रबंधन के लिए Maven।

### पर्यावरण सेटअप आवश्यकताएँ
1. **Maven कॉन्फ़िगरेशन** – अपने `pom.xml` में GroupDocs.Viewer जोड़ें।  
2. **लाइसेंस प्राप्ति** – GroupDocs से अस्थायी लाइसेंस प्राप्त करें। [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) देखें या [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) पर अस्थायी लाइसेंस के लिए आवेदन करें।

## Java के लिए GroupDocs.Viewer सेटअप करना

Maven का उपयोग करके अपने Java प्रोजेक्ट में GroupDocs.Viewer को एकीकृत करने के लिए, अपने `pom.xml` को अपडेट करें:

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

### बेसिक इनिशियलाइज़ेशन और सेटअप
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## GroupDocs.Viewer के साथ विशिष्ट PDF पृष्ठों को कैसे घुमाएँ
### सारांश
विशिष्ट PDF पृष्ठों को घुमाने से आप मूल फ़ाइल को बदले बिना दस्तावेज़ प्रस्तुति पर सूक्ष्म नियंत्रण प्राप्त करते हैं।

### चरण 1: पृष्ठ घुमाव कॉन्फ़िगर करें
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### चरण 2: Viewer को इनिशियलाइज़ करें और रेंडर करें
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### पैरामीटर और कॉन्फ़िगरेशन
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` जहाँ घुमाव विकल्प `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE` हैं।  
- **HtmlViewOptions** – लेआउट और एम्बेडेड रिसोर्सेज़ को संरक्षित रखते हुए PDF‑to‑HTML रूपांतरण को संभालता है।  
- **pdf to html java** – यह क्लास उसी API का हिस्सा है और एक सटीक विज़ुअल प्रतिनिधित्व सुनिश्चित करता है।

## विशिष्ट PDF पृष्ठों को क्यों घुमाएँ?
- **Document Alignment** – स्कैन किए गए अनुबंधों या चालानों की सही दिशा।  
- **Presentation Tweaks** – PDF के रूप में निर्यात किए गए स्लाइड्स को समायोजित करें।  
- **Archival Consistency** – बड़े पैमाने पर डिजिटलीकरण के दौरान पृष्ठ दिशा को मानकीकृत करें।

## सामान्य समस्याएँ और समाधान (pdf घुमाव का निवारण)

- **Incorrect Paths** – सुनिश्चित करें कि `YOUR_DOCUMENT_DIRECTORY` और `YOUR_OUTPUT_DIRECTORY` मौजूद हैं और पहुँच योग्य हैं।  
- **Missing Dependencies** – सुनिश्चित करें कि Maven कोऑर्डिनेट्स नवीनतम GroupDocs.Viewer संस्करण से मेल खाते हैं।  
- **License Restrictions** – अस्थायी लाइसेंस को सही ढंग से लागू करें; अन्यथा कुछ फीचर अक्षम हो सकते हैं।  
- **Memory Spikes** – बड़े PDFs को छोटे बैच में रेंडर करें या JVM हीप साइज बढ़ाएँ।

## व्यावहारिक अनुप्रयोग

### वास्तविक‑दुनिया उपयोग केस
1. **Document Alignment** – स्कैन किए गए दस्तावेज़ों को सही डिजिटल दिशा के लिए घुमाएँ।  
2. **Presentation Adjustments** – साझा करने से पहले PDFs के भीतर प्रस्तुति स्लाइड्स को संशोधित करें।  
3. **Archival Workflows** – डिजिटलीकरण के दौरान ऐतिहासिक दस्तावेज़ों की दिशा को स्वचालित रूप से समायोजित करें।

### एकीकरण संभावनाएँ
GroupDocs.Viewer को Java‑आधारित कंटेंट मैनेजमेंट सिस्टम, एंटरप्राइज़ पोर्टल, या कस्टम APIs के साथ मिलाएँ जो PDFs को ऑन‑द‑फ्लाई देखने की आवश्यकता रखते हैं।

## प्रदर्शन विचार
- **Resource Management** – फ़ाइल हैंडल और मेमोरी रिलीज़ करने के लिए हमेशा `Viewer` इंस्टेंस को बंद करें।  
- **Java Memory Management** – बड़े PDFs को प्रोसेस करते समय हीप उपयोग की निगरानी करें; पूरे फ़ाइल को लोड करने के बजाय पृष्ठों को स्ट्रीम करने पर विचार करें।  
- **Best Practices** – अक्सर एक्सेस किए जाने वाले दस्तावेज़ों के लिए रेंडर किया गया HTML कैश करें ताकि प्रोसेसिंग समय कम हो।

## निष्कर्ष
इस ट्यूटोरियल में **Java में GroupDocs.Viewer का उपयोग करके विशिष्ट pdf पृष्ठों को कैसे घुमाएँ** को Maven सेटअप से लेकर घुमाए गए पृष्ठों को रेंडर करने और सामान्य समस्याओं को संभालने तक कवर किया गया है। वॉटरमार्किंग, फ़ॉर्मेट रूपांतरण, या बैच प्रोसेसिंग जैसे अतिरिक्त फीचर के साथ प्रयोग करें ताकि अपने दस्तावेज़ वर्कफ़्लो को और विस्तारित किया जा सके।

**अगले कदम:** PDFs को PNG में बदलने, वॉटरमार्क जोड़ने, या क्लाउड स्टोरेज प्रोवाइडर्स के साथ एकीकृत करने जैसी अन्य GroupDocs.Viewer क्षमताओं में डुबकी लगाएँ।

## FAQ Section
- **Troubleshooting Rotation Issues** – पृष्ठ संख्याएँ और घुमाव पैरामीटर सही हैं यह सत्यापित करें।  
- **Handling Large PDF Files** – पृष्ठों को बैच में प्रोसेस करें और मेमोरी उपयोग की निगरानी करें।  
- **Licensing Requirements** – विकास के लिए अस्थायी लाइसेंस उपयोग करें; प्रोडक्शन के लिए पूर्ण लाइसेंस खरीदें।  
- **Rotating Multiple Pages** – विभिन्न पृष्ठ संख्याओं और कोणों के साथ `rotatePage` को बार‑बार कॉल करें।  
- **Integration with Java Libraries** – GroupDocs.Viewer Spring Boot, Jakarta EE, और अन्य Java फ्रेमवर्क के साथ सहजता से काम करता है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक साथ PDF के सभी पृष्ठों को घुमा सकता हूँ?**  
A: हाँ। पृष्ठ संख्याओं के माध्यम से लूप करें और प्रत्येक पृष्ठ के लिए `rotatePage(page, Rotation.ON_90_DEGREE)` को कॉल करें।

**Q: क्या घुमाव मूल PDF फ़ाइल को प्रभावित करता है?**  
A: नहीं। घुमाव केवल रेंडरिंग प्रक्रिया के दौरान लागू होता है; स्रोत PDF अपरिवर्तित रहता है।

**Q: यदि PDF पासवर्ड‑सुरक्षित है तो क्या करें?**  
A: `Viewer` इंस्टेंस बनाते समय पासवर्ड प्रदान करें: `new Viewer(path, password)`।

**Q: HtmlViewOptions सेटअप करते समय “null pointer” त्रुटि को कैसे डिबग करें?**  
A: सुनिश्चित करें कि आउटपुट डायरेक्टरी मौजूद है और `pageFilePathFormat` सही ढंग से रिज़ॉल्व हो रहा है।

**Q: क्या अन्य फ़ॉर्मेट (जैसे PNG) में रूपांतरण करते समय पृष्ठों को घुमाने का तरीका है?**  
A: हाँ। लक्ष्य फ़ॉर्मेट के लिए उपयुक्त व्यू ऑप्शन्स के साथ वही `rotatePage` कॉन्फ़िगरेशन उपयोग करें।

## संसाधन
- **दस्तावेज़ीकरण**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **डाउनलोड**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **खरीद**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **फ्री ट्रायल**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **अस्थायी लाइसेंस**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **समर्थन**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-04-04  
**परीक्षण किया गया:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs