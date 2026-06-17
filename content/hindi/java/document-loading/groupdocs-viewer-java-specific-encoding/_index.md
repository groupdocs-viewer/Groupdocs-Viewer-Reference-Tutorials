---
date: '2026-05-21'
description: GroupDocs.Viewer का उपयोग करके Java में दस्तावेज़ एन्कोडिंग कैसे लोड
  करें और Java character set निर्दिष्ट करना सीखें, साथ ही garbled text को ठीक करने
  के टिप्स।
keywords:
- load documents encoding java
- load text file encoding
- specify character set java
- troubleshoot garbled text
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to load documents encoding java and specify character set
    java using GroupDocs.Viewer, plus troubleshooting garbled text tips.
  headline: How to Load Documents Encoding Java with GroupDocs.Viewer
  type: TechArticle
- description: Learn how to load documents encoding java and specify character set
    java using GroupDocs.Viewer, plus troubleshooting garbled text tips.
  name: How to Load Documents Encoding Java with GroupDocs.Viewer
  steps:
  - name: Define Paths and Choose a Charset
    text: First, specify where your source file lives, where the rendered output should
      be saved, and which character set the source uses.
  - name: Configure LoadOptions with the Selected Charset
    text: Create a `LoadOptions` instance and attach the charset you defined. `LoadOptions`
      is the configuration object that tells GroupDocs.Viewer how to interpret the
      incoming byte stream.
  - name: Initialize Viewer Using LoadOptions and Render
    text: Pass the `LoadOptions` to the `Viewer` constructor so that the library knows
      how to decode the file from the start. `Viewer` is GroupDocs.Viewer’s core class
      that orchestrates rendering based on the supplied options.
  type: HowTo
- questions:
  - answer: It’s a robust library that renders over 100 document formats (PDF, DOCX,
      TXT, etc.) directly in Java applications.
    question: What is GroupDocs.Viewer for Java?
  - answer: Use `Charset.availableCharsets()` to list all supported charsets and choose
      the closest match, or convert the source file to a supported encoding before
      loading.
    question: How do I handle an unsupported charset?
  - answer: Absolutely—inject the rendering logic into a controller and return the
      generated HTML or PDF stream to the client.
    question: Can I integrate this into a Spring Boot web service?
  - answer: Providing the wrong charset, forgetting to set `LoadOptions`, or using
      a file path that points to a different file version.
    question: What are common pitfalls when setting the charset?
  - answer: Visit the [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)
      for community assistance and official support.
    question: Where can I get help if I run into issues?
  type: FAQPage
title: GroupDocs.Viewer के साथ Java में दस्तावेज़ एन्कोडिंग कैसे लोड करें
type: docs
url: /hi/java/document-loading/groupdocs-viewer-java-specific-encoding/
weight: 1
---

# GroupDocs.Viewer के साथ Java में दस्तावेज़ एन्कोडिंग लोड कैसे करें

यदि आपको एक Java एप्लिकेशन में **एन्कोडिंग के साथ दस्तावेज़ लोड** करने की सही आवश्यकता है, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम GroupDocs.Viewer को कॉन्फ़िगर करने के सटीक चरणों के माध्यम से चलेंगे ताकि किसी भी charset—चाहे UTF‑8, Shift_JIS, या ISO‑8859‑1—का टेक्स्ट सटीक रूप से रेंडर हो। आप *java encoding troubleshooting* के व्यावहारिक टिप्स भी देखेंगे जो चीज़ें सही नहीं दिखने पर आपका समय बचाते हैं। यह गाइड मुख्य कीवर्ड **load documents encoding java** पर केंद्रित है और दिखाता है कि इसे वास्तविक परिदृश्यों में कैसे लागू किया जाए।

![विशिष्ट एन्कोडिंग के साथ दस्तावेज़ लोड करना GroupDocs.Viewer for Java](/viewer/document-loading/load-documents-with-specific-encoding.png)
[विशिष्ट एन्कोडिंग के साथ दस्तावेज़ लोड करना GroupDocs.Viewer for Java](/viewer/document-loading/load-documents-with-specific-encoding.png)

**आप क्या सीखेंगे**
- GroupDocs.Viewer for Java को कैसे सेट अप करें।
- दस्तावेज़ लोड करते समय कैरेक्टर सेट कैसे निर्दिष्ट करें।
- विभिन्न भाषाओं में टेक्स्ट रेंडर करने के वास्तविक उदाहरण।
- एन्कोडिंग समस्याओं के सामान्य pitfalls और troubleshooting चरण।

## त्वरित उत्तर
- **कौन सी लाइब्रेरी दस्तावेज़ रेंडरिंग को संभालती है?** GroupDocs.Viewer for Java.  
- **कौन सा मेथड charset सेट करता है?** `LoadOptions.setCharset(Charset)`.  
- **क्या मुझे विकास के लिए लाइसेंस की आवश्यकता है?** एक मुफ्त ट्रायल टेस्टिंग के लिए काम करता है; प्रोडक्शन के लिए एक वाणिज्यिक लाइसेंस आवश्यक है।  
- **क्या मैं non‑UTF‑8 फ़ाइलें रेंडर कर सकता हूँ?** हाँ—सिर्फ सही `Charset` प्रदान करें (उदा., `shift_jis`).  
- **एक सामान्य troubleshooting चरण क्या है?** `Charset.availableCharsets()` के साथ फ़ाइल की वास्तविक एन्कोडिंग सत्यापित करें।

## “एन्कोडिंग के साथ दस्तावेज़ लोड करना” क्या है?
एन्कोडिंग के साथ दस्तावेज़ लोड करना मतलब व्यूअर को बताना है कि फ़ाइल की कच्ची बाइट स्ट्रीम को कैसे व्याख्या किया जाए ताकि अक्षर ठीक उसी तरह दिखें जैसे वे लिखे गए थे। इस चरण के बिना, आप गड़बड़ या गायब टेक्स्ट देख सकते हैं, विशेष रूप से उन भाषाओं के लिए जो मल्टीबाइट एन्कोडिंग का उपयोग करती हैं।

## Java के लिए GroupDocs.Viewer का उपयोग क्यों करें?
GroupDocs.Viewer **100 से अधिक फ़ाइल फ़ॉर्मेट**—जिसमें PDF, DOCX, XLSX, PPTX, TXT, और कई इमेज प्रकार शामिल हैं—को रेंडर करने का समर्थन करता है, जबकि आपको कैरेक्टर सेट को नियंत्रित करने की अनुमति देता है। यह मापी गई क्षमता लेगेसी दस्तावेज़ों को संभालने के अनुमान को समाप्त करती है और प्लेटफ़ॉर्म के बीच सुसंगत आउटपुट की गारंटी देती है।

## पूर्वापेक्षाएँ

### आवश्यक लाइब्रेरी और निर्भरताएँ
GroupDocs.Viewer for Java का उपयोग करने के लिए, अपनी प्रोजेक्ट में इसकी लाइब्रेरी शामिल करें। अनुशंसित तरीका Maven के माध्यम से है। इस कॉन्फ़िगरेशन को अपने `pom.xml` फ़ाइल में जोड़ें:

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

### पर्यावरण सेटअप
- Java Development Kit (JDK) 8 या उससे ऊपर।  
- Maven‑compatible IDE (IntelliJ IDEA, Eclipse, VS Code, आदि)।

### ज्ञान पूर्वापेक्षाएँ
बुनियादी Java सिंटैक्स और फ़ाइल I/O की समझ सहायक है, लेकिन हम हर चरण को सरल भाषा में समझाएंगे।

## GroupDocs.Viewer for Java को कैसे सेट अप करें

तीन सरल चरणों में अपना GroupDocs.Viewer पर्यावरण लोड करें: Maven निर्भरता जोड़ें, लाइसेंस प्राप्त करें, और Viewer ऑब्जेक्ट को इंस्टैंशिएट करें। `Viewer` वह कोर क्लास है जो दस्तावेज़ों को विभिन्न फ़ॉर्मेट में रेंडर करता है। यह संक्षिप्त तरीका आपको पाँच मिनट से कम समय में चलाने में मदद करता है, भले ही आप लाइब्रेरी में नए हों।

1. **Configure Maven** – ऊपर दिखाए गए रिपॉजिटरी और निर्भरता जोड़ें।  
2. **Obtain a License** – एक मुफ्त ट्रायल से शुरू करें या अस्थायी लाइसेंस का अनुरोध करें। प्रोडक्शन के लिए, यहाँ लाइसेंस खरीदें: [GroupDocs Purchase](https://purchase.groupdocs.com/buy).  
3. **Initialize the Viewer** – पहला कोड स्निपेट न्यूनतम सेटअप दिखाता है:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with a document path
try (Viewer viewer = new Viewer("path/to/your/document")) {
    // Document processing code will go here
}
```

## एन्कोडिंग के साथ दस्तावेज़ लोड कैसे करें

एन्कोडिंग के साथ दस्तावेज़ लोड करने के लिए स्रोत पाथ निर्धारित करें, सही `Charset` चुनें, और उन विकल्पों को Viewer को पास करें। `LoadOptions` लोडिंग व्यवहार को कॉन्फ़िगर करता है जैसे charset, और `Charset` एक कैरेक्टर एन्कोडिंग को दर्शाता है। यह तीन‑चरणीय पैटर्न सुनिश्चित करता है कि व्यूअर फ़ाइल को ठीक उसी तरह डिकोड करे जैसा इरादा है, जिससे गड़बड़ आउटपुट रोका जा सके।

### चरण 1: पाथ निर्धारित करें और Charset चुनें
पहले, यह निर्दिष्ट करें कि आपका स्रोत फ़ाइल कहाँ है, रेंडर किया गया आउटपुट कहाँ सहेजा जाना चाहिए, और स्रोत कौन सा कैरेक्टर सेट उपयोग करता है।

```java
import java.nio.charset.Charset;
import java.nio.file.Path;

String filePath = "YOUR_DOCUMENT_DIRECTORY/sample.txt"; // Replace with your actual file path
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "LoadDocumentsWithEncoding");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

// Specify the character encoding for the document
Charset charset = Charset.forName("shift_jis"); 
```

### चरण 2: चयनित Charset के साथ LoadOptions कॉन्फ़िगर करें
`LoadOptions` का एक इंस्टेंस बनाएं और आपने जो charset परिभाषित किया है उसे संलग्न करें।

`LoadOptions` वह कॉन्फ़िगरेशन ऑब्जेक्ट है जो GroupDocs.Viewer को बताता है कि आने वाली बाइट स्ट्रीम की व्याख्या कैसे की जाए।

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setCharset(charset);
```

### चरण 3: LoadOptions का उपयोग करके Viewer को इनिशियलाइज़ करें और रेंडर करें
`LoadOptions` को `Viewer` कंस्ट्रक्टर में पास करें ताकि लाइब्रेरी को शुरू से फ़ाइल को डिकोड करने का तरीका पता चल सके। `Viewer` GroupDocs.Viewer की कोर क्लास है जो प्रदान किए गए विकल्पों के आधार पर रेंडरिंग का समन्वय करती है।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer(filePath, loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document with specified view options
}
```

#### मुख्य पैरामीटरों की व्याख्या
- **`LoadOptions.setCharset(Charset charset)`** – GroupDocs.Viewer को बताता है कि कौन सी एन्कोडिंग लागू करनी है।  
- **`HtmlViewOptions` यह निर्धारित करता है कि HTML आउटपुट कैसे उत्पन्न किया जाता है, जिसमें रिसोर्स एम्बेडिंग शामिल है।**  
- **`HtmlViewOptions.forEmbeddedResources(Path pageFilePathFormat)`** – सभी रिसोर्स (इमेज, CSS) एम्बेडेड के साथ HTML पेज बनाता है, जो निर्दिष्ट पाथ पैटर्न के तहत संग्रहीत होते हैं।

## Java एन्कोडिंग ट्रबलशूटिंग टिप्स
यदि रेंडर किया गया टेक्स्ट गड़बड़ दिखता है, तो इन सटीक चरणों का पालन करें:

1. **फ़ाइल के वास्तविक charset की पुष्टि करें** – इसे ऐसे टेक्स्ट एडिटर में खोलें जो एन्कोडिंग जानकारी दिखा सके, या `Charset.availableCharsets()` का उपयोग करके एक छोटा Java स्निपेट चलाएँ।  
2. **charset को बिल्कुल मिलाएँ** – `Charset.forName("UTF-8")` बनाम `"utf-8"` केस‑इंसेंसिटिव हैं, लेकिन वर्तनी महत्वपूर्ण है (`"shift_jis"` बनाम `"Shift_JIS"`).  
3. **फ़ाइल अनुमतियों की जाँच करें** – IOExceptions अक्सर इनकोडिंग मिसमैच की बजाय पहुँच न योग्य पाथ्स से उत्पन्न होते हैं।  
4. **आउटपुट डायरेक्टरी की समीक्षा करें** – सुनिश्चित करें कि एप्लिकेशन के पास लिखने की अनुमति है; अन्यथा HTML पेज नहीं बनेंगे।

## व्यावहारिक अनुप्रयोग
- **Content Management Systems** – उपयोगकर्ता‑अपलोडेड दस्तावेज़ों को उनकी मूल भाषा में मैन्युअल रूपांतरण के बिना रेंडर करें।  
- **E‑commerce Platforms** – प्रोडक्ट मैनुअल दिखाएँ जो क्षेत्रीय एन्कोडिंग में लिखे गए थे।  
- **Document Archiving** – लेगेसी दस्तावेज़ों (जैसे पुराने जापानी PDFs) को सही कैरेक्टर प्रतिनिधित्व के साथ संरक्षित रखें।

## प्रदर्शन संबंधी विचार
- बड़े फ़ाइलों को अलग थ्रेड में प्रोसेस करें ताकि UI रिस्पॉन्सिव रहे।  
- अपेक्षित दस्तावेज़ आकार के आधार पर JVM हीप साइज (`-Xmx`) को ट्यून करें।  
- try‑with‑resources (जैसा दिखाया गया) का उपयोग करें ताकि नेटिव रिसोर्सेज तुरंत रिलीज़ हों।

## निष्कर्ष
अब आपके पास GroupDocs.Viewer for Java का उपयोग करके **एन्कोडिंग के साथ दस्तावेज़ लोड** करने की एक पूर्ण, प्रोडक्शन‑रेडी विधि है। यह तरीका सामान्य *java encoding troubleshooting* समस्याओं को समाप्त करता है और आपको बहुभाषी कंटेंट को आसानी से सपोर्ट करने में सक्षम बनाता है।

**अगले कदम**
- `windows-1252` या `utf-16` जैसे अन्य charsets के साथ प्रयोग करें।  
- [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) के साथ व्यू कस्टमाइज़ेशन में गहराई से जाएँ।

## अक्सर पूछे जाने वाले प्रश्न

**Q: GroupDocs.Viewer for Java क्या है?**  
A: यह एक मजबूत लाइब्रेरी है जो 100 से अधिक दस्तावेज़ फ़ॉर्मेट (PDF, DOCX, TXT, आदि) को सीधे Java एप्लिकेशन में रेंडर करती है।

**Q: मैं असमर्थित charset को कैसे संभालूँ?**  
A: `Charset.availableCharsets()` का उपयोग करके सभी समर्थित charsets की सूची प्राप्त करें और सबसे नज़दीकी मिलान चुनें, या लोड करने से पहले स्रोत फ़ाइल को समर्थित एन्कोडिंग में बदलें।

**Q: क्या मैं इसे Spring Boot वेब सर्विस में इंटीग्रेट कर सकता हूँ?**  
A: बिल्कुल—रेंडरिंग लॉजिक को कंट्रोलर में इंजेक्ट करें और जेनरेटेड HTML या PDF स्ट्रीम को क्लाइंट को रिटर्न करें।

**Q: charset सेट करते समय सामान्य pitfalls क्या हैं?**  
A: गलत charset प्रदान करना, `LoadOptions` सेट करना भूल जाना, या ऐसा फ़ाइल पाथ उपयोग करना जो अलग फ़ाइल संस्करण की ओर इशारा करता है।

**Q: यदि मुझे समस्याएँ आती हैं तो मैं मदद कहाँ पा सकता हूँ?**  
A: समुदाय सहायता और आधिकारिक समर्थन के लिए [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9) पर जाएँ।

---

**अंतिम अपडेट:** 2026-05-21  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs  

## संसाधन
- [डॉक्यूमेंटेशन](https://docs.groupdocs.com/viewer/java/)
- [API रेफ़रेंस](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer डाउनलोड करें](https://releases.groupdocs.com/viewer/java/)
- [लाइसेंस खरीदें](https://purchase.groupdocs.com/buy)
- [फ़्री ट्रायल](https://releases.groupdocs.com/viewer/java/)
- [अस्थायी लाइसेंस](https://purchase.groupdocs.com/temporary-license/)

## संबंधित ट्यूटोरियल

- [Java में URL लोड कैसे करें - दस्तावेज़ लोडिंग ट्यूटोरियल - GroupDocs.Viewer उदाहरण और सर्वोत्तम प्रथाएँ](/viewer/java/document-loading/)
- [GroupDocs.Viewer Java में लाइसेंस सेट कैसे करें: फ़ाइल और URL सेटअप गाइड](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)
- [GroupDocs.Viewer for Java का उपयोग करके दस्तावेज़ों को HTML के रूप में लोड और रेंडर कैसे करें](/viewer/java/rendering-basics/groupdocs-viewer-java-html-rendering/)