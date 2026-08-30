---
date: '2026-08-30'
description: Μάθετε πώς να μετατρέψετε το Word σε PNG με στρώση αναζητήσιμου κειμένου
  σε Java χρησιμοποιώντας το GroupDocs.Viewer, καθώς και πώς να μετατρέψετε το PDF
  σε PNG με επικάλυψη κειμένου για εικόνες υψηλής ευκρίνειας με δυνατότητα αναζήτησης.
keywords:
- convert word to png
- convert pdf to png
- extract text overlay
- groupdocs viewer java
- searchable document images
lastmod: '2026-08-30'
og_description: Μετατροπή Word σε PNG με στρώση αναζητήσιμου κειμένου σε Java χρησιμοποιώντας
  το GroupDocs.Viewer. Αυτός ο οδηγός δείχνει επίσης πώς να μετατρέψετε το PDF σε
  PNG με επικάλυψη κειμένου για εικόνες με δυνατότητα αναζήτησης.
og_image_alt: 'Developer guide: Convert Word to PNG with text layer using GroupDocs.Viewer
  for Java'
og_title: Μετατροπή Word σε PNG με στρώση αναζητήσιμου κειμένου σε Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert Word to PNG with a searchable text layer in Java
    using GroupDocs.Viewer, and also convert PDF to PNG with text overlay for high‑clarity
    searchable images.
  headline: Convert Word to PNG with a searchable text layer in Java
  type: TechArticle
- description: Learn how to convert Word to PNG with a searchable text layer in Java
    using GroupDocs.Viewer, and also convert PDF to PNG with text overlay for high‑clarity
    searchable images.
  name: Convert Word to PNG with a searchable text layer in Java
  steps:
  - name: define the output directory
    text: First, tell the viewer where to store the generated PNG files. The code
      below creates (or re‑uses) a folder called `YOUR_OUTPUT_DIRECTORY`. > **Pro
      tip:** Use `Files.createDirectories(outputDirectory);` if you want the folder
      to be created automatically.
  - name: configure view options
    text: '`PngViewOptions` configures how each page is rendered to PNG and can enable
      text extraction. By calling `setExtractText(true)` you instruct GroupDocs.Viewer
      to embed an invisible text layer in every image.'
  - name: render the document
    text: 'The `viewer.view(viewOptions)` call opens the source DOCX and generates
      the PNG pages. The `try‑with‑resources` block guarantees that the `Viewer` instance
      is closed properly, releasing all native resources. When the process completes,
      each page of the Word document appears as a high‑resolution PNG '
  type: HowTo
- questions:
  - answer: Render pages incrementally and release each `Viewer` instance after processing
      a batch to keep memory usage low.
    question: How do I handle large documents?
  - answer: Yes, GroupDocs.Viewer supports PDF and the same `setExtractText(true)`
      flag will generate searchable PDF images.
    question: Can I render PDFs with the same approach?
  - answer: Verify that `viewOptions.setExtractText(true)` is set and that the output
      folder has write permissions.
    question: What if the text layer isn’t visible in the output?
  - answer: Besides PNG, you can use `JpgViewOptions` or `BmpViewOptions` by swapping
      the view option class.
    question: Are other image formats supported?
  - answer: The official docs provide exhaustive examples and configuration details.
    question: Where can I find more detailed API documentation?
  type: FAQPage
tags:
- convert word
- convert pdf
- groupdocs viewer
- java rendering
title: Μετατροπή Word σε PNG με στρώση αναζητήσιμου κειμένου σε Java
type: docs
url: /el/java/advanced-rendering/render-documents-to-images-with-text-layer-java/
weight: 1
---

# Μετατροπή Word σε PNG με επιπλέον στρώση αναζητήσιμου κειμένου σε Java

Σε αυτόν τον ολοκληρωμένο οδηγό θα μάθετε πώς να **μετατρέψετε το Word σε PNG** διατηρώντας ένα κρυφό, επιλέξιμο στρώμα κειμένου χρησιμοποιώντας το GroupDocs.Viewer για Java. Η ίδια τεχνική λειτουργεί και για PDFs, παρέχοντάς σας προεπισκοπήσεις εικόνας υψηλής ευκρίνειας που παραμένουν πλήρως αναζητήσιμες — ιδανικό για διαδικτυακές πύλες, συστήματα CMS και αρχειοθετητικές λύσεις που χρειάζονται γρήγορη απόδοση χωρίς να θυσιάζεται η δυνατότητα εύρεσης.

