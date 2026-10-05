---
date: '2026-10-05'
description: Μάθετε πώς να περιστρέψετε συγκεκριμένες σελίδες PDF με το GroupDocs.Viewer
  for Java. Αυτός ο οδηγός βήμα προς βήμα καλύπτει τη ρύθμιση του Maven, την περιστροφή
  pdf 90 μοιρών και την αντιμετώπιση προβλημάτων.
keywords:
- rotate specific pdf pages
- rotate pdf 90 degrees
- pdf to html java
- rotate multiple pdf pages
lastmod: '2026-10-05'
og_description: Περιστρέψτε συγκεκριμένες σελίδες PDF με το GroupDocs.Viewer for Java.
  Μάθετε πώς να περιστρέψετε pdf 90 μοιρών, να ρυθμίσετε το Maven και να αντιμετωπίσετε
  κοινά προβλήματα σε έναν συνοπτικό οδηγό.
og_image_alt: Developer guide showing rotation of PDF pages using GroupDocs.Viewer
  Java SDK
og_title: Περιστροφή συγκεκριμένων σελίδων PDF με το GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-05'
  description: Learn how to rotate specific PDF pages with GroupDocs.Viewer for Java.
    This step‑by‑step guide covers Maven setup, rotate pdf 90 degrees, and troubleshooting.
  headline: How to Rotate Specific PDF Pages with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Yes. Loop through the page numbers and call `rotatePage(page, Rotation.ON_90_DEGREE)`
      for each page.
    question: Can I rotate all pages of a PDF at once?
  - answer: No. Rotation is applied only during the rendering process; the source
      PDF remains unchanged.
    question: Does the rotation affect the original PDF file?
  - answer: 'Provide the password when creating the `Viewer` instance: `new Viewer(path,
      password)`.'
    question: What if a PDF is password‑protected?
  - answer: Ensure the output directory exists and that `pageFilePathFormat` resolves
      correctly.
    question: How do I debug a “null pointer” error when setting up HtmlViewOptions?
  - answer: Yes. Use the same `rotatePage` configuration with the appropriate view
      options for the target format.
    question: Is there a way to rotate pages when converting to other formats (e.g.,
      PNG)?
  type: FAQPage
tags:
- rotate pdf
- groupdocs viewer
- java pdf processing
title: Πώς να περιστρέψετε συγκεκριμένες σελίδες PDF με το GroupDocs.Viewer for Java
type: docs
url: /el/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/
weight: 1
---

# Πώς να περιστρέψετε συγκεκριμένες σελίδες pdf με το GroupDocs.Viewer για Java

Η περιστροφή συγκεκριμένων σελίδων μέσα σε ένα PDF μπορεί να είναι απαραίτητη για την ευθυγράμμιση εγγράφων, τη διόρθωση σαρωμένων εικόνων ή την προσαρμογή διαφανειών παρουσίασης. **Σε αυτόν τον οδηγό θα μάθετε πώς να περιστρέφετε συγκεκριμένες σελίδες pdf προγραμματιστικά με το GroupDocs.Viewer**, είτε χρειάζεται να περιστρέψετε pdf 90 μοίρες, να αντιστρέψετε ολόκληρη ενότητα, είτε να διαχειριστείτε πολλαπλές σελίδες σε μία κλήση.

![Περιστροφή συγκεκριμένων σελίδων PDF με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

[Περιστροφή συγκεκριμένων σελίδων PDF με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/rotate-specific-pdf-pages-java.png)

**Τι θα μάθετε**
- Ρύθμιση του GroupDocs.Viewer στο έργο Java σας (συμπεριλαμβανομένης της διαμόρφωσης Maven GroupDocs Viewer)
- Προγραμματιστική περιστροφή συγκεκριμένων σελίδων PDF (περιστροφή pdf 90 μοιρών, 180 μοιρών κ.λπ.)
- Κύριες ρυθμίσεις για βέλτιστη χρήση
- Αντιμετώπιση κοινών προβλημάτων κατά την υλοποίηση

## Σύντομες απαντήσεις
- **Ποια βιβλιοθήκη μπορεί να περιστρέψει σελίδες PDF σε Java;** Το GroupDocs.Viewer for Java παρέχει ενσωματωμένη υποστήριξη περιστροφής χωρίς εξωτερικά εργαλεία.  
- **Μπορώ να περιστρέψω μία σελίδα κατά 90 μοίρες;** Ναι – καλέστε `rotatePage(pageNumber, Rotation.ON_90_DEGREE)` στην παρουσία του viewer.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια προσωρινή άδεια είναι δωρεάν για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Απαιτείται Maven;** Το Maven είναι ο προτεινόμενος διαχειριστής εξαρτήσεων, αλλά μπορείτε επίσης να χρησιμοποιήσετε Gradle ή χειροκίνητη ένταξη JAR.  
- **Πώς αποδίδω τις περιστραμμένες σελίδες;** Χρησιμοποιήστε `HtmlViewOptions` με `viewer.view(documentPath, viewOptions)` για να λάβετε HTML έξοδο που αντικατοπτρίζει την περιστροφή.

## Τι είναι η περιστροφή συγκεκριμένων σελίδων pdf;
`rotate specific pdf pages` αναφέρεται στην ικανότητα αλλαγής του προσανατολισμού μεμονωμένων σελίδων μέσα σε ένα έγγραφο PDF, ενώ το υπόλοιπο του αρχείου παραμένει αμετάβλητο. Η λειτουργία αυτή εκτελείται κατά το χρόνο απόδοσης, έτσι ώστε το αρχικό αρχείο PDF να παραμένει αμετάβλητο.

## Γιατί να περιστρέφετε συγκεκριμένες σελίδες pdf;
Μπορείτε να περιστρέψετε μία σελίδα σε λιγότερο από 0,05 δευτερόλεπτα σε μια τυπική εικονική μηχανή server‑grade, επιτρέποντας προεπισκόπηση σε πραγματικό χρόνο σαρωμένων συμβάσεων, παρουσιάσεων ή πολυσελιδών τιμολογίων που περιέχουν λανθασμένα προσανατολισμένες σαρώσεις. Αυτός ο λεπτομερής έλεγχος εξαλείφει την ανάγκη για δαπανηρά εργαλεία μετα‑επεξεργασίας και μειώνει την χειροκίνητη εργασία έως και 70 % σε μεγάλης κλίμακας έργα ψηφιοποίησης.

## Προαπαιτούμενα

### Απαιτούμενες βιβλιοθήκες και εξαρτήσεις
- Java Development Kit (JDK) 8 ή νεότερο.  
- Ένα IDE όπως το IntelliJ IDEA ή το Eclipse.  
- Maven για διαχείριση εξαρτήσεων.

### Απαιτήσεις ρύθμισης περιβάλλοντος
1. **Διαμόρφωση Maven** – προσθέστε το GroupDocs.Viewer στο `pom.xml` σας.  
2. **Απόκτηση άδειας** – αποκτήστε μια προσωρινή άδεια από το GroupDocs. Επισκεφθείτε [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) ή υποβάλετε αίτηση για προσωρινή άδεια στη [GroupDocs Temporary License Page](https://purchase.groupdocs.com/temporary-license/).

## Ρύθμιση του GroupDocs.Viewer για Java

Για να ενσωματώσετε το GroupDocs.Viewer στο έργο Java σας χρησιμοποιώντας Maven, ενημερώστε το `pom.xml` σας:

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

### Βασική αρχικοποίηση και ρύθμιση
`Viewer` είναι η κεντρική κλάση που φορτώνει ένα έγγραφο και οργανώνει τις λειτουργίες απόδοσης. Μετά τη δημιουργία μιας παρουσίας μπορείτε να καλέσετε μεθόδους όπως `view` ή `rotatePage`.  

```java
Path YOUR_DOCUMENT_DIRECTORY = Path.of("YOUR_DOCUMENT_DIRECTORY");
Path YOUR_OUTPUT_DIRECTORY = Path.of("YOUR_OUTPUT_DIRECTORY");

// Format for page file paths
Path pageFilePathFormat = YOUR_OUTPUT_DIRECTORY.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

## Πώς να περιστρέψετε συγκεκριμένες σελίδες PDF με το GroupDocs.Viewer
Η περιστροφή συγκεκριμένων σελίδων PDF με το GroupDocs.Viewer περιλαμβάνει δύο κύριες ενέργειες: πρώτα, καθορίστε την επιθυμητή περιστροφή για κάθε στοχευμένη σελίδα χρησιμοποιώντας τη μέθοδο `rotatePage`, και δεύτερον, αποδώστε το έγγραφο με `HtmlViewOptions` ώστε η περιστροφή να αντικατοπτρίζεται στην έξοδο. Αυτή η προσέγγιση διατηρεί το αρχικό PDF αμετάβλητο ενώ παρέχει σωστά προσανατολισμένο HTML.

### Βήμα 1: διαμόρφωση περιστροφής σελίδας
`rotatePage` είναι μια μέθοδος που δέχεται έναν δείκτη σελίδας με βάση το μηδέν και μια τιμή enum `Rotation`. Το enum παρέχει τρεις επιλογές: `ON_90_DEGREE`, `ON_180_DEGREE` και `ON_270_DEGREE`.  

```java
// Rotate the first page by 90 degrees clockwise.
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);

// Rotate the second page by 180 degrees.
viewOptions.rotatePage(2, Rotation.ON_180_DEGREE);
```

