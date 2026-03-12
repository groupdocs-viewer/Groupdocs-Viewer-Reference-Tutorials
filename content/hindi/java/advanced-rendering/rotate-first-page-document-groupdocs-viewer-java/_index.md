---
date: '2026-01-18'
description: GroupDocs Viewer का उपयोग करके जावा में पृष्ठ को 90 डिग्री घुमाना सीखें,
  जिसमें सेटअप, कोड और प्रदर्शन टिप्स शामिल हैं।
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: GroupDocs Viewer for Java के साथ पृष्ठ को 90 डिग्री घुमाएँ
type: docs
url: /hi/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer for Java के साथ पृष्ठ को 90 डिग्री घुमाएँ

जब आपको किसी दस्तावेज़ में **पृष्ठ को 90 डिग्री घुमाना** हो—चाहे वह PDF, Word फ़ाइल, या स्प्रेडशीट हो—तो इसे प्रोग्रामेटिक रूप से करने से समय बचता है और मैन्युअल त्रुटियों से बचा जा सकता है। इस उन्नत गाइड में हम **GroupDocs Viewer for Java** का उपयोग करके किसी भी समर्थित दस्तावेज़ के पहले पृष्ठ को घुमाने के सटीक चरणों को दिखाएंगे। अंत तक, आपके पास एक पुन: उपयोग योग्य स्निपेट होगा जिसे आप अपने प्रोजेक्ट्स में डाल सकते हैं।

