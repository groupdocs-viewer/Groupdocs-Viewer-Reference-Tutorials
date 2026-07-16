---
date: '2026-03-24'
description: GroupDocs Viewer for Java का उपयोग करके ईमेल को HTML में बदलना और ईमेल
  फ़ील्ड्स का नाम बदलना सीखें। यह गाइड कस्टम हेडर्स के साथ ईमेल को HTML में रेंडर
  करना दर्शाता है।
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: ईमेल को HTML में बदलें और फ़ील्ड्स का नाम बदलें – GroupDocs Viewer Java
type: docs
url: /hi/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# ईमेल को HTML में बदलें और फ़ील्ड्स का नाम बदलें – GroupDocs Viewer Java

यदि आपको **ईमेल को HTML में बदलना** है और ईमेल हेडर को कस्टम लुक देना है, तो आप सही जगह पर हैं। इस ट्यूटोरियल में हम ईमेल फ़ील्ड्स का नाम बदलने, **ईमेल को HTML में बदलने**, और GroupDocs.Viewer for Java का उपयोग करके ईमेल हेडर को कस्टमाइज़ करने के सटीक चरणों को देखेंगे। अंत में आपके पास एक साफ़ HTML प्रतिनिधित्व होगा जिसमें आप पसंदीदा हेडर नाम होंगे, जिससे आउटपुट पढ़ने और आपके एप्लिकेशन में इंटीग्रेट करने में आसानी होगी।

![HTML में ईमेल परिवर्तित करते समय ईमेल फ़ील्ड्स का नाम बदलें – GroupDocs.Viewer for Java के साथ](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### आप क्या सीखेंगे
- GroupDocs.Viewer for Java का उपयोग करके **ईमेल को HTML में बदलना**।  
- “From”, “To”, “Sent”, और “Subject” जैसे **ईमेल फ़ील्ड्स का नाम बदलने** की तकनीकें।  
- Maven और लाइसेंसिंग सेटअप के लिए सर्वोत्तम प्रथाएँ।  
- वास्तविक परिदृश्य जहाँ **ईमेल हेडर को कस्टमाइज़** करने से मूल्य जुड़ता है।

## त्वरित उत्तर
- **“ईमेल को HTML में बदलना” का क्या अर्थ है?** इसका मतलब है ईमेल फ़ाइल (MSG/EML) को वेब‑तैयार HTML दस्तावेज़ के रूप में रेंडर करना।  
- **कौन सी लाइब्रेरी परिवर्तन संभालती है?** GroupDocs.Viewer for Java (v25.2+)।  
- **क्या मुझे लाइसेंस चाहिए?** मूल्यांकन के लिए ट्रायल काम करता है; उत्पादन के लिए पूर्ण लाइसेंस आवश्यक है।  
- **क्या मैं किसी भी हेडर का नाम बदल सकता हूँ?** हाँ, किसी भी मानक ईमेल हेडर को `fieldTextMap` के माध्यम से पुनः मैप किया जा सकता है।  
- **क्या आउटपुट HTML है या एम्बेडेड रिसोर्सेज?** आप एकल स्व-समाहित फ़ाइल के लिए एम्बेडेड रिसोर्सेज चुन सकते हैं।

## GroupDocs.Viewer के संदर्भ में “ईमेल को HTML में बदलना” क्या है?
ईमेल को HTML में बदलना का अर्थ है कच्ची ईमेल फ़ाइल को लेकर एक HTML पेज बनाना जो संदेश बॉडी के साथ उसके मेटाडेटा को भी दिखाता है। जब आप **ईमेल फ़ील्ड्स का नाम बदलते** हैं, तो डिफ़ॉल्ट लेबल (जैसे “From”) को कस्टम टेक्स्ट (जैसे “Sender”) से बदल दिया जाता है, जिससे आप कॉरपोरेट शब्दावली से मेल कर सकते हैं या UI संगतता सुधार सकते हैं।

## क्यों ईमेल को HTML में बदलें और ईमेल फ़ील्ड्स का नाम बदलें?
- **सुसंगत ब्रांडिंग:** आउटपुट को आपके संगठन की भाषा के साथ संरेखित करें।  
- **बेहतर खोजयोग्यता:** कस्टम हेडर को आर्काइविंग सिस्टम में अधिक प्रभावी ढंग से इंडेक्स किया जा सकता है।  
- **बेहतर UI इंटीग्रेशन:** HTML स्निपेट को वेब पोर्टल या सपोर्ट डैशबोर्ड में सहजता से फिट करने के लिए टेलर करें।

## पूर्वापेक्षाएँ

### आवश्यक लाइब्रेरी, संस्करण, और निर्भरताएँ
- **GroupDocs.Viewer for Java** – संस्करण 25.2 या बाद का।  
- **Java Development Kit (JDK)** – संस्करण 8+।

### पर्यावरण सेटअप आवश्यकताएँ
- **Maven** निर्भरता प्रबंधन के लिए।  
- IntelliJ IDEA, Eclipse, या VS Code जैसे IDE।

### ज्ञान पूर्वापेक्षाएँ
बुनियादी Java और Maven की समझ आपको जल्दी से ट्यूटोरियल फॉलो करने में मदद करेगी।

## GroupDocs.Viewer for Java सेटअप करना

### Maven कॉन्फ़िगरेशन
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

### लाइसेंस प्राप्त करने के चरण
- **नि:शुल्क परीक्षण:** [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) से नि:शुल्क परीक्षण डाउनलोड करें।  
- **अस्थायी लाइसेंस:** सीमाओं के बिना पूरी सुविधाओं का अन्वेषण करने के लिए [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) से अस्थायी लाइसेंस प्राप्त करें।  
- **खरीद:** निरंतर उपयोग के लिए [GroupDocs Purchase](https://purchase.groupdocs.com/buy) के माध्यम से लाइसेंस खरीदने पर विचार करें।

### बुनियादी इनिशियलाइज़ेशन और सेटअप
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
फ़ाइल पाथ को अपने `.msg` फ़ाइल की ओर इंगित करने के लिए समायोजित करें।

## ईमेल को HTML में बदलने और फ़ील्ड्स का नाम बदलने के चरण‑दर‑चरण

### 1. आउटपुट डायरेक्टरी पाथ सेट करें
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*`"YOUR_OUTPUT_DIRECTORY"` को उस फ़ोल्डर से बदलें जहाँ आप HTML फ़ाइलें सहेजना चाहते हैं।*

### 2. पेज फ़ाइल पाथ फ़ॉर्मेट निर्धारित करें
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*रेंडरिंग के दौरान `{0}` पेज नंबर से बदल दिया जाएगा।*

### 3. ईमेल फ़ील्ड्स को नए नामों से मैप करें
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*यहाँ हम डिफ़ॉल्ट लेबल को कस्टम लेबल में बदलते हैं।*

### 4. HTML व्यू विकल्प कॉन्फ़िगर करें
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` CSS/JS को HTML के अंदर बंडल करता है, जबकि `setFieldTextMap` कस्टम हेडर नाम लागू करता है।*

### 5. ईमेल को HTML में रेंडर करें
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*`"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` को अपने MSG फ़ाइल के वास्तविक पाथ से बदलें।*

#### समस्या निवारण टिप्स
- आउटपुट डायरेक्टरी लिखने योग्य है या नहीं, जाँचें।  
- इनपुट MSG फ़ाइल मौजूद है और पाथ सही है, यह सुनिश्चित करें।  
- Maven में घोषित संस्करण (25.2) के समान GroupDocs.Viewer संस्करण उपयोग करें।

## व्यावहारिक अनुप्रयोग
1. **कस्टम ईमेल रिपोर्ट्स:** स्पष्ट रिपोर्ट्स के लिए ईमेल हेडर को कॉरपोरेट शब्दावली के साथ संरेखित करें।  
2. **ईमेल आर्काइविंग सिस्टम:** मानकीकृत हेडर नामों का उपयोग करके खोजयोग्यता में सुधार करें।  
3. **ग्राहक समर्थन प्लेटफ़ॉर्म:** बेहतर एजेंट अनुभव के लिए व्यक्तिगत हेडर लेबल के साथ टिकट प्रस्तुत करें।

## प्रदर्शन विचार
- मेमोरी को तुरंत मुक्त करने के लिए `Viewer` ऑब्जेक्ट को try‑with‑resources के साथ डिस्पोज़ करें।  
- बड़े बैच प्रोफ़ाइल करें और आवश्यक होने पर ईमेल को समानांतर स्ट्रीम्स में प्रोसेस करने पर विचार करें।

## निष्कर्ष
अब आप **ईमेल को HTML में बदलना** और **ईमेल फ़ील्ड्स का नाम बदलना** तथा GroupDocs.Viewer for Java के साथ **ईमेल हेडर को कस्टमाइज़ करना** जानते हैं। यह तकनीक आपको HTML आउटपुट में ईमेल मेटाडेटा की प्रस्तुति पर पूर्ण नियंत्रण देती है।

### अगले कदम
- अतिरिक्त फ़ील्ड मैपिंग (जैसे CC, BCC) के साथ प्रयोग करें।  
- PDF या PNG जैसे अन्य रेंडरिंग फ़ॉर्मेट्स का अन्वेषण करें।  
- गहरी API अंतर्दृष्टि के लिए [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) देखें।

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या यह तरीका EML जैसे अन्य ईमेल फ़ॉर्मेट्स के साथ काम करता है?**  
उत्तर: हाँ, GroupDocs.Viewer MSG और EML दोनों फ़ाइलों को सपोर्ट करता है; वही फ़ील्ड‑मैपिंग लॉजिक लागू होता है।

**प्रश्न: क्या मैं एम्बेडेड रिसोर्सेज के बिना HTML आउटपुट कर सकता हूँ?**  
उत्तर: यदि आप अलग‑अलग CSS/JS फ़ाइलें पसंद करते हैं तो `HtmlViewOptions.forExternalResources(...)` का उपयोग कर सकते हैं।

**प्रश्न: किस संस्करण के GroupDocs.Viewer का परीक्षण किया गया था?**  
उत्तर: कोड को GroupDocs.Viewer **25.2** के साथ परीक्षण किया गया था।

**प्रश्न: क्या कस्टम हेडर के फ़ॉन्ट या स्टाइल बदलना संभव है?**  
उत्तर: रेंडरिंग के बाद CSS के माध्यम से स्टाइल लागू किया जा सकता है, या आप `HtmlViewOptions.getResourcesPath()` का उपयोग करके कस्टम CSS इंजेक्ट कर सकते हैं।

**प्रश्न: उत्पन्न HTML फ़ाइल पाथ को प्रोग्रामेटिकली कैसे प्राप्त करें?**  
उत्तर: फ़ाइल पाथ `pageFilePathFormat` में परिभाषित पैटर्न का अनुसरण करता है; आप पेज नंबर के साथ `String.format` का उपयोग करके इसे बना सकते हैं।

## संसाधन
- **डॉक्यूमेंटेशन:** विस्तृत गाइड्स [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) पर उपलब्ध हैं।  
- **API रेफ़रेंस:** विस्तृत API जानकारी [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/) पर मिल सकती है।  
- **GroupDocs.Viewer डाउनलोड करें:** नवीनतम संस्करण [Downloads Page](https://releases.groupdocs.com/viewer/java/) से एक्सेस करें।

---

**अंतिम अपडेट:** 2026-03-24  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2  
**लेखक:** GroupDocs