---
date: '2026-08-30'
description: Μάθετε πώς να μετατρέψετε DWG σε PNG, να ορίσετε το χρώμα φόντου σε Java
  και να προσαρμόσετε το μέγεθος της εικόνας με το GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Μετατρέψτε DWG σε PNG χρησιμοποιώντας το GroupDocs.Viewer for Java,
  ορίζοντας προσαρμοσμένο πλάτος εικόνας και χρώμα φόντου. Αυτός ο οδηγός παρέχει
  βήμα‑βήμα εγκατάσταση, αποσπάσματα κώδικα και συμβουλές αντιμετώπισης προβλημάτων.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Μετατροπή DWG σε PNG με προσαρμοσμένο μέγεθος, χρώμα φόντου σε Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Πώς να μετατρέψετε DWG σε PNG με προσαρμοσμένο μέγεθος & χρώμα φόντου χρησιμοποιώντας
  το GroupDocs.Viewer for Java
type: docs
url: /el/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Πώς να μετατρέψετε DWG σε PNG με προσαρμοσμένο μέγεθος & χρώμα φόντου χρησιμοποιώντας το GroupDocs.Viewer για Java

Σε αυτό το σεμινάριο θα μάθετε **πώς να μετατρέψετε DWG σε PNG** ελέγχοντας τις διαστάσεις εξόδου και το χρώμα φόντου, χρησιμοποιώντας το GroupDocs.Viewer για Java. Είτε χρειάζεστε να ενσωματώσετε σχέδια CAD σε μια αναφορά, να δημιουργήσετε μικρογραφίες για μια διαδικτυακή πύλη, είτε να αυτοματοποιήσετε την παρτίδα απόδοσης, τα παρακάτω βήματα σας δίνουν πλήρη έλεγχο της οπτικής εμφάνισης κάθε αρχείου PNG.

## Σύντομες απαντήσεις
- **Τι σημαίνει “convert DWG to PNG”;** Είναι η διαδικασία μετατροπής ενός αρχείου DWG CAD σε εικόνα PNG μέσω κώδικα, διατηρώντας τις διανυσματικές λεπτομέρειες ως εικονοστοιχεία raster.  
- **Μπορώ να ορίσω προσαρμοσμένο πλάτος;** Ναι – καλέστε `CadOptions.forRenderingByWidth(int width)` για να ορίσετε το ακριβές πλάτος σε εικονοστοιχεία που χρειάζεστε.  
- **Πώς αλλάζω το χρώμα φόντου;** Χρησιμοποιήστε `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` πριν από την απόδοση.  
- **Ποια βιβλιοθήκη απαιτείται;** GroupDocs.Viewer για Java (έκδοση 25.2 ή νεότερη).  
- **Χρειάζομαι άδεια;** Μια προσωρινή ή πλήρης άδεια αφαιρεί τους περιορισμούς αξιολόγησης και ενεργοποιεί απεριόριστη απόδοση.

