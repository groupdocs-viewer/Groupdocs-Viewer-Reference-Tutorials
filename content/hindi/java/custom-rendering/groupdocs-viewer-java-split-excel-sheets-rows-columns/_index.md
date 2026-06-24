---
date: '2026-06-15'
description: GroupDocs Viewer का उपयोग करके Excel को PDF Java में परिवर्तित करना और
  पंक्तियों और स्तंभों द्वारा Excel शीट्स को विभाजित करना सीखें। शामिल हैं setup,
  code, और best practices.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Excel को PDF Java में परिवर्तित करें और पंक्तियों और स्तंभों द्वारा शीट्स को
  विभाजित करें
type: docs
url: /hi/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Excel को PDF Java में बदलें और पंक्तियों एवं स्तंभों द्वारा शीट्स विभाजित करें (Java)

Large Excel workbooks often contain more data than can be comfortably displayed on a single screen or printed page. **convert excel to pdf java** is a common requirement when you need a static, share‑able format, while **splitting Excel sheets by rows and columns** makes the data easier to consume in web or print layouts. In this guide we’ll walk through both tasks using **GroupDocs Viewer for Java**, show you how to configure pagination, and explain best‑practice tips for performance and troubleshooting.

![Rows और Columns द्वारा Split Excel Sheets with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Rows और Columns द्वारा Split Excel Sheets with GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## त्वरित उत्तर
- **कौन सी लाइब्रेरी उपयोग की गई है?** GroupDocs Viewer for Java.  
- **क्या मैं पंक्तियों और स्तंभों दोनों द्वारा विभाजित कर सकता हूँ?** Yes – you can define rows‑per‑page and columns‑per‑page together.  
- **क्या मुझे लाइसेंस चाहिए?** A trial or temporary license works for development; a full license is required for production.  
- **कौन से आउटपुट फ़ॉर्मेट समर्थित हैं?** HTML (embedded resources) is shown; PDF can be generated with the same options.  
- **क्या Maven आवश्यक है?** Maven is the recommended way to manage dependencies.  
- **क्या मैं Excel को PDF में भी बदल सकता हूँ?** Absolutely – just switch `HtmlViewOptions` to `PdfViewOptions` and reuse the same pagination settings.

## “How to Split Excel” क्या है?
Splitting an Excel sheet means dividing a single worksheet into multiple pages or files based on a fixed number of rows, columns, or both. This technique is handy when you need to create paginated reports, embed data in web pages, or generate printable sections without loading the entire workbook at once.

## GroupDocs Viewer for Java क्यों उपयोग करें?
GroupDocs Viewer processes spreadsheets in a single pass and automatically paginates them, eliminating manual calculations. **Fast rendering processes a 250‑page XLSX workbook in under 2 seconds on a typical 2‑core server**, and **the library supports 50+ input and output formats**, including XLS, XLSX, CSV, PDF, and HTML. It runs on any JVM‑compatible platform—Windows, Linux, macOS, Docker containers, or cloud‑based serverless runtimes—so you can integrate it wherever your Java application lives.

## पूर्वापेक्षाएँ
- Java 17 या बाद का संस्करण स्थापित हो।  
- IntelliJ IDEA या Eclipse जैसे IDE।  
- निर्भरताओं के प्रबंधन के लिए Maven।  
- बुनियादी Java ज्ञान और Excel फ़ाइल हैंडलिंग की परिचितता।

### आवश्यक लाइब्रेरी, संस्करण, और निर्भरताएँ
Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
Obtain a free trial, temporary license, or purchase a full license from [GroupDocs](https://purchase.groupdocs.com/buy).

## Excel को PDF Java में कैसे बदलें?

The `Viewer` class is the core component of GroupDocs Viewer that loads a document and provides rendering methods for various output formats. `SpreadsheetOptions` allows you to control pagination settings such as rows‑per‑page and columns‑per‑page for spreadsheet rendering.

Load your Excel file with `new Viewer("source.xlsx")`, configure `SpreadsheetOptions` for pagination, and call `viewer.view(pdfOptions, stream)` – that single call converts the workbook to a PDF while respecting the row/column limits you set. The conversion preserves formulas, images, and cell styles, delivering a faithful PDF replica ready for distribution.

## Excel शीट्स को पंक्तियों द्वारा विभाजित कैसे करें

Splitting by rows creates a series of HTML pages, each containing a fixed number of rows (e.g., 15). This approach is ideal for dashboards that display a limited number of records per view. The viewer will generate separate HTML files such as `page_0.html`, `page_1.html`, etc., each containing the specified number of rows. This makes it simple to load only the needed portion in a web interface, reducing bandwidth and rendering time.

### परिभाषा एंकर
`Viewer` is GroupDocs Viewer’s core class that loads a document and orchestrates rendering to the chosen output format.

### चरण‑दर‑चरण कार्यान्वयन

#### चरण 1: पाथ सेट करें और Viewer को इनिशियलाइज़ करें
First, define where the split pages will be saved and create a `Viewer` instance for the source workbook.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### चरण 2: प्रति पेज पंक्तियों को कॉन्फ़िगर करें
Tell the viewer how many rows each page should contain.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### चरण 3: दस्तावेज़ रेंडर करें
Finally, render the workbook using the options you defined.

```java
viewer.view(viewOptions);
```

## Excel शीट्स को पंक्तियों और स्तंभों द्वारा विभाजित कैसे करें

Sometimes a single page needs to show a matrix of rows **and** columns (e.g., 15 rows × 7 columns). This gives you full control over the layout of each HTML page. The resulting pages display a rectangular block of cells, for example rows 1‑15 and columns A‑G on the first page, rows 16‑30 and columns H‑N on the next. This grid‑style pagination is useful for creating printable reports that fit standard paper sizes.

### परिभाषा एंकर
`SpreadsheetOptions` configures how many rows and columns appear on each generated page.

### चरण‑दर‑चरण कार्यान्वयन

#### चरण 1: पाथ सेट करें और Viewer को इनिशियलाइज़ करें
The setup mirrors the row‑only example, only the file name changes.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### चरण 2: प्रति पेज पंक्तियों और स्तंभों को कॉन्फ़िगर करें
Specify both dimensions to create a grid‑style split.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### चरण 3: दस्तावेज़ रेंडर करें
Render using the same `view` call.

```java
viewer.view(options);
```

## व्यावहारिक अनुप्रयोग
- **Generate Excel report Java**: बड़े वित्तीय मॉडल को पेजिनेटेड HTML रिपोर्टों की श्रृंखला में बदलें।  
- **GroupDocs Viewer Excel**: विभाजित पेजों को सीधे वेब पोर्टल में एम्बेड करें इंटरैक्टिव डेटा एक्सप्लोरेशन के लिए।  
- **Render Excel HTML Java**: तेज़ क्लाइंट‑साइड रेंडरिंग के लिए सर्वलेट या Spring कंट्रोलर के माध्यम से उत्पन्न HTML पेज सर्व करें।  

## प्रदर्शन संबंधी विचार
- **Memory usage** – बड़े वर्कबुक काफी हीप उपयोग कर सकते हैं; JVM `-Xmx` सेटिंग बढ़ाने पर विचार करें।  
- **Chunk size** – पेज आकार और रेंडरिंग गति के बीच संतुलन बनाने के लिए पंक्तियों/स्तंभों की संख्या चुनें।  
- **Version updates** – प्रदर्शन सुधारों के लिए GroupDocs Viewer को अद्यतित रखें; नवीनतम 25.2 रिलीज़ रेंडरिंग गति को 24.x की तुलना में 30 % तक बढ़ाता है।  

## सामान्य समस्याएँ और समस्या निवारण
| लक्षण | संभावित कारण | समाधान |
|---------|--------------|-----|
| `OutOfMemoryError` | बहुत बड़ी शीट को बहुत अधिक पंक्तियों प्रति पेज के साथ रेंडर करना | `countRowsPerPage` कम करें या JVM हीप बढ़ाएँ |
| खाली आउटपुट फ़ाइलें | गलत फ़ाइल पाथ या लिखने की अनुमति नहीं है | `outputDirectory` मौजूद है और लिखने योग्य है, यह सत्यापित करें |
| HTML संसाधन लोड नहीं हो रहे हैं | `forEmbeddedResources` का उपयोग कर रहे हैं लेकिन फ़ाइलें अलग बेस URL से सर्व कर रहे हैं | पूरी आउटपुट फ़ोल्डर सर्व करें या `forExternalResources` पर स्विच करें |

## अक्सर पूछे जाने वाले प्रश्न

**प्रश्न: क्या मैं HTML के बजाय PDF जनरेट कर सकता हूँ?**  
A: हाँ। `HtmlViewOptions` को `PdfViewOptions` से बदलें और वही `SpreadsheetOptions` कॉन्फ़िगरेशन रखें।

**प्रश्न: क्या स्थिर पंक्तियों/स्तंभों के बजाय सेल कंटेंट के आधार पर विभाजन संभव है?**  
A: सीधे कंटेंट‑आधारित विभाजन GroupDocs Viewer में नहीं है, लेकिन आप रेंडरिंग से पहले Apache POI से वर्कबुक को प्रोसेस करके अलग शीट्स बना सकते हैं।

**प्रश्न: क्या GroupDocs Viewer पुराने Excel फ़ॉर्मेट (XLS) को सपोर्ट करता है?**  
A: बिल्कुल। Viewer XLS, XLSX, CSV और अन्य स्प्रेडशीट फ़ॉर्मेट को संभालता है।

**प्रश्न: उत्पन्न HTML को Spring MVC व्यू में कैसे एम्बेड करूँ?**  
A: आउटपुट फ़ोल्डर को स्थैतिक रिसोर्स के रूप में सर्व करें और अपने Thymeleaf या JSP टेम्पलेट्स से उत्पन्न `page_0.html`, `page_1.html` आदि को रेफ़र करें।

**प्रश्न: व्यावसायिक डिप्लॉयमेंट के लिए कौन सा लाइसेंस चाहिए?**  
A: GroupDocs से पूर्ण प्रोडक्शन लाइसेंस आवश्यक है; ट्रायल लाइसेंस केवल मूल्यांकन के लिए होते हैं।

## संसाधन
- **डॉक्यूमेंटेशन**: [GroupDocs Viewer Java दस्तावेज़](https://docs.groupdocs.com/viewer/java/)
- **API रेफ़रेंस**: [GroupDocs API रेफ़रेंस](https://reference.groupdocs.com/viewer/java/)
- **डाउनलोड**: [GroupDocs Viewer Java रिलीज़](https://releases.groupdocs.com/viewer/java/)
- **खरीद**: [GroupDocs लाइसेंस खरीदें](https://purchase.groupdocs.com/buy)
- **फ़्री ट्रायल**: [GroupDocs फ़्री ट्रायल](https://releases.groupdocs.com/viewer/java/)
- **अस्थायी लाइसेंस**: [अस्थायी लाइसेंस प्राप्त करें](https://purchase.groupdocs.com/temporary-license/)
- **सपोर्ट**: [GroupDocs सपोर्ट फ़ोरम](https://forum.groupdocs.com/c/viewer/9)

---

**अंतिम अपडेट:** 2026-06-15  
**परीक्षित संस्करण:** GroupDocs Viewer 25.2 for Java  
**लेखक:** GroupDocs  

---

## संबंधित ट्यूटोरियल

- [Java स्प्रेडशीट में छिपी पंक्तियों और स्तंभों को रेंडर करना GroupDocs.Viewer का उपयोग करके](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Java में GroupDocs.Viewer का उपयोग करके खाली पंक्तियों को रेंडर न करना: एक प्रदर्शन गाइड](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [व्यापक गाइड: Excel 2003 XML को HTML/JPG/PNG/PDF में बदलना GroupDocs.Viewer Java के साथ](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)