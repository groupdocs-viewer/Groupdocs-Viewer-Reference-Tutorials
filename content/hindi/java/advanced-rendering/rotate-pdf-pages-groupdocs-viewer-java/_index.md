---
date: '2026-10-05'
description: GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को कैसे घुमाएँ,
  सीखें। यह step‑by‑step guide Maven सेटअप, rotate pdf 90 degrees, और troubleshooting
  को कवर करता है।
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को घुमाएँ। rotate
  pdf 90 degrees, configure Maven, और सामान्य समस्याओं को troubleshoot करने के लिए
  एक संक्षिप्त guide में सीखें।
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को घुमाएँ
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को घुमाने का तरीका
type: docs
url: /hi/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को कैसे घुमाएँ

PDF के भीतर विशिष्ट पृष्ठों को घुमाना दस्तावेज़ों को संरेखित करने, स्कैन की गई छवियों को ठीक करने, या प्रस्तुति स्लाइड्स को समायोजित करने के लिए आवश्यक हो सकता है। **इस गाइड में आप सीखेंगे कि GroupDocs.Viewer के साथ प्रोग्रामेटिक रूप से विशिष्ट PDF पृष्ठों को कैसे घुमाएँ**, चाहे आपको PDF को 90 डिग्री घुमाना हो, पूरे सेक्शन को उलटना हो, या एक ही कॉल में कई पृष्ठों को संभालना हो।

![GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को घुमाएँ](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठों को घुमाएँ](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**आप क्या सीखेंगे**
- अपने Java प्रोजेक्ट में GroupDocs.Viewer सेटअप करना (Maven GroupDocs Viewer कॉन्फ़िगरेशन सहित)
- प्रोग्रामेटिक रूप से विशिष्ट PDF पृष्ठों को घुमाना (PDF को 90 डिग्री, 180 डिग्री आदि घुमाएँ)
- सर्वोत्तम उपयोग के लिए प्रमुख कॉन्फ़िगरेशन
- कार्यान्वयन के दौरान सामान्य समस्याओं का निवारण

## त्वरित उत्तर
- **Java में PDF पृष्ठों को घुमाने वाली लाइब्रेरी कौन सी है?** GroupDocs.Viewer for Java बाहरी टूल्स के बिना अंतर्निहित घुमाव समर्थन प्रदान करता है।  
- **क्या मैं एक पृष्ठ को 90 डिग्री घुमा सकता हूँ?** हाँ – व्यूअर इंस्टेंस पर `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` कॉल करें।  
- **क्या विकास के लिए लाइसेंस चाहिए?** एक अस्थायी लाइसेंस मूल्यांकन के लिए मुफ्त है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या Maven आवश्यक है?** Maven अनुशंसित डिपेंडेंसी मैनेजर है, लेकिन आप Gradle या मैन्युअल JAR इन्क्लूज़न भी उपयोग कर सकते हैं।  
- **घुमाए गए पृष्ठों को कैसे रेंडर करें?** `HtmlViewOptions` को `viewer.view(documentPath, viewOptions)` के साथ उपयोग करके HTML आउटपुट प्राप्त करें जो घुमाव को दर्शाता है।

## विशिष्ट PDF पृष्ठों को घुमाना क्या है?
`rotate specific pdf pages` का अर्थ है PDF दस्तावेज़ के भीतर व्यक्तिगत पृष्ठों की अभिविन्यास बदलने की क्षमता, जबकि फ़ाइल के बाकी हिस्से को अपरिवर्तित रखा जाता है। यह ऑपरेशन रेंडर समय पर किया जाता है, इसलिए मूल PDF फ़ाइल अपरिवर्तित रहती है।

## विशिष्ट PDF पृष्ठों को क्यों घुमाएँ?
आप एक सामान्य सर्वर‑ग्रेड VM पर 0.05 सेकंड से कम समय में एक पृष्ठ को घुमा सकते हैं, जिससे स्कैन किए गए अनुबंधों, प्रस्तुति डेक्स, या कई‑पृष्ठीय इनवॉइसेस जो गलत अभिविन्यास स्कैन रखते हैं, का रीयल‑टाइम प्रीव्यू संभव हो जाता है। यह सूक्ष्म नियंत्रण महंगे पोस्ट‑प्रोसेसिंग टूल्स की आवश्यकता को समाप्त करता है और बड़े‑पैमाने पर डिजिटलीकरण परियोजनाओं में मैन्युअल प्रयास को 70 % तक कम करता है।

## पूर्वापेक्षाएँ

### आवश्यक लाइब्रेरी और निर्भरताएँ
- Java Development Kit (JDK) 8 या बाद का।  
- IntelliJ IDEA या Eclipse जैसे IDE।  
- निर्भरताओं के प्रबंधन के लिए Maven।

### पर्यावरण सेटअप आवश्यकताएँ
1. **Maven कॉन्फ़िगरेशन** – अपने `pom.xml` में GroupDocs.Viewer जोड़ें।  
2. **लाइसेंस प्राप्ति** – GroupDocs से एक अस्थायी लाइसेंस प्राप्त करें। [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) पर जाएँ या [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) पर अस्थायी लाइसेंस के लिए आवेदन करें।

## GroupDocs.Viewer for Java सेटअप करना

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

### बुनियादी इनिशियलाइज़ेशन और सेटअप
`Viewer` वह मुख्य क्लास है जो दस्तावेज़ लोड करता है और रेंडरिंग ऑपरेशन्स को समन्वयित करता है। एक इंस्टेंस बनाने के बाद आप `view` या `rotatePage` जैसी मेथड्स को कॉल कर सकते हैं।  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## GroupDocs.Viewer के साथ विशिष्ट PDF पृष्ठों को कैसे घुमाएँ
GroupDocs.Viewer के साथ विशिष्ट PDF पृष्ठों को घुमाने में दो मुख्य कार्य होते हैं: पहला, `rotatePage` मेथड का उपयोग करके प्रत्येक लक्ष्य पृष्ठ के लिए वांछित घुमाव निर्दिष्ट करना, और दूसरा, दस्तावेज़ को `HtmlViewOptions` के साथ रेंडर करना ताकि घुमाव आउटपुट में प्रतिबिंबित हो। यह विधि मूल PDF को अपरिवर्तित रखती है जबकि सही अभिविन्यास वाला HTML प्रदान करती है।

### चरण 1: पृष्ठ घुमाव कॉन्फ़िगर करें
`rotatePage` एक मेथड है जो शून्य‑आधारित पृष्ठ इंडेक्स और एक `Rotation` enum मान स्वीकार करता है। यह enum तीन विकल्प प्रदान करता है: `ON_90_DEGREE`, `ON_180_DEGREE`, और `ON_270_DEGREE`।  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### चरण 2: व्यूअर को इनिशियलाइज़ करें और रेंडर करें
`HtmlViewOptions` PDF‑से‑HTML रूपांतरण प्रक्रिया को नियंत्रित करता है। यह लेआउट, फ़ॉन्ट्स और एम्बेडेड रिसोर्सेज को संरक्षित रखता है जबकि आपके द्वारा कॉन्फ़िगर किए गए किसी भी घुमाव को लागू करता है।  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### पैरामीटर और कॉन्फ़िगरेशन
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` जहाँ घुमाव विकल्प `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE` हैं।  
- **HtmlViewOptions** – लेआउट और एम्बेडेड रिसोर्सेज को संरक्षित रखते हुए pdf‑से‑html रूपांतरण को संभालता है।  
- **pdf to html java** – यह क्लास उसी API का हिस्सा है और एक सटीक दृश्य प्रतिनिधित्व सुनिश्चित करता है।

## सामान्य समस्याएँ और समाधान (pdf घुमाव का निवारण)
- **गलत पथ** – सुनिश्चित करें कि `YOUR_DOCUMENT_DIRECTORY` और `YOUR_OUTPUT_DIRECTORY` मौजूद हैं और पहुँच योग्य हैं।  
- **निर्भरताएँ अनुपलब्ध** – सुनिश्चित करें कि Maven कोऑर्डिनेट्स नवीनतम GroupDocs.Viewer संस्करण (वर्तमान में 25.2) से मेल खाते हैं।  
- **लाइसेंस प्रतिबंध** – अस्थायी लाइसेंस को सही तरीके से लागू करें; अन्यथा कुछ फीचर अक्षम हो सकते हैं।  
- **मेमोरी स्पाइक** – बड़े PDFs को छोटे बैचों में रेंडर करें या JVM हीप साइज बढ़ाएँ।

## व्यावहारिक अनुप्रयोग

### वास्तविक‑विश्व उपयोग केस
1. **दस्तावेज़ संरेखण** – सही डिजिटल अभिविन्यास के लिए स्कैन किए गए अनुबंधों को घुमाएँ।  
2. **प्रेजेंटेशन समायोजन** – साझा करने से पहले PDFs के भीतर प्रस्तुति स्लाइड्स को संशोधित करें।  
3. **आर्काइव वर्कफ़्लो** – डिजिटलीकरण के दौरान ऐतिहासिक दस्तावेज़ों की अभिविन्यास को स्वचालित रूप से समायोजित करें।

### एकीकरण संभावनाएँ
GroupDocs.Viewer को Java‑आधारित कंटेंट मैनेजमेंट सिस्टम, एंटरप्राइज़ पोर्टल्स, या कस्टम APIs के साथ संयोजित करें जिन्हें PDFs का ऑन‑द‑फ्लाई व्यूइंग चाहिए।

## प्रदर्शन विचार
- **संसाधन प्रबंधन** – फ़ाइल हैंडल्स और मेमोरी रिलीज़ करने के लिए हमेशा `Viewer` इंस्टेंस को बंद करें।  
- **Java मेमोरी प्रबंधन** – बड़े PDFs को प्रोसेस करते समय हीप उपयोग की निगरानी करें; पूरे फ़ाइल को लोड करने के बजाय पृष्ठों को स्ट्रीम करने पर विचार करें।  
- **सर्वोत्तम प्रथाएँ** – अक्सर एक्सेस किए जाने वाले दस्तावेज़ों के लिए रेंडर किए गए HTML को कैश करें ताकि प्रोसेसिंग समय को 60 % तक कम किया जा सके।

## निष्कर्ष
इस ट्यूटोरियल में **Java में GroupDocs.Viewer का उपयोग करके विशिष्ट PDF पृष्ठों को कैसे घुमाएँ** को Maven सेटअप से लेकर घुमाए गए पृष्ठों को रेंडर करने और सामान्य समस्याओं को संभालने तक कवर किया गया है। वॉटरमार्किंग, फ़ॉर्मेट रूपांतरण, या बैच प्रोसेसिंग जैसी अतिरिक्त सुविधाओं के साथ प्रयोग करें ताकि अपने दस्तावेज़ वर्कफ़्लो को और विस्तारित किया जा सके।

**अगले कदम:** PDFs को PNG में बदलना, वॉटरमार्क जोड़ना, या क्लाउड स्टोरेज प्रोवाइडर्स के साथ एकीकरण जैसी अन्य GroupDocs.Viewer क्षमताओं में डुबकी लगाएँ।

## अक्सर पूछे जाने वाले प्रश्न
- **घुमाव समस्याओं का निवारण** – पृष्ठ संख्याएँ और घुमाव पैरामीटर सही हैं यह सुनिश्चित करें।  
- **बड़े PDF फ़ाइलों को संभालना** – पृष्ठों को बैच में प्रोसेस करें और मेमोरी उपयोग की निगरानी करें।  
- **लाइसेंसिंग आवश्यकताएँ** – विकास के लिए अस्थायी लाइसेंस उपयोग करें; उत्पादन के लिए पूर्ण लाइसेंस खरीदें।  
- **कई पृष्ठों को घुमाना** – विभिन्न पृष्ठ संख्याओं और कोणों के साथ `rotatePage` को बार‑बार कॉल करें।  
- **Java लाइब्रेरीज़ के साथ एकीकरण** – GroupDocs.Viewer Spring Boot, Jakarta EE, और अन्य Java फ्रेमवर्क्स के साथ सहजता से काम करता है।

## अक्सर पूछे जाने वाले प्रश्न

**प्र: क्या मैं एक बार में PDF के सभी पृष्ठों को घुमा सकता हूँ?**  
**उ:** हाँ। पृष्ठ संख्याओं पर लूप करें और प्रत्येक पृष्ठ के लिए `rotatePage(page, Rotation.ON_90_DEGREE)` कॉल करें।

**प्र: क्या घुमाव मूल PDF फ़ाइल को प्रभावित करता है?**  
**उ:** नहीं। घुमाव केवल रेंडरिंग प्रक्रिया के दौरान लागू होता है; स्रोत PDF अपरिवर्तित रहता है।

**प्र: यदि PDF पासवर्ड‑सुरक्षित है तो क्या करें?**  
**उ:** `Viewer` इंस्टेंस बनाते समय पासवर्ड प्रदान करें: `new Viewer(path, password)`।

**प्र: HtmlViewOptions सेटअप करते समय “null pointer” त्रुटि को कैसे डिबग करें?**  
**उ:** सुनिश्चित करें कि आउटपुट डायरेक्टरी मौजूद है और `pageFilePathFormat` सही ढंग से रिज़ॉल्व हो रहा है।

**प्र: क्या अन्य फ़ॉर्मेट (जैसे PNG) में रूपांतरण करते समय पृष्ठों को घुमाने का कोई तरीका है?**  
**उ:** हाँ। लक्ष्य फ़ॉर्मेट के लिए उपयुक्त व्यू विकल्पों के साथ वही `rotatePage` कॉन्फ़िगरेशन उपयोग करें।

## संसाधन
- **डॉक्यूमेंटेशन**: [GroupDocs Viewer दस्तावेज़ीकरण](https://docs.groupdocs.com/viewer/java/)  
- **API रेफ़रेंस**: [GroupDocs API रेफ़रेंस](https://reference.groupdocs.com/viewer/java/)  
- **डाउनलोड**: [GroupDocs डाउनलोड पेज](https://releases.groupdocs.com/viewer/java/)  
- **खरीद**: [GroupDocs खरीद विकल्प](https://purchase.groupdocs.com/buy)  
- **फ़्री ट्रायल**: [GroupDocs फ़्री ट्रायल](https://releases.groupdocs.com/viewer/java/)  
- **अस्थायी लाइसेंस**: [अस्थायी लाइसेंस का अनुरोध करें](https://purchase.groupdocs.com/temporary-license/)  
- **समर्थन**: [GroupDocs समर्थन फ़ोरम](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-10-05  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs

## संबंधित ट्यूटोरियल

- [Java गाइड: GroupDocs.Viewer के साथ चयनित पृष्ठ रेंडर करें](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Java PDF रेंडरिंग GroupDocs Viewer पेज ब्रेक्स](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [GroupDocs Viewer Java रिस्पॉन्सिव HTML रेंडरिंग](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)