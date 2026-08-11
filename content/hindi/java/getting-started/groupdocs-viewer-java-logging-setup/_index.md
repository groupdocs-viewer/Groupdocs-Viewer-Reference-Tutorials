---
date: '2026-04-10'
description: GroupDocs.Viewer for Java में लॉगिंग को कॉन्फ़िगर करना सीखें, जिसमें
  बेहतर दस्तावेज़ रेंडरिंग के लिए कंसोल लॉगर और फ़ाइल लॉगर जोड़ना शामिल है।
keywords:
- how to configure logging
- add console logger
- add file logger
- java logging best practices
- html view options
title: GroupDocs.Viewer for Java में लॉगिंग कैसे कॉन्फ़िगर करें
type: docs
url: /hi/java/getting-started/groupdocs-viewer-java-logging-setup/
weight: 1
---

# GroupDocs.Viewer for Java में लॉगिंग को कॉन्फ़िगर करने का तरीका

इस ट्यूटोरियल में, आप GroupDocs.Viewer for Java में **लॉगिंग को कॉन्फ़िगर करने** का तरीका सीखेंगे, जो आपको दस्तावेज़ रेंडरिंग पाइपलाइन की वास्तविक‑समय अंतर्दृष्टि देता है और समस्याओं को जल्दी से हल करने में मदद करता है।

## त्वरित उत्तर
- **लॉगिंग क्या प्रदान करता है?** रेंडरिंग ऑपरेशन्स और त्रुटि विवरणों पर वास्तविक‑समय प्रतिक्रिया।  
- **कौन सा लॉगर कंसोल में प्रिंट करता है?** `ConsoleLogger` (कंसोल लॉगर जोड़ें)।  
- **कौन सा लॉगर फ़ाइल में लिखता है?** `FileLogger` (फ़ाइल लॉगर जोड़ें)।  
- **क्या लॉगिंग सक्षम करने के लिए लाइसेंस आवश्यक है?** नहीं, लॉगिंग ट्रायल और लाइसेंस्ड दोनों संस्करणों में काम करती है।  
- **क्या मैं लॉग फ़ॉर्मेट को कस्टमाइज़ कर सकता हूँ?** हाँ, लॉगर क्लासेस को एक्स्टेंड करके।

## परिचय
Java एप्लिकेशनों में **GroupDocs.Viewer for Java** का उपयोग करके अपने दस्तावेज़ रेंडरिंग प्रक्रिया को बेहतर बनाएं। यह गाइड आपको कंसोल या फ़ाइल दोनों में लॉगिंग कॉन्फ़िगर करने के चरण दिखाता है, जिससे आपके दस्तावेज़ रेंडरिंग के संचालन के बारे में महत्वपूर्ण अंतर्दृष्टि मिलती है।

![GroupDocs.Viewer for Java के साथ कंसोल और फ़ाइल लॉगिंग](/viewer/getting-started/console-and-file-logging-java.png)

**मुख्य सीखने बिंदु:**
- GroupDocs.Viewer for Java में लॉगिंग को कॉन्फ़िगर करें।  
- कंसोल और फ़ाइल‑आधारित दोनों लॉगिंग सिस्टम लागू करें।  
- GroupDocs.Viewer का उपयोग करके एम्बेडेड रिसोर्सेज़ के साथ HTML में दस्तावेज़ रेंडर करें।

## पूर्वापेक्षाएँ
सुनिश्चित करें कि आपके पास है:

1. **आवश्यक लाइब्रेरीज़:**  
   - GroupDocs.Viewer for Java लाइब्रेरी (संस्करण 25.2 या बाद का)।  

2. **पर्यावरण सेटअप आवश्यकताएँ:**  
   - आपके सिस्टम पर स्थापित Java Development Kit (JDK)।  
   - IntelliJ IDEA या Eclipse जैसे Integrated Development Environment (IDE)।  

3. **ज्ञान पूर्वापेक्षाएँ:**  
   - Java प्रोग्रामिंग की बुनियादी समझ।  
   - डिपेंडेंसी मैनेजमेंट के लिए Maven की परिचितता।  

इन पूर्वापेक्षाओं के साथ, आप GroupDocs.Viewer for Java सेट अप करने के लिए तैयार हैं!

## GroupDocs.Viewer for Java सेट अप करना
GroupDocs.Viewer का उपयोग करने के लिए, Maven के माध्यम से इसे अपने प्रोजेक्ट में एक डिपेंडेंसी के रूप में जोड़ें। यह रहा तरीका:

### Maven सेटअप
`pom.xml` फ़ाइल में निम्न कॉन्फ़िगरेशन जोड़ें:
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
- **फ़्री ट्रायल:** [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) से एक फ़्री ट्रायल डाउनलोड करें।  
- **टेम्पररी लाइसेंस:** मूल्यांकन सीमाओं को हटाने के लिए [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) से एक टेम्पररी लाइसेंस प्राप्त करें।  
- **खरीद:** पूर्ण एक्सेस के लिए, [GroupDocs Purchase](https://purchase.groupdocs.com/buy) पर लाइसेंस खरीदने पर विचार करें।

### बेसिक इनिशियलाइज़ेशन
निम्न पैटर्न के साथ GroupDocs.Viewer को इनिशियलाइज़ करें:
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

// Initialize with sample PDF file and settings
try (Viewer viewer = new Viewer("path/to/your/document.pdf")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```

यह सेटअप अधिक जटिल लॉगिंग कॉन्फ़िगरेशन के लिए आधार बनाता है।

## लॉगिंग को कैसे कॉन्फ़िगर करें
GroupDocs.Viewer के साथ **कंसोल लॉगर जोड़ना** और **फ़ाइल लॉगर जोड़ना** कैसे है, देखें।

### फीचर 1: कंसोल में लॉगिंग
#### अवलोकन
कंसोल में लॉगिंग आपके टर्मिनल में तुरंत फीडबैक देती है, जो विकास या डिबगिंग चरणों में उपयोगी है।

#### चरण
##### चरण 1: आवश्यक क्लासेस इम्पोर्ट करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.ConsoleLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### चरण 2: लॉगिंग कॉन्फ़िगरेशन सेट अप करें
`ConsoleLogger` का उपयोग करके लॉग्स को कंसोल पर निर्देशित करें।
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new ConsoleLogger()))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**व्याख्या**  
- **ConsoleLogger:** यह क्लास लॉग्स को कंसोल पर भेजती है, जिससे ऑपरेशन्स का वास्तविक‑समय दृश्य मिलता है।  
- **HtmlViewOptions.forEmbeddedResources:** प्रत्येक पेज के लिए एम्बेडेड रिसोर्सेज़ के साथ HTML जनरेट करता है, जो **html view options** के प्रभावी उपयोग का एक उदाहरण है।

#### ट्रबलशूटिंग टिप्स
सुनिश्चित करें कि आपका दस्तावेज़ पाथ सही और एक्सेसिबल है। यह जाँचें कि लॉगिंग स्टेटमेंट्स आपके कंसोल सेटिंग्स में सही ढंग से कॉन्फ़िगर हैं।

### फीचर 2: फ़ाइल में लॉगिंग
#### अवलोकन
फ़ाइल में लॉगिंग ऑपरेशन्स का स्थायी रिकॉर्ड रखने में मदद करती है, जो ऑडिटिंग या पोस्ट‑मॉर्टेम विश्लेषण के लिए उपयोगी है।

#### चरण
##### चरण 1: आवश्यक क्लासेस इम्पोर्ट करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.ViewerSettings;
import com.groupdocs.viewer.logging.FileLogger;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

##### चरण 2: फ़ाइल‑आधारित लॉगिंग कॉन्फ़िगरेशन सेट अप करें
`FileLogger` का उपयोग करके लॉग्स को निर्दिष्ट फ़ाइल में लिखें।
```java
try (Viewer viewer = new Viewer("path/to/your/document.pdf", 
    new ViewerSettings(new FileLogger("output.log")))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/page_{0}.html");
    viewer.view(options);
}
```
**व्याख्या**  
- **FileLogger:** यह क्लास लॉग्स को `output.log` नामक फ़ाइल में भेजती है।  
- **ViewerSettings with FileLogger:** GroupDocs.Viewer को निर्दिष्ट लॉग फ़ाइल में **व्यूअर लॉग्स कैप्चर** करने के लिए कॉन्फ़िगर करता है।

#### ट्रबलशूटिंग टिप्स
सुनिश्चित करें कि आउटपुट फ़ाइल के लिए डायरेक्टरी लिखने योग्य है। यदि लॉगिंग फेल हो तो फ़ाइल परमिशन चेक करें।

## व्यावहारिक अनुप्रयोग
GroupDocs.Viewer दस्तावेज़ प्रबंधन और रेंडरिंग क्षमताओं को बढ़ा सकता है:

1. **वेब पोर्टल्स:** वेब उपयोगकर्ताओं के लिए सीधे डाउनलोड किए बिना ऑन‑द‑फ्लाई दस्तावेज़ रेंडर करें।  
2. **एंटरप्राइज़ सिस्टम्स:** कॉन्ट्रैक्ट्स या एग्रीमेंट्स दिखाने के लिए CRM टूल्स के साथ इंटीग्रेट करें।  
3. **इंट्रानेट डैशबोर्ड्स:** इंट्रानेट के भीतर रिपोर्ट्स और प्रेजेंटेशन्स के सुलभ दृश्य प्रदान करें।

## प्रदर्शन विचार एवं Java लॉगिंग बेस्ट प्रैक्टिसेज
Java में GroupDocs.Viewer का उपयोग करते समय, इन बिंदुओं को ध्यान में रखें:

- **रिसोर्स उपयोग को ऑप्टिमाइज़ करें:** बड़े दस्तावेज़ रेंडर करते समय मेमोरी खपत की निगरानी करें।  
- **Java मेमोरी मैनेजमेंट:** ऑटोमैटिक रिसोर्स क्लीनअप के लिए try‑with‑resources का उपयोग करें।  
- **लॉगिंग वर्बोसिटी:** विवरण और प्रदर्शन प्रभाव के बीच संतुलन बनाने के लिए लॉगर लेवल्स (जैसे INFO, DEBUG) को समायोजित करें—जो **java logging best practices** का एक आवश्यक हिस्सा है।

## निष्कर्ष
आपने GroupDocs.Viewer for Java में **लॉगिंग को कॉन्फ़िगर करने** का तरीका सीख लिया है, चाहे आपको तेज़ कंसोल व्यू चाहिए या स्थायी फ़ाइल रिकॉर्ड। यह क्षमता डिबगिंग, मॉनिटरिंग और आपके एप्लिकेशनों के ऑडिटिंग के लिए अमूल्य है। आगे की कॉन्फ़िगरेशन देखें, कस्टम लॉगर्स के साथ प्रयोग करें, और GroupDocs.Viewer को अन्य सिस्टम्स के साथ इंटीग्रेट करके मजबूती बढ़ाएँ।

क्या आप अपनी इम्प्लीमेंटेशन स्किल्स को अगले स्तर पर ले जाने के लिए तैयार हैं? विभिन्न वातावरणों में लॉगिंग सेट अप करके देखें कि यह आपके एप्लिकेशन की विश्वसनीयता को कैसे बढ़ाता है!

## संसाधन
- [डॉक्यूमेंटेशन](https://docs.groupdocs.com/viewer/java/)
- [API रेफ़रेंस](https://reference.groupdocs.com/viewer/java/)
- [डाउनलोड](https://downloads.groupdocs.com/viewer/java/)

---

**अंतिम अपडेट:** 2026-04-10  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs