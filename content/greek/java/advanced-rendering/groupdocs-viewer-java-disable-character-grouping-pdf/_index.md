---
date: '2026-09-05'
description: Μάθετε πώς να δημιουργήσετε html από pdf και να απενεργοποιήσετε την
  character grouping χρησιμοποιώντας το GroupDocs Viewer for Java για ακριβή αναπαράσταση
  κειμένου.
keywords:
- generate html from pdf
- render pdf to html
- convert pdf to html
lastmod: '2026-09-05'
og_description: Δημιουργήστε html από pdf με το GroupDocs Viewer for Java ενώ απενεργοποιείτε
  την character grouping για ακριβή glyph placement. Μάθετε την υλοποίηση βήμα‑βήμα.
og_image_alt: GroupDocs Viewer for Java rendering PDF to HTML with precise character
  placement
og_title: Δημιουργία html από pdf & απενεργοποίηση grouping – GroupDocs Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-05'
  description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  headline: Generate html from pdf & disable grouping – GroupDocs Java
  type: TechArticle
- description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  name: Generate html from pdf & disable grouping – GroupDocs Java
  steps:
  - name: define output directory
    text: '**Why?** This ensures your rendered HTML files are stored in a dedicated
      folder, making it easy to locate and manage them later.'
  - name: configure file path format
    text: '**Why?** Using a placeholder (`{0}`) lets the viewer create a separate
      HTML file for each PDF page, keeping the output organized.'
  - name: initialize HTML view options
    text: '**Why?** Embedded resources bundle images, fonts, and CSS directly with
      each HTML page, which is ideal for web‑based viewers or e‑learning platforms.'
  - name: disable character grouping
    text: '`setDisableCharsGrouping(true)` disables the default behavior of grouping
      adjacent characters, ensuring each glyph is rendered separately. **Why?** This
      is the crucial line that tells the rendering engine **not** to merge adjacent
      characters, guaranteeing that the generated HTML reflects the exact g'
  - name: render the document
    text: '`Viewer` is the primary class that opens a document and provides rendering
      capabilities. **Why?** Wrapping the `Viewer` in a try‑with‑resources block guarantees
      that all native resources are released automatically, preventing memory leaks
      in long‑running applications.'
  type: HowTo
- questions:
  - answer: It forces the renderer to treat each character as an independent element,
      preserving exact layout.
    question: What does “disable grouping” do?
  - answer: '`viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.'
    question: Which API option controls this?
  - answer: A trial works for testing, but a full license is required for production.
    question: Do I need a license?
  - answer: Yes—use `HtmlViewOptions` to create HTML output while disabling grouping.
    question: Can I generate html from pdf at the same time?
  - answer: It’s primarily for PDFs, but the viewer supports many other formats.
    question: Is this feature limited to PDFs?
  type: FAQPage
tags:
- generate html
- GroupDocs Viewer
- Java document rendering
title: Δημιουργία html από pdf & απενεργοποίηση grouping – GroupDocs Java
type: docs
url: /el/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Δημιουργία html από pdf και απενεργοποίηση ομαδοποίησης με GroupDocs Viewer για Java

Σε πολλά έργα χρειάζεται να **δημιουργήσετε html από pdf** διατηρώντας κάθε γλύφο ακριβώς εκεί που ανήκει. Αυτό ισχύει ιδιαίτερα για σύνθετα συστήματα γραφής, αρχαίες γλώσσες ή νομικά έγγραφα όπου ένας μόνο λανθασμένος χαρακτήρας μπορεί να αλλάξει το νόημα. Σε αυτό το tutorial θα σας καθοδηγήσουμε στη διαδικασία απόδοσης PDF σε HTML με το GroupDocs Viewer για Java και θα σας δείξουμε **πώς να απενεργοποιήσετε την ομαδοποίηση** ώστε κάθε χαρακτήρας να αντιμετωπίζεται ως ανεξάρτητο στοιχείο.

![Ακριβείς Τεχνικές Απόδοσης με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Γρήγορες απαντήσεις
- **Τι κάνει η “απενεργοποίηση ομαδοποίησης”;** Αναγκάζει τον renderer να αντιμετωπίζει κάθε χαρακτήρα ως ανεξάρτητο στοιχείο, διατηρώντας την ακριβή διάταξη.  
- **Ποια επιλογή API ελέγχει αυτό;** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Χρειάζομαι άδεια;** Μια δοκιμαστική έκδοση λειτουργεί για δοκιμές, αλλά απαιτείται πλήρης άδεια για παραγωγή.  
- **Μπορώ να δημιουργήσω html από pdf ταυτόχρονα;** Ναι—χρησιμοποιήστε `HtmlViewOptions` για να δημιουργήσετε έξοδο HTML ενώ απενεργοποιείτε την ομαδοποίηση.  
- **Είναι αυτή η λειτουργία περιορισμένη μόνο στα PDF;** Είναι κυρίως για PDF, αλλά ο viewer υποστηρίζει πολλές άλλες μορφές.

## Τι είναι η δημιουργία html από pdf;
`generate html from pdf` περιγράφει τη διαδικασία μετατροπής ενός εγγράφου PDF σε ένα σύνολο σελίδων HTML που διατηρούν την αρχική διάταξη, τις γραμματοσειρές και τις εικόνες. Αυτή η μετατροπή επιτρέπει εύκολη προβολή στο web, ευρετηρίαση και αλληλεπίδραση χωρίς την ανάγκη πρόσθετου PDF.

## Γιατί να χρησιμοποιήσετε το GroupDocs Viewer για Java;
Το GroupDocs.Viewer για Java υποστηρίζει **πάνω από 100 μορφές εισόδου** και μπορεί να αποδώσει PDF έως **500 σελίδες** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη. Η βιβλιοθήκη επεξεργάζεται κάθε σελίδα με ροή, μειώνοντας τη χρήση heap έως **70 %** σε σύγκριση με τη φόρτωση ολόκληρου του εγγράφου. Αυτές οι μετρήσιμες δυνατότητες το καθιστούν αξιόπιστη επιλογή για pipelines εγγράφων υψηλού όγκου και επιχειρησιακού επιπέδου.

## Εισαγωγή

Κατά την εργασία με έγγραφα PDF, η ακρίβεια στην απόδοση είναι κρίσιμη—ιδιαίτερα όταν αντιμετωπίζονται σύνθετες δομές κειμένου όπως ιερογλυφικά ή γλώσσες που απαιτούν ακριβή αναπαράσταση χαρακτήρων. Η λειτουργία «Ομαδοποίηση Χαρακτήρων» συχνά προκαλεί προβλήματα ομαδοποιώντας λανθασμένα χαρακτήρες, οδηγώντας σε παρερμηνεία του περιεχομένου του εγγράφου. Αυτό μπορεί να είναι ιδιαίτερα προβληματικό για χρήστες που χρειάζονται ακριβή αντιγραφή της διάταξης κειμένου των εγγράφων τους.

**GroupDocs.Viewer for Java** είναι μια βιβλιοθήκη διακομιστή που αποδίδει πάνω από 100 μορφές εγγράφων σε HTML, εικόνες και PDF, παρέχοντας πιστότητα pixel‑perfect.

### Προαπαιτούμενα

Πριν ξεκινήσετε την υλοποίηση του κώδικα, βεβαιωθείτε ότι πληροίτε τις ακόλουθες απαιτήσεις:
- **Βιβλιοθήκες & εξαρτήσεις**: Θα χρειαστείτε το GroupDocs.Viewer για Java έκδοση 25.2 ή νεότερη.  
- **Ρύθμιση περιβάλλοντος**: Εγκαταστήστε ένα Java Development Kit (JDK) και διαμορφώστε το IDE σας για έργα Maven.  
- **Προαπαιτούμενες γνώσεις**: Βασικός προγραμματισμός Java, διαχείριση συστήματος αρχείων και εξοικείωση με Maven.

## Πώς να δημιουργήσετε html από pdf με το GroupDocs Viewer

Η δημιουργία html από pdf είναι μια διαδικασία δύο βημάτων: διαμορφώστε το viewer, στη συνέχεια αποδώστε το έγγραφο. Το κλειδί είναι να απενεργοποιήσετε την ομαδοποίηση χαρακτήρων πριν από την απόδοση ώστε η έξοδος HTML να αντικατοπτρίζει την αρχική διάταξη PDF χαρακτήρα‑με‑χαρακτήρα.

### Ρύθμιση του GroupDocs.Viewer για Java

#### Εγκατάσταση μέσω Maven

Add the following dependency to your `pom.xml`:

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

#### Απόκτηση άδειας

Για πλήρη αξιοποίηση του GroupDocs.Viewer, εξετάστε την απόκτηση άδειας:
- **Δωρεάν δοκιμή**: Ξεκινήστε με τη δωρεάν δοκιμή για να δοκιμάσετε τις λειτουργίες.  
- **Προσωρινή άδεια**: Αιτηθείτε προσωρινή άδεια εάν χρειάζεστε περισσότερο χρόνο.  
- **Αγορά**: Για μακροπρόθεσμα έργα, η αγορά άδειας είναι συνιστώμενη.

#### Βασική αρχικοποίηση και ρύθμιση

`HtmlViewOptions` configures the output format and options for rendering a document to HTML.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Οδηγός υλοποίησης

#### Χαρακτηριστικό: απενεργοποίηση ομαδοποίησης χαρακτήρων

Παρακάτω αναλύουμε κάθε γραμμή του παραδείγματος ώστε να καταλάβετε **γιατί** το κάνουμε και **πώς** συμβάλλει στη δημιουργία html από pdf χωρίς ανεπιθύμητη συγχώνευση χαρακτήρων.

##### Βήμα 1: ορισμός καταλόγου εξόδου  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Γιατί;** Αυτό εξασφαλίζει ότι τα αποδοθέντα αρχεία HTML αποθηκεύονται σε έναν αφιερωμένο φάκελο, καθιστώντας εύκολο τον εντοπισμό και τη διαχείρισή τους αργότερα.

##### Βήμα 2: διαμόρφωση μορφής διαδρομής αρχείου  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Γιατί;** Η χρήση ενός placeholder (`{0}`) επιτρέπει στο viewer να δημιουργήσει ξεχωριστό αρχείο HTML για κάθε σελίδα PDF, διατηρώντας την έξοδο οργανωμένη.

##### Βήμα 3: αρχικοποίηση επιλογών προβολής HTML  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Γιατί;** Οι ενσωματωμένοι πόροι ενσωματώνουν εικόνες, γραμματοσειρές και CSS απευθείας σε κάθε σελίδα HTML, κάτι που είναι ιδανικό για web‑viewers ή πλατφόρμες e‑learning.

##### Βήμα 4: απενεργοποίηση ομαδοποίησης χαρακτήρων  

`setDisableCharsGrouping(true)` disables the default behavior of grouping adjacent characters, ensuring each glyph is rendered separately.

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Γιατί;** Αυτή είναι η κρίσιμη γραμμή που λέει στη μηχανή απόδοσης **να μην** συγχωνεύει γειτονικούς χαρακτήρες, εξασφαλίζοντας ότι το παραγόμενο HTML αντανακλά την ακριβή τοποθέτηση των γλυφών από το πηγαίο PDF.

##### Βήμα 5: απόδοση του εγγράφου  

`Viewer` is the primary class that opens a document and provides rendering capabilities.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Γιατί;** Η τοποθέτηση του `Viewer` σε μπλοκ try‑with‑resources εγγυάται ότι όλοι οι εγγενείς πόροι απελευθερώνονται αυτόματα, αποτρέποντας διαρροές μνήμης σε εφαρμογές που εκτελούνται για μεγάλο χρονικό διάστημα.

## Πώς η απενεργοποίηση της ομαδοποίησης χαρακτήρων βελτιώνει την πιστότητα του HTML;

Η απενεργοποίηση της ομαδοποίησης χαρακτήρων αναγκάζει τη μηχανή να εκτυπώνει κάθε γλύφο ως ξεχωριστό στοιχείο HTML, διατηρώντας το αρχικό διάστημα, τις συνδέσεις και τα διακριτικά ακριβώς όπως εμφανίζονται στο πηγαίο PDF. Αυτό οδηγεί σε πιστή διαδικτυακή αναπαράσταση που είναι απαραίτητη για συστήματα γραφής όπου η σειρά και το διάστημα των χαρακτήρων μεταδίδουν νόημα, όπως η Αραβική, η Devanagari ή τα αρχαία ιερογλυφικά κείμενα.

## Ποιες είναι οι επιπτώσεις στην απόδοση της απενεργοποίησης της ομαδοποίησης;

Η απενεργοποίηση της ομαδοποίησης αυξάνει ελαφρώς τους κύκλους CPU επειδή ο renderer επεξεργάζεται κάθε χαρακτήρα ξεχωριστά. Στην πράξη, το πρόσθετο κόστος είναι κάτω από **5 %** για τυπικά PDF 100 σελίδων και παραμένει κάτω από **12 %** για έγγραφα που υπερβαίνουν τις 500 σελίδες, εφόσον το heap του JVM είναι διαμορφωμένο κατάλληλα (π.χ., `-Xmx2g`). Η ανταλλαγή αξίζει όταν απαιτείται ακριβής οπτική πιστότητα.

## Συνηθισμένα προβλήματα και λύσεις

- **FileNotFoundException** – Ελέγξτε ξανά τη διαδρομή που περνάτε στο `new Viewer(...)`. Χρησιμοποιήστε απόλυτες διαδρομές ή `Path.of(...)` για σαφήνεια.  
- **Δικαιώματα εγγραφής** – Βεβαιωθείτε ότι ο φάκελος εξόδου είναι εγγράψιμος από τη διαδικασία Java· σε Linux ίσως χρειαστεί να προσαρμόσετε τα δικαιώματα φακέλου (`chmod 775`).  
- **Ασυμφωνία έκδοσης** – Η επιλογή `setDisableCharsGrouping` είναι διαθέσιμη από την έκδοση 25.2. Επαληθεύστε ότι το `pom.xml` σας αντικατοπτρίζει τη σωστή έκδοση.

## Πρακτικές εφαρμογές

1. **Διατήρηση γλώσσας** – Ιδανικό για απόδοση εγγράφων στα Κινέζικα, Ιαπωνικά, Αραβικά ή αρχαία συστήματα γραφής όπου το διάστημα χαρακτήρων μεταφέρει νόημα.  
2. **Νομικά & οικονομικά έγγραφα** – Εγγυάται ακριβή αντιγραφή κειμένου για έγγραφα με υψηλές απαιτήσεις συμμόρφωσης.  
3. **Εκπαιδευτικοί πόροι** – Ιδανικό για σχολικά εγχειρίδια που περιλαμβάνουν σύνθετα διαγράμματα, σημειώσεις ή πολυγλωσσικό περιεχόμενο.

## Σκέψεις απόδοσης

- **Βελτιστοποίηση χρήσης πόρων** – Μεγάλα PDF μπορούν να καταναλώνουν σημαντική μνήμη. Επεξεργαστείτε τις σελίδες σε παρτίδες και απελευθερώστε άμεσα τις παρουσίες `Viewer`.  
- **Διαχείριση μνήμης Java** – Ρυθμίστε το heap του JVM (`-Xmx2g` ή υψηλότερο) εάν προβλέπετε επεξεργασία PDF πολλών εκατοντάδων σελίδων.  
- **Παράλληλη απόδοση** – Για μαζικές μετατροπές, δημιουργήστε ξεχωριστά νήματα, το καθένα με τη δική του παρουσία `Viewer`, για να αξιοποιήσετε πολυπύρηνους επεξεργαστές.

## Συχνές ερωτήσεις

**Q:** *Γιατί θα χρειαστεί να απενεργοποιήσω την ομαδοποίηση χαρακτήρων;*  
**A:** Η απενεργοποίηση της ομαδοποίησης αποτρέπει τον renderer από τη συγχώνευση χαρακτήρων που ανήκουν σε διαφορετικούς γλύφους, κάτι που είναι ουσιώδες για συστήματα γραφής όπου το διάστημα και η σειρά μεταδίδουν νόημα.

**Q:** *Ισχύει η ρύθμιση `setDisableCharsGrouping` μόνο για έξοδο HTML;*  
**A:** Όχι, επηρεάζει τη βασική μηχανή απόδοσης PDF, έτσι οποιαδήποτε μορφή εξόδου (HTML, PNG, JPEG, κλπ.) θα αντικατοπτρίζει την αλλαγή.

**Q:** *Μπορώ να συνδυάσω αυτή τη ρύθμιση με προσαρμοσμένες γραμματοσειρές;*  
**A:** Ναι—φορτώστε τις προσαρμοσμένες γραμματοσειρές πριν την αρχικοποίηση του `Viewer`, και ο κανόνας ομαδοποίησης θα ισχύει ακόμη.

**Q:** *Επηρεάζει η απενεργοποίηση της ομαδοποίησης την απόδοση;*  
**A:** Ελαφρώς, επειδή η μηχανή επεξεργάζεται κάθε χαρακτήρα ξεχωριστά, αλλά η επίπτωση είναι ελάχιστη για τα περισσότερα έγγραφα (συνήθως κάτω από 5 % επιπλέον φόρτο).

**Q:** *Υπάρχει τρόπος να εναλλάσσετε την ομαδοποίηση ανά σελίδα;*  
**A:** Προς το παρόν η επιλογή είναι παγκόσμια ανά αντικείμενο `PdfOptions`; θα χρειαστείτε ξεχωριστές παρουσίες `Viewer` για διαφορετικές σελίδες εάν απαιτείται μεικτή συμπεριφορά.

## Πόροι

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία ενημέρωση:** 2026-09-05  
**Δοκιμή με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

## Σχετικά Μαθήματα

- [Πώς να μετατρέψετε pdf σε html και να βελτιστοποιήσετε την ποιότητα εικόνας σε Java με το GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [Απόδοση PDF Layered Java – Αποτελεσματική Στρωματική Απόδοση PDF με το GroupDocs.Viewer](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)
- [Groupdocs Viewer Java Ανταποκρινόμενη Απόδοση Html](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)