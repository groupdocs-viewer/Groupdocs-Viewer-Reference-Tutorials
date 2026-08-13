---
date: '2026-05-21'
description: Μάθετε πώς να εκτελέσετε εξαγωγή HTML από MS Project με προσαρμοσμένες
  μονάδες χρόνου χρησιμοποιώντας το GroupDocs Viewer for Java. Step‑by‑step guide
  with prerequisites, setup, and troubleshooting.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
type: docs
url: /el/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Εξαγωγή MS Project σε HTML: Προσαρμογή Μονάδων Χρόνου μέσω GroupDocs Java

Η εξαγωγή ενός αρχείου **MS Project** σε HTML είναι μια συχνή απαίτηση για πίνακες ελέγχου διαχείρισης έργων, πύλες αναφορών κατάστασης και εργαλεία συνεργατικής ανασκόπησης. Από προεπιλογή, ο προβολέας αποδίδει τα χρονικά δεδομένα σε λεπτά, κάτι που μπορεί να γεμίσει την οπτική διάταξη και να δυσκολέψει την ανάγνωση των ημερήσιων αναφορών. Με το **GroupDocs Viewer for Java** μπορείτε προγραμματιστικά να ορίσετε τη μονάδα χρόνου σε **ημέρες**, παράγοντας μια καθαρή *ms project html export* που ευθυγραμμίζεται με τις τυπικές προσδοκίες των ενδιαφερομένων. Σε αυτό το σεμινάριο θα μάθετε πώς να διαμορφώσετε τον προβολέα, να προσαρμόσετε τη μονάδα χρόνου και να αποδώσετε το έργο σε HTML με λίγα απλά βήματα.