![GroupDocs.Viewer for Java के साथ दस्तावेज़ का पहला पृष्ठ घुमाएँ](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## त्वरित उत्तर
- **“पृष्ठ को 90 डिग्री घुमाना” क्या मतलब है?** यह चयनित पृष्ठ को घड़ी की दिशा में एक चौथाई घुमाव (90 डिग्री) में घुमाता है।  
- **कौन सी लाइब्रेरी घुमाव को संभालती है?** GroupDocs Viewer for Java `rotatePage` मेथड प्रदान करता है।  
- **क्या मैं Java के साथ PDF पृष्ठ घुमा सकता हूँ?** हाँ—उसी `rotatePage` कॉल का उपयोग करें; यह PDF, DOCX, XLSX और अन्य फ़ाइलों के लिए काम करता है।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए भुगतान किया गया लाइसेंस आवश्यक है।  
- **क्या यह ऑपरेशन मेमोरी‑गहन है?** नहीं, जब आप `Viewer` इंस्टेंस को तुरंत बंद कर देते हैं; नीचे प्रदर्शन टिप्स देखें।

## “पृष्ठ को 90 डिग्री घुमाना” क्या है?
पृष्ठ को 90 डिग्री घुमाने से पृष्ठ का अभिविन्यास पोर्ट्रेट से लैंडस्केप (या इसके विपरीत) में बदल जाता है, बिना मूल सामग्री को बदले। यह विशेष रूप से प्रस्तुतियों, केवल लैंडस्केप ग्राफ़िक्स को प्रिंट करने, या स्कैन किए गए दस्तावेज़ों को जो बगल में कैप्चर किए गए थे, सुधारने में उपयोगी है।

## GroupDocs Viewer for Java के साथ पृष्ठ क्यों घुमाएँ?
GroupDocs Viewer कई फ़ाइल फ़ॉर्मेट को संभालने की जटिलताओं को सरल बनाता है। यह आपको पृष्ठ‑स्तर के परिवर्तन—जैसे घुमाव—को लागू करने देता है, जबकि मूल फ़ाइल को अपरिवर्तित रखता है। API सुगम, थ्रेड‑सेफ़, और किसी भी Java 8+ रनटाइम पर काम करता है।

## पूर्वापेक्षाएँ
- **GroupDocs.Viewer for Java** (नवीनतम संस्करण)  
- **JDK 8** या नया  
- **Maven** (या Gradle) निर्भरता प्रबंधन के लिए  
- IntelliJ IDEA या Eclipse जैसे IDE  
- Java I/O की बुनियादी परिचितता  

## GroupDocs.Viewer for Java सेटअप करना
अपने `pom.xml` में GroupDocs रिपॉजिटरी और निर्भरता जोड़ें। यह स्निपेट मूल ट्यूटोरियल से अपरिवर्तित है:

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
- **Free trial** – GroupDocs साइट से डाउनलोड करें।  
- **Temporary license** – यदि आपको विस्तारित मूल्यांकन अवधि चाहिए तो अनुरोध करें।  
- **Full license** – उत्पादन परिनियोजन के लिए खरीदें।  

### बेसिक Viewer इनिशियलाइज़ेशन
निम्नलिखित कोड `Viewer` इंस्टेंस बनाने का न्यूनतम तरीका दिखाता है। इसे बिल्कुल जैसा दिखाया गया है वैसा ही रखें:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## चरण‑दर‑चरण कार्यान्वयन: पहला पृष्ठ 90 डिग्री घुमाएँ

### 1. आवश्यक पैकेज इम्पोर्ट करें
ये इम्पोर्ट्स आपको PDF रेंडरिंग विकल्प और रोटेशन enum तक पहुँच प्रदान करते हैं।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. आउटपुट स्थान निर्धारित करें और Viewer बनाएं
प्लेसहोल्डर पाथ को अपने वास्तविक डायरेक्टरीज़ से बदलें।

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
`rotatePage` मेथड पृष्ठ संख्या (1‑आधारित) और एक `Rotation` enum मान लेता है।

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. दस्तावेज़ रेंडर करें
अंत में, घुमाए गए PDF को जनरेट करने के लिए `view` कॉल करें।

```java
viewer.view(viewOptions);
```

#### यह कैसे काम करता है
- **PdfViewOptions** Viewer को PDF फ़ाइल आउटपुट करने के लिए बताता है।  
- **rotatePage(int, Rotation)** केवल निर्दिष्ट पृष्ठ को घुमाता है, बाकी को अपरिवर्तित छोड़ता है।  
- यह मेथड `ON_90_DEGREE`, `ON_180_DEGREE`, और `ON_270_DEGREE` को सपोर्ट करता है।  

## सामान्य समस्याएँ और समाधान
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| **FileNotFoundException** | गलत पाथ या फ़ोल्डर नहीं मौजूद | `YOUR_OUTPUT_DIRECTORY` और `YOUR_DOCUMENT_DIRECTORY` मौजूद हैं और पढ़ने योग्य हैं, यह सत्यापित करें। |
| **Unsupported file format** | Viewer द्वारा असमर्थित फ़ॉर्मेट को घुमाने की कोशिश | [GroupDocs Viewer supported formats] पेज देखें। |
| **No rotation visible** | गलत पृष्ठ संख्या (0‑आधारित) का उपयोग | याद रखें `rotatePage` **1‑आधारित** इंडेक्सिंग उपयोग करता है। |
| **Out‑of‑memory errors on large docs** | एक ही थ्रेड में कई बड़े फ़ाइलों को रेंडर करना | दस्तावेज़ों को क्रमिक रूप से प्रोसेस करें या सीमित समवर्तीता के साथ थ्रेड पूल उपयोग करें। |

## व्यावहारिक अनुप्रयोग
1. **प्रेजेंटेशन समायोजन** – पोर्ट्रेट स्लाइड को तुरंत लैंडस्केप में बदलें।  
2. **बड़े पैमाने पर दस्तावेज़ सुधार** – स्कैन किए गए PDF को जो बगल में कैप्चर हुए थे, स्वचालित रूप से ठीक करें।  
3. **प्रिंट‑तैयार आउटपुट** – लैंडस्केप ग्राफ़िक्स को पोर्ट्रेट‑ओरिएंटेड कागज़ पर सही ढंग से प्रिंट होना सुनिश्चित करें।  

## प्रदर्शन टिप्स
- **संसाधनों को तुरंत बंद करें** – `try‑with‑resources` ब्लॉक स्वचालित रूप से `Viewer` को डिस्पोज़ कर देता है।  
- **बैच प्रोसेसिंग** – कई फ़ाइलों को संभालते समय, ओवरहेड कम करने के लिए प्रति थ्रेड एक ही `Viewer` इंस्टेंस पुन: उपयोग करें।  
- **मेमोरी मॉनिटर करें** – 100 MB से बड़े दस्तावेज़ों के लिए, आउटपुट को मेमोरी में रखने के बजाय डिस्क पर स्ट्रीम करने पर विचार करें।  

## अक्सर पूछे जाने वाले प्रश्न
**प्रश्न: क्या मैं एक साथ कई पृष्ठ घुमा सकता हूँ?**  
**उत्तर:** हाँ—जिस प्रत्येक पृष्ठ को घुमाना है, उसके लिए `rotatePage()` कॉल करें।

**प्रश्न: रेंडरिंग के बाद घुमाव को वापस करने का कोई तरीका है?**  
**उत्तर:** सीधे नहीं। आपको बिना घुमाव विकल्पों के दस्तावेज़ को फिर से रेंडर करना पड़ेगा।

**प्रश्न: GroupDocs Viewer में कौन से फ़ाइल फ़ॉर्मेट पृष्ठ घुमाव को सपोर्ट करते हैं?**  
**उत्तर:** DOCX, PDF, PPTX, XLSX, और आधिकारिक दस्तावेज़ में सूचीबद्ध कई अन्य फ़ॉर्मेट।

**प्रश्न: मैं दस्तावेज़ों के बैच में पृष्ठों को स्वचालित रूप से कैसे घुमा सकता हूँ?**  
**उत्तर:** कोड को एक लूप में रखें जो फ़ाइल पाथ के संग्रह पर इटरेट करे, और प्रत्येक पर समान `rotatePage` लॉजिक लागू करे।

**प्रश्न: घुमाव के दौरान त्रुटियों को संभालने की सर्वोत्तम प्रथा क्या है?**  
**उत्तर:** Viewer उपयोग को `try‑catch` ब्लॉक में रखें, अपवाद को लॉग करें, और वैकल्पिक रूप से अगले फ़ाइल को प्रोसेस करना जारी रखें।

## संसाधन
- **डॉक्यूमेंटेशन**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API रेफ़रेंस**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **डाउनलोड**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **खरीदें**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **फ़्री ट्रायल**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **टेम्पररी लाइसेंस**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **सपोर्ट**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-01-18  
**परीक्षण किया गया:** GroupDocs Viewer 25.2 for Java  
**लेखक:** GroupDocs