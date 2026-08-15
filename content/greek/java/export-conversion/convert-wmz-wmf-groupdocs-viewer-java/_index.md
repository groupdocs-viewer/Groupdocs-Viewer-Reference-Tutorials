---
date: '2026-07-19'
description: Μάθετε πώς να μετατρέψετε WMZ σε PDF, HTML, JPG και PNG με GroupDocs
  Viewer for Java. Οδηγός βήμα προς βήμα για java μετατροπή διανυσματικών γραφικών.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Μετατρέψτε WMZ σε PDF, HTML, JPG και PNG χρησιμοποιώντας το GroupDocs
  Viewer for Java. Αυτό το σεμινάριο δείχνει βήμα‑βήμα java μετατροπή διανυσματικών
  γραφικών με υψηλή πιστότητα.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Μετατροπή WMZ σε PDF με GroupDocs Viewer for Java – Σύντομος Οδηγός
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Μετατροπή WMZ σε PDF και άλλα μορφότυπα με GroupDocs Viewer for Java
type: docs
url: /el/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Μετατροπή WMZ σε PDF και άλλες μορφές χρησιμοποιώντας το GroupDocs Viewer για Java

Η μετατροπή αρχείων WMZ (Web Metafile) και WMF (Windows Metafile) σε πιο προσβάσιμες μορφές—ιδιαίτερα **convert WMZ to PDF**—μπορεί να είναι δύσκολη επειδή αυτές οι μορφές διανυσματικών γραφικών αποθηκεύουν οδηγίες σχεδίασης αντί για δεδομένα εικονοστοιχείων. Με το **GroupDocs Viewer for Java**, μπορείτε να αποδώσετε έγγραφα WMZ/WMF σε HTML, JPG, PNG, **PDF**, και άλλες δημοφιλείς μορφές με λίγες μόνο γραμμές κώδικα, διατηρώντας ταυτόχρονα την αρχική οπτική πιστότητα.

![Μετατροπή εγγράφων WMZ/WMF με το GroupDocs.Viewer για Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Μετατροπή εγγράφων WMZ/WMF με το GroupDocs.Viewer για Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Γρήγορες Απαντήσεις
- **Σε ποιες μορφές μπορεί να μετατραπεί το WMZ/WMF;** HTML, JPG, PNG και PDF υποστηρίζονται πλήρως.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· μια εμπορική άδεια αφαιρεί τα όρια αξιολόγησης.  
- **Ποια έκδοση της Java απαιτείται;** Συνιστάται Java 8 ή νεότερη.  
- **Μπορώ να αποδώσω μόνο συγκεκριμένες σελίδες;** Ναι, μπορείτε να καθορίσετε περιοχές σελίδων στις επιλογές προβολής.  
- **Ανησυχεί η χρήση μνήμης για μεγάλα αρχεία;** Χρησιμοποιήστε try‑with‑resources και αποδώστε μόνο τις απαραίτητες σελίδες για να διατηρήσετε τη μνήμη χαμηλή.

## Τι είναι το “convert WMZ to PDF”;
**Convert WMZ to PDF** σημαίνει τη λήψη ενός διανυσματικού αρχείου WMZ και την ενσωμάτωση των οδηγιών σχεδίασής του μέσα σε ένα δοχείο PDF, παράγοντας ένα καθολικά προβληματικό, αναζητήσιμο και εκτυπώσιμο έγγραφο. Η μετατροπή διατηρεί την ποιότητα των γραμμών και των σχημάτων, ώστε το παραγόμενο PDF να φαίνεται ταυτόσημο με το αρχικό γραφικό σε οποιαδήποτε συσκευή.

## Γιατί να χρησιμοποιήσετε το GroupDocs Viewer για Java για τη μετατροπή διανυσματικών γραφικών;
Το GroupDocs Viewer για Java διαχειρίζεται την απόδοση WMZ και WMF με **υψηλή πιστότητα**, διατηρώντας τις διανυσματικές λεπτομέρειες είτε εξάγετε σε PDF, PNG ή HTML. Η βιβλιοθήκη λειτουργεί σε οποιαδήποτε πλατφόρμα με JDK, δεν απαιτεί εγγενή στοιχεία των Windows και παρέχει ένα API μονής κλήσης που κλιμακώνεται από αρχεία με ένα εικονίδιο έως πολυσελιδείς τεχνικές σχεδιάσεις. Σε δοκιμές απόδοσης, επεξεργάζεται **αρχεία WMZ άνω των 200 σελίδων σε λιγότερο από 12 δευτερόλεπτα** σε έναν τυπικό διακομιστή 4‑πυρήνων.

## Προαπαιτούμενα

- **GroupDocs.Viewer for Java** – βασική μηχανή απόδοσης.  
- Java Development Kit (JDK) 8 ή νεότερο.  
- Ένα IDE όπως IntelliJ IDEA ή Eclipse (προαιρετικό αλλά συνιστάται).  
- Maven (ή Gradle) για διαχείριση εξαρτήσεων.  

Η εξοικείωση με το Java NIO (`java.nio.file.Path`) και τις βασικές λειτουργίες αρχείων I/O θα σας βοηθήσει να ακολουθήσετε τα παραδείγματα ομαλά.

## Ρύθμιση του GroupDocs.Viewer για Java

Η κλάση `Viewer` είναι το σημείο εισόδου για όλες τις λειτουργίες απόδοσης. Αντιπροσωπεύει μια μηχανή ασφαλή ως προς τα νήματα που μπορεί να επαναχρησιμοποιηθεί σε πολλαπλές μετατροπές.

Προσθέστε το αποθετήριο και την εξάρτηση στο `pom.xml` σας (ή το αντίστοιχο Gradle). Μετά την επίλυση του artefact από το Maven, μπορείτε να δημιουργήσετε μια παρουσία `Viewer` που θα επαναχρησιμοποιείται για κάθε βήμα μετατροπής.

> **Συμβουλή άδειας:** Χρησιμοποιήστε μια δωρεάν δοκιμή για αξιολόγηση, στη συνέχεια εφαρμόστε προσωρινή ή αγορασμένη άδεια για να ξεκλειδώσετε πλήρη λειτουργικότητα.

## Οδηγός Υλοποίησης

Παρακάτω περπατάμε μέσα από τέσσερα σενάρια μετατροπής—HTML, JPG, PNG και PDF. Κάθε σενάριο ακολουθεί το ίδιο μοτίβο τριών βημάτων:

1. **Ορίστε τον φάκελο εξόδου** όπου θα αποθηκευτούν τα αποδοθέντα αρχεία.  
2. **Δημιουργήστε μια παρουσία `Viewer`** που δείχνει στο πηγαίο αρχείο WMZ/WMF.  
3. **Διαμορφώστε τις επιλογές προβολής ειδικές για τη μορφή** και καλέστε τη μέθοδο `view`.  

Η μέθοδος `view` εκτελεί την απόδοση βάσει των παρεχόμενων επιλογών.

### Απόδοση WMZ/WMF σε HTML

#### Επισκόπηση
Η έξοδος HTML σας επιτρέπει να ενσωματώσετε το γραφικό απευθείας σε ιστοσελίδες, με όλους τους πόρους (εικόνες, CSS) να περιέχονται σε ένα μόνο αρχείο.

**Βήμα 1: Ορίστε τη Διαδρομή του Φακέλου Εξόδου**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Βήμα 2: Αρχικοποιήστε το Viewer και αποδώστε σε HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Απόδοση WMZ/WMF σε JPG

#### Επισκόπηση
Το JPG είναι μια ευρέως υποστηριζόμενη μορφή raster, ιδανική για γρήγορες προεπισκοπήσεις ή συνημμένα email.

**Βήμα 1: Ορίστε τη Διαδρομή του Φακέλου Εξόδου**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Βήμα 2: Αρχικοποιήστε το Viewer και αποδώστε σε JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Απόδοση WMZ/WMF σε PNG

#### Επισκόπηση
Το PNG υποστηρίζει διαφάνεια, καθιστώντας το ιδανικό για γραφικά που χρειάζεται να ενσωματωθούν με διαφορετικά υπόβαθρα.

**Βήμα 1: Ορίστε τη Διαδρομή του Φακέλου Εξόδου**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Βήμα 2: Αρχικοποιήστε το Viewer και αποδώστε σε PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Απόδοση WMZ/WMF σε PDF

#### Επισκόπηση
Το PDF παρέχει ένα ανεξάρτητο από πλατφόρμα, αναζητήσιμο έγγραφο που διατηρεί την αρχική διάταξη.

**Βήμα 1: Ορίστε τη Διαδρομή του Φακέλου Εξόδου**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Βήμα 2: Αρχικοποιήστε το Viewer και αποδώστε σε PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Συχνά Προβλήματα και Λύσεις

`PageStreamViewOptions` επιτρέπει την απόδοση συγκεκριμένων σελίδων ως ροές.  
`PdfViewOptions` διαμορφώνει τις ρυθμίσεις εξόδου PDF όπως περιοχή σελίδων και DPI.  
`FontSettings` σας επιτρέπει να παρέχετε προσαρμοσμένες γραμματοσειρές όταν το πηγαίο έγγραφο αναφέρει ελλείπουσες γραμματοσειρές.

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **OutOfMemoryError** σε μεγάλα αρχεία WMZ | Το Viewer φορτώνει ολόκληρο το έγγραφο στη μνήμη | Αποδώστε μία σελίδα τη φορά χρησιμοποιώντας `PageStreamViewOptions` ή αυξήστε το heap της JVM (`-Xmx`). |
| **Missing fonts** σε PDF | Η γραμματοσειρά δεν είναι ενσωματωμένη στο πηγαίο WMZ | Εγκαταστήστε τις απαιτούμενες γραμματοσειρές στο σύστημα ή χρησιμοποιήστε `FontSettings` για να παρέχετε προσαρμοσμένες γραμματοσειρές. |
| **Blank PNG output** | Λανθασμένη διαδρομή εξόδου ή ανεπαρκή δικαιώματα εγγραφής | Επαληθεύστε ότι το `outputDirectory` υπάρχει και η εφαρμογή έχει δικαίωμα εγγραφής. |
| **HTML resources not loading** | Χρήση `forExternalResources` χωρίς αντιγραφή αρχείων | Μείνετε με `forEmbeddedResources` για ένα αυτόνομο αρχείο HTML. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να μετατρέψω WMF σε PNG χρησιμοποιώντας τον ίδιο κώδικα;**  
Α: Ναι. Το παράδειγμα PNG λειτουργεί και για αρχεία WMZ και WMF· απλώς αντικαταστήστε το `TestFiles.SAMPLE_WMZ` με την πηγή WMF σας.

**Ε: Είναι δυνατόν να μετατρέψω μόνο ένα υποσύνολο σελίδων;**  
Α: Απόλυτα. Χρησιμοποιήστε `PdfViewOptions` (ή τις αντίστοιχες επιλογές για άλλες μορφές) και καλέστε `setPageNumbers(List<Integer>)` πριν από την απόδοση.

**Ε: Χρειάζομαι ξεχωριστή άδεια για κάθε μορφή εξόδου;**  
Α: Όχι. Μία άδεια GroupDocs Viewer καλύπτει όλες τις υποστηριζόμενες μορφές, συμπεριλαμβανομένων HTML, JPG, PNG και PDF.

**Ε: Πώς επηρεάζει η “java convert vector graphics” την απόδοση;**  
Α: Η μετατροπή διανυσματικού σε raster είναι απαιτητική για την CPU. Για μεγάλες παρτίδες, σκεφτείτε πολυνηματισμό και επαναχρησιμοποίηση μιας μοναδικής παρουσίασης `Viewer` σε πολλά αρχεία.

**Ε: Θα διατηρήσει το PDF την ποιότητα του διανύσματος ή θα είναι rasterized;**  
Α: Κατά τη μετατροπή WMZ/WMF σε PDF, το GroupDocs Viewer διατηρεί τις διανυσματικές οδηγίες όπου είναι δυνατόν, παράγοντας ένα κλιμακώσιμο PDF.

## Συμπέρασμα

Τώρα έχετε έναν πλήρη, έτοιμο για παραγωγή οδηγό για **convert WMZ to PDF** και άλλες κοινές μορφές χρησιμοποιώντας το **GroupDocs Viewer για Java**. Είτε δημιουργείτε μια υπηρεσία web που εξυπηρετεί γραφικά σε πραγματικό χρόνο είτε ένα εργαλείο αρχειοθέτησης που αποθηκεύει έγγραφα ως PDF, τα παραπάνω βήματα θα σας βοηθήσουν να το πετύχετε γρήγορα και αξιόπιστα. Εξερευνήστε περαιτέρω το API για να προσαρμόσετε περιοχές σελίδων, ρυθμίσεις DPI ή υδατογράφημα όπως απαιτεί το έργο σας.

---

**Τελευταία Ενημέρωση:** 2026-07-19  
**Δοκιμάστηκε Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

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

## Σχετικά Μαθήματα

- [Πώς να Μετατρέψετε OBJ σε HTML, JPG, PNG και PDF σε Java Χρησιμοποιώντας το GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Μετατροπή IGS σε PDF, HTML, JPG & PNG χρησιμοποιώντας το GroupDocs Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Μετατροπή Εγγράφων σε PDF – Πλήρης Οδηγός](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)