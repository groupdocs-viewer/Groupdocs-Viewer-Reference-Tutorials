---
date: '2026-06-25'
description: Μάθετε πώς να μετατρέψετε PDF σε PNG σε Java χρησιμοποιώντας το GroupDocs
  Viewer, διατηρώντας το αρχικό μέγεθος σελίδας και αποφεύγοντας κοινά προβλήματα
  απόδοσης.
keywords:
- convert pdf to png
- groupdocs viewer java
- pdf to image conversion
schemas:
- author: GroupDocs
  dateModified: '2026-06-25'
  description: Learn how to convert PDF to PNG in Java using GroupDocs Viewer, preserving
    the original page size and avoiding common rendering issues.
  headline: Convert PDF to PNG with GroupDocs Viewer for Java
  type: TechArticle
- questions:
  - answer: Register `Viewer` as a Spring bean, inject it where needed, and let Spring
      manage its lifecycle for thread‑safe reuse.
    question: How do I integrate GroupDocs.Viewer with Spring Boot?
  - answer: Yes – GroupDocs.Viewer also supports JPEG, SVG, and PDF‑to‑HTML conversions.
    question: Can I render PDFs to formats other than PNG?
  - answer: Inspect the stack trace for missing file paths or licensing issues, and
      verify that the PDF is not corrupted.
    question: What should I do if the rendering process fails with an exception?
  - answer: Technically no, but very large files may require increased JVM memory
      and benefit from splitting into smaller sections.
    question: Is there a size limit for PDFs that can be rendered?
  - answer: Absolutely – simply pass the password to the `Viewer` constructor or via
      the `LoadOptions` object.
    question: Does GroupDocs.Viewer handle password‑protected PDFs?
  type: FAQPage
title: Μετατροπή PDF σε PNG με το GroupDocs Viewer για Java
type: docs
url: /el/java/custom-rendering/render-pdf-original-page-size-groupdocs-viewer-java/
weight: 1
---

# Μετατροπή PDF σε PNG με το GroupDocs Viewer για Java

Σε αυτόν τον ολοκληρωμένο οδηγό θα ανακαλύψετε **πώς να μετατρέψετε PDF σε PNG** σε Java διατηρώντας κάθε σελίδα στις ακριβείς αρχικές της διαστάσεις. Η διατήρηση του αρχικού μεγέθους της σελίδας είναι κρίσιμη για νομικές υποβολές, διαφημιστικό υλικό που διατηρεί την ταυτότητα της μάρκας, και τεχνικά διαγράμματα όπου οποιαδήποτε κλιμάκωση θα διασπά τις μετρήσεις. Θα σας καθοδηγήσουμε στην εγκατάσταση του GroupDocs.Viewer, στη διαμόρφωση των επιλογών απόδοσης και στην αντιμετώπιση κοινών προβλημάτων ώστε να μπορείτε να παράγετε εικόνες PNG με τέλεια ακρίβεια κάθε φορά.

![Απόδοση PDF σε Αρχικό Μέγεθος με το GroupDocs.Viewer για Java](/viewer/custom-rendering/render-pdfs-in-original-size.png)

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη μπορεί να μετατρέψει PDF σε PNG σε Java;** το GroupDocs.Viewer for Java παρέχει ένα απλό API για `convert pdf to png`.  
- **Πώς μπορώ να διατηρήσω το αρχικό μέγεθος της σελίδας;** Καλέστε `setRenderOriginalPageSize(true)` στο αντικείμενο `PdfOptions`.  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι – απαιτείται μόνιμη ή προσωρινή άδεια GroupDocs για χρήση εκτός δοκιμής.  
- **Μπορώ να αποδώσω PDF με προστασία κωδικού;** Απολύτως· παρέχετε τον κωδικό όταν δημιουργείτε το παράδειγμα `Viewer`.  
- **Ποια έκδοση της Java απαιτείται;** Το JDK 8 ή νεότερο υποστηρίζεται πλήρως.

## Τι σημαίνει «απόδοση PDF σε αρχικό μέγεθος»;
Η απόδοση ενός PDF σε αρχικό μέγεθος σημαίνει εξαγωγή κάθε σελίδας στις ακριβείς διαστάσεις της χωρίς καμία κλιμάκωση. Όταν αποδίδετε ένα PDF, ο προβολέας μπορεί είτε να κλιμακώσει τις σελίδες ώστε να ταιριάζουν σε έναν προορισμό μορφής είτε να διατηρήσει τις ακριβείς διαστάσεις που ορίζονται στο αρχείο προέλευσης. Η απόδοση σε αρχικό μέγεθος σημαίνει ότι κάθε σελίδα εξάγεται pixel‑perfect, κάτι που είναι κρίσιμο για νομικά έγγραφα, αρχειακό υλικό και οποιοδήποτε σενάριο όπου η πιστότητα της διάταξης δεν μπορεί να θυσιαστεί.

## Γιατί να διατηρήσετε το μέγεθος της σελίδας PDF;
Η διατήρηση του αρχικού μεγέθους της σελίδας PDF εξασφαλίζει ότι η οπτική διάταξη, οι ακριβείς μετρήσεις και τα στοιχεία σχεδίασης παραμένουν αμετάβλητα μετά τη μετατροπή, κάτι που είναι απαραίτητο για νομική συμμόρφωση, συνέπεια μάρκας και τεχνική ακρίβεια σε διαγράμματα ή φόρμες. Επίσης αποτρέπει το ακούσιο περικοπή ή παραμόρφωση των γραφικών, διασφαλίζοντας ότι οι υπογραφές και τα υδατογραφήματα εμφανίζονται ακριβώς όπως προορίζονται σε όλες τις πλατφόρμες.

## Προαπαιτούμενα
- **Java Development Kit (JDK):** Έκδοση 8 ή νεότερη.  
- **GroupDocs.Viewer for Java:** Προσθέστε τη βιβλιοθήκη μέσω Maven (δείτε παρακάτω).  
- **IDE:** IntelliJ IDEA, Eclipse ή οποιονδήποτε επεξεργαστή συμβατό με Java.  

## Ρύθμιση του GroupDocs.Viewer για Java

### Διαμόρφωση Maven
Προσθέστε το επίσημο αποθετήριο GroupDocs και την εξάρτηση Viewer στο `pom.xml`. *(Μην τροποποιήσετε το μπλοκ κώδικα – πρέπει να παραμείνει ακριβώς όπως φαίνεται.)*

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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

#### Απόκτηση Άδειας
Η GroupDocs προσφέρει τρεις επιλογές αδειοδότησης: **Free Trial** (απεριόριστες σελίδες, περιορισμένος χρόνος), **Temporary License** (πλήρεις λειτουργίες έως 30 ημέρες), και **Permanent Purchase** (απεριόριστη χρήση παραγωγής). Επιλέξτε την επιλογή που ταιριάζει στο χρονοδιάγραμμα του έργου σας.

## Οδηγός Υλοποίησης

### Βήμα 1: Αρχικοποίηση του GroupDocs.Viewer
`Viewer` είναι η βασική κλάση στο GroupDocs.Viewer που φορτώνει ένα έγγραφο και παρέχει δυνατότητες απόδοσης. Δημιουργήστε ένα παράδειγμα `Viewer` και διαμορφώστε το `PngViewOptions`. Το `PngViewOptions` ορίζει ρυθμίσεις για την απόδοση των σελίδων ως εικόνες PNG. Η κρίσιμη κλήση `viewOptions.getPdfOptions().setRenderOriginalPageSize(true);` λέει στη μηχανή να **ορίσει το αρχικό μέγεθος της σελίδας**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

import java.nio.file.Path;

public class RenderOriginalPageSize {
    public static void main(String[] args) {
        // Define output directory path for rendered pages
        Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
        
        // Format for the output page file paths
        String pageFilePathFormat = "page_{0}.png";
        Path pageFilePath = outputDirectory.resolve(pageFilePathFormat);
        
        // Initialize PngViewOptions with the path format
        PngViewOptions viewOptions = new PngViewOptions(pageFilePath.toString());
        
        // Set option to render original page size for PDF documents
        viewOptions.getPdfOptions().setRenderOriginalPageSize(true);
        
        // Create a Viewer instance for the source PDF document
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF")) {
            // Render the PDF using the specified options
            viewer.view(viewOptions);
        }
    }
}
```

**Εξήγηση βασικών γραμμών**  
- **Διαμόρφωση Διαδρομής:** Καθορίζει πού θα αποθηκευτεί κάθε παραγόμενη PNG.  
- **PngViewOptions:** Επιλέγει PNG ως μορφή εξόδου (το κλασικό σενάριο *pdf to png java*).  
- **Render Original Page Size:** Εγγυάται ότι δεν θα γίνει κλιμάκωση, διατηρώντας τις ακριβείς διαστάσεις κάθε σελίδας PDF.

### Βήμα 2: Εκτέλεση και Επαλήθευση
Φορτώστε το PDF σας, καλέστε τη διαδικασία απόδοσης και στη συνέχεια ελέγξτε τα παραγόμενα αρχεία PNG. Οι εικόνες πρέπει να ταιριάζουν με τις αρχικές διαστάσεις των σελίδων PDF pixel‑for‑pixel. Εάν οι εικόνες εμφανίζονται τεντωμένες, ελέγξτε ξανά ότι το `setRenderOriginalPageSize(true)` είναι παρόν και ότι χρησιμοποιείτε την πιο πρόσφατη έκδοση του GroupDocs.Viewer.

## Αντιμετώπιση Προβλημάτων & Συνηθισμένα Πιθανά Σφάλματα
- **Λανθασμένες διαδρομές αρχείων:** Βεβαιωθείτε ότι τόσο το `outputDirectory` όσο και η διαδρομή του πηγαίου PDF είναι απόλυτες ή σωστά σχετικές με το έργο σας.  
- **Απουσία άδειας:** Χωρίς έγκυρη άδεια, η απόδοση μπορεί να επιστρέψει σε λειτουργία δοκιμής που περιορίζει τον αριθμό των σελίδων.  
- **Σφάλματα έλλειψης μνήμης σε μεγάλα PDF:** Αυξήστε τη μνήμη heap του JVM (`-Xmx2g` ή μεγαλύτερη) ή ενεργοποιήστε τη lazy φόρτωση των σελίδων.  
- **Κρυπτογραφημένα PDF:** Παρέχετε τον κωδικό κατά τη δημιουργία του παραδείγματος `Viewer` για να αποφύγετε σφάλματα *pdf rendering troubleshooting*.

## Πρακτικές Περιπτώσεις Χρήσης
1. **Ψηφιακά Αρχεία:** Διατηρήστε ιστορικές σάρωση χωρίς καμία παραμόρφωση.  
2. **Πύλες Νομικών Εγγράφων:** Προσφέρετε PDF έτοιμα για δικαστήριο που εμφανίζονται ακριβώς όπως υποβλήθηκαν.  
3. **Πλατφόρμες E‑Learning:** Μετατρέψτε βιβλία σε μορφή εικόνας διατηρώντας την ακεραιότητα της διάταξης.  
4. **Αυτοματοποίηση Τιμολογίων:** Διασφαλίστε ότι τα στοιχεία γραμμής και τα σύνολα παραμένουν αναγνώσιμα μετά τη μετατροπή.

## Συμβουλές Απόδοσης
- **Διαχείριση Μνήμης:** Κατανείμετε επαρκή χώρο heap για μεγάλα έγγραφα.  
- **Lazy Loading:** Αποδώστε μόνο τις σελίδες που χρειάζεστε αντί για ολόκληρο το αρχείο όταν είναι δυνατόν.  
- **Caching:** Αποθηκεύστε τις παραγόμενες PNG για PDF που προσπελαύνονται συχνά ώστε να αποφύγετε επαναλαμβανόμενη επεξεργασία.

## Συχνές Ερωτήσεις

**Q: Πώς ενσωματώνω το GroupDocs.Viewer με το Spring Boot;**  
A: Καταχωρίστε το `Viewer` ως bean του Spring, ενσωματώστε το όπου χρειάζεται και αφήστε το Spring να διαχειρίζεται τον κύκλο ζωής του για ασφαλή χρήση από πολλαπλά νήματα.

**Q: Μπορώ να αποδώσω PDF σε μορφές εκτός του PNG;**  
A: Ναι – το GroupDocs.Viewer υποστηρίζει επίσης JPEG, SVG και μετατροπές PDF‑σε‑HTML.

**Q: Τι πρέπει να κάνω αν η διαδικασία απόδοσης αποτύχει με εξαίρεση;**  
A: Εξετάστε το stack trace για ελλιπείς διαδρομές αρχείων ή προβλήματα αδειοδότησης και βεβαιωθείτε ότι το PDF δεν είναι κατεστραμμένο.

**Q: Υπάρχει όριο μεγέθους για τα PDF που μπορούν να αποδοθούν;**  
A: Τεχνικά όχι, αλλά πολύ μεγάλα αρχεία μπορεί να απαιτούν αυξημένη μνήμη JVM και να ωφεληθούν από το διαχωρισμό σε μικρότερες ενότητες.

**Q: Το GroupDocs.Viewer διαχειρίζεται PDF με προστασία κωδικού;**  
A: Απολύτως – απλώς περάστε τον κωδικό στον κατασκευαστή `Viewer` ή μέσω του αντικειμένου `LoadOptions`.

## Πόροι
- **Τεκμηρίωση:** [GroupDocs Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Αναφορά API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)  
- **Λήψη GroupDocs.Viewer:** [Official Downloads](https://releases.groupdocs.com/viewer/java/)  
- **Αγορά και Αδειοδότηση:** [Buy GroupDocs Products](https://purchase.groupdocs.com/buy)  
- **Δωρεάν Δοκιμή:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Προσωρινή Άδεια:** [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Φόρουμ Υποστήριξης:** [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία Ενημέρωση:** 2026-06-25  
**Δοκιμάστηκε Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs  

---

## Σχετικά Μαθήματα

- [Πώς να αποδώσετε pdf σε html και να βελτιστοποιήσετε την ποιότητα εικόνας σε Java με το GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [Πώς να αποδώσετε Σχέδια CAD ως PNG με Προσαρμοσμένο Μέγεθος & Χρώμα Φόντου Χρησιμοποιώντας το GroupDocs.Viewer για Java](/viewer/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/)