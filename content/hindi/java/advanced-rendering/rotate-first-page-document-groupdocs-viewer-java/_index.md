---
date: '2026-03-29'
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

जब आपको किसी दस्तावेज़ में **पृष्ठ को 90 डिग्री घुमाने** की आवश्यकता होती है—चाहे वह PDF, Word फ़ाइल, या स्प्रेडशीट हो—तो इसे प्रोग्रामेटिक रूप से करने से समय बचता है और मैन्युअल त्रुटियों से बचा जा सकता है। इस उन्नत गाइड में हम **GroupDocs Viewer for Java** का उपयोग करके किसी भी समर्थित दस्तावेज़ के पहले पृष्ठ को घुमाने के सटीक चरणों को दिखाएंगे। अंत तक, आपके पास एक पुन: उपयोग योग्य स्निपेट होगा जिसे आप अपने प्रोजेक्ट्स में सम्मिलित कर सकते हैं।  
हम यह भी चर्चा करेंगे कि जावा में पृष्ठ घुमाना क्यों महत्वपूर्ण है, किन सामान्य परिस्थितियों में यह तकनीक उपयोगी है, और ऑपरेशन को हल्का कैसे रखें।

![GroupDocs.Viewer for Java के साथ दस्तावेज़ के पहले पृष्ठ को घुमाएँ](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## त्वरित उत्तर
- **“rotate page 90 degrees” का क्या अर्थ है?** यह चयनित पृष्ठ को घड़ी की दिशा में एक चौथाई घुमाव द्वारा घुमाता है।  
- **कौन सा लाइब्रेरी घुमाव को संभालता है?** GroupDocs Viewer for Java `rotatePage` मेथड प्रदान करता है।  
- **क्या मैं जावा के साथ PDF पृष्ठ घुमा सकता हूँ?** हाँ—उसी `rotatePage` कॉल का उपयोग करें; यह PDF, DOCX, XLSX और अन्य फ़ाइलों के लिए काम करता है।  
- **क्या मुझे लाइसेंस चाहिए?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए भुगतान किया गया लाइसेंस आवश्यक है।  
- **क्या यह ऑपरेशन मेमोरी‑गहन है?** जब आप `Viewer` इंस्टेंस को तुरंत बंद कर देते हैं तो नहीं; नीचे प्रदर्शन सुझाव देखें।

## “rotate page 90 degrees” क्या है?
पृष्ठ को 90 डिग्री घुमाने से पृष्ठ को पोर्ट्रेट से लैंडस्केप (या इसके विपरीत) में पुनः व्यवस्थित किया जाता है, बिना मूल सामग्री को बदले। यह विशेष रूप से प्रस्तुतियों, केवल लैंडस्केप ग्राफ़िक्स को प्रिंट करने, या स्कैन किए गए दस्तावेज़ों को जो बगल में कैप्चर हुए थे, सुधारने के लिए उपयोगी है।

## GroupDocs Viewer for Java के साथ पृष्ठों को प्रोग्रामेटिक रूप से क्यों घुमाएँ?
GroupDocs Viewer कई फ़ाइल फ़ॉर्मैट्स को संभालने की जटिलताओं को सरल बनाता है। यह आपको पृष्ठ‑स्तर के परिवर्तन—जैसे घुमाव—को लागू करने देता है जबकि मूल फ़ाइल को अपरिवर्तित रखता है। API सहज, थ्रेड‑सेफ़ है, और किसी भी Java 8+ रनटाइम पर काम करता है, जिससे यह एंटरप्राइज़‑ग्रेड ऑटोमेशन के लिए एक विश्वसनीय विकल्प बनता है।

## पूर्वापेक्षाएँ

- **GroupDocs.Viewer for Java** (नवीनतम संस्करण)
- **JDK 8** या नया
- **Maven** (या Gradle) निर्भरता प्रबंधन के लिए
- IntelliJ IDEA या Eclipse जैसे IDE
- Java I/O की बुनियादी परिचितता

## GroupDocs.Viewer for Java की सेटअप

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

### बेसिक Viewer प्रारंभिककरण
निम्नलिखित कोड `Viewer` इंस्टेंस बनाने का न्यूनतम तरीका दिखाता है। इसे बिल्कुल जैसा दिखाया गया है वैसा ही रखें:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## GroupDocs Viewer के साथ Java में PDF पृष्ठ कैसे घुमाएँ
हालाँकि API कई फ़ॉर्मैट्स पर काम करता है, PDF पृष्ठ घुमाने के लिए सबसे सामान्य उपयोग केस है। वही `rotatePage` मेथड उपयोग किया जाता है, इसलिए आपको केवल Viewer को PDF फ़ाइल की ओर इंगित करना है और पृष्ठ संख्या निर्दिष्ट करनी है।

## चरण‑दर‑चरण कार्यान्वयन: पहले पृष्ठ को 90 डिग्री घुमाएँ

### 1. आवश्यक पैकेज आयात करें
ये इम्पोर्ट्स आपको PDF रेंडरिंग विकल्प और रोटेशन enum तक पहुंच देते हैं।

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
अंत में, घुमाए गए PDF को उत्पन्न करने के लिए `view` कॉल करें।

```java
viewer.view(viewOptions);
```

#### यह कैसे काम करता है
- **PdfViewOptions** Viewer को PDF फ़ाइल आउटपुट करने के लिए बताता है।  
- **rotatePage(int, Rotation)** केवल निर्दिष्ट पृष्ठ को घुमाता है, बाकी को अपरिवर्तित छोड़ता है।  
- यह मेथड `ON_90_DEGREE`, `ON_180_DEGREE`, और `ON_270_DEGREE` का समर्थन करता है।

## सामान्य समस्याएँ और समाधान

| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| **FileNotFoundException** | गलत पथ या फ़ोल्डर अनुपलब्ध | `YOUR_OUTPUT_DIRECTORY` और `YOUR_DOCUMENT_DIRECTORY` मौजूद हैं और पढ़ने योग्य हैं, यह सत्यापित करें। |
| **Unsupported file format** | Viewer द्वारा समर्थित नहीं फ़ॉर्मेट को घुमाने का प्रयास | [GroupDocs Viewer supported formats] पृष्ठ देखें। |
| **No rotation visible** | गलत पृष्ठ संख्या (0‑आधारित) का उपयोग करना | ध्यान रखें `rotatePage` **1‑आधारित** इंडेक्सिंग का उपयोग करता है। |
| **Out‑of‑memory errors on large docs** | एक ही थ्रेड में कई बड़ी फ़ाइलें रेंडर करना | दस्तावेज़ों को क्रमिक रूप से प्रोसेस करें या सीमित समवर्तीता वाले थ्रेड पूल का उपयोग करें। |

## व्यावहारिक अनुप्रयोग

1. **Presentation adjustments** – तुरंत पोर्ट्रेट स्लाइड को लैंडस्केप में बदलें।  
2. **Bulk document correction** – स्कैन किए गए PDF जिन्हें बगल में कैप्चर किया गया था, उन्हें स्वचालित रूप से सुधारें।  
3. **Print‑ready output** – लैंडस्केप ग्राफ़िक्स को पोर्ट्रेट‑ओरिएंटेड कागज पर सही ढंग से प्रिंट होना सुनिश्चित करें।  

## प्रदर्शन सुझाव

- **Close resources promptly** – `try‑with‑resources` ब्लॉक स्वचालित रूप से `Viewer` को डिस्पोज़ कर देता है।  
- **Batch processing** – कई फ़ाइलों को संभालते समय, ओवरहेड कम करने के लिए प्रति थ्रेड एक ही `Viewer` इंस्टेंस पुन: उपयोग करें।  
- **Monitor memory** – 100 MB से बड़े दस्तावेज़ों के लिए, आउटपुट को मेमोरी में रखने के बजाय डिस्क पर स्ट्रीम करने पर विचार करें।  

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं एक साथ कई पृष्ठ घुमा सकता हूँ?**  
A: हाँ—जिस प्रत्येक पृष्ठ संख्या को घुमाने की आवश्यकता है, उसके लिए `rotatePage()` कॉल करें।

**Q: क्या रेंडरिंग के बाद घुमाव को वापस करने का कोई तरीका है?**  
A: सीधे नहीं। आपको बिना घुमाव विकल्पों के दस्तावेज़ को फिर से रेंडर करना होगा।

**Q: कौन से फ़ाइल फ़ॉर्मैट्स GroupDocs Viewer में पृष्ठ घुमाव का समर्थन करते हैं?**  
A: DOCX, PDF, PPTX, XLSX, और आधिकारिक दस्तावेज़ में सूचीबद्ध कई अन्य फ़ॉर्मैट्स।

**Q: मैं दस्तावेज़ों के बैच में पृष्ठों को स्वचालित रूप से कैसे घुमा सकता हूँ?**  
A: कोड को एक लूप में रखें जो फ़ाइल पाथ्स के संग्रह पर इटररेट करे, और प्रत्येक पर समान `rotatePage` लॉजिक लागू करे।

**Q: घुमाव के दौरान त्रुटियों को संभालने की सर्वश्रेष्ठ प्रथा क्या है?**  
A: Viewer उपयोग को `try‑catch` ब्लॉक में रखें, अपवाद को लॉग करें, और वैकल्पिक रूप से अगले फ़ाइल को प्रोसेस करना जारी रखें।

## संसाधन

- **दस्तावेज़ीकरण**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API संदर्भ**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **डाउनलोड**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **खरीद**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **मुफ़्त ट्रायल**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **अस्थायी लाइसेंस**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **समर्थन**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-03-29  
**परीक्षित संस्करण:** GroupDocs Viewer 25.2 for Java  
**लेखक:** GroupDocs