---
date: '2026-02-23'
description: Μάθετε πώς να ορίζετε στοιχεία ανά σελίδα, να ενσωματώνετε HTML πόρων
  και να μετατρέπετε μαζικά αρχεία σε HTML μονής ή πολλαπλής σελίδας χρησιμοποιώντας
  το GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Ορισμός στοιχείων ανά σελίδα: Μετατροπή αρχείων σε HTML με το GroupDocs.Viewer
  Java'
type: docs
url: /el/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Ορισμός Στοιχείων ανά Σελίδα: Μετατροπή Αρχείων Συμπιεσμένων σε HTML με GroupDocs.Viewer Java

Η μετατροπή αρχείων συμπιεσμένων όπως ZIP ή RAR σε HTML φιλικό προς το web είναι συχνή ανάγκη όταν θέλετε να μοιραστείτε ή να ελέγξετε έγγραφα απευθείας σε έναν περιηγητή. Σε αυτόν τον οδηγό θα μάθετε **πώς να ορίσετε στοιχεία ανά σελίδα** κατά την απόδοση των αρχείων συμπιεσμένων, πώς να ενσωματώσετε resources HTML για αυτόνομη έξοδο και πώς να μετατρέψετε παρτίδες αρχείων συμπιεσμένων αποδοτικά με το GroupDocs.Viewer Java.

![Μετατροπή Αρχείων Συμπιεσμένων σε HTML με GroupDocs.Viewer για Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Γρήγορες Απαντήσεις
- **Τι ελέγχει η επιλογή “set items per page”;** Καθορίζει πόσα αρχεία ή φάκελοι από ένα αρχείο συμπιεσμένο εμφανίζονται σε κάθε παραγόμενο HTML αρχείο.  
- **Μπορώ να ενσωματώσω εικόνες και CSS απευθείας στο HTML;** Ναι – χρησιμοποιήστε την επιλογή `forEmbeddedResources` για ενσωμάτωση resources HTML.  
- **Είναι δυνατή η μετατροπή παρτίδας;** Απόλυτα· μπορείτε να επαναλάβετε τη διαδικασία για μια συλλογή αρχείων συμπιεσμένων και να αποδώσετε το καθένα με τις ίδιες ρυθμίσεις.  
- **Χρειάζεται Maven για να χρησιμοποιήσω το GroupDocs.Viewer;** Ναι, προσθέστε την εξάρτηση `maven groupdocs viewer` όπως φαίνεται παρακάτω.  
- **Ποιοι μορφότυποι εξόδου υποστηρίζονται;** Διατίθενται τόσο HTML μίας σελίδας Java όσο και HTML πολλαπλών σελίδων Java.

## Τι είναι το «set items per page» στο GroupDocs.Viewer;
Η ρύθμιση **set items per page** ανήκει στις επιλογές απόδοσης αρχείων συμπιεσμένων. Λέει στον viewer πόσες καταχωρήσεις του αρχείου (αρχεία ή φάκελοι) πρέπει να εμφανίζονται σε κάθε HTML σελίδα όταν δημιουργείτε ένα έγγραφο HTML πολλαπλών σελίδων. Η προσαρμογή αυτής της τιμής βοηθά στην εξισορρόπηση του μεγέθους της σελίδας και της ταχύτητας πλοήγησης, ειδικά για μεγάλα αρχεία συμπιεσμένων.

## Γιατί να ενσωματώσετε resources HTML;
Η ενσωμάτωση resources (εικόνες, CSS, γραμματοσειρές) απευθείας μέσα στο HTML αρχείο δημιουργεί ένα ενιαίο, φορητό έγγραφο που μπορεί να ανοιχθεί χωρίς εξωτερικά αρχεία. Αυτό είναι ιδανικό για συνημμένα email, προβολή εκτός σύνδεσης ή ενσωμάτωση της εξόδου σε άλλες ιστοσελίδες.

## Προαπαιτούμενα

- **Απαιτούμενες Βιβλιοθήκες:** Συμπεριλάβετε το GroupDocs.Viewer έκδοση 25.2 ή νεότερη.  
- **Περιβάλλον:** Εγκατεστημένο και ρυθμισμένο Java Development Kit (JDK).  
- **Γνώση:** Βασικές γνώσεις Java και διαχείρισης εξαρτήσεων Maven.  

## Ρύθμιση Maven GroupDocs Viewer

Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση viewer στο `pom.xml` σας:

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
Το GroupDocs.Viewer προσφέρει **σύνδεσμο δωρεάν δοκιμής**, προσωρινή άδεια ή πλήρη επιλογή αγοράς. Επιλέξτε αυτή που ταιριάζει στο χρονοδιάγραμμα του έργου σας.

### Βασική Αρχικοποίηση
Μετά τη ρύθμιση Maven, φέρετε τον viewer στον κώδικά σας:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Πώς να Μετατρέψετε Αρχεία Συμπιεσμένων σε HTML Μίας Σελίδας

### Βήμα 1: Ορισμός Καταλόγου Εξόδου
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Βήμα 2: Ορισμός Ονόματος Αρχείου για Έξοδο Μίας Σελίδας
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Βήμα 3: Αρχικοποίηση του Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Βήμα 4: Διαμόρφωση Επιλογών Απόδοσης (ενσωμάτωση resources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Βήμα 5: Απόδοση ως Μία Σελίδα
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Πώς να Μετατρέψετε Αρχεία Συμπιεσμένων σε HTML Πολλαπλών Σελίδων και να Ορίσετε Στοιχεία ανά Σελίδα

### Βήμα 1: Επαναχρησιμοποίηση του Καταλόγου Εξόδου
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Βήμα 2: Ορισμός Μορφής Ονόματος Αρχείου για Πολλαπλές Σελίδες
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Βήμα 3: Επανάληψη Αρχικοποίησης του Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Βήμα 4: Διαμόρφωση Επιλογών Πολλαπλών Σελίδων (ενσωμάτωση resources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Βήμα 5: Ορισμός Στοιχείων ανά Σελίδα (κύρια λέξη-κλειδί σε ενέργεια)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Πρακτικές Εφαρμογές

- **Συστήματα Διαχείρισης Εγγράφων:** Προσθέστε λειτουργία προεπισκόπησης αρχείων συμπιεσμένων χωρίς εγκατάσταση επιπλέον προβολέων.  
- **Ιστοσελίδες:** Προσφέρετε στους χρήστες έναν γρήγορο, χωρίς λήψη τρόπο εξερεύνησης ενσωματωμένων εγγράφων.  
- **Εργαλεία Συνεργασίας:** Επιτρέψτε στις ομάδες να ελέγχουν κοινά αρχεία συμπιεσμένων απευθείας στον περιηγητή.

## Σκέψεις για την Απόδοση

- **Διαχείριση Πόρων:** Παρακολουθείτε τη χρήση μνήμης· εξετάστε τη βελτιστοποίηση του garbage‑collector της JVM για μεγάλες παρτίδες.  
- **Μετατροπή Παρτίδας Αρχείων Συμπιεσμένων:** Επανάληψη μέσω λίστας αρχείων συμπιεσμένων και κλήση της ίδιας λογικής απόδοσης για μέγιστη απόδοση.  
- **Στρατηγική Caching:** Αποθηκεύστε το παραγόμενο HTML σε cache εάν το ίδιο αρχείο συμπιεσμένο προσπελαύνεται συχνά.

## Συχνές Ερωτήσεις

**Q: Τι είναι το GroupDocs.Viewer Java;**  
A: Μια ευέλικτη βιβλιοθήκη για απόδοση εγγράφων—συμπεριλαμβανομένων των αρχείων συμπιεσμένων—σε μορφές όπως HTML, PDF και εικόνες.

**Q: Πώς μπορώ να αποκτήσω δωρεάν δοκιμή του GroupDocs.Viewer;**  
A: Επισκεφθείτε τον [σύνδεσμο δωρεάν δοκιμής](https://releases.groupdocs.com/viewer/java/) για λήψη και δοκιμή.

**Q: Μπορώ να μετατρέψω άλλους τύπους εγγράφων εκτός των αρχείων συμπιεσμένων;**  
A: Ναι, ο viewer υποστηρίζει PDF, Word, Excel και πολλούς άλλους μορφότυπους.

**Q: Τι πρέπει να κάνω αν η απόδοση είναι αργή;**  
A: Μειώστε τον αριθμό των στοιχείων ανά σελίδα, ενεργοποιήστε streaming ή επεξεργαστείτε τα αρχεία σε μικρότερες παρτίδες.

**Q: Πού μπορώ να λάβω βοήθεια ή υποστήριξη;**  
A: Επικοινωνήστε μέσω του [φόρουμ υποστήριξης](https://forum.groupdocs.com/c/viewer/9).

**Q: Είναι δυνατόν να ενσωματώσω CSS και εικόνες απευθείας στο HTML;**  
A: Απόλυτα—χρησιμοποιήστε το `HtmlViewOptions.forEmbeddedResources` όπως φαίνεται στα παραδείγματα.

**Q: Πώς μπορώ να μετατρέψω παρτίδα φακέλου με αρχεία συμπιεσμένων;**  
A: Επανάληψη σε κάθε αρχείο με βρόχο `for`, εφαρμόζοντας την ίδια διαμόρφωση `Viewer` και `HtmlViewOptions` για κάθε επανάληψη.

## Πόροι

- **Τεκμηρίωση:** Εμβαθύνετε στη λειτουργικότητα με την [τεκμηρίωση GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Αναφορά API:** Εξερευνήστε το πλήρες API στο [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Λήψη:** Λάβετε τα πιο πρόσφατα binaries από τη [σελίδα λήψης](https://releases.groupdocs.com/viewer/java/).  
- **Αγορά και Άδειες:** Εξετάστε τις επιλογές στην [σελίδα αγοράς](https://purchase.groupdocs.com/buy).  
- **Υποστήριξη και Κοινότητα:** Συμμετέχετε σε συζητήσεις στο [φόρουμ GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Τελευταία Ενημέρωση:** 2026-02-23  
**Δοκιμή Με:** GroupDocs.Viewer 25.2  
**Συγγραφέας:** GroupDocs