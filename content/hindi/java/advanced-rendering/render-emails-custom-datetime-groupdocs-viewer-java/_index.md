---
date: '2026-09-15'
description: GroupDocs.Viewer for Java का उपयोग करके कस्टम datetime फ़ॉर्मेट और टाइमज़ोन
  ऑफ़सेट के साथ eml को html में कैसे परिवर्तित करें, सीखें—ईमेल आर्काइविंग और सपोर्ट
  पोर्टल्स के लिए आदर्श।
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: GroupDocs.Viewer for Java का उपयोग करके कस्टम datetime फ़ॉर्मेट और
  टाइमज़ोन ऑफ़सेट के साथ eml को html में परिवर्तित करें। सटीक ईमेल रेंडरिंग के लिए
  इस चरण‑दर‑चरण गाइड का पालन करें।
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: GroupDocs.Viewer का उपयोग करके Java में कस्टम datetime के साथ eml को html
  में परिवर्तित करें
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: GroupDocs.Viewer का उपयोग करके Java में कस्टम datetime के साथ eml को html में
  परिवर्तित करें
type: docs
url: /hi/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# कस्टम डेटाटाइम के साथ जावा में GroupDocs.Viewer का उपयोग करके eml को html में बदलें

आधुनिक समर्थन और अभिलेखीय प्रणालियों में, **convert eml to html** को तेज़ी से करना और सटीक टाइमस्टैम्प को संरक्षित रखना एक अनिवार्य क्षमता है। यह ट्यूटोरियल आपको दिखाता है कि कैसे GroupDocs.Viewer for Java का उपयोग करके एक EML ईमेल को HTML में रेंडर किया जाए, **custom datetime format** लागू किया जाए, और **timezone offset** सेट किया जाए। अंत तक आपके पास एक पुन: उपयोग योग्य स्निपेट होगा जो किसी भी **email to html conversion** वर्कफ़्लो के लिए सटीक, वेब‑तैयार ईमेल दृश्य उत्पन्न करता है।

