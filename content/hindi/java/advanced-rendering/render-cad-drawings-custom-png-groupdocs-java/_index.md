---
date: '2026-01-08'
description: GroupDocs.Viewer for Java का उपयोग करके कस्टम आयामों और बैकग्राउंड रंगों
  के साथ CAD ड्रॉइंग्स को उच्च‑गुणवत्ता वाले PNG इमेज में रेंडर करना सीखें।
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: GroupDocs.Viewer for Java का उपयोग करके कस्टम आकार और पृष्ठभूमि रंग के साथ
  CAD ड्रॉइंग्स को PNG में रेंडर कैसे करें
type: docs
url: /hi/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# CAD ड्रॉइंग्स को कस्टम साइज और बैकग्राउंड कलर के साथ PNG में रेंडर कैसे करें GroupDocs.Viewer for Java का उपयोग करके

क्या आप अपने CAD ड्रॉइंग्स को विशिष्ट आयामों और सौंदर्यशास्त्र को बनाए रखते हुए हाई‑क्वालिटी इमेज में बदलने में कठिनाई महसूस कर रहे हैं? इस ट्यूटोरियल में हम **how to render CAD** फ़ाइलों को कस्टम साइज और बैकग्राउंड कलर के साथ PNG में रेंडर करना दिखाएंगे, ताकि आप रिपोर्ट, प्रेजेंटेशन या वेब प्रीव्यू के लिए बिल्कुल वही लुक प्राप्त कर सकें।

## त्वरित उत्तर
- **“how to render CAD” का क्या मतलब है?** यह CAD फ़ाइलों (जैसे DWG) को कोड का उपयोग करके PNG जैसे इमेज फ़ॉर्मेट में बदलने को दर्शाता है।  
- **क्या मैं कस्टम चौड़ाई सेट कर सकता हूँ?** हाँ – `CadOptions.forRenderingByWidth(int width)` का उपयोग करें।  
- **बैकग्राउंड कैसे बदलें?** `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` को कॉल करें।  
- **कौन सी लाइब्रेरी आवश्यक है?** GroupDocs.Viewer for Java (संस्करण 25.2 या बाद का)।  
- **क्या लाइसेंस चाहिए?** एक टेम्पररी या खरीदा गया लाइसेंस मूल्यांकन सीमाओं को हटा देता है।

![CAD ड्रॉइंग्स को कस्टम साइज और बैकग्राउंड कलर के साथ PNG में रेंडर करना GroupDocs.Viewer for Java के साथ](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## CAD ड्रॉइंग्स को रेंडर करने का अवलोकन
यह सेक्शन मुख्य लक्ष्य को विस्तारित करता है: **how to render CAD** ड्रॉइंग्स को PNG फ़ाइलों में बदलना जबकि साइज और बैकग्राउंड को नियंत्रित किया जाए। हम पूरी सेटअप, कोड स्निपेट्स और व्यावहारिक टिप्स को चरण‑बद्ध दिखाएंगे।

## आप क्या सीखेंगे
- अपने प्रोजेक्ट में GroupDocs.Viewer for Java सेटअप करना  
- कस्टम डाइमेंशन के साथ **Convert DWG to PNG**  
- रेंडरिंग के दौरान **Set background color PNG** लागू करके पॉलिश्ड लुक प्राप्त करना  
- वास्तविक‑दुनिया के परिदृश्य जहाँ कस्टम रेंडरिंग मूल्य जोड़ती है  

## पूर्वापेक्षाएँ

### आवश्यक लाइब्रेरी और डिपेंडेंसीज़
- Java Development Kit (JDK) 8+  
- डिपेंडेंसी मैनेजमेंट के लिए Maven  

### पर्यावरण सेटअप आवश्यकताएँ
- IntelliJ IDEA या Eclipse जैसे IDE  
- बेसिक Java ज्ञान  

### ज्ञान की पूर्वापेक्षाएँ
- Java में फ़ाइलों को हैंडल करने की परिचितता  

## GroupDocs.Viewer for Java सेटअप करना
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

### लाइसेंस प्राप्त करना
मूल्यांकन प्रतिबंधों को हटाने के लिए एक टेम्पररी या फुल लाइसेंस प्राप्त करें।

### बेसिक इनिशियलाइज़ेशन और सेटअप
एक `Viewer` इंस्टेंस बनाएं जो आपके CAD फ़ाइल की ओर इशारा करे:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## इम्प्लीमेंटेशन गाइड

### फीचर 1: कस्टम इमेज साइज और बैकग्राउंड कलर के साथ CAD ड्रॉइंग्स रेंडर करना

#### अवलोकन
यह फीचर आपको **convert DWG to PNG** करने की अनुमति देता है जबकि इमेज चौड़ाई और बैकग्राउंड ह्यू निर्दिष्ट किया जाता है।

#### चरण‑बद्ध इम्प्लीमेंटेशन

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

**पैरामीटर की व्याख्या**  
- `PngViewOptions` – आउटपुट फ़ॉर्मेट और नेमिंग को परिभाषित करता है।  
- `forRenderingByWidth(int width)` – कस्टम इमेज चौड़ाई सेट करता है।  
- `setBackgroundColor(Color color)` – **apply background color rendering** को PNG पर लागू करता है।

#### ट्रबलशूटिंग टिप्स
- आउटपुट फ़ोल्डर मौजूद है या नहीं, जांचें; यदि नहीं है तो बनाएं।  
- इनपुट फ़ाइल पाथ और परमिशन को दोबारा चेक करें।  

### फीचर 2: रेंडरिंग ऑप्शन्स में बैकग्राउंड कलर सेट करना

#### अवलोकन
यहाँ हम **set background color PNG** पर फोकस करेंगे ताकि विज़ुअल कंसिस्टेंसी बेहतर हो।

#### चरण‑बद्ध इम्प्लीमेंटेशन

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

**मुख्य कॉन्फ़िगरेशन ऑप्शन्स**  
- विभिन्न डाइमेंशन के लिए `forRenderingByWidth(int width)` को एडजस्ट करें।  
- किसी भी `Color` कॉन्स्टेंट या कस्टम `new Color(r,g,b)` का उपयोग करके कस्टम बैकग्राउंड बनाएं।  

## व्यावहारिक अनुप्रयोग

### 1. इंजीनियरिंग डॉक्यूमेंटेशन
कस्टम रेंडरिंग सुनिश्चित करता है कि इंजीनियरिंग ड्रॉइंग्स कॉरपोरेट स्टाइल गाइड्स को पूरा करें।

### 2. आर्किटेक्चरल विज़ुअलाइज़ेशन
ब्लूप्रिंट्स को साफ़ बैकग्राउंड के साथ प्रस्तुत करें जो प्रेजेंटेशन डेक्स से मेल खाता हो।

### 3. मैन्युफैक्चरिंग प्रोटोटाइपिंग
रैपिड प्रोटोटाइपिंग वर्कफ़्लोज़ के लिए सटीक PNG जेनरेट करें।

### इंटीग्रेशन संभावनाएँ
इस रेंडरिंग पाइपलाइन को डॉक्यूमेंट मैनेजमेंट सिस्टम्स के साथ जोड़ें ताकि विज़ुअल एसेट जेनरेशन ऑटोमेट हो सके।

## प्रदर्शन संबंधी विचार

### प्रदर्शन को ऑप्टिमाइज़ करना
- **बैच प्रोसेसिंग:** लूप में कई CAD फ़ाइलें रेंडर करें।  
- **रिसोर्स मैनेजमेंट:** बड़े ड्रॉइंग्स के लिए JVM हीप साइज ट्यून करें।

### रिसोर्स उपयोग दिशानिर्देश
CPU और मेमोरी की निगरानी रखें; `Viewer` इंस्टेंस को तुरंत रिलीज़ करें।

### Java मेमोरी मैनेजमेंट के लिए बेस्ट प्रैक्टिसेज
- जैसा दिखाया गया है, `try‑with‑resources` का उपयोग करके `Viewer` को ऑटो‑क्लोज़ करें।  
- बड़े `Path` ऑब्जेक्ट्स को आवश्यक से अधिक समय तक न रखें।

## सामान्य समस्याएँ और समाधान
| समस्या | समाधान |
|-------|----------|
| **Output folder not found** | पहले से डायरेक्टरी बनाएं या `Files.createDirectories(outputDirectory);` जोड़ें |
| **Blank image** | सुनिश्चित करें कि `cadOptions.setBackgroundColor` को `forRenderingByWidth` के बाद सेट किया गया है। |
| **Out‑of‑memory errors** | `-Xmx` JVM ऑप्शन बढ़ाएँ या फ़ाइलों को छोटे बैच में प्रोसेस करें। |

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं DWG के अलावा अन्य CAD फ़ॉर्मेट रेंडर कर सकता हूँ?**  
A: हाँ, GroupDocs.Viewer DXF, DWF और कई अन्य CAD फ़ाइल टाइप्स को सपोर्ट करता है।

**Q: प्री-डिफाइंड कॉन्स्टेंट की बजाय कस्टम RGB कलर कैसे उपयोग करूँ?**  
A: नया `Color` इंस्टेंस बनाएं, उदाहरण के लिए `new Color(123, 45, 67)` और इसे `setBackgroundColor` में पास करें।

**Q: क्या केवल एक विशिष्ट लेआउट या लेयर रेंडर करना संभव है?**  
A: `viewer.view` कॉल करने से पहले `CadOptions` में लेआउट या लेयर ऑप्शन सेट कर सकते हैं।

**Q: क्या लाइब्रेरी ट्रांसपेरेंट बैकग्राउंड सपोर्ट करती है?**  
A: यदि टार्गेट फ़ॉर्मेट सपोर्ट करता है तो `new Color(0,0,0,0)` सेट करके पूरी ट्रांसपेरेंसी प्राप्त करें।

**Q: GroupDocs.Viewer का कौन सा संस्करण आवश्यक है?**  
A: ट्यूटोरियल संस्करण 25.2 का उपयोग करता है, लेकिन नए संस्करणों में वही API रहता है।

## निष्कर्ष
अब आप **how to render CAD** ड्रॉइंग्स को कस्टम डाइमेंशन और बैकग्राउंड कलर के साथ PNG फ़ाइलों में बदलना जानते हैं, GroupDocs.Viewer for Java का उपयोग करके। इन तकनीकों को लागू करके आप इंजीनियरिंग, आर्किटेक्चर या मैन्युफैक्चरिंग वर्कफ़्लोज़ के लिए प्रोफेशनल‑लुकिंग विज़ुअल एसेट बना सकते हैं।

### अगले कदम
- विभिन्न इमेज चौड़ाइयों और रंगों के साथ प्रयोग करें।  
- रेंडरिंग कोड को बैच प्रोसेसिंग सर्विस में इंटीग्रेट करें।  
- अतिरिक्त Viewer ऑप्शन्स जैसे PDF कन्वर्ज़न या मल्टी‑पेज रेंडरिंग को एक्सप्लोर करें।

---

**Last Updated:** 2026-01-08  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

---