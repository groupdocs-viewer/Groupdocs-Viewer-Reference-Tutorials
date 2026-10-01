---
date: '2026-09-30'
description: GroupDocs Viewer का उपयोग करके Java में पृष्ठ को 90 डिग्री घुमाने का
  तरीका सीखें, जिसमें setup, code, और performance tips शामिल हैं।
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: GroupDocs Viewer का उपयोग करके Java में पृष्ठ को 90 डिग्री घुमाएँ।
  Step‑by‑step guide, performance tips, और real‑world use cases डेवलपर्स के लिए।
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: GroupDocs Viewer for Java के साथ पृष्ठ को 90 डिग्री घुमाएँ
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: GroupDocs Viewer for Java के साथ पृष्ठ को 90 डिग्री घुमाएँ
type: docs
url: /hi/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# पृष्ठ को 90 डिग्री घुमाएँ GroupDocs Viewer for Java के साथ

यदि आपको किसी दस्तावेज़ में **पृष्ठ को 90 डिग्री घुमाएँ** की आवश्यकता है—चाहे वह PDF, Word फ़ाइल, या स्प्रेडशीट हो—तो इसे Java में प्रोग्रामेटिकली करना समय बचाता है, मैन्युअल त्रुटियों को हटाता है, और ऑपरेशन को स्वचालित पाइपलाइन में एम्बेड करने की अनुमति देता है। इस उन्नत गाइड में आप सीखेंगे कि **GroupDocs Viewer for Java** का उपयोग करके किसी भी समर्थित दस्तावेज़ का पहला पृष्ठ कैसे घुमाएँ, यह क्षमता वास्तविक‑दुनिया के प्रोजेक्ट्स में क्यों महत्वपूर्ण है, और प्रक्रिया को हल्का और मेमोरी‑कुशल कैसे रखें।

![GroupDocs.Viewer for Java के साथ दस्तावेज़ का पहला पृष्ठ घुमाएँ](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## त्वरित उत्तर
- **“पृष्ठ को 90 डिग्री घुमाएँ” का क्या अर्थ है?** यह चयनित पृष्ठ को घड़ी की दिशा में एक चौथाई घुमाव द्वारा घुमाता है।  
- **कौन सा लाइब्रेरी घुमाव को संभालती है?** GroupDocs Viewer for Java `rotatePage` मेथड प्रदान करता है।  
- **क्या मैं Java के साथ PDF पृष्ठ घुमा सकता हूँ?** हाँ—उसी `rotatePage` कॉल का उपयोग करें; यह PDF, DOCX, XLSX, और अधिक के लिए काम करता है।  
- **क्या मुझे लाइसेंस की आवश्यकता है?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक भुगतान किया हुआ लाइसेंस आवश्यक है।  
- **क्या यह ऑपरेशन मेमोरी‑गहन है?** `Viewer` इंस्टेंस को तुरंत बंद करने पर नहीं; नीचे प्रदर्शन टिप्स देखें।

## “पृष्ठ को 90 डिग्री घुमाएँ” क्या है?
पृष्ठ को 90 डिग्री घुमाने से पृष्ठ को पोर्ट्रेट से लैंडस्केप (या इसके विपरीत) में पुनः अभिविन्यस्त किया जाता है, बिना अंतर्निहित सामग्री को बदले। यह प्रस्तुतियों, केवल लैंडस्केप ग्राफ़िक्स को प्रिंट करने, या स्कैन किए गए दस्तावेज़ों को जो बगल में कैप्चर हुए थे, सुधारने के लिए उपयोगी है। घुमाव रेंडर समय पर लागू होता है, मूल फ़ाइल अपरिवर्तित रहती है।

## GroupDocs Viewer for Java के साथ पृष्ठों को प्रोग्रामेटिकली क्यों घुमाएँ?
GroupDocs Viewer **50+ इनपुट और आउटपुट फ़ॉर्मेट**—PDF, DOCX, PPTX, XLSX, और कई इमेज टाइप्स सहित—को समर्थन करता है, इसलिए आप किसी भी दस्तावेज़ को बाहरी कन्वर्टर्स के बिना रेंडर कर सकते हैं। API फ़्लुएंट, थ्रेड‑सेफ़, और किसी भी Java 8+ रनटाइम पर चलता है, जिससे यह एंटरप्राइज़‑ग्रेड ऑटोमेशन के लिए विश्वसनीय विकल्प बनता है जो कई फ़ाइल प्रकारों को लगातार संभालना चाहिए।

## पूर्वापेक्षाएँ

- GroupDocs Viewer for Java (नवीनतम संस्करण)
- JDK 8 या नया
- निर्भरता प्रबंधन के लिए Maven (या Gradle)
- IntelliJ IDEA या Eclipse जैसे IDE
- Java I/O की बुनियादी परिचितता

## GroupDocs.Viewer for Java सेटअप करना

अपने `pom.xml` में GroupDocs रिपॉज़िटरी और डिपेंडेंसी जोड़ें। यह स्निपेट मूल ट्यूटोरियल से अपरिवर्तित है:

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
- **मुफ़्त ट्रायल** – GroupDocs साइट से डाउनलोड करें।  
- **अस्थायी लाइसेंस** – यदि आपको विस्तारित मूल्यांकन अवधि चाहिए तो अनुरोध करें।  
- **पूर्ण लाइसेंस** – उत्पादन परिनियोजन के लिए खरीदें।

### बेसिक Viewer इनिशियलाइज़ेशन
`Viewer` क्लास वह एंट्री पॉइंट है जो दस्तावेज़ लोड करता है और रेंडरिंग तथा ट्रांसफ़ॉर्मेशन मेथड्स को एक्सपोज़ करता है। कोड को बिल्कुल जैसा दिखाया गया है वैसा रखें:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## GroupDocs Viewer के साथ Java में PDF पृष्ठ कैसे घुमाएँ
`Viewer` के साथ लक्ष्य फ़ाइल लोड करें, पृष्ठ संख्या निर्दिष्ट करें, और `rotatePage` को कॉल करें। यह मेथड PDF, DOCX, PPTX, XLSX और लाइब्रेरी द्वारा समर्थित किसी भी फ़ॉर्मेट के लिए काम करता है। घुमाव के बाद, आप दस्तावेज़ को नई PDF में रेंडर कर सकते हैं या सीधे क्लाइंट को स्ट्रीम कर सकते हैं, जिससे मूल फ़ाइल अपरिवर्तित रहती है।

## चरण‑दर‑चरण कार्यान्वयन: पहला पृष्ठ 90 डिग्री घुमाएँ

### 1. आवश्यक पैकेज इम्पोर्ट करें
`PdfViewOptions` Viewer को PDF फ़ाइल आउटपुट करने के लिए बताता है, जबकि `Rotation` एनेम घुमाव का कोण परिभाषित करता है। दोनों क्लासेस `com.groupdocs.viewer.options` पैकेज में स्थित हैं।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. आउटपुट लोकेशन परिभाषित करें और Viewer बनाएं
प्लेसहोल्डर पाथ को अपने वास्तविक डायरेक्टरी पाथ से बदलें। `Viewer` कंस्ट्रक्टर एक `File` ऑब्जेक्ट लेता है जो स्रोत दस्तावेज़ की ओर इशारा करता है।

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. PDF व्यू विकल्प कॉन्फ़िगर करें और घुमाव लागू करें
`rotatePage(int, Rotation)` मेथड **1‑आधारित** पेज इंडेक्स और `Rotation` एनेम वैल्यू लेता है। इस उदाहरण में हम `Rotation.ON_90_DEGREE` का उपयोग करके पहला पृष्ठ घड़ी की दिशा में घुमाते हैं।

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. दस्तावेज़ को रेंडर करें
कॉन्फ़िगर किए गए विकल्पों के साथ `view` को कॉल करने से घुमा हुआ PDF आउटपुट फ़ोल्डर में लिखा जाता है।

```java
viewer.view(viewOptions);
```

#### यह कैसे काम करता है
- **PdfViewOptions** Viewer को PDF आउटपुट फ़ाइल जनरेट करने के लिए निर्देशित करता है।  
- **rotatePage(int, Rotation)** केवल निर्दिष्ट पृष्ठ को घुमाता है, बाकी सभी पृष्ठों को अपरिवर्तित छोड़ता है।  
- यह मेथड तीन घुमाव स्थिरांक को समर्थन देता है: `ON_90_DEGREE`, `ON_180_DEGREE`, और `ON_270_DEGREE`।

## सामान्य समस्याएँ और समाधान
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| **FileNotFoundException** | गलत पथ या फ़ोल्डर अनुपलब्ध | `YOUR_OUTPUT_DIRECTORY` और `YOUR_DOCUMENT_DIRECTORY` मौजूद हैं और पढ़ने योग्य हैं, यह सत्यापित करें। |
| **Unsupported file format** | Viewer द्वारा समर्थित नहीं फ़ॉर्मेट को घुमाने का प्रयास | [GroupDocs Viewer supported formats] पृष्ठ देखें। |
| **No rotation visible** | गलत पृष्ठ संख्या (0‑आधारित) का उपयोग | `rotatePage` **1‑आधारित** इंडेक्सिंग उपयोग करता है, याद रखें। |
| **Out‑of‑memory errors on large docs** | एक ही थ्रेड में कई बड़े फ़ाइलों को रेंडर करना | दस्तावेज़ों को क्रमिक रूप से प्रोसेस करें या सीमित समवर्तीता के साथ थ्रेड पूल उपयोग करें। |

## व्यावहारिक अनुप्रयोग

1. **प्रेजेंटेशन समायोजन** – बेहतर दृश्य प्रभाव के लिए पोर्ट्रेट स्लाइड को तुरंत लैंडस्केप में बदलें।  
2. **बड़े पैमाने पर दस्तावेज़ सुधार** – स्कैन किए गए PDF को जो बगल में कैप्चर हुए थे, स्वचालित रूप से ठीक करें, जिससे कई घंटे का मैनुअल काम बचता है।  
3. **प्रिंट‑तैयार आउटपुट** – लैंडस्केप ग्राफ़िक्स को पोर्ट्रेट‑ओरिएंटेड कागज पर सही ढंग से प्रिंट सुनिश्चित करें, प्रिंटर ड्राइवर में मैनुअल घुमाव के बिना।

## प्रदर्शन टिप्स

- **संसाधनों को तुरंत बंद करें** – `try‑with‑resources` ब्लॉक स्वचालित रूप से `Viewer` को डिस्पोज़ करता है, मेमोरी मुक्त करता है।  
- **बैच प्रोसेसिंग** – प्रत्येक थ्रेड के लिए एक `Viewer` इंस्टेंस पुन: उपयोग करें ताकि इनिशियलाइज़ेशन ओवरहेड कम हो।  
- **मेमोरी मॉनिटर करें** – 100 MB से बड़े दस्तावेज़ों के लिए, आउटपुट को डिस्क पर स्ट्रीम करें बजाय पूरी फ़ाइल को मेमोरी में रखने के; GroupDocs Viewer 200 MB फ़ाइलों को 250 MB RAM से कम में प्रोसेस कर सकता है।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं एक साथ कई पृष्ठ घुमा सकता हूँ?**  
A: हाँ—आपको घुमाने वाले प्रत्येक पृष्ठ संख्या के लिए `rotatePage()` को कॉल करें, चाहे लूप में या चेनिंग कॉल्स द्वारा।

**प्रश्न: क्या रेंडरिंग के बाद घुमाव को वापस करने का कोई तरीका है?**  
A: सीधे नहीं। आपको घुमाव विकल्पों के बिना दस्तावेज़ को फिर से रेंडर करना होगा।

**प्रश्न: GroupDocs Viewer में कौन से फ़ाइल फ़ॉर्मेट पृष्ठ घुमाव का समर्थन करते हैं?**  
A: DOCX, PDF, PPTX, XLSX, और आधिकारिक दस्तावेज़ में सूचीबद्ध कई अन्य फ़ॉर्मेट।

**प्रश्न: कई दस्तावेज़ों के बैच में पृष्ठों को स्वचालित रूप से कैसे घुमाएँ?**  
A: घुमाव लॉजिक को एक लूप में रखें जो फ़ाइल पाथ्स के संग्रह पर इटरेट करे, प्रत्येक फ़ाइल पर समान `rotatePage` कॉन्फ़िगरेशन लागू करे।

**प्रश्न: घुमाव के दौरान त्रुटियों को संभालने की सर्वोत्तम प्रथा क्या है?**  
A: Viewer उपयोग को `try‑catch` ब्लॉक में रखें, अपवाद विवरण लॉग करें, और वैकल्पिक रूप से अगले फ़ाइल को प्रोसेस करना जारी रखें ताकि एकल विफलता पूरी बैच को रोक न सके।

## संसाधन

- **दस्तावेज़ीकरण**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API रेफ़रेंस**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **डाउनलोड**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **खरीदें**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **मुफ़्त ट्रायल**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **अस्थायी लाइसेंस**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **समर्थन**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-09-30  
**परीक्षित संस्करण:** GroupDocs Viewer 25.2 for Java  
**लेखक:** GroupDocs

## संबंधित ट्यूटोरियल

- [How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Load Document from URL in Java – GroupDocs.Viewer Tutorial](/viewer/java/document-loading/)
- [Groupdocs Viewer Java Document Views](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)