![Απόδοση σχεδίων CAD ως PNG με προσαρμοσμένο μέγεθος & χρώμα φόντου με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Τι είναι το GroupDocs.Viewer για Java;
GroupDocs.Viewer για Java είναι ένα API διακομιστή‑πλευράς που αποδίδει πάνω από 150 μορφές αρχείων—συμπεριλαμβανομένων των αρχείων CAD—σε εικόνες, PDF ή HTML. Λειτουργεί χωρίς να απαιτεί οποιοδήποτε λογισμικό τρίτου, όπως το AutoCAD, καθιστώντας το ιδανικό για αυτοματοποιημένες διαδικασίες.

## Πώς να μετατρέψετε DWG σε PNG με προσαρμοσμένο μέγεθος και χρώμα φόντου;
Φορτώστε το αρχείο DWG με μια παρουσία `Viewer`, διαμορφώστε το `CadOptions` για το επιθυμητό πλάτος και φόντο, και τέλος καλέστε `viewer.view` με `PngViewOptions`. Αυτή η τρι‑βήμα ροή διαχειρίζεται το I/O αρχείων, την απόδοση και την ονομασία εξόδου σε μια ενιαία, μνήμη‑αποδοτική λειτουργία.

`Viewer` είναι η κύρια κλάση που φορτώνει ένα έγγραφο και εκτελεί την απόδοση.  
`CadOptions` διαμορφώνει ρυθμίσεις ειδικές για CAD όπως το πλάτος εικόνας και το χρώμα φόντου.  
`PngViewOptions` ορίζει τη μορφή εξόδου PNG και το πρότυπο ονομασίας για τις αποδοθείσες σελίδες.

Μπορείτε τώρα να αποδώσετε οποιοδήποτε σχέδιο DWG σε PNG με ακριβώς το πλάτος που καθορίζετε, και μπορείτε να επιλέξετε οποιοδήποτε συμπαγές χρώμα (ή διαφανές) φόντο ώστε να ταιριάζει με το brand ή το UI θέμα σας.

## Γιατί να ορίσετε προσαρμοσμένο χρώμα φόντου;
Η ρύθμιση χρώματος φόντου εξασφαλίζει ότι το αποδοθέν PNG ενσωματώνεται αβίαστα με τα περιβάλλοντα UI στοιχεία, αποφεύγει ανεπιθύμητα λευκά περιθώρια, και μπορεί να αναδείξει λεπτομέρειες του σχεδίου που διαφορετικά θα χάνονταν σε λευκό καμβά. Το GroupDocs.Viewer υποστηρίζει οποιοδήποτε `java.awt.Color`, συμπεριλαμβανομένων προσαρμοσμένων τιμών RGB, παρέχοντας πλήρη έλεγχο σε επίπεδο pixel.

`java.awt.Color` αντιπροσωπεύει μια τιμή χρώματος που χρησιμοποιείται για την απόδοση φόντων.

## Προαπαιτούμενα
- **Java Development Kit (JDK) 8+** – το API στοχεύει σε Java 8 και νεότερες εκδόσεις.  
- **Maven** – για διαχείριση εξαρτήσεων.  
- **IDE** – IntelliJ IDEA, Eclipse ή οποιονδήποτε επεξεργαστή προτιμάτε.  
- **Βασική γνώση διαχείρισης αρχείων Java** – για ανάγνωση πηγών DWG και εγγραφή εξόδων PNG.

## Ρύθμιση του GroupDocs.Viewer για Java
Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση Viewer στο Maven `pom.xml`:

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
Αποκτήστε ένα προσωρινό ή πλήρες κλειδί άδειας από το portal του GroupDocs και τοποθετήστε το αρχείο `license.lic` στον φάκελο πόρων του έργου σας. Αυτό αφαιρεί το όριο αξιολόγησης 20 σελίδων και ξεκλειδώνει την απόδοση πλήρους ανάλυσης.

### Βασική αρχικοποίηση και ρύθμιση
Δημιουργήστε μια παρουσία `Viewer` που δείχνει στον φάκελο που περιέχει τα αρχεία DWG σας:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Χαρακτηριστικό 1: απόδοση σχεδίων CAD με προσαρμοσμένο μέγεθος εικόνας και χρώμα φόντου
### Πώς να αλλάξετε το χρώμα φόντου CAD
Για να αλλάξετε το χρώμα φόντου CAD, διαμορφώστε το αντικείμενο CadOptions πριν από την απόδοση. Ορίστε το επιθυμητό πλάτος με `forRenderingByWidth` και εφαρμόστε το νέο φόντο χρησιμοποιώντας `setBackgroundColor`. Ο viewer στη συνέχεια δημιουργεί εικόνες PNG που αντανακλούν το καθορισμένο χρώμα, εξασφαλίζοντας συνεπή οπτικό στυλ σε όλα τα αρχεία εξόδου.

#### Υλοποίηση βήμα‑βήμα

##### Εισαγωγή απαιτούμενων πακέτων
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Ρύθμιση του καταλόγου εξόδου και μορφής διαδρομής αρχείου
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Αρχικοποίηση του viewer με προσαρμοσμένες επιλογές απόδοσης
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Επεξήγηση παραμέτρων**  
- `PngViewOptions` – ορίζει τη μορφή εξόδου PNG και το πρότυπο ονομασίας.  
- `forRenderingByWidth(int width)` – αναγκάζει τον renderer να παράγει εικόνα του οποίου το πλάτος ταιριάζει με την παρεχόμενη τιμή εικονοστοιχείων· το ύψος κλιμακώνεται αναλογικά.  
- `setBackgroundColor(Color color)` – αντικαθιστά το προεπιλεγμένο λευκό καμβά με το χρώμα που επιλέγετε, βελτιώνοντας τη συνοχή της εμφάνισης μεταξύ των παραγόμενων πόρων.

#### Συμβουλές αντιμετώπισης προβλημάτων
- Βεβαιωθείτε ότι ο φάκελος εξόδου υπάρχει· χρησιμοποιήστε `Files.createDirectories(outputDir)` αν δεν υπάρχει.  
- Επαληθεύστε ότι η διαδρομή εισόδου είναι σωστή και ότι η εφαρμογή έχει δικαιώματα ανάγνωσης.  

## Χαρακτηριστικό 2: ορισμός χρώματος φόντου στις επιλογές απόδοσης
### Πώς να ορίσετε χρώμα φόντου PNG
Η ρύθμιση του χρώματος φόντου PNG περιλαμβάνει τη δημιουργία μιας στιγμής Color και την ανάθεσή της στο CadOptions πριν από την απόδοση. Αυτό διασφαλίζει ότι κάθε παραγόμενο PNG χρησιμοποιεί το καθορισμένο φόντο, ταιριάζοντας με τις οδηγίες brand ή το UI θέμα σας. Μπορείτε να χρησιμοποιήσετε προεπιλεγμένες σταθερές ή να ορίσετε προσαρμοσμένες τιμές RGB για ακριβή έλεγχο.

`java.awt.Color` αντιπροσωπεύει μια τιμή χρώματος που χρησιμοποιείται για την απόδοση φόντων.

#### Υλοποίηση βήμα‑βήμα

##### Εισαγωγή απαιτούμενων πακέτων
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Διαμόρφωση επιλογών απόδοσης με χρώμα φόντου
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Κύριες επιλογές διαμόρφωσης**  
- Ρυθμίστε `forRenderingByWidth(int width)` για διαφορετικές διαστάσεις, όπως 800 px για μικρογραφίες ιστού ή 1920 px για εκτυπώσεις υψηλής ανάλυσης.  
- Χρησιμοποιήστε οποιαδήποτε προεπιλεγμένη σταθερά `Color` (π.χ., `Color.LIGHT_GRAY`) ή δημιουργήστε προσαρμοσμένη στιγμή με `new Color(r, g, b)` για ακριβή επωνυμία.

## Πρακτικές εφαρμογές

### 1. Τεχνική τεκμηρίωση
Η προσαρμοσμένη απόδοση εξασφαλίζει ότι κάθε σχέδιο τηρεί τις οδηγίες στυλ της εταιρείας, εξαλείφοντας την ανάγκη χειροκίνητης επεξεργασίας εικόνας μετά την εξαγωγή.

### 2. Αρχιτεκτονική απεικόνιση
Παρουσιάστε τα σχέδια με φόντο που ταιριάζει με παρουσιάσεις ή πελατειακές πύλες, βελτιώνοντας τη συνοχή της οπτικής.

### 3. Κατασκευή πρωτοτύπων
Δημιουργήστε PNG για ροές εργασίας γρήγορης δημιουργίας πρωτοτύπων όπου τα επόμενα εργαλεία απαιτούν συγκεκριμένο μέγεθος εικόνας και φόντο.

### Δυνατότητες ενσωμάτωσης
Συνδυάστε αυτή τη γραμμή απόδοσης με σύστημα διαχείρισης εγγράφων (π.χ., SharePoint) για αυτόματη δημιουργία εικόνων προεπισκόπησης κάθε φορά που ανεβαίνει ένα αρχείο DWG.

## Σκέψεις απόδοσης

### Βελτιστοποίηση απόδοσης
- **Batch processing:** Επανάληψη σε έναν κατάλογο αρχείων DWG και απόδοση του καθενός διαδοχικά για εξοικονόμηση του κόστους εκκίνησης JVM.  
- **Resource management:** Για μεγάλα σχέδια (500+ σελίδες), αυξήστε το heap της JVM (`-Xmx2g`) ή επεξεργαστείτε τα αρχεία σε μικρότερες παρτίδες για αποφυγή σφαλμάτων out‑of‑memory.

### Οδηγίες χρήσης πόρων
Παρακολουθήστε τη χρήση CPU και μνήμης με εργαλεία όπως το VisualVM· απελευθερώστε άμεσα τις στιγμές `Viewer` χρησιμοποιώντας try‑with‑resources.

### Καλές πρακτικές για τη διαχείριση μνήμης Java
- Χρησιμοποιήστε try‑with‑resources (όπως φαίνεται) για αυτόματο κλείσιμο του `Viewer`.  
- Αποφύγετε τη διατήρηση μεγάλων αντικειμένων `Path` πέρα από την άμεση χρήση τους.  

## Συνηθισμένα προβλήματα και λύσεις

| Πρόβλημα | Λύση |
|----------|------|
| Δεν βρέθηκε ο φάκελος εξόδου | Δημιουργήστε τον φάκελο εκ των προτέρων ή προσθέστε `Files.createDirectories(outputDirectory);` |
| Κενή εικόνα | Βεβαιωθείτε ότι καλείται `cadOptions.setBackgroundColor` μετά το `forRenderingByWidth`. |
| Σφάλματα out‑of‑memory | Αυξήστε την επιλογή JVM `-Xmx` ή επεξεργαστείτε τα αρχεία σε μικρότερες παρτίδες. |

## Συχνές ερωτήσεις

**Ε: Μπορώ να αποδώσω άλλες μορφές CAD εκτός του DWG;**  
Α: Ναι, το GroupDocs.Viewer υποστηρίζει DXF, DWF και αρκετές επιπλέον μορφές CAD.

**Ε: Πώς χρησιμοποιώ προσαρμοσμένο χρώμα RGB αντί για προεπιλεγμένη σταθερά;**  
Α: Δημιουργήστε ένα νέο `Color` με `new Color(123, 45, 67)` και περάστε το στο `setBackgroundColor`.

**Ε: Είναι δυνατόν να αποδώσω μόνο συγκεκριμένη διάταξη ή επίπεδο;**  
Α: Μπορείτε να καθορίσετε επιλογές διάταξης ή επιπέδου μέσω του `CadOptions` πριν καλέσετε `viewer.view`.

**Ε: Υποστηρίζει η βιβλιοθήκη διαφανή φόντα;**  
Α: Ορίστε το χρώμα φόντου σε `new Color(0,0,0,0)` για πλήρη διαφάνεια εάν η μορφή εξόδου το υποστηρίζει.

**Ε: Ποια έκδοση του GroupDocs.Viewer απαιτείται;**  
Α: Το σεμινάριο χρησιμοποιεί την έκδοση 25.2, αλλά οι νεότερες εκδόσεις διατηρούν το ίδιο API.

---

**Τελευταία ενημέρωση:** 2026-08-30  
**Δοκιμάστηκε με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

## Σχετικά σεμινάρια

- [groupdocs viewer dwg – Πώς να αποδώσετε συγκεκριμένα σχέδια CAD σε Java χρησιμοποιώντας το GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Απόδοση επιπέδων CAD Java με το GroupDocs.Viewer – Πλήρης Οδηγός](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Πώς να μετατρέψετε pdf σε html και να βελτιστοποιήσετε την ποιότητα εικόνας σε Java με το GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)