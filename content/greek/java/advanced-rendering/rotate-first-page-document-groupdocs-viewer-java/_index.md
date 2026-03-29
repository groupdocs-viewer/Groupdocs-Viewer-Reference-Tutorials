---
date: '2026-03-29'
description: Μάθετε πώς να περιστρέψετε τη σελίδα 90 μοίρες σε Java χρησιμοποιώντας
  το GroupDocs Viewer, συμπεριλαμβανομένης της εγκατάστασης, του κώδικα και των συμβουλών
  απόδοσης.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Περιστροφή σελίδας 90 μοιρών με το GroupDocs Viewer για Java
type: docs
url: /el/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Περιστροφή σελίδας 90 μοιρών με GroupDocs Viewer for Java

Όταν χρειάζεστε να **περιστρέψετε τη σελίδα 90 μοιρών** σε ένα έγγραφο—είτε πρόκειται για PDF, αρχείο Word ή υπολογιστικό φύλλο—η προγραμματιστική εκτέλεση εξοικονομεί χρόνο και εξαλείφει τα χειροκίνητα σφάλματα. Σε αυτόν τον προχωρημένο οδηγό, θα περάσουμε βήμα-βήμα τις ακριβείς ενέργειες για να περιστρέψετε την πρώτη σελίδα οποιουδήποτε υποστηριζόμενου εγγράφου χρησιμοποιώντας το **GroupDocs Viewer for Java**. Στο τέλος, θα έχετε ένα επαναχρησιμοποιήσιμο κομμάτι κώδικα που μπορείτε να ενσωματώσετε στα δικά σας έργα.  
Θα συζητήσουμε επίσης γιατί η περιστροφή σελίδων σε Java είναι σημαντική, κοινά σενάρια όπου αυτή η τεχνική διαπρέπει, και πώς να διατηρήσετε τη λειτουργία ελαφριά.

![Περιστροφή της πρώτης σελίδας ενός εγγράφου με GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Γρήγορες Απαντήσεις
- **Τι σημαίνει η “περιστροφή σελίδας 90 μοιρών”;** Γυρίζει τη επιλεγμένη σελίδα δεξιόστροφα κατά ένα τέταρτο γύρο.  
- **Ποια βιβλιοθήκη διαχειρίζεται την περιστροφή;** Το GroupDocs Viewer for Java παρέχει τη μέθοδο `rotatePage`.  
- **Μπορώ να περιστρέψω σελίδες PDF με Java;** Ναι—χρησιμοποιήστε την ίδια κλήση `rotatePage`; λειτουργεί για PDF, DOCX, XLSX και άλλα.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται πληρωμένη άδεια για παραγωγή.  
- **Είναι η λειτουργία εντατική σε μνήμη;** Όχι όταν κλείνετε άμεσα το αντικείμενο `Viewer`; δείτε τις συμβουλές απόδοσης παρακάτω.

## Τι είναι η “περιστροφή σελίδας 90 μοιρών”;
Η περιστροφή μιας σελίδας 90 μοιρών επαναπροσανατολίζει τη σελίδα από πορτραίτο σε τοπίο (ή αντίστροφα) χωρίς να τροποποιεί το υποκείμενο περιεχόμενο. Αυτό είναι ιδιαίτερα χρήσιμο για παρουσιάσεις, εκτύπωση γραφικών μόνο σε τοπίο, ή διόρθωση σαρωμένων εγγράφων που λήφθηκαν πλαγίως.

## Γιατί να περιστρέφετε σελίδες προγραμματιστικά με GroupDocs Viewer for Java;
Το GroupDocs Viewer αφαιρεί τις πολυπλοκότητες της διαχείρισης δεκάδων μορφών αρχείων. Σας επιτρέπει να εφαρμόζετε μετασχηματισμούς επιπέδου σελίδας—όπως η περιστροφή—διατηρώντας το αρχικό αρχείο ανέπαφο. Το API είναι ευανάγνωστο, ασφαλές ως προς τα νήματα, και λειτουργεί σε οποιοδήποτε runtime Java 8+, καθιστώντας το αξιόπιστη επιλογή για αυτοματοποίηση επιχειρησιακού επιπέδου.

## Προαπαιτούμενα

- **GroupDocs.Viewer for Java** (τελευταία έκδοση)
- **JDK 8** ή νεότερο
- **Maven** (ή Gradle) για διαχείριση εξαρτήσεων
- Ένα IDE όπως IntelliJ IDEA ή Eclipse
- Βασική εξοικείωση με Java I/O

## Ρύθμιση του GroupDocs.Viewer για Java

Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση στο `pom.xml`. Αυτό το απόσπασμα παραμένει αμετάβλητο από το αρχικό tutorial:

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
- **Free trial** – λήψη από τον ιστότοπο GroupDocs.  
- **Temporary license** – αίτηση εάν χρειάζεστε παρατεταμένη περίοδο αξιολόγησης.  
- **Full license** – αγορά για παραγωγικές εγκαταστάσεις.

### Βασική αρχικοποίηση Viewer
Ο παρακάτω κώδικας δείχνει τον ελάχιστο τρόπο δημιουργίας ενός αντικειμένου `Viewer`. Διατηρήστε τον ακριβώς όπως φαίνεται:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Πώς να περιστρέψετε σελίδα PDF σε Java με το GroupDocs Viewer
Αν και το API λειτουργεί σε πολλές μορφές, το PDF είναι η πιο συνηθισμένη περίπτωση χρήσης για περιστροφή σελίδας. Χρησιμοποιείται η ίδια μέθοδος `rotatePage`, οπότε χρειάζεται μόνο να κατευθύνετε το Viewer σε ένα αρχείο PDF και να καθορίσετε τον αριθμό σελίδας.

## Υλοποίηση βήμα-βήμα: Περιστροφή της πρώτης σελίδας 90 μοιρών

### 1. Εισαγωγή των απαιτούμενων πακέτων
Αυτές οι εισαγωγές σας δίνουν πρόσβαση στις επιλογές απόδοσης PDF και στο enum περιστροφής.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Ορισμός τοποθεσιών εξόδου και δημιουργία του Viewer
Αντικαταστήστε τις διαδρομές placeholder με τις πραγματικές σας καταλόγους.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Διαμόρφωση επιλογών προβολής PDF και εφαρμογή της περιστροφής
Η μέθοδος `rotatePage` δέχεται τον αριθμό σελίδας (από 1) και μια τιμή enum `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Απόδοση του εγγράφου
Τέλος, καλέστε τη μέθοδο `view` για να δημιουργήσετε το περιστραμμένο PDF.

```java
viewer.view(viewOptions);
```

#### Πώς λειτουργεί
- **PdfViewOptions** λέει στο Viewer να εξάγει αρχείο PDF.  
- **rotatePage(int, Rotation)** περιστρέφει μόνο τη σελίδα που καθορίζετε, αφήνοντας τις υπόλοιπες αμετάβλητες.  
- Η μέθοδος υποστηρίζει `ON_90_DEGREE`, `ON_180_DEGREE` και `ON_270_DEGREE`.

## Κοινά Προβλήματα και Λύσεις

| Σύμπτωμα | Πιθανή Αιτία | Διόρθωση |
|----------|--------------|----------|
| **FileNotFoundException** | Λάθος διαδρομή ή λείπει ο φάκελος | Επαληθεύστε ότι οι φάκελοι `YOUR_OUTPUT_DIRECTORY` και `YOUR_DOCUMENT_DIRECTORY` υπάρχουν και είναι αναγνώσιμα. |
| **Unsupported file format** | Προσπάθεια περιστροφής μορφής που δεν υποστηρίζεται από το Viewer | Ελέγξτε τη σελίδα [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Χρήση λανθασμένου αριθμού σελίδας (από 0) | Θυμηθείτε ότι η `rotatePage` χρησιμοποιεί αρίθμηση **από 1**. |
| **Out‑of‑memory errors on large docs** | Απόδοση πολλών μεγάλων αρχείων σε ένα νήμα | Επεξεργαστείτε τα έγγραφα διαδοχικά ή χρησιμοποιήστε μια ομάδα νημάτων με περιορισμένη ταυτόχρονη εκτέλεση. |

## Πρακτικές Εφαρμογές

- **Presentation adjustments** – Μετατρέψτε μια διαφάνεια πορτραίτου σε τοπίο άμεσα.  
- **Bulk document correction** – Αυτοματοποιήστε τη διόρθωση σαρωμένων PDF που λήφθηκαν πλαγίως.  
- **Print‑ready output** – Διασφαλίστε ότι τα γραφικά τοπίου εκτυπώνονται σωστά σε χαρτί προσανατολισμένο σε πορτραίτο.

## Συμβουλές Απόδοσης

- **Κλείσιμο πόρων άμεσα** – Το μπλοκ `try‑with‑resources` απελευθερώνει αυτόματα το `Viewer`.  
- **Επεξεργασία σε παρτίδες** – Όταν διαχειρίζεστε πολλά αρχεία, επαναχρησιμοποιήστε ένα μόνο αντικείμενο `Viewer` ανά νήμα για μείωση του κόστους.  
- **Παρακολούθηση μνήμης** – Για έγγραφα μεγαλύτερα από 100 MB, σκεφτείτε τη ροή εξόδου στο δίσκο αντί να τα κρατάτε στη μνήμη.

## Συχνές Ερωτήσεις

**Q: Μπορώ να περιστρέψω πολλές σελίδες ταυτόχρονα;**  
A: Ναι—καλέστε τη `rotatePage()` για κάθε αριθμό σελίδας που χρειάζεται να περιστραφεί.

**Q: Υπάρχει τρόπος να αναιρέσετε την περιστροφή μετά την απόδοση;**  
A: Δεν είναι δυνατό άμεσα. Θα πρέπει να επαναδημιουργήσετε το έγγραφο χωρίς τις επιλογές περιστροφής.

**Q: Ποιοι τύποι αρχείων υποστηρίζουν την περιστροφή σελίδας στο GroupDocs Viewer;**  
A: DOCX, PDF, PPTX, XLSX και πολλές άλλες μορφές που αναφέρονται στην επίσημη τεκμηρίωση.

**Q: Πώς μπορώ να περιστρέψω σελίδες σε μια παρτίδα εγγράφων αυτόματα;**  
A: Τυλίξτε τον κώδικα σε βρόχο που διατρέχει μια συλλογή διαδρομών αρχείων, εφαρμόζοντας την ίδια λογική `rotatePage` σε κάθε ένα.

**Q: Ποια είναι η βέλτιστη πρακτική για τη διαχείριση σφαλμάτων κατά τη διάρκεια της περιστροφής;**  
A: Τοποθετήστε τη χρήση του Viewer μέσα σε μπλοκ `try‑catch`, καταγράψτε την εξαίρεση και, προαιρετικά, συνεχίστε την επεξεργασία του επόμενου αρχείου.

## Πόροι

- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Purchase**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free Trial**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Temporary License**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία ενημέρωση:** 2026-03-29  
**Δοκιμάστηκε με:** GroupDocs Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs