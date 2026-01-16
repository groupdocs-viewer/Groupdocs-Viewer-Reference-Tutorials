---
date: '2025-12-23'
description: GroupDocs.Viewer का उपयोग करके एक्सेल प्रिंट एरिया को रेंडर करके जावा
  में दस्तावेज़ प्रीव्यू बनाना सीखें। कुशल जावा प्रीव्यू समाधान के लिए चरण‑दर‑चरण
  मार्गदर्शिका।
keywords:
- Java spreadsheet print areas rendering
- rendering print areas with GroupDocs.Viewer for Java
- efficient document preview solutions
title: 'जावा में दस्तावेज़ पूर्वावलोकन बनाएं - GroupDocs.Viewer के साथ स्प्रेडशीट प्रिंट
  क्षेत्रों को रेंडर करें'
type: docs
url: /hi/java/advanced-rendering/java-groupdocs-viewer-render-print-areas-spreadsheet/
weight: 1
---

# दस्तावेज़ प्रीव्यू जावा बनाएं: GroupDocs.Viewer के साथ स्प्रेडशीट प्रिंट एरिया रेंडर करें

स्प्रेडशीट के केवल प्रिंट‑एरिया सेक्शन को रेंडर करने से आपके उपयोगकर्ताओं को स्कैन करने वाले डेटा की मात्रा में काफी कमी आ सकती है, जिससे दस्तावेज़ प्रीव्यू तेज़ और अधिक केंद्रित हो जाता है। इस गाइड में आप **create document preview java** प्रोजेक्ट बनाएँगे जो केवल परिभाषित प्रिंट एरिया को रेंडर करेंगे, **GroupDocs.Viewer for Java** का उपयोग करके। हम सेटअप, कॉन्फ़िगरेशन और वास्तविक उपयोग के चरणों के माध्यम से चलेंगे ताकि आप जल्दी से इस क्षमता को अपने एप्लिकेशन में जोड़ सकें।

![GroupDocs.Viewer for Java के साथ स्प्रेडशीट प्रिंट एरिया रेंडरिंग](/viewer/advanced-rendering/spreadsheet-print-areas-rendering-java.png)

## त्वरित उत्तर
- **“create document preview java” का क्या अर्थ है?** यह जावा कोड से सीधे एक दस्तावेज़ का दृश्य प्रतिनिधित्व (HTML, इमेज, PDF) उत्पन्न करने को दर्शाता है।  
- **क्यों केवल एक्सेल प्रिंट एरिया को रेंडर करें?** यह सबसे प्रासंगिक डेटा को अलग करता है, जिससे रेंडरिंग समय और बैंडविड्थ कम होती है।  
- **क्या इसे आज़माने के लिए लाइसेंस चाहिए?** एक मुफ्त ट्रायल या अस्थायी लाइसेंस उपलब्ध है; प्रोडक्शन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **कौन सा जावा संस्करण समर्थित है?** जावा 8 या उससे नया।  
- **क्या मैं प्रीव्यू को वेब पेज में एम्बेड कर सकता हूँ?** हाँ—एम्बेडेड‑रिसोर्सेज़ विकल्प का उपयोग करके सेल्फ‑कंटेन्ड HTML पेज बनाएं।  

## “create document preview java” क्या है?
जावा में दस्तावेज़ प्रीव्यू बनाना मतलब प्रोग्रामेटिकली एक स्रोत फ़ाइल (जैसे XLSX वर्कबुक) को ऐसे फ़ॉर्मेट में बदलना है जिसे ब्राउज़र या अन्य UI कंपोनेंट्स में मूल एप्लिकेशन खोले बिना दिखाया जा सके। यह तरीका पोर्टल, इंट्रानेट और SaaS प्लेटफ़ॉर्म के लिए आवश्यक है जिन्हें दस्तावेज़ सामग्री को तेज़ और सुरक्षित रूप से दिखाना होता है।

## क्यों केवल एक्सेल प्रिंट एरिया को रेंडर करें?
- **प्रदर्शन:** छोटे HTML पेलोड तेज़ लोड होते हैं।  
- **स्पष्टता:** उपयोगकर्ता केवल प्रिंट के लिए चिह्नित सेक्शन देखते हैं, जिससे अव्यवस्था नहीं होती।  
- **सुरक्षा:** अनचाहे वर्कशीट प्रीव्यू में छिपे रहते हैं।  

## पूर्वापेक्षाएँ
- **GroupDocs.Viewer for Java** v25.2 या बाद का।  
- आपके विकास मशीन पर Maven स्थापित हो।  
- JDK 8 या नया (Java 11 सिफ़ारिश)।  
- एक IDE (IntelliJ IDEA, Eclipse, या VS Code)।  

