---
date: '2026-02-23'
description: GroupDocs.Viewer Java का उपयोग करके पृष्ठ प्रति आइटम सेट करना, संसाधन
  HTML को एम्बेड करना, और संग्रहों को एकल या बहु‑पृष्ठ HTML में बैच रूपांतरण करना
  सीखें।
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'प्रति पृष्ठ आइटम सेट करें: GroupDocs.Viewer Java के साथ अभिलेखों को HTML में
  बदलें'
type: docs
url: /hi/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# आइटम्स प्रति पेज सेट करें: GroupDocs.Viewer Java के साथ आर्काइव को HTML में बदलें

आर्काइव फ़ाइलों जैसे ZIP या RAR को वेब‑फ़्रेंडली HTML में बदलना अक्सर आवश्यक होता है जब आप दस्तावेज़ों को सीधे ब्राउज़र में साझा या रिव्यू करना चाहते हैं। इस गाइड में आप सीखेंगे **आइटम्स प्रति पेज कैसे सेट करें** जबकि आर्काइव रेंडर कर रहे हों, स्व‑निहित आउटपुट के लिए रिसोर्सेज HTML को एम्बेड कैसे करें, और GroupDocs.Viewer Java के साथ आर्काइव को प्रभावी ढंग से बैच कन्वर्ट कैसे करें।

![GroupDocs.Viewer for Java के साथ आर्काइव को HTML में बदलें](/viewer/export-conversion/convert-archives-to-html-java.png)

## त्वरित उत्तर
- **“आइटम्स प्रति पेज सेट” नियंत्रण क्या करता है?** यह निर्धारित करता है कि एक जनरेटेड HTML पेज पर आर्काइव की कितनी फ़ाइलें या फ़ोल्डर दिखेंगे।  
- **क्या मैं इमेज और CSS को सीधे HTML में एम्बेड कर सकता हूँ?** हाँ – `forEmbeddedResources` विकल्प का उपयोग करके रिसोर्सेज HTML को एम्बेड करें।  
- **क्या बैच कन्वर्ज़न संभव है?** बिल्कुल; आप आर्काइव्स के एक संग्रह पर लूप करके प्रत्येक को समान सेटिंग्स के साथ रेंडर कर सकते हैं।  
- **क्या GroupDocs.Viewer उपयोग करने के लिए Maven की आवश्यकता है?** हाँ, नीचे दिखाए अनुसार `maven groupdocs viewer` डिपेंडेंसी जोड़ें।  
- **कौन‑से आउटपुट फ़ॉर्मेट समर्थित हैं?** सिंगल‑पेज HTML Java और मल्टी‑पेज HTML Java दोनों उपलब्ध हैं।

## GroupDocs.Viewer में “आइटम्स प्रति पेज सेट” क्या है?
**आइटम्स प्रति पेज सेट** विकल्प आर्काइव रेंडरिंग ऑप्शन्स से संबंधित है। यह व्यूअर को बताता है कि मल्टी‑पेज HTML दस्तावेज़ बनाते समय प्रत्येक HTML पेज पर कितनी आर्काइव एंट्रीज़ (फ़ाइलें या फ़ोल्डर) प्रदर्शित हों। इस मान को समायोजित करने से आप पेज साइज और नेविगेशन स्पीड के बीच संतुलन बना सकते हैं, विशेषकर बड़े आर्काइव्स के लिए।

## रिसोर्सेज HTML को एम्बेड क्यों करें?
रिसोर्सेज (इमेज, CSS, फ़ॉन्ट) को सीधे HTML फ़ाइल में एम्बेड करने से एक सिंगल, पोर्टेबल डॉक्यूमेंट बनता है जिसे बाहरी फ़ाइलों की आवश्यकता के बिना खोला जा सकता है। यह ई‑मेल अटैचमेंट, ऑफ़लाइन व्यूइंग, या आउटपुट को अन्य वेब पेजों में एम्बेड करने के लिए आदर्श है।

## पूर्वापेक्षाएँ

- **आवश्यक लाइब्रेरीज़:** GroupDocs.Viewer संस्करण 25.2 या बाद का शामिल करें।  
- **पर्यावरण:** Java Development Kit (JDK) स्थापित और कॉन्फ़िगर किया हुआ।  
- **ज्ञान:** बेसिक Java और Maven डिपेंडेंसी मैनेजमेंट।

## Maven GroupDocs Viewer सेटअप

`pom.xml` में GroupDocs रिपॉज़िटरी और व्यूअर डिपेंडेंसी जोड़ें:

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
GroupDocs.Viewer एक **फ्री ट्रायल लिंक**, एक टेम्पररी लाइसेंस, या पूर्ण खरीद विकल्प प्रदान करता है। अपने प्रोजेक्ट टाइमलाइन के अनुसार उपयुक्त विकल्प चुनें।

### बेसिक इनिशियलाइज़ेशन
Maven सेटअप के बाद, व्यूअर को अपने कोड में लाएँ:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## आर्काइव को सिंगल‑पेज HTML में रेंडर करने का तरीका

### चरण 1: आउटपुट डायरेक्टरी परिभाषित करें
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### चरण 2: सिंगल‑पेज आउटपुट के लिए फ़ाइल नाम सेट करें
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### चरण 3: व्यूअर को इनिशियलाइज़ करें
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### चरण 4: रेंडरिंग ऑप्शन कॉन्फ़िगर करें (रिसोर्सेज HTML एम्बेड)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### चरण 5: सिंगल पेज के रूप में रेंडर करें
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## आर्काइव को मल्टी‑पेज HTML में रेंडर करने और आइटम्स प्रति पेज सेट करने का तरीका

### चरण 1: आउटपुट डायरेक्टरी को पुनः उपयोग करें
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### चरण 2: कई पेजों के लिए फ़ाइल नाम फ़ॉर्मेट परिभाषित करें
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### चरण 3: फिर से व्यूअर को इनिशियलाइज़ करें
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### चरण 4: मल्टी‑पेज ऑप्शन कॉन्फ़िगर करें (रिसोर्सेज HTML एम्बेड)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### चरण 5: आइटम्स प्रति पेज सेट करें (मुख्य कीवर्ड एक्शन में)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## व्यावहारिक उपयोग

- **डॉक्यूमेंट मैनेजमेंट सिस्टम:** अतिरिक्त व्यूअर्स इंस्टॉल किए बिना आर्काइव प्रीव्यू फ़ंक्शनालिटी जोड़ें।  
- **वेब पोर्टल्स:** उपयोगकर्ताओं को बंडल्ड डॉक्यूमेंट्स को जल्दी, बिना डाउनलोड के एक्सप्लोर करने का विकल्प दें।  
- **कोलैबोरेशन टूल्स:** टीमों को ब्राउज़र में सीधे साझा किए गए आर्काइव्स को इंस्पेक्ट करने की सुविधा दें।

## प्रदर्शन संबंधी विचार

- **रिसोर्स मैनेजमेंट:** मेमोरी उपयोग पर नजर रखें; बड़े बैच के लिए JVM के गार्बेज‑कलेक्टर को ट्यून करने पर विचार करें।  
- **बैच कन्वर्ट आर्काइव्स:** आर्काइव फ़ाइलों की सूची पर लूप चलाएँ और समान रेंडरिंग लॉजिक को कॉल करके थ्रूपुट अधिकतम करें।  
- **कैशिंग स्ट्रेटेजी:** यदि वही आर्काइव बार‑बार एक्सेस किया जाता है तो रेंडर किया हुआ HTML कैश में स्टोर करें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: GroupDocs.Viewer Java क्या है?**  
उत्तर: एक बहुमुखी लाइब्रेरी जो डॉक्यूमेंट्स—आर्काइव सहित—को HTML, PDF, और इमेज जैसे फ़ॉर्मेट में रेंडर करती है।

**प्रश्न: GroupDocs.Viewer का फ्री ट्रायल कैसे प्राप्त करूँ?**  
उत्तर: [free trial link](https://releases.groupdocs.com/viewer/java/) पर जाएँ और डाउनलोड व टेस्ट करें।

**प्रश्न: क्या मैं आर्काइव के अलावा अन्य डॉक्यूमेंट टाइप्स भी कन्वर्ट कर सकता हूँ?**  
उत्तर: हाँ, व्यूअर PDFs, Word, Excel, और कई अन्य फ़ॉर्मेट्स को सपोर्ट करता है।

**प्रश्न: यदि रेंडरिंग धीमी हो रही है तो क्या करें?**  
उत्तर: आइटम्स प्रति पेज की संख्या घटाएँ, स्ट्रीमिंग सक्षम करें, या आर्काइव्स को छोटे बैच में प्रोसेस करें।

**प्रश्न: सहायता या सपोर्ट कहाँ प्राप्त करूँ?**  
उत्तर: [support forum](https://forum.groupdocs.com/c/viewer/9) के माध्यम से संपर्क करें।

**प्रश्न: क्या CSS और इमेज को सीधे HTML में एम्बेड करना संभव है?**  
उत्तर: बिल्कुल—उदाहरणों में दिखाए अनुसार `HtmlViewOptions.forEmbeddedResources` का उपयोग करें।

**प्रश्न: फ़ोल्डर में मौजूद कई आर्काइव्स को बैच में कैसे कन्वर्ट करूँ?**  
उत्तर: प्रत्येक फ़ाइल पर `for` लूप चलाएँ और प्रत्येक इटरेशन में समान `Viewer` और `HtmlViewOptions` कॉन्फ़िगरेशन लागू करें।

## संसाधन

- **डॉक्यूमेंटेशन:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) के साथ फ़ंक्शनालिटी में गहराई से जाएँ।  
- **API रेफ़रेंस:** पूर्ण API को [GroupDocs API](https://reference.groupdocs.com/viewer/java/) पर एक्सप्लोर करें।  
- **डाउनलोड:** नवीनतम बाइनरीज़ को [download page](https://releases.groupdocs.com/viewer/java/) से प्राप्त करें।  
- **पर्चेज और लाइसेंसिंग:** विकल्पों की समीक्षा [purchase page](https://purchase.groupdocs.com/buy) पर करें।  
- **सपोर्ट और कम्युनिटी:** चर्चाओं में शामिल हों [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) पर।

---

**अंतिम अपडेट:** 2026-02-23  
**टेस्टेड विथ:** GroupDocs.Viewer 25.2  
**लेखक:** GroupDocs