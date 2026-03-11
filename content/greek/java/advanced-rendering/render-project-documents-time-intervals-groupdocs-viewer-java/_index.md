---
date: '2026-01-15'
description: Μάθετε πώς να χρησιμοποιείτε το GroupDocs Viewer για να δημιουργείτε
  HTML από έγγραφα έργου σε συγκεκριμένα χρονικά διαστήματα. Αυτός ο οδηγός καλύπτει
  τη ρύθμιση, τον κώδικα και τις πραγματικές περιπτώσεις χρήσης.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Πώς να χρησιμοποιήσετε το GroupDocs Viewer για την απόδοση εγγράφων έργου ανά
  χρονικά διαστήματα σε Java
type: docs
url: /el/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Πώς να Χρησιμοποιήσετε το GroupDocs Viewer για την Απόδοση Εγγράφων Έργου ανά Χρονικά Διαστήματα σε Java

Αν ψάχνετε για **how to use GroupDocs** ώστε να αποδίδετε χρονοδιαγράμματα έργου σε ένα εστιασμένο χρονικό παράθυρο, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από τη διαδικασία—από τη ρύθμιση του Maven μέχρι τη δημιουργία HTML από έγγραφα έργου—ώστε να μπορείτε να ενσωματώσετε ακριβείς προβολές χρονολογίου απευθείας στις εφαρμογές σας.

![Απόδοση Εγγράφων Έργου ανά Χρονικά Διαστήματα με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Γρήγορες Απαντήσεις
- **Τι κάνει η λειτουργία;** Αποδίδει μόνο το τμήμα ενός αρχείου Microsoft Project που βρίσκεται μεταξύ μιας ημερομηνίας έναρξης και λήξης.  
- **Ποια μορφή εξόδου χρησιμοποιείται;** HTML με ενσωματωμένους πόρους, ιδανική για ενσωμάτωση στο web.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Μπορώ να αλλάξω το εύρος ημερομηνιών κατά την εκτέλεση;** Ναι—προσαρμόστε τις τιμές `setStartDate` και `setEndDate` στις επιλογές απόδοσης.  
- **Υποστηρίζεται σε όλες τις εκδόσεις Java;** Λειτουργεί με Java 8+ εφόσον χρησιμοποιείτε το GroupDocs.Viewer 25.2 ή νεότερο.

## Τι σημαίνει “How to Use GroupDocs” σε Αυτό το Πλαίσιο;
Το GroupDocs Viewer είναι μια βιβλιοθήκη Java που μετατρέπει πάνω από 100 μορφές αρχείων σε web‑φιλικές αναπαραστάσεις. Όταν **how to use GroupDocs** για αρχεία έργου, αποκτάτε τη δυνατότητα να εξάγετε, να οπτικοποιήσετε και να μοιραστείτε δεδομένα χρονοδιαγράμματος χωρίς να απαιτείται το Microsoft Project στην πλευρά του πελάτη.

## Γιατί να Αποδίδετε Έγγραφα Έργου με Χρονικά Διαστήματα;
- **Εστιασμένη ανάλυση:** Εμφανίστε μόνο τη φάση που σας ενδιαφέρει (π.χ., Q3 2024).  
- **Απόδοση:** Μικρότερο αρχείο HTML σημαίνει ταχύτερη φόρτωση σελίδας.  
- **Ενσωμάτωση:** Ενσωματώστε προβολές χρονολογίου σε πίνακες ελέγχου, πύλες αναφορών ή προσαρμοσμένα εργαλεία PM.  

## Προαπαιτούμενα
- **GroupDocs.Viewer for Java** έκδοση 25.2 ή νεότερη.  
- Java Development Kit (JDK) 8 ή νεότερο.  
- Ένα IDE όπως το IntelliJ IDEA ή το Eclipse.  
- Βασικές γνώσεις Maven.  

## Ρύθμιση του GroupDocs.Viewer για Java

### Maven Εξάρτηση
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

### Βήματα Απόκτησης Άδειας
1. **Free Trial** – Κατεβάστε μια δοκιμαστική έκδοση από τη [σελίδα λήψης του GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Αποκτήστε μια προσωρινή άδεια για εκτεταμένη δοκιμή μέσω [αυτού του συνδέσμου](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Για απεριόριστη χρήση σε παραγωγή, αγοράστε άδεια στη [σελίδα αγοράς του GroupDocs](https://purchase.groupdocs.com/buy).

### Βασική Αρχικοποίηση Viewer
Το παρακάτω απόσπασμα δείχνει πώς να δημιουργήσετε μια παρουσία `Viewer` που δείχνει σε ένα αρχείο Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Οδηγός Υλοποίησης Βήμα‑βήμα

### 1. Ορισμός του Καταλόγου Εξόδου
Δημιουργήστε έναν φάκελο όπου θα αποθηκευτούν οι παραγόμενες σελίδες HTML:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Γιατί;* Η οργάνωση των παραγόμενων αρχείων καθιστά πιο εύκολο το σερβίρισμα από web server ή η ενσωμάτωσή τους σε UI.

### 2. Αρχικοποίηση του Viewer με το Αρχείο Έργου Σας
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Γιατί;* Η φόρτωση του εγγράφου προετοιμάζει τον εσωτερικό parser και καθιστά προσβάσιμα τα μεταδεδομένα του έργου.

### 3. Ανάκτηση Πληροφοριών Προβολής για Αρχεία Έργου
```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Γιατί;* Το `ProjectManagementViewInfo` σας παρέχει τις ημερομηνίες έναρξης και λήξης του χρονοδιαγράμματος, τις οποίες θα χρησιμοποιήσετε αργότερα για να περιορίσετε το εύρος απόδοσης.

### 4. Διαμόρφωση Επιλογών Απόδοσης HTML (Δημιουργία HTML από Έργο)
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Γιατί;* Ορίζοντας `StartDate` και `EndDate` λέτε στο GroupDocs να **generate HTML from project** δεδομένα μόνο εντός αυτού του παραθύρου.

### 5. Εκτέλεση της Διαδικασίας Απόδοσης
```java
viewer.view(viewOptions);
```

*Γιατί;* Αυτή η κλήση παράγει μια σειρά από αυτόνομα HTML σελίδες που αντιπροσωπεύουν το επιλεγμένο χρονικό τμήμα του χρονοδιαγράμματος του έργου σας.

## Συνηθισμένα Πιθανά Σφάλματα & Επίλυση Προβλημάτων
- **Λανθασμένες διαδρομές αρχείων** – Επαληθεύστε ότι τόσο το πηγαίο αρχείο `.mpp` όσο και ο φάκελος εξόδου υπάρχουν.  
- **Μη υποστηριζόμενος τύπος αρχείου** – Βεβαιωθείτε ότι το έγγραφο είναι σε υποστηριζόμενη μορφή Project (π.χ., `.mpp`, `.mpt`).  
- **Σφάλματα άδειας** – Μια δοκιμαστική άδεια μπορεί να επιβάλλει όρια απόδοσης· μεταβείτε σε πλήρη άδεια για απεριόριστη χρήση.  

## Πρακτικές Εφαρμογές
1. **Ανάλυση Χρονοδιαγράμματος Έργου** – Εμφανίστε στους ενδιαφερόμενους μόνο τη τρέχουσα φάση.  
2. **Αυτοματοποιημένες Αναφορές** – Δημιουργήστε HTML αναφορές με χρονικό περιορισμό για εβδομαδιαίες ενημερώσεις κατάστασης.  
3. **Ενσωμάτωση με Πίνακες Ελέγχου** – Ενσωματώστε τις παραγόμενες σελίδες σε εργαλεία BI ή προσαρμοσμένες πύλες.  
4. **Αρχειοθέτηση** – Αποθηκεύστε ένα web‑φιλικό στιγμιότυπο του χρονοδιαγράμματος του έργου για μελλοντική αναφορά.  

## Συμβουλές Απόδοσης
- Χρησιμοποιήστε την επιλογή *embedded resources* για να διατηρείτε κάθε σελίδα HTML αυτόνομα, μειώνοντας τα αιτήματα HTTP.  
- Για πολύ μεγάλα έργα, σκεφτείτε την απόδοση σε μικρότερα χρονικά τμήματα ώστε η χρήση μνήμης να παραμένει χαμηλή.  
- Καθαρίστε τα προσωρινά αρχεία μετά την εξυπηρέτησή τους για να αποφύγετε την υπερφόρτωση του δίσκου.  

## Συμπέρασμα
Τώρα γνωρίζετε **how to use GroupDocs** Viewer για την απόδοση εγγράφων έργου εντός συγκεκριμένου χρονικού διαστήματος και **generate HTML from project** δεδομένα σε Java. Αυτή η δυνατότητα απλοποιεί τις οπτικοποιήσεις χρονολογίων, βελτιώνει την αποδοτικότητα των αναφορών και ενσωματώνεται ομαλά με σύγχρονες web εφαρμογές.

### Επόμενα Βήματα
- Εξερευνήστε πρόσθετες λειτουργίες του Viewer όπως υδατογράφημα, προστασία με κωδικό ή προσαρμοσμένο CSS.  
- Συνδυάστε αυτή τη διαδικασία απόδοσης με ένα REST API για παροχή χρονολογίων κατ' απαίτηση.  

## Συχνές Ερωτήσεις

**Q: Ποιοι τύποι αρχείων υποστηρίζει το GroupDocs.Viewer;**  
A: Το GroupDocs.Viewer υποστηρίζει μια ευρεία γκάμα μορφών, συμπεριλαμβανομένων των Microsoft Project (MPP), PDF, Word, Excel, PowerPoint, και πολλών άλλων.

**Q: Πώς μπορώ να ξεκινήσω με μια δωρεάν δοκιμή του GroupDocs.Viewer;**  
A: Μπορείτε να κατεβάσετε τη δοκιμαστική έκδοση από [εδώ](https://releases.groupdocs.com/viewer/java/).

**Q: Μπορώ να αποδώσω έγγραφα χωρίς ενσωμάτωση πόρων;**  
A: Ναι, μπορείτε να επιλέξετε μια διαφορετική επιλογή προβολής HTML που αναφέρεται σε εξωτερικούς πόρους αντί για ενσωμάτωση.

**Q: Τι γίνεται αν το έγγραφό μου είναι πολύ μεγάλο για απόδοση;**  
A: Σκεφτείτε να χωρίσετε το έγγραφο σε μικρότερες ενότητες ή να αποδώσετε μόνο το απαιτούμενο εύρος ημερομηνιών, όπως φαίνεται παραπάνω.

**Q: Πώς αντιμετωπίζω σφάλματα απόδοσης;**  
A: Επαληθεύστε όλες τις ρυθμίσεις διαμόρφωσης, βεβαιωθείτε ότι έχετε έγκυρη άδεια και συμβουλευτείτε την τεκμηρίωση του GroupDocs για λεπτομερείς κωδικούς σφαλμάτων.

## Πόροι
- **Documentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free Trial**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-01-15  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs