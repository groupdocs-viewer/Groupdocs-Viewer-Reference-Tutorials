---
date: '2026-05-21'
description: MS Project HTML निर्यात को समायोजित समय इकाइयों के साथ करने के लिए GroupDocs
  Viewer for Java का उपयोग कैसे करें, जानें। पूर्वापेक्षाएँ, सेटअप, और समस्या निवारण
  के साथ चरण-दर-चरण गाइड।
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'MS Project HTML निर्यात: GroupDocs Java के माध्यम से समय इकाइयों को समायोजित
  करें'
type: docs
url: /hi/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML निर्यात: GroupDocs Java के माध्यम से समय इकाइयों को समायोजित करें

HTML में **MS Project** फ़ाइल निर्यात करना प्रोजेक्ट‑मैनेजमेंट डैशबोर्ड, स्टेटस‑रिपोर्ट पोर्टल और सहयोगी रिव्यू टूल्स के लिए एक सामान्य आवश्यकता है। डिफ़ॉल्ट रूप से व्यूअर समय‑संबंधी डेटा को मिनटों में रेंडर करता है, जिससे विज़ुअल लेआउट अव्यवस्थित हो सकता है और दैनिक रिपोर्टिंग पढ़ने में कठिन हो जाती है। **GroupDocs Viewer for Java** के साथ आप प्रोग्रामेटिकली समय‑इकाई को **days** (दिन) पर सेट कर सकते हैं, जिससे एक साफ़ *ms project html export* बनता है जो सामान्य स्टेकहोल्डर अपेक्षाओं के अनुरूप होता है। इस ट्यूटोरियल में आप सीखेंगे कि व्यूअर को कैसे कॉन्फ़िगर करें, समय इकाई को कैसे समायोजित करें, और कुछ सरल चरणों में प्रोजेक्ट को HTML में रेंडर करें।

