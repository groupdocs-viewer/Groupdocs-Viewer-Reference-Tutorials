---
date: '2026-03-29'
description: GroupDocs Viewer का उपयोग करके Java में HTML view MPP बनाना सीखें, समय
  अंतराल के अनुसार प्रोजेक्ट दस्तावेज़ को चरण‑दर‑चरण कोड के साथ रेंडर करना।
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: GroupDocs Viewer (Java) के साथ MPP का HTML व्यू बनाएं
type: docs
url: /hi/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# GroupDocs Viewer का उपयोग करके जावा में समय अंतराल के अनुसार प्रोजेक्ट दस्तावेज़ों को रेंडर कैसे करें

इस ट्यूटोरियल में आप सीखेंगे कि GroupDocs Viewer for Java के साथ **create html view mpp** कैसे बनाएं, जिससे आप Microsoft Project फ़ाइल के केवल उन भागों को रेंडर कर सकेंगे जो किसी विशिष्ट समय अंतराल में आते हैं। हम Maven सेटअप, कोड कॉन्फ़िगरेशन और वास्तविक दुनिया के परिदृश्यों के माध्यम से चलेंगे ताकि आप अपने एप्लिकेशन में सीधे सटीक टाइमलाइन व्यू एम्बेड कर सकें।

![GroupDocs.Viewer for Java के साथ समय अंतराल द्वारा प्रोजेक्ट दस्तावेज़ रेंडर करना](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## त्वरित उत्तर
- **यह फीचर क्या करता है?** यह केवल Microsoft Project फ़ाइल के उस हिस्से को रेंडर करता है जो प्रारंभ और समाप्ति तिथि के बीच आता है।  
- **कौन सा आउटपुट फॉर्मेट उपयोग किया जाता है?** HTML जिसमें एम्बेडेड रिसोर्सेज होते हैं, वेब इंटीग्रेशन के लिए उपयुक्त।  
- **क्या मुझे लाइसेंस की आवश्यकता है?** मूल्यांकन के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या मैं रनटाइम पर डेट रेंज बदल सकता हूँ?** हाँ—रेंडरिंग विकल्पों में `setStartDate` और `setEndDate` मानों को समायोजित करें।  
- **क्या यह सभी Java संस्करणों पर समर्थित है?** Java 8+ के साथ काम करता है, बशर्ते आप GroupDocs.Viewer 25.2 या उससे नया उपयोग करें।

## प्रोजेक्ट दस्तावेज़ों के लिए html view mpp कैसे बनाएं
GroupDocs Viewer Microsoft Project फ़ाइलों (`.mpp`, `.mpt`) को HTML पेजों में बदल सकता है। रेंडरिंग विकल्पों में प्रारंभ और समाप्ति तिथियों को कॉन्फ़िगर करके, आप आउटपुट को उस समय स्लाइस तक सीमित कर सकते हैं जिसकी आपको आवश्यकता है, जिससे फ़ाइल आकार घटता है और पेज लोड तेज़ होते हैं।

## इस संदर्भ में “How to Use GroupDocs” क्या है?
GroupDocs Viewer एक Java लाइब्रेरी है जो 100 से अधिक फ़ाइल फ़ॉर्मेट को वेब‑फ्रेंडली प्रतिनिधित्व में बदलती है। जब आप प्रोजेक्ट फ़ाइलों के लिए **how to use GroupDocs** करते हैं, तो आपको शेड्यूल डेटा को निकालने, विज़ुअलाइज़ करने और साझा करने की क्षमता मिलती है, बिना क्लाइंट साइड पर Microsoft Project की आवश्यकता के।

## समय अंतराल के साथ प्रोजेक्ट दस्तावेज़ों को रेंडर क्यों करें?
- **केन्द्रित विश्लेषण:** केवल वह चरण दिखाएँ जो आपको चाहिए (जैसे, Q3 2024)।  
- **प्रदर्शन:** छोटा HTML आउटपुट तेज़ पेज लोड का मतलब है।  
- **इंटीग्रेशन:** टाइमलाइन व्यू को डैशबोर्ड, रिपोर्टिंग पोर्टल या कस्टम PM टूल्स में एम्बेड करें।  

## आवश्यकताएँ
- **GroupDocs.Viewer for Java** संस्करण 25.2 या उससे ऊपर।  
- Java Development Kit (JDK) 8 या नया।  
- IntelliJ IDEA या Eclipse जैसे IDE।  
- Maven का बुनियादी ज्ञान।  

## GroupDocs.Viewer for Java सेटअप करना

### Maven निर्भरता
अपने `pom.xml` में रिपॉजिटरी और निर्भरता जोड़ें:

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

### लाइसेंस प्राप्ति चरण
1. **Free Trial** – [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/) से ट्रायल संस्करण डाउनलोड करें।  
2. **Temporary License** – विस्तारित परीक्षण के लिए [this link](https://purchase.groupdocs.com/temporary-license/) से अस्थायी लाइसेंस प्राप्त करें।  
3. **Purchase** – बिना प्रतिबंध के प्रोडक्शन उपयोग के लिए, [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy) पर लाइसेंस खरीदें।  

### बेसिक व्यूअर इनिशियलाइज़ेशन
निम्नलिखित स्निपेट दिखाता है कि कैसे `Viewer` इंस्टेंस बनाएं जो Microsoft Project फ़ाइल (`.mpp`) की ओर इशारा करता है:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## स्टेप‑बाय‑स्टेप इम्प्लीमेंटेशन गाइड

### 1. आउटपुट डायरेक्टरी निर्धारित करें
एक फ़ोल्डर बनाएं जहाँ उत्पन्न HTML पेज़ सहेजे जाएंगे:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*क्यों?* रेंडर किए गए फ़ाइलों को व्यवस्थित रखने से उन्हें वेब सर्वर से सर्व करना या UI में एम्बेड करना आसान हो जाता है।

### 2. अपने प्रोजेक्ट फ़ाइल के साथ व्यूअर इनिशियलाइज़ करें
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*क्यों?* दस्तावेज़ लोड करने से आंतरिक पार्सर तैयार होता है और प्रोजेक्ट‑विशिष्ट मेटाडेटा उपलब्ध हो जाता है।

### 3. प्रोजेक्ट फ़ाइलों के लिए व्यू जानकारी प्राप्त करें
```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*क्यों?* `ProjectManagementViewInfo` आपको शेड्यूल की प्रारंभ और समाप्ति तिथियां देता है, जिन्हें आप बाद में रेंडरिंग स्कोप सीमित करने के लिए उपयोग करेंगे।

### 4. HTML रेंडरिंग विकल्प कॉन्फ़िगर करें (प्रोजेक्ट से HTML जनरेट करें)
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*क्यों?* `StartDate` और `EndDate` सेट करने से GroupDocs को केवल उस विंडो के भीतर **generate html view mpp** डेटा जनरेट करने को कहा जाता है।

### 5. रेंडरिंग प्रक्रिया निष्पादित करें
```java
viewer.view(viewOptions);
```

*क्यों?* यह कॉल आपके प्रोजेक्ट शेड्यूल के चयनित समय स्लाइस को दर्शाने वाले स्व-निहित HTML पेजों की श्रृंखला बनाता है।

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **Incorrect file paths** – यह सुनिश्चित करने के लिए दोबारा जांचें कि स्रोत `.mpp` फ़ाइल और आउटपुट डायरेक्टरी दोनों मौजूद हैं।  
- **Unsupported file type** – सुनिश्चित करें कि दस्तावेज़ एक समर्थित प्रोजेक्ट फ़ॉर्मेट है (जैसे, `.mpp`, `.mpt`).  
- **License errors** – ट्रायल लाइसेंस रेंडरिंग सीमा लगा सकता है; बिना प्रतिबंध के उपयोग के लिए पूर्ण लाइसेंस में स्विच करें।  

## व्यावहारिक अनुप्रयोग
1. **Project Timeline Analysis** – हितधारकों को केवल वर्तमान चरण दिखाएँ।  
2. **Automated Reporting** – साप्ताहिक स्थिति अपडेट के लिए समय‑सीमित HTML रिपोर्ट जनरेट करें।  
3. **Integration with Dashboards** – रेंडर किए गए पेजों को BI टूल्स या कस्टम पोर्टल में एम्बेड करें।  
4. **Archival** – भविष्य के संदर्भ के लिए प्रोजेक्ट शेड्यूल का वेब‑फ्रेंडली स्नैपशॉट संग्रहीत करें।  

## प्रदर्शन टिप्स
- *embedded resources* विकल्प का उपयोग करें ताकि प्रत्येक HTML पेज स्व-निहित रहे, जिससे HTTP अनुरोध कम हों।  
- बहुत बड़े प्रोजेक्ट्स के लिए, मेमोरी उपयोग कम रखने हेतु छोटे डेट चंक्स में रेंडरिंग पर विचार करें।  
- डिस्क बloat से बचने के लिए सर्व करने के बाद अस्थायी फ़ाइलों को साफ़ करें।  

## निष्कर्ष
अब आप जानते हैं कि **how to use GroupDocs** Viewer का उपयोग करके जावा में विशिष्ट समय अंतराल के भीतर प्रोजेक्ट दस्तावेज़ों को रेंडर किया जा सकता है और **generate HTML from project** डेटा जनरेट किया जा सकता है। यह क्षमता टाइमलाइन विज़ुअलाइज़ेशन को सरल बनाती है, रिपोर्टिंग दक्षता को सुधारती है, और आधुनिक वेब एप्लिकेशन के साथ सहजता से इंटीग्रेट होती है।

### अगले कदम
- वॉटरमार्किंग, पासवर्ड प्रोटेक्शन, या कस्टम CSS स्टाइलिंग जैसे अतिरिक्त Viewer फीचर्स का अन्वेषण करें।  
- इस रेंडरिंग पाइपलाइन को REST API के साथ संयोजित करके ऑन‑डिमांड टाइमलाइन व्यू सर्व करें।  

## अक्सर पूछे जाने वाले प्रश्न

**Q: GroupDocs.Viewer कौन से फ़ाइल फ़ॉर्मेट सपोर्ट करता है?**  
A: GroupDocs.Viewer कई फ़ॉर्मेट सपोर्ट करता है जिसमें Microsoft Project (MPP), PDF, Word, Excel, PowerPoint, और कई अन्य शामिल हैं।

**Q: GroupDocs.Viewer का फ्री ट्रायल कैसे शुरू करूँ?**  
A: आप ट्रायल संस्करण [here](https://releases.groupdocs.com/viewer/java/) से डाउनलोड कर सकते हैं।

**Q: क्या मैं रिसोर्सेज एम्बेड किए बिना दस्तावेज़ रेंडर कर सकता हूँ?**  
A: हाँ, आप एक अलग HTML व्यू विकल्प चुन सकते हैं जो एम्बेड करने के बजाय बाहरी रिसोर्सेज को रेफ़र करता है।

**Q: यदि मेरा दस्तावेज़ रेंडरिंग के लिए बहुत बड़ा है तो क्या करें?**  
A: दस्तावेज़ को छोटे सेक्शन में विभाजित करने या केवल आवश्यक डेट रेंज को रेंडर करने पर विचार करें, जैसा कि ऊपर दिखाया गया है।

**Q: रेंडरिंग त्रुटियों को कैसे संभालूँ?**  
A: सभी कॉन्फ़िगरेशन सेटिंग्स की जाँच करें, सुनिश्चित करें कि आपके पास वैध लाइसेंस है, और विस्तृत एरर कोड के लिए GroupDocs दस्तावेज़ देखें।

## संसाधन
- **डॉक्यूमेंटेशन**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API रेफ़रेंस**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **डाउनलोड**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **खरीद**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **फ्री ट्रायल**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **अस्थायी लाइसेंस**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **सपोर्ट**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-03-29  
**परीक्षण किया गया:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs