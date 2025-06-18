---
"date": "2025-04-24"
"description": "Java के लिए GroupDocs.Viewer का उपयोग करके TXT फ़ाइलों को HTML, JPG, PNG और PDF जैसे कई प्रारूपों में कुशलतापूर्वक परिवर्तित करना सीखें। इस चरण-दर-चरण मार्गदर्शिका का पालन करें।"
"title": "Java के लिए GroupDocs.Viewer का उपयोग करके TXT फ़ाइलों को HTML, JPG, PNG और PDF में कनवर्ट करें"
"url": "/hi/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/"
"weight": 1
---

# Java के लिए GroupDocs.Viewer के साथ TXT फ़ाइलों को कनवर्ट करें: एक व्यापक गाइड

## परिचय

आज की डिजिटल दुनिया में, कुशल दस्तावेज़ प्रबंधन व्यवसायों और व्यक्तियों दोनों के लिए महत्वपूर्ण है। चाहे आपको वेब पर टेक्स्ट दस्तावेज़ प्रदर्शित करने की आवश्यकता हो या विभिन्न प्रारूपों में फ़ाइलों को संग्रहित करना हो, टेक्स्ट (TXT) फ़ाइलों को परिवर्तित करना एक लगातार आवश्यकता है। **जावा के लिए GroupDocs.Viewer** TXT फ़ाइलों को HTML, JPG, PNG, और PDF जैसे कई फ़ॉर्मेट में आसानी से रेंडर करने के लिए एक प्रभावी समाधान प्रदान करता है। यह गाइड आपको सहज रूपांतरण प्राप्त करने के लिए इस बहुमुखी लाइब्रेरी का उपयोग करने के बारे में बताएगा।

### आप क्या सीखेंगे:
- अपने Java वातावरण में GroupDocs.Viewer सेट अप करना
- TXT फ़ाइलों को बहु-पृष्ठ और एकल-पृष्ठ HTML में परिवर्तित करना
- TXT दस्तावेज़ों को छवि प्रारूपों में प्रस्तुत करना (JPG, PNG)
- TXT सामग्री को PDF प्रारूप में बदलना

आइए कार्यान्वयन शुरू करने से पहले आवश्यक पूर्वापेक्षाओं पर गौर करें।

## आवश्यक शर्तें

Java के लिए GroupDocs.Viewer में प्रवेश करने से पहले, सुनिश्चित करें कि आपके पास:

### आवश्यक लाइब्रेरी और निर्भरताएँ:
- **जावा के लिए GroupDocs.Viewer** संस्करण 25.2 या बाद का.
  
### पर्यावरण सेटअप आवश्यकताएँ:
- आपके सिस्टम पर एक संगत जावा डेवलपमेंट किट (JDK) स्थापित है (जावा 8+ अनुशंसित)।
- एक एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA, Eclipse, या NetBeans.

### ज्ञान पूर्वापेक्षाएँ:
- जावा प्रोग्रामिंग और फ़ाइल हैंडलिंग की बुनियादी समझ।
- निर्भरता प्रबंधन के लिए मावेन से परिचित होना उपयोगी है।

## Java के लिए GroupDocs.Viewer सेट अप करना

उपयोग शुरू करने के लिए **ग्रुपडॉक्स.व्यूअर**इसे मावेन के माध्यम से अपने प्रोजेक्ट में निम्नानुसार शामिल करें:

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

### लाइसेंस प्राप्ति चरण:
- एक से शुरू करें **मुफ्त परीक्षण** या प्राप्त करें **अस्थायी लाइसेंस** GroupDocs.Viewer की पूर्ण क्षमताओं का पता लगाने के लिए।
- उनके आधिकारिक माध्यम से लाइसेंस खरीदने पर विचार करें [खरीद पृष्ठ](https://purchase.groupdocs.com/buy) दीर्घकालिक उपयोग के लिए।

### बुनियादी आरंभीकरण और सेटअप:
1. अपने प्रोजेक्ट में Maven निर्भरता जोड़ें.
2. सुनिश्चित करें कि आपने अपना वातावरण JDK और IDE के साथ स्थापित किया है।

अब, आइए देखें कि TXT फ़ाइलों को विभिन्न स्वरूपों में परिवर्तित करने के लिए GroupDocs.Viewer की विभिन्न सुविधाओं को कैसे लागू किया जाए।

## कार्यान्वयन मार्गदर्शिका

### फ़ीचर 1: TXT को मल्टी-पेज HTML में रेंडर करें

#### अवलोकन:
यह सुविधा TXT दस्तावेज़ को बहु-पृष्ठ HTML प्रारूप में परिवर्तित करती है, तथा कई वेब पृष्ठों पर पाठ संरचना को संरक्षित रखती है।

##### चरण:

**आवश्यक लाइब्रेरीज़ आयात करें**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**पथ और व्यूअर सेट अप करें**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // एम्बेडेड संसाधनों के साथ रेंडरिंग के लिए विकल्प कॉन्फ़िगर करें
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // इन विकल्पों का उपयोग करके दस्तावेज़ को HTML में प्रस्तुत करें
    viewer.view(options);
}
```

**स्पष्टीकरण:**
- `HtmlViewOptions.forEmbeddedResources` यहां इसका उपयोग यह सुनिश्चित करने के लिए किया जाता है कि सभी संसाधन आउटपुट फ़ाइलों के भीतर अंतर्निहित हों, जिससे वे आत्मनिर्भर बन सकें।

### फ़ीचर 2: TXT को एकल-पृष्ठ HTML में प्रस्तुत करें

#### अवलोकन:
यह सुविधा आपके संपूर्ण पाठ दस्तावेज़ को एकल HTML पृष्ठ में संक्षिप्त कर देती है, जो त्वरित पूर्वावलोकन या सारांश के लिए आदर्श है।

##### चरण:

**आवश्यक लाइब्रेरीज़ आयात करें**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**पथ और व्यूअर सेट अप करें**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // एम्बेडेड संसाधनों के साथ रेंडरिंग के लिए विकल्प कॉन्फ़िगर करें
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // एकल पृष्ठ HTML के रूप में रेंडर करने का विकल्प सेट करें
    options.setRenderToSinglePage(true);
    
    // इन विकल्पों का उपयोग करके दस्तावेज़ प्रस्तुत करें
    viewer.view(options);
}
```

**स्पष्टीकरण:**
The `setRenderToSinglePage(true)` यह विधि सभी पाठ को एक वेब पेज में संक्षिप्त कर देती है।

### फ़ीचर 3: TXT को JPG में रेंडर करें

#### अवलोकन:
अपनी TXT फ़ाइलों को उच्च गुणवत्ता वाली JPEG छवियों में परिवर्तित करें, जो साझा करने या मुद्रण के लिए उपयुक्त हों।

##### चरण:

**आवश्यक लाइब्रेरीज़ आयात करें**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**पथ और व्यूअर सेट अप करें**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // JPEG छवि को रेंडर करने के लिए विकल्प कॉन्फ़िगर करें
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // इन विकल्पों का उपयोग करके दस्तावेज़ को JPG के रूप में प्रस्तुत करें
    viewer.view(options);
}
```

**स्पष्टीकरण:**
- `JpgViewOptions` आपको छवि रूपांतरण के लिए अनुकूलित आउटपुट पथ और रेंडरिंग सेटिंग्स निर्दिष्ट करने की अनुमति देता है।

### फ़ीचर 4: TXT को PNG में रेंडर करें

#### अवलोकन:
पाठ्य दस्तावेजों को पोर्टेबल नेटवर्क ग्राफिक्स (पीएनजी) प्रारूप में परिवर्तित करें, हानि रहित संपीड़न के साथ उच्च गुणवत्ता वाली छवियां प्रदान करें।

##### चरण:

**आवश्यक लाइब्रेरीज़ आयात करें**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**पथ और व्यूअर सेट अप करें**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // PNG छवि में रेंडरिंग के लिए विकल्प कॉन्फ़िगर करें
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // इन विकल्पों का उपयोग करके दस्तावेज़ को PNG के रूप में प्रस्तुत करें
    viewer.view(options);
}
```

**स्पष्टीकरण:**
- `PngViewOptions` यहाँ प्रयोग किया गया है, इसी के समान `JpgViewOptions`, लेकिन PNG प्रारूप के लिए विशिष्ट लाभ के साथ।

### फ़ीचर 5: TXT को PDF में रेंडर करें

#### अवलोकन:
पाठ्य दस्तावेजों से पीडीएफ फाइलें उत्पन्न करें, जो सार्वभौमिक रूप से स्वीकृत प्रारूप में वितरण या संग्रह के लिए आदर्श हैं।

##### चरण:

**आवश्यक लाइब्रेरीज़ आयात करें**
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**पथ और व्यूअर सेट अप करें**
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // PDF में रेंडर करने के लिए विकल्प कॉन्फ़िगर करें
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // इन विकल्पों का उपयोग करके दस्तावेज़ को PDF के रूप में प्रस्तुत करें
    viewer.view(options);
}
```

**स्पष्टीकरण:**
- `PdfViewOptions` पृष्ठ सेटअप और संसाधन एम्बेडिंग सहित पीडीएफ रूपांतरण के लिए विशिष्ट सेटिंग्स प्रदान करता है।

## व्यावहारिक अनुप्रयोगों

GroupDocs.Viewer for Java की क्षमताएं कई व्यावहारिक उपयोग मामलों तक विस्तारित होती हैं:

1. **दस्तावेज़ प्रबंधन प्रणालियाँ:** आंतरिक पोर्टलों के लिए पाठ-आधारित दस्तावेज़ीकरण को वेब-अनुकूल प्रारूपों में परिवर्तित करने को स्वचालित करना।
2. **प्रकाशन प्लेटफार्म:** सामग्री प्रबंधन प्रणालियों में निर्बाध एकीकरण के लिए लेखक की प्रस्तुतियों को TXT से HTML में परिवर्तित करें।
3. **संग्रहण समाधान:** विरासत पाठ फ़ाइलों को आधुनिक, आसानी से सुलभ पीडीएफ या छवि प्रारूपों में संरक्षित करें।
4. **क्लाउड स्टोरेज के साथ एकीकरण:** बेहतर पहुंच के लिए क्लाउड प्लेटफॉर्म पर दस्तावेजों को स्वचालित रूप से परिवर्तित और संग्रहीत करें।