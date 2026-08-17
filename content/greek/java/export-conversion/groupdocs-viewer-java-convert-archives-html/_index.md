---
date: '2026-08-03'
description: Μάθετε πώς να μετατρέψετε zip σε html χρησιμοποιώντας το GroupDocs.Viewer
  Java, να ορίσετε στοιχεία ανά σελίδα, να ενσωματώσετε πόρους html και να μετατρέψετε
  μαζικά αρχεία αποδοτικά.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Μάθετε πώς να μετατρέψετε zip σε html χρησιμοποιώντας το GroupDocs.Viewer
  Java, να ορίσετε στοιχεία ανά σελίδα, να ενσωματώσετε πόρους html και να μετατρέψετε
  μαζικά αρχεία αποδοτικά. Ακολουθήστε κώδικα βήμα‑βήμα και συμβουλές απόδοσης.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Μετατροπή zip σε html και ορισμός στοιχείων ανά σελίδα με GroupDocs.Viewer
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Μετατροπή zip σε html και ορισμός στοιχείων ανά σελίδα με GroupDocs.Viewer
  Java
type: docs
url: /el/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Μετατροπή zip σε html και ορισμός στοιχείων ανά σελίδα με GroupDocs.Viewer Java

Σε πολλές web εφαρμογές χρειάζεται να εμφανίζετε το περιεχόμενο ενός αρχείου ZIP ή RAR απευθείας σε έναν περιηγητή. Με το GroupDocs.Viewer for Java μπορείτε να **convert zip to html** σε ένα μόνο βήμα, να ελέγχετε πόσες καταχωρήσεις αρχείου εμφανίζονται σε κάθε σελίδα, να ενσωματώνετε όλες τις εικόνες και τα CSS που υποστηρίζουν, και ακόμη να επεξεργάζεστε μαζικά δεκάδες αρχεία. Αυτό το tutorial σας καθοδηγεί μέσα από τη πλήρη ροή εργασίας, από τη ρύθμιση του Maven μέχρι την απόδοση πολλαπλών σελίδων, και εξηγεί γιατί κάθε ρύθμιση είναι σημαντική για την απόδοση και τη χρηστικότητα.

![Μετατροπή αρχείων σε HTML με το GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Γρήγορες απαντήσεις
- **Τι ελέγχει το “set items per page”;** Καθορίζει πόσα αρχεία ή φάκελοι από ένα αρχείο εμφανίζονται σε κάθε παραγόμενο HTML αρχείο.  
- **Μπορώ να ενσωματώσω εικόνες και CSS απευθείας στο HTML;** Ναι – χρησιμοποιήστε την επιλογή `forEmbeddedResources` για ενσωμάτωση πόρων HTML.  
- **Είναι δυνατή η μαζική μετατροπή;** Απολύτως· μπορείτε να επαναλάβετε πάνω σε μια συλλογή αρχείων και να αποδώσετε το καθένα με τις ίδιες ρυθμίσεις.  
- **Χρειάζομαι το Maven για να χρησιμοποιήσω το GroupDocs.Viewer;** Ναι, προσθέστε την εξάρτηση Maven `groupdocs-viewer` όπως φαίνεται παρακάτω.  
- **Ποιοι τύποι εξόδου υποστηρίζονται;** Διατίθενται τόσο HTML μονής σελίδας όσο και HTML πολλαπλών σελίδων, και η βιβλιοθήκη υποστηρίζει πάνω από 50 τύπους αρχείων εισόδου.

## Τι είναι το “set items per page” στο GroupDocs.Viewer;
Η ρύθμιση **set items per page** ανήκει στις επιλογές απόδοσης αρχείων. Λέει στον προβολέα πόσες καταχωρήσεις αρχείου (αρχεία ή φάκελοι) πρέπει να εμφανίζονται σε κάθε σελίδα HTML όταν δημιουργείτε ένα έγγραφο HTML πολλαπλών σελίδων. Η προσαρμογή αυτής της τιμής σας βοηθά να ισορροπήσετε το μέγεθος της σελίδας και την ταχύτητα πλοήγησης, ειδικά για μεγάλα αρχεία.

## Γιατί να ενσωματώσετε πόρους html;
Η ενσωμάτωση πόρων (εικόνες, CSS, γραμματοσειρές) απευθείας μέσα στο αρχείο HTML δημιουργεί ένα ενιαίο, φορητό έγγραφο που μπορεί να ανοιχθεί χωρίς εξωτερικά αρχεία. Αυτό είναι ιδανικό για συνημμένα email, προβολή εκτός σύνδεσης ή ενσωμάτωση του αποτελέσματος σε άλλες ιστοσελίδες. Αυτή η προσέγγιση επίσης απλοποιεί την ανάπτυξη επειδή δεν χρειάζεται να διαχειρίζεστε εξωτερικές διαδρομές πόρων.

## Προαπαιτούμενα
- **Απαιτούμενες βιβλιοθήκες:** Συμπεριλάβετε το GroupDocs.Viewer έκδοση 25.2 ή νεότερη.  
- **Περιβάλλον:** Εγκατεστημένο και ρυθμισμένο Java Development Kit (JDK).  
- **Γνώση:** Βασική Java και διαχείριση εξαρτήσεων Maven.  

## Ρύθμιση Maven GroupDocs Viewer
Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση του viewer στο `pom.xml` σας:

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
Το GroupDocs.Viewer προσφέρει **free trial link**, προσωρινή άδεια ή πλήρη επιλογή αγοράς. Επιλέξτε αυτή που ταιριάζει στο χρονοδιάγραμμα του έργου σας.

### Βασική αρχικοποίηση
Μετά τη ρύθμιση Maven, φέρετε τον viewer στον κώδικά σας:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Πώς να αποδώσετε αρχεία σε html μονής σελίδας
Το Viewer είναι η κεντρική κλάση που φορτώνει ένα έγγραφο ή αρχείο για απόδοση.

Για να δημιουργήσετε ένα ενιαίο αρχείο HTML που περιέχει ολόκληρο το αρχείο, δημιουργήστε μια παρουσία `Viewer` για το αρχείο ZIP και χρησιμοποιήστε `HtmlViewOptions.forEmbeddedResources()` για ενσωμάτωση όλων των εικόνων, CSS και γραμματοσειρών. Η απόδοση του αρχείου με αυτές τις επιλογές παράγει μία αυτόνομη σελίδα κατάλληλη για email ή χρήση εκτός σύνδεσης.

### Βήμα 1: Ορισμός καταλόγου εξόδου
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Βήμα 2: Ορισμός ονόματος αρχείου για έξοδο μονής σελίδας
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Βήμα 3: Αρχικοποίηση του viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Βήμα 4: Διαμόρφωση επιλογών απόδοσης (ενσωμάτωση πόρων html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Βήμα 5: Απόδοση ως μία σελίδα
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Πώς να αποδώσετε αρχεία σε html πολλαπλών σελίδων και να ορίσετε στοιχεία ανά σελίδα
`HtmlViewOptions` διαμορφώνει πώς ο viewer αποδίδει την έξοδο HTML, συμπεριλαμβανομένης της σελιδοποίησης και της ενσωμάτωσης πόρων.

Για να χωρίσετε ένα αρχείο σε πολλαπλές σελίδες, δημιουργήστε `HtmlViewOptions.forEmbeddedResources()` και ορίστε το επιθυμητό μέγεθος σελίδας με `options.setItemsPerPage(20)`. Ο viewer θα δημιουργήσει ξεχωριστά αρχεία HTML, το καθένα εμφανίζοντας έως τον καθορισμένο αριθμό καταχωρήσεων, κάτι που βελτιώνει την πλοήγηση για μεγάλα αρχεία και εξασφαλίζει ταχύτερη φόρτωση.

### Βήμα 1: Επαναχρησιμοποίηση του καταλόγου εξόδου
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Βήμα 2: Ορισμός μορφής ονόματος αρχείου για πολλαπλές σελίδες
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Βήμα 3: Επαναφορά του viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Βήμα 4: Διαμόρφωση επιλογών πολλαπλών σελίδων (ενσωμάτωση πόρων html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Βήμα 5: Ορισμός στοιχείων ανά σελίδα (κύρια λέξη-κλειδί σε δράση)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Πρακτικές εφαρμογές
- **Συστήματα διαχείρισης εγγράφων:** Προσθέστε λειτουργία προεπισκόπησης αρχείων χωρίς εγκατάσταση πρόσθετων προβολέων.  
- **Ιστοσελίδες:** Προσφέρετε στους χρήστες έναν γρήγορο, χωρίς λήψη τρόπο για εξερεύνηση ενσωματωμένων εγγράφων.  
- **Εργαλεία συνεργασίας:** Επιτρέψτε στις ομάδες να ελέγχουν κοινά αρχεία απευθείας στον περιηγητή.  

## Σκέψεις για την απόδοση
- **Διαχείριση πόρων:** Διατηρήστε τη χρήση μνήμης χαμηλή επεξεργαζόμενοι τα αρχεία σε ροές· ο viewer μπορεί να διαχειριστεί αρχεία έως 500 MB χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.  
- **Μαζική μετατροπή αρχείων:** Επανάληψη μέσω λίστας αρχείων και κλήση της ίδιας λογικής απόδοσης για μεγιστοποίηση της απόδοσης.  
- **Στρατηγική caching:** Αποθηκεύστε το παραγόμενο HTML σε cache εάν το ίδιο αρχείο προσπελάζεται συχνά, μειώνοντας τον χρόνο επαναλαμβανόμενης επεξεργασίας έως και 70 %.  

## Συχνές ερωτήσεις
**Q: Τι είναι το GroupDocs.Viewer Java;**  
A: Το GroupDocs.Viewer Java είναι μια βιβλιοθήκη διακομιστή που αποδίδει πάνω από 50 μορφές εγγράφων και αρχείων—συμπεριλαμβανομένων των ZIP και RAR—σε HTML, PDF ή αρχεία εικόνας χωρίς να απαιτούνται εξωτερικές εφαρμογές.

**Q: Πώς μπορώ να αποκτήσω δωρεάν δοκιμαστική έκδοση του GroupDocs.Viewer;**  
A: Επισκεφθείτε το [free trial link](https://releases.groupdocs.com/viewer/java/) για λήψη και δοκιμή.

**Q: Μπορώ να μετατρέψω άλλους τύπους εγγράφων εκτός από αρχεία;**  
A: Ναι, ο viewer υποστηρίζει PDFs, Word, Excel, PowerPoint και πάνω από 35 επιπλέον μορφές.

**Q: Τι πρέπει να κάνω αν η απόδοση είναι αργή;**  
A: Μειώστε τον αριθμό των στοιχείων ανά σελίδα, ενεργοποιήστε τη ροή ή επεξεργαστείτε τα αρχεία σε μικρότερες δόσεις για βελτίωση της ταχύτητας.

**Q: Πού μπορώ να λάβω βοήθεια ή υποστήριξη;**  
A: Επικοινωνήστε μέσω του [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: Είναι δυνατόν να ενσωματώσω CSS και εικόνες απευθείας στο HTML;**  
A: Απολύτως—χρησιμοποιήστε το `HtmlViewOptions.forEmbeddedResources` όπως φαίνεται στα παραδείγματα.

**Q: Πώς μπορώ να μετατρέψω μαζικά έναν φάκελο αρχείων;**  
A: Επαναλάβετε για κάθε αρχείο με έναν βρόχο `for`, εφαρμόζοντας την ίδια διαμόρφωση `Viewer` και `HtmlViewOptions` για κάθε επανάληψη.

## Πόροι
- **Τεκμηρίωση:** Εμβαθύνετε στη λειτουργικότητα με την [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **Αναφορά API:** Εξερευνήστε το πλήρες API στο [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Λήψη:** Κατεβάστε τα πιο πρόσφατα binaries από τη [download page](https://releases.groupdocs.com/viewer/java/).  
- **Αγορά και άδειες:** Εξετάστε τις επιλογές στη [purchase page](https://purchase.groupdocs.com/buy).  
- **Υποστήριξη και κοινότητα:** Συμμετέχετε σε συζητήσεις στο [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Τελευταία ενημέρωση:** 2026-08-03  
**Δοκιμή με:** GroupDocs.Viewer 25.2  
**Συγγραφέας:** GroupDocs

## Σχετικά μαθήματα
- [Πώς να μετατρέψετε zip σε HTML και να αποδώσετε φακέλους zip σε Java με το GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [μετατροπή zip σε pdf με GroupDocs.Viewer Java - Προσαρμοσμένα ονόματα αρχείων](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Πώς να μετατρέψετε DOCX σε HTML χρησιμοποιώντας το GroupDocs.Viewer για Java: Οδηγός βήμα‑βήμα](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)