![GroupDocs.Viewer for Java के साथ कस्टम डेटाटाइम के साथ ईमेल रेंडर करें](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## त्वरित उत्तर
- **Can GroupDocs.Viewer convert EML to HTML?** Yes – the API renders EML files directly to HTML without external mail clients.  
  - **हाँ – API EML फ़ाइलों को सीधे HTML में रेंडर करता है बिना किसी बाहरी मेल क्लाइंट के।**
- **Do I need a license for production?** A free trial is fine for testing; a paid license is required for production deployments.  
  - **टेस्टिंग के लिए एक मुफ्त ट्रायल पर्याप्त है; उत्पादन परिनियोजन के लिए एक पेड लाइसेंस आवश्यक है।**
- **Which Java version is supported?** Java 8 or newer is fully supported.  
  - **Java 8 या उससे नया पूरी तरह समर्थित है।**
- **How do I change the displayed date format?** Call `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
  - **Call `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.**
- **Can I adjust the time zone?** Yes, use `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.  
  - **हाँ, उपयोग करें `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.**

## “convert eml to html” क्या है?
`Convert eml to html` वह प्रक्रिया है जिसमें EML ईमेल फ़ाइल को ब्राउज़र रेंडरिंग के लिए HTML दस्तावेज़ में परिवर्तित किया जाता है। EML फ़ाइल को HTML में बदलने से कच्चा ईमेल (हेडर, बॉडी, और अटैचमेंट सहित) वेब‑फ्रेंडली फ़ॉर्मेट में बदल जाता है जिसे ब्राउज़र अतिरिक्त प्लगइन्स के बिना प्रदर्शित कर सकते हैं। इससे वेब एप्लिकेशन, अभिलेख या समर्थन डैशबोर्ड में ईमेल को एम्बेड करना आसान हो जाता है।

## इस कार्य के लिए GroupDocs.Viewer क्यों उपयोग करें?
GroupDocs.Viewer **50+ इनपुट और आउटपुट फ़ॉर्मेट** का समर्थन करता है, जिसमें EML, MSG, PST, और PDF शामिल हैं, और पूरी फ़ाइल को मेमोरी में लोड किए बिना कई‑सौ‑पृष्ठों वाले ईमेल को रेंडर कर सकता है। इसका ज़ीरो‑डिपेंडेंसी इंजन Outlook या थर्ड‑पार्टी पार्सर्स की आवश्यकता को समाप्त करता है, जिससे आपको **custom datetime format** और **timezone offset** पर पूर्ण नियंत्रण मिलता है जबकि संसाधन उपयोग कम रहता है।

## पूर्वापेक्षाएँ
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ और एक Java IDE (IntelliJ IDEA, Eclipse, VS Code)  
- निर्भरता प्रबंधन के लिए Maven  

## Java के लिए GroupDocs.Viewer सेटअप करना

### Maven कॉन्फ़िगरेशन
`pom.xml` फ़ाइल में GroupDocs रिपॉज़िटरी और Viewer डिपेंडेंसी जोड़ें।

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
शुरुआत में एक मुफ्त ट्रायल से शुरू करें या विस्तारित परीक्षण के लिए एक अस्थायी लाइसेंस का अनुरोध करें। उत्पादन उपयोग के लिए पूर्ण लाइसेंस खरीदें।

### बुनियादी इनिशियलाइज़ेशन
एक `Viewer` इंस्टेंस बनाएं जो उस EML फ़ाइल की ओर संकेत करता है जिसे आप बदलना चाहते हैं।

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## जावा में कस्टम डेटाटाइम के साथ eml को html में बदलें

यह निम्नलिखित चरण आपको एक EML फ़ाइल को HTML में रेंडर करने के दौरान कस्टम डेटाटाइम फ़ॉर्मेट और टाइमज़ोन ऑफ़सेट लागू करने की प्रक्रिया दिखाते हैं।

### चरण 1: आउटपुट डायरेक्टरी और फ़ाइल पाथ सेट करें
परिभाषित करें कि उत्पन्न HTML कहाँ सहेजा जाएगा।

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*व्याख्या:* `Path.of()` वह रेफ़रेंस बनाता है जो फ़ोल्डर की ओर संकेत करता है जहाँ HTML सहेजा जाएगा। `resolve()` फ़ाइल नाम जोड़ता है।

### चरण 2: ईमेल फ़ाइल के साथ viewer को इनिशियलाइज़ करें
लक्षित EML फ़ाइल के लिए `Viewer` क्लास का इंस्टेंस बनाएं।

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*व्याख्या:* `Viewer` इंस्टेंस उस EML फ़ाइल की ओर संकेत करता है जिसे आप बदलना चाहते हैं।

### चरण 3: HtmlViewOptions को कॉन्फ़िगर करें
एक `HtmlViewOptions` ऑब्जेक्ट बनाएं जो इमेज़ और अन्य संसाधनों को सीधे HTML आउटपुट में बंडल करता है।

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*व्याख्या:* `forEmbeddedResources()` इमेज़ और अन्य संसाधनों को सीधे HTML आउटपुट में बंडल करता है।

### चरण 4: कस्टम डेटाटाइम फ़ॉर्मेट सेट करें *(custom datetime java)*
`setDateTimeFormat` वह डेट‑टाइम पैटर्न सेट करता है जो ईमेल टाइमस्टैम्प रेंडर करते समय उपयोग होता है।  
रेंडर किए गए HTML में सभी टाइमस्टैम्प के लिए उपयोग किया जाने वाला पैटर्न परिभाषित करें।

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*व्याख्या:* यह पैटर्न महीने, दिन, वर्ष, घंटे, मिनट, AM/PM संकेतक, और टाइमज़ोन ऑफ़सेट (`zzz`) दिखाता है।

### चरण 5: टाइमज़ोन ऑफ़सेट सेट करें *(timezone offset java)*
`setTimeZoneOffset` वह टाइम‑ज़ोन निर्दिष्ट करता है जो सभी ईमेल टाइमस्टैम्प पर लागू होगा।  
टाइमस्टैम्प को इच्छित टाइम ज़ोन में समायोजित करें।

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*व्याख्या:* रेंडर किए गए टाइमस्टैम्प को इच्छित टाइम ज़ोन में समायोजित करता है। `"GMT+1"` को किसी भी वैध ज़ोन पहचानकर्ता से बदलें।

### जावा में ईमेल टाइमज़ोन कैसे समायोजित करें
यदि आपको सरल ऑफ़सेट से परे **adjust email timezone** की आवश्यकता है—जैसे डेलाइट‑सेविंग परिवर्तन को संभालना—तो आप `java.util.TimeZone` API से उपयुक्त `TimeZone` ऑब्जेक्ट को क्षेत्र ID जैसे `"Europe/Paris"` या `"America/New_York"` का उपयोग करके प्राप्त कर सकते हैं और उसे `setTimeZoneOffset` को पास कर सकते हैं। इससे ईमेल टाइमस्टैम्प हमेशा सही स्थानीय समय दर्शाते हैं।

### चरण 6: दस्तावेज़ रेंडर करें
परिवर्तन को निष्पादित करें और अंतिम HTML फ़ाइल उत्पन्न करें।

```java
viewer.view(options);
```
*व्याख्या:* परिवर्तन को निष्पादित करता है, आपके कस्टम डेट‑टाइम सेटिंग्स के साथ एक HTML फ़ाइल बनाता है।

## कस्टम डेटाटाइम फ़ॉर्मेट रेंडर किए गए HTML को कैसे प्रभावित करता है?
कस्टम डेटाटाइम फ़ॉर्मेट यह निर्धारित करता है कि उत्पन्न HTML में प्रत्येक ईमेल टाइमस्टैम्प कैसे दिखेगा, जिससे पठनीयता और स्थानीय अनुपालन प्रभावित होते हैं। `"MMM dd, yyyy hh:mm a zzz"` जैसे पैटर्न को निर्दिष्ट करके आप सुनिश्चित करते हैं कि हर तिथि सुसंगत रूप से प्रदर्शित हो, जिसमें महीने का संक्षिप्त रूप, दिन, वर्ष, घंटे, मिनट, AM/PM संकेतक, और स्पष्ट टाइमज़ोन ऑफ़सेट शामिल हो, जो वैश्विक समर्थन टीमों के लिए महत्वपूर्ण है।

## ईमेल रेंडरिंग के लिए GroupDocs.Viewer कौन‑से फ़ाइल फ़ॉर्मेट समर्थन करता है?
GroupDocs.Viewer **EML, MSG, PST, MBOX, और EMLX** फ़ाइलों को HTML, PDF, PNG, और JPEG में रेंडर कर सकता है। यह 50 से अधिक कुल दस्तावेज़ और इमेज़ फ़ॉर्मेट का समर्थन करता है, जिससे आप ईमेल को किसी भी सामान्य वेब‑फ्रेंडली आउटपुट में अतिरिक्त कन्वर्टर्स के बिना बदल सकते हैं।

## कई EML फ़ाइलों को बैच में कैसे बदलें?
सभी EML फ़ाइलों को एक ही डायरेक्टरी में रखें, प्रत्येक फ़ाइल को `for` या `foreach` संरचना से लूप करें, वही `HtmlViewOptions` इंस्टेंस पुन: उपयोग करें, और प्रत्येक फ़ाइल के लिए `viewer.view` को कॉल करें। यह तरीका ऑब्जेक्ट निर्माण ओवरहेड को कम करता है और बड़े पैमाने पर परिवर्तन को तेज़ करता है।

## समस्या निवारण सुझाव
- **FileNotFoundException:** `Viewer` और `Path.of()` में उपयोग किए गए पाथ की जाँच करें।  
- **Incorrect timestamps:** सुनिश्चित करें कि `TimeZone` ID आपके लक्ष्य क्षेत्र से मेल खाती है।  
- **Missing images:** पुष्टि करें कि आपने `HtmlViewOptions.forEmbeddedResources()` का उपयोग किया है; अन्यथा बाहरी संसाधन छोड़ दिए जा सकते हैं।  

## व्यावहारिक अनुप्रयोग
1. **Email archiving:** अनुपालन ऑडिट के लिए ईमेल के खोज योग्य HTML स्नैपशॉट सहेजें।  
2. **Customer support portals:** विश्व भर के एजेंटों के लिए सटीक स्थानीय समय के साथ आने वाले टिकट दिखाएँ।  
3. **Legal documentation:** मानकीकृत टाइमस्टैम्प के साथ कोर्ट‑तैयार ईमेल रिकॉर्ड बनाएं।  

## प्रदर्शन संबंधी विचार
- बड़ी मात्रा में परिवर्तन के लिए एक समर्पित सर्वर पर डिप्लॉय करें।  
- Java हीप उपयोग की निगरानी करें; यदि `OutOfMemoryError` मिलता है तो `-Xmx` बढ़ाएँ।  
- जब एक ही ईमेल बार‑बार अनुरोधित हो तो रेंडर किए गए HTML को कैश करें ताकि CPU लोड कम हो।  

## निष्कर्ष
अब आपके पास GroupDocs.Viewer for Java का उपयोग करके **convert eml to html** करने का एक पूर्ण, उत्पादन‑तैयार तरीका है, जिसमें कस्टम डेटाटाइम फ़ॉर्मेट और टाइमज़ोन ऑफ़सेट शामिल है। यह समाधान पठनीयता को बढ़ाता है, टाइमस्टैम्प की सटीकता की गारंटी देता है, और अभिलेखन, समर्थन, या कानूनी वर्कफ़्लो में सहजता से फिट होता है।

**अगले कदम:** अतिरिक्त Viewer विकल्पों जैसे कस्टम CSS इंजेक्शन, पेजिनेशन, या PDF रूपांतरण का अन्वेषण करें ताकि आउटपुट को आपके एप्लिकेशन की आवश्यकताओं के अनुसार और अधिक अनुकूलित किया जा सके।

## अक्सर पूछे जाने वाले प्रश्न

**Q: मैं eml फ़ाइलों के साथ अटैचमेंट्स को कैसे संभालूँ?**  
A: अटैचमेंट्स स्वचालित रूप से एम्बेड हो जाते हैं जब आप `HtmlViewOptions.forEmbeddedResources()` का उपयोग करते हैं। यदि आपको अलग फ़ाइलों की आवश्यकता हो तो आप Viewer API के माध्यम से उन्हें निकाल भी सकते हैं।

**Q: क्या मैं HTML टेम्पलेट बदल सकता हूँ या कस्टम CSS जोड़ सकता हूँ?**  
A: हाँ, रेंडरिंग के बाद आप उत्पन्न HTML फ़ाइल को संपादित कर सकते हैं या सहेजने से पहले प्रोग्रामेटिक रूप से CSS इंजेक्ट कर सकते हैं।

**Q: क्या कई eml फ़ाइलों को बैच में रेंडर करना संभव है?**  
A: रेंडरिंग लॉजिक को लूप में रखें और प्रत्येक फ़ाइल के लिए वही `HtmlViewOptions` इंस्टेंस पुन: उपयोग करें।

**Q: यदि मुझे msg जैसे अन्य ईमेल फ़ॉर्मेट का समर्थन करना हो तो क्या करें?**  
A: GroupDocs.Viewer MSG, PST, और अन्य ईमेल कंटेनर को भी समर्थन देता है—सिर्फ `Viewer` कंस्ट्रक्टर में फ़ाइल एक्सटेंशन बदलें।

**Q: क्या प्रत्येक सर्वर के लिए अलग लाइसेंस चाहिए?**  
A: लाइसेंसिंग प्रत्येक परिनियोजन के अनुसार है; मल्टी‑सर्वर परिदृश्यों के लिए GroupDocs लाइसेंस गाइड देखें।

## संसाधन
- [दस्तावेज़ीकरण](https://docs.groupdocs.com/viewer/java/)
- [API संदर्भ](https://reference.groupdocs.com/viewer/java/)
- [डाउनलोड](https://releases.groupdocs.com/viewer/java/)
- [खरीदें](https://purchase.groupdocs.com/buy)
- [मुफ्त ट्रायल](https://releases.groupdocs.com/viewer/java/)
- [अस्थायी लाइसेंस](https://purchase.groupdocs.com/temporary-license/)
- [समर्थन फ़ोरम](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-09-15  
**परीक्षण किया गया:** GroupDocs.Viewer 25.2 (Java)  
**लेखक:** GroupDocs

## संबंधित ट्यूटोरियल
- [ईमेल को HTML में बदलें और फ़ील्ड्स का नाम बदलें – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convert msg to pdf – GroupDocs.Viewer के साथ Email-to-PDF रेंडरिंग को ऑप्टिमाइज़ करें](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Groupdocs Viewer Java रिस्पॉन्सिव HTML रेंडरिंग](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}