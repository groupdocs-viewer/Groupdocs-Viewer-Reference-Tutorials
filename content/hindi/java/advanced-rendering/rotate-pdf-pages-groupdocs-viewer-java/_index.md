---
date: '2026-01-18'
description: GroupDocs.Viewer for Java के साथ PDF पृष्ठों को घुमाना सीखें। इस चरण-दर-चरण
  ट्यूटोरियल में Maven सेटअप, पृष्ठ घुमाना (जिसमें PDF को 90 डिग्री घुमाना शामिल है)
  और समस्या निवारण को कवर किया गया है।
keywords:
- rotate PDF pages Java
- GroupDocs.Viewer setup Java
- programmatically rotate PDF Java
title: Java में GroupDocs.Viewer का उपयोग करके PDF पेज कैसे घुमाएँ – एक व्यापक गाइड
type: docs
url: /hi/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer का उपयोग करके जावा में PDF पृष्ठ कैसे घुमाएँ

PDF के भीतर विशिष्ट पृष्ठों को घुमाना दस्तावेज़ों को संरेखित करने या प्रस्तुति स्लाइड्स को समायोजित करने के लिए आवश्यक हो सकता है। **इस गाइड में आप सीखेंगे कि कैसे प्रोग्रामेटिक रूप से GroupDocs.Viewer के साथ PDF पृष्ठों को घुमाया जाए**, चाहे आपको PDF को 90 डिग्री घुमाना हो, पूरे सेक्शन को उलटना हो, या एक ही कॉल में कई पृष्ठों को संभालना हो।

![GroupDocs.Viewer for Java के साथ विशिष्ट PDF पृष्ठ घुमाएँ](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**आप क्या सीखेंगे:**
- अपने जावा प्रोजेक्ट में GroupDocs.Viewer सेट अप करना (Maven GroupDocs Viewer कॉन्फ़िगरेशन सहित)
- प्रोग्रामेटिक रूप से विशिष्ट PDF पृष्ठों को घुमाना (PDF को 90 डिग्री, 180 डिग्री आदि घुमाएँ)
- सर्वोत्तम उपयोग के लिए प्रमुख कॉन्फ़िगरेशन
- इम्प्लीमेंटेशन के दौरान सामान्य समस्याओं का निवारण

## त्वरित उत्तर
- **जावा में PDF पृष्ठ घुमाने वाली लाइब्रेरी कौन सी है?** GroupDocs.Viewer for Java.  
- **क्या मैं एक पृष्ठ को 90 डिग्री घुमा सकता हूँ?** हाँ, `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` का उपयोग करें।  
- **क्या विकास के लिए लाइसेंस चाहिए?** फ्री ट्रायल के लिए एक अस्थायी लाइसेंस उपलब्ध है।  
- **क्या Maven आवश्यक है?** Maven, GroupDocs निर्भरताओं को प्रबंधित करने का अनुशंसित तरीका है।  
- **घुमाए गए पृष्ठों को कैसे रेंडर करें?** `HtmlViewOptions` का उपयोग करें और `viewer.view(...)` को कॉल करें।

## पूर्वापेक्षाएँ

### आवश्यक लाइब्रेरी और निर्भरताएँ
- अपने मशीन पर Java Development Kit (JDK) संस्करण 8 या उससे नया स्थापित होना चाहिए।  
- IntelliJ IDEA या Eclipse जैसे एक इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (IDE) होना चाहिए।  
- प्रोजेक्ट निर्भरताओं को प्रबंधित करने के लिए Maven।

### पर्यावरण सेटअप आवश्यकताएँ
1. **Maven कॉन्फ़िगरेशन**: अपने `pom.xml` में आवश्यक रिपॉज़िटरी और निर्भरताएँ जोड़कर GroupDocs.Viewer को अपने Maven प्रोजेक्ट में शामिल करें।  
2. **लाइसेंस प्राप्ति**: विकास के दौरान सभी सुविधाओं को बिना सीमा के एक्सप्लोर करने के लिए GroupDocs से एक अस्थायी लाइसेंस प्राप्त करें। देखें [GroupDocs फ्री ट्रायल](https://releases.groupdocs.com/viewer/java/) या [GroupDocs अस्थायी लाइसेंस पेज](https://purchase.groupdocs.com/temporary-license/) पर अस्थायी लाइसेंस के लिए आवेदन करें।

## जावा के लिए GroupDocs.Viewer सेट अप करना

Maven का उपयोग करके अपने जावा प्रोजेक्ट में GroupDocs.Viewer को इंटीग्रेट करने के लिए, अपने `pom.xml` को अपडेट करें:

**Maven कॉन्फ़िगरेशन**  
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

अपने दस्तावेज़ डायरेक्टरी और आउटपुट पाथ को निर्दिष्ट करके GroupDocs.Viewer को इनिशियलाइज़ करें:  
```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## इम्प्लीमेंटेशन गाइड

### GroupDocs.Viewer के साथ विशिष्ट पृष्ठ घुमाना

**सारांश:** बेहतर दस्तावेज़ प्रस्तुति के लिए विशिष्ट PDF पृष्ठ घुमाएँ।

#### चरण 1: पृष्ठ घुमाव कॉन्फ़िगर करें

`HtmlViewOptions` का उपयोग करके पहले पृष्ठ को 90 डिग्री और दूसरे पृष्ठ को 180 डिग्री घुमाएँ:  
```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

#### चरण 2: Viewer को इनिशियलाइज़ करें और रेंडर करें

अपने दस्तावेज़ के साथ एक `Viewer` इंस्टेंस बनाएं और निर्दिष्ट पृष्ठों को रेंडर करें:  
```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

### पैरामीटर और कॉन्फ़िगरेशन
- **Rotation**: पृष्ठ संख्याओं और घुमाव कोणों के साथ `rotatePage` का उपयोग करें। उपलब्ध घुमाव: `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`।  
- **HtmlViewOptions**: PDF पृष्ठ को HTML में बदलने को कॉन्फ़िगर करता है, जिससे एम्बेडेड रिसोर्सेज़ शामिल हों।  
- **pdf to html java**: `HtmlViewOptions` क्लास लेआउट को बनाए रखते हुए PDF‑to‑HTML रूपांतरण को संभालती है।

#### ट्रबलशूटिंग टिप्स (pdf rotation को ट्रबलशूट करें)
- अपने दस्तावेज़ और आउटपुट डायरेक्टरी के पाथ को सत्यापित करें।  
- गुम निर्भरताओं या गलत लाइब्रेरी संस्करणों की जाँच करें।  
- यदि ट्रायल के दौरान फीचर प्रतिबंध होते हैं तो लाइसेंस सही ढंग से लागू किया गया है, यह सुनिश्चित करें।  
- यदि मेमोरी स्पाइक का सामना करते हैं, तो पृष्ठों को छोटे बैच में रेंडर करने पर विचार करें (कई PDF पृष्ठों को क्रमिक रूप से घुमाएँ)।

## व्यावहारिक अनुप्रयोग

### वास्तविक‑विश्व उपयोग केस
1. **दस्तावेज़ संरेखण** – स्कैन किए गए दस्तावेज़ों को सही डिजिटल अभिविन्यास के लिए घुमाएँ।  
2. **प्रेजेंटेशन समायोजन** – साझा करने से पहले PDFs के भीतर प्रेजेंटेशन स्लाइड्स को संशोधित करें।  
3. **आर्काइव वर्कफ़्लो** – डिजिटलीकरण के दौरान ऐतिहासिक दस्तावेज़ों की अभिविन्यास को स्वचालित रूप से समायोजित करें।

### इंटीग्रेशन संभावनाएँ
GroupDocs.Viewer को जावा‑आधारित दस्तावेज़ प्रबंधन सिस्टम, कंटेंट प्लेटफ़ॉर्म, या गतिशील व्यूइंग क्षमताओं की आवश्यकता वाले कस्टम एंटरप्राइज़ सॉल्यूशन्स के साथ इंटीग्रेट करें।

## प्रदर्शन विचार

- **रिसोर्स मैनेजमेंट**: रिसोर्सेज़ रिलीज़ करने के लिए `Viewer` इंस्टेंस को बंद करें।  
- **जावा मेमोरी मैनेजमेंट**: बड़े दस्तावेज़ रेंडर करते समय मेमोरी उपयोग की निगरानी करें और कुशल डेटा स्ट्रक्चर का उपयोग करें।  
- **सर्वोत्तम प्रैक्टिसेज़**: अक्सर एक्सेस किए जाने वाले दस्तावेज़ों या पृष्ठों के लिए कैशिंग का उपयोग करें।

## निष्कर्ष

यह ट्यूटोरियल GroupDocs.Viewer का उपयोग करके जावा में **PDF पृष्ठ कैसे घुमाएँ** को कवर करता है, पर्यावरण सेटअप से लेकर व्यावहारिक अनुप्रयोगों तक। वॉटरमार्किंग या दस्तावेज़ों को विभिन्न फ़ॉर्मैट में बदलने जैसी अतिरिक्त कार्यात्मकताओं के साथ प्रयोग करें।

**अगले कदम:** अपने दस्तावेज़ प्रोसेसिंग क्षमताओं को बढ़ाने के लिए अधिक GroupDocs.Viewer सुविधाओं का अन्वेषण करें।

## अक्सर पूछे जाने वाले प्रश्न (FAQ) सेक्शन

### सामान्य प्रश्न
1. **रोटेशन समस्याओं का निवारण**: पृष्ठ संख्याएँ और घुमाव पैरामीटर सही हैं, यह सत्यापित करें।  
2. **बड़े PDF फ़ाइलों को संभालना**: उचित रिसोर्स मैनेजमेंट के साथ बड़े दस्तावेज़ों को कुशलतापूर्वक प्रोसेस करें।  
3. **लाइसेंसिंग आवश्यकताएँ**: विकास के लिए अस्थायी लाइसेंस का उपयोग करें; प्रोडक्शन के लिए पूर्ण लाइसेंस खरीदें।  
4. **कई पृष्ठ घुमाना**: विभिन्न पृष्ठ संख्याओं और कोणों के साथ `rotatePage` को कई बार कॉल करें।  
5. **जावा लाइब्रेरीज़ के साथ इंटीग्रेशन**: बड़े एप्लिकेशन या फ्रेमवर्क के भीतर GroupDocs.Viewer को सहजता से इंटीग्रेट करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं एक साथ PDF के सभी पृष्ठ घुमा सकता हूँ?**  
**उत्तर:** हाँ। पृष्ठ संख्याओं पर लूप करें और प्रत्येक पृष्ठ के लिए `rotatePage(page, Rotation.ON_90_DEGREE)` कॉल करें।

**प्रश्न: क्या घुमाव मूल PDF फ़ाइल को प्रभावित करता है?**  
**उत्तर:** नहीं। घुमाव केवल रेंडरिंग प्रक्रिया के दौरान लागू होता है; स्रोत PDF अपरिवर्तित रहता है।

**प्रश्न: यदि PDF पासवर्ड‑सुरक्षित है तो क्या करें?**  
**उत्तर:** `Viewer` इंस्टेंस बनाते समय पासवर्ड प्रदान करें: `new Viewer(path, password)`।

**प्रश्न: HtmlViewOptions सेटअप करते समय “null pointer” त्रुटि को कैसे डिबग करें?**  
**उत्तर:** सुनिश्चित करें कि आउटपुट डायरेक्टरी मौजूद है और `pageFilePathFormat` सही ढंग से रिजॉल्व हो रहा है।

**प्रश्न: क्या अन्य फ़ॉर्मैट (जैसे PNG) में कनवर्ट करते समय पृष्ठ घुमाने का तरीका है?**  
**उत्तर:** लक्ष्य फ़ॉर्मैट के लिए उपयुक्त व्यू विकल्पों के साथ वही `rotatePage` कॉन्फ़िगरेशन उपयोग करें।

## संसाधन
- **डॉक्यूमेंटेशन**: [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API रेफ़रेंस**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **डाउनलोड**: [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)  
- **खरीद**: [GroupDocs Purchase Options](https://purchase.groupdocs.com/buy)  
- **फ्री ट्रायल**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **अस्थायी लाइसेंस**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **सपोर्ट**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-01-18  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs