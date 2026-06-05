---
date: '2026-02-28'
description: GroupDocs.Viewer for Java का उपयोग करके CDR फ़ाइलों को HTML, JPG, PNG
  और PDF में कैसे बदलें, सीखें। सेटअप, कोड उदाहरण और प्रदर्शन टिप्स शामिल हैं।
keywords:
- render CDR files
- GroupDocs.Viewer Java
- HTML conversion
title: GroupDocs.Viewer Java के साथ cdr को html, jpg, png, pdf में परिवर्तित करें
type: docs
url: /hi/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# GroupDocs.Viewer Java के साथ CDR को HTML, JPG, PNG, PDF में परिवर्तित करें

यदि आपको **CDR को HTML** (या JPG, PNG, और PDF) में तेज़ और विश्वसनीय तरीके से परिवर्तित करना है, तो आप सही ट्यूटोरियल पर आए हैं। इस गाइड में हम सब कुछ बताएँगे—GroupDocs.Viewer for Java को इंस्टॉल करने से लेकर CorelDRAW (CDR) फ़ाइलों को वेब‑फ़्रेंडली HTML पेज, हाई‑क्वालिटी इमेज और सार्वभौमिक रूप से पढ़े जाने वाले PDF में रेंडर करने तक। अंत तक, आप कुछ ही कोड लाइनों के साथ इन रूपांतरणों को किसी भी Java एप्लिकेशन में इंटीग्रेट कर पाएँगे।

![Render CDR Files with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-cdr-files.png)

## त्वरित उत्तर
- **CDR को HTML में परिवर्तित करने वाली लाइब्रेरी कौन सी है?** GroupDocs.Viewer for Java.  
- **क्या मैं CDR को JPG, PNG, और PDF में भी परिवर्तित कर सकता हूँ?** हाँ—विभिन्न view विकल्पों के साथ वही Viewer API उपयोग करें।  
- **क्या मुझे लाइसेंस की आवश्यकता है?** परीक्षण के लिए फ्री ट्रायल या टेम्पररी लाइसेंस काम करता है; प्रोडक्शन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण आवश्यक है?** JDK 8 या नया।  
- **क्या बैच रूपांतरण समर्थित है?** बिल्कुल—सिर्फ वही Viewer इंस्टेंस के साथ फ़ाइलों को लूप करें।

## “CDR को HTML में परिवर्तित करें” क्या है?
CDR को HTML में परिवर्तित करना का अर्थ है CorelDRAW वेक्टर फ़ाइल को मानक HTML मार्कअप में बदलना, वैकल्पिक रूप से इमेज और स्टाइल एम्बेड करके डिज़ाइन को सीधे वेब ब्राउज़र में मूल डिज़ाइन सॉफ़्टवेयर की आवश्यकता के बिना देखा जा सके।

## CDR को HTML, JPG, PNG, या PDF में क्यों परिवर्तित करें?
- **HTML** आपको वेब पोर्टल में ग्राफ़िक्स एम्बेड करने और तुरंत शेयर करने की सुविधा देता है।  
- **JPG** और **PNG** आपको गैलरी, थंबनेल या ई‑मेल अटैचमेंट के लिए रास्टर इमेज प्रदान करते हैं।  
- **PDF** एक प्रिंटेबल, प्लेटफ़ॉर्म‑इंडिपेंडेंट संस्करण देता है जो आर्काइविंग या डॉक्यूमेंट‑शेयरिंग सिस्टम के लिए उपयुक्त है।  

इन चार फ़ॉर्मेट्स को हाथ में रखने से आप सही फ़ाइल टाइप सही ऑडियंस को दे सकते हैं, प्रदर्शन में सुधार कर सकते हैं, और अपने एसेट्स को भविष्य‑सुरक्षित बना सकते हैं।

## पूर्वापेक्षाएँ

शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

1. **लाइब्रेरीज़ और डिपेंडेंसीज़** – आपके Maven प्रोजेक्ट में GroupDocs.Viewer जोड़ा गया हो।  
2. **Java Development Kit (JDK)** – संस्करण 8 या नया स्थापित हो।  
3. **बेसिक Java ज्ञान** – कोड स्निपेट्स को समझने के लिए।

### आवश्यक लाइब्रेरीज़, संस्करण और डिपेंडेंसीज़

अपने `pom.xml` में निम्न Maven कॉन्फ़िगरेशन जोड़ें (मूल ट्यूटोरियल जैसा ही):

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

### लाइसेंस प्राप्त करने के चरण

GroupDocs.Viewer फ्री ट्रायल, परीक्षण के लिए टेम्पररी लाइसेंस, या पूर्ण‑पर्चेज विकल्प प्रदान करता है:

- **Free Trial** – डाउनलोड करें [GroupDocs Release Page](https://releases.groupdocs.com/viewer/java/) से।  
- **Temporary License** – अनुरोध करें [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/) पर।  
- **Purchase** – स्थायी लाइसेंस प्राप्त करें [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy) से।

## GroupDocs.Viewer for Java सेटअप करना

### Maven के साथ इंस्टॉलेशन
ऊपर दिया गया Maven स्निपेट सभी आवश्यक JARs को स्वचालित रूप से लाएगा। फ़ाइल सहेजने के बाद `mvn clean install` चलाएँ।

### लाइसेंस इनिशियलाइज़ेशन
किसी भी डॉक्यूमेंट को रेंडर करने से पहले अपना लाइसेंस इनिशियलाइज़ करें:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## इम्प्लीमेंटेशन गाइड

नीचे प्रत्येक आउटपुट फ़ॉर्मेट के लिए चरण‑बद्ध उदाहरण दिए गए हैं। कोड ब्लॉक्स मूल ट्यूटोरियल के समान हैं; हमने उनके आसपास केवल व्याख्यात्मक टेक्स्ट जोड़ा है।

### GroupDocs.Viewer के साथ CDR को HTML में परिवर्तित करना

#### CDR डॉक्यूमेंट को HTML में रेंडर करना
**Overview:** अपने CDR फ़ाइलों को वेब‑फ़्रेंडली HTML में बदलें ताकि आसानी से शेयर किया जा सके।

**Step 1 – Set Up File Paths**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### GroupDocs.Viewer के साथ CDR को JPG में परिवर्तित करना

#### CDR डॉक्यूमेंट को JPG में रेंडर करना
**Overview:** अपने CDR स्रोत से हाई‑क्वालिटी JPEG इमेज बनाएं।

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### GroupDocs.Viewer के साथ CDR को PNG में परिवर्तित करना

#### CDR डॉक्यूमेंट को PNG में रेंडर करना
**Overview:** आर्काइव या डिज़ाइन उद्देश्यों के लिए लॉसलेस PNG इमेज जेनरेट करें।

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### GroupDocs.Viewer के साथ CDR को PDF में परिवर्तित करना

#### CDR डॉक्यूमेंट को PDF में रेंडर करना
**Overview:** अपने CDR फ़ाइलों को सार्वभौमिक रूप से पढ़े जाने वाले PDF में बदलें।

**Step 1 – Set Up File Paths**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Step 2 – Initialize Viewer and Render**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## व्यावहारिक उपयोग

- **Web Portals:** HTML रूपांतरण का उपयोग करके CDR डिज़ाइन को सीधे अपनी साइट पर एम्बेड करें।  
- **Image Galleries:** तेज़‑लोडिंग इमेज गैलरी के लिए JPG/PNG आउटपुट डिप्लॉय करें।  
- **Document Sharing:** उन क्लाइंट्स के लिए PDF प्रदान करें जिन्हें प्रिंटेबल, रीड‑ओनली संस्करण चाहिए।  
- **Archiving:** कई फ़ॉर्मेट्स स्टोर करके भविष्य में एक्सेसिबिलिटी सुनिश्चित करें।  
- **Cross‑Platform Integration:** उत्पन्न फ़ाइलों को अन्य सर्विसेज (जैसे OCR, एनालिटिक्स) में फीड करें।

## प्रदर्शन संबंधी विचार

- **Viewer इंस्टेंस को तुरंत डिस्पोज़** करें (जैसा कि try‑with‑resources में दिखाया गया है) ताकि मेमोरी मुक्त हो सके।  
- **बैच प्रोसेसिंग:** समान Viewer कॉन्फ़िगरेशन के साथ CDR फ़ाइलों के संग्रह को लूप करके ओवरहेड कम करें।  
- **रिसोर्स एलोकेशन:** बड़े या जटिल CDR फ़ाइलों के लिए पर्याप्त CPU/RAM आवंटित करें; मॉनिटरिंग टूल्स से फ़ाइन‑ट्यूनिंग में मदद मिलती है।

## निष्कर्ष

हमने दिखाया कि कैसे **CDR को HTML**, साथ ही JPG, PNG, और PDF में GroupDocs.Viewer for Java का उपयोग करके परिवर्तित किया जा सकता है। संक्षिप्त कोड स्निपेट्स और बेस्ट‑प्रैक्टिस टिप्स का पालन करके आप इन रूपांतरणों को किसी भी Java‑आधारित वर्कफ़्लो में इंटीग्रेट कर सकते हैं, जिससे आपके उपयोगकर्ताओं को लचीले, हाई‑क्वालिटी आउटपुट मिलेंगे।

### अगले कदम
- कस्टम पेज साइज या वॉटरमार्क जैसी एडवांस्ड रेंडरिंग विकल्पों के साथ प्रयोग करें।  
- रूपांतरण पाइपलाइन को REST API के साथ जोड़ें ताकि ऑन‑डिमांड फ़ाइल ट्रांसफ़ॉर्मेशन प्रदान किया जा सके।  
- समुदाय में शामिल हों और प्रश्न पूछें [GroupDocs Forum](https://forum.groupdocs.com/c/viewer) में।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं पासवर्ड‑प्रोटेक्टेड CDR फ़ाइलों को परिवर्तित कर सकता हूँ?**  
A: हाँ। `Viewer` इंस्टेंस को पासवर्ड पैरामीटर के साथ लोड करें (API डॉक्यूमेंटेशन देखें)।

**Q: क्या एक साथ परिवर्तित किए जाने वाले पेजों की संख्या पर कोई सीमा है?**  
A: कोई हार्ड लिमिट नहीं है, लेकिन बहुत बड़ी फ़ाइलों को अधिक मेमोरी की आवश्यकता हो सकती है; पेज‑बाय‑पेज प्रोसेसिंग पर विचार करें।

**Q: क्या HTML आउटपुट में एम्बेडेड फ़ॉन्ट्स शामिल होते हैं?**  
A: जब आप `HtmlViewOptions.forEmbeddedResources` उपयोग करते हैं, तो फ़ॉन्ट्स Base64 के रूप में एम्बेड होते हैं, जिससे रेंडरिंग सुसंगत रहती है।

**Q: JPEG क्वालिटी कैसे नियंत्रित करूँ?**  
A: `JpgViewOptions` में `setQuality(int)` मेथड है जहाँ आप 1‑100 के बीच मान निर्दिष्ट कर सकते हैं।

**Q: क्या मैं Linux सर्वर पर CDR फ़ाइलें परिवर्तित कर सकता हूँ?**  
A: बिल्कुल—GroupDocs.Viewer प्लेटफ़ॉर्म‑अज्ञेय है बशर्ते JDK स्थापित हो।

---

**Last Updated:** 2026-02-28  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs