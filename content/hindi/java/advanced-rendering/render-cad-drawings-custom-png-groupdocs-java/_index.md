---
date: '2026-03-16'
description: GroupDocs.Viewer for Java का उपयोग करके कस्टम आकार और बैकग्राउंड रंग
  के साथ DWG को PNG में कैसे बदलें, सीखें।
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: GroupDocs.Viewer for Java का उपयोग करके कस्टम आकार और बैकग्राउंड रंग के साथ
  DWG को PNG में कैसे बदलें
type: docs
url: /hi/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

Check for any markdown links: none besides maybe none.

Now produce final content with translations.

Make sure to keep headings with same number of #.

Now produce final answer.# DWG को PNG में कस्टम साइज और बैकग्राउंड कलर के साथ GroupDocs.Viewer for Java का उपयोग करके कैसे कन्वर्ट करें

यदि आप **DWG को PNG में कन्वर्ट** करना चाहते हैं और इमेज डाइमेंशन और बैकग्राउंड स्टाइलिंग पर पूरी नियंत्रण रखना चाहते हैं, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम आपको CAD फ़ाइलों को PNG के रूप में रेंडर करने, चौड़ाई को कस्टमाइज़ करने, और बैकग्राउंड कलर बदलने के बारे में बताएँगे ताकि आउटपुट आपके रिपोर्ट, प्रेज़ेंटेशन या वेब‑प्रिव्यू आवश्यकताओं से मेल खाए।

## त्वरित उत्तर
- **DWG को PNG में कन्वर्ट** का क्या मतलब है? यह कोड का उपयोग करके DWG CAD फ़ाइल को PNG इमेज में बदलने की प्रक्रिया है।  
- **क्या मैं कस्टम चौड़ाई सेट कर सकता हूँ?** हाँ – `CadOptions.forRenderingByWidth(int width)` का उपयोग करें।  
- **बैकग्राउंड कलर कैसे बदलें?** `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` को कॉल करें।  
- **कौन सी लाइब्रेरी आवश्यक है?** GroupDocs.Viewer for Java (संस्करण 25.2 या बाद का)।  
- **क्या मुझे लाइसेंस चाहिए?** एक टेम्पररी या खरीदा गया लाइसेंस इवैल्यूएशन लिमिट्स को हटा देता है।  

![कस्टम साइज और बैकग्राउंड कलर के साथ GroupDocs.Viewer for Java का उपयोग करके CAD ड्रॉइंग्स को PNG में रेंडर करें](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## DWG को PNG में कन्वर्ट करने का अवलोकन
इस सेक्शन में हम मुख्य लक्ष्य पर विस्तार करेंगे: **DWG को PNG में कैसे कन्वर्ट करें** जबकि साइज और बैकग्राउंड को नियंत्रित किया जाए। आप पूरी सेटअप, आवश्यक कोड, और सामान्य समस्याओं से बचने के लिए व्यावहारिक टिप्स देखेंगे।

## आप क्या सीखेंगे
- Maven प्रोजेक्ट में GroupDocs.Viewer for Java को सेट अप करना  
- **कस्टम डाइमेंशन के साथ DWG को PNG में कन्वर्ट** करना  
- रेंडरिंग के दौरान **CAD बैकग्राउंड कलर बदलना** ताकि पॉलिश्ड लुक मिले  
- वास्तविक दुनिया के परिदृश्य जहाँ कस्टम रेंडरिंग मूल्य जोड़ती है  

## पूर्वापेक्षाएँ

### आवश्यक लाइब्रेरीज़ और डिपेंडेंसीज़
- Java Development Kit (JDK) 8+  
- डिपेंडेंसी मैनेजमेंट के लिए Maven  

### पर्यावरण सेटअप आवश्यकताएँ
- IntelliJ IDEA या Eclipse जैसे IDE  
- बेसिक Java ज्ञान  

### ज्ञान पूर्वापेक्षाएँ
- Java में फाइलों को हैंडल करने की परिचितता  

## GroupDocs.Viewer for Java सेट अप करना
अपने Maven `pom.xml` में GroupDocs रिपॉजिटरी और डिपेंडेंसी जोड़ें:

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

### लाइसेंस प्राप्ति
इवैल्यूएशन प्रतिबंधों को हटाने के लिए एक टेम्पररी या फुल लाइसेंस प्राप्त करें।

### बेसिक इनिशियलाइज़ेशन और सेटअप
एक `Viewer` इंस्टेंस बनाएं जो आपके CAD फ़ाइल की ओर इशारा करता हो:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## फीचर 1: कस्टम इमेज साइज और बैकग्राउंड कलर के साथ CAD ड्रॉइंग्स को रेंडर करना

### CAD बैकग्राउंड कलर कैसे बदलें
यह फीचर आपको **DWG को PNG में कन्वर्ट** करने देता है जबकि कस्टम चौड़ाई निर्दिष्ट करते हैं और नया बैकग्राउंड ह्यू लागू करते हैं।

#### चरण‑दर‑चरण कार्यान्वयन

##### आवश्यक पैकेज इम्पोर्ट करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### आउटपुट डायरेक्टरी और फ़ाइल पाथ फ़ॉर्मेट सेट करें
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### कस्टम रेंडरिंग ऑप्शन्स के साथ Viewer इनिशियलाइज़ करें
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**पैरामीटर्स की व्याख्या**  
- `PngViewOptions` – आउटपुट फ़ॉर्मेट और नामकरण को परिभाषित करता है।  
- `forRenderingByWidth(int width)` – कस्टम इमेज चौड़ाई सेट करता है।  
- `setBackgroundColor(Color color)` – **PNG बैकग्राउंड कलर सेट** करता है ताकि विज़ुअल कंसिस्टेंसी बेहतर हो।  

#### ट्रबलशूटिंग टिप्स
- आउटपुट फ़ोल्डर मौजूद है या नहीं, जांचें; यदि आवश्यक हो तो बनाएं।  
- इनपुट फ़ाइल पाथ और परमिशन को दोबारा जांचें।  

## फीचर 2: रेंडरिंग ऑप्शन्स में बैकग्राउंड कलर सेट करना

### PNG बैकग्राउंड कलर कैसे सेट करें
यहाँ हम **set background color PNG** विकल्प पर ध्यान देंगे ताकि हर रेंडर की गई इमेज आपके ब्रांड पैलेट से मेल खाए।

#### चरण‑दर‑चरण कार्यान्वयन

##### आवश्यक पैकेज इम्पोर्ट करें
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### बैकग्राउंड कलर के साथ रेंडरिंग ऑप्शन्स कॉन्फ़िगर करें
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**मुख्य कॉन्फ़िगरेशन विकल्प**  
- विभिन्न डाइमेंशन्स के लिए `forRenderingByWidth(int width)` को एडजस्ट करें।  
- किसी भी `Color` कॉन्स्टेंट या कस्टम `new Color(r,g,b)` का उपयोग करके विशेष बैकग्राउंड बनाएं।  

## व्यावहारिक अनुप्रयोग

### 1. इंजीनियरिंग दस्तावेज़ीकरण
कस्टम रेंडरिंग यह सुनिश्चित करती है कि इंजीनियरिंग ड्रॉइंग्स कॉरपोरेट स्टाइल गाइड्स को पूरा करें।

### 2. आर्किटेक्चरल विज़ुअलाइज़ेशन
ब्लूप्रिंट्स को साफ़ बैकग्राउंड के साथ प्रस्तुत करें जो प्रेज़ेंटेशन डेक्स से मेल खाता हो।

### 3. मैन्युफैक्चरिंग प्रोटोटाइपिंग
रैपिड प्रोटोटाइपिंग वर्कफ़्लोज़ के लिए सटीक PNG बनाएं।

### इंटीग्रेशन संभावनाएँ
इस रेंडरिंग पाइपलाइन को डॉक्यूमेंट मैनेजमेंट सिस्टम्स के साथ संयोजित करके विज़ुअल एसेट जेनरेशन को ऑटोमेट करें।

## प्रदर्शन संबंधी विचार

### प्रदर्शन को ऑप्टिमाइज़ करना
- **बैच प्रोसेसिंग:** लूप में कई CAD फ़ाइलों को रेंडर करें।  
- **रिसोर्स मैनेजमेंट:** बड़े ड्रॉइंग्स के लिए JVM हीप साइज ट्यून करें।

### रिसोर्स उपयोग दिशानिर्देश
CPU और मेमोरी की निगरानी करें; `Viewer` इंस्टेंस को तुरंत रिलीज़ करें।

### Java मेमोरी मैनेजमेंट के बेस्ट प्रैक्टिसेज
- `Viewer` को ऑटो‑क्लोज़ करने के लिए try‑with‑resources (जैसा दिखाया गया) का उपयोग करें।  
- ज़रूरत से अधिक बड़े `Path` ऑब्जेक्ट्स को रखे रखने से बचें।

## सामान्य समस्याएँ और समाधान

| समस्या | समाधान |
|-------|----------|
| **आउटपुट फ़ोल्डर नहीं मिला** | डायरेक्टरी पहले से बनाएं या `Files.createDirectories(outputDirectory);` जोड़ें |
| **ब्लैंक इमेज** | सुनिश्चित करें कि `cadOptions.setBackgroundColor` को `forRenderingByWidth` के बाद सेट किया गया है। |
| **आउट‑ऑफ़‑मेमोरी त्रुटियाँ** | `-Xmx` JVM विकल्प बढ़ाएँ या फ़ाइलों को छोटे बैच में प्रोसेस करें। |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं DWG के अलावा अन्य CAD फ़ॉर्मेट रेंडर कर सकता हूँ?**  
**उत्तर:** हाँ, GroupDocs.Viewer DXF, DWF और कई अन्य CAD फ़ाइल प्रकारों को सपोर्ट करता है।

**प्रश्न: प्री‑डिफाइंड कॉन्स्टेंट की बजाय कस्टम RGB कलर कैसे उपयोग करें?**  
**उत्तर:** एक नया `Color` इंस्टेंस बनाएं, जैसे `new Color(123, 45, 67)` और इसे `setBackgroundColor` में पास करें।

**प्रश्न: क्या केवल एक विशिष्ट लेआउट या लेयर को रेंडर करना संभव है?**  
**उत्तर:** आप `viewer.view` कॉल करने से पहले `CadOptions` के माध्यम से लेआउट या लेयर विकल्प निर्दिष्ट कर सकते हैं।

**प्रश्न: क्या लाइब्रेरी ट्रांसपेरेंट बैकग्राउंड सपोर्ट करती है?**  
**उत्तर:** यदि टार्गेट फ़ॉर्मेट सपोर्ट करता है, तो पूर्ण ट्रांसपेरेंसी के लिए बैकग्राउंड कलर को `new Color(0,0,0,0)` सेट करें।

**प्रश्न: GroupDocs.Viewer का कौन सा संस्करण आवश्यक है?**  
**उत्तर:** इस ट्यूटोरियल में संस्करण 25.2 उपयोग किया गया है, लेकिन नए संस्करण भी वही API रखते हैं।

---

**अंतिम अपडेट:** 2026-03-16  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs