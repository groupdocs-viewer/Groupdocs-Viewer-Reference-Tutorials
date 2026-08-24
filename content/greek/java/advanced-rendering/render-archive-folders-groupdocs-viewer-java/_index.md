---
date: '2026-08-24'
description: Μάθετε πώς να μετατρέψετε zip σε HTML χρησιμοποιώντας το GroupDocs.Viewer
  for Java και να αποδώσετε συγκεκριμένους φακέλους zip στις εφαρμογές σας.
keywords:
- render archive folders
- GroupDocs.Viewer for Java
- rendering specific folders in archives
lastmod: '2026-08-24'
og_description: Το Convert zip to HTML with GroupDocs.Viewer for Java σας επιτρέπει
  να αποδίδετε φακέλους αρχείων απευθείας σε ιστοσελίδες φιλικές προς το web, εξοικονομώντας
  χρόνο εξαγωγής και μειώνοντας το φόρτο I/O. Αυτός ο οδηγός παρουσιάζει τη ρύθμιση,
  την επιλογή φακέλων και συμβουλές απόδοσης.
og_image_alt: GroupDocs.Viewer Java rendering of archive folders to HTML
og_title: Μετατροπή zip σε HTML με το GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-24'
  description: Learn how to convert zip to HTML using GroupDocs.Viewer for Java and
    render specific zip folders in your applications.
  headline: How to convert zip to HTML and render zip folders in Java with GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert zip to HTML using GroupDocs.Viewer for Java and
    render specific zip folders in your applications.
  name: How to convert zip to HTML and render zip folders in Java with GroupDocs.Viewer
  steps:
  - name: '**Document management systems** – Show only the relevant part of a large
      archive without exposing everything.'
    text: '**Document management systems** – Show only the relevant part of a large
      archive without exposing everything.'
  - name: '**Digital libraries** – Stream selected sections of e‑books or research
      collections directly in the browser.'
    text: '**Digital libraries** – Stream selected sections of e‑books or research
      collections directly in the browser.'
  - name: '**Legal review platforms** – Focus on specific case folders inside massive
      zip bundles, saving time and storage.'
    text: '**Legal review platforms** – Focus on specific case folders inside massive
      zip bundles, saving time and storage.'
  type: HowTo
- questions:
  - answer: It is a library that allows developers to render documents—including archives—directly
      within Java applications.
    question: What is GroupDocs.Viewer for Java?
  - answer: Add the repository and dependency configurations to your `pom.xml` file
      as shown in the Maven configuration section.
    question: How do I install GroupDocs.Viewer using Maven?
  - answer: A free trial is available but production deployments require a licensed
      version.
    question: Can I use GroupDocs.Viewer for free?
  - answer: Ensure the folder name matches exactly (case‑sensitive) and that the archive
      is not password‑protected unless you supply credentials.
    question: What are common issues when rendering archives?
  - answer: Visit the [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) for
      community assistance or consult the official documentation.
    question: Where can I get support if needed?
  type: FAQPage
tags:
- convert zip to HTML
- GroupDocs Viewer
- Java archive rendering
- zip folder extraction
- document conversion
title: Πώς να μετατρέψετε zip σε HTML και να αποδώσετε φακέλους zip σε Java με το
  GroupDocs.Viewer
type: docs
url: /el/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/
weight: 1
---

# Πώς να μετατρέψετε zip σε HTML και να αποδώσετε φακέλους zip σε Java με GroupDocs.Viewer

Σε αυτόν τον οδηγό θα μάθετε **πώς να μετατρέψετε zip σε HTML** και να αποδώσετε μόνο τους φακέλους που χρειάζεστε από ένα αρχείο ZIP χρησιμοποιώντας το GroupDocs.Viewer για Java. Στο τέλος του tutorial θα καταλάβετε γιατί αυτή η προσέγγιση μειώνει το φόρτο I/O, πώς να ρυθμίσετε το viewer ώστε να στοχεύει έναν μόνο φάκελο, και ποιες βελτιώσεις απόδοσης διατηρούν την εφαρμογή σας ανταποκρινόμενη ακόμη και με μεγάλα αρχεία.

![Απόδοση φακέλων αρχείου με GroupDocs.Viewer για Java](/viewer/advanced-rendering/rendering-archive-folders-java.png)

[Απόδοση φακέλων αρχείου με GroupDocs.Viewer για Java](/viewer/advanced-rendering/rendering-archive-folders-java.png)

## Γρήγορες απαντήσεις
- **Τι σημαίνει “convert zip to HTML”;** Σημαίνει τη μετατροπή των περιεχομένων ενός αρχείου ZIP (ή ενός συγκεκριμένου φακέλου μέσα σε αυτό) σε ιστοσελίδες HTML φιλικές προς το web.  
- **Ποια βιβλιοθήκη το διαχειρίζεται;** Το GroupDocs.Viewer for Java παρέχει ενσωματωμένες δυνατότητες απόδοσης αρχείων.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Μπορώ να αποδώσω μόνο έναν φάκελο;** Ναι – χρησιμοποιήστε `ArchiveOptions.setFolder("YourFolder")` για να στοχεύσετε έναν μόνο κατάλογο.  
- **Ποια έκδοση της Java απαιτείται;** Java 8 ή νεότερη.

## Πώς να μετατρέψετε zip σε HTML με το GroupDocs.Viewer

Φορτώστε το αρχείο ZIP και ζητήστε από το viewer να παράγει έξοδο HTML – το viewer εξάγει τα ζητούμενα αρχεία στη μνήμη και γράφει έτοιμες προς εμφάνιση σελίδες HTML στην τοποθεσία που καθορίζετε. Αυτό εξαλείφει την ανάγκη για ξεχωριστό βήμα αποσυμπίεσης και μειώνει τη χρήση προσωρινής δίσκου.

## Τι είναι το “how to render zip” με το GroupDocs.Viewer;

Το GroupDocs.Viewer είναι μια βιβλιοθήκη Java που μετατρέπει ένα ευρύ φάσμα τύπων εγγράφων—συμπεριλαμβανομένων των συμπιεσμένων αρχείων—σε μορφές φιλικές προς το web. Όταν χρειάζεται να εμφανίσετε μόνο ένα τμήμα ενός αρχείου ZIP (π.χ., έναν φάκελο που περιέχει εικόνες ή PDF), το viewer σας επιτρέπει να απομονώσετε και να αποδώσετε αυτόν τον φάκελο χωρίς να εξάγετε ολόκληρο το αρχείο.

**Άμεση απάντηση:** Το GroupDocs.Viewer διαβάζει το αρχείο ZIP, επιλέγει το φάκελο που καθορίζετε μέσω του `ArchiveOptions` και μεταδίδει κάθε αρχείο σε σελίδες HTML, ώστε να έχετε μια περιηγήσιμη προβολή web μόνο αυτού του φακέλου με μία ενέργεια.

## Γιατί να χρησιμοποιήσετε το GroupDocs.Viewer για την απόδοση φακέλων zip;

Το GroupDocs.Viewer επεξεργάζεται τα αρχεία απευθείας στη μνήμη, εξαλείφοντας την ανάγκη πλήρους εξαγωγής και διατηρώντας τα ευαίσθητα δεδομένα εκτός του συστήματος αρχείων. Μεταδίδει κάθε αρχείο, το αποδίδει σε HTML και υποστηρίζει μεγάλα αρχεία, προσφέροντας έναν γρήγορο, ασφαλή τρόπο για την εμφάνιση μόνο των απαιτούμενων περιεχομένων φακέλου.

**Ποσοτικοποιημένα οφέλη**
- **Ταχύτητα:** Η άμεση απόδοση είναι συνήθως 2‑3× πιο γρήγορη από μια αλυσίδα δύο βημάτων αποσυμπίεσης‑μετά‑μετατροπής.  
- **Αποτύπωμα μνήμης:** Το viewer μεταδίδει δεδομένα, επιτρέποντας την επεξεργασία αρχείων έως 5 GB σε JVM με heap 2 GB.  
- **Υποστήριξη μορφών:** Υποστηρίζονται πάνω από 50 μορφές εισόδου και εξόδου, συμπεριλαμβανομένων των DOCX, PDF, PPTX, HTML και κοινών τύπων εικόνων.  
- **Ασφάλεια:** Δεν γράφονται ενδιάμεσα αρχεία εκτός εάν επιλέξετε ρητά φάκελο εξόδου, μειώνοντας την επιφάνεια επίθεσης για κακόβουλα αρχεία.

## Προαπαιτούμενα
- **Java Development Kit (JDK)** 8 ή νεότερο.  
- **Maven** για διαχείριση εξαρτήσεων.  
- Βασική εξοικείωση με τις έννοιες προγραμματισμού Java.  

## Ρύθμιση του GroupDocs.Viewer για Java

### Διαμόρφωση Maven

Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση Viewer στο αρχείο `pom.xml`. Αυτό το βήμα κατεβάζει την πιο πρόσφατη σταθερή έκδοση της βιβλιοθήκης και τις μεταβιβαστικές εξαρτήσεις της.

**Αγκύρωση ορισμού:** `GroupDocs.Viewer` είναι η βασική κλάση που συντονίζει τη φόρτωση εγγράφων, την απόδοση και τη δημιουργία εξόδου για όλες τις υποστηριζόμενες μορφές.

### Απόκτηση άδειας

Για να ξεκλειδώσετε το πλήρες δυναμικό του GroupDocs.Viewer, μπορείτε να αποκτήσετε μια [δωρεάν δοκιμή](https://releases.groupdocs.com/viewer/java/) ή να αποκτήσετε προσωρινή άδεια μέσω της [σελίδας προσωρινής άδειας](https://purchase.groupdocs.com/temporary-license/). Για μακροπρόθεσμα έργα, σκεφτείτε την αγορά πλήρους άδειας.

## Βασική αρχικοποίηση

Αφού το Maven επιλύσει τα πακέτα, δημιουργήστε μια παρουσία `Viewer` που δείχνει στο αρχείο ZIP που θέλετε να επεξεργαστείτε. Το viewer θα διαχειριστεί για εσάς όλες τις χαμηλού επιπέδου λειτουργίες του αρχείου.

## Πώς να εξαγάγετε φάκελο από zip χρησιμοποιώντας το GroupDocs.Viewer

Όταν χρειάζεστε μόνο έναν συγκεκριμένο κατάλογο μέσα στο αρχείο, μπορείτε να πείτε στο viewer ακριβώς ποιον φάκελο να επεξεργαστεί. Αυτή η λειτουργία **extract folder from zip** γίνεται στη μνήμη, έτσι αποφεύγετε το κόστος της χειροκίνητης εξαγωγής.

**Άμεση απάντηση:** Καλέστε `viewer.view(zipPath, HtmlViewOptions.forFolder("TargetFolder"))` – το viewer διαβάζει το αρχείο, απομονώνει το `TargetFolder` και γράφει κάθε αρχείο ως σελίδα HTML στον φάκελο εξόδου που καθορίζετε.

### Ορισμός διαδρομής εξόδου

Δημιουργήστε μια βοηθητική μέθοδο που δείχνει στον κατάλογο όπου θα αποθηκευτούν τα αποδοθέντα αρχεία HTML. Αυτή η μέθοδος επιστρέφει μια πλήρως προσδιορισμένη διαδρομή συστήματος αρχείων και διασφαλίζει ότι ο φάκελος υπάρχει πριν ξεκινήσει η απόδοση.

### Απόδοση συγκεκριμένου φακέλου

Διαμορφώστε το viewer ώστε να στοχεύει έναν συγκεκριμένο φάκελο μέσα στο αρχείο και να δημιουργεί έξοδο HTML. `ArchiveOptions.setFolder` καθορίζει το φάκελο μέσα στο αρχείο που πρέπει να αποδοθεί. Η κλήση `ArchiveOptions.setFolder(...)` απομονώνει το φάκελο, ενώ το `HtmlViewOptions` ελέγχει τη συμπεριφορά απόδοσης HTML.

**Αγκύρωση ορισμού:** `HtmlViewOptions` είναι ένα αντικείμενο διαμόρφωσης που σας επιτρέπει να προσαρμόσετε την έξοδο HTML, όπως ονομασία σελίδων, διαχείριση εικόνων και ένταξη CSS.

**Επεξήγηση βασικών παραμέτρων**
- `pageFilePathFormat`: Ελέγχει το πρότυπο ονομασίας για κάθε αποδοθέν σελίδα HTML.  
- `viewOptions.getArchiveOptions().setFolder(...)`: Κατευθύνει το viewer να αποδώσει μόνο τον καθορισμένο φάκελο μέσα στο αρχείο ZIP.

### Προσαρμοσμένος ορισμός διαδρομής για φάκελο εξόδου

Εάν χρειάζεστε διαφορετική τοποθεσία εξόδου, απλώς προσαρμόστε τη βοηθητική μέθοδο που δημιουργεί τη διαδρομή εξόδου. Αυτή η ευελιξία σας επιτρέπει να αποθηκεύετε τα αποδοθέντα αρχεία μαζί με άλλα στοιχεία ή σε προσωρινή τοποθεσία για περαιτέρω επεξεργασία.

## Πρακτικές εφαρμογές
1. **Συστήματα διαχείρισης εγγράφων** – Εμφάνιση μόνο του σχετικού μέρους ενός μεγάλου αρχείου χωρίς να εκτίθεται όλο το περιεχόμενο.  
2. **Ψηφιακές βιβλιοθήκες** – Ροή επιλεγμένων τμημάτων e‑books ή συλλογών έρευνας απευθείας στον περιηγητή.  
3. **Πλατφόρμες νομικής ανασκόπησης** – Επικεντρωθείτε σε συγκεκριμένους φακέλους υποθέσεων μέσα σε τεράστια πακέτα zip, εξοικονομώντας χρόνο και χώρο.  

## Σκέψεις απόδοσης
- **Διαχείριση μνήμης:** Για πολύ μεγάλα αρχεία ZIP, αυξήστε το μέγεθος heap της JVM (`-Xmx4g`) ή επεξεργαστείτε φακέλους σε μικρότερες παρτίδες χρησιμοποιώντας σελιδοποίηση.  
- **Αποδοτικότητα I/O:** Γράψτε τα αποδοθέντα αρχεία σε γρήγορο SSD ή σε δίκτυο‑προσαρτημένο δίσκο για μείωση της καθυστέρησης.  
- **Επιλογές απόδοσης:** Ρυθμίστε την ποιότητα εικόνας (`HtmlViewOptions.setImageQuality(80)`) ή ενεργοποιήστε τη συμπίεση HTML (`HtmlViewOptions.setMinifyHtml(true)`) για ισορροπία ταχύτητας και οπτικής πιστότητας.  

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να μετατρέψετε zip σε HTML** και να αποδώσετε φακέλους zip σε Java χρησιμοποιώντας το GroupDocs.Viewer—από τη ρύθμιση Maven μέχρι την στόχευση ενός μόνο φακέλου μέσα σε ένα αρχείο και τη διαχείριση ζητημάτων απόδοσης. Ενσωματώστε αυτά τα βήματα στις εφαρμογές σας για γρήγορη, ασφαλή και φιλική προς το χρήστη πρόσβαση στο αρχειοθετημένο περιεχόμενο.

### Επόμενα βήματα
Εξερευνήστε πρόσθετες δυνατότητες του GroupDocs.Viewer όπως μετατροπή PDF, υδατογράφημα ή απόδοση πολλαπλών σελίδων για περαιτέρω εμπλουτισμό της αλυσίδας επεξεργασίας εγγράφων.

## Συχνές ερωτήσεις

**Q: Τι είναι το GroupDocs.Viewer για Java;**  
A: Είναι μια βιβλιοθήκη που επιτρέπει στους προγραμματιστές να αποδίδουν έγγραφα—συμπεριλαμβανομένων των αρχείων—απευθείας μέσα σε εφαρμογές Java.

**Q: Πώς εγκαθιστώ το GroupDocs.Viewer χρησιμοποιώντας Maven;**  
A: Προσθέστε τις ρυθμίσεις αποθετηρίου και εξαρτήσεων στο αρχείο `pom.xml` όπως φαίνεται στην ενότητα διαμόρφωσης Maven.

**Q: Μπορώ να χρησιμοποιήσω το GroupDocs.Viewer δωρεάν;**  
A: Διατίθεται δωρεάν δοκιμή, αλλά οι παραγωγικές εγκαταστάσεις απαιτούν έκδοση με άδεια.

**Q: Ποια είναι τα κοινά προβλήματα κατά την απόδοση αρχείων;**  
A: Βεβαιωθείτε ότι το όνομα του φακέλου ταιριάζει ακριβώς (διάκριση πεζών‑κεφαλαίων) και ότι το αρχείο δεν είναι προστατευμένο με κωδικό, εκτός εάν παρέχετε τα διαπιστευτήρια.

**Q: Πού μπορώ να λάβω υποστήριξη αν χρειαστεί;**  
A: Επισκεφθείτε το [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9) για βοήθεια από την κοινότητα ή συμβουλευτείτε την επίσημη τεκμηρίωση.

## Πόροι
- [Τεκμηρίωση](https://docs.groupdocs.com/viewer/java/)
- [Αναφορά API](https://reference.groupdocs.com/viewer/java/)
- [Λήψη GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Αγορά Άδειας](https://purchase.groupdocs.com/buy)
- [Δωρεάν Δοκιμή](https://releases.groupdocs.com/viewer/java/)
- [Προσωρινή Άδεια](https://purchase.groupdocs.com/temporary-license/)
- [Φόρουμ Υποστήριξης](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία Ενημέρωση:** 2026-08-24  
**Δοκιμάστηκε Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("path/to/archive.zip")) {
    // Rendering logic goes here
}
```

```java
import java.nio.file.Path;
import java.nio.file.Paths;

public static Path definePath() {
    return Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderArchiveFolder");
}
```

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public static void renderArchiveFolder() {
    Path outputDirectory = definePath();
    Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

    HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewOptions.getArchiveOptions().setFolder("ThirdFolderWithItems");

    try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
        viewer.view(viewOptions);
    }
}
```

```java
public static Path definePath() {
    return Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderArchiveFolder");
}
```

## Σχετικά Μαθήματα

- [Groupdocs Viewer Java Convert Archives Html](/viewer/java/export-conversion/groupdocs-viewer-java-convert-archives-html/)
- [convert zip to pdf with GroupDocs.Viewer Java - Custom Filenames](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [How to Convert Document to HTML Using GroupDocs.Viewer for Java](/viewer/java/rendering-basics/groupdocs-viewer-java-html-rendering/)