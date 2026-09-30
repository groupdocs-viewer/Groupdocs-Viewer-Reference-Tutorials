---
date: '2026-09-30'
description: Μάθετε πώς να περιστρέφετε μια σελίδα 90 μοιρών σε Java χρησιμοποιώντας
  το GroupDocs Viewer, συμπεριλαμβανομένης της εγκατάστασης, του κώδικα και των συμβουλών
  απόδοσης.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Περιστρέψτε μια σελίδα 90 μοιρών σε Java χρησιμοποιώντας το GroupDocs
  Viewer. Οδηγός βήμα‑βήμα, συμβουλές απόδοσης και πραγματικές περιπτώσεις χρήσης
  για προγραμματιστές.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Περιστροφή σελίδας 90 μοιρών με το GroupDocs Viewer για Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Περιστροφή σελίδας 90 μοιρών με το GroupDocs Viewer για Java
type: docs
url: /el/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Περιστροφή σελίδας 90 μοιρών με το GroupDocs Viewer για Java

Αν χρειάζεστε **rotate page 90 degrees** σε ένα έγγραφο—είτε είναι PDF, αρχείο Word ή λογιστικό φύλλο—η προγραμματιστική υλοποίηση σε Java εξοικονομεί χρόνο, αφαιρεί τα χειροκίνητα σφάλματα και σας επιτρέπει να ενσωματώσετε τη λειτουργία σε αυτοματοποιημένες διαδικασίες. Σε αυτόν τον προχωρημένο οδηγό θα μάθετε πώς να περιστρέφετε την πρώτη σελίδα οποιουδήποτε υποστηριζόμενου εγγράφου χρησιμοποιώντας **GroupDocs Viewer for Java**, γιατί αυτή η δυνατότητα είναι σημαντική σε πραγματικά έργα, και πώς να διατηρήσετε τη διαδικασία ελαφριά και αποδοτική σε μνήμη.

![Περιστροφή της πρώτης σελίδας ενός εγγράφου με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Γρήγορες απαντήσεις
- **What does “rotate page 90 degrees” mean?** Σημαίνει ότι η επιλεγμένη σελίδα περιστρέφεται δεξιόστροφα κατά ένα τέταρτο γύρο.  
- **Which library handles the rotation?** Το GroupDocs Viewer for Java παρέχει τη μέθοδο `rotatePage`.  
- **Can I rotate PDF pages with Java?** Ναι—χρησιμοποιήστε την ίδια κλήση `rotatePage`; λειτουργεί για PDF, DOCX, XLSX και άλλα.  
- **Do I need a license?** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται πληρωμένη άδεια για παραγωγή.  
- **Is the operation memory‑intensive?** Όχι όταν κλείνετε άμεσα το αντικείμενο `Viewer`; δείτε τις συμβουλές απόδοσης παρακάτω.

## Τι είναι η “περιστροφή σελίδας 90 μοιρών”;
Η περιστροφή μιας σελίδας 90 μοιρών αλλάζει την προσανατολισμό της από πορτραίτο σε τοπίο (ή αντίστροφα) χωρίς να τροποποιεί το περιεχόμενο. Είναι χρήσιμη για παρουσιάσεις, εκτύπωση γραφικών μόνο σε τοπίο ή διόρθωση σαρωμένων εγγράφων που λήφθηκαν πλαγίως. Η περιστροφή εφαρμόζεται κατά το rendering, αφήνοντας το αρχικό αρχείο αμετάβλητο.

## Γιατί να περιστρέφετε σελίδες προγραμματιστικά με το GroupDocs Viewer για Java;
Το GroupDocs Viewer υποστηρίζει **πάνω από 50 μορφές εισόδου και εξόδου**—συμπεριλαμβανομένων PDF, DOCX, PPTX, XLSX και πολλών τύπων εικόνων—ώστε μπορείτε να αποδώσετε οποιοδήποτε έγγραφο χωρίς εξωτερικούς μετατροπείς. Το API είναι fluent, thread‑safe και τρέχει σε οποιοδήποτε runtime Java 8+, καθιστώντας το αξιόπιστη επιλογή για αυτοματισμούς επιχειρησιακού επιπέδου που πρέπει να διαχειρίζονται δεκάδες τύπους αρχείων σταθερά.

## Προαπαιτούμενα

- GroupDocs Viewer for Java (τελευταία έκδοση)
- JDK 8 ή νεότερο
- Maven (ή Gradle) για διαχείριση εξαρτήσεων
- Ένα IDE όπως IntelliJ IDEA ή Eclipse
- Βασική εξοικείωση με Java I/O

## Ρύθμιση του GroupDocs.Viewer για Java

Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση στο `pom.xml`. Αυτό το απόσπασμα παραμένει αμετάβλητο από το αρχικό tutorial:

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

### Απόκτηση άδειας
- **Free trial** – κατεβάστε από τον ιστότοπο GroupDocs.  
- **Temporary license** – ζητήστε αν χρειάζεστε παρατεταμένη περίοδο αξιολόγησης.  
- **Full license** – αγοράστε για παραγωγικές εγκαταστάσεις.

### Βασική αρχικοποίηση Viewer
Η κλάση `Viewer` είναι το σημείο εισόδου που φορτώνει ένα έγγραφο και εκθέτει μεθόδους απόδοσης και μετασχηματισμού. Διατηρήστε τον κώδικα ακριβώς όπως φαίνεται:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Πώς να περιστρέψετε σελίδα PDF με Java χρησιμοποιώντας το GroupDocs Viewer
Φορτώστε το αρχείο-στόχο με το `Viewer`, καθορίστε τον αριθμό σελίδας και καλέστε `rotatePage`. Η μέθοδος λειτουργεί για PDF, DOCX, PPTX, XLSX και οποιαδήποτε άλλη μορφή υποστηρίζεται από τη βιβλιοθήκη. Μετά την περιστροφή, μπορείτε να αποδώσετε το έγγραφο σε νέο PDF ή να το ρέξετε απευθείας στον πελάτη, διασφαλίζοντας ότι το αρχικό αρχείο παραμένει αμετάβλητο.

## Υλοποίηση βήμα‑βήμα: περιστροφή της πρώτης σελίδας 90 μοιρών

### 1. Εισαγωγή των απαιτούμενων πακέτων
`PdfViewOptions` λέει στο Viewer να εξάγει αρχείο PDF, ενώ το enum `Rotation` ορίζει τη γωνία. Και οι δύο κλάσεις ανήκουν στο πακέτο `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Ορισμός τοποθεσιών εξόδου και δημιουργία του Viewer
Αντικαταστήστε τις διαδρομές placeholder με τους πραγματικούς σας φακέλους. Ο κατασκευαστής `Viewer` δέχεται ένα αντικείμενο `File` που δείχνει στο πηγαίο έγγραφο.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Διαμόρφωση επιλογών προβολής PDF και εφαρμογή της περιστροφής
Η μέθοδος `rotatePage(int, Rotation)` δέχεται έναν **1‑based** δείκτη σελίδας και μια τιμή enum `Rotation`. Σε αυτό το παράδειγμα χρησιμοποιούμε `Rotation.ON_90_DEGREE` για να περιστρέψουμε την πρώτη σελίδα δεξιόστροφα.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Απόδοση του εγγράφου
Καλώντας `view` με τις ρυθμισμένες επιλογές γράφει το περιστραμμένο PDF στον φάκελο εξόδου.

```java
viewer.view(viewOptions);
```

#### Πώς λειτουργεί
- **PdfViewOptions** καθοδηγεί το Viewer να δημιουργήσει αρχείο PDF.  
- **rotatePage(int, Rotation)** περιστρέφει μόνο τη συγκεκριμένη σελίδα, αφήνοντας όλες τις άλλες αμετάβλητες.  
- Η μέθοδος υποστηρίζει τρεις σταθερές περιστροφής: `ON_90_DEGREE`, `ON_180_DEGREE` και `ON_270_DEGREE`.

## Συχνά προβλήματα και λύσεις
| Συμπτωμα | Πιθανή αιτία | Διόρθωση |
|---------|--------------|----------|
| **FileNotFoundException** | Λανθασμένη διαδρομή ή λείπει ο φάκελος | Επαληθεύστε ότι οι `YOUR_OUTPUT_DIRECTORY` και `YOUR_DOCUMENT_DIRECTORY` υπάρχουν και είναι αναγνώσιμες. |
| **Unsupported file format** | Προσπάθεια περιστροφής μορφής που δεν υποστηρίζεται από το Viewer | Ελέγξτε τη σελίδα [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Χρήση λανθασμένου αριθμού σελίδας (από 0) | Θυμηθείτε ότι το `rotatePage` χρησιμοποιεί αρίθμηση **1‑based**. |
| **Out‑of‑memory errors on large docs** | Απόδοση πολλών μεγάλων αρχείων σε ένα νήμα | Επεξεργαστείτε τα έγγραφα διαδοχικά ή χρησιμοποιήστε μια ομάδα νήματος με περιορισμένη ταυτόχρονη εκτέλεση. |

## Πρακτικές εφαρμογές

1. **Presentation adjustments** – Μετατρέψτε μια κάθετη διαφάνεια σε οριζόντια επί τόπου για καλύτερη οπτική επίδραση.  
2. **Bulk document correction** – Αυτοματοποιήστε τη διόρθωση σαρωμένων PDF που λήφθηκαν πλαγίως, εξοικονομώντας ώρες χειροκίνητης εργασίας.  
3. **Print‑ready output** – Διασφαλίστε ότι τα τοπίο γραφικά εκτυπώνονται σωστά σε χαρτί προσανατολισμένο κατακόρυφα χωρίς χειροκίνητη περιστροφή στον οδηγό εκτυπωτή.

## Συμβουλές απόδοσης

- **Close resources promptly** – Το μπλοκ `try‑with‑resources` διαγράφει αυτόματα το `Viewer`, ελευθερώνοντας μνήμη.  
- **Batch processing** – Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `Viewer` ανά νήμα για μείωση του κόστους εκκίνησης.  
- **Monitor memory** – Για έγγραφα μεγαλύτερα από 100 MB, ρέξτε την έξοδο στο δίσκο αντί να κρατάτε ολόκληρο το αρχείο στη μνήμη· το GroupDocs Viewer μπορεί να επεξεργαστεί αρχεία 200 MB χρησιμοποιώντας κάτω από 250 MB RAM.

## Συχνές ερωτήσεις

**Q: Μπορώ να περιστρέψω πολλαπλές σελίδες ταυτόχρονα;**  
A: Ναι—καλέστε `rotatePage()` για κάθε αριθμό σελίδας που χρειάζεται περιστροφή, είτε σε βρόχο είτε αλυσιδωτά.

**Q: Υπάρχει τρόπος να αναιρέσω τη περιστροφή μετά το rendering;**  
A: Όχι άμεσα. Θα πρέπει να αποδώσετε ξανά το έγγραφο χωρίς τις επιλογές περιστροφής.

**Q: Ποιες μορφές αρχείων υποστηρίζουν περιστροφή σελίδας στο GroupDocs Viewer;**  
A: DOCX, PDF, PPTX, XLSX και πολλές άλλες μορφές που αναφέρονται στην επίσημη τεκμηρίωση.

**Q: Πώς μπορώ να περιστρέψω σελίδες σε μια δέσμη εγγράφων αυτόματα;**  
A: Τυλίξτε τη λογική περιστροφής σε έναν βρόχο που διατρέχει μια συλλογή διαδρομών αρχείων, εφαρμόζοντας την ίδια διαμόρφωση `rotatePage` σε κάθε αρχείο.

**Q: Ποια είναι η βέλτιστη πρακτική για τη διαχείριση σφαλμάτων κατά τη διάρκεια της περιστροφής;**  
A: Περιβάλλετε τη χρήση του Viewer σε μπλοκ `try‑catch`, καταγράψτε τις λεπτομέρειες της εξαίρεσης και, προαιρετικά, συνεχίστε με το επόμενο αρχείο ώστε ένα σφάλμα να μην σταματήσει ολόκληρη τη δέσμη.

## Πόροι

- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free trial**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία ενημέρωση:** 2026-09-30  
**Δοκιμάστηκε με:** GroupDocs Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

## Σχετικά μαθήματα

- [How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Load Document from URL in Java – GroupDocs.Viewer Tutorial](/viewer/java/document-loading/)
- [Groupdocs Viewer Java Document Views](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}