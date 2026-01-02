---
date: '2026-01-02'
description: GroupDocs.Viewer के साथ JPG गुणवत्ता को समायोजित करके Java में PDF आकार
  को कैसे घटाएँ, यह सीखें—PDF छवियों को संपीड़ित करने और फ़ाइल आकार को दृश्य गुणवत्ता
  के साथ संतुलित करने का एक सरल तरीका।
keywords:
- reduce pdf size java
- convert pptx to pdf
- compress pdf images
title: PDF आकार घटाएँ जावा – GroupDocs के साथ JPG गुणवत्ता को अनुकूलित करें
type: docs
url: /hi/java/advanced-rendering/optimize-jpg-quality-groupdocs-viewer-java/
weight: 1
---

# Reduce PDF Size Java – Optimize JPG Quality with GroupDocs.Viewer

PDF फ़ाइलों के आकार और दृश्य गुणवत्ता के बीच संतुलन बनाना अक्सर एक चुनौती होती है। इस ट्यूटोरियल में आप **reduce PDF size Java** को कैसे प्राप्त करें, यह जानेंगे, जिसमें PDF दस्तावेज़ों के भीतर JPG इमेज की गुणवत्ता को समायोजित किया जाता है, GroupDocs.Viewer for Java का उपयोग करके। हम सेटअप, कोड इम्प्लीमेंटेशन और व्यावहारिक टिप्स को चरण‑दर‑चरण देखेंगे ताकि आप पढ़ने की क्षमता से समझौता किए बिना PDF इमेज को संकुचित कर सकें।

![Optimize JPG Quality in PDFs with GroupDocs.Viewer for Java](/viewer/advanced-rendering/optimize-jpg-quality-in-pdfs.png)

## Quick Answers
- **“reduce PDF size Java” का क्या अर्थ है?** इमेज गुणवत्ता, संपीड़न और संसाधन प्रबंधन को समायोजित करके Java एप्लिकेशन में छोटे PDF फ़ाइलें बनाना।  
- **कौन सा सेटिंग JPG गुणवत्ता को नियंत्रित करता है?** `PdfViewOptions.setJpgQuality(byte quality)` जहाँ मान 0 (सबसे कम) से 100 (सबसे अधिक) तक होता है।  
- **क्या मैं उसी प्रवाह में PPTX को PDF में भी बदल सकता हूँ?** हाँ—सिर्फ `Viewer` को `.pptx` स्रोत की ओर इंगित करें और वही विकल्प लागू होंगे।  
- **वेब प्रकाशन के लिए सामान्य गुणवत्ता स्तर क्या है?** लगभग **50‑70** का मान अधिकांश वेब परिदृश्यों के लिए अच्छा संतुलन देता है।  
- **क्या इस फीचर के लिए लाइसेंस चाहिए?** मूल्यांकन के लिए एक फ्री ट्रायल काम करता है; उत्पादन उपयोग के लिए एक स्थायी लाइसेंस आवश्यक है।

## What is “reduce PDF size Java”?
Java में PDF आकार को कम करना मतलब PDF के अंदर मौजूद संसाधनों—विशेषकर इमेज—को ऑप्टिमाइज़ करना, ताकि अंतिम फ़ाइल कम स्टोरेज ले और तेज़ लोड हो। JPG गुणवत्ता को घटाकर आप प्रभावी रूप से **PDF इमेज को संकुचित** करते हैं, जो अक्सर दस्तावेज़ के आकार का अधिकांश हिस्सा बनाते हैं।

## Why adjust JPG quality with GroupDocs Viewer?
- **महत्वपूर्ण आकार घटाव**: इमेज गुणवत्ता घटाने से मूल रिज़ॉल्यूशन के आधार पर PDF 30‑70 % तक छोटा हो सकता है।  
- **सिंगल‑पास कन्वर्ज़न**: अलग इमेज प्रोसेसिंग चरण की आवश्यकता नहीं; GroupDocs PDF जनरेशन के दौरान इसे संभालता है।  
- **लचीलापन**: आप `byte` गुणवत्ता मान को प्रोजेक्ट की आवश्यकताओं के अनुसार बारीकी से सेट कर सकते हैं (जैसे हाई‑क्वालिटी प्रिंट बनाम हल्का वेब प्रीव्यू)।

## Prerequisites
- **GroupDocs.Viewer for Java** संस्करण 25.2 या नया।  
- Maven‑आधारित Java प्रोजेक्ट जिसमें JDK 8 या बाद का संस्करण हो।  
- Java और PDF हैंडलिंग का बुनियादी ज्ञान।

## Setting Up GroupDocs.Viewer for Java
`pom.xml` में GroupDocs रिपॉज़िटरी और डिपेंडेंसी जोड़ें:

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

> **Pro tip:** नवीनतम संस्करण रखें ताकि प्रदर्शन सुधार और नई संपीड़न विकल्पों का लाभ मिल सके।

## Implementation Guide

### Step 1: Resolve the Output Directory Path
एक हेल्पर क्लास बनाएं जो आउटपुट फ़ोल्डर को बनाता है जहाँ PDF सहेजा जाएगा।

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public class FeatureResolveOutputDirectoryPath {
    public static Path getOutputDirectoryPath(String subdirectory) {
        String directory = Paths.get("YOUR_OUTPUT_DIRECTORY", "AdjustQualityOfJpgImages", subdirectory).toString();
        
        try {
            return Paths.get(directory);
        } catch (IOException e) {
            throw new RuntimeException("Failed to create output directory.", e);
        }
    }
}
```

### Step 2: Configure `PdfViewOptions` with Desired JPG Quality
रेंडर करने से पहले JPG गुणवत्ता स्तर (0‑100) सेट करें।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class FeatureAdjustQualityOfJpgImages {
    public static void run() {
        Path outputDirectory = FeatureResolveOutputDirectoryPath.getOutputDirectoryPath("YOUR_DOCUMENT_DIRECTORY");
        Path filePath = outputDirectory.resolve("output.pdf");

        PdfViewOptions viewOptions = new PdfViewOptions(filePath);
        
        // Set desired JPG quality (0-100 scale)
        byte quality = 10;
        viewOptions.setJpgQuality(quality);

        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/source.pptx")) {
            viewer.view(viewOptions);
        }
    }
}
```

**Explanation:**  
- `setJpgQuality(byte quality)` GroupDocs को बताता है कि JPG इमेज पर कितना संपीड़न लागू करना है। कम मान छोटे फ़ाइल बनाते हैं लेकिन दृश्य तीक्ष्णता घटा सकते हैं।  
- उदाहरण में `source.pptx` का उपयोग करके **convert pptx to pdf** दिखाया गया है, साथ ही इमेज को संकुचित किया गया है।

### Step 3: Run the Code and Verify the Result
`FeatureAdjustQualityOfJpgImages.run()` चलाएँ। उत्पन्न `output.pdf` में निर्दिष्ट गुणवत्ता स्तर की JPG इमेज होंगी, जिससे **PDF इमेज संकुचित** हो जाएगी और कुल फ़ाइल आकार घटेगा।

## Common Issues & Troubleshooting
- **गलत फ़ाइल पथ:** सुनिश्चित करें कि स्रोत दस्तावेज़ (`source.pptx`) कार्य निर्देशिका के सापेक्ष मौजूद है।  
- **पर्याप्त अनुमति नहीं:** आउटपुट फ़ोल्डर लिखने योग्य होना चाहिए; अन्यथा `RuntimeException` फेंका जाएगा।  
- **अप्रत्याशित बड़े PDF:** जांचें कि `quality` मान आपके आकार लक्ष्य के लिए पर्याप्त रूप से कम है या नहीं।

## Practical Applications
1. **दस्तावेज़ अभिलेखागार:** छोटे PDF स्टोरेज लागत बचाते हैं और पुनः प्राप्ति गति बढ़ाते हैं।  
2. **वेब प्रकाशन:** जब PDF वेबसाइट पर एम्बेड या लिंक किए जाते हैं तो तेज़ पेज लोड होते हैं।  
3. **ई‑मेल अटैचमेंट:** भेजने से पहले इमेज गुणवत्ता घटाकर आकार सीमा पूरी करें।

## Performance Considerations
- **बैच प्रोसेसिंग:** बड़ी संख्या में दस्तावेज़ों के लिए समानांतर थ्रेड्स में प्रोसेस करें और मेमोरी उपयोग पर नज़र रखें।  
- **इष्टतम गुणवत्ता सेटिंग्स:** प्रिंट‑रेडी PDF के लिए उच्च गुणवत्ता (80‑100) उपयोग करें; वेब प्रीव्यू के लिए 30‑50 अक्सर पर्याप्त होती है।

## Conclusion
आप अब जानते हैं कि **reduce PDF size Java** को कैसे हासिल किया जाए, JPG इमेज गुणवत्ता को GroupDocs.Viewer के साथ समायोजित करके। विभिन्न गुणवत्ता स्तरों के साथ प्रयोग करें, कोड को अपने मौजूदा पाइपलाइन में एकीकृत करें, और तेज़, हल्के PDF का आनंद लें।

### Next Steps
- विभिन्न गुणवत्ता सेटिंग्स का परीक्षण करके अपने उपयोग‑केस के लिए सबसे उपयुक्त बिंदु खोजें।  
- वॉटरमार्किंग या पासवर्ड सुरक्षा जैसे अतिरिक्त GroupDocs फीचर्स का अन्वेषण करें।

## FAQ Section

1. **JPG गुणवत्ता समायोजित करने से फ़ाइल आकार पर क्या प्रभाव पड़ता है?**  
   गुणवत्ता घटाने से फ़ाइल आकार कम हो जाता है, जिससे दस्तावेज़ साझा या संग्रहीत करना आसान हो जाता है।

2. **क्या मैं JPG के अलावा अन्य फ़ॉर्मेट की इमेज गुणवत्ता समायोजित कर सकता हूँ?**  
   यह फीचर विशेष रूप से PDF के भीतर JPG इमेज को लक्षित करता है; हालांकि, GroupDocs.Viewer विभिन्न फ़ॉर्मेट के लिए अन्य विकल्प प्रदान करता है।

3. **वेब उपयोग के लिए आदर्श JPG गुणवत्ता सेटिंग क्या है?**  
   लगभग 50‑70 का संतुलन अक्सर अच्छी स्पष्टता के साथ कम फ़ाइल आकार देता है, जो वेब एप्लिकेशन के लिए उपयुक्त है।

4. **क्या इस प्रक्रिया को बैच वर्कफ़्लो में स्वचालित किया जा सकता है?**  
   हाँ, आप इस फीचर को स्वचालित सिस्टम में एकीकृत करके कई दस्तावेज़ों को कुशलता से संभाल सकते हैं।

5. **यदि आउटपुट PDF अपेक्षित रूप से नहीं बन रहा है तो क्या करें?**  
   इनपुट दस्तावेज़ पथ की जाँच करें और सुनिश्चित करें कि सभी डिपेंडेंसी सही ढंग से कॉन्फ़िगर हैं।

## Frequently Asked Questions

**Q:** *क्या मैं इस विधि का उपयोग करके DOCX जैसे अन्य फ़ॉर्मेट को PDF में बदलते समय आकार घटा सकता हूँ?*  
**A:** बिल्कुल। वही `PdfViewOptions.setJpgQuality` सेटिंग किसी भी स्रोत फ़ॉर्मेट पर लागू होती है जो PDF में JPG इमेज उत्पन्न करता है।

**Q:** *क्या JPG गुणवत्ता घटाने से टेक्स्ट रेंडरिंग प्रभावित होती है?*  
**A:** नहीं। टेक्स्ट वेक्टर‑आधारित रहता है और स्पष्ट रहता है; केवल रास्टर इमेज प्रभावित होते हैं।

**Q:** *क्या विभिन्न पृष्ठों के लिए अलग‑अलग गुणवत्ता स्तर सेट करना संभव है?*  
**A:** वर्तमान में GroupDocs प्रत्येक कन्वर्ज़न के लिए एक समान गुणवत्ता सेटिंग लागू करता है। पृष्ठ‑वार नियंत्रण के लिए आपको PDF को किसी समर्पित इमेज हैंडलिंग लाइब्रेरी से पोस्ट‑प्रोसेस करना पड़ेगा।

**Q:** *उत्पादन परिनियोजन के लिए क्या लाइसेंस आवश्यक है?*  
**A:** हाँ, उत्पादन उपयोग के लिए एक वैध GroupDocs.Viewer लाइसेंस आवश्यक है। मूल्यांकन के लिए एक फ्री ट्रायल उपलब्ध है।

**Q:** *वास्तविक गुणवत्ता कमी कैसे सत्यापित करूँ?*  
**A:** परिवर्तन से पहले और बाद के फ़ाइल आकार की तुलना करें, और PDF खोलकर इमेज की स्पष्टता को दृश्य रूप से जांचें।

---

**Last Updated:** 2026-01-02  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Resources**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Information](https://purchase.groupdocs.com/temporary-license/)  
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)