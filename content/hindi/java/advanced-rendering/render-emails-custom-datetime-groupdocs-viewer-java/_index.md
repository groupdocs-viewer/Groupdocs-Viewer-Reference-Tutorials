---
date: '2026-03-24'
description: GroupDocs.Viewer का उपयोग करके जावा में कस्टम डेटटाइम फ़ॉर्मेट के साथ
  EML को HTML में कैसे बदलें और टाइमज़ोन ऑफ़सेट सेट करें, सीखें। ईमेल आर्काइविंग और
  सपोर्ट सिस्टम के लिए आदर्श।
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: GroupDocs.Viewer का उपयोग करके जावा में कस्टम डेटटाइम के साथ EML को HTML में
  परिवर्तित करें
type: docs
url: /hi/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# GroupDocs.Viewer का उपयोग करके Java में कस्टम DateTime के साथ EML को HTML में बदलें

आज की तेज़ गति वाली डिजिटल दुनिया में, **EML को HTML में बदलने** की क्षमता, सही डेट‑टाइम प्रस्तुति के साथ, आर्काइविंग, सपोर्ट पोर्टल और कानूनी अनुपालन के लिए आवश्यक है। यह ट्यूटोरियल आपको GroupDocs.Viewer for Java का उपयोग करके ईमेल संदेशों को HTML में रेंडर करने और **कस्टम datetime फ़ॉर्मेट** तथा **टाइमज़ोन ऑफ़सेट** लागू करने के चरण दिखाता है। अंत तक, आपके पास एक पुन: उपयोग योग्य समाधान होगा जो टाइमस्टैम्प को सटीक और पठनीय रखता है, जो किसी भी **email to HTML Java** वर्कफ़्लो के लिए उपयुक्त है।

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**आप क्या सीखेंगे**
- Java प्रोजेक्ट में GroupDocs.Viewer सेट अप कैसे करें  
- एंबेडेड रिसोर्सेज़ के साथ ईमेल को HTML में रेंडर कैसे करें  
- अपने ईमेल संदेशों का **date‑time फ़ॉर्मेट** कस्टमाइज़ कैसे करें (custom datetime java)  
- **timezone ऑफ़सेट** सेट करके सही टाइमस्टैम्प कैसे प्राप्त करें (timezone offset java)  

## त्वरित उत्तर
- **क्या GroupDocs.Viewer EML को HTML में बदल सकता है?** हाँ, यह EML फ़ाइलों को सीधे HTML में रेंडर करता है।  
- **क्या मुझे लाइसेंस चाहिए?** परीक्षण के लिए एक फ्री ट्रायल काम करता है; उत्पादन के लिए एक पेड लाइसेंस आवश्यक है।  
- **कौन सा Java संस्करण आवश्यक है?** Java 8 या उससे नया।  
- **प्रदर्शित डेट फ़ॉर्मेट कैसे बदलें?** `options.getEmailOptions().setDateTimeFormat(...)` का उपयोग करें।  
- **क्या मैं टाइम ज़ोन समायोजित कर सकता हूँ?** हाँ, `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))` के साथ।  

## “convert EML to HTML” क्या है?
EML फ़ाइल को HTML में बदलने से कच्चा ईमेल (हेडर, बॉडी और अटैचमेंट सहित) वेब‑फ्रेंडली फ़ॉर्मेट में परिवर्तित हो जाता है जिसे ब्राउज़र अतिरिक्त प्लगइन के बिना प्रदर्शित कर सकते हैं। इससे ईमेल को वेब एप्लिकेशन, आर्काइव या सपोर्ट डैशबोर्ड में एम्बेड करना आसान हो जाता है।

## इस कार्य के लिए GroupDocs.Viewer का उपयोग क्यों करें?
- **Zero‑dependency rendering** – Outlook या बाहरी मेल पार्सर की आवश्यकता नहीं।  
- **Embedded resources** (images, attachments) के लिए बिल्ट‑इन सपोर्ट।  
- **Fine‑grained control** date‑time फ़ॉर्मेटिंग और टाइमज़ोन हैंडलिंग पर।  

