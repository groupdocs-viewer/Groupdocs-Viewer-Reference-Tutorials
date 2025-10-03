---
"date": "2025-04-24"
"description": "GroupDocs.Viewer Java का उपयोग करके Excel फ़ाइलों को HTML, JPG, PNG और PDF में बदलने का तरीका जानें। यह गाइड सेटअप, रेंडरिंग विकल्प और व्यावहारिक अनुप्रयोगों को कवर करता है।"
"title": "Excel के लिए GroupDocs.Viewer Java का उपयोग करके HTML/JPG/PNG/PDF रूपांतरण कैसे करें&#58; एक चरण-दर-चरण मार्गदर्शिका"
"url": "/hi/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/"
"weight": 1
type: docs
---
# Excel के लिए GroupDocs.Viewer Java का उपयोग HTML/JPG/PNG/PDF रूपांतरण में कैसे करें: एक चरण-दर-चरण मार्गदर्शिका

## परिचय

स्प्रेडशीट डेटा को HTML, JPG, PNG या PDF जैसे विभिन्न फ़ॉर्मेट में बदलना, साथ ही पंक्ति और कॉलम हेडिंग जैसे महत्वपूर्ण विवरण को बनाए रखना कई परिदृश्यों में ज़रूरी है। चाहे आप रिपोर्ट बना रहे हों, हितधारकों के साथ जानकारी साझा कर रहे हों या स्प्रेडशीट को वेब एप्लिकेशन में एकीकृत कर रहे हों, एक्सेल शीट को परिवर्तित करना एक महत्वपूर्ण आवश्यकता हो सकती है। यह मार्गदर्शिका आपको बताएगी कि GroupDocs.Viewer Java इन कार्यों को कैसे आसान और सटीक बनाता है।

**आप क्या सीखेंगे:**
- Java के लिए GroupDocs.Viewer सेट अप करना और उसका उपयोग करना
- एक्सेल फाइलों को HTML, JPG, PNG, और PDF प्रारूपों में प्रस्तुत करना
- अपने आउटपुट में पंक्ति और स्तंभ शीर्षकों को शामिल करने के लिए विकल्पों को कॉन्फ़िगर करना
- प्रस्तुत दस्तावेजों के व्यावहारिक अनुप्रयोग

आइए कार्यान्वयन से पहले आवश्यक पूर्वापेक्षाओं से शुरुआत करें।

## आवश्यक शर्तें

GroupDocs.Viewer Java के साथ स्प्रेडशीट प्रस्तुत करने से पहले, सुनिश्चित करें कि आपके पास:

### आवश्यक लाइब्रेरी और निर्भरताएँ

Maven का उपयोग करके Java के लिए GroupDocs.Viewer सेट करें। इसे अपने प्रोजेक्ट में शामिल करने का तरीका यहां बताया गया है:

**मावेन सेटअप:**
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
- सुनिश्चित करें कि आपके पास जावा डेवलपमेंट किट (JDK) स्थापित है।
- विकास की सुविधा के लिए IntelliJ IDEA या Eclipse जैसे IDE का उपयोग करें।

### ज्ञान पूर्वापेक्षाएँ
- जावा प्रोग्रामिंग से परिचित होना
- निर्भरता प्रबंधन के लिए मावेन की बुनियादी समझ

इन पूर्वावश्यकताओं के साथ, चलिए Java के लिए GroupDocs.Viewer सेट अप करना शुरू करते हैं और सुविधाओं को लागू करना शुरू करते हैं।

## Java के लिए GroupDocs.Viewer सेट अप करना

GroupDocs.Viewer for Java एक बहुमुखी लाइब्रेरी है जो आपको विभिन्न प्रारूपों में दस्तावेज़ प्रस्तुत करने की अनुमति देती है। आरंभ करने का तरीका यहां बताया गया है:

### स्थापना जानकारी
जैसा कि बताया गया है, अपने प्रोजेक्ट में निर्भरता के रूप में GroupDocs.Viewer जोड़ने के लिए Maven का उपयोग करें `pom.xml` फ़ाइल।

### लाइसेंस प्राप्ति चरण
1. **मुफ्त परीक्षण:** परीक्षण संस्करण यहां से डाउनलोड करें [ग्रुपडॉक्स निःशुल्क परीक्षण](https://releases.groupdocs.com/viewer/java/).
2. **अस्थायी लाइसेंस:** अधिक सुविधाओं के लिए अस्थायी लाइसेंस प्राप्त करें [ग्रुपडॉक्स अस्थायी लाइसेंस](https://purchase.groupdocs.com/temporary-license/).
3. **खरीदना:** पूर्ण पहुँच और समर्थन के लिए, यहाँ से लाइसेंस खरीदें [ग्रुपडॉक्स खरीदें](https://purchase.groupdocs.com/buy).

### मूल आरंभीकरण
एक बार इंस्टॉल हो जाने पर, आप GroupDocs.Viewer को निम्न के साथ आरंभ कर सकते हैं:
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("Sample.xlsx")) {
            // व्यूअर का उपयोग करने के लिए आपका कोड यहाँ है
        }
    }
}
```
यह आपके परिवेश को आरंभ करता है, तथा आपको दस्तावेज़ प्रस्तुत करने के लिए तैयार करता है।

## कार्यान्वयन मार्गदर्शिका

आइये प्रत्येक सुविधा का विश्लेषण करें और विस्तार से देखें कि उन्हें कैसे क्रियान्वित किया जाए।

### स्प्रेडशीट को HTML में प्रस्तुत करें
**अवलोकन:** वेब प्रस्तुतियों या रिपोर्टों के लिए पंक्ति और स्तंभ शीर्षकों को संरक्षित करते हुए एक्सेल शीट को HTML प्रारूप में परिवर्तित करें।

#### चरण-दर-चरण कार्यान्वयन:
##### 1. आवश्यक लाइब्रेरीज़ आयात करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```
##### 2. आउटपुट निर्देशिका सेट करें
निर्धारित करें कि आपकी रेंडर की गई फ़ाइलें कहाँ संग्रहीत की जाएंगी.
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
##### 3. व्यूअर आरंभ करें और विकल्प कॉन्फ़िगर करें
दस्तावेज़ को रेंडर करने के लिए GroupDocs.Viewer का उपयोग करें:
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    
    // स्प्रेडशीट में पंक्ति और स्तंभ शीर्षकों का रेंडरिंग सक्षम करें.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // पृष्ठ 1 से 3 तक प्रस्तुत करें.
}
```
**स्पष्टीकरण:** The `HtmlViewOptions` क्लास का उपयोग HTML आउटपुट को कॉन्फ़िगर करने के लिए किया जाता है। `setRenderHeadings(true)` यह सुनिश्चित करता है कि पंक्ति और स्तंभ शीर्षक रेंडर किए गए HTML में दृश्यमान हों।

### स्प्रेडशीट को JPG में प्रस्तुत करें
**अवलोकन:** पंक्ति और स्तंभ शीर्षकों को शामिल करते हुए एक्सेल शीट को उच्च गुणवत्ता वाली छवि फ़ाइलों (JPG) में परिवर्तित करें, जो दृश्य प्रस्तुतियों या प्रिंटआउट के लिए आदर्श है।

#### चरण-दर-चरण कार्यान्वयन:
##### 1. आवश्यक लाइब्रेरीज़ आयात करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```
##### 2. आउटपुट निर्देशिका सेट करें
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```
##### 3. व्यूअर आरंभ करें और विकल्प कॉन्फ़िगर करें
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // स्प्रेडशीट में पंक्ति और स्तंभ शीर्षकों का रेंडरिंग सक्षम करें.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // पृष्ठ 1 से 3 तक प्रस्तुत करें.
}
```
**स्पष्टीकरण:** `JpgViewOptions` छवि सेटिंग्स को संभालता है। `setRenderHeadings(true)` विकल्प यह सुनिश्चित करता है कि हेडर JPG आउटपुट में शामिल हों।