![Απόδοση εγγράφων ως εικόνες με στρώση κειμένου με GroupDocs.Viewer για Java](/viewer/advanced-rendering/render-documents-as-images-with-text-layer-java.png)

[Απόδοση εγγράφων ως εικόνες με στρώση κειμένου με GroupDocs.Viewer για Java](/viewer/advanced-rendering/render-documents-as-images-with-text-layer-java.png)

## Γρήγορες απαντήσεις
- **Τι σημαίνει “convert Word to PNG”;** Δημιουργεί ένα raster PNG για κάθε σελίδα και ενσωματώνει μια αόρατη επικάλυψη κειμένου ώστε το περιεχόμενο να παραμένει αναζητήσιμο.  
- **Γιατί να προσθέσετε στρώση κειμένου;** Η επικάλυψη επιτρέπει στα προγράμματα περιήγησης και τις μηχανές αναζήτησης να ευρετηριάσουν το κείμενο χωρίς να εκτελούν OCR, βελτιώνοντας την προσβασιμότητα και το SEO.  
- **Ποια βιβλιοθήκη το διαχειρίζεται;** Το GroupDocs.Viewer για Java παρέχει ενσωματωμένη υποστήριξη τόσο για απόδοση εικόνας όσο και για εξαγωγή κειμένου.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή είναι επαρκής για ανάπτυξη· απαιτείται πληρωμένη άδεια για παραγωγικές εγκαταστάσεις.  
- **Μπορώ να χρησιμοποιήσω τον ίδιο κώδικα για PDFs;** Ναι—απλώς κατευθύνετε το viewer σε ένα PDF και ενεργοποιήστε την ίδια επιλογή επικάλυψης κειμένου.  

## Τι είναι η μετατροπή Word σε PNG με στρώση κειμένου;
Η μετατροπή Word σε PNG με στρώση κειμένου αποδίδει κάθε σελίδα DOCX ως εικόνα PNG και ενσωματώνει μια αόρατη επικάλυψη κειμένου για αναζητησιμότητα.  
Αυτή η διαδικασία μετατρέπει ένα έγγραφο Word σε σύνολο εικόνων υψηλής ανάλυσης, διατηρώντας το αρχικό κείμενο προσβάσιμο σε προγράμματα ανάγνωσης οθόνης και μηχανές ανίχνευσης. Το αποτέλεσμα φαίνεται ως στατική εικόνα, αλλά μπορείτε να αντιγράψετε‑επικολλήσετε ή να αναζητήσετε το περιεχόμενο επειδή το κείμενο ζει σε κρυφή στρώση πίσω από τα pixel.

## Γιατί να χρησιμοποιήσετε το GroupDocs.Viewer για αυτήν την εργασία;
Το GroupDocs.Viewer παρέχει έξοδο PNG pixel‑perfect **και** προσθέτει αυτόματα μια στρώση αναζητήσιμου κειμένου, εξαλείφοντας την ανάγκη για ξεχωριστό βήμα OCR. Η μηχανή απόδοσής του επεξεργάζεται τα έγγραφα με ροή, ώστε ακόμη και αρχεία με εκατοντάδες σελίδες να διαχειρίζονται χωρίς να φορτώνεται ολόκληρο το αρχείο στη μνήμη. Η βιβλιοθήκη υποστηρίζει **70+ μορφές εισόδου και εξόδου**, συμπεριλαμβανομένων των DOCX, PDF, PPTX, XLSX και κοινών τύπων εικόνας, καθιστώντας την μια ολοκληρωμένη λύση για ποικίλες διαδρόμους εγγράφων.

- **Έξοδος PNG υψηλής ποιότητας** που αντικατοπτρίζει την αρχική διάταξη pixel προς pixel.  
- **Αυτόματη εξαγωγή επικάλυψης κειμένου** σας εξοικονομεί την υλοποίηση OCR.  
- **Απλό API**—μερικές γραμμές κώδικα Java διαχειρίζονται όλη τη ροή εργασίας.  
- **Ευρεία υποστήριξη μορφών**—η ίδια προσέγγιση λειτουργεί για PDFs, PPTX και πολλές άλλες μορφές.  
- **Βελτιωμένη σαφήνεια εγγράφου** χάρη σε μια μη απωλεστική μηχανή απόδοσης που διατηρεί γραφικά vector και γραμματοσειρές.

## Προαπαιτούμενα
- Java Development Kit (JDK) 8 ή νεότερο εγκατεστημένο και διαμορφωμένο.  
- Maven για διαχείριση εξαρτήσεων.  
- Βασική εξοικείωση με τη διαχείριση αρχείων Java και τη δομή έργου Maven.  

## Ρύθμιση GroupDocs.Viewer για Java

### Πληροφορίες εγκατάστασης
Προσθέστε το GroupDocs.Viewer στο Maven έργο σας εισάγοντας το αποθετήριο και την εξάρτηση στο `pom.xml` σας:

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
Ξεκινήστε με μια δωρεάν δοκιμή κατεβάζοντας το GroupDocs.Viewer από τη [σελίδα λήψης](https://releases.groupdocs.com/viewer/java/). Για παραγωγική χρήση, αγοράστε άδεια ή αποκτήστε προσωρινό κλειδί από τη [σελίδα προσωρινής άδειας](https://purchase.groupdocs.com/temporary-license/).

### Βασική αρχικοποίηση και ρύθμιση
Η κλάση `Viewer` είναι το κύριο συστατικό που φορτώνει έγγραφα και τα αποδίδει σύμφωνα με τις καθορισμένες επιλογές προβολής. Μετά το συγχρονισμό Maven, μπορείτε να δημιουργήσετε μια παρουσία `Viewer`—αυτό το αντικείμενο θα οδηγήσει τη διαδικασία απόδοσης.

## Οδηγός βήμα‑βήμα για τη μετατροπή Word σε PNG

### Βήμα 1: ορισμός του καταλόγου εξόδου
Πρώτα, ενημερώστε το viewer πού θα αποθηκεύσει τα παραγόμενα αρχεία PNG. Ο κώδικας παρακάτω δημιουργεί (ή επαναχρησιμοποιεί) έναν φάκελο με όνομα `YOUR_OUTPUT_DIRECTORY`.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
```

> **Συμβουλή:** Χρησιμοποιήστε `Files.createDirectories(outputDirectory);` αν θέλετε ο φάκελος να δημιουργηθεί αυτόματα.

### Βήμα 2: διαμόρφωση επιλογών προβολής
`PngViewOptions` διαμορφώνει πώς κάθε σελίδα αποδίδεται σε PNG και μπορεί να ενεργοποιήσει την εξαγωγή κειμένου. Καλώντας `setExtractText(true)` υποδεικνύετε στο GroupDocs.Viewer να ενσωματώσει μια αόρατη στρώση κειμένου σε κάθε εικόνα.

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
viewOptions.setExtractText(true);  // Enable extracting text over the image
```

### Βήμα 3: απόδοση του εγγράφου
Η κλήση `viewer.view(viewOptions)` ανοίγει το πηγαίο DOCX και δημιουργεί τις σελίδες PNG. Το μπλοκ `try‑with‑resources` εγγυάται ότι η παρουσία `Viewer` κλείνει σωστά, απελευθερώνοντας όλους τους εγγενείς πόρους.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DOCX")) {
    viewer.view(viewOptions);  // Perform rendering operation
}
```

Όταν ολοκληρωθεί η διαδικασία, κάθε σελίδα του εγγράφου Word εμφανίζεται ως PNG υψηλής ανάλυσης με αόρατη στρώση κειμένου, έτοιμη για ευρετηρίαση και αναζήτηση.

## Γιατί αυτό είναι σημαντικό
Η ενσωμάτωση μιας στρώσης αναζητήσιμου κειμένου σημαίνει ότι μπορείτε να προσφέρετε ελαφριές προεπισκοπήσεις εικόνας **και** να διατηρήσετε πλήρη δυνατότητα αναζήτησης κειμένου. Αυτό είναι ιδιαίτερα πολύτιμο για:

1. **Διαδικτυακές πύλες** που χρειάζονται γρήγορες προεπισκοπήσεις μικρογραφιών χωρίς να θυσιάζεται το SEO.  
2. **Συστήματα Διαχείρισης Περιεχομένου** που αποθηκεύουν αρχειοθετημένα στιγμιότυπα αλλά εξακολουθούν να απαιτούν ευρετηρίαση κειμένου.  
3. **Αρχειοθέτηση εγγράφων** όπου το κόστος αποθήκευσης είναι σημαντικό αλλά η δυνατότητα εύρεσης πρέπει να παραμένει υψηλή.  

## Κοινά προβλήματα και λύσεις
- **Αρχείο δεν βρέθηκε:** Ελέγξτε ξανά τη διαδρομή προς το `SAMPLE_DOCX`. Χρησιμοποιήστε απόλυτες διαδρομές για βεβαιότητα.  
- **Προβλήματα δικαιωμάτων:** Βεβαιωθείτε ότι η διαδικασία Java μπορεί να γράψει στο `YOUR_OUTPUT_DIRECTORY`.  
- **Ασυμφωνία έκδοσης:** Επαληθεύστε ότι η έκδοση στο `pom.xml` ταιριάζει με τη βιβλιοθήκη που κατεβάσατε.  
- **Λείπει η στρώση κειμένου:** Επιβεβαιώστε ότι το `viewOptions.setExtractText(true)` είναι ορισμένο και ότι ο φάκελος εξόδου είναι εγγράψιμος.  

## Πρακτικές εφαρμογές
1. **Διαδικτυακές πύλες:** Εμφανίστε προεπισκοπήσεις εγγράφων που οι χρήστες μπορούν να αναζητήσουν χωρίς να κατεβάσουν το αρχικό αρχείο.  
2. **Συστήματα Διαχείρισης Περιεχομένου:** Αποθηκεύστε αναζητήσιμα στιγμιότυπα εικόνας για αρχειοθετητικούς σκοπούς.  
3. **Αρχειοθέτηση εγγράφων:** Διατηρήστε μια ελαφριά έκδοση εικόνας ενώ εξακολουθείτε να επιτρέπετε πλήρη αναζήτηση κειμένου.  

## Παραμέτρους απόδοσης
- Αποδεσμεύστε άμεσα τα αντικείμενα `Viewer` (όπως φαίνεται με `try‑with‑resources`).  
- Επιλέξτε PNG για ποιότητα· αλλάξτε σε JPEG αν η ζήτηση bandwidth είναι πρόβλημα.  
- Κρατήστε στην cache τις αποδομένες σελίδες όταν το ίδιο έγγραφο ζητείται επανειλημμένα.  

## Συχνές ερωτήσεις

**Q: Πώς διαχειρίζομαι μεγάλα έγγραφα;**  
A: Αποδίδετε τις σελίδες σταδιακά και απελευθερώνετε κάθε παρουσία `Viewer` μετά την επεξεργασία ενός batch για να διατηρείται η χρήση μνήμης χαμηλή.

**Q: Μπορώ να αποδώσω PDFs με την ίδια προσέγγιση;**  
A: Ναι, το GroupDocs.Viewer υποστηρίζει PDF και η ίδια σημαία `setExtractText(true)` θα δημιουργήσει αναζητήσιμες εικόνες PDF.

**Q: Τι γίνεται αν η στρώση κειμένου δεν είναι ορατή στην έξοδο;**  
A: Επαληθεύστε ότι το `viewOptions.setExtractText(true)` είναι ορισμένο και ότι ο φάκελος εξόδου έχει δικαιώματα εγγραφής.

**Q: Υποστηρίζονται και άλλες μορφές εικόνας;**  
A: Εκτός από PNG, μπορείτε να χρησιμοποιήσετε `JpgViewOptions` ή `BmpViewOptions` αντικαθιστώντας την κλάση επιλογής προβολής.

**Q: Πού μπορώ να βρω πιο λεπτομερή τεκμηρίωση API;**  
A: Η επίσημη τεκμηρίωση παρέχει εκτενείς παραδείγματα και λεπτομέρειες διαμόρφωσης.

## Πόροι
- **Τεκμηρίωση:** [GroupDocs Viewer Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Οδηγός αναφοράς API:** [API Reference Guide](https://reference.groupdocs.com/viewer/java/)  
- **Λήψη:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Αγορά άδειας:** [Buy License](https://purchase.groupdocs.com/buy)  
- **Λήψη δωρεάν δοκιμής:** [Download Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Απόκτηση προσωρινής άδειας:** [Acquire Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Φόρουμ GroupDocs:** [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία ενημέρωση:** 2026-08-30  
**Δοκιμάστηκε με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

## Σχετικά μαθήματα

- [Μετατροπή PDF σε PNG με GroupDocs Viewer για Java](/viewer/java/custom-rendering/render-pdf-original-page-size-groupdocs-viewer-java/)
- [Απόδοση PDF σε στρώσεις Java – Αποτελεσματική απόδοση PDF σε στρώσεις με GroupDocs.Viewer](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)
- [Πώς να μετατρέψετε Excel σε HTML, JPG, PNG και PDF χρησιμοποιώντας το GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)