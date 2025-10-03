---
"date": "2025-04-24"
"description": "जानें कि कैसे आसानी से Outlook PST/OST फ़ाइलों को Java के लिए GroupDocs.Viewer का उपयोग करके HTML, JPG, PNG, या PDF जैसे सुलभ प्रारूपों में परिवर्तित किया जाए। यह मार्गदर्शिका सभी आवश्यक चरणों और कॉन्फ़िगरेशन को कवर करती है।"
"title": "Java के लिए GroupDocs.Viewer का उपयोग करके PST/OST को HTML, JPG, PNG, PDF में बदलें | निर्यात और रूपांतरण गाइड"
"url": "/hi/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/"
"weight": 1
type: docs
---
# Java के लिए GroupDocs.Viewer का उपयोग करके PST/OST को HTML, JPG, PNG, PDF में परिवर्तित करें

## परिचय

क्या आप अपनी Outlook PST या OST फ़ाइलों को HTML, JPG, PNG, या PDF जैसे अधिक सुलभ प्रारूपों में बदलना चाहते हैं? Java के लिए शक्तिशाली GroupDocs.Viewer लाइब्रेरी के साथ, यह कार्य सरल और कुशल है। यह ट्यूटोरियल आपको Java के लिए GroupDocs.Viewer का उपयोग करके PST/OST दस्तावेज़ों को रेंडर करने के बारे में मार्गदर्शन करता है, जिससे विभिन्न प्लेटफ़ॉर्म पर आसानी से साझा करना और देखना संभव हो जाता है।

**आप क्या सीखेंगे:**
- Java के लिए GroupDocs.Viewer के साथ अपना वातावरण कैसे सेट करें।
- PST/OST फ़ाइलों को HTML, JPG, PNG और PDF प्रारूपों में परिवर्तित करने के लिए चरण-दर-चरण निर्देश।
- आपके दस्तावेज़ रूपांतरण प्रक्रिया को अनुकूलित करने के लिए प्रमुख कॉन्फ़िगरेशन विकल्प।

आइये, आरंभ करने से पहले उन पूर्व-आवश्यकताओं की समीक्षा करें जिनकी आपको आवश्यकता है।

## आवश्यक शर्तें

इस ट्यूटोरियल का अनुसरण करने के लिए, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

### आवश्यक लाइब्रेरी और निर्भरताएँ
- **जावा के लिए GroupDocs.Viewer**आपको संस्करण 25.2 या बाद के संस्करण की आवश्यकता होगी.
- **जावा डेवलपमेंट किट (JDK)**आपके एप्लिकेशन को संकलित और चलाने के लिए JDK 8 या उच्चतर संस्करण की आवश्यकता है।

### पर्यावरण सेटअप आवश्यकताएँ
- एक संगत एकीकृत विकास वातावरण (IDE) जैसे कि IntelliJ IDEA, Eclipse, या NetBeans.
- निर्भरताओं के प्रबंधन के लिए आपके सिस्टम पर Maven स्थापित है।

### ज्ञान पूर्वापेक्षाएँ
- जावा प्रोग्रामिंग की बुनियादी समझ.
- निर्भरता प्रबंधन के लिए मावेन के उपयोग से परिचित होना।

पूर्वावश्यकताओं के साथ, चलिए Java के लिए GroupDocs.Viewer सेट अप करना शुरू करते हैं।

## Java के लिए GroupDocs.Viewer सेट अप करना

Java के लिए GroupDocs.Viewer का उपयोग करने के लिए, आपको इसे अपने प्रोजेक्ट में निर्भरता के रूप में जोड़ना होगा। यदि आप Maven का उपयोग कर रहे हैं, तो इन चरणों का पालन करें:

**मावेन कॉन्फ़िगरेशन:**

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
- **मुफ्त परीक्षण**आप सुविधाओं का पता लगाने के लिए निःशुल्क परीक्षण से शुरुआत कर सकते हैं।
- **अस्थायी लाइसेंस**यदि आपको मूल्यांकन के लिए अधिक समय चाहिए तो अस्थायी लाइसेंस के लिए आवेदन करें।
- **खरीदना**: दीर्घकालिक उपयोग के लिए लाइसेंस खरीदें।

### बुनियादी आरंभीकरण और सेटअप

एक बार जब आपका Maven कॉन्फ़िगरेशन पूरा हो जाए, तो अपने Java एप्लिकेशन में GroupDocs.Viewer को इनिशियलाइज़ करें:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // नमूना PST फ़ाइल पथ के साथ व्यूअर आरंभ करें
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

सेटअप पूरा होने के बाद, आइए रेंडरिंग सुविधाओं को लागू करने के लिए आगे बढ़ें।

## कार्यान्वयन मार्गदर्शिका

यह अनुभाग आपके PST/OST दस्तावेज़ों को जिस प्रारूप में प्रस्तुत करना चाहते हैं, उसके आधार पर तार्किक चरणों में विभाजित है: HTML, JPG, PNG, और PDF.

### PST/OST दस्तावेज़ों को HTML में प्रस्तुत करना

**अवलोकन:**
PST/OST फ़ाइलों को HTML में रेंडर करने से उन्हें वेब ब्राउज़र में आसानी से देखा जा सकता है। यह सुविधा संसाधनों को सीधे HTML फ़ाइल में एम्बेड करती है ताकि उन्हें आसानी से देखा जा सके।

#### चरण 1: आउटपुट निर्देशिका सेट करें

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

**स्पष्टीकरण**: निर्धारित करें कि आपकी HTML फ़ाइलें कहाँ सहेजी जाएँगी। `Paths` क्लास फ़ाइल पथों को कुशलतापूर्वक प्रबंधित करने में मदद करता है।

#### चरण 2: लोड विकल्प कॉन्फ़िगर करें

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**स्पष्टीकरण**: रेंडरिंग के दौरान देरी को रोकने के लिए संसाधन लोडिंग के लिए टाइमआउट सेट करें।

#### चरण 3: व्यूअर आरंभ करें और HTML रेंडर करें

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

**स्पष्टीकरण**: उपयोग `HtmlViewOptions` HTML फ़ाइल के भीतर संसाधनों को एम्बेड करने के लिए। `view()` विधि रेंडरिंग करती है।

### PST/OST दस्तावेज़ों को JPG में प्रस्तुत करना

**अवलोकन:**
आसानी से साझा करने और देखने के लिए अपनी PST/OST फ़ाइलों के प्रत्येक पृष्ठ को अलग-अलग JPG छवियों में परिवर्तित करें।

#### चरण 1: आउटपुट निर्देशिका सेट करें

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

**स्पष्टीकरण**: आउटपुट JPG फ़ाइलों के लिए निर्देशिका और फ़ाइल नाम पैटर्न निर्दिष्ट करें।

#### चरण 2: लोड विकल्प कॉन्फ़िगर करें

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**स्पष्टीकरण**: HTML रेंडरिंग के समान, संसाधन लोडिंग के लिए टाइमआउट सेट करें।

#### चरण 3: व्यूअर आरंभ करें और JPG रेंडर करें

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**स्पष्टीकरण**: उपयोग `JpgViewOptions` प्रत्येक पृष्ठ को एक अलग JPG फ़ाइल के रूप में प्रस्तुत करने के लिए।

### PST/OST दस्तावेज़ों को PNG में प्रस्तुत करना

**अवलोकन:**
अपनी PST/OST फ़ाइलों को PNG छवियों में परिवर्तित करें, जो उच्च गुणवत्ता वाली प्रस्तुतियों और प्रिंटआउट के लिए आदर्श हैं।

#### चरण 1: आउटपुट निर्देशिका सेट करें

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

**स्पष्टीकरण**: PNG फ़ाइलों के लिए निर्देशिका और फ़ाइल नाम पैटर्न परिभाषित करें।

#### चरण 2: लोड विकल्प कॉन्फ़िगर करें

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**स्पष्टीकरण**रेंडरिंग समय को कुशलतापूर्वक प्रबंधित करने के लिए संसाधन लोडिंग टाइमआउट सेट करें।

#### चरण 3: व्यूअर आरंभ करें और PNG रेंडर करें

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**स्पष्टीकरण**: उपयोग `PngViewOptions` प्रत्येक पृष्ठ को एक अलग PNG फ़ाइल के रूप में प्रस्तुत करने के लिए।

### पीएसटी/ओएसटी दस्तावेजों को पीडीएफ में प्रस्तुत करना

**अवलोकन:**
आसान वितरण और संग्रहण के लिए अपने संपूर्ण PST/OST दस्तावेज़ को एकल PDF फ़ाइल में परिवर्तित करें।

#### चरण 1: आउटपुट निर्देशिका सेट करें

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

**स्पष्टीकरण**: आउटपुट PDF फ़ाइल के लिए निर्देशिका और फ़ाइल नाम निर्दिष्ट करें।

#### चरण 2: लोड विकल्प कॉन्फ़िगर करें

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

**स्पष्टीकरण**: बिना किसी देरी के सुचारू रेंडरिंग सुनिश्चित करने के लिए टाइमआउट सेट करें।

#### चरण 3: व्यूअर आरंभ करें और पीडीएफ रेंडर करें

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

**स्पष्टीकरण**: उपयोग `PdfViewOptions` संपूर्ण दस्तावेज़ को एक एकल पीडीएफ फ़ाइल के रूप में प्रस्तुत करने के लिए।

## व्यावहारिक अनुप्रयोगों

यहां PST/OST दस्तावेज़ों को प्रस्तुत करने के लिए कुछ वास्तविक उपयोग के मामले दिए गए हैं:

1. **ईमेल संग्रहण:** आसान पहुंच और साझाकरण के लिए ईमेल अभिलेखों को HTML या PDF में परिवर्तित करें।
2. **दस्तावेज़ प्रबंधन प्रणालियाँ:** उन प्रणालियों के साथ एकीकृत करें जिनमें भंडारण और पुनर्प्राप्ति के लिए दस्तावेज़ रूपांतरण की आवश्यकता होती है।
3. **सहयोग उपकरण:** परिवर्तित दस्तावेज़ों को Slack या Microsoft Teams जैसे सहयोग टूल में साझा करें.
4. **कानूनी दस्तावेज:** कानूनी दस्तावेजों को सार्वभौमिक रूप से सुलभ प्रारूप में परिवर्तित करके उन्हें तैयार करें।
5. **बैकअप समाधान:** विभिन्न प्रारूपों में महत्वपूर्ण ईमेल और अनुलग्नकों का बैकअप बनाएं।

## प्रदर्शन संबंधी विचार

Java के लिए GroupDocs.Viewer का उपयोग करते समय प्रदर्शन को अनुकूलित करने के लिए, निम्नलिखित सुझावों पर विचार करें:
- रेंडरिंग के दौरान कुशल संसाधन प्रबंधन सुनिश्चित करें।
- मेमोरी उपयोग पर नज़र रखें और बाधाओं को रोकने के लिए आवश्यकतानुसार कॉन्फ़िगरेशन समायोजित करें।
- यदि आपकी अनुप्रयोग संदर्भ द्वारा समर्थित है तो प्रत्युत्तरशीलता में सुधार के लिए अतुल्यकालिक प्रसंस्करण का लाभ उठाएं।

इस गाइड का पालन करके, आप Java के लिए GroupDocs.Viewer का उपयोग करके PST/OST फ़ाइलों को विभिन्न प्रारूपों में कुशलतापूर्वक परिवर्तित कर सकते हैं, विभिन्न प्लेटफार्मों पर पहुंच और उपयोगिता को बढ़ा सकते हैं।