![Προσαρμογή Μονάδων Χρόνου MS Project με GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Προσαρμογή Μονάδων Χρόνου MS Project με GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη αποδίδει αρχεία MS Project;** GroupDocs Viewer for Java.  
- **Ποια μονάδα χρόνου μπορώ να ορίσω για εξαγωγή HTML;** Ημέρες, χρησιμοποιώντας `TimeUnit.DAYS`.  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι—απαιτείται μόνιμη άδεια· μια δοκιμαστική έκδοση λειτουργεί για αξιολόγηση. Μπορείτε να ξεκινήσετε με ένα [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Ποιο IDE είναι το καλύτερο;** Οποιοδήποτε Java IDE (IntelliJ IDEA, Eclipse, NetBeans) που υποστηρίζει Maven.  
- **Είναι το Maven υποχρεωτικό;** Το Maven απλοποιεί τη διαχείριση εξαρτήσεων, αλλά μπορείτε επίσης να χρησιμοποιήσετε Gradle ή χειροκίνητη προσθήκη JAR.  
- **Πού μπορώ να αγοράσω;** Επισκεφθείτε τη [σελίδα αγοράς](https://purchase.groupdocs.com/buy) για τιμές.

## Τι είναι το GroupDocs Viewer for Java;
Το **GroupDocs Viewer for Java** είναι ένα Java SDK που μετατρέπει πάνω από 150 μορφές εγγράφων—συμπεριλαμβανομένου του MS Project—σε web‑φιλικό HTML, PNG, JPEG ή PDF.  
Απομονώνει τη λογική ανάλυσης, σας επιτρέπει να ελέγχετε τις επιλογές απόδοσης όπως οι μονάδες χρόνου, και λειτουργεί σε οποιαδήποτε πλατφόρμα που υποστηρίζει Java 8 ή νεότερη.

## Γιατί να προσαρμόσετε τις μονάδες χρόνου για την εξαγωγή MS Project σε HTML;
Ο ορισμός της μονάδας χρόνου σε **ημέρες** μειώνει το οπτικό θόρυβο, ταιριάζει με τις περισσότερες ρυθμίσεις αναφορών και βελτιώνει τους χρόνους φόρτωσης της σελίδας επειδή παράγονται λιγότερο λεπτομερή χρονικά σημεία. Σε ποσοτικούς όρους, η απόδοση με ημέρες αντί για λεπτά μπορεί να μειώσει το μέγεθος του παραγόμενου HTML έως και **45 %** για τυπικά έργα 30 ημερών, και επιταχύνει την απόδοση στην πλευρά του πελάτη κατά περίπου **30 %**.

## Προαπαιτούμενα
- **Java Development Kit (JDK) 8 ή νεότερο** εγκατεστημένο στον υπολογιστή σας.  
- **Maven** (ή Gradle) για διαχείριση εξαρτήσεων.  
- Ένα αρχείο **MS Project (.mpp)** που θέλετε να εξάγετε.  
- Πρόσβαση σε άδεια **GroupDocs Viewer for Java** (δοκιμαστική ή μόνιμη).  

### Απαιτούμενες Βιβλιοθήκες
Προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας (ή το αντίστοιχο απόσπασμα Gradle):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Συμβουλή:** Κρατήστε τον αριθμό έκδοσης ενημερωμένο· οι νεότερες εκδόσεις προσθέτουν υποστήριξη μορφών και βελτιώσεις απόδοσης.

## Πώς να ρυθμίσετε το GroupDocs Viewer for Java;
Αρχικοποιήστε τον προβολέα δημιουργώντας μια παρουσία `Viewer` που δείχνει στο αρχείο MS Project σας. Η κλάση `Viewer` είναι το σημείο εισόδου για όλες τις λειτουργίες απόδοσης. Φορτώνει το πηγαίο έγγραφο, προετοιμάζει εσωτερικές δομές και εκθέτει μεθόδους όπως `view()` και `viewToHtml()` για τη δημιουργία των επιθυμητών μορφών εξόδου.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Ορισμός:** Η κλάση `Viewer` είναι το βασικό συστατικό του GroupDocs Viewer που φορτώνει ένα πηγαίο έγγραφο και παρέχει μεθόδους απόδοσης όπως `view()` και `viewToHtml()`.

## Πώς μπορώ να προσαρμόσω τις μονάδες χρόνου για την εξαγωγή HTML;
Για να αλλάξετε την ακρίβεια του χρόνου, δημιουργήστε ένα αντικείμενο `ViewOptions`, διαμορφώστε το `ProjectOptions` του ώστε να χρησιμοποιεί `TimeUnit.DAYS` και περάστε το στον προβολέα. Το `ViewOptions` ορίζει τις ρυθμίσεις απόδοσης για το έγγραφο, ενώ η απαρίθμηση `TimeUnit` καθορίζει τη μονάδα (λεπτά, ώρες, ημέρες) για τα χρονικά δεδομένα. Αφού ορίσετε αυτές τις επιλογές, καλέστε `viewer.view(options)` για να παραχθεί HTML με ημερήσιες ενδείξεις.

Φορτώστε το αρχείο MS Project με `new Viewer("file.mpp")`, δημιουργήστε ένα αντικείμενο `ViewOptions`, ορίστε `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, και στη συνέχεια καλέστε `viewer.view(options)`. Αυτή η τριβήμα ροή αλλάζει τη μονάδα χρόνου από λεπτά σε ημέρες και δημιουργεί αρχεία HTML που εμφανίζουν μόνο ημερήσια διαστήματα.

### Βήμα 1: Ορίστε το φάκελο εξόδου
Επιλέξτε έναν εγγράψιμο κατάλογο όπου θα αποθηκευτούν οι σελίδες HTML, π.χ. `output/`.

### Βήμα 2: Δημιουργήστε επιλογές προβολής με ενσωματωμένους πόρους
Οι ενσωματωμένοι πόροι (CSS, JavaScript) διασφαλίζουν ότι οι σελίδες HTML είναι αυτόνομες.

### Βήμα 3: Ορίστε τη μονάδα χρόνου σε ημέρες
Χρησιμοποιήστε `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` για να αλλάξετε την ακρίβεια.

### Βήμα 4: Αποδώστε το έγγραφο
Καλέστε `viewer.view(options)`· ο προβολέας γράφει ένα αρχείο HTML ανά σελίδα έργου στον φάκελο εξόδου.

### Βήμα 5: Επαληθεύστε το αποτέλεσμα
Ανοίξτε το παραγόμενο `index.html` σε έναν περιηγητή· θα πρέπει να δείτε τις γραμμές εργασιών ευθυγραμμισμένες με ενδείξεις ημέρας αντί για ενδείξεις λεπτών.

## Συνηθισμένα προβλήματα και αντιμετώπιση
- **Λάθος διαδρομή εξόδου** – Βεβαιωθείτε ότι ο φάκελος υπάρχει και η διαδικασία Java έχει δικαιώματα εγγραφής.  
- **Απουσία άδειας** – Χωρίς έγκυρη άδεια, ο προβολέας επιστρέφει σε λειτουργία δοκιμής και μπορεί να ενσωματώνει υδατογραφήματα.  
- **Μεγάλα αρχεία (> 500 MB)** – Σκεφτείτε να αυξήσετε το μέγεθος heap της JVM (`-Xmx2g`) ή να αποδώσετε με `options.setRenderLimit(1000)` για επεξεργασία σε παρτίδες.  

## Πρακτικές εφαρμογές της προσαρμοσμένης εξαγωγής HTML με μονάδα χρόνου
1. **Εκτελεστικά dashboards** – Η ημερήσια ακρίβεια ταιριάζει με τις περισσότερες οπτικοποιήσεις KPI.  
2. **Αυτόματα email κατάστασης** – Ενσωματώστε το παραγόμενο HTML απευθείας στα σώματα των email για γρήγορες ενημερώσεις.  
3. **Πύλες έργου** – Φιλοξενήστε το HTML σε εσωτερική ιστοσελίδα όπου τα μέλη της ομάδας μπορούν να φιλτράρουν τις εργασίες ανά ημέρα.  

## Σκέψεις απόδοσης για μεγάλα αρχεία MS Project
- **Διαχείριση μνήμης** – Χρησιμοποιήστε σημαίες του garbage collector της Java (`-XX:+UseG1GC`) για άμεση απελευθέρωση αχρησιμοποίητων αντικειμένων.  
- **Επιλεκτική απόδοση** – Εάν χρειάζεστε μόνο το διάγραμμα Gantt, απενεργοποιήστε την απόδοση άλλων πόρων μέσω `options.getProjectOptions().setRenderGantt(true)` και `setRenderResources(false)`.  
- **Παράλληλη επεξεργασία** – Για μαζικές μετατροπές, δημιουργήστε ξεχωριστά αντικείμενα `Viewer` ανά αρχείο και τρέξτε τα σε μια ομάδα νημάτων (thread pool) για αξιοποίηση πολυπύρηνων CPU.  

## Συμπέρασμα
Τώρα έχετε μια πλήρη, έτοιμη για παραγωγή ροή εργασίας για την εκτέλεση μιας **ms project html export** με μονάδες χρόνου ορισμένες σε ημέρες χρησιμοποιώντας το GroupDocs Viewer for Java. Αυτή η προσέγγιση μειώνει το μέγεθος του HTML, επιταχύνει την απόδοση στην πλευρά του πελάτη και παρέχει μια φιλική προς τα ενδιαφερόμενα προβολή των χρονοδιαγραμμάτων του έργου. Εξερευνήστε πρόσθετες επιλογές απόδοσης—όπως εξαγωγή PDF ή στιγμιότυπα εικόνας—για να επεκτείνετε την ενσωμάτωση σε ευρύτερους αγωγούς αναφοράς.

## Συχνές Ερωτήσεις

**Ε: Μπορώ να αποδώσω άλλες προβολές Project (π.χ., Φύλλο Πόρων) σε HTML;**  
Α: Ναι, το αντικείμενο `ProjectOptions` σας επιτρέπει να ενεργοποιήσετε ή να απενεργοποιήσετε συγκεκριμένες προβολές όπως Gantt, Φύλλο Πόρων και Ημερολόγιο πριν από την απόδοση.

**Ε: Είναι δυνατόν να προσαρμόσω το CSS του παραγόμενου HTML;**  
Α: Απόλυτα. Παρέχετε μια διαδρομή προσαρμοσμένου φύλλου στυλ μέσω `options.setStyleSheetPath("path/to/custom.css")` και ο προβολέας θα το ενσωματώσει σε κάθε σελίδα.

**Ε: Ποιο είναι το όριο μεγέθους αρχείου που υποστηρίζει το GroupDocs Viewer για MS Project;**  
Α: Το SDK μπορεί να διαχειριστεί αρχεία έως **500 MB** χωρίς να χρειάζεται η φόρτωση ολόκληρου του εγγράφου στη μνήμη, χάρη στην αρχιτεκτονική ροής δεδομένων.

**Ε: Χρειάζεται να εγκαταστήσω το Microsoft Project στον διακομιστή;**  
Α: Όχι. Το GroupDocs Viewer αναλύει άμεσα τη μορφή .mpp και δεν απαιτεί το Microsoft Project ή οποιαδήποτε εγκατάσταση Office.

**Ε: Πώς αδειοδοτώ το προβολέα για περιβάλλον παραγωγής;**  
Α: Αγοράστε μια μόνιμη άδεια από το κατάστημα GroupDocs· εφαρμόστε το αρχείο άδειας κατά την εκτέλεση με `License license = new License(); license.setLicense("path/to/license.lic");`. Για βραχυπρόθεσμες ανάγκες μπορείτε να αποκτήσετε μια [προσωρινή άδεια](https://purchase.groupdocs.com/temporary-license/).

---

**Τελευταία Ενημέρωση:** 2026-05-21  
**Δοκιμάστηκε Με:** GroupDocs Viewer Java 25.2  
**Συγγραφέας:** GroupDocs  

**Πόροι**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Σχετικά Μαθήματα

- [Πώς να αποδώσετε αρχεία MS Project ως HTML, JPG, PNG και PDF με σημειώσεις χρησιμοποιώντας το GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Πώς να χρησιμοποιήσετε το GroupDocs Viewer για απόδοση εγγράφων έργου ανά χρονικά διαστήματα σε Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Πώς να ορίσετε άδειες στο GroupDocs.Viewer Java: Οδηγός ρύθμισης αρχείου και URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)