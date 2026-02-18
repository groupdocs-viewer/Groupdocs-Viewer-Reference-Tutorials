---
date: '2026-02-18'
description: Μάθετε πώς να μετατρέπετε αρχεία WMZ και WMF σε PDF, HTML, JPG και PNG
  χρησιμοποιώντας το GroupDocs Viewer για Java. Αυτός ο οδηγός καλύπτει το GroupDocs
  Viewer Java και τη μετατροπή διανυσματικών γραφικών σε Java.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Πώς να μετατρέψετε WMZ σε PDF και άλλες μορφές χρησιμοποιώντας το GroupDocs
  Viewer για Java
type: docs
url: /el/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

25.2 for Java"

**Author:** GroupDocs => "**Συγγραφέας:** GroupDocs"

Make sure to keep bold formatting.

Now ensure we didn't miss any markdown links. There were none.

Now produce final content.# Πώς να Μετατρέψετε WMZ σε PDF και Άλλες Μορφές Χρησιμοποιώντας το GroupDocs Viewer για Java

Η μετατροπή αρχείων WMZ (Web Metafile) και WMF (Windows Metafile) σε πιο προσβάσιμες μορφές—ιδιαίτερα **convert WMZ to PDF**—μπορεί να είναι δύσκολη επειδή αυτές οι μορφές διανυσματικών γραφικών αποθηκεύουν οδηγίες σχεδίασης αντί για δεδομένα εικονοστοιχείων. Με το **GroupDocs Viewer for Java**, μπορείτε να αποδώσετε έγγραφα WMZ/WMF σε HTML, JPG, PNG, **PDF**, και άλλες δημοφιλείς μορφές με μόνο λίγες γραμμές κώδικα.

![Μετατροπή Εγγράφων WMZ/WMF με το GroupDocs.Viewer για Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

Σε αυτό το εκπαιδευτικό υλικό θα μάθετε πώς να ρυθμίσετε τη βιβλιοθήκη, να αποδώσετε αρχεία WMZ/WMF στην επιθυμητή έξοδο και να αντιμετωπίσετε κοινά προβλήματα. Στο τέλος, θα μπορείτε να ενσωματώσετε το **groupdocs viewer java** στις εφαρμογές Java σας για **java convert vector graphics** γρήγορα και αξιόπιστα.

## Γρήγορες Απαντήσεις
- **Σε ποιες μορφές μπορεί να μετατραπεί το WMZ/WMF;** HTML, JPG, PNG και PDF υποστηρίζονται πλήρως.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν δοκιμή λειτουργεί για δοκιμές· μια εμπορική άδεια αφαιρεί τους περιορισμούς αξιολόγησης.  
- **Ποια έκδοση της Java απαιτείται;** Συνιστάται Java 8 ή νεότερη.  
- **Μπορώ να αποδώσω μόνο συγκεκριμένες σελίδες;** Ναι, μπορείτε να καθορίσετε εύρος σελίδων στις επιλογές προβολής.  
- **Ανησυχεί η χρήση μνήμης για μεγάλα αρχεία;** Χρησιμοποιήστε try‑with‑resources και αποδώστε μόνο τις απαραίτητες σελίδες για να διατηρήσετε τη μνήμη χαμηλή.

## Τι είναι το “convert WMZ to PDF”;
Η μετατροπή WMZ σε PDF σημαίνει ότι παίρνετε το διανυσματικό αρχείο WMZ και το rasterize (ή διατηρείτε τα διανυσματικά του δεδομένα) μέσα σε ένα κοντέινερ PDF. Το PDF είναι παγκοσμίως προβλέψιμο, αναζητήσιμο και εκτυπώσιμο, καθιστώντας το ιδανικό για αρχειοθέτηση και κοινή χρήση γραφικών WMZ.

## Γιατί να χρησιμοποιήσετε το GroupDocs Viewer για Java για τη μετατροπή διανυσματικών γραφικών;
- **Υψηλή πιστότητα**: Η βιβλιοθήκη διατηρεί την αρχική ποιότητα σχεδίασης, είτε εξάγετε σε PDF είτε σε PNG.  
- **Μηδενικές εξωτερικές εξαρτήσεις**: Δεν χρειάζονται εγγενείς βιβλιοθήκες Windows· όλα εκτελούνται σε οποιαδήποτε πλατφόρμα με JDK.  
- **Απλό API**: Μία παρουσία `Viewer` και μία κλήση `view` διαχειρίζονται ολόκληρη τη μετατροπή.  
- **Κλιμακώσιμο**: Λειτουργεί εξίσου καλά για εικονίδια μονής σελίδας και τεχνικά σχέδια πολλαπλών σελίδων.

## Προαπαιτούμενα

### Απαιτούμενες Βιβλιοθήκες
- **GroupDocs.Viewer for Java** – η κύρια μηχανή απόδοσης.  
- Java Development Kit (JDK) 8+.

### Ρύθμιση Περιβάλλοντος
- IDE όπως IntelliJ IDEA ή Eclipse.  
- Maven για διαχείριση εξαρτήσεων (ή Gradle αν προτιμάτε).

### Προαπαιτούμενες Γνώσεις
- Εξοικείωση με Java file I/O (`java.nio.file.Path`).  
- Βασική κατανόηση του πώς οι προβολείς εγγράφων αποδίδουν περιεχόμενο.

## Ρύθμιση του GroupDocs.Viewer για Java

Προσθέστε το αποθετήριο και την εξάρτηση στο `pom.xml` σας:

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

> **Συμβουλή άδειας:** Χρησιμοποιήστε μια δωρεάν δοκιμή για αξιολόγηση, στη συνέχεια εφαρμόστε προσωρινή ή αγορασμένη άδεια για να ξεκλειδώσετε πλήρη λειτουργικότητα.

Μόλις επιλυθεί η εξάρτηση, μπορείτε να δημιουργήσετε μια παρουσία `Viewer` που θα επαναχρησιμοποιείται για κάθε βήμα μετατροπής.

## Οδηγός Υλοποίησης

Θα περάσουμε από τέσσερα σενάρια μετατροπής: HTML, JPG, PNG και PDF. Κάθε παράδειγμα ακολουθεί το ίδιο μοτίβο—ορίζετε διαδρομή εξόδου, δημιουργείτε `Viewer` με το πηγαίο αρχείο WMZ, ρυθμίζετε τις κατάλληλες επιλογές προβολής και καλείτε `view`.

### Απόδοση WMZ/WMF σε HTML

#### Επισκόπηση
Η έξοδος HTML σας επιτρέπει να ενσωματώσετε το γραφικό απευθείας σε ιστοσελίδες, με όλους τους πόρους (εικόνες, CSS) να περιέχονται σε ένα μόνο αρχείο.

**Βήμα 1: Ορίστε τη Διαδρομή Καταλόγου Εξόδου**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Βήμα 2: Αρχικοποιήστε το Viewer και Αποδώστε σε HTML**

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

**Βήμα 1: Ορίστε τη Διαδρομή Καταλόγου Εξόδου**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Βήμα 2: Αρχικοποιήστε το Viewer και Αποδώστε σε JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Απόδοση WMZ/WMF σε PNG

#### Επισκόπηση
Το PNG υποστηρίζει διαφάνεια, καθιστώντας το ιδανικό για γραφικά που πρέπει να ενσωματωθούν με διαφορετικά υπόβαθρα.

**Βήμα 1: Ορίστε τη Διαδρομή Καταλόγου Εξόδου**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Βήμα 2: Αρχικοποιήστε το Viewer και Αποδώστε σε PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Απόδοση WMZ/WMF σε PDF

#### Επισκόπηση
Το PDF παρέχει ένα ανεξάρτητο από πλατφόρμα, αναζητήσιμο έγγραφο που διατηρεί την αρχική διάταξη.

**Βήμα 1: Ορίστε τη Διαδρομή Καταλόγου Εξόδου**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Βήμα 2: Αρχικοποιήστε το Viewer και Αποδώστε σε PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Συχνά Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **OutOfMemoryError** σε μεγάλα αρχεία WMZ | Το Viewer φορτώνει ολόκληρο το έγγραφο στη μνήμη | Αποδώστε μία σελίδα τη φορά χρησιμοποιώντας `PageStreamViewOptions` ή αυξήστε το heap της JVM (`-Xmx`). |
| **Missing fonts** σε PDF | Η γραμματοσειρά δεν είναι ενσωματωμένη στην πηγή WMZ | Εγκαταστήστε τις απαιτούμενες γραμματοσειρές στο σύστημα ή χρησιμοποιήστε `FontSettings` για να παρέχετε προσαρμοσμένες γραμματοσειρές. |
| **Blank PNG output** | Λανθασμένη διαδρομή εξόδου ή ανεπαρκή δικαιώματα εγγραφής | Επαληθεύστε ότι το `outputDirectory` υπάρχει και ότι η εφαρμογή έχει δικαιώματα εγγραφής. |
| **HTML resources not loading** | Χρήση `forExternalResources` χωρίς αντιγραφή αρχείων | Παραμείνετε με `forEmbeddedResources` για ένα αυτόνομο αρχείο HTML. |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να μετατρέψω WMF σε PNG χρησιμοποιώντας τον ίδιο κώδικα;**  
Α: Ναι. Το παράδειγμα PNG λειτουργεί και για αρχεία WMZ και WMF· απλώς αντικαταστήστε `TestFiles.SAMPLE_WMZ` με την πηγή WMF σας.

**Ε: Είναι δυνατόν να μετατρέψω μόνο ένα υποσύνολο σελίδων;**  
Α: Απόλυτα. Χρησιμοποιήστε `PdfViewOptions` (ή τις αντίστοιχες επιλογές για άλλες μορφές) και καλέστε `setPageNumbers(List<Integer>)` πριν από την απόδοση.

**Ε: Χρειάζομαι ξεχωριστή άδεια για κάθε μορφή εξόδου;**  
Α: Όχι. Μία άδεια GroupDocs Viewer καλύπτει όλες τις υποστηριζόμενες μορφές, συμπεριλαμβανομένων HTML, JPG, PNG και PDF.

**Ε: Πώς επηρεάζει η “java convert vector graphics” την απόδοση;**  
Α: Η μετατροπή διανύσματος σε raster είναι εντατική σε CPU. Για μεγάλες παρτίδες, σκεφτείτε πολυνηματισμό και επαναχρησιμοποίηση μιας μοναδικής παρουσίασης `Viewer` σε πολλά αρχεία.

**Ε: Θα διατηρήσει το PDF την ποιότητα του διανύσματος ή θα rasterize;**  
Α: Κατά τη μετατροπή WMZ/WMF σε PDF, το GroupDocs Viewer διατηρεί τις διανυσματικές οδηγίες όπου είναι δυνατόν, παράγοντας ένα κλιμακώσιμο PDF.

## Συμπέρασμα

Τώρα έχετε έναν πλήρη, έτοιμο για παραγωγή οδηγό για **convert WMZ to PDF** και άλλες κοινές μορφές χρησιμοποιώντας το **GroupDocs Viewer for Java**. Είτε δημιουργείτε μια υπηρεσία web που εξυπηρετεί γραφικά σε πραγματικό χρόνο είτε ένα εργαλείο αρχειοθέτησης που αποθηκεύει έγγραφα ως PDF, τα παραπάνω βήματα θα σας βοηθήσουν να το πετύχετε γρήγορα.

---

**Τελευταία Ενημέρωση:** 2026-02-18  
**Δοκιμή Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs