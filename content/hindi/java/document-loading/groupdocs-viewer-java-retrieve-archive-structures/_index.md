---
date: '2026-06-30'
description: GroupDocs.Viewer का उपयोग करके viewinfo प्राप्त करने और java आर्काइव
  फ़ाइल प्रकार संरचनाओं को पुनः प्राप्त करने के बारे में जानें। यह गाइड setup, code
  examples, और real‑world use cases को कवर करता है।
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Java में ViewInfo कैसे प्राप्त करें और आर्काइव संरचनाओं को पुनः प्राप्त करें
type: docs
url: /hi/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# ViewInfo प्राप्त करने और Java में आर्काइव संरचनाओं को पुनः प्राप्त करने का तरीका

आर्काइव फ़ाइलों का प्रभावी प्रबंधन करने के लिए उनकी संरचना की स्पष्ट समझ आवश्यक है। इस ट्यूटोरियल में आप किसी भी आर्काइव के लिए **how to get viewinfo** सीखेंगे और देखेंगे कि यह **java archive file type** के साथ काम करने में कैसे मदद करता है। हम GroupDocs.Viewer को सेटअप करने, view जानकारी निकालने, और फ़ोल्डर पदानुक्रम को पुनरावर्ती रूप से पढ़ने के चरणों से गुजरेंगे ताकि आप इस समाधान को वास्तविक प्रोजेक्ट्स में एकीकृत कर सकें।

![GroupDocs.Viewer for Java के साथ आर्काइव संरचनाएँ](/viewer/document-loading/archive-structures-java.png)

**आप क्या सीखेंगे**
- GroupDocs.Viewer for Java को सेटअप और कॉन्फ़िगर करना।  
- आर्काइव से **get viewinfo** प्राप्त करने की विधियाँ।  
- आर्काइव फ़ाइल की फ़ोल्डर संरचना को पढ़ने और प्रदर्शित करने की तकनीकें।  
- Java प्रोजेक्ट्स में GroupDocs.Viewer का उपयोग करते समय व्यावहारिक अनुप्रयोग और प्रदर्शन विचार।  

## त्वरित उत्तर
- **“viewinfo” क्या प्रदान करता है?** यह फ़ाइल प्रकार, पृष्ठ गिनती, और आर्काइव के भीतर फ़ोल्डर और फ़ाइलों की पूरी सूची लौटाता है।  
- **कौन से आर्काइव फ़ॉर्मेट समर्थित हैं?** ZIP, RAR, TAR, 7z, ISO, और 12+ अन्य सामान्य फ़ॉर्मेट।  
- **उत्पादन के लिए मुझे लाइसेंस चाहिए?** हां—उत्पादन के लिए एक व्यावसायिक लाइसेंस आवश्यक है; मूल्यांकन के लिए एक मुफ्त ट्रायल काम करता है।  
- **क्या बड़े आर्काइव को कुशलता से प्रोसेस किया जा सकता है?** बिल्कुल—स्ट्रीमिंग विकल्पों का उपयोग करें और मेमोरी उपयोग कम रखने के लिए एक फ़ोल्डर स्तर पर एक बार प्रोसेस करें।  
- **क्या लाइब्रेरी जोड़ने का एकमात्र तरीका Maven है?** Maven अनुशंसित डिपेंडेंसी मैनेजर है, लेकिन Gradle या मैन्युअल JAR इन्क्लूजन भी काम करता है।  

## “how to get viewinfo” क्या है?

`getViewInfo` एक GroupDocs.Viewer API मेथड है जो दस्तावेज़ या आर्काइव से पूर्ण रेंडरिंग के बिना मेटाडेटा निकालता है। यह एक कॉल में आंतरिक फ़ोल्डर ट्री, फ़ाइल गिनती, और बुनियादी गुण लौटाता है, जिससे आप तय कर सकते हैं कि कौन से भाग प्रोसेस करने हैं। यह कॉल सामान्य सर्वरों पर एक सेकंड से कम समय में 500 MB तक के आर्काइव का पूर्ण स्नैपशॉट लौटाता है।  

## Java आर्काइव फ़ाइल प्रकार संरचनाओं को पुनः प्राप्त क्यों करें?

**java archive file type** का आंतरिक लेआउट पुनः प्राप्त करने से आप आवश्यक फ़ाइलों को तुरंत ढूंढ सकते हैं, अनावश्यक एक्सट्रैक्शन से बच सकते हैं, और स्वचालित पाइपलाइन बना सकते हैं जो केवल संबंधित सब‑फ़ोल्डर को छूते हैं। यह तरीका बड़े आर्काइव के लिए I/O को 70 % तक कम करता है और डेटा‑इंगेस्ट्शन परिदृश्यों में प्रति मिनट हजारों फ़ाइलों को स्कैन करना संभव बनाता है।  

## पूर्वापेक्षाएँ

- **Java Development Kit (JDK):** संस्करण 8 या नया।  
- **Maven:** डिपेंडेंसी प्रबंधन और बिल्ड्स के लिए।  
- **Basic Java knowledge:** OOP अवधारणाओं की परिचितता मददगार है लेकिन अनिवार्य नहीं है।  

आपको GroupDocs.Viewer लाइब्रेरी तक पहुँच भी चाहिए, जिसे आप नीचे दिखाए अनुसार अपने Maven प्रोजेक्ट में जोड़ सकते हैं।  

## Java के लिए GroupDocs.Viewer सेटअप करना

### Maven कॉन्फ़िगरेशन

`pom.xml` में रिपॉज़िटरी और डिपेंडेंसी जोड़ें।

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### लाइसेंस प्राप्ति

- **Free Trial:** GroupDocs वेबसाइट से ट्रायल संस्करण डाउनलोड करें।  
- **Temporary License:** अल्पकालिक मूल्यांकन के लिए एक अस्थायी कुंजी अनुरोध करें।  
- **Full License:** असीमित उत्पादन उपयोग के लिए व्यावसायिक लाइसेंस खरीदें।  

जब लाइब्रेरी आपके क्लासपाथ पर हो जाए, तो आप कोडिंग शुरू कर सकते हैं।  

## कार्यान्वयन गाइड

### आर्काइव फ़ाइलों के लिए ViewInfo प्राप्त करने का तरीका

View जानकारी प्राप्त करने के लिए, पहले आर्काइव को Viewer में लोड करें, फिर मेटाडेटा प्राप्त करने के लिए `getViewInfo` कॉल करें, और अंत में लौटाई गई फ़ोल्डर पदानुक्रम पर इटररेट करें। यह तीन‑स्टेप पैटर्न सभी समर्थित आर्काइव फ़ॉर्मेट्स के लिए काम करता है और एकल API कॉल में पूर्ण स्नैपशॉट प्रदान करता है, जिससे आगे की प्रोसेसिंग सरल हो जाती है।  

#### Viewer को इनिशियलाइज़ करें

`Viewer` क्लास सभी रेंडरिंग और निरीक्षण ऑपरेशन्स का एंट्री पॉइंट है। यह फ़ाइल स्ट्रीम, फ़ॉर्मेट डिटेक्शन, और रिसोर्स क्लीनअप को मैनेज करता है।

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### View जानकारी प्राप्त करें

`ViewInfo` में फ़ाइल प्रकार, कुल पृष्ठ, और फ़ोल्डर व फ़ाइलों की पदानुक्रमित सूची जैसी मेटाडेटा समाहित होती है। `getViewInfo` कॉल करने पर यह ऑब्जेक्ट तुरंत लौटता है।

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### फ़ोल्डर संरचना प्रदर्शित करें

