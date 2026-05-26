---
date: '2026-02-23'
description: Μάθετε πώς να μετατρέπετε IGS σε PDF, HTML, JPG και PNG με το GroupDocs.Viewer
  για Java. Ακολουθήστε αυτόν τον οδηγό βήμα‑προς‑βήμα με έτοιμα παραδείγματα κώδικα.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Μετατροπή IGS σε PDF, HTML, JPG & PNG χρησιμοποιώντας το GroupDocs.Viewer Java
type: docs
url: /el/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

-23  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

Translate:

---

**Τελευταία Ενημέρωση:** 2026-02-23  
**Δοκιμή Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

Make sure to keep bold formatting.

Now ensure all markdown formatting preserved.

Check for any other shortcodes: none besides {{CODE_BLOCK_X}}.

Check for any other markdown links: none.

Check for images: we translated alt text.

Check for any other code fences: placeholders only.

Now produce final content.# Μετατροπή IGS σε PDF, HTML, JPG & PNG χρησιμοποιώντας το GroupDocs.Viewer Java

Αν χρειάζεστε **convert IGS to PDF** (ή σε HTML, JPG, PNG) απευθείας από μια εφαρμογή Java, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από όλα όσα χρειάζεστε — από τη ρύθμιση της βιβλιοθήκης μέχρι την απόδοση του 3‑D μοντέλου στη μορφή που ταιριάζει στο έργο σας. Θα δείτε γιατί το GroupDocs.Viewer είναι μια αξιόπιστη επιλογή για γρήγορες, αξιόπιστες μετατροπές και θα λάβετε πρακτικό κώδικα που μπορείτε να ενσωματώσετε στη δική σας λύση.

![Μετατροπή αρχείων IGS σε HTML, JPG, PNG και PDF με το GroupDocs.Viewer για Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Γρήγορες Απαντήσεις
- **Μπορώ να μετατρέψω IGS σε PDF με Java;** Ναι, χρησιμοποιώντας το `PdfViewOptions` του GroupDocs.Viewer.  
- **Ποιοι τύποι εξόδου υποστηρίζονται;** HTML, JPG, PNG και PDF.  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται εμπορική άδεια· διατίθεται δωρεάν δοκιμή για δοκιμές.  
- **Ποια έκδοση Java απαιτείται;** JDK 8 ή νεότερη.  
- **Είναι το Maven ο μοναδικός τρόπος για να προσθέσετε τη βιβλιοθήκη;** Όχι, μπορείτε επίσης να χρησιμοποιήσετε Gradle ή χειροκίνητη προσθήκη JAR.

## Τι είναι το “convert IGS to PDF”;
Η μετατροπή IGS (μια ουδέτερη μορφή αρχείου για δεδομένα 3‑D CAD) σε PDF σημαίνει τη μετατροπή ενός σύνθετου 3‑D μοντέλου σε ένα στατικό, ευρέως προβάλλον έγγραφο. Αυτό είναι χρήσιμο για την κοινή χρήση σχεδίων με ενδιαφερόμενους που δεν διαθέτουν εργαλεία CAD.

## Γιατί να χρησιμοποιήσετε το GroupDocs.Viewer για μετατροπές IGS;
- **Zero‑code CAD rendering** – η βιβλιοθήκη αναλαμβάνει την βαριά δουλειά της ανάλυσης της μορφής IGS.  
- **Multiple output options** – μία κλήση API μπορεί να παράγει HTML, JPG, PNG ή PDF.  
- **Cross‑platform** – λειτουργεί σε οποιοδήποτε OS που υποστηρίζει Java.  
- **Performance‑focused** – γρήγορη απόδοση ακόμη και για μεγάλες συναρμολογήσεις.

## Προαπαιτούμενα
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** εγκατεστημένο και ρυθμισμένο στο IDE σας (IntelliJ IDEA, Eclipse, NetBeans, κ.λπ.)  
- Βασικές γνώσεις Maven (προαιρετικό αλλά συνιστάται)

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

### Απόκτηση Άδειας
GroupDocs.Viewer offers:
- **Free trial** – περιορισμένη χρήση, ιδανική για γρήγορες δοκιμές.  
- **Temporary license** – πλήρες σύνολο λειτουργιών για σύντομη περίοδο αξιολόγησης.  
- **Commercial license** – απεριόριστη χρήση σε παραγωγή.

### Βασική Αρχικοποίηση Viewer
Το παρακάτω απόσπασμα δείχνει πώς να δημιουργήσετε μια παρουσία `Viewer` που δείχνει στο αρχείο IGS σας:

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
Η έξοδος HTML σας παρέχει μια διαδραστική, φιλική προς το πρόγραμμα περιήγησης προβολή του 3‑D μοντέλου.

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

**Κύριο σημείο:** `HtmlViewOptions.forEmbeddedResources()` ενσωματώνει όλα τα απαιτούμενα στοιχεία (CSS, εικόνες) απευθείας στο αρχείο HTML, καθιστώντας το φορητό.

## Απόδοση IGS σε JPG

### Πώς να μετατρέψετε IGS σε JPG;
Οι εικόνες JPG είναι ιδανικές για μικρογραφίες ή γρήγορες προεπισκοπήσεις.

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

Μπορείτε να ρυθμίσετε το `JpgViewOptions` για να ελέγξετε την ανάλυση και την ποιότητα συμπίεσης.

## Απόδοση IGS σε PNG

### Πώς να μετατρέψετε IGS σε PNG;
Το PNG υποστηρίζει διαφάνεια, κάτι που είναι χρήσιμο για επικάλυψη του μοντέλου σε διαφορετικά φόντα.

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

Δοκιμάστε το `PngViewOptions` για να βρείτε την καλύτερη ισορροπία μεταξύ μεγέθους αρχείου και οπτικής πιστότητας.

## Απόδοση IGS σε PDF

### Πώς να μετατρέψετε IGS σε PDF;
Το PDF είναι η προτιμώμενη μορφή για την κοινή χρήση λεπτομερούς τεκμηρίωσης σχεδίου. Αυτή η ενότητα απευθύνεται άμεσα στη βασική λέξη-κλειδί **convert IGS to PDF**.

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

`PdfViewOptions` σας επιτρέπει να ελέγξετε τη διάταξη σελίδας, την ποιότητα εικόνας και το αν θα ενσωματωθούν οι γραμματοσειρές.

## Πρακτικές Εφαρμογές
- **Web portals** – ενσωματώστε μοντέλα που αποδίδονται σε HTML απευθείας σε διαμορφωτές προϊόντων.  
- **Marketing assets** – δημιουργήστε εικόνες JPG/PNG υψηλής ανάλυσης για φυλλάδια.  
- **Technical documentation** – συμπεριλάβετε αποδόσεις PDF μοντέλων CAD σε εγχειρίδια χρήστη.  
- **Quality assurance** – αυτοματοποιήστε τη δημιουργία μικρογραφιών για μεγάλες παρτίδες αρχείων IGS.

## Συχνά Προβλήματα & Λύσεις

| Πρόβλημα | Λύση |
|-------|----------|
| **Output folder not found** | Επαληθεύστε τη διαδρομή που περνάτε στο `Path outputDirectory` και βεβαιωθείτε ότι η διαδικασία Java έχει δικαιώματα εγγραφής. |
| **Blank pages in PDF** | Βεβαιωθείτε ότι το αρχείο IGS δεν είναι κατεστραμμένο· δοκιμάστε να το ανοίξετε πρώτα σε προβολέα CAD. |
| **Slow rendering for large assemblies** | Αυξήστε τη μνήμη heap του JVM (`-Xmx2g` ή περισσότερο) και εξετάστε την απόδοση σελίδα‑με‑σελίδα χρησιμοποιώντας `viewer.getPageCount()` αν χρειάζεται. |
| **Missing fonts in PDF** | Χρησιμοποιήστε το `PdfViewOptions` για να ενσωματώσετε τις απαιτούμενες γραμματοσειρές ή εγκαταστήστε τις λείπουσες γραμματοσειρές στον διακομιστή. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να μετατρέψω πολλαπλά αρχεία IGS σε μία εκτέλεση;**  
A: Ναι. Επαναλάβετε τη λίστα των διαδρομών αρχείων και καλέστε τη σχετική μέθοδο `view` για κάθε ένα.

**Q: Είναι δυνατόν να προσαρμόσετε το μέγεθος σελίδας PDF;**  
A: Απόλυτα. Το `PdfViewOptions` παρέχει τη μέθοδο `setPageSize(PageSize.A4)` και παρόμοιες.

**Q: Χρειάζομαι ξεχωριστή άδεια για κάθε μορφή εξόδου;**  
A: Όχι. Μία άδεια GroupDocs.Viewer καλύπτει όλες τις υποστηριζόμενες μορφές.

**Q: Πόσο μεγάλο μπορεί να είναι ένα αρχείο IGS πριν μειωθεί η απόδοση;**  
A: Η βιβλιοθήκη διαχειρίζεται αρχεία έως μερικές εκατοντάδες megabytes, αλλά μπορεί να χρειαστεί να διαθέσετε περισσότερη μνήμη JVM για πολύ μεγάλα μοντέλα.

**Q: Μπορώ να αποδώσω μόνο μια συγκεκριμένη προβολή ή προσανατολισμό;**  
A: Το GroupDocs.Viewer αποδίδει την προεπιλεγμένη προβολή. Για προσαρμοσμένους προσανατολισμούς, προεπεξεργαστείτε το αρχείο IGS με ένα εργαλείο CAD πριν από τη μετατροπή.

---

**Τελευταία Ενημέρωση:** 2026-02-23  
**Δοκιμή Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs