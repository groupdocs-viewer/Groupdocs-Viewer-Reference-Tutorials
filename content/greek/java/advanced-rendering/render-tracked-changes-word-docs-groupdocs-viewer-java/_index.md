---
date: '2026-01-15'
description: Μάθετε πώς να αποδίδετε τις παρακολουθούμενες αλλαγές του Word και να
  προβάλλετε τις εκδόσεις εγγράφων Word σε αρχεία Word χρησιμοποιώντας το GroupDocs.Viewer
  για Java. Ακολουθήστε αυτόν τον οδηγό βήμα‑βήμα για προγραμματιστές.
keywords:
- render tracked changes Word docs GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- Java document rendering
title: Απόδοση των παρακολουθούμενων αλλαγών του Word σε έγγραφα Word με το GroupDocs.Viewer
  για Java
type: docs
url: /el/java/advanced-rendering/render-tracked-changes-word-docs-groupdocs-viewer-java/
weight: 1
---

# Render word tracked changes σε έγγραφα Word με το GroupDocs.Viewer για Java

Αν χρειάζεστε **render word tracked changes** μέσα στην εφαρμογή Java σας, βρίσκεστε στο σωστό μέρος. Σε αυτόν τον οδηγό θα σας δείξουμε πώς να εμφανίσετε κάθε αναθεώρηση, εισαγωγή και διαγραφή που εμφανίζεται σε ένα αρχείο Word, μετατρέποντάς το σε καθαρό, πλοηγήσιμο HTML. Είτε δημιουργείτε μια πύλη ανασκόπησης εγγράφων, ένα σύστημα διαχείρισης νομικών υποθέσεων, ή οποιαδήποτε λύση που πρέπει να **view word document revisions**, αυτό το tutorial σας καθοδηγεί σε όλη τη διαδικασία—από τη ρύθμιση του περιβάλλοντος μέχρι την τελική απόδοση.

![Render Tracked Changes in Word Documents with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-tracked-changes-in-word-documents-java.png)

## Γρήγορες Απαντήσεις
- **What does “render word tracked changes” mean?** Μετατρέπει το markup αναθεώρησης ενός αρχείου Word σε μια οπτική αναπαράσταση HTML.  
- **Which library handles this?** GroupDocs.Viewer for Java.  
- **Do I need a license?** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· μια πλήρης άδεια αφαιρεί όλους τους περιορισμούς.  
- **What Java version is required?** Java 8 ή νεότερη.  
- **Can I disable tracked‑changes rendering?** Ναι—ορίστε `setRenderTrackedChanges(false)` στις επιλογές προβολής.

## Τι είναι το “render word tracked changes”;
Η απόδοση αλλαγών παρακολούθησης σημαίνει ότι λαμβάνει τα δεδομένα αναθεώρησης που αποθηκεύονται μέσα σε ένα αρχείο `.docx` (εισαγωγές, διαγραφές, σχόλια κ.λπ.) και παράγει μια μορφή που μπορεί να προβληθεί—συνήθως HTML—όπου αυτές οι αλλαγές επισημαίνονται οπτικά. Αυτό επιτρέπει στους τελικούς χρήστες να βλέπουν ακριβώς τι τροποποιήθηκε χωρίς να ανοίγουν το Microsoft Word.

## Γιατί να χρησιμοποιήσετε το GroupDocs.Viewer για την προβολή αναθεωρήσεων εγγράφων Word;
Το GroupDocs.Viewer for Java αφαιρεί την χαμηλού επιπέδου διαχείριση OpenXML και σας παρέχει μια ενιαία κλήση API για τη δημιουργία HTML, PDF ή εικόνων. Επίσης υποστηρίζει **view word document revisions** έτοιμο, διατηρώντας το στυλ, τους ενσωματωμένους πόρους και την παρακολούθηση αλλαγών.

## Προαπαιτούμενα
- **GroupDocs.Viewer for Java** βιβλιοθήκη έκδοση 25.2 ή νεότερη.  
- Maven για διαχείριση εξαρτήσεων.  
- Βασικό περιβάλλον ανάπτυξης Java (IDE, JDK 8+).

## Ρύθμιση του GroupDocs.Viewer για Java

### Διαμόρφωση Maven
Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση στο `pom.xml` σας:

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
Ξεκινήστε με μια δωρεάν δοκιμή ή ζητήστε μια προσωρινή άδεια αξιολόγησης. Όταν είστε έτοιμοι για παραγωγή, αγοράστε μια πλήρη άδεια για να ξεκλειδώσετε όλες τις λειτουργίες.

### Βασική Αρχικοποίηση
Εισάγετε τις απαιτούμενες κλάσεις στον κώδικα Java σας και προετοιμάστε τις διαδρομές αρχείων για είσοδο και έξοδο.

## Πώς να αποδώσετε αλλαγές παρακολούθησης σε έγγραφα Word

Παρακάτω υπάρχει ένας βήμα‑βήμα οδηγός που αντικατοπτρίζει τον ακριβή κώδικα που θα χρειαστείτε. Τα μπλοκ κώδικα διατηρούνται αμετάβλητα από το αρχικό tutorial.

### Βήμα 1: Ορισμός Διαδρομής Καταλόγου Εξόδου
Δημιουργήστε έναν φάκελο όπου θα αποθηκευτούν οι παραγόμενες σελίδες HTML.

```java
Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RenderTrackedChanges");
```

### Βήμα 2: Καθορισμός Μορφής για Αποθήκευση Κάθε Σελίδας
Ορίστε ένα πρότυπο ονομασίας για κάθε παραγόμενο αρχείο HTML.

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

### Βήμα 3: Διαμόρφωση Επιλογών Προβολής
Ενεργοποιήστε τους ενσωματωμένους πόρους και ενεργοποιήστε την απόδοση αλλαγών παρακολούθησης.

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getWordProcessingOptions().setRenderTrackedChanges(true);
```

### Βήμα 4: Δημιουργία Αντικειμένου Viewer και Απόδοση
Φορτώστε το έγγραφο Word που περιέχει αλλαγές παρακολούθησης και δημιουργήστε την έξοδο HTML.

```java
try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("SAMPLE_DOCX_WITH_TRACKED_CHANGES"))) {
    viewer.view(viewOptions);
}
```

## Συνηθισμένα Προβλήματα και Λύσεις
- **Incorrect file paths** – Ελέγξτε ξανά ότι τα `YOUR_OUTPUT_DIRECTORY` και `YOUR_DOCUMENT_DIRECTORY` δείχνουν σε υπάρχοντες φακέλους.  
- **Unsupported document format** – Βεβαιωθείτε ότι το αρχείο είναι `.docx` ή `.doc` που υποστηρίζει το GroupDocs.Viewer.  
- **Missing license** – Χωρίς έγκυρη άδεια, η βιβλιοθήκη μπορεί να περιορίσει τις δυνατότητες απόδοσης.

## Πρακτικές Εφαρμογές
1. **Document Review Systems** – Εμφανίστε στους ελεγκτές ακριβώς τι προστέθηκε ή αφαιρέθηκε.  
2. **Legal Case Management** – Επισημάνετε τροποποιήσεις σε συμβόλαια ή καταθέσεις.  
3. **Academic Collaboration** – Οπτικοποιήστε τις συνεισφορές πολλαπλών συγγραφέων.

## Σκέψεις Απόδοσης
- Επεξεργαστείτε περιορισμένο αριθμό εγγράφων ταυτόχρονα για να διατηρήσετε τη χρήση μνήμης χαμηλή.  
- Χρησιμοποιήστε αποδοτικές δομές καταλόγων για να μειώσετε το φόρτο I/O.  
- Διατηρήστε τη βιβλιοθήκη ενημερωμένη· οι νεότερες εκδόσεις περιέχουν βελτιστοποιήσεις απόδοσης.

## Συμπέρασμα
Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή μέθοδο για **render word tracked changes** και **view word document revisions** χρησιμοποιώντας το GroupDocs.Viewer for Java. Ενσωματώστε αυτά τα βήματα στην εφαρμογή σας και θα προσφέρετε στους χρήστες μια ισχυρή, διαδραστική εμπειρία ανασκόπησης εγγράφων.

## Ενότητα Συχνών Ερωτήσεων

1. **What is the minimum Java version required?**  
   Java 8 ή νεότερη συνήθως συνιστάται για συμβατότητα με σύγχρονες βιβλιοθήκες όπως το GroupDocs.Viewer.  
2. **Can I render documents without tracked changes?**  
   Ναι, απλώς απενεργοποιήστε το `setRenderTrackedChanges(true)` στις επιλογές διαμόρφωσης.  
3. **How do I handle large documents efficiently?**  
   Σκεφτείτε να χωρίσετε μεγάλα αρχεία σε μικρότερες ενότητες ή να χρησιμοποιήσετε τεχνικές σελιδοποίησης για αποτελεσματική διαχείριση των πόρων.  
4. **What are the licensing options for GroupDocs.Viewer?**  
   Μπορείτε να ξεκινήσετε με δωρεάν δοκιμή, να επιλέξετε προσωρινή άδεια αξιολόγησης ή να αγοράσετε πλήρη άδεια ανάλογα με τις ανάγκες του έργου σας.  
5. **Is there support available if I encounter issues?**  
   Ναι, μπορείτε να έχετε πρόσβαση σε υποστήριξη μέσω του φόρουμ GroupDocs και των επίσημων πόρων τεκμηρίωσης.

## Πόροι
- [Τεκμηρίωση](https://docs.groupdocs.com/viewer/java/)
- [Αναφορά API](https://reference.groupdocs.com/viewer/java/)
- [Λήψη](https://releases.groupdocs.com/viewer/java/)
- [Αγορά](https://purchase.groupdocs.com/buy)
- [Δωρεάν Δοκιμή](https://releases.groupdocs.com/viewer/java/)
- [Προσωρινή Άδεια](https://purchase.groupdocs.com/temporary-license/)
- [Υποστήριξη](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία Ενημέρωση:** 2026-01-15  
**Δοκιμάστηκε Με:** GroupDocs.Viewer for Java 25.2  
**Συγγραφέας:** GroupDocs