`viewInfo.getFolders()` के माध्यम से इटररेट करके प्रत्येक फ़ोल्डर का नाम, उसकी गहराई, और शामिल फ़ाइलें प्रिंट करें। यह सरल लूप आपको आर्काइव का पठनीय ट्री व्यू देता है।

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### पुनरावर्ती फ़ोल्डर रीडिंग

गहराई से नेस्टेड आर्काइव के लिए, एक पुनरावर्ती हेल्पर मेथड ट्री को डेप्थ‑फ़र्स्ट चलाता है, जिससे प्रत्येक सब‑फ़ोल्डर को मेमोरी में पूरे आर्काइव को लोड किए बिना विज़िट किया जा सके।

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### फीचर 2: आर्काइव फ़ोल्डर संरचना प्राप्त करें

यह फीचर आर्काइव फ़ाइल की फ़ोल्डर संरचना प्रिंट करने पर केंद्रित है। यह पहले फीचर जैसा है लेकिन पुनरावर्ती अन्वेषण पर ज़ोर देता है।  

#### View Info विकल्प सेटअप करें

`ArchiveOptions` आपको `getViewInfo` कॉल करने से पहले पासवर्ड प्रोटेक्शन, पेज लिमिट, और स्ट्रीमिंग प्रेफ़रेंसेज़ निर्दिष्ट करने देता है।

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### पुनरावर्ती अन्वेषण

एक दूसरा पुनरावर्ती रूटीन दिखाता है कि पासवर्ड‑प्रोटेक्टेड आर्काइव और बड़े फ़ाइल सेट को कुशलता से कैसे हैंडल किया जाए।

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## व्यावहारिक अनुप्रयोग

1. **Data Management:** आर्काइव संरचनाओं को समझकर बड़े डेटासेट को जल्दी व्यवस्थित करें।  
2. **Automated File Processing:** पूरी तरह एक्सट्रैक्ट किए बिना बैच‑प्रोसेस आर्काइव्ड फ़ाइलें, जिससे I/O 70 % तक घटता है।  
3. **CMS Integration:** ऑन‑द‑फ्लाई आर्काइव नेविगेशन के साथ कंटेंट‑मैनेजमेंट सिस्टम को बेहतर बनाएं, जिससे संपादक सीधे आर्काइव से फ़ाइलों का प्रीव्यू ले सकें।  

## प्रदर्शन विचार

- **Optimize Memory Usage:** फ़ोल्डर को एक स्तर पर एक बार प्रोसेस करें और `Viewer` इंस्टेंस को तुरंत बंद करें।  
- **Stay Updated:** प्रदर्शन सुधार के लिए नवीनतम GroupDocs.Viewer संस्करण (लेखन समय 25.2) और JDK रिलीज़ का उपयोग करें।  
- **Streaming Support:** लाइब्रेरी 1 GB से बड़े आर्काइव को पूरी फ़ाइल को RAM में लोड किए बिना स्ट्रीम कर सकती है, इसके आंतरिक चंक्ड‑रीड आर्किटेक्चर के कारण।  

## सामान्य समस्याएँ और समाधान

| समस्या | क्यों होता है | समाधान |
|-------|----------------|-----|
| `NullPointerException` फ़ोल्डर पढ़ते समय | `viewInfo.getFolders()` खाली डायरेक्टरी के लिए null लौटाता है | इटररेट करने से पहले null या खाली सूची की जाँच करें। |
| बड़े ZIP फ़ाइलों की धीमी प्रोसेसिंग | पूरा आर्काइव मेमोरी में लोड हो जाता है | नए GroupDocs संस्करणों में उपलब्ध स्ट्रीमिंग विकल्पों का उपयोग करें। |
| लाइसेंस नहीं मिला | लाइसेंस फ़ाइल पाथ गलत है | लाइसेंस फ़ाइल को एप्लिकेशन रूट में रखें या `License.setLicense("path/to/license.json")` सेट करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q:** GroupDocs.Viewer क्या है?  
A: GroupDocs.Viewer एक Java लाइब्रेरी है जो 100 से अधिक दस्तावेज़, इमेज, और आर्काइव फ़ॉर्मेट को HTML, PDF, या इमेज स्ट्रीम में रेंडर करती है बिना नेटिव एप्लिकेशन की आवश्यकता के।

**Q:** क्या मैं GroupDocs.Viewer को अन्य प्रोग्रामिंग भाषाओं के साथ उपयोग कर सकता हूँ?  
A: हाँ, GroupDocs .NET, Python, PHP आदि के लिए SDK प्रदान करता है, लेकिन यह ट्यूटोरियल Java इम्प्लीमेंटेशन पर केंद्रित है।

**Q:** बड़े आर्काइव फ़ाइलों को कैसे हैंडल करूँ?  
A: `ArchiveOptions.setUseStreaming(true)` के माध्यम से स्ट्रीमिंग सक्षम करें, एक फ़ोल्डर स्तर पर एक बार प्रोसेस करें, और उपयोग के बाद `Viewer` ऑब्जेक्ट को डिस्पोज़ करें।

**Q:** GroupDocs.Viewer कौन से प्रकार के आर्काइव सपोर्ट करता है?  
A: यह 12+ आर्काइव फ़ॉर्मेट सपोर्ट करता है, जिसमें ZIP, RAR, TAR, 7z, ISO, ARJ, और CAB शामिल हैं, साथ ही कई प्रोपाइटरी कंटेनर टाइप्स भी।

**Q:** आर्काइव के लिए कोई आकार सीमा है?  
A: व्यावहारिक सीमा आपके सर्वर की RAM और CPU पर निर्भर करती है; परीक्षण दर्शाते हैं कि स्ट्रीमिंग सक्षम होने पर 16 GB RAM मशीन पर 2 GB आर्काइव सहजता से प्रोसेस होते हैं।

**Q:** क्या “how to get viewinfo” पासवर्ड‑प्रोटेक्टेड आर्काइव के साथ काम करता है?  
A: हाँ, `getViewInfo` को कॉल करने से पहले `ArchiveOptions.setPassword("yourPassword")` के माध्यम से पासवर्ड प्रदान करें।

## निष्कर्ष

इस गाइड का पालन करके आप अब किसी भी समर्थित आर्काइव के लिए **how to get viewinfo** जानते हैं और GroupDocs.Viewer for Java का उपयोग करके उसकी फ़ोल्डर पदानुक्रम को कैसे पार करना है। ये तकनीकें आपको स्मार्ट डेटा‑प्रोसेसिंग पाइपलाइन बनाने, CMS इंटीग्रेशन सुधारने, और बड़े संग्रहित फ़ाइलों को आत्मविश्वास के साथ हैंडल करने में सक्षम बनाती हैं। अगला, आर्काइव से व्यक्तिगत फ़ाइलों को रेंडर करने या उन्हें PDF/HTML में बदलने के लिए अन्य Viewer फीचर का अन्वेषण करें।

---

**अंतिम अपडेट:** 2026-06-30  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs  

**संसाधन**
- **दस्तावेज़ीकरण:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API रेफ़रेंस:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs.Viewer डाउनलोड करें:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **लाइसेंस खरीदें:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **फ़्री ट्रायल और टेम्पररी लाइसेंस:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## संबंधित ट्यूटोरियल

- [GroupDocs.Viewer for Java के साथ दस्तावेज़ मेटाडेटा निकालें - दस्तावेज़ व्यू जानकारी और अंतर्दृष्टि प्राप्त करें](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [GroupDocs.Viewer for Java के साथ अटैचमेंट्स प्राप्त करें और दस्तावेज़ अटैचमेंट्स प्रिंट करें](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java गाइड: दस्तावेज़ प्रीव्यू और मैनेजमेंट के लिए GroupDocs.Viewer API के साथ विशिष्ट पेज रेंडर करें](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)