---
date: '2026-01-18'
description: Μάθετε πώς να περιστρέφετε μια σελίδα 90 μοίρες σε Java χρησιμοποιώντας
  το GroupDocs Viewer, συμπεριλαμβανομένης της ρύθμισης, του κώδικα και των συμβουλών
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

Όταν χρειάζεται να **περιστρέψετε μια σελίδα 90 μοιρών** σε ένα έγγραφο—είτε είναι PDF, αρχείο Word ή υπολογιστικό φύλλο—η προγραμματιστική προσέγγιση εξοικονομεί χρόνο και αποτρέπει χειροκίνητα σφάλματα. Σε αυτόν τον προχωρημένο οδηγό θα περάσουμε βήμα‑βήμα από τις ακριβείς ενέργειες για την περιστροφή της πρώτης σελίδας οποιουδήποτε υποστηριζόμενου εγγράφου χρησιμοποιώντας το **GroupDocs Viewer for Java**. Στο τέλος, θα έχετε ένα επαναχρησιμοποιήσιμο απόσπασμα κώδικα που μπορείτε να ενσωματώσετε στα δικά σας έργα.

![Rotate the First Page of a Document with GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Γρήγορες Απαντήσεις
- **Τι σημαίνει “περιστροφή σελίδας 90 μοιρών”;** Γυρίζει τη συγκεκριμένη σελίδα δεξιόστροφα κατά ένα τέταρτο γύρο.  
- **Ποια βιβλιοθήκη εκτελεί την περιστροφή;** Το GroupDocs Viewer for Java παρέχει τη μέθοδο `rotatePage`.  
- **Μπορώ να περιστρέψω σελίδες PDF με Java;** Ναι—χρησιμοποιήστε την ίδια κλήση `rotatePage`; λειτουργεί για PDF, DOCX, XLSX και άλλα.  
- **Χρειάζεται άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται πληρωμένη άδεια για παραγωγή.  
- **Είναι η λειτουργία απαιτητική σε μνήμη;** Όχι, εφόσον κλείνετε άμεσα το αντικείμενο `Viewer`; δείτε τις συμβουλές απόδοσης παρακάτω.

## Τι σημαίνει “περιστροφή σελίδας 90 μοιρών”;
Η περιστροφή μιας σελίδας 90 μοιρών αλλάζει τον προσανατολισμό της από πορτραίτο σε τοπίο (ή αντίστροφα) χωρίς να τροποποιεί το υποκείμενο περιεχόμενο. Είναι ιδιαίτερα χρήσιμο για παρουσιάσεις, εκτύπωση γραφικών μόνο τοπίου ή διόρθωση σαρωμένων εγγράφων που έχουν ληφθεί πλαγίως.

## Γιατί να περιστρέφετε σελίδες με το GroupDocs Viewer for Java;
Το GroupDocs Viewer αφαιρεί τις πολυπλοκότητες της διαχείρισης δεκάδων μορφών αρχείων. Σας επιτρέπει να εφαρμόζετε μετασχηματισμούς επιπέδου σελίδας—όπως η περιστροφή—διατηρώντας το αρχικό αρχείο αμετάβλητο. Το API είναι fluent, thread‑safe και λειτουργεί σε οποιοδήποτε runtime Java 8+.

## Προαπαιτούμενα

- **GroupDocs.Viewer for Java** (τελευταία έκδοση)  
- **JDK 8** ή νεότερο  
- **Maven** (ή Gradle) για διαχείριση εξαρτήσεων  
- Ένα IDE όπως IntelliJ IDEA ή Eclipse  
- Βασική εξοικείωση με Java I/O  

## Ρύθμιση του GroupDocs.Viewer for Java

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
- **Δωρεάν δοκιμή** – κατεβάστε από την ιστοσελίδα GroupDocs.  
- **Προσωρινή άδεια** – ζητήστε την εάν χρειάζεστε παρατεταμένη περίοδο αξιολόγησης.  
- **Πλήρης άδεια** – αγοράστε για παραγωγικές εγκαταστάσεις.

### Βασική αρχικοποίηση Viewer
Ο παρακάτω κώδικας δείχνει τον ελάχιστο τρόπο δημιουργίας ενός αντικειμένου `Viewer`. Διατηρήστε τον ακριβώς όπως φαίνεται:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Υλοποίηση βήμα‑βήμα: Περιστροφή της πρώτης σελίδας 90 μοιρών

### 1. Εισαγωγή των απαιτούμενων πακέτων
Αυτές οι εισαγωγές σας δίνουν πρόσβαση στις επιλογές απόδοσης PDF και στο enum περιστροφής.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Ορισμός τοποθεσιών εξόδου και δημιουργία του Viewer
Αντικαταστήστε τις διαδρομές placeholder με τους πραγματικούς σας φακέλους.

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
Τέλος, καλέστε `view` για να δημιουργήσετε το περιστραμμένο PDF.

```java
viewer.view(viewOptions);
```

#### Πώς λειτουργεί
- **PdfViewOptions** υποδεικνύει στον Viewer να εξάγει αρχείο PDF.  
- **rotatePage(int, Rotation)** περιστρέφει μόνο τη σελίδα που καθορίζετε, αφήνοντας τις υπόλοιπες αμετάβλητες.  
- Η μέθοδος υποστηρίζει `ON_90_DEGREE`, `ON_180_DEGREE` και `ON_270_DEGREE`.

## Συχνά Προβλήματα και Λύσεις
| Σύμπτωμα | Πιθανή Αιτία | Διόρθωση |
|---------|--------------|----------|
| **FileNotFoundException** | Λάθος διαδρομή ή λείπει ο φάκελος | Επαληθεύστε ότι τα `YOUR_OUTPUT_DIRECTORY` και `YOUR_DOCUMENT_DIRECTORY` υπάρχουν και είναι αναγνώσιμα. |
| **Unsupported file format** | Προσπάθεια περιστροφής μορφής που δεν υποστηρίζεται από το Viewer | Ελέγξτε τη σελίδα [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Χρήση λανθασμένου αριθμού σελίδας (0‑based) | Θυμηθείτε ότι το `rotatePage` χρησιμοποιεί **αρίθμηση από 1**. |
| **Out‑of‑memory errors on large docs** | Απόδοση πολλών μεγάλων αρχείων σε ένα νήμα | Επεξεργαστείτε τα έγγραφα διαδοχικά ή χρησιμοποιήστε thread pool με περιορισμένη ταυτόχρονη εκτέλεση. |

## Πρακτικές Εφαρμογές

1. **Ρυθμίσεις παρουσίασης** – Μετατρέψτε μια κάθετη διαφάνεια σε οριζόντια επί τόπου.  
2. **Μαζική διόρθωση εγγράφων** – Αυτοματοποιήστε τη διόρθωση σαρωμένων PDF που λήφθηκαν πλαγίως.  
3. **Έξοδος έτοιμη για εκτύπωση** – Εξασφαλίστε ότι τα τοπίο γραφικά εκτυπώνονται σωστά σε χαρτί προσανατολισμένο κατακόρυφα.  

## Συμβουλές Απόδοσης

- **Κλείσιμο πόρων άμεσα** – Το μπλοκ `try‑with‑resources` διαγράφει αυτόματα το αντικείμενο `Viewer`.  
- **Επεξεργασία παρτίδας** – Όταν χειρίζεστε πολλά αρχεία, επαναχρησιμοποιήστε ένα μόνο αντικείμενο `Viewer` ανά νήμα για να μειώσετε το κόστος.  
- **Παρακολούθηση μνήμης** – Για έγγραφα μεγαλύτερα από 100 MB, σκεφτείτε να κάνετε streaming της εξόδου σε δίσκο αντί να τη διατηρείτε στη μνήμη.  

## Συχνές Ερωτήσεις

**Ε: Μπορώ να περιστρέψω πολλές σελίδες ταυτόχρονα;**  
Α: Ναι—καλέστε `rotatePage()` για κάθε αριθμό σελίδας που θέλετε να περιστρέψετε.

**Ε: Υπάρχει τρόπος να αναιρέσω την περιστροφή μετά την απόδοση;**  
Α: Όχι άμεσα. Θα πρέπει να αποδώσετε ξανά το έγγραφο χωρίς τις επιλογές περιστροφής.

**Ε: Ποιες μορφές αρχείων υποστηρίζουν περιστροφή σελίδας στο GroupDocs Viewer;**  
Α: DOCX, PDF, PPTX, XLSX και πολλές άλλες μορφές που αναφέρονται στην επίσημη τεκμηρίωση.

**Ε: Πώς μπορώ να περιστρέψω σελίδες σε μια παρτίδα εγγράφων αυτόματα;**  
Α: Τυλίξτε τον κώδικα σε βρόχο που διατρέχει μια συλλογή διαδρομών αρχείων, εφαρμόζοντας την ίδια λογική `rotatePage` σε κάθε αρχείο.

**Ε: Ποια είναι η καλύτερη πρακτική για τη διαχείριση σφαλμάτων κατά την περιστροφή;**  
Α: Τοποθετήστε τη χρήση του Viewer μέσα σε μπλοκ `try‑catch`, καταγράψτε την εξαίρεση και, προαιρετικά, συνεχίστε με το επόμενο αρχείο.

## Πόροι

- **Τεκμηρίωση**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Αναφορά API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Λήψη**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Αγορά**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Δωρεάν Δοκιμή**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Προσωρινή Άδεια**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Υποστήριξη**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία ενημέρωση:** 2026-01-18  
**Δοκιμασμένο με:** GroupDocs Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs  

---