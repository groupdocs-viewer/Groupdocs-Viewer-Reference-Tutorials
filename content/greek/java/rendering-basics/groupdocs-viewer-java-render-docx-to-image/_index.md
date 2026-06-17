---
date: '2026-06-05'
description: Μάθετε πώς να μετατρέψετε docx σε jpeg χρησιμοποιώντας το GroupDocs Viewer
  for Java, καλύπτοντας τη ρύθμιση, τη διαμόρφωση και την πρακτική απόδοση εικόνας.
keywords:
- convert docx to jpeg
- convert word to image
- GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-05'
  description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  headline: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert docx to jpeg using GroupDocs Viewer for Java,
    covering setup, configuration, and practical image rendering.
  name: How to Convert DOCX to JPEG with GroupDocs Viewer for Java
  steps:
  - name: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
    text: '**Preview Generation** – Show document thumbnails in a content‑management
      system without requiring a full‑screen viewer.'
  - name: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
    text: '**Email Attachments** – Embed page‑by‑page JPEGs in emails to avoid attachment
      size limits.'
  - name: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
    text: '**Web Display** – Render pages as images for fast loading on low‑bandwidth
      connections.'
  type: HowTo
- questions:
  - answer: '`DocumentSplitter` allows you to divide a large document into separate
      parts for easier processing. Split the source file into smaller sections using
      `DocumentSplitter` before rendering, or process pages in sequential batches
      to keep memory usage low.'
    question: How do I handle documents larger than 500 pages?
  - answer: Yes, replace `JpgViewOptions` with `PngViewOptions` and adjust the file‑path
      pattern accordingly.
    question: Can I output PNG instead of JPEG?
  - answer: A free trial license works for evaluation and development, but a commercial
      license is required for production deployments.
    question: Is a license mandatory for development builds?
  - answer: Absolutely. Pass the password to the `Viewer` constructor to unlock the
      document before rendering.
    question: Does the library support password‑protected DOCX files?
  - answer: GroupDocs.Viewer for Java is compatible with Java 8, 11, and 17.
    question: What Java versions are supported?
  type: FAQPage
title: Πώς να μετατρέψετε DOCX σε JPEG με το GroupDocs Viewer for Java
type: docs
url: /el/java/rendering-basics/groupdocs-viewer-java-render-docx-to-image/
weight: 1
---

# Μετατροπή DOCX σε JPEG με GroupDocs Viewer για Java

Η μετατροπή **DOCX σε JPEG** σας επιτρέπει να μοιράζεστε τις σελίδες του εγγράφου ως ελαφριές εικόνες που εμφανίζονται σταθερά σε προγράμματα περιήγησης και πελάτες email. Σε αυτόν τον οδηγό θα δείτε πώς να χρησιμοποιήσετε το **GroupDocs.Viewer for Java** για να μετατρέψετε ένα αρχείο Word σε εικόνες JPEG υψηλής ποιότητας, να προσαρμόσετε τις διαστάσεις και να διαχειριστείτε τους πόρους αποδοτικά.

![Απόδοση DOCX σε Εικόνα με GroupDocs.Viewer for Java](/viewer/rendering-basics/render-docx-to-image.png)

[Απόδοση DOCX σε Εικόνα με GroupDocs.Viewer for Java](/viewer/rendering-basics/render-docx-to-image.png)

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή DOCX → JPEG;** GroupDocs.Viewer for Java.  
- **Πόσες γραμμές κώδικα απαιτούνται;** Μόνο δύο γραμμές για τη φόρτωση και την απόδοση του αρχείου.  
- **Μπορώ να ορίσω προσαρμοσμένο μέγεθος εικόνας;** Ναι, μέσω του `JpgViewOptions` μπορείτε να ορίσετε πλάτος και ύψος.  
- **Απαιτείται άδεια για παραγωγή;** Απαιτείται εμπορική άδεια· διατίθεται δωρεάν δοκιμή.  
- **Λειτουργεί με μεγάλα έγγραφα;** Ναι, επεξεργάζεται αρχεία έως 500 σελίδες ενώ διατηρεί τη χρήση μνήμης κάτω από 200 MB.

## Τι είναι η “μετατροπή docx σε jpeg”;
Η μετατροπή ενός αρχείου DOCX σε JPEG δημιουργεί μία εικόνα ανά σελίδα, διατηρώντας την αρχική διάταξη, τις γραμματοσειρές και τα γραφικά. Κάθε JPEG μπορεί να εμφανιστεί σε προγράμματα περιήγησης, να ενσωματωθεί σε email ή να χρησιμοποιηθεί ως μικρογραφία. Αυτή η μορφή είναι ελαφριά, ευρέως υποστηριζόμενη και ιδανική για προεπισκόπηση εγγράφων χωρίς την ανάγκη του Microsoft Word ή πρόσθετων προσθέτων.

## Γιατί να χρησιμοποιήσετε το GroupDocs Viewer για Java για αυτή τη μετατροπή;
Το GroupDocs.Viewer υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου** και μπορεί να αποδίδει έγγραφα έως **500 σελίδες** σε λιγότερο από **2 δευτερόλεπτα ανά σελίδα** σε τυπικό εξοπλισμό διακομιστή. Το API λειτουργεί χωρίς εγκατεστημένο Microsoft Office, εξασφαλίζοντας σταθερή διατήρηση της διάταξης και χαμηλή κατανάλωση μνήμης.

## Προαπαιτούμενα
- **Java Development Kit** 8 ή νεότερο.  
- **Maven** για διαχείριση εξαρτήσεων (ή χειροκίνητη προσθήκη JAR).  
- **GroupDocs.Viewer for Java** βιβλιοθήκη (διαθέσιμη για λήψη από την επίσημη ιστοσελίδα).  
- Βασική εξοικείωση με τη δομή έργου Java.

## Ρύθμιση του GroupDocs Viewer για Java

Για να προσθέσετε τη βιβλιοθήκη σε ένα έργο Maven, εισάγετε την ακόλουθη εξάρτηση στο `pom.xml` σας:

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

### Απόκτηση Άδειας
Η GroupDocs προσφέρει δωρεάν δοκιμή για εξερεύνηση λειτουργιών. Για εκτεταμένη χρήση, αποκτήστε προσωρινή ή αγορασμένη άδεια μέσω της επίσημης ιστοσελίδας τους.

## Πώς να Μετατρέψετε DOCX σε JPEG;

Η κλάση `Viewer` διαβάζει ένα έγγραφο και παρέχει δυνατότητες απόδοσης.  
`JpgViewOptions` ρυθμίζει τις ρυθμίσεις εξόδου JPEG όπως μέγεθος, ποιότητα και ονομασία αρχείου.

Για να μετατρέψετε, δημιουργήστε ένα αντικείμενο `Viewer` με τη διαδρομή του DOCX, δημιουργήστε `JpgViewOptions` που δείχνει σε φάκελο εξόδου, προαιρετικά ορίστε διαστάσεις και ποιότητα, και καλέστε `viewer.view(options)`. Η βιβλιοθήκη επεξεργάζεται κάθε σελίδα και αποθηκεύει ένα αρχείο JPEG ακολουθώντας το καθορισμένο μοτίβο ονομασίας.

## Οδηγός Υλοποίησης

### Απόδοση DOCX σε JPEG

Μετατρέψτε ένα έγγραφο Word σε εικόνες JPEG για σκοπούς προεπισκόπησης ή κοινής χρήσης.

#### Υλοποίηση Βήμα‑βήμα

**1. Ρύθμιση Φακέλου Εξόδου**  
Ορίστε το φάκελο όπου θα αποθηκευτούν τα αποδοθέντα JPEG:

```java
import com.groupdocs.viewer.Viewer;

public class DocumentRenderer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
            // Configuration and rendering logic goes here
        }
    }
}
```

**2. Καθορισμός Μορφής Διαδρομής Αρχείου**  
Δημιουργήστε ένα μοτίβο ονομασίας που περιλαμβάνει τον αριθμό σελίδας, π.χ., `page_{0}.jpg`:

```java
import java.nio.file.Path;

// Define output directory using Path API
Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("rendered_document");
```

**3. Διαμόρφωση Επιλογών Εικόνας**  
`JpgViewOptions` σας επιτρέπει να ορίσετε πλάτος, ύψος και ποιότητα. Για παράδειγμα, 1024 × 768 εικονοστοιχεία με ποιότητα 90 %:

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.jpg");
```

**4. Απόδοση του Εγγράφου**  
Χρησιμοποιήστε ένα μπλοκ try‑with‑resources για να διασφαλίσετε ότι το αντικείμενο `Viewer` κλείνει αυτόματα, απελευθερώνοντας τους εγγενείς πόρους και αποτρέποντας διαρροές μνήμης:

```java
import com.groupdocs.viewer.options.JpgViewOptions;

// Create JpgViewOptions with specified path format
JpgViewOptions viewOptions = new JpgViewOptions(pageFilePathFormat);

