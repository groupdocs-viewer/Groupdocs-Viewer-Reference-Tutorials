---
date: '2026-08-25'
description: Μάθετε πώς να μετατρέψετε αρχεία Numbers με το GroupDocs.Viewer for Java,
  μετατρέποντας αρχεία Apple Numbers σε PDF, HTML, JPG ή PNG. Περιλαμβάνει οδηγίες
  εγκατάστασης, βήματα μετατροπής εγγράφων java και συμβουλές εμφάνισης στο web.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Μάθετε πώς να μετατρέψετε αρχεία Numbers με το GroupDocs.Viewer for
  Java, μετατρέποντας αρχεία Apple Numbers σε PDF, HTML, JPG ή PNG. Περιλαμβάνει οδηγίες
  εγκατάστασης, βήματα μετατροπής εγγράφων java και συμβουλές εμφάνισης στο web.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Πώς να μετατρέψετε αρχεία Numbers με το GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Πώς να μετατρέψετε αρχεία Numbers με το GroupDocs.Viewer for Java
type: docs
url: /el/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Πώς να μετατρέψετε αριθμούς με το GroupDocs.Viewer για Java

Η εμφάνιση των λογιστικών φύλλων Apple Numbers στο web ή μέσα σε έναν πελάτη επιφάνειας εργασίας μπορεί να φαίνεται σαν γρίφος, ειδικά όταν χρειάζεται να **μετατρέψετε αριθμούς σε PDF** ή να τους ενσωματώσετε ως εικόνες για αναφορές. Σε αυτό το εκπαιδευτικό υλικό θα μάθετε ακριβώς **πώς να μετατρέψετε αριθμούς** σε PDF, HTML, JPG και PNG χρησιμοποιώντας το **GroupDocs.Viewer για Java**. Θα περάσουμε από τη ρύθμιση του έργου, την απόδοση σε επίπεδο κώδικα και πραγματικά σενάρια, ώστε να μπορείτε να δημιουργήσετε αξιόπιστες διαδικασίες προεπισκόπησης ή αρχειοθέτησης σε λίγα λεπτά.

![Απόδοση εγγράφων Apple Numbers με το GroupDocs.Viewer για Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Απόδοση εγγράφων Apple Numbers με το GroupDocs.Viewer για Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Τι θα μάθετε
- Πώς να προσθέσετε το GroupDocs.Viewer σε ένα Maven‑βάσιμο έργο Java.  
- Κώδικας βήμα‑βήμα για **μετατροπή αριθμών σε pdf**, **μετατροπή αριθμών σε html**, **μετατροπή αριθμών σε jpg**, και **μετατροπή αριθμών σε png**.  
- Πότε να επιλέξετε κάθε μορφή εξόδου για διαδικτυακές πύλες, ροές εργασίας email ή συστήματα διαχείρισης εγγράφων.  

## Γρήγορες απαντήσεις
- **Μπορώ να μετατρέψω Numbers σε PDF με Java;** Ναι – δημιουργήστε ένα αντικείμενο `Viewer` και καλέστε `PdfViewOptions` για να λάβετε ένα έτοιμο‑για‑αποθήκευση PDF.  
- **Ποια μορφή παρέχει την πιο πλούσια προεπισκόπηση στο web;** HTML, επειδή διατηρεί τους πίνακες, τους τύπους και το στυλ διαδραστικά.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια για οποιαδήποτε μη‑δοκιμαστική ανάπτυξη.  
- **Υποστηρίζεται η μετατροπή εικόνων;** Απόλυτα – χρησιμοποιήστε `JpgViewOptions` ή `PngViewOptions` για στιγμιότυπα υψηλής ποιότητας.  
- **Ποια έκδοση Java απαιτείται;** Java 8+ και Maven για διαχείριση εξαρτήσεων.  

## Προαπαιτούμενα
- Java Development Kit (JDK) 8 ή νεότερο εγκατεστημένο στον υπολογιστή σας.  
- Maven για διαχείριση εξαρτήσεων και κατασκευή του έργου.  
- Βασική εξοικείωση με Java file I/O, διαδρομές και διαχείριση εξαιρέσεων.  

## Ρύθμιση του GroupDocs.Viewer για Java

### Εγκατάσταση με Maven
Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση Viewer στο `pom.xml` σας. Αυτό το τμήμα πρέπει να παραμείνει ακριβώς όπως φαίνεται:

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
- **Δωρεάν δοκιμή:** Πλήρες σύνολο λειτουργιών, χωρίς ανάγκη πιστωτικής κάρτας.  
- **Προσωρινή άδεια:** Ζητήστε ένα κλειδί περιορισμένου χρόνου για εκτεταμένη δοκιμή.  
- **Πλήρης αγορά:** Αποκτήστε μια διαρκή άδεια για εμπορική χρήση.  

## Τι είναι η κλάση Viewer;
Η κλάση `Viewer` είναι η βασική μηχανή του GroupDocs.Viewer που φορτώνει ένα έγγραφο και το αποδίδει στη ζητούμενη μορφή εξόδου. Απομονώνει τη διαχείριση τύπων αρχείων ώστε να μπορείτε να εστιάσετε στη λογική της επιχείρησης αντί για την ανάλυση των εσωτερικών στοιχείων του λογιστικού φύλλου.  

## Πώς να μετατρέψετε Numbers σε HTML με το GroupDocs.Viewer για Java;

`HtmlViewOptions` καθορίζει ρυθμίσεις για την απόδοση HTML, όπως ενσωμάτωση πόρων ή σύνδεση εξωτερικών αρχείων.  
Φορτώστε το αρχείο Numbers, διαμορφώστε τις επιλογές HTML και καλέστε `viewer.view()`. Η μέθοδος `HtmlViewOptions.forEmbeddedResources()` ενσωματώνει CSS και εικόνες απευθείας στο HTML, καθιστώντας το αποτέλεσμα ιδανικό για ενσωμάτωση σε ιστοσελίδα χωρίς πρόσθετους πόρους.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Γιατί είναι σημαντικό:** Οι ενσωματωμένοι πόροι διατηρούν την προεπισκόπηση αυτόνομη, εξαλείφοντας σπασμένους συνδέσμους εικόνων και απλοποιώντας την ανάπτυξη CDN.  

## Πώς να μετατρέψετε Numbers σε JPG με το GroupDocs.Viewer για Java;

`JpgViewOptions` διαμορφώνει την έξοδο JPEG, επιτρέποντας ρυθμίσεις ποιότητας και μεγέθους για κάθε αποδοθέντα σελίδα.  
Μπορείτε να μετατρέψετε κάθε σελίδα λογιστικού φύλλου σε στιγμιότυπο JPEG. Ρυθμίστε την παράμετρο `quality` για να εξισορροπήσετε το μέγεθος αρχείου και την οπτική πιστότητα, χρήσιμο όταν χρειάζεστε ελαφριές εικόνες για κοινωνικά δίκτυα ή ενημερωτικά δελτία email.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Συμβουλή:** Για ταχύτερη επεξεργασία μεγάλων βιβλίων εργασίας, μειώστε την ποιότητα στο 70 % – η οπτική επίδραση είναι ελάχιστη ενώ το μέγεθος του αρχείου μειώνεται δραστικά.  

## Πώς να μετατρέψετε Numbers σε PNG με το GroupDocs.Viewer για Java;

`PngViewOptions` διαμορφώνει την έξοδο PNG, υποστηρίζοντας συμπίεση χωρίς απώλειες και ρυθμίσεις ανάλυσης για εικόνες υψηλής ποιότητας.  
Το PNG προσφέρει συμπίεση χωρίς απώλειες, διατηρώντας κάθε pixel ακριβώς όπως αποδίδεται. Χρησιμοποιήστε την ιδιότητα `resolution` για να αυξήσετε το DPI όταν χρειάζεστε γραφικά έτοιμα για εκτύπωση σε αναφορές ή PDF.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Επαγγελματική συμβουλή:** Ορίστε `options.setResolution(300)` για έξοδο υψηλής ανάλυσης που φαίνεται καθαρό σε εκτυπωμένες σελίδες.  

## Πώς να μετατρέψετε Numbers σε PDF με το GroupDocs.Viewer για Java;

`PdfViewOptions` ορίζει τις επιλογές απόδοσης PDF, συμπεριλαμβανομένης της ενσωμάτωσης γραμματοσειρών, της συμπίεσης και του ελέγχου μεγέθους σελίδας.  
Το αντικείμενο `PdfViewOptions` σας επιτρέπει να ενσωματώσετε γραμματοσειρές, να ελέγξετε το μέγεθος της σελίδας και να διατηρήσετε την αρχική διάταξη του βιβλίου εργασίας Numbers. Η μετατροπή εκτελείται με μία κλήση, παράγοντας ένα αναζητήσιμο, μη‑επεξεργάσιμο PDF που είναι ιδανικό για αρχειοθέτηση ή συμμόρφωση.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Κύρια ρύθμιση:** Ενεργοποιήστε `options.setCompress(true)` για να μειώσετε το μέγεθος του PDF χωρίς να θυσιάσετε την ποιότητα, κάτι που είναι απαραίτητο για αποθήκες εγγράφων μεγάλης κλίμακας.  

## Γιατί να χρησιμοποιήσετε το GroupDocs.Viewer για Java;

Το GroupDocs.Viewer υποστηρίζει **πάνω από 100 μορφές αρχείων**, συμπεριλαμβανομένου του Apple Numbers, και μπορεί να αποδώσει λογιστικά φύλλα εκατοντάδων σελίδων χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Τα benchmarks δείχνουν ότι ένα αρχείο Numbers 250 σελίδων μετατρέπεται σε PDF σε λιγότερο από 8 δευτερόλεπτα σε τυπική CPU 2.5 GHz, παρέχοντας ταχύτητα και αξιοπιστία για επιχειρησιακές διαδικασίες.  

## Πρακτικές εφαρμογές
- **Ενσωμάτωση web:** Απόδοση σε HTML για έναν διαδραστικό προβολέα λογιστικών φύλλων που λειτουργεί σε όλα τα προγράμματα περιήγησης χωρίς πρόσθετα.  
- **Κοινή χρήση περιεχομένου:** Μετατροπή σε JPG/PNG για γρήγορη ενσωμάτωση εικόνων σε ενημερωτικά δελτία, εφαρμογές συνομιλίας ή κοινωνικά δίκτυα.  
- **Εταιρικό DMS:** Χρησιμοποιήστε **πώς να μετατρέψετε numbers** σε PDF για να αποθηκεύσετε μια μη‑επεξεργάσιμη, αναζητήσιμη έκδοση του λογιστικού φύλλου για συμμόρφωση και ελεγκτικά ίχνη.  

## Σκέψεις απόδοσης
- **Διαχείριση πόρων:** Πάντα δημιουργήστε το `Viewer` μέσα σε μπλοκ try‑with‑resources (όπως φαίνεται) ώστε οι εγγενείς πόροι να απελευθερώνονται άμεσα.  
- **Μεγάλα βιβλία εργασίας:** Επεξεργαστείτε σελίδα‑με‑σελίδα και ρέξτε την έξοδο για να διατηρήσετε τη χρήση μνήμης κάτω από 100 MB, ακόμη και για αρχεία 500 σελίδων.  
- **Ασφάλεια νήματος:** Δημιουργήστε ξεχωριστό αντικείμενο `Viewer` ανά νήμα· η κλάση δεν είναι thread‑safe, επομένως η κοινή χρήση ενός αντικειμένου μπορεί να προκαλέσει συνθήκες αγώνα.  

## Συνηθισμένα προβλήματα και αντιμετώπιση
- **Απουσία γραμματοσειρών:** Εάν το παραγόμενο PDF φαίνεται διαφορετικό, βεβαιωθείτε ότι οι απαιτούμενες γραμματοσειρές είναι διαθέσιμες στον διακομιστή ή ενσωματώστε τις χρησιμοποιώντας `PdfViewOptions.setEmbedFonts(true)`.  
- **Κενές σελίδες:** Ελέγξτε ότι το αρχείο Numbers δεν είναι προστατευμένο με κωδικό· το GroupDocs.Viewer αυτή τη στιγμή δεν αποκρυπτογραφεί προστατευμένα βιβλία εργασίας.  
- **Σφάλματα έλλειψης μνήμης:** Για εξαιρετικά μεγάλα αρχεία, ενεργοποιήστε `options.setPageCount(1)` για απόδοση μιας σελίδας τη φορά και συνδυάστε τα αποτελέσματα αργότερα.  

## Συχνές ερωτήσεις

**Q:** Ποιες μορφές αρχείων υποστηρίζει το GroupDocs.Viewer;  
**A:** Πάνω από 100 μορφές, συμπεριλαμβανομένων των DOCX, XLSX, PDF, HTML και Apple Numbers, με πλήρεις δυνατότητες απόδοσης για κάθε μία.  

**Q:** Πώς να διαχειριστώ αποδοτικά μεγάλα αρχεία Numbers;  
**A:** Ρέξτε τη μετατροπή σελίδα‑με‑σελίδα, χρησιμοποιήστε `options.setPageCount()` για περιορισμό της χρήσης μνήμης και εξετάστε τη συμπίεση του PDF εξόδου.  

**Q:** Μπορεί το GroupDocs.Viewer να χρησιμοποιηθεί σε εμπορικό έργο;  
**A:** Ναι—αγοράστε εμπορική άδεια για να αφαιρέσετε τους περιορισμούς της δοκιμής και να λάβετε υποστήριξη παραγωγικού επιπέδου.  

**Q:** Μπορεί να προσαρμοστεί η ποιότητα εξόδου των εικόνων;  
**A:** Απόλυτα. Ρυθμίστε `JpgViewOptions.setQuality(int)` ή `PngViewOptions.setResolution(int)` ώστε να καλύψετε τις απαιτήσεις σας σε μέγεθος‑ποιότητα.  

**Q:** Πού μπορώ να βρω πιο προχωρημένα παραδείγματα χρήσης;  
**A:** Επισκεφθείτε την [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) για αναλυτικούς οδηγούς, παραδείγματα έργων και λεπτομέρειες αναφοράς API.  

## Επόμενα βήματα
Δοκιμάστε τις παραπάνω επιλογές, έπειτα εξερευνήστε πρόσθετες προσαρμογές όπως υδατογράφημα PDF, προσθήκη προστασίας με κωδικό ή ενσωμάτωση του viewer σε υπηρεσία Spring Boot REST. Η [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) παρέχει πλήρη κατάλογο λειτουργιών που μπορείτε να συνδυάσετε.  

## Πόροι
- **Τεκμηρίωση:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Τεκμηρίωση GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Αναφορά API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Αναφορά API:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Λήψη:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Αγορά άδειας:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Δωρεάν δοκιμή:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Προσωρινή άδεια:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Φόρουμ υποστήριξης:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία ενημέρωση:** 2026-08-25  
**Δοκιμάστηκε με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

## Σχετικά Μαθήματα

- [Πώς να μετατρέψετε το Excel σε HTML, JPG, PNG και PDF χρησιμοποιώντας το GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [Πώς να μετατρέψετε το Excel σε HTML και να αποδώσετε κρυμμένες γραμμές & στήλες σε Java με το GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Java Tutorial Απόδοσης Εγγράφων - Μετατροπή αρχείων σε HTML, PDF & Images](/viewer/java/rendering-basics/)