---
date: '2026-04-01'
description: Μάθετε πώς να χωρίζετε τα σχέδια CAD σε πλακίδια χρησιμοποιώντας το GroupDocs
  Viewer for Java, βελτιώνοντας την απόδοση της απεικόνισης και απλοποιώντας τη διαχείριση
  μεγάλων αρχείων.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Πώς να χωρίσετε τα σχέδια CAD σε πλακίδια με το GroupDocs Viewer
type: docs
url: /el/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Πώς να Διαχωρίσετε Σχέδια CAD σε Τίλς με το GroupDocs Viewer

Αν αναρωτιέστε **πώς να διαχωρίσετε CAD** αρχεία σε μικρότερα, πιο διαχειρίσιμα κομμάτια, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από τα ακριβή βήματα που απαιτούνται για το διαχωρισμό μεγάλων σχεδίων CAD σε τίλς χρησιμοποιώντας **GroupDocs Viewer for Java**. Στο τέλος θα έχετε μια έτοιμη λύση που βελτιώνει την ταχύτητα απόδοσης, μειώνει την κατανάλωση μνήμης και διευκολύνει την εμφάνιση των σχεδίων σε web ή mobile εφαρμογές.

![Διαχωρισμός Σχεδίων CAD με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Σύντομες Απαντήσεις
- **Τι επιτυγχάνει το «διαχωρισμός CAD»;** Διασπά ένα τεράστιο σχέδιο σε μικρότερες εικόνες (τίλς) που φορτώνουν πιο γρήγορα και καταναλώνουν λιγότερη μνήμη.  
- **Ποια μορφή χρησιμοποιείται για τις τίλς;** Τα αρχεία PNG δημιουργούνται εξ ορισμού, αλλά υποστηρίζονται και άλλες μορφές μέσω των επιλογών του Viewer.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται πληρωμένη άδεια για παραγωγή.  
- **Μπορώ να αλλάξω το μέγεθος της τίλς;** Ναι – προσαρμόστε τους υπολογισμούς `tileWidth` και `tileHeight` σύμφωνα με τις ανάγκες σας.  
- **Είναι αυτή η προσέγγιση ασφαλής για νήματα;** Η απόδοση κάθε τίλς σε ξεχωριστό αντικείμενο `Viewer` με try‑with‑resources είναι ασφαλής για ταυτόχρονη εκτέλεση.

## Τι είναι το «διαχωρισμός CAD»;
Ο διαχωρισμός CAD αναφέρεται στη διαίρεση ενός ενιαίου, συχνά τεράστιου, σχεδίου CAD σε πολλαπλές ορθογώνιες ενότητες (τίλς). Κάθε τίλς αποδίδεται ανεξάρτητα, επιτρέποντάς σας να φορτώνετε μόνο τα τμήματα που χρειάζεται ο χρήστης — ιδανικό για web χάρτες, πύλες εγγράφων και mobile προβολείς.

## Γιατί να χρησιμοποιήσετε το GroupDocs Viewer για Java;
Το GroupDocs Viewer παρέχει έτοιμη υποστήριξη για πάνω από 100 μορφές αρχείων, συμπεριλαμβανομένων των DWG, DXF και DWF. Το API τίλς σας επιτρέπει να καθορίζετε ακριβείς συντεταγμένες, ώστε να αποδίδετε ακριβώς την περιοχή που σας ενδιαφέρει χωρίς να επεξεργάζεστε ολόκληρο το αρχείο πρώτα. Αυτό εξοικονομεί κύκλους CPU, μειώνει το εύρος ζώνης και προσφέρει πιο ομαλή εμπειρία χρήστη.

## Προαπαιτούμενα
- **Βιβλιοθήκες**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Οποιοδήποτε πρόσφατο Java Development Kit (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse ή άλλο IDE συμβατό με Java.  
- **Εργαλείο Κατασκευής**: Maven (άλλα εργαλεία λειτουργούν εφόσον προστεθεί η εξάρτηση).  

## Ρύθμιση του GroupDocs.Viewer για Java
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
GroupDocs Viewer προσφέρει δωρεάν δοκιμαστική άδεια για αξιολόγηση:

- **Δωρεάν Δοκιμή**: Επισκεφθείτε το [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) για να κατεβάσετε τη βιβλιοθήκη.  
- **Προσωρινή Άδεια**: Κάντε αίτηση στη [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Πλήρης Άδεια**: Αγοράστε άδεια παραγωγής στη [Purchase Page](https://purchase.groupdocs.com/buy).

### Βασική Αρχικοποίηση
Δημιουργήστε ένα απλό αντικείμενο `Viewer` για να επαληθεύσετε ότι η βιβλιοθήκη φορτώνεται σωστά:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Οδηγός Βήμα‑Βήμα για το Διαχωρισμό Σχεδίων CAD σε Τίλς

### Βήμα 1: Ορισμός του Καταλόγου Εξόδου
Θα αποθηκεύσουμε κάθε τίλς ως ξεχωριστό αρχείο PNG. Η χρήση μιας βοηθητικής μεθόδου διατηρεί τη λογική διαδρομής καθαρή και επαναχρησιμοποιήσιμη.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Βήμα 2: Διαμόρφωση Επιλογών Προβολής
Ορίστε τη μορφή απόδοσης σε PNG και πείτε στον viewer να μην προφορτώσει κάθε σελίδα (που εξοικονομεί μνήμη).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Βήμα 3: Υπολογισμός Διαστάσεων Τίλς
Πρώτα λαμβάνουμε το αρχικό πλάτος και ύψος του σχεδίου, έπειτα το χωρίζουμε σε τέσσερα ίσα τεταρτημόρια.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Βήμα 4: Απόδοση και Αποθήκευση των Τίλς
Προσθέστε τις υπολογισμένες τίλς στις επιλογές απόδοσης και αφήστε το `Viewer` να δημιουργήσει τα αρχεία PNG.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Συμβουλές Επίλυσης Προβλημάτων
- **Διαδρομή Κατασκευής** – Βεβαιωθείτε ότι τα αρχεία JAR του GroupDocs βρίσκονται στο classpath.  
- **Δικαιώματα** – Ο φάκελος εξόδου πρέπει να είναι εγγράψιμος από τη διαδικασία Java.  
- **Εξαιρέσεις** – Εάν δείτε `ViewerException`, ελέγξτε ξανά ότι το αρχείο DWG δεν είναι κατεστραμμένο και ότι έχει εφαρμοστεί η σωστή άδεια.

## Συνηθισμένες Περιπτώσεις Χρήσης για το Διαχωρισμό Τίλς CAD
1. **Web Mapping** – Φορτώστε μόνο το ορατό τμήμα ενός σχεδίου ορόφου καθώς ο χρήστης μετακινεί/ζουμάρει.  
2. **Διαχείριση Εγγράφων** – Αποθηκεύστε κάθε τίλς ξεχωριστά για ταχύτερη δημιουργία προεπισκόπησης.  
3. **Κινητή Προβολή** – Μειώστε το εύρος ζώνης κατεβάζοντας μόνο τις τίλς που χρειάζονται για την τρέχουσα οθόνη.

## Σκέψεις Απόδοσης
- **Μέγεθος Τίλς** – Μεγαλύτερες τίλς σημαίνουν λιγότερα αρχεία αλλά πιο αργή απόδοση· βρείτε μια ισορροπία βάσει των αναγκών του UI σας.  
- **Παρακολούθηση Μνήμης** – Χρησιμοποιήστε τα εργαλεία προφίλ της Java (π.χ., VisualVM) για να παρακολουθείτε τη χρήση heap κατά την επεξεργασία πολύ μεγάλων σχεδίων.  
- **Καθαρισμός Πόρων** – Το πρότυπο try‑with‑resources που εμφανίζεται παραπάνω απελευθερώνει αυτόματα τους εγγενείς πόρους.

## Συχνές Ερωτήσεις

**Q: Μπορώ να διαχωρίσω άλλους τύπους αρχείων (PDF, εικόνες) σε τίλς χρησιμοποιώντας την ίδια προσέγγιση;**  
A: Ναι. Το GroupDocs Viewer υποστηρίζει πολλές μορφές· αρκεί να χρησιμοποιήσετε την αντίστοιχη κλάση επιλογών (π.χ., `PdfViewOptions`).

**Q: Πώς αλλάζω την ποιότητα της εξαγόμενης εικόνας;**  
A: Προσαρμόστε `viewOptions.setResolution(int dpi)` ή ορίστε ρυθμίσεις συμπίεσης στο αντικείμενο `PngOptions`.

**Q: Η εφαρμογή μου εξαντλεί τη μνήμη σε πολύ μεγάλα αρχεία DWG—τι μπορώ να κάνω;**  
A: Μειώστε τις διαστάσεις των τίλς, αυξήστε το heap της JVM (`-Xmx`), ή αποδώστε τις τίλς διαδοχικά σε ξεχωριστά αντικείμενα `Viewer`.

**Q: Είναι δυνατόν να αποδίδονται οι τίλς ασύγχρονα;**  
A: Απόλυτα. Τυλίξτε κάθε κλήση απόδοσης τίλς σε ένα `CompletableFuture` ή χρησιμοποιήστε ένα executor service για να παραλληλοποιήσετε το φορτίο εργασίας.

**Q: Χρειάζομαι ξεχωριστή άδεια για κάθε τίλς;**  
A: Όχι. Μία έγκυρη άδεια GroupDocs Viewer καλύπτει όλες τις λειτουργίες απόδοσης μέσα στην εφαρμογή σας.

## Πόροι
- [Τεκμηρίωση](https://docs.groupdocs.com/viewer/java/)
- [Αναφορά API](https://reference.groupdocs.com/viewer/java/)
- [Λήψη GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Αγορά Άδειας](https://purchase.groupdocs.com/buy)
- [Δωρεάν Δοκιμή](https://releases.groupdocs.com/viewer/java/)
- [Προσωρινή Άδεια](https://purchase.groupdocs.com/temporary-license/)
- [Φόρουμ Υποστήριξης](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία Ενημέρωση:** 2026-04-01  
**Δοκιμάστηκε Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs