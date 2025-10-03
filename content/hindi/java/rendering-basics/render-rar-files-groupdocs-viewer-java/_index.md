---
"date": "2025-04-24"
"description": "Java के लिए GroupDocs.Viewer का उपयोग करके RAR फ़ाइलों को HTML, JPG, PNG और PDF जैसे सुलभ प्रारूपों में बदलना सीखें। यह चरण-दर-चरण मार्गदर्शिका सेटअप से लेकर विशिष्ट फ़ोल्डरों को रेंडर करने तक सब कुछ कवर करती है।"
"title": "Java के लिए GroupDocs.Viewer का उपयोग करके RAR फ़ाइलों को HTML, JPG, PNG और PDF में प्रस्तुत करें"
"url": "/hi/java/rendering-basics/render-rar-files-groupdocs-viewer-java/"
"weight": 1
type: docs
---
# Java के लिए GroupDocs.Viewer का उपयोग करके विभिन्न प्रारूपों में RAR फ़ाइलें प्रस्तुत करें

Java के लिए GroupDocs.Viewer के साथ अपने RAR अभिलेखागार को HTML, JPG, PNG और PDF जैसे सुलभ प्रारूपों में बदलकर उनकी क्षमता को अनलॉक करें। यह ट्यूटोरियल आपको प्रत्येक चरण के माध्यम से मार्गदर्शन करेगा, जिससे सहज दस्तावेज़ प्रबंधन और प्रस्तुति सक्षम होगी।

## आप क्या सीखेंगे
- Java के लिए GroupDocs.Viewer का उपयोग करके RAR फ़ाइलों को कई प्रारूपों में प्रस्तुत करें।
- RAR को HTML, JPG, PNG और PDF में परिवर्तित करने के लिए चरण-दर-चरण कोड उदाहरण।
- RAR संग्रह से दृश्य जानकारी पुनः प्राप्त करें.
- RAR फ़ाइल के भीतर विशिष्ट फ़ोल्डरों को रेंडर करें।

चलो इसमें गोता लगाएँ!

### आवश्यक शर्तें
शुरू करने से पहले, सुनिश्चित करें कि आपके पास निम्नलिखित हैं:

1. **जावा डेवलपमेंट किट (JDK)**: संस्करण 8 या उच्चतर आवश्यक है.
2. **मावेन**यह ट्यूटोरियल निर्भरता प्रबंधन के लिए मावेन का उपयोग करता है।
3. **जावा लाइब्रेरी के लिए GroupDocs.Viewer**हम संस्करण 25.2 का उपयोग करेंगे।

#### पर्यावरण सेटअप
- सुनिश्चित करें कि आपका विकास वातावरण JDK और Maven के साथ स्थापित है।
- बुनियादी जावा प्रोग्रामिंग अवधारणाओं से परिचित होने से आपको अधिक आसानी से अनुसरण करने में मदद मिलेगी।

### Java के लिए GroupDocs.Viewer सेट अप करना
अपने प्रोजेक्ट में GroupDocs.Viewer को एकीकृत करने के लिए, अपने में निम्नलिखित निर्भरताएँ जोड़ें `pom.xml` फ़ाइल:

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

#### लाइसेंस अधिग्रहण
- **मुफ्त परीक्षण**: यहाँ से निःशुल्क परीक्षण डाउनलोड करें [ग्रुपडॉक्स वेबसाइट](https://releases.groupdocs.com/viewer/java/).
- **अस्थायी लाइसेंस**: विस्तारित सुविधाओं के लिए अस्थायी लाइसेंस प्राप्त करें [ग्रुपडॉक्स लाइसेंस पृष्ठ](https://purchase.groupdocs.com/temporary-license/).
- **खरीदना**: दीर्घकालिक उपयोग के लिए, के माध्यम से लाइसेंस खरीदें [ग्रुपडॉक्स खरीद पृष्ठ](https://purchase.groupdocs.com/buy).

#### मूल आरंभीकरण
अपना परिवेश और निर्भरताएँ सेट करने के बाद, GroupDocs.Viewer को इस प्रकार प्रारंभ करें:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/file.rar")) {
            // आपका रेंडरिंग कोड यहाँ है
        }
    }
}
```

### कार्यान्वयन मार्गदर्शिका
हम यह पता लगाएंगे कि RAR फ़ाइलों को विभिन्न प्रारूपों में कैसे प्रस्तुत किया जाए, जिनमें से प्रत्येक का अपना कॉन्फ़िगरेशन होगा।

#### RAR को HTML में प्रस्तुत करना
**अवलोकन**: वेब देखने के लिए RAR फ़ाइल को HTML दस्तावेज़ में परिवर्तित करें।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class RenderRarToHtml {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options); // RAR फ़ाइल को HTML प्रारूप में प्रस्तुत करता है
        }
    }
}
```
- **स्पष्टीकरण**: द `HtmlViewOptions` क्लास का उपयोग एम्बेडेड संसाधनों के साथ किया जाता है, जिससे CSS और छवियों सहित संपूर्ण वेब पेज रेंडर करने की अनुमति मिलती है।

#### RAR को JPG में परिवर्तित करना
**अवलोकन**: RAR फ़ाइलों को JPEG छवियों में बदलें, थंबनेल पूर्वावलोकन के लिए आदर्श।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;

public class RenderRarToJpg {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.jpg");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options); // RAR फ़ाइल को JPG प्रारूप में परिवर्तित करता है
        }
    }
}
```
- **स्पष्टीकरण**: `JpgViewOptions` आउटपुट पथ निर्दिष्ट करता है और छवि रेंडरिंग को संभालता है।

#### RAR को PNG में परिवर्तित करना
**अवलोकन**: उच्च गुणवत्ता वाले पूर्वावलोकन के लिए RAR अभिलेखागार को PNG छवियों में परिवर्तित करें।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

public class RenderRarToPng {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.png");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options); // RAR फ़ाइल को PNG प्रारूप में प्रस्तुत करता है
        }
    }
}
```
- **स्पष्टीकरण**: JPG के समान, `PngViewOptions` इसका उपयोग RAR के प्रत्येक पृष्ठ को PNG छवि के रूप में प्रस्तुत करने के लिए किया जाता है।

#### RAR को PDF में परिवर्तित करना
**अवलोकन**आसान साझाकरण और मुद्रण के लिए RAR फ़ाइलों से PDF दस्तावेज़ उत्पन्न करें।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class RenderRarToPdf {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result.pdf");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options); // RAR फ़ाइल को PDF प्रारूप में परिवर्तित करता है
        }
    }
}
```
- **स्पष्टीकरण**: `PdfViewOptions` पीडीएफ दस्तावेज़ के लिए आउटपुट पथ कॉन्फ़िगर करता है।

#### RAR के लिए दृश्य जानकारी प्राप्त करना
**अवलोकन**: RAR संग्रह से मेटाडेटा और संरचना जानकारी पुनर्प्राप्त करें।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ArchiveViewInfo;

public class GetViewInfoForRar {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            ViewInfo info = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
            System.out.println("File type: " + info.getFileType());
            System.out.println("Pages count: " + info.getPages().size());

            readFolders(viewer, "");
        }
    }

    private static void readFolders(Viewer viewer, String folder) {
        ViewInfoOptions options = ViewInfoOptions.forHtmlView();
        options.getArchiveOptions().setFolder(folder);

        ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(options);
        for (String subFolder : viewInfo.getFolders()) {
            System.out.println(" - " + subFolder);
            readFolders(viewer, subFolder);
        }
    }
}
```
- **स्पष्टीकरण**यह कोड RAR संग्रह में फ़ाइल प्रकार और पृष्ठों की संख्या को पुनर्प्राप्त और प्रिंट करता है।

#### RAR संग्रह के विशिष्ट फ़ोल्डर का प्रतिपादन
**अवलोकन**: RAR फ़ाइल के भीतर विशिष्ट फ़ोल्डरों को HTML प्रारूप में प्रस्तुत करने पर ध्यान केंद्रित करें।

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class RenderSpecificArchiveFolder {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderSpecificArchiveFolder");
        Path pageFilePathFormat = outputDirectory.resolve("archive_folder_page_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            options.getArchiveOptions().setFolder("TargetFolderName"); // वह फ़ोल्डर निर्दिष्ट करें जिसे आप रेंडर करना चाहते हैं
            viewer.view(options); // निर्दिष्ट फ़ोल्डर सामग्री को HTML में प्रस्तुत करता है
        }
    }
}
```
- **स्पष्टीकरण**: उपयोग `HtmlViewOptions` RAR संग्रह के भीतर अलग-अलग फ़ोल्डरों को लक्षित करने और रेंडर करने के लिए विशिष्ट फ़ोल्डर सेटिंग्स के साथ।

इन चरणों का पालन करके, आप अपने RAR फ़ाइलों को विभिन्न प्रारूपों में प्रबंधित और परिवर्तित करने के लिए Java के लिए GroupDocs.Viewer का प्रभावी ढंग से उपयोग कर सकते हैं।

## निष्कर्ष

यह ट्यूटोरियल आपको Java के लिए GroupDocs.Viewer का उपयोग करके RAR अभिलेखागार को HTML, JPG, PNG और PDF जैसे सुलभ प्रारूपों में आसानी से परिवर्तित करने के ज्ञान से लैस करता है। आप चरण-दर-चरण कार्यान्वयन विवरण सीखेंगे, जिसमें विशिष्ट फ़ोल्डरों को प्रस्तुत करना और संग्रह जानकारी को पुनः प्राप्त करना, आपकी दस्तावेज़ प्रबंधन क्षमताओं को बढ़ाना शामिल है। चाहे वेब देखने, पूर्वावलोकन या साझा करने के लिए, ये तकनीकें आपके Java अनुप्रयोगों में RAR फ़ाइलों को संभालने के तरीके को सुव्यवस्थित करती हैं।

### अक्सर पूछे जाने वाले प्रश्न

1. **क्या मैं Java के लिए GroupDocs.Viewer के साथ पासवर्ड-संरक्षित RAR फ़ाइलों को परिवर्तित कर सकता हूं?**  

हां, लेकिन आपको संरक्षित अभिलेखों को अनलॉक करने और देखने के लिए विकल्पों में पासवर्ड प्रदान करना होगा।

2. **क्या RAR में केवल विशिष्ट पृष्ठों या फ़ोल्डरों को ही रेंडर करना संभव है?**  

बिल्कुल, आप समर्पित विकल्पों का उपयोग करके रेंडर करने के लिए फ़ोल्डर्स या पेज निर्दिष्ट कर सकते हैं जैसे `setFolder()` रेंडरिंग सेटिंग्स के भीतर.

3. **GroupDocs.Viewer RAR फ़ाइलों के लिए कौन से आउटपुट स्वरूपों का समर्थन करता है?**  

यह HTML, JPG, PNG और PDF प्रारूपों का समर्थन करता है, तथा देखने और साझा करने के लिए लचीले विकल्प प्रदान करता है।

4. **क्या मुझे Java के लिए GroupDocs.Viewer का उपयोग करने के लिए लाइसेंस की आवश्यकता है?**  

निःशुल्क परीक्षण उपलब्ध है; पूर्ण सुविधाओं और दीर्घकालिक उपयोग के लिए लाइसेंस खरीदना या अस्थायी लाइसेंस प्राप्त करना अनुशंसित है।

5. **क्या मैं जावा अनुप्रयोग में RAR रूपांतरण को स्वचालित कर सकता हूँ?**  

हां, आप बैच रूपांतरणों को स्वचालित रूप से करने के लिए दिए गए कोड उदाहरणों को अपनी जावा परियोजनाओं में एम्बेड कर सकते हैं।