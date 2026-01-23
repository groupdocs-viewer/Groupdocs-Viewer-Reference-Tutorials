---
date: '2026-01-23'
description: GroupDocs.Viewer for Java का उपयोग करके CAD ड्रॉइंग को टाइल्स में विभाजित
  करना सीखें, जिससे तेज़ रेंडरिंग और आपके अनुप्रयोगों में आसान एकीकरण संभव हो।
keywords:
- GroupDocs.Viewer Java
- split CAD drawings into tiles
- rendering large CAD files
title: GroupDocs.Viewer Java के साथ CAD ड्राइंग को टाइल्स में विभाजित करें
type: docs
url: /hi/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

बंधिताई महसूस कर रहे हैं? यह गाइड आपको **CAD ड्रॉइंग को** प्रबंध किया गया है। ड्रॉइंग को छोटे हिस्सों में विभाजित करके आप प्रदर्शन को काफी हद तक बढ़ा सकते हैं और हैंडलिंग को आसान बना सकते हैं।

## त्वरित उत्तर
- **CAD ड्रॉइंग को विभाजित करने से क्या हासिल होता है?** यह पूरे फ़ाइल को एक साथ प्रोसेस करने के बजाय छोटे इमेज टाइल्स को प्रोसेस करके रेंडरिंग लोड को कम करता है।  
- **कौन सी लाइब्रेरी आवश्यक है?** GroupDocs.Viewer for Java (संस्करण 25.2 या बाद का)।  
- **क्या मुझे लाइसेंस चाहिए?** एक मुफ्त ट्रायल लाइसेंस उपलब्ध है; उत्पादन उपयोग के लिए वाणिज्यिक लाइसेंस आवश्यक है।  
- **क्या मैं टाइल आकार को कस्टमाइज़ कर सकता हूँ?** हाँ, आप अपने प्रदर्शन और विवरण की जरूरतों के अनुसार टाइल आयाम निर्धारित कर सकते हैं।  
- **क्या यह तरीका वेब या मोबाइल ऐप्स के लिए उपयुक्त है?** बिल्कुल – टाइल्ड इमेजेज तेज़ लोड होती हैं और कम बैंडविड्थ खपत करती हैं।

![GroupDocs.Viewer for Java के साथ CAD ड्रॉइंग्स को विभाजित करें](/viewer/advanced-rendering/split-cad-drawings-java.png)

**आप क्या सीखेंगे:**
- GroupDocs.Viewer for Java को सेटअप और कॉन्फ़िगर करना।  
- CAD ड्रॉइंग को टाइल्स में विभाजित करने की चरण‑दर‑चरण प्रक्रिया।  
- प्रमुख कॉन्फ़िगरेशन और ऑप्टिमाइज़ेशन तकनीकें।  
- व्यावहारिक अनुप्रयोग और इंटीग्रेशन संभावनाएँ।

आइए शुरू करते हैं, यह सुनिश्चित करके कि आपका वातावरण आवश्यक प्री‑रिक्विज़िट्स के साथ तैयार है।

## प्री‑रिक्विज़िट्स
शुरू करने से पहले सुनिश्चित करें कि आपके पास हैं:

- **लाइब्रेरीज़**: GroupDocs.Viewer for Java (संस्करण 25.2 या बाद का)।  
- **पर्यावरण सेटअप**: एक कार्यशील Java Development Kit (JDK) और IntelliJ IDEA या Eclipse जैसे IDE।  
- **ज्ञान की पूर्वशर्तें**: बुनियादी Java प्रोग्रामिंग कौशल और Maven से परिचितता।

## GroupDocs.Viewer for Java को सेटअप करना
GroupDocs.Viewer का उपयोग करने के लिए इसे अपने प्रोजेक्ट में डिपेंडेंसी के रूप में जोड़ें। यदि आप Maven का उपयोग कर रहे हैं:

**Maven Configuration:**
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
GroupDocs.Viewer अपनी पूरी क्षमताओं को अन्वेषण करने के लिए एक मुफ्त ट्रायल लाइसेंस प्रदान करता है:
- **Free Trial**: लाइब्रेरी डाउनलोड और परीक्षण करने के लिए [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) पर जाएँ।  
- **Temporary License**: एक अस्थायी लाइसेंस के लिए [Temporary License Page](https://purchase.groupdocs.com/temporary-license/) पर आवेदन करें।  
- **Purchase**: पूर्ण लाइसेंस खरीदने के लिए उनके [Purchase Page](https://purchase.groupdocs.com/buy) पर जाएँ।

### बेसिक इनिशियलाइज़ेशन और सेटअप
अपने Java एप्लिकेशन में GroupDocs.Viewer को इनिशियलाइज़ करने के लिए:
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
सेटअप पूरा होने के बाद, आइए फीचर को लागू करने की ओर बढ़ते हैं।

## CAD ड्रॉइंग को टाइल्स में विभाजित करने का तरीका
यह अनुभाग दिखाता है कि CAD ड्रॉइंग को छोटे टाइल्स में कैसे विभाजित किया जाए, जिससे हैंडलिंग और रेंडरिंग अधिक कुशल हो सके। प्रत्येक टाइल मूल आकार का एक चौथाई होगी।

### चरण 1: आउटपुट डायरेक्टरी पाथ परिभाषित करें
सबसे पहले यह निर्धारित करें कि आपके रेंडर किए गए इमेजेज़ कहाँ सहेजे जाएंगे:
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```
यह सेटअप पुन: उपयोगिता और स्पष्टता के लिए एक यूटिलिटी मेथड का उपयोग करता है।

### चरण 2: व्यू ऑप्शन्स कॉन्फ़िगर करें
प्रत्येक सेक्शन को अलग‑अलग रेंडर करने के विकल्प सेट करें:
```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```
यह स्निपेट सभी पेजों को एक साथ प्रोसेस किए बिना PNG रेंडरिंग को कॉन्फ़िगर करता है।

### चरण 3: टाइल डाइमेंशन्स की गणना करें
प्रत्येक टाइल के आयाम निर्धारित करें:
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
गणना किए गए प्रत्येक टाइल को रेंडरिंग ऑप्शन्स में जोड़ें और रेंडर करें:
```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```
यह अंतिम चरण निर्दिष्ट टाइल्स के आधार पर दस्तावेज़ को रेंडर करता है और प्रत्येक को अलग‑अलग PNG फ़ाइल के रूप में सहेजता है।

### ट्रबलशूटिंग टिप्स
- सुनिश्चित करें कि आपके प्रोजेक्ट की बिल्ड पाथ में GroupDocs.Viewer JAR फ़ाइलें शामिल हैं।  
- यह जांचें कि आउटपुट डायरेक्टरी आपके एप्लिकेशन द्वारा लिखी जा सकती है।  
- रेंडरिंग में किसी भी एक्सेप्शन को देखें ताकि विशिष्ट ड्रॉइंग फ़ाइलों से संबंधित समस्याओं का निदान किया जा सके।

## व्यावहारिक अनुप्रयोग
CAD ड्रॉइंग को टाइल्स में विभाजित करना निम्नलिखित मामलों में उपयोगी हो सकता है:
1. **वेब मैपिंग** – बड़े आर्किटेक्चरल प्लान्स को वेब मैप्स पर बिना सर्वर संसाधनों को अधिक लोड किए लोड करना।  
2. **डॉक्यूमेंट मैनेजमेंट सिस्टम्स** – बड़े ड्रॉइंग्स के विशिष्ट सेक्शनकर्ता इंटरैक्शन के केवल आवश्यक भागों को रेंडर करके प्रदर्शन को बढ़ाना।

## प्रदर्शन विचार
अपने एप्लिकेशन के प्रदर्शन को अनुकूलित करने के लिए:
- टाइल्स का रणनीतिक उपयोग करके विवरण और प्रोसेसिंग समय के बीच संतुलन बनाएं।  
- विशेष रूप से बहुत बड़े ड्रॉइंग्स के साथ काम करते समय मेमोरी उपयोग की निगरानी करें।  
- Java की बेस्ट प्रैक्टिसेज़ अपनाएँ, जैसे कि ऑटोमैटिक क्लीन‑अप के लिए try‑with का उपयोग।

##ने अब **CAD ड्रॉइंग को** टाइल्स में विभाजित करने का तरीका GroupDocs.Viewer for Java के साथ सीख लिया है  
 की अन्य सुविधाओं का अन्वेषण करें।

क्या आप इस समाधान को अपने प्रोजेक्ट में लागू करने के लिए तैयार हैं? इसे आज़माएँ और स्वयं प्रदर्शन सुधार देखें!

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: GroupDocs.Viewer Java का उपयोग करते समय सामान्य त्रुटियाँ क्या हैं?**  
उत्तर: आम समस्याओं में गलत फ़ाइल पाथ, आउटपुट डायरेक्टरी पर अपर्याप्त अनुमतियाँ, या डिपेंडेंसीज़ की कमी शामिल हैं।

**प्रश्न: क्या मैं इस विधि से अन्य प्रकार के दस्तावेज़ों को भी टाइल्स में विभाजित कर सकता हूँ?**  
उत्तर: जबकि उदाहरण CAD ड्रॉइंग्स पर केंद्रित है, समान सिद्धांतों को GroupDocs.Viewer द्वारा समर्थित अन्य फ़ॉर्मैट्स पर भी लागू किया जा सकता है।

**प्रश्न: बहुत बड़े फ़ाइलों को कुशलतापूर्वक कैसे संभालूँ?**  
उत्तर: Java में मल्टी‑थ्रेडिंग या असिंक्रोनस प्रोसेसिंग पर विचार करें, और मेमोरी उपयोग को नियंत्रित रखने के लिए टाइल आकार को समायोजित करें।

**प्रश्न: क्या आउटपुट इमेज क्वालिटी को कस्टमाइज़ किया जा सकता है?**  
उत्तर: हाँ, PNGViewOptions आपको रिज़ॉल्यूशन और कम्प्रेशन सेटिंग्स सेट करने की अनुमति देता है जिससे इमेज क्वालिटी नियंत्रित की जा सकती है।

**प्रश्न: यदि रेंडरिंग के दौरान मेरा एप्लिकेशन मेमोरी समाप्त कर देता है तो क्या करूँ?**  
उत्तर: टाइल आयाम घटाएँ, JVM हीप साइज बढ़ाएँ (उदाहरण के लिए `-Xmx2g`), और Viewer इंस्टेंसेज़ को तुरंत डिस्पोज़ करना सुनिश्चित करें।

## संसाधन
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-01-23  
**Tested With:** GroupDocs.Viewer Java 25.2  
**Author:** GroupDocs