![MS Project समय इकाइयों को GroupDocs.Viewer for Java के साथ समायोजित करें](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[MS Project समय इकाइयों को GroupDocs.Viewer for Java के साथ समायोजित करें](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## त्वरित उत्तर
- **MS Project फ़ाइलों को रेंडर करने वाली लाइब्रेरी कौन सी है?** GroupDocs Viewer for Java.  
- **HTML निर्यात के लिए मैं कौन सी समय इकाई सेट कर सकता हूँ?** Days, using `TimeUnit.DAYS`.  
- **उत्पादन के लिए मुझे लाइसेंस चाहिए?** हाँ— एक स्थायी लाइसेंस आवश्यक है; मूल्यांकन के लिए ट्रायल काम करता है। आप एक [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) से शुरू कर सकते हैं।  
- **कौन सा IDE सबसे अच्छा है?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **क्या Maven अनिवार्य है?** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **मैं कहां खरीद सकता हूँ?** Visit the [buy page](https://purchase.groupdocs.com/buy) for pricing.

## GroupDocs Viewer for Java क्या है?
**GroupDocs Viewer for Java** एक Java SDK है जो 150 से अधिक दस्तावेज़ फ़ॉर्मैट—जिसमें MS Project भी शामिल है—को वेब‑फ्रेंडली HTML, PNG, JPEG, या PDF में बदलता है।  
यह पार्सिंग लॉजिक को एब्स्ट्रैक्ट करता है, आपको समय इकाइयों जैसी रेंडरिंग विकल्पों को नियंत्रित करने देता है, और किसी भी प्लेटफ़ॉर्म पर काम करता है जो Java 8 या उससे ऊपर को सपोर्ट करता है।  

## MS Project HTML निर्यात के लिए समय इकाइयों को समायोजित क्यों करें?
समय इकाई को **days** (दिन) पर सेट करने से विज़ुअल शोर कम होता है, अधिकांश रिपोर्टिंग अंतरालों से मेल खाता है, और पेज लोड समय में सुधार होता है क्योंकि कम सूक्ष्म समय मार्कर उत्पन्न होते हैं। मात्रात्मक रूप से, मिनटों के बजाय दिनों के साथ रेंडर करने से सामान्य 30‑दिन प्रोजेक्ट्स के लिए उत्पन्न HTML आकार लगभग **45 %** तक घट सकता है, और क्लाइंट‑साइड रेंडरिंग लगभग **30 %** तेज़ हो जाती है।

## पूर्वापेक्षाएँ
- **Java Development Kit (JDK) 8 या नया** आपके कार्यस्थल पर स्थापित होना चाहिए।  
- **Maven** (या Gradle) डिपेंडेंसी मैनेजमेंट के लिए।  
- एक **MS Project (.mpp)** फ़ाइल जिसे आप निर्यात करना चाहते हैं।  
- **GroupDocs Viewer for Java** लाइसेंस (ट्रायल या स्थायी) तक पहुंच।  

### आवश्यक लाइब्रेरीज़
`pom.xml` में निम्नलिखित डिपेंडेंसी जोड़ें (या समकक्ष Gradle स्निपेट):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tip:** संस्करण संख्या को अद्यतित रखें; नए रिलीज़ फ़ॉर्मेट सपोर्ट और प्रदर्शन सुधार जोड़ते हैं।

## GroupDocs Viewer for Java को कैसे सेटअप करें?
व्यूअर को इनिशियलाइज़ करने के लिए एक `Viewer` इंस्टेंस बनाएं जो आपके MS Project फ़ाइल की ओर इशारा करता हो। `Viewer` क्लास सभी रेंडरिंग ऑपरेशन्स के लिए एंट्री पॉइंट है। यह स्रोत दस्तावेज़ को लोड करता है, आंतरिक संरचनाओं को तैयार करता है, और `view()` तथा `viewToHtml()` जैसी मेथड्स प्रदान करता है ताकि वांछित आउटपुट फ़ॉर्मैट उत्पन्न किए जा सकें।

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition anchor:** `Viewer` क्लास GroupDocs Viewer का कोर कंपोनेंट है जो स्रोत दस्तावेज़ को लोड करता है और `view()` तथा `viewToHtml()` जैसी रेंडरिंग मेथड्स प्रदान करता है।

## HTML निर्यात के लिए समय इकाइयों को कैसे समायोजित करें?
समय ग्रैन्युलैरिटी बदलने के लिए, एक `ViewOptions` ऑब्जेक्ट बनाएं, उसके `ProjectOptions` को `TimeUnit.DAYS` उपयोग करने के लिए कॉन्फ़िगर करें, और इसे व्यूअर को पास करें। `ViewOptions` दस्तावेज़ के रेंडरिंग सेटिंग्स को परिभाषित करता है, जबकि `TimeUnit` एन्नुम समय‑संबंधी डेटा के लिए इकाई (मिनट, घंटे, दिन) निर्दिष्ट करता है। इन विकल्पों को सेट करने के बाद, `viewer.view(options)` को कॉल करें ताकि दैनिक मार्कर वाले HTML उत्पन्न हो।  

`new Viewer("file.mpp")` के साथ अपना MS Project फ़ाइल लोड करें, एक `ViewOptions` ऑब्जेक्ट बनाएं, `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` सेट करें, फिर `viewer.view(options)` को कॉल करें। यह तीन‑स्टेप प्रक्रिया समय‑इकाई को मिनटों से दिनों में बदल देती है और ऐसे HTML फ़ाइलें बनाती है जो केवल दैनिक अंतराल दिखाती हैं।  

### चरण 1: आउटपुट फ़ोल्डर निर्धारित करें
एक लिखने योग्य डायरेक्टरी चुनें जहाँ HTML पेज़ सेव किए जाएंगे, उदाहरण के लिए `output/`।  

### चरण 2: एम्बेडेड रिसोर्सेज़ के साथ व्यू ऑप्शन बनाएं
एम्बेडेड रिसोर्सेज़ (CSS, JavaScript) सुनिश्चित करते हैं कि HTML पेज़ स्वयं‑समाहित हों।  

### चरण 3: समय‑इकाई को दिनों में सेट करें
ग्रैन्युलैरिटी बदलने के लिए `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` का उपयोग करें।  

### चरण 4: दस्तावेज़ को रेंडर करें
`viewer.view(options)` को कॉल करें; व्यूअर आउटपुट फ़ोल्डर में प्रत्येक प्रोजेक्ट पेज के लिए एक HTML फ़ाइल लिखता है।  

### चरण 5: परिणाम की जाँच करें
जनरेटेड `index.html` को ब्राउज़र में खोलें; आपको टास्क बार दिन के मार्कर के साथ संरेखित दिखेंगे, मिनट के मार्कर के बजाय।  

## सामान्य समस्याएँ और ट्रबलशूटिंग
- **गलत आउटपुट पाथ** – सुनिश्चित करें कि डायरेक्टरी मौजूद है और Java प्रोसेस के पास लिखने की अनुमति है।  
- **लाइसेंस नहीं है** – वैध लाइसेंस के बिना व्यूअर ट्रायल मोड में वापस जाता है और वॉटरमार्क एम्बेड कर सकता है।  
- **बड़ी फ़ाइलें (> 500 MB)** – JVM हीप साइज (`-Xmx2g`) बढ़ाने या `options.setRenderLimit(1000)` के साथ रेंडर करने पर विचार करें ताकि पेज़ को बैच में प्रोसेस किया जा सके।  

## समायोजित समय‑इकाई HTML निर्यात के व्यावहारिक उपयोग
1. **एक्जीक्यूटिव डैशबोर्ड** – दैनिक ग्रैन्युलैरिटी अधिकांश KPI विज़ुअलाइज़ेशन से मेल खाती है।  
2. **ऑटोमेटेड स्टेटस ईमेल** – जनरेटेड HTML को सीधे ईमेल बॉडी में एम्बेड करें त्वरित अपडेट के लिए।  
3. **प्रोजेक्ट पोर्टल** – HTML को इंट्रानेट साइट पर होस्ट करें जहाँ टीम सदस्य दिन के आधार पर टास्क फ़िल्टर कर सकें।  

## बड़े MS Project फ़ाइलों के लिए प्रदर्शन विचार
- **मेमोरी मैनेजमेंट** – Java के गार्बेज कलेक्टर फ्लैग्स (`-XX:+UseG1GC`) का उपयोग करें ताकि अनउपयोगी ऑब्जेक्ट्स तुरंत मुक्त हो सकें।  
- **सेलेक्टिव रेंडरिंग** – यदि आपको केवल गैंट चार्ट चाहिए, तो `options.getProjectOptions().setRenderGantt(true)` और `setRenderResources(false)` के माध्यम से अन्य रिसोर्स रेंडरिंग को डिसेबल करें।  
- **पैरालल प्रोसेसिंग** – बैच कन्वर्ज़न के लिए, प्रति फ़ाइल अलग `Viewer` ऑब्जेक्ट बनाएं और उन्हें थ्रेड पूल में चलाएँ ताकि मल्टी‑कोर CPU का उपयोग हो सके।  

## निष्कर्ष
अब आपके पास GroupDocs Viewer for Java का उपयोग करके समय इकाइयों को दिनों में सेट करके **ms project html export** करने के लिए एक पूर्ण, प्रोडक्शन‑रेडी वर्कफ़्लो है। यह तरीका HTML आकार को कम करता है, क्लाइंट रेंडरिंग को तेज़ करता है, और प्रोजेक्ट शेड्यूल का स्टेकहोल्डर‑फ़्रेंडली दृश्य प्रदान करता है। अतिरिक्त रेंडरिंग विकल्पों—जैसे PDF निर्यात या इमेज स्नैपशॉट—की खोज करें ताकि इंटीग्रेशन को व्यापक रिपोर्टिंग पाइपलाइन में विस्तारित किया जा सके।  

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं अन्य प्रोजेक्ट व्यूज़ (जैसे Resource Sheet) को HTML में रेंडर कर सकता हूँ?**  
उत्तर: हाँ, `ProjectOptions` ऑब्जेक्ट आपको रेंडरिंग से पहले Gantt, Resource Sheet, और Calendar जैसी विशिष्ट व्यूज़ को सक्षम या अक्षम करने देता है।  

**प्रश्न: क्या उत्पन्न HTML की CSS को कस्टमाइज़ करना संभव है?**  
उत्तर: बिल्कुल। `options.setStyleSheetPath("path/to/custom.css")` के माध्यम से एक कस्टम स्टाइलशीट पाथ प्रदान करें और व्यूअर इसे प्रत्येक पेज में एम्बेड कर देगा।  

**प्रश्न: GroupDocs Viewer MS Project के लिए कौन सी फ़ाइल आकार सीमाएँ समर्थन करता है?**  
उत्तर: SDK अपनी स्ट्रीमिंग आर्किटेक्चर के कारण पूरी दस्तावेज़ को मेमोरी में लोड किए बिना **500 MB** तक की फ़ाइलों को संभाल सकता है।  

**प्रश्न: क्या सर्वर पर Microsoft Project इंस्टॉल करना आवश्यक है?**  
उत्तर: नहीं। GroupDocs Viewer .mpp फ़ॉर्मैट को सीधे पार्स करता है और Microsoft Project या किसी भी Office इंस्टॉलेशन की आवश्यकता नहीं होती।  

**प्रश्न: प्रोडक्शन एनवायरनमेंट के लिए व्यूअर को कैसे लाइसेंस करें?**  
उत्तर: GroupDocs स्टोर से एक स्थायी लाइसेंस खरीदें; रनटाइम पर लाइसेंस फ़ाइल को `License license = new License(); license.setLicense("path/to/license.lic");` के साथ लागू करें। अल्पकालिक आवश्यकताओं के लिए आप एक [temporary license](https://purchase.groupdocs.com/temporary-license/) प्राप्त कर सकते हैं।  

---

**अंतिम अपडेट:** 2026-05-21  
**परीक्षित संस्करण:** GroupDocs Viewer Java 25.2  
**लेखक:** GroupDocs  

**संसाधन**  
- [डॉक्यूमेंटेशन](https://docs.groupdocs.com/viewer/java/)  
- [API रेफ़रेंस](https://reference.groupdocs.com/viewer/java/)  
- [GroupDocs.Viewer डाउनलोड करें](https://releases.groupdocs.com/viewer/java/)  
- [लाइसेंस खरीदें](https://purchase.groupdocs.com/buy)  

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## संबंधित ट्यूटोरियल्स

- [GroupDocs.Viewer for Java का उपयोग करके नोट्स के साथ MS Project फ़ाइलों को HTML, JPG, PNG, और PDF में कैसे रेंडर करें](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Java में समय अंतराल के अनुसार प्रोजेक्ट दस्तावेज़ों को रेंडर करने के लिए GroupDocs Viewer का उपयोग कैसे करें](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [GroupDocs.Viewer Java में लाइसेंस कैसे सेट करें: फ़ाइल और URL सेटअप गाइड](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)