### Βήμα 2: αρχικοποίηση του viewer και απόδοση
`HtmlViewOptions` ελέγχει τη διαδικασία μετατροπής PDF‑σε‑HTML. Διατηρεί τη διάταξη, τις γραμματοσειρές και τους ενσωματωμένους πόρους ενώ εφαρμόζει οποιαδήποτε περιστροφή έχετε διαμορφώσει.  

```java
Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SampleDocument.pdf"));

// Render the specified pages (1 and 2) using the configured options.
viewer.view(viewOptions, 1, 2);

// Always close the viewer to free resources.
viewer.close();
```

#### Παράμετροι και διαμόρφωση
- **Rotation** – `rotatePage(pageNumber, Rotation.*)` όπου οι επιλογές περιστροφής είναι `ON_90_DEGREE`, `ON_180_DEGREE`, `ON_270_DEGREE`.  
- **HtmlViewOptions** – Διαχειρίζεται τη μετατροπή pdf‑to‑html διατηρώντας τη διάταξη και τους ενσωματωμένους πόρους.  
- **pdf to html java** – Η κλάση είναι μέρος του ίδιου API και εξασφαλίζει πιστή οπτική αναπαράσταση.

## Συχνά προβλήματα και λύσεις (αντιμετώπιση περιστροφής pdf)
- **Incorrect paths** – Επαληθεύστε ότι οι φάκελοι `YOUR_DOCUMENT_DIRECTORY` και `YOUR_OUTPUT_DIRECTORY` υπάρχουν και είναι προσβάσιμοι.  
- **Missing dependencies** – Βεβαιωθείτε ότι οι συντεταγμένες Maven ταιριάζουν με την τελευταία έκδοση του GroupDocs.Viewer (προς το παρόν 25.2).  
- **License restrictions** – Εφαρμόστε τη προσωρινή άδεια σωστά· διαφορετικά, ορισμένες λειτουργίες μπορεί να είναι απενεργοποιημένες.  
- **Memory spikes** – Αποδώστε μεγάλα PDF σε μικρότερα παρτίδες ή αυξήστε το μέγεθος της μνήμης heap της JVM.

## Πρακτικές εφαρμογές

### Πραγματικές περιπτώσεις χρήσης
1. **Document alignment** – Περιστρέψτε σαρωμένα συμβόλαια για σωστή ψηφιακή προσανατολισμό.  
2. **Presentation adjustments** – Τροποποιήστε διαφάνειες παρουσίασης μέσα σε PDF πριν τη διανομή.  
3. **Archival workflows** – Αυτόματη προσαρμογή του προσανατολισμού ιστορικών εγγράφων κατά τη διαδικασία ψηφιοποίησης.

### Δυνατότητες ενσωμάτωσης
Συνδυάστε το GroupDocs.Viewer με συστήματα διαχείρισης περιεχομένου βασισμένα σε Java, εταιρικές πύλες ή προσαρμοσμένα API που απαιτούν άμεση προβολή PDF.

## Σκέψεις απόδοσης
- **Resource management** – Πάντα κλείστε την παρουσία `Viewer` για να απελευθερώσετε τους χειριστές αρχείων και τη μνήμη.  
- **Java memory management** – Παρακολουθήστε τη χρήση heap κατά την επεξεργασία μεγάλων PDF· σκεφτείτε τη ροή σελίδων αντί της φόρτωσης ολόκληρου του αρχείου.  
- **Best practices** – Κρατήστε στην κρυφή μνήμη (cache) το αποδοθέν HTML για συχνά προσπελαζόμενα έγγραφα ώστε να μειώσετε τον χρόνο επεξεργασίας έως και 60 %.

## Συμπέρασμα
Αυτό το εκπαιδευτικό υλικό κάλυψε **πώς να περιστρέψετε συγκεκριμένες σελίδες pdf χρησιμοποιώντας το GroupDocs.Viewer σε Java**, από τη ρύθμιση Maven μέχρι την απόδοση περιστραμμένων σελίδων και την αντιμετώπιση κοινών παγίδων. Πειραματιστείτε με πρόσθετες λειτουργίες όπως υδατογράφημα, μετατροπή μορφών ή επεξεργασία δέσμης για να επεκτείνετε περαιτέρω τη ροή εργασίας των εγγράφων σας.

**Επόμενα βήματα:** Εξερευνήστε άλλες δυνατότητες του GroupDocs.Viewer όπως η μετατροπή PDF σε PNG, η προσθήκη υδατογραφήματος ή η ενσωμάτωση με παρόχους αποθήκευσης cloud.

## Ενότητα Συχνών Ερωτήσεων
- **Troubleshooting rotation issues** – Επαληθεύστε ότι οι αριθμοί σελίδων και οι παράμετροι περιστροφής είναι σωστοί.  
- **Handling large PDF files** – Επεξεργαστείτε τις σελίδες σε δέσμες και παρακολουθήστε τη χρήση μνήμης.  
- **Licensing requirements** – Χρησιμοποιήστε προσωρινή άδεια για ανάπτυξη· αγοράστε πλήρη άδεια για παραγωγή.  
- **Rotating multiple pages** – Καλέστε `rotatePage` επανειλημμένα με διαφορετικούς αριθμούς σελίδων και γωνίες.  
- **Integration with Java libraries** – Το GroupDocs.Viewer λειτουργεί άψογα με Spring Boot, Jakarta EE και άλλα πλαίσια Java.

## Συχνές ερωτήσεις

**Q: Μπορώ να περιστρέψω όλες τις σελίδες ενός PDF ταυτόχρονα;**  
A: Ναι. Επαναλάβετε μέσω των αριθμών σελίδων και καλέστε `rotatePage(page, Rotation.ON_90_DEGREE)` για κάθε σελίδα.

**Q: Επηρεάζει η περιστροφή το αρχικό αρχείο PDF;**  
A: Όχι. Η περιστροφή εφαρμόζεται μόνο κατά τη διαδικασία απόδοσης· το πηγαίο PDF παραμένει αμετάβλητο.

**Q: Τι γίνεται αν ένα PDF είναι προστατευμένο με κωδικό;**  
A: Παρέχετε τον κωδικό κατά τη δημιουργία της παρουσίας `Viewer`: `new Viewer(path, password)`.

**Q: Πώς εντοπίζω σφάλμα “null pointer” κατά τη ρύθμιση του HtmlViewOptions;**  
A: Βεβαιωθείτε ότι ο φάκελος εξόδου υπάρχει και ότι το `pageFilePathFormat` επιλύεται σωστά.

**Q: Υπάρχει τρόπος να περιστρέψω σελίδες κατά τη μετατροπή σε άλλες μορφές (π.χ., PNG);**  
A: Ναι. Χρησιμοποιήστε την ίδια διαμόρφωση `rotatePage` με τις κατάλληλες επιλογές προβολής για τη μορφή-στόχο.

## Πόροι
- **Τεκμηρίωση**: [Τεκμηρίωση GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)  
- **Αναφορά API**: [Αναφορά API GroupDocs](https://reference.groupdocs.com/viewer/java/)  
- **Λήψη**: [Σελίδα Λήψης GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Αγορά**: [Επιλογές Αγοράς GroupDocs](https://purchase.groupdocs.com/buy)  
- **Δωρεάν Δοκιμή**: [Δωρεάν Δοκιμή GroupDocs](https://releases.groupdocs.com/viewer/java/)  
- **Προσωρινή Άδεια**: [Αίτηση Προσωρινής Άδειας](https://purchase.groupdocs.com/temporary-license/)  
- **Υποστήριξη**: [Φόρουμ Υποστήριξης GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία Ενημέρωση:** 2026-10-05  
**Δοκιμάστηκε Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

## Σχετικά Μαθήματα

- [Οδηγός Java: απόδοση επιλεγμένων σελίδων java με το GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [Απόδοση PDF Java με Groupdocs Viewer – Διακοπές Σελίδας](/viewer/java/advanced-rendering/java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [Groupdocs Viewer Java – Ανταποκρινόμενη Απόδοση Html](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)