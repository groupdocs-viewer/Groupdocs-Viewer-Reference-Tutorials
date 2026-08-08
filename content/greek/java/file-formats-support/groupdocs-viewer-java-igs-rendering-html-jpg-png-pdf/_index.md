---
date: '2026-08-08'
description: Μάθετε πώς να μετατρέπετε IGS σε PDF, HTML, JPG και PNG χρησιμοποιώντας
  το GroupDocs.Viewer για Java. Step‑by‑step guide, prerequisites, and troubleshooting
  for Java developers.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Μετατρέψτε IGS σε PDF, HTML, JPG και PNG χρησιμοποιώντας το GroupDocs.Viewer
  για Java. Detailed setup, code snippets, and troubleshooting for Java developers.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Μετατροπή IGS σε PDF, HTML, JPG & PNG με το GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Μετατροπή IGS σε PDF, HTML, JPG & PNG με το GroupDocs.Viewer Java
type: docs
url: /el/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Μετατροπή IGS σε PDF, HTML, JPG & PNG με το GroupDocs.Viewer Java

Αν χρειάζεστε **convert IGS to PDF** (ή σε HTML, JPG, PNG) απευθείας από μια εφαρμογή Java, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα καλύψουμε όλα όσα χρειάζεστε—από την εγκατάσταση της βιβλιοθήκης μέχρι την απόδοση του 3‑D μοντέλου στη μορφή που ταιριάζει στο έργο σας. Θα καταλάβετε γιατί το GroupDocs.Viewer είναι μια αξιόπιστη επιλογή για γρήγορες, αξιόπιστες μετατροπές και θα λάβετε έτοιμα κομμάτια κώδικα που μπορείτε να ενσωματώσετε στη δική σας λύση.

![Μετατροπή αρχείων IGS σε HTML, JPG, PNG και PDF με το GroupDocs.Viewer για Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Γρήγορες απαντήσεις
- **Μπορώ να μετατρέψω IGS σε PDF με Java;** Ναι, χρησιμοποιήστε το `PdfViewOptions` μαζί με το `Viewer` API.  
- **Ποιοι τύποι εξόδου υποστηρίζονται;** HTML, JPG, PNG και PDF υποστηρίζονται εγγενώς.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια· μια δωρεάν δοκιμή σας επιτρέπει να δοκιμάσετε τις βασικές λειτουργίες.  
- **Ποια έκδοση Java απαιτείται;** JDK 8 ή νεότερη· η βιβλιοθήκη λειτουργεί επίσης σε Java 11, 17 και μεταγενέστερες.  
- **Είναι το Maven ο μοναδικός τρόπος για να προσθέσετε τη βιβλιοθήκη;** Όχι, μπορείτε επίσης να χρησιμοποιήσετε Gradle ή να προσθέσετε χειροκίνητα τα αρχεία JAR στο classpath σας.

## Τι είναι η μετατροπή IGS σε PDF;
Η μετατροπή IGS σε PDF σημαίνει τη μετατροπή ενός ουδέτερου 3‑D αρχείου CAD σε ένα στατικό, καθολικά προβληματικό έγγραφο. Αυτό σας επιτρέπει να μοιράζεστε οπτικά σχέδια με ενδιαφερόμενους που δεν διαθέτουν εργαλεία CAD, να ενσωματώνετε την απόδοση σε αναφορές ή να αρχειοθετείτε το μοντέλο για σκοπούς συμμόρφωσης.

## Γιατί να χρησιμοποιήσετε το GroupDocs.Viewer για μετατροπές IGS;
Το GroupDocs.Viewer επεξεργάζεται αρχεία IGS χωρίς την ανάγκη εξωτερικού λογισμικού CAD. Υποστηρίζει **50+ μορφές εισόδου και εξόδου**, μπορεί να αποδώσει συναρμολογήσεις που περιέχουν **εκατοντάδες εξαρτήματα** διατηρώντας τη χρήση μνήμης κάτω από **200 MB**, και παρέχει αποτελέσματα σε λιγότερο από **2 δευτερόλεπτα** για τυπικά μοντέλα σε έναν τυπικό διακομιστή. Αυτά τα μετρητά οφέλη το καθιστούν μια υψηλής απόδοσης, οικονομικά αποδοτική επιλογή για επιχειρησιακές γραμμές παραγωγής.

## Προαπαιτούμενα
- **GroupDocs.Viewer for Java** ≥ 25.2 (η τελευταία σταθερή έκδοση).  
- **JDK 8+** εγκατεστημένο και ρυθμισμένο στο IDE σας (IntelliJ IDEA, Eclipse, NetBeans κ.λπ.).  
- Βασικές γνώσεις Maven (προαιρετικό αλλά συνιστάται για τη διαχείριση εξαρτήσεων).  

## Ρύθμιση του GroupDocs.Viewer για Java

### Εξάρτηση Maven
Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση Viewer στο `pom.xml` σας:

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
Το GroupDocs.Viewer προσφέρει τρεις επιλογές αδειοδότησης:
- **Free trial** – περιορισμένη χρήση, ιδανική για γρήγορες δοκιμές proof‑of‑concept.  
- **Temporary license** – πλήρες σύνολο λειτουργιών για σύντομη περίοδο αξιολόγησης, ιδανική για πιλοτικά έργα.  
- **Commercial license** – απεριόριστη χρήση σε παραγωγή, περιλαμβάνει προτεραιότητα υποστήριξης και ενημερώσεις.

### Βασική αρχικοποίηση του viewer
Η κλάση `Viewer` είναι το σημείο εισόδου για όλες τις λειτουργίες απόδοσης. Φορτώνει το αρχείο προέλευσης, αναλύει τη μορφή και εκθέτει μεθόδους για την παραγωγή της επιθυμητής εξόδου.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Απόδοση IGS σε HTML

### Πώς να μετατρέψετε IGS σε HTML;
Φορτώστε το αρχείο IGS με μια παρουσία `Viewer` και περάστε ένα αντικείμενο `HtmlViewOptions` που ενσωματώνει όλα τα απαιτούμενα assets. Η κλήση επιστρέφει ένα ενιαίο αρχείο HTML που περιέχει την πλήρη 3‑D προβολή, καθιστώντας εύκολη την ενσωμάτωση σε ιστοσελίδες. Μπορείτε επίσης να προσαρμόσετε την απόδοση ορίζοντας επιλογές όπως το μέγεθος σελίδας, το χρώμα φόντου και αν θα συμπεριληφθούν διαδραστικοί έλεγχοι.  
`HtmlViewOptions` διαμορφώνει πώς δημιουργείται η έξοδος HTML, συμπεριλαμβανομένης της ενσωμάτωσης πόρων και της διάταξης σελίδας.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Απόδοση IGS σε JPG

### Πώς να μετατρέψετε IGS σε JPG;
Δημιουργήστε ένα αντικείμενο `JpgViewOptions`, ρυθμίστε την επιθυμητή ανάλυση και την ποιότητα συμπίεσης, και αφήστε το `Viewer` να δημιουργήσει raster εικόνες για κάθε σελίδα του μοντέλου. Τα παραγόμενα αρχεία JPG μπορούν να αποθηκευτούν σε έναν καθορισμένο φάκελο, και μπορείτε να προσαρμόσετε την παράμετρο ποιότητας για να ισορροπήσετε το μέγεθος αρχείου με την οπτική πιστότητα, κάτι χρήσιμο για μικρογραφίες ή εκτυπώσεις υψηλής ανάλυσης.  
`JpgViewOptions` καθορίζει ρυθμίσεις για τη δημιουργία εικόνων JPG όπως ανάλυση, ποιότητα και φάκελο εξόδου.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Απόδοση IGS σε PNG

### Πώς να μετατρέψετε IGS σε PNG;
Η κλάση `PngViewOptions` σας επιτρέπει να παράγετε εικόνες χωρίς απώλειες με προαιρετική διαφάνεια. Αυτή η μορφή είναι ιδανική για επικάλυψη του μοντέλου σε χρωματιστά φόντα σε υλικό μάρκετινγκ. Μπορείτε επίσης να ορίσετε την ανάλυση και το χρώμα φόντου ώστε να ταιριάζει με τις οδηγίες της μάρκας σας, εξασφαλίζοντας συνεπή εμφάνιση σε όλα τα παραγόμενα assets.  
`PngViewOptions` ορίζει παραμέτρους για την απόδοση PNG, συμπεριλαμβανομένης της ανάλυσης, της διαφάνειας και του χρώματος φόντου.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Απόδοση IGS σε PDF

### Πώς να μετατρέψετε IGS σε PDF;
Χρησιμοποιήστε το `PdfViewOptions` για να δημιουργήσετε ένα σελιδοποιημένο PDF που διατηρεί τη οπτική διάταξη του 3‑D μοντέλου. Μπορείτε επίσης να ενσωματώσετε γραμματοσειρές και να ελέγξετε το μέγεθος της σελίδας ώστε να ταιριάζει με τις οδηγίες εταιρικής ταυτότητας. Πρόσθετες ρυθμίσεις σας επιτρέπουν να καθορίσετε την ποιότητα εικόνας, το επίπεδο συμπίεσης και αν θα συμπεριληφθεί πίνακας περιεχομένων για συναρμολογήσεις πολλαπλών σελίδων.  
`PdfViewOptions` ελέγχει τη δημιουργία PDF, επιτρέποντας ρύθμιση μεγέθους σελίδας, ποιότητας εικόνας και ενσωμάτωσης γραμματοσειρών.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Πρακτικές εφαρμογές
- **Web portals** – ενσωματώστε μοντέλα που αποδίδονται σε HTML απευθείας σε διαμορφωτές προϊόντων, επιτρέποντας στους πελάτες να περιστρέφουν και να ζουμάρουν χωρίς εγκατάσταση plugins.  
- **Marketing assets** – δημιουργήστε εικόνες υψηλής ανάλυσης JPG/PNG για φυλλάδια, παρουσιάσεις και αναρτήσεις στα κοινωνικά δίκτυα.  
- **Technical documentation** – συμπεριλάβετε αποδόσεις PDF μοντέλων CAD σε εγχειρίδια χρήστη, διασφαλίζοντας ότι οι μηχανικοί μπορούν να δουν τα σχέδια εκτός σύνδεσης.  
- **Quality assurance** – αυτοματοποιήστε τη δημιουργία μικρογραφιών για χιλιάδες αρχεία IGS, επιταχύνοντας τις ροές εργασίας οπτικού ελέγχου.

## Συνηθισμένα προβλήματα & λύσεις

| Πρόβλημα | Λύση |
|-------|----------|
| **Ο φάκελος εξόδου δεν βρέθηκε** | Επαληθεύστε τη διαδρομή που περνάτε στο `Path outputDirectory` και βεβαιωθείτε ότι η διαδικασία Java έχει δικαιώματα εγγραφής στον προορισμό. |
| **Κενές σελίδες στο PDF** | Επιβεβαιώστε ότι το αρχείο IGS προέλευσης δεν είναι κατεστραμμένο· ανοίξτε το πρώτα σε έναν εγγενή προβολέα CAD. |
| **Αργή απόδοση για μεγάλες συναρμολογήσεις** | Αυξήστε τη μνήμη heap της JVM (`-Xmx2g` ή περισσότερο) και εξετάστε την απόδοση σελίδα‑με‑σελίδα χρησιμοποιώντας `viewer.getPageCount()` για επεξεργασία τμημάτων. |
| **Απουσία γραμματοσειρών στο PDF** | Χρησιμοποιήστε το `PdfViewOptions` για να ενσωματώσετε τις απαιτούμενες γραμματοσειρές ή εγκαταστήστε τις ελλείπουσες γραμματοσειρές στον διακομιστή που φιλοξενεί την υπηρεσία μετατροπής. |

## Συχνές ερωτήσεις

**Q: Μπορώ να μετατρέψω πολλαπλά αρχεία IGS σε μια εκτέλεση;**  
A: Ναι. Επανάλαβε πάνω σε μια συλλογή διαδρομών αρχείων και κάλεσε τη σχετική μέθοδο `view` για κάθε αρχείο μέσα στην ίδια παρουσία `Viewer`.

**Q: Είναι δυνατόν να προσαρμόσετε το μέγεθος σελίδας PDF;**  
A: Απόλυτα. Το `PdfViewOptions` προσφέρει `setPageSize(PageSize.A4)`, `PageSize.Letter` και προσαρμοσμένες διαστάσεις μέσω `setCustomSize(width, height)`.

**Q: Χρειάζομαι ξεχωριστή άδεια για κάθε μορφή εξόδου;**  
A: Όχι. Μία άδεια GroupDocs.Viewer καλύπτει όλες τις υποστηριζόμενες μορφές, συμπεριλαμβανομένων HTML, JPG, PNG και PDF.

**Q: Πόσο μεγάλο μπορεί να είναι ένα αρχείο IGS πριν υποχωρήσει η απόδοση;**  
A: Η βιβλιοθήκη επεξεργάζεται αξιόπιστα αρχεία έως **500 MB**· για μοντέλα μεγαλύτερα από 200 MB, διαθέστε επιπλέον μνήμη JVM και εξετάστε την απόδοση σε παρτίδες.

**Q: Μπορώ να αποδώσω μόνο μια συγκεκριμένη προβολή ή προσανατολισμό;**  
A: Το GroupDocs.Viewer αποδίδει τον προεπιλεγμένο προσανατολισμό που ορίζεται στο αρχείο IGS. Για προσαρμοσμένες προβολές, προεπεξεργαστείτε το αρχείο με εργαλείο CAD ή προσαρμόστε το μοντέλο πριν από τη μετατροπή.

---

**Τελευταία ενημέρωση:** 2026-08-08  
**Δοκιμή με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

## Σχετικά μαθήματα

- [μετατροπή cdr σε html, jpg, png, pdf με το GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Πώς να μετατρέψετε pdf σε html και να βελτιστοποιήσετε την ποιότητα εικόνας σε Java με το GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)