## GroupDocs.Viewer for Java सेटअप करना
`pom.xml` में GroupDocs रिपॉज़िटरी और डिपेंडेंसी जोड़ें:

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
शुरुआत **मुफ़्त ट्रायल** से करें या मूल्यांकन के लिए **अस्थायी लाइसेंस** का अनुरोध करें। जब आप प्रोडक्शन के लिए तैयार हों, सभी फीचर अनलॉक करने और ट्रायल सीमाओं को हटाने के लिए पूर्ण लाइसेंस खरीदें।

### बेसिक इनिशियलाइज़ेशन
नीचे वह न्यूनतम कोड है जो GroupDocs.Viewer के साथ स्प्रेडशीट खोलने के लिए आवश्यक है:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer object with the path to your spreadsheet
try (Viewer viewer = new Viewer("path/to/your/spreadsheet.xlsx")) {
    // Further configurations will be discussed in upcoming sections.
}
```

## GroupDocs.Viewer के साथ **create document preview java** कैसे बनाएं
नीचे एक चरण‑दर‑चरण walkthrough है जो केवल **render excel print area** करता है, और सेल्फ‑कंटेन्ड HTML फ़ाइलें बनाता है।

### चरण 1: आउटपुट डायरेक्टरी और फ़ाइल पाथ फ़ॉर्मेट निर्धारित करें
पहले, व्यूअर को बताएं कि उत्पन्न HTML पेज कहां लिखे जाएँ।

```java
import java.nio.file.Path;
import java.nio.file.Paths;

// Set the output directory path
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");

// Define a file path format for the rendered pages
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*व्याख्या:* `outputDirectory` वह फ़ोल्डर है जो सभी प्रीव्यू फ़ाइलें रखेगा। `pageFilePathFormat` एक प्लेसहोल्डर (`{0}`) उपयोग करता है जिसे व्यूअर पेज नंबर से बदलता है।

### चरण 2: प्रिंट‑एरिया रेंडरिंग के लिए HTML व्यू विकल्प कॉन्फ़िगर करें
व्यूअर को कॉन्फ़िगर करें ताकि वह रिसोर्सेज़ (CSS, इमेज) सीधे एम्बेड करे और परिभाषित प्रिंट एरिया पर फोकस करे।

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
import com.groupdocs.viewer.options.SpreadsheetOptions;

// Configure HTML view options with embedded resources and print area rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forRenderingPrintArea());
```

*व्याख्या:* `HtmlViewOptions.forEmbeddedResources` प्रत्येक पेज के लिए एकल HTML फ़ाइल बनाता है जिसमें सभी CSS/JS इनलाइन होते हैं, जिससे डिप्लॉयमेंट सरल हो जाता है। `forRenderingPrintArea()` इंजन को केवल **render excel print area** करने के लिए बताता है।

### चरण 3: स्प्रेडशीट लोड करें और रेंडर करें
अंत में, व्यूअर को अपने वर्कबुक की ओर इंगित करें और रेंडरिंग प्रक्रिया को कॉल करें।

```java
// Replace with your actual document path
Path documentPath = Paths.get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_XLSX_WITH_PRINT_AREAS.xlsx");

try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Render to HTML using the configured view options
    viewer.view(viewOptions);
}
```

*व्याख्या:* `view()` मेथड सेट किए गए विकल्पों के अनुसार वर्कबुक को प्रोसेस करता है, और केवल प्रिंट‑एरिया सेक्शन दिखाने वाली HTML फ़ाइलें आउटपुट करता है।

## सामान्य समस्याएँ और समाधान
- **फ़ाइल‑पाथ त्रुटियाँ:** सुनिश्चित करें कि पाथ एब्सोल्यूट हैं या आपके प्रोजेक्ट की वर्किंग डायरेक्टरी के सापेक्ष सही हैं।  
- **परमीशन समस्याएँ:** जावा प्रोसेस को स्रोत फ़ाइल पढ़ने और आउटपुट फ़ोल्डर में लिखने की अनुमति हो।  
- **प्रिंट एरिया नहीं मिल रहा:** जाँचें कि स्प्रेडशीट में वास्तव में प्रिंट एरिया परिभाषित है (Excel में Page Layout → Print Area)।  

## व्यावहारिक उपयोग
1. **डॉक्यूमेंट मैनेजमेंट सिस्टम:** पूरे वर्कबुक को लोड किए बिना रिपोर्ट का साफ़ प्रीव्यू उपयोगकर्ताओं को दिखाएँ।  
2. **फ़ाइनेंशियल डैशबोर्ड:** प्रिंट एरिया के रूप में चिह्नित प्रमुख वित्तीय टेबल्स के HTML स्नैपशॉट ऑटो‑जनरेट करें।  
3. **लर्निंग प्लेटफ़ॉर्म:** छात्रों को असाइनमेंट डेटा के फोकस्ड व्यू प्रदान करें।  
4. **CRM पोर्टल:** ग्राहक मीट्रिक्स को हाइलाइट करें जबकि आंतरिक वर्कशीट छिपी रहें।  
5. **डेटा‑साइंस नोटबुक:** दस्तावेज़ीकरण में संक्षिप्त स्प्रेडशीट प्रीव्यू एम्बेड करें।  

## प्रदर्शन टिप्स
- **मेमोरी ट्यूनिंग:** बहुत बड़े वर्कबुक के लिए JVM हीप बढ़ाएँ (`-Xmx2g` या अधिक)।  
- **लेज़ी लोडिंग:** यदि केवल पहले कुछ पेज चाहिए, तो आवश्यक पेजों के बाद रेंडरिंग रोकें।  
- **पैरेलल प्रोसेसिंग:** अलग-अलग `Viewer` इंस्टेंस (प्रत्येक अपने थ्रेड में) का उपयोग करके कई वर्कबुक एक साथ रेंडर करें।  

## निष्कर्ष
अब आप जानते हैं कि कैसे **create document preview java** समाधान बनाएं जो स्प्रेडशीट के केवल परिभाषित प्रिंट एरिया को रेंडर करते हैं। यह तकनीक प्रीव्यू को तेज़, साफ़ और अधिक सुरक्षित बनाती है—आधुनिक वेब और एंटरप्राइज़ एप्लिकेशन के लिए उपयुक्त।

### अगले कदम
- `PdfViewOptions` या `PngViewOptions` का उपयोग करके अन्य व्यू फ़ॉर्मेट (PDF, PNG) के साथ प्रयोग करें।  
- संवेदनशील डेटा की सुरक्षा के लिए प्रीव्यू जेनरेशन को ऑथेंटिकेशन के साथ संयोजित करें।  
- कस्टम पेज साइजिंग, ग्रिडलाइन आदि के लिए पूर्ण `SpreadsheetOptions` API देखें।  

## FAQ सेक्शन
**Q: केवल एक्सेल प्रिंट एरिया को रेंडर करने का मुख्य लाभ क्या है?**  
A: यह अव्यवस्था कम करता है और रेंडरिंग को तेज़ करता है, एक फोकस्ड प्रीव्यू प्रदान करता है जो सबसे महत्वपूर्ण डेटा को हाइलाइट करता है।

**Q: क्या मैं गैर‑प्रिंटेबल वर्कशीट भी रेंडर कर सकता हूँ?**  
A: हाँ—`SpreadsheetOptions.forRenderingPrintArea()` को हटाएँ और डिफ़ॉल्ट विकल्पों का उपयोग करके पूरे वर्कबुक को रेंडर करें।

**Q: क्या GroupDocs.Viewer अन्य स्प्रेडशीट फ़ॉर्मेट्स को सपोर्ट करता है?**  
A: यह XLS, XLSX, CSV, ODS और कई अन्य फ़ॉर्मेट्स को संभालता है। पूरी सूची के लिए आधिकारिक डॉक्यूमेंट देखें।

**Q: बहुत बड़े फ़ाइलों के लिए रेंडरिंग स्पीड कैसे बढ़ा सकता हूँ?**  
A: JVM हीप साइज बढ़ाएँ, केवल आवश्यक पेज रेंडर करें, और मल्टी‑थ्रेडेड प्रोसेसिंग पर विचार करें।

**Q: मेरे प्रिंट एरिया नहीं दिख रहे—मुझे क्या जांचना चाहिए?**  
A: सुनिश्चित करें कि स्रोत फ़ाइल में प्रिंट एरिया परिभाषित है (Excel → Page Layout → Print Area) और आप नवीनतम GroupDocs.Viewer संस्करण का उपयोग कर रहे हैं।

## संसाधन
- **डॉक्यूमेंटेशन:** [GroupDocs.Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API रेफ़रेंस:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **डाउनलोड:** [Get GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)
- **खरीदें:** [Buy a License](https://purchase.groupdocs.com/buy)
- **फ़्री ट्रायल:** [Start with a Free Trial](https://releases.groupdocs.com/viewer/java/)
- **अस्थायी लाइसेंस:** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **सपोर्ट:** [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2025-12-23  
**परीक्षित संस्करण:** GroupDocs.Viewer for Java 25.2  
**लेखक:** GroupDocs