// Set custom width and height for each image
viewOptions.setWidth(600);  // Image width in pixels
viewOptions.setHeight(800); // Image height in pixels
```

### Κοινά Προβλήματα και Λύσεις
- **Προβλήματα Διαδρομής Αρχείου** – Επαληθεύστε ότι ο φάκελος εξόδου υπάρχει και η εφαρμογή έχει δικαιώματα εγγραφής.  
- **Διαχείριση Μνήμης** – Για έγγραφα μεγαλύτερα από 300 σελίδες, εξετάστε την επεξεργασία σελίδων σε παρτίδες και την κλήση `System.gc()` μετά από κάθε παρτίδα.  
- **Μη Υποστηριζόμενα Στοιχεία** – Ορισμένα προχωρημένα χαρακτηριστικά του Word (π.χ., ενσωματωμένες μακροεντολές) αγνοούνται κατά την απόδοση· δεν επηρεάζουν την οπτική έξοδο.

## Πρακτικές Εφαρμογές

1. **Δημιουργία Προεπισκόπησης** – Εμφανίστε μικρογραφίες εγγράφων σε σύστημα διαχείρισης περιεχομένου χωρίς την ανάγκη πλήρους προβολέα.  
2. **Συνημμένα Email** – Ενσωματώστε JPEG ανά σελίδα σε email για να αποφύγετε τα όρια μεγέθους συνημμένων.  
3. **Εμφάνιση στο Web** – Αποδώστε σελίδες ως εικόνες για γρήγορη φόρτωση σε συνδέσεις χαμηλού εύρους ζώνης.

## Παράγοντες Απόδοσης

- **Διαχείριση Πόρων** – Χρησιμοποιείτε πάντα try‑with‑resources για να κλείσετε το `Viewer`.  
- **Διαστάσεις Εικόνας** – Μικρότερες διαστάσεις μειώνουν τη χρήση RAM· επιλέξτε το μικρότερο μέγεθος που ικανοποιεί τις απαιτήσεις ποιότητας.  
- **Ασύγχρονη Επεξεργασία** – Για μαζικές μετατροπές, εκτελέστε εργασίες απόδοσης σε ξεχωριστό thread pool για να διατηρήσετε το UI ανταποκρινόμενο.

## Συχνές Ερωτήσεις

**Q: Πώς διαχειρίζομαι έγγραφα μεγαλύτερα από 500 σελίδες;**  
A: Το `DocumentSplitter` σας επιτρέπει να χωρίσετε ένα μεγάλο έγγραφο σε ξεχωριστά τμήματα για ευκολότερη επεξεργασία. Χωρίστε το αρχείο προέλευσης σε μικρότερες ενότητες χρησιμοποιώντας το `DocumentSplitter` πριν από την απόδοση, ή επεξεργαστείτε τις σελίδες σε διαδοχικές παρτίδες για να διατηρήσετε τη χρήση μνήμης χαμηλή.

**Q: Μπορώ να εξάγω PNG αντί για JPEG;**  
A: Ναι, αντικαταστήστε το `JpgViewOptions` με `PngViewOptions` και προσαρμόστε το μοτίβο διαδρομής αρχείου αναλόγως.

**Q: Είναι η άδεια υποχρεωτική για εκδόσεις ανάπτυξης;**  
A: Μια άδεια δοκιμής λειτουργεί για αξιολόγηση και ανάπτυξη, αλλά απαιτείται εμπορική άδεια για παραγωγικές εγκαταστάσεις.

**Q: Υποστηρίζει η βιβλιοθήκη αρχεία DOCX με κωδικό πρόσβασης;**  
A: Απόλυτα. Περνάτε τον κωδικό πρόσβασης στον κατασκευαστή `Viewer` για να ξεκλειδώσετε το έγγραφο πριν από την απόδοση.

**Q: Ποιες εκδόσεις Java υποστηρίζονται;**  
A: Το GroupDocs.Viewer for Java είναι συμβατό με Java 8, 11 και 17.

## Πόροι

- **Τεκμηρίωση**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Αναφορά API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Σελίδα Λήψης**: [Download Page](https://releases.groupdocs.com/viewer/java/)
- **Αγορά Άδειας**: [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Δοκιμή Δωρεάν**: [Try GroupDocs for Free](https://releases.groupdocs.com/viewer/java/)
- **Λήψη Προσωρινής Άδειας**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Φόρουμ Υποστήριξης**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία Ενημέρωση:** 2026-06-05  
**Δοκιμάστηκε Με:** GroupDocs.Viewer 23.12 for Java  
**Συγγραφέας:** GroupDocs

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);
}
```

## Σχετικά Μαθήματα

- [Πώς να Μετατρέψετε Αρχεία DOCX σε PNG Χρησιμοποιώντας το GroupDocs.Viewer για Java](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)
- [Πώς να Μετατρέψετε DOCX σε HTML Χρησιμοποιώντας το GroupDocs.Viewer για Java: Οδηγός Βήμα‑Βήμα](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)
- [Απόδοση Αρχείων DOCX από InputStream σε Java χρησιμοποιώντας το GroupDocs.Viewer](/viewer/java/rendering-basics/render-docx-from-inputstream-groupdocs-viewer-java/)