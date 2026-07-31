---
date: '2026-04-01'
description: GroupDocs Viewer for Java का उपयोग करके CAD ड्रॉइंग्स को टाइल्स में विभाजित
  करना सीखें, जिससे रेंडरिंग प्रदर्शन में सुधार हो और बड़े फ़ाइलों को संभालना सरल
  हो जाए।
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: GroupDocs Viewer के साथ CAD ड्रॉइंग्स को टाइल्स में कैसे विभाजित करें
type: docs
url: /hi/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# CAD ड्रॉइंग्स को टाइल्स में विभाजित करने के लिए GroupDocs Viewer के साथ कैसे करें

यदि आप सोच रहे हैं **how to split CAD** फ़ाइलों को छोटे, अधिक प्रबंधनीय टुकड़ों में विभाजित करने के बारे में, तो आप सही जगह पर आए हैं। इस ट्यूटोरियल में हम बड़े CAD ड्रॉइंग्स को टाइल्स में विभाजित करने के लिए आवश्यक सटीक चरणों को **GroupDocs Viewer for Java** का उपयोग करके दिखाएंगे। अंत तक आपके पास एक तैयार‑उपयोग समाधान होगा जो रेंडरिंग गति को सुधारता है, मेमोरी खपत को कम करता है, और वेब या मोबाइल एप्लिकेशन में ड्रॉइंग्स को प्रदर्शित करना आसान बनाता है।

![GroupDocs.Viewer for Java के साथ CAD ड्रॉइंग्स को विभाजित करें](/viewer/advanced-rendering/split-cad-drawings-java.png)

## त्वरित उत्तर
- **“splitting CAD” क्या हासिल करता है?** यह एक बड़े ड्रॉइंग को छोटे इमेज (टाइल्स) में विभाजित करता है जो तेज़ लोड होते हैं और कम मेमोरी खपत करते हैं।  
- **टाइल्स के लिए कौन सा फ़ॉर्मेट उपयोग किया जाता है?** डिफ़ॉल्ट रूप से PNG फ़ाइलें उत्पन्न होती हैं, लेकिन अन्य फ़ॉर्मेट Viewer विकल्पों के माध्यम से समर्थित हैं।  
- **क्या मुझे लाइसेंस की आवश्यकता है?** विकास के लिए एक मुफ्त ट्रायल काम करता है; उत्पादन के लिए एक पेड लाइसेंस आवश्यक है।  
- **क्या मैं टाइल आकार बदल सकता हूँ?** हाँ – अपनी आवश्यकता के अनुसार `tileWidth` और `tileHeight` गणनाओं को समायोजित करें।  
- **क्या यह तरीका थ्रेड‑सेफ़ है?** प्रत्येक टाइल को अपने स्वयं के `Viewer` इंस्टेंस में try‑with‑resources के साथ रेंडर करना समवर्ती निष्पादन के लिए सुरक्षित है।

## “how to split CAD” क्या है?
Splitting CAD का अर्थ है एक एकल, अक्सर बहुत बड़ा, CAD ड्रॉइंग को कई आयताकार सेक्शन (टाइल्स) में विभाजित करना। प्रत्येक टाइल स्वतंत्र रूप से रेंडर होती है, जिससे आप केवल वही भाग लोड कर सकते हैं जो उपयोगकर्ता को वास्तव में चाहिए—वेब मैप्स, दस्तावेज़ पोर्टल, और मोबाइल व्यूअर्स के लिए उपयुक्त।

## GroupDocs Viewer for Java का उपयोग क्यों करें?
GroupDocs Viewer 100 से अधिक फ़ाइल फ़ॉर्मेट्स के लिए बॉक्स से ही समर्थन प्रदान करता है, जिसमें DWG, DXF, और DWF शामिल हैं। इसका टाइल API आपको सटीक निर्देशांक निर्दिष्ट करने देता है, ताकि आप पूरी फ़ाइल को पहले प्रोसेस किए बिना वही क्षेत्र रेंडर कर सकें जिसकी आपको आवश्यकता है। यह CPU साइकिल बचाता है, बैंडविड्थ कम करता है, और एक सुगम उपयोगकर्ता अनुभव प्रदान करता है।

## आवश्यकताएँ
- **लाइब्रेरीज़**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: कोई भी नवीनतम Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse, या कोई अन्य Java‑संगत IDE।  
- **बिल्ड टूल**: Maven (अन्य बिल्ड टूल्स भी काम करेंगे जब तक निर्भरता जोड़ी गई हो)।

## GroupDocs.Viewer for Java सेट अप करना
अपने `pom.xml` में GroupDocs रिपॉजिटरी और निर्भरता जोड़ें:

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
GroupDocs Viewer मूल्यांकन के लिए एक मुफ्त ट्रायल लाइसेंस प्रदान करता है:

- **Free Trial**: लाइब्रेरी डाउनलोड करने के लिए [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) पर जाएँ।  
- **Temporary License**: [Temporary License Page](https://purchase.groupdocs.com/temporary-license/) पर आवेदन करें।  
- **Full License**: [Purchase Page](https://purchase.groupdocs.com/buy) पर उत्पादन लाइसेंस खरीदें।

### बुनियादी प्रारंभिककरण
लाइब्रेरी सही ढंग से लोड होती है यह सत्यापित करने के लिए एक सरल `Viewer` इंस्टेंस बनाएं:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## CAD ड्रॉइंग्स को टाइल्स में विभाजित करने के लिए चरण‑दर‑चरण मार्गदर्शिका

### चरण 1: आउटपुट डायरेक्टरी निर्धारित करें
हम प्रत्येक टाइल को अलग PNG फ़ाइल के रूप में संग्रहीत करेंगे। एक यूटिलिटी मेथड का उपयोग पाथ लॉजिक को साफ़ और पुन: उपयोग योग्य रखता है।

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### चरण 2: व्यू विकल्प कॉन्फ़िगर करें
रेंडरिंग फ़ॉर्मेट को PNG सेट करें और व्यूअर को हर पेज को प्री‑लोड न करने के लिए कहें (जो मेमोरी बचाता है)।

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### चरण 3: टाइल आयामों की गणना करें
पहले हम ड्रॉइंग की मूल चौड़ाई और ऊँचाई प्राप्त करते हैं, फिर इसे चार समान चतुर्थांशों में विभाजित करते हैं।

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### चरण 4: टाइल्स को रेंडर और सहेजें
गणना की गई टाइल्स को रेंडरिंग विकल्पों में जोड़ें और `Viewer` को PNG फ़ाइलें उत्पन्न करने दें।

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### समस्या निवारण टिप्स
- **Build path** – सुनिश्चित करें कि GroupDocs JAR फ़ाइलें क्लासपाथ पर हैं।  
- **Permissions** – आउटपुट फ़ोल्डर को Java प्रोसेस द्वारा लिखने योग्य होना चाहिए।  
- **Exceptions** – यदि आप `ViewerException` देखते हैं, तो दोबारा जांचें कि DWG फ़ाइल भ्रष्ट नहीं है और सही लाइसेंस लागू किया गया है।

## CAD टाइल्स को विभाजित करने के सामान्य उपयोग केस
1. **Web Mapping** – उपयोगकर्ता के पैन/ज़ूम करने पर फ़्लोर प्लान का केवल दृश्यमान भाग लोड करें।  
2. **Document Management** – तेज़ प्रीव्यू जनरेशन के लिए प्रत्येक टाइल को अलग से संग्रहीत करें।  
3. **Mobile Viewing** – वर्तमान स्क्रीन के लिए आवश्यक टाइल्स को ही डाउनलोड करके बैंडविड्थ कम करें।

## प्रदर्शन संबंधी विचार
- **Tile Size** – बड़े टाइल्स का मतलब कम फ़ाइलें लेकिन धीमी रेंडरिंग; अपने UI आवश्यकताओं के आधार पर संतुलन खोजें।  
- **Memory Monitoring** – बहुत बड़े ड्रॉइंग्स को प्रोसेस करते समय हीप उपयोग को देखने के लिए Java के प्रोफाइलिंग टूल्स (जैसे VisualVM) का उपयोग करें।  
- **Resource Cleanup** – ऊपर दिखाया गया try‑with‑resources पैटर्न स्वचालित रूप से नेटिव संसाधनों को रिलीज़ करता है।

## अक्सर पूछे जाने वाले प्रश्न

**Q: क्या मैं उसी दृष्टिकोण का उपयोग करके अन्य फ़ाइल प्रकारों (PDF, images) को टाइल्स में विभाजित कर सकता हूँ?**  
A: हाँ। GroupDocs Viewer कई फ़ॉर्मेट्स का समर्थन करता है; आपको केवल संबंधित विकल्प क्लास (जैसे `PdfViewOptions`) का उपयोग करना होगा।

**Q: आउटपुट इमेज क्वालिटी कैसे बदलूँ?**  
A: `viewOptions.setResolution(int dpi)` को समायोजित करें या `PngOptions` ऑब्जेक्ट पर संपीड़न सेटिंग्स सेट करें।

**Q: मेरे एप्लिकेशन में बहुत बड़े DWG फ़ाइलों पर मेमोरी खत्म हो जाती है—मैं क्या करूँ?**  
A: टाइल आयाम कम करें, JVM हीप (`-Xmx`) बढ़ाएँ, या अलग-अलग `Viewer` इंस्टेंस में टाइल्स को क्रमिक रूप से रेंडर करें।

**Q: क्या टाइल्स को असिंक्रोनस रूप से रेंडर करना संभव है?**  
A: बिल्कुल। प्रत्येक टाइल रेंडरिंग कॉल को `CompletableFuture` में रैप करें या कार्यभार को समानांतर करने के लिए एक executor सर्विस का उपयोग करें।

**Q: क्या मुझे प्रत्येक टाइल के लिए अलग लाइसेंस चाहिए?**  
A: नहीं। एक एकल वैध GroupDocs Viewer लाइसेंस आपके एप्लिकेशन के भीतर सभी रेंडरिंग ऑपरेशन्स को कवर करता है।

## संसाधन
- [डॉक्यूमेंटेशन](https://docs.groupdocs.com/viewer/java/)
- [API रेफ़रेंस](https://reference.groupdocs.com/viewer/java/)
- [GroupDocs.Viewer डाउनलोड करें](https://releases.groupdocs.com/viewer/java/)
- [लाइसेंस खरीदें](https://purchase.groupdocs.com/buy)
- [फ़्री ट्रायल](https://releases.groupdocs.com/viewer/java/)
- [टेम्पररी लाइसेंस](https://purchase.groupdocs.com/temporary-license/)
- [सपोर्ट फ़ोरम](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-04-01  
**परीक्षित संस्करण:** GroupDocs.Viewer 25.2 for Java  
**लेखक:** GroupDocs  

---