## आवश्यकताएँ
- **GroupDocs.Viewer for Java** संस्करण 25.2 या बाद का।  
- **Java Development Kit (JDK)** 8+ और एक IDE (IntelliJ IDEA, Eclipse, आदि)।  
- बेसिक Java ज्ञान और Maven से परिचितता।  

## GroupDocs.Viewer for Java सेट अप करना

### Maven कॉन्फ़िगरेशन
`pom.xml` में GroupDocs रिपॉज़िटरी और डिपेंडेंसी जोड़ें:

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
फ़्री ट्रायल से शुरू करें या विस्तारित परीक्षण के लिए एक टेम्पररी लाइसेंस का अनुरोध करें। उत्पादन उपयोग के लिए पूर्ण लाइसेंस खरीदें।

### बेसिक इनिशियलाइज़ेशन
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Java में कस्टम DateTime के साथ EML को HTML में बदलें

निम्नलिखित चरण‑दर‑चरण गाइड दिखाता है कि **EML को HTML में कैसे बदलें** जबकि कस्टम datetime फ़ॉर्मेट और टाइमज़ोन ऑफ़सेट लागू किया जाए।

### चरण 1: आउटपुट डायरेक्टरी और फ़ाइल पाथ सेट करें
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*व्याख्या:* `Path.of()` उस फ़ोल्डर का रेफ़रेंस बनाता है जहाँ HTML सेव किया जाएगा। `resolve()` फ़ाइल नाम जोड़ता है।

### चरण 2: ईमेल फ़ाइल के साथ Viewer इनिशियलाइज़ करें
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*व्याख्या:* `Viewer` इंस्टेंस उस EML फ़ाइल की ओर इशारा करता है जिसे आप बदलना चाहते हैं।

### चरण 3: HtmlViewOptions कॉन्फ़िगर करें
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*व्याख्या:* `forEmbeddedResources()` इमेज़ और अन्य रिसोर्सेज़ को सीधे HTML आउटपुट में बंडल करता है।

### चरण 4: कस्टम DateTime फ़ॉर्मेट सेट करें *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*व्याख्या:* यह पैटर्न महीने, दिन, वर्ष, घंटे, मिनट, AM/PM मार्कर और टाइमज़ोन ऑफ़सेट (`zzz`) दिखाता है।

### चरण 5: टाइमज़ोन ऑफ़सेट सेट करें *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*व्याख्या:* रेंडर किए गए टाइमस्टैम्प को इच्छित टाइम ज़ोन में समायोजित करता है। `"GMT+1"` को किसी भी वैध ज़ोन आइडेंटिफ़ायर से बदलें।

### Java में ईमेल टाइमज़ोन कैसे समायोजित करें
यदि आपको साधारण ऑफ़सेट से परे **ईमेल टाइमज़ोन समायोजित** करना है—जैसे डेलाइट‑सेविंग बदलावों को संभालना—तो आप `java.util.TimeZone` API से उपयुक्त `TimeZone` ऑब्जेक्ट को `"Europe/Paris"` या `"America/New_York"` जैसे रीजन आईडी का उपयोग करके प्राप्त कर सकते हैं और उसे `setTimeZoneOffset` में पास कर सकते हैं। इससे ईमेल टाइमस्टैम्प हमेशा सही स्थानीय समय दर्शाते हैं।

### चरण 6: डॉक्यूमेंट रेंडर करें
```java
viewer.view(options);
```
*व्याख्या:* परिवर्तन को निष्पादित करता है, आपके कस्टम date‑time सेटिंग्स के साथ एक HTML फ़ाइल बनाता है।

## समस्या निवारण टिप्स
- **FileNotFoundException:** `Viewer` और `Path.of()` में उपयोग किए गए पाथ को दोबारा जांचें।  
- **Incorrect timestamps:** यह सुनिश्चित करें कि `TimeZone` ID आपके लक्ष्य क्षेत्र से मेल खाती है।  
- **Missing images:** सुनिश्चित करें कि आपने `HtmlViewOptions.forEmbeddedResources()` का उपयोग किया है; अन्यथा बाहरी रिसोर्सेज़ शामिल नहीं हो सकते।  

## व्यावहारिक अनुप्रयोग
1. **Email Archiving:** अनुपालन के लिए ईमेल के खोज योग्य HTML स्नैपशॉट संग्रहीत करें।  
2. **Customer Support Portals:** आने वाले टिकटों को सटीक स्थानीय समय के साथ दिखाएँ।  
3. **Legal Documentation:** मानकीकृत टाइमस्टैम्प के साथ कोर्ट‑रेडी ईमेल रिकॉर्ड बनाएं।  

## प्रदर्शन संबंधी विचार
- बड़े पैमाने पर रूपांतरण के लिए एक समर्पित सर्वर पर डिप्लॉय करें।  
- Java हीप उपयोग की निगरानी करें; यदि `OutOfMemoryError` मिलता है तो `-Xmx` बढ़ाएँ।  
- जब एक ही ईमेल बार‑बार अनुरोध किया जाए तो रेंडर किया गया HTML कैश करें।  

## निष्कर्ष
अब आपके पास GroupDocs.Viewer for Java का उपयोग करके कस्टम datetime फ़ॉर्मेट और टाइमज़ोन ऑफ़सेट के साथ **EML को HTML में बदलने** की एक पूर्ण, प्रोडक्शन‑रेडी विधि है। यह पठनीयता बढ़ाता है, टाइमस्टैम्प की सटीकता सुनिश्चित करता है, और आर्काइविंग या सपोर्ट वर्कफ़्लो में सहजता से फिट होता है।

**अगले कदम:** अतिरिक्त Viewer विकल्पों जैसे CSS स्टाइलिंग, पेजिनेशन, या PDF रूपांतरण का अन्वेषण करें ताकि आउटपुट को अपनी जरूरतों के अनुसार और अधिक अनुकूलित किया जा सके।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न:** EML फ़ाइलों में अटैचमेंट्स को कैसे हैंडल करें?  
**उत्तर:** जब आप `HtmlViewOptions.forEmbeddedResources()` का उपयोग करते हैं तो अटैचमेंट्स स्वचालित रूप से एम्बेड हो जाते हैं। आवश्यकता पड़ने पर आप Viewer API के माध्यम से उन्हें एक्सट्रैक्ट भी कर सकते हैं।

**प्रश्न:** क्या मैं HTML टेम्पलेट बदल सकता हूँ या कस्टम CSS जोड़ सकता हूँ?  
**उत्तर:** हाँ, रेंडरिंग के बाद आप जनरेटेड HTML फ़ाइल को संपादित कर सकते हैं या सेव करने से पहले प्रोग्रामेटिकली CSS इन्जेक्ट कर सकते हैं।

**प्रश्न:** क्या कई EML फ़ाइलों को बैच में रेंडर करना संभव है?  
**उत्तर:** रेंडरिंग लॉजिक को लूप में रखें और प्रत्येक फ़ाइल के लिए समान `HtmlViewOptions` इंस्टेंस को पुन: उपयोग करें।

**प्रश्न:** यदि मुझे MSG जैसे अन्य ईमेल फ़ॉर्मेट को सपोर्ट करना हो तो क्या करें?  
**उत्तर:** GroupDocs.Viewer MSG, PST और अन्य ईमेल कंटेनर को भी सपोर्ट करता है—सिर्फ `Viewer` कंस्ट्रक्टर में फ़ाइल एक्सटेंशन बदलें।

**प्रश्न:** क्या प्रत्येक सर्वर के लिए अलग लाइसेंस चाहिए?  
**उत्तर:** लाइसेंसिंग प्रत्येक डिप्लॉयमेंट के लिए होती है; मल्टी‑सर्वर परिदृश्यों के लिए GroupDocs लाइसेंस गाइड देखें।

## संसाधन

- [डॉक्यूमेंटेशन](https://docs.groupdocs.com/viewer/java/)
- [API रेफ़रेंस](https://reference.groupdocs.com/viewer/java/)
- [डाउनलोड](https://releases.groupdocs.com/viewer/java/)
- [खरीदें](https://purchase.groupdocs.com/buy)
- [फ़्री ट्रायल](https://releases.groupdocs.com/viewer/java/)
- [टेम्पररी लाइसेंस](https://purchase.groupdocs.com/temporary-license/)
- [सपोर्ट फ़ोरम](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-03-24  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 (Java)  
**लेखक:** GroupDocs