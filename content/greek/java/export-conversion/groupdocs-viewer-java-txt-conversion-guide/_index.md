---
date: '2026-02-21'
description: Μάθετε πώς να χρησιμοποιείτε το GroupDocs Viewer Maven για να μετατρέψετε
  αρχεία txt σε html, jpg, png και pdf σε Java. Περιλαμβάνει βήματα για μετατροπή
  txt σε pdf σε Java και για πολυσελιδικό html σε Java.
keywords:
- GroupDocs.Viewer for Java
- convert TXT to HTML
- render TXT as JPG/PNG
title: 'groupdocs viewer maven: Μετατροπή TXT σε HTML, JPG, PNG, PDF'
type: docs
url: /el/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/
weight: 1
---

 formatting preserved.

Now produce final content.# groupdocs viewer maven: Μετατροπή Αρχείων TXT σε HTML, JPG, PNG και PDF Χρησιμοποιώντας το GroupDocs.Viewer για Java

Σε σύγχρονες εφαρμογές Java, το **groupdocs viewer maven** καθιστά εύκολη τη μετατροπή εγγράφων plain‑text (TXT) σε έτοιμο για το web HTML, εικόνες υψηλής ανάλυσης ή φορητά αρχεία PDF. Είτε δημιουργείτε μια πύλη εγγράφων, μια υπηρεσία αρχειοθέτησης ή μια λειτουργία προεπισκόπησης, η μετατροπή αρχείων TXT με το GroupDocs.Viewer σας εξοικονομεί χρόνο και εξαλείφει την ανάγκη για προσαρμοσμένους αναλυτές. Σε αυτόν τον οδηγό θα περάσουμε από τη πλήρη ρύθμιση και θα σας δείξουμε πώς να **convert txt files java** σε HTML (μονή‑ και πολλαπλή‑σελίδα), JPG, PNG και PDF.

![Μετατροπή αρχείων TXT σε HTML, JPG, PNG και PDF με το GroupDocs.Viewer για Java](/viewer/export-conversion/convert-txt-files-to-html-jpg-png-and-pdf-java.png)

## Quick Answers
- **Ποιο Maven artifact χρειάζομαι;** `com.groupdocs:groupdocs-viewer` (δείτε το Maven snippet παρακάτω).  
- **Μπορώ να αποδώσω HTML πολλαπλών σελίδων;** Ναι – χρησιμοποιήστε `HtmlViewOptions.forEmbeddedResources` χωρίς τη σημαία μονής σελίδας.  
- **Απαιτείται άδεια για παραγωγή;** Μια δοκιμαστική άδεια λειτουργεί για αξιολόγηση· απαιτείται μόνιμη άδεια για εμπορική χρήση.  
- **Ποια έκδοση Java υποστηρίζεται;** Java 8 ή νεότερη (συστήνεται Java 11+).  
- **Χρειάζομαι επιπλέον βιβλιοθήκες για έξοδο εικόνας;** Όχι, η βιβλιοθήκη Viewer περιλαμβάνει υποστήριξη JPG και PNG από το κουτί.

## What is groupdocs viewer maven?
**groupdocs viewer maven** είναι η διανομή βασισμένη σε Maven της βιβλιοθήκης GroupDocs.Viewer για Java. Παρέχει ένα απλό API για απόδοση πάνω από 100 μορφών εγγράφων—συμπεριλαμβανομένου του plain‑text—σε HTML, εικόνες ή PDF χωρίς την ανάγκη Microsoft Office ή άλλων εργαλείων τρίτων.

## Why convert txt files java?
- **Προεπισκόπηση πολλαπλών πλατφορμών** – HTML και εικόνες μπορούν να εμφανιστούν σε προγράμματα περιήγησης ή κινητές εφαρμογές.  
- **Τυποποιημένη αρχειοθέτηση** – PDF διατηρεί τη μορφοποίηση και είναι καθολικά αναγνώσιμο.  
- **Φιλική προς την αυτοματοποίηση** – Ενσωματώστε τη μετατροπή σε εργασίες batch, υπηρεσίες cloud ή pipelines CI.  

## Prerequisites

- **GroupDocs.Viewer for Java** έκδοση 25.2 ή νεότερη (παρέχεται μέσω Maven).  
- JDK 8 + (Java 11 + συνιστάται).  
- Ένα IDE όπως IntelliJ IDEA, Eclipse ή NetBeans.  
- Βασικές γνώσεις Java και Maven.  

## Setting Up GroupDocs.Viewer for Java

Add the repository and dependency to your `pom.xml`:

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

### License Acquisition Steps
- Ξεκινήστε με μια **δωρεάν δοκιμή** ή αποκτήστε μια **προσωρινή άδεια** για να εξερευνήσετε όλες τις δυνατότητες.  
- Για παραγωγή, αγοράστε άδεια μέσω της επίσημης [σελίδας αγοράς](https://purchase.groupdocs.com/buy).  

### Basic Initialization and Setup
1. Προσθέστε την εξάρτηση Maven που φαίνεται παραπάνω.  
2. Βεβαιωθείτε ότι το JDK και το IDE σας είναι σωστά ρυθμισμένα.  

Τώρα ας βουτήξουμε στις συγκεκριμένες περιπτώσεις μετατροπής.

## Implementation Guide

### Feature 1: Render TXT to Multi‑page HTML *(multi page html java)*

#### Overview
Αυτό το παράδειγμα μετατρέπει ένα έγγραφο TXT σε αρχείο **HTML πολλαπλών σελίδων**, διατηρώντας τις αλλαγές γραμμής σε ξεχωριστές ιστοσελίδες.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering with embedded resources
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Render the document to HTML using these options
    viewer.view(options);
}
```

*Explanation:* `HtmlViewOptions.forEmbeddedResources` ενσωματώνει CSS, γραμματοσειρές και εικόνες απευθείας στην έξοδο HTML, καθιστώντας την φορητή.

### Feature 2: Render TXT to Single‑page HTML *(convert txt to html java)*

#### Overview
Συμπιέστε ολόκληρο το αρχείο κειμένου σε μία μόνο σελίδα HTML — ιδανικό για γρήγορες προεπισκοπήσεις.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // Configure options for rendering with embedded resources
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Set the option to render as a single page HTML
    options.setRenderToSinglePage(true);
    
    // Render the document using these options
    viewer.view(options);
}
```

*Explanation:* `setRenderToSinglePage(true)` συγχωνεύει όλες τις σελίδες σε ένα αρχείο HTML.

### Feature 3: Render TXT to JPG

#### Overview
Μετατρέψτε ένα αρχείο TXT σε εικόνα JPEG υψηλής ποιότητας, χρήσιμη για κοινή χρήση σε πλατφόρμες που δέχονται μόνο εικόνες.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a JPEG image
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // Render the document as a JPG using these options
    viewer.view(options);
}
```

*Explanation:* `JpgViewOptions` σας επιτρέπει να ελέγχετε την ποιότητα της εικόνας, το DPI και τη διαδρομή εξόδου.

### Feature 4: Render TXT to PNG

#### Overview
Δημιουργήστε εικόνες PNG χωρίς απώλειες από αρχεία κειμένου — ιδανικό όταν χρειάζεστε καθαρά, κλιμακώσιμα γραφικά.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a PNG image
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // Render the document as a PNG using these options
    viewer.view(options);
}
```

*Explanation:* Το PNG παρέχει συμπίεση χωρίς απώλειες, διατηρώντας την ακριβή εμφάνιση του αρχικού κειμένου.

### Feature 5: Render TXT to PDF *(txt to pdf java / convert txt to pdf java)*

#### Overview
Δημιουργήστε ένα αρχείο PDF από ένα έγγραφο TXT — ιδανικό για αρχειοθέτηση, εκτύπωση ή αποστολή σε πελάτες.

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a PDF
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // Render the document as a PDF using these options
    viewer.view(options);
}
```

*Explanation:* `PdfViewOptions` διαχειρίζεται αυτόματα τη διάταξη σελίδων, τις γραμματοσειρές και την ενσωμάτωση πόρων.

## Practical Applications

1. **Συστήματα Διαχείρισης Εγγράφων:** Αυτοματοποιήστε τη μετατροπή παλαιών εγγράφων TXT σε HTML για εσωτερικές πύλες.  
2. **Πλατφόρμες Δημοσίευσης:** Μετατρέψτε χειρόγραφα TXT που υποβάλλονται από συγγραφείς σε HTML για απρόσκοπτη ενσωμάτωση CMS.  
3. **Λύσεις Αρχειοθέτησης:** Διατηρήστε παλιά αρχεία κειμένου ως PDF ή PNG για μακροπρόθεσμη αποθήκευση.  
4. **Ενσωμάτωση με Cloud Storage:** Μετατρέψτε άμεσα και αποθηκεύστε τα παραγόμενα αρχεία σε AWS S3, Azure Blob ή Google Cloud.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **Η έξοδος είναι κενή** | Λανθασμένη διαδρομή αρχείου ή έλλειψη δικαιωμάτων ανάγνωσης. | Επαληθεύστε ότι το `YOUR_DOCUMENT_DIRECTORY` δείχνει στο πραγματικό αρχείο TXT και ότι η διαδικασία έχει δικαιώματα ανάγνωσης. |
| **Οι εικόνες έχουν χαμηλή ποιότητα** | Το προεπιλεγμένο DPI είναι χαμηλό. | Χρησιμοποιήστε `JpgViewOptions.setResolution(int dpi)` ή `PngViewOptions.setResolution(int dpi)` για να αυξήσετε το DPI (π.χ., 300). |
| **Το HTML περιέχει σπασμένους συνδέσμους** | Οι πόροι δεν είναι ενσωματωμένοι. | Χρησιμοποιήστε `HtmlViewOptions.forEmbeddedResources` ή παρέχετε έναν προσαρμοσμένο φάκελο πόρων. |
| **Εξαίρεση άδειας** | Δεν έχει οριστεί έγκυρη άδεια. | Φορτώστε το αρχείο άδειας με `License license = new License(); license.setLicense("path/to/license.file");` πριν δημιουργήσετε το `Viewer`. |

## Frequently Asked Questions

**Μ: Μπορώ να μετατρέψω μεγάλα αρχεία TXT (εκατοντάδες MB) με το GroupDocs.Viewer;**  
Α: Ναι. Η βιβλιοθήκη κάνει streaming του αρχείου προέλευσης, αλλά ίσως χρειαστεί να αυξήσετε το μέγεθος heap της JVM για πολύ μεγάλα έγγραφα.

**Μ: Χρειάζομαι επιπλέον εξαρτήσεις για τη δημιουργία JPG ή PNG;**  
Α: Όχι. Το πακέτο Viewer περιλαμβάνει όλες τις απαιτούμενες βιβλιοθήκες επεξεργασίας εικόνας.

**Μ: Είναι δυνατόν να προσαρμόσω το μέγεθος σελίδας PDF;**  
Α: Απόλυτα. Χρησιμοποιήστε `PdfViewOptions.setPageSize(PageSize.A4)` ή οποιοδήποτε άλλο `PageSize` πριν από τη δημιουργία.

**Μ: Πώς διαχειρίζομαι αρχεία TXT με κωδικό πρόσβασης;**  
Α: Τα αρχεία TXT δεν υποστηρίζουν κωδικούς πρόσβασης. Εάν το αρχείο είναι κρυπτογραφημένο, αποκρυπτογραφήστε το πρώτα πριν το περάσετε στο Viewer.

**Μ: Μπορώ να εκτελέσω αυτή τη μετατροπή σε κοντέινερ Docker;**  
Α: Ναι. Απλώς συμπεριλάβετε το JDK, αντιγράψτε το `pom.xml` σας με την εξάρτηση GroupDocs, και εκτελέστε την εφαρμογή Java μέσα στο κοντέινερ.

---

**Last Updated:** 2026-02-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs