---
date: '2026-10-10'
description: Μάθετε πώς να μετατρέψετε zip σε html χρησιμοποιώντας το GroupDocs.Viewer
  Java, να ορίσετε στοιχεία ανά σελίδα, να ενσωματώσετε πόρους html και να batch convert
  archives αποδοτικά.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: Μάθετε πώς να μετατρέψετε zip σε html με το GroupDocs.Viewer Java,
  να ενσωματώσετε πόρους, να ορίσετε στοιχεία ανά σελίδα και να batch‑process archives
  για γρήγορες, φορητές web previews.
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: Μετατροπή zip σε HTML με σελιδοποίηση GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
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

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή zip σε html και ορισμός στοιχείων ανά σελίδα με GroupDocs.Viewer Java

Σε πολλές web εφαρμογές χρειάζεται να εμφανίζετε τα περιεχόμενα ενός αρχείου ZIP ή RAR απευθείας σε έναν περιηγητή. **Πώς να μετατρέψετε zip** σε HTML χρησιμοποιώντας το GroupDocs.Viewer για Java είναι μια κοινή απαίτηση, και η βιβλιοθήκη σας επιτρέπει να ενσωματώνετε εικόνες, CSS και γραμματοσειρές ώστε το αποτέλεσμα να είναι μια ενιαία, φορητή σελίδα. Αυτό το tutorial σας καθοδηγεί βήμα προς βήμα—από τη ρύθμιση του Maven μέχρι την αποτύπωση πολλαπλών σελίδων—εξηγώντας γιατί κάθε επιλογή είναι σημαντική για την απόδοση και τη χρηστικότητα.

![Μετατροπή αρχείων σε HTML με GroupDocs.Viewer για Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Γρήγορες απαντήσεις
- **Τι ελέγχει η επιλογή “set items per page”;** Καθορίζει πόσα αρχεία ή φάκελοι από ένα αρχείο συμπιεσμένου τύπου εμφανίζονται σε κάθε παραγόμενη σελίδα HTML.  
- **Μπορώ να ενσωματώσω εικόνες και CSS απευθείας στο HTML;** Ναι – χρησιμοποιήστε την επιλογή `forEmbeddedResources` για να ενσωματώσετε τους πόρους στο HTML.  
- **Είναι δυνατή η μαζική μετατροπή;** Απόλυτα· μπορείτε να επαναλάβετε πάνω σε μια συλλογή αρχείων και να αποτυπώσετε το καθένα με τις ίδιες ρυθμίσεις.  
- **Χρειάζομαι το Maven για να χρησιμοποιήσω το GroupDocs.Viewer;** Ναι, προσθέστε την εξάρτηση Maven `groupdocs-viewer` όπως φαίνεται παρακάτω.  
- **Ποιοι μορφές εξόδου υποστηρίζονται;** Διαθέσιμα είναι το HTML μονής σελίδας και το HTML πολλαπλών σελίδων, και η βιβλιοθήκη υποστηρίζει πάνω από 50 τύπους αρχείων συμπίεσης.

## Τι είναι το “set items per page” στο GroupDocs.Viewer;
Καθορίζει στον προβολέα πόσες καταχωρήσεις του αρχείου (αρχεία ή φάκελοι) πρέπει να εμφανίζονται σε κάθε σελίδα HTML όταν δημιουργείτε ένα έγγραφο πολλαπλών σελίδων. Η ρύθμιση αυτής της τιμής βοηθά στην εξισορρόπηση του μεγέθους της σελίδας και της ταχύτητας πλοήγησης, ιδιαίτερα για μεγάλα αρχεία, περιορίζοντας την ποσότητα δεδομένων που φορτώνεται ανά σελίδα και μειώνοντας το χρόνο απόδοσης για τους τελικούς χρήστες.

## Γιατί να ενσωματώσετε πόρους html;
Η ενσωμάτωση πόρων (εικόνες, CSS, γραμματοσειρές) απευθείας μέσα στο αρχείο HTML δημιουργεί ένα ενιαίο, φορητό έγγραφο που μπορεί να ανοιχθεί χωρίς εξωτερικά αρχεία. Αυτό είναι ιδανικό για συνημμένα email, προβολή εκτός σύνδεσης ή ενσωμάτωση του αποτελέσματος σε άλλες ιστοσελίδες. Επίσης, αφαιρεί την ανάγκη διαχείρισης εξωτερικών διαδρομών πόρων.

## Προαπαιτούμενα

- **Απαιτούμενες βιβλιοθήκες:** Συμπεριλάβετε το GroupDocs.Viewer έκδοση 25.2 ή νεότερη.  
- **Περιβάλλον:** Εγκατεστημένο και ρυθμισμένο Java Development Kit (JDK).  
- **Γνώση:** Βασική Java και διαχείριση εξαρτήσεων Maven.  

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

### Απόκτηση άδειας
Το GroupDocs.Viewer προσφέρει **σύνδεσμο δωρεάν δοκιμής**, προσωρινή άδεια ή πλήρη επιλογή αγοράς. Επιλέξτε αυτή που ταιριάζει στο χρονοδιάγραμμα του έργου σας.

## Βασική αρχικοποίηση
Η κλάση `Viewer` είναι το σημείο εισόδου για την απόδοση εγγράφων και αρχείων. Μετά τη ρύθμιση του Maven, φέρτε τον προβολέα στον κώδικά σας:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Πώς να αποτυπώσετε αρχεία σε HTML μονής σελίδας
Η κλάση `HtmlViewOptions` ορίζει ρυθμίσεις για την έξοδο HTML, όπως η ενσωμάτωση πόρων. Φορτώστε το αρχείο, ρυθμίστε τις επιλογές HTML για ενσωμάτωση πόρων και αποτυπώστε τα πάντα σε μία αυτόνομη σελίδα. Αυτό παράγει ένα ενιαίο αρχείο HTML που περιέχει όλα τα αρχεία, τις εικόνες, το CSS και τις γραμματοσειρές, έτοιμο για χρήση εκτός σύνδεσης ή ως συνημμένο email.

**Άμεση απάντηση:** Δημιουργήστε μια παρουσία `Viewer` για το αρχείο ZIP, καλέστε `HtmlViewOptions.forEmbeddedResources()` και εκτελέστε `viewer.view(documentPath, options)`. Αυτό παράγει ένα ενιαίο αρχείο HTML που περιέχει όλα τα αρχεία, τις εικόνες, το CSS και τις γραμματοσειρές, έτοιμο για χρήση εκτός σύνδεσης ή ως συνημμένο email.

### Βήμα 1: Ορισμός καταλόγου εξόδου
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Βήμα 2: Ορισμός ονόματος αρχείου για έξοδο μονής σελίδας
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Βήμα 3: Αρχικοποίηση του προβολέα
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Βήμα 4: Ρύθμιση επιλογών απόδοσης (ενσωμάτωση πόρων html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Βήμα 5: Απόδοση ως μονή σελίδα
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Πώς να αποτυπώσετε αρχεία σε HTML πολλαπλών σελίδων και να ορίσετε στοιχεία ανά σελίδα
Η κλάση `HtmlViewOptions` υποστηρίζει επίσης σελιδοποίηση. Με την κλήση `options.setItemsPerPage(N)`, υποδεικνύετε στον προβολέα να χωρίσει το αρχείο σε πολλά αρχεία HTML, το καθένα εμφανίζοντας έως **N** καταχωρήσεις. Αυτή η προσέγγιση βελτιώνει την ταχύτητα πλοήγησης για μεγάλα αρχεία, διατηρώντας κάθε σελίδα ελαφριά.

**Άμεση απάντηση:** Χρησιμοποιήστε `HtmlViewOptions.forEmbeddedResources()`, καλέστε `options.setItemsPerPage(N)` και αποτυπώστε το αρχείο. Ο προβολέας θα δημιουργήσει ξεχωριστά αρχεία HTML—ένα ανά σελίδα—κάθε ένα περιέχει έως **N** καταχωρήσεις, κάτι που επιταχύνει την πλοήγηση για μεγάλα αρχεία.

### Βήμα 1: Επαναχρησιμοποίηση του καταλόγου εξόδου
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Βήμα 2: Ορισμός μορφής ονόματος αρχείου για πολλαπλές σελίδες
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Βήμα 3: Επαναφορά του προβολέα
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Βήμα 4: Ρύθμιση επιλογών πολλαπλών σελίδων (ενσωμάτωση πόρων html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Βήμα 5: Ορισμός στοιχείων ανά σελίδα (κύρια λέξη-κλειδί στην ενέργεια)
`options.setItemsPerPage(20); // πώς να μετατρέψετε αρχεία zip με 20 καταχωρήσεις ανά σελίδα`

```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Πρακτικές εφαρμογές

- **Συστήματα διαχείρισης εγγράφων:** Προσθέστε λειτουργία προεπισκόπησης αρχείων χωρίς την εγκατάσταση πρόσθετων προβολέων.  
- **Ιστοσελίδες/Πύλες:** Προσφέρετε στους χρήστες έναν γρήγορο, χωρίς λήψη τρόπο για να εξερευνήσουν τα ενσωματωμένα έγγραφα.  
- **Εργαλεία συνεργασίας:** Επιτρέψτε στις ομάδες να ελέγχουν κοινόχρηστα αρχεία απευθείας στον περιηγητή.  

## Παραμέτρους απόδοσης

- **Διαχείριση πόρων:** Διατηρήστε τη χρήση μνήμης χαμηλή επεξεργαζόμενοι τα αρχεία σε ροές· ο προβολέας μπορεί να χειριστεί αρχεία έως 500 MB χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.  
- **Μαζική μετατροπή αρχείων:** Επανάληψη σε λίστα αρχείων και κλήση της ίδιας λογικής απόδοσης για μέγιστη απόδοση.  
- **Στρατηγική caching:** Αποθηκεύστε το αποτυπωμένο HTML σε cache εάν το ίδιο αρχείο προσπελαύνεται συχνά, μειώνοντας τον χρόνο επαναλαμβανόμενης επεξεργασίας έως και 70 %.  

## Συχνές ερωτήσεις

**Q: Τι είναι το GroupDocs.Viewer Java;**  
A: Το GroupDocs.Viewer Java είναι μια βιβλιοθήκη διακομιστή που αποτυπώνει πάνω από 50 μορφές εγγράφων και αρχείων συμπίεσης—συμπεριλαμβανομένων των ZIP και RAR—σε HTML, PDF ή αρχεία εικόνας χωρίς την ανάγκη εξωτερικών εφαρμογών.

**Q: Πώς μπορώ να αποκτήσω δωρεάν δοκιμή του GroupDocs.Viewer;**  
A: Επισκεφθείτε τον [σύνδεσμο δωρεάν δοκιμής](https://releases.groupdocs.com/viewer/java/) για λήψη και δοκιμή.

**Q: Μπορώ να μετατρέψω άλλους τύπους εγγράφων εκτός των αρχείων συμπίεσης;**  
A: Ναι, ο προβολέας υποστηρίζει PDFs, Word, Excel, PowerPoint και πάνω από 35 επιπλέον μορφές.

**Q: Τι πρέπει να κάνω αν η απόδοση είναι αργή;**  
A: Μειώστε τον αριθμό των στοιχείων ανά σελίδα, ενεργοποιήστε τη ροή ή επεξεργαστείτε τα αρχεία σε μικρότερες παρτίδες για βελτίωση της ταχύτητας.

**Q: Πού μπορώ να λάβω βοήθεια ή υποστήριξη;**  
A: Επικοινωνήστε μέσω του [φόρουμ υποστήριξης](https://forum.groupdocs.com/c/viewer/9).

**Q: Είναι δυνατόν να ενσωματώσετε CSS και εικόνες απευθείας στο HTML;**  
A: Απόλυτα—χρησιμοποιήστε `HtmlViewOptions.forEmbeddedResources` όπως φαίνεται στα παραδείγματα.

**Q: Πώς μπορώ να μετατρέψω μαζικά έναν φάκελο με αρχεία;**  
A: Επαναλάβετε πάνω σε κάθε αρχείο με βρόχο `for`, εφαρμόζοντας την ίδια διαμόρφωση `Viewer` και `HtmlViewOptions` για κάθε επανάληψη.

**Q: Πού μπορώ να συζητήσω προβλήματα με άλλους χρήστες;**  
A: Επισκεφθείτε το [φόρουμ GroupDocs](https://forum.groupdocs.com/c/viewer/9) για συζητήσεις της κοινότητας.

## Πόροι

- **Τεκμηρίωση:** Εμβαθύνετε στη λειτουργικότητα με την [τεκμηρίωση GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Αναφορά API:** Εξερευνήστε το πλήρες API στο [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Λήψη:** Κατεβάστε τα πιο πρόσφατα binaries από τη [σελίδα λήψης](https://releases.groupdocs.com/viewer/java/).  
- **Αγορά και άδειες:** Εξετάστε τις επιλογές στη [σελίδα αγοράς](https://purchase.groupdocs.com/buy).  
- **Υποστήριξη και κοινότητα:** Συμμετέχετε σε συζητήσεις στο [φόρουμ υποστήριξης](https://forum.groupdocs.com/c/viewer/9).  
- **Φόρουμ GroupDocs:** Πρόσβαση σε βοήθεια της κοινότητας στο [φόρουμ GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Last Updated:** 2026-10-10  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs

## Σχετικά tutorials

- [Πώς να μετατρέψετε zip σε HTML και να αποτυπώσετε φακέλους zip σε Java με GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [μετατροπή zip σε pdf με GroupDocs.Viewer Java - Προσαρμοσμένα ονόματα αρχείων](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Πώς να μετατρέψετε DOCX σε HTML χρησιμοποιώντας το GroupDocs.Viewer για Java: Οδηγός βήμα‑βήμα](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}