### स्प्रेडशीट को PNG में प्रस्तुत करें
**अवलोकन:** पंक्ति और स्तंभ शीर्षकों को बनाए रखते हुए एक्सेल शीट को PNG प्रारूप में परिवर्तित करें, जो उच्च गुणवत्ता वाली छवि आउटपुट के लिए उपयुक्त है।

#### चरण-दर-चरण कार्यान्वयन:
##### 1. आवश्यक लाइब्रेरीज़ आयात करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```
##### 2. आउटपुट निर्देशिका सेट करें
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
##### 3. व्यूअर आरंभ करें और विकल्प कॉन्फ़िगर करें
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // स्प्रेडशीट में पंक्ति और स्तंभ शीर्षकों का रेंडरिंग सक्षम करें.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // पृष्ठ 1 से 3 तक प्रस्तुत करें.
}
```
**स्पष्टीकरण:** `PngViewOptions` PNG सेटिंग्स के लिए उपयोग किया जाता है। `setRenderHeadings(true)`, हेडर आउटपुट छवियों में शामिल हैं।

### स्प्रेडशीट को पीडीएफ में प्रस्तुत करें
**अवलोकन:** एक्सेल शीट को पीडीएफ प्रारूप में रूपांतरित करें, साथ ही यह सुनिश्चित करें कि पंक्ति और स्तंभ शीर्षक दृश्यमान रहें, जो दस्तावेजों को संग्रहित करने या साझा करने के लिए एकदम उपयुक्त है।

#### चरण-दर-चरण कार्यान्वयन:
##### 1. आवश्यक लाइब्रेरीज़ आयात करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```
##### 2. आउटपुट निर्देशिका सेट करें
```java
Path outputDirectory = Paths.get("YOUR_DOCUMENT_DIRECTORY", "RenderRowAndColumnHeadings");
Path pageFilePathFormat = outputDirectory.resolve("output.pdf");
```
##### 3. व्यूअर आरंभ करें और विकल्प कॉन्फ़िगर करें
```java
try (Viewer viewer = new Viewer(Paths.get("Sample.xlsx"))) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    // स्प्रेडशीट में पंक्ति और स्तंभ शीर्षकों का रेंडरिंग सक्षम करें.
    options.getSpreadsheetOptions().setRenderHeadings(true);

    viewer.view(options, 1, 2, 3); // पृष्ठ 1 से 3 तक प्रस्तुत करें.
}
```
**स्पष्टीकरण:** `PdfViewOptions` पीडीएफ आउटपुट सेटिंग्स कॉन्फ़िगर करता है। `setRenderHeadings(true)` विकल्प यह सुनिश्चित करता है कि हेडर अंतिम पीडीएफ में दिखाई दें।

## व्यावहारिक अनुप्रयोगों
यहां कुछ वास्तविक परिदृश्य दिए गए हैं जहां इन सुविधाओं को लागू किया जा सकता है:

1. **व्यवसाय रिपोर्टिंग:** आसान प्रसार और देखने के लिए एक्सेल डेटा को HTML या PDF प्रारूप में परिवर्तित करके हितधारकों के साथ विस्तृत रिपोर्ट साझा करें।
2. **डेटा विज़ुअलाइज़ेशन:** प्रस्तुतियों के लिए स्प्रेडशीट को JPG या PNG जैसे छवि प्रारूपों में परिवर्तित करें, यह सुनिश्चित करते हुए कि हेडर दृश्यमान डेटा के लिए संदर्भ प्रदान करते हैं।
3. **दस्तावेज़ संग्रहण:** दस्तावेजों को सार्वभौमिक रूप से सुलभ प्रारूप में संग्रहित करने के लिए पीडीएफ रूपांतरण का उपयोग करें, जिसमें शीर्षकों जैसे सभी आवश्यक विवरण सुरक्षित रहें।