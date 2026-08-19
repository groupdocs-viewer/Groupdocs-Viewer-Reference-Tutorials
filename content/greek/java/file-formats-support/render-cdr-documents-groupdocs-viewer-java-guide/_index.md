---
date: '2026-08-19'
description: Μάθετε πώς να μετατρέψετε cdr σε html, καθώς και jpg, png και pdf, χρησιμοποιώντας
  GroupDocs.Viewer for Java. Περιλαμβάνει setup, code examples, και performance tips.
keywords:
- convert cdr to html
- convert cdr to pdf
- convert cdr to jpg
- convert cdr to png
- java convert coreldraw
lastmod: '2026-08-19'
og_description: Μάθετε πώς να μετατρέψετε cdr σε html, jpg, png και pdf χρησιμοποιώντας
  GroupDocs.Viewer for Java. Step‑by‑step guide με setup, code snippets, και performance
  best practices.
og_image_alt: Guide showing conversion of CorelDRAW CDR files to HTML, JPG, PNG, and
  PDF using GroupDocs.Viewer for Java
og_title: Μετατροπή cdr σε html, jpg, png, pdf με GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  headline: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  type: TechArticle
- description: Learn how to convert cdr to html, as well as jpg, png, and pdf, using
    GroupDocs.Viewer for Java. Includes setup, code examples, and performance tips.
  name: Convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java
  steps:
  - name: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
    text: '**Libraries and dependencies** – GroupDocs.Viewer added to your Maven project.'
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Basic Java knowledge** – to understand the code snippets.'
    text: '**Basic Java knowledge** – to understand the code snippets.'
  type: HowTo
- questions:
  - answer: Yes. Load the file with a `Viewer` instance that accepts a password parameter
      (see the API docs).
    question: Can I convert password‑protected CDR files?
  - answer: No hard limit, but very large files may require more memory; consider
      processing page‑by‑page.
    question: Is there a limit on the number of pages that can be converted at once?
  - answer: When using `HtmlViewOptions.forEmbeddedResources`, fonts are embedded
      as Base64, ensuring consistent rendering across browsers.
    question: Does the HTML output include embedded fonts?
  - answer: '`JpgViewOptions` provides a `setQuality(int)` method where you can specify
      a value from 1‑100.'
    question: How do I control JPEG quality?
  - answer: Absolutely—GroupDocs.Viewer is platform‑agnostic as long as the JDK is
      installed.
    question: Can I convert CDR files on a Linux server?
  type: FAQPage
tags:
- convert cdr
- groupdocs.viewer
- java file conversion
- coreldraw cdr
- document rendering
title: Μετατροπή cdr σε html, jpg, png, pdf με GroupDocs.Viewer Java
type: docs
url: /el/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# Μετατροπή cdr σε html, jpg, png, pdf με GroupDocs.Viewer Java

Αν χρειάζεστε **convert cdr to html** (ή σε JPG, PNG και PDF) γρήγορα και αξιόπιστα, βρήκατε το σωστό tutorial. Σε αυτόν τον οδηγό θα καλύψουμε όλα όσα χρειάζεστε—από την εγκατάσταση του GroupDocs.Viewer για Java μέχρι την απόδοση αρχείων CorelDRAW (CDR) σε ιστοσελίδες HTML φιλικές στο web, εικόνες υψηλής ποιότητας και PDF που διαβάζονται παντού. Στο τέλος, θα μπορείτε να ενσωματώσετε αυτές τις μετατροπές σε οποιαδήποτε εφαρμογή Java με λίγες μόνο γραμμές κώδικα.

![Απόδοση αρχείων CDR με GroupDocs.Viewer για Java](/viewer/file-formats-support/render-cdr-files.png)

[Απόδοση αρχείων CDR με GroupDocs.Viewer για Java](/viewer/file-formats-support/render-cdr-files.png)

## Γρήγορες απαντήσεις
- **Ποια βιβλιοθήκη μετατρέπει CDR σε HTML;** GroupDocs.Viewer for Java.  
- **Μπορώ επίσης να μετατρέψω CDR σε JPG, PNG και PDF;** Ναι—χρησιμοποιήστε το ίδιο Viewer API με διαφορετικές επιλογές προβολής.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή ή προσωρινή άδεια λειτουργεί για δοκιμές· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποια έκδοση Java απαιτείται;** JDK 8 ή νεότερη.  
- **Υποστηρίζεται η μαζική μετατροπή;** Απόλυτα—απλώς κάντε βρόχο πάνω από τα αρχεία με την ίδια παρουσία Viewer.

## Τι είναι το “convert cdr to html”;
Η μετατροπή cdr σε html σημαίνει τη μετατροπή ενός αρχείου vector CorelDRAW σε τυπικό HTML markup, προαιρετικά ενσωματώνοντας εικόνες και στυλ ώστε το σχέδιο να μπορεί να προβληθεί απευθείας σε έναν web browser χωρίς την ανάγκη του αρχικού λογισμικού σχεδίασης. Η διαδικασία διατηρεί τη αρχική διάταξη, τα χρώματα και τα vector σχήματα μετατρέποντάς τα σε κλιμακούμενα στοιχεία SVG ή raster εικόνες ενσωματωμένες στο HTML, επιτρέποντας ακριβή οπτική αναπαράσταση σε browsers ενώ διατηρεί το μέγεθος του αρχείου χαμηλό.

## Γιατί να μετατρέψετε cdr σε html, jpg, png ή pdf;
Μπορείτε να αποδώσετε ένα μόνο πηγαίο CDR σε τέσσερις ευρέως υποστηριζόμενες μορφές, η καθεμία με διαφορετικό σκοπό: HTML για άμεση προεπισκόπηση στο web, JPG/PNG για raster εικόνες, και PDF για εκτυπώσιμα, αρχειοθετημένα έγγραφα. Αυτή η ευελιξία σας επιτρέπει να παρέχετε τον βέλτιστο τύπο αρχείου σε κάθε πελάτη, να μειώσετε τον διπλό αποθηκευτικό χώρο και να εξασφαλίσετε τη μακροπρόθεσμη διαθεσιμότητα των πόρων σας.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

1. **Βιβλιοθήκες και εξαρτήσεις** – GroupDocs.Viewer προστέθηκε στο Maven project σας.  
2. **Java Development Kit (JDK)** – έκδοση 8 ή νεότερη εγκατεστημένη.  
3. **Βασικές γνώσεις Java** – για την κατανόηση των αποσπασμάτων κώδικα.

### Απαιτούμενες βιβλιοθήκες, εκδόσεις και εξαρτήσεις

Προσθέστε την ακόλουθη διαμόρφωση Maven στο `pom.xml` σας (αμετάβλητη από το αρχικό tutorial):

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

### Βήματα απόκτησης άδειας

Το GroupDocs.Viewer προσφέρει δωρεάν δοκιμή, προσωρινές άδειες για δοκιμές ή επιλογές πλήρους αγοράς:

- **Δωρεάν δοκιμή** – Λήψη από τη [Σελίδα Κυκλοφορίας GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Προσωρινή άδεια** – Αίτηση στη [Σελίδα Προσωρινής Άδειας GroupDocs](https://purchase.groupdocs.com/temporary-license/).  
- **Αγορά** – Απόκτηση μόνιμης άδειας μέσω της [Σελίδας Αγοράς GroupDocs](https://purchase.groupdocs.com/buy).

## Ρύθμιση GroupDocs.Viewer για Java

Viewer είναι η κεντρική κλάση που φορτώνει ένα έγγραφο και παρέχει μεθόδους απόδοσης για όλες τις υποστηριζόμενες μορφές εξόδου.

### Εγκατάσταση με Maven
Το παραπάνω snippet Maven θα κατεβάσει όλα τα απαιτούμενα JAR αυτόματα. Απλώς εκτελέστε `mvn clean install` μετά την αποθήκευση του αρχείου.

### Αρχικοποίηση άδειας
`Viewer` είναι η κεντρική κλάση που φορτώνει ένα έγγραφο και παρέχει μεθόδους απόδοσης για όλες τις υποστηριζόμενες μορφές εξόδου. Αρχικοποιήστε την άδειά σας πριν από την απόδοση οποιουδήποτε εγγράφου:

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Οδηγός υλοποίησης

Παρακάτω θα βρείτε παραδείγματα βήμα‑βήμα για κάθε μορφή εξόδου. Τα αποσπάσματα κώδικα είναι ακριβώς όπως στο αρχικό tutorial· προσθέσαμε μόνο εξηγητικό κείμενο γύρω από αυτά.

### Πώς να μετατρέψετε cdr σε html με GroupDocs.Viewer

Φορτώστε ένα αρχείο CDR και καλέστε το API απόδοσης HTML – αυτό είναι ό,τι χρειάζεστε για να δημιουργήσετε markup έτοιμο για web. Η διαδικασία απαιτεί ρύθμιση διαδρομών αρχείων, δημιουργία ενός αντικειμένου `HtmlViewOptions` και κλήση του `viewer.view()`. Αυτό το μοτίβο δύο βημάτων λειτουργεί για οποιοδήποτε μέγεθος εγγράφου και διατηρεί την ακρίβεια των vector.

#### Απόδοση εγγράφου cdr σε HTML
**Επισκόπηση:** Μετατρέψτε τα αρχεία CDR σας σε HTML φιλικό στο web για εύκολη κοινή χρήση.

**Βήμα 1 – ρύθμιση διαδρομών αρχείων**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Βήμα 2 – αρχικοποίηση viewer και απόδοση**

Το `HtmlViewOptions` διαμορφώνει την απόδοση HTML, επιτρέποντας την ενσωμάτωση πόρων ή την αποθήκευσή τους ξεχωριστά. Ο παρακάτω κώδικας αποδίδει κάθε σελίδα σε ξεχωριστό αρχείο HTML ενώ ενσωματώνει τις εικόνες ως Base64 strings.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### Πώς να μετατρέψετε cdr σε jpg με GroupDocs.Viewer

Μπορείτε να παραγάγετε εικόνες JPEG υψηλής ποιότητας από μια πηγή CDR με μόλις δύο γραμμές κώδικα. Πρώτα, διαμορφώστε το `JpgViewOptions` με την επιθυμητή ποιότητα, έπειτα καλέστε το `viewer.view()`. Αυτή η προσέγγιση είναι ιδανική για μικρογραφίες, συνημμένα email ή οποιοδήποτε σενάριο που απαιτεί μια συμπαγή raster εικόνα.

#### Απόδοση εγγράφου cdr σε JPG
**Επισκόπηση:** Παραγάγετε εικόνες JPEG υψηλής ποιότητας από την πηγή CDR σας.

**Βήμα 1 – ρύθμιση διαδρομών αρχείων**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Βήμα 2 – αρχικοποίηση viewer και απόδοση**

Το `JpgViewOptions` ορίζει τις ρυθμίσεις απόδοσης JPEG, όπως η ποιότητα συμπίεσης και η ονομασία εξόδου. Το παρακάτω παράδειγμα αποθηκεύει κάθε σελίδα ως ξεχωριστό αρχείο JPEG.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### Πώς να μετατρέψετε cdr σε png με GroupDocs.Viewer

Η έξοδος PNG σας παρέχει raster εικόνες χωρίς απώλειες, ιδανικές για αρχειοθέτηση ή περαιτέρω επεξεργασία γραφικών. Χρησιμοποιήστε το `PngViewOptions` για να διατηρήσετε κάθε pixel άθικτο, έπειτα αποδώστε το έγγραφο σελίδα προς σελίδα.

#### Απόδοση εγγράφου cdr σε PNG
**Επισκόπηση:** Δημιουργήστε εικόνες PNG χωρίς απώλειες για αρχειοθέτηση ή σκοπούς σχεδίασης.

**Βήμα 1 – ρύθμιση διαδρομών αρχείων**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Βήμα 2 – αρχικοποίηση viewer και απόδοση**

Το `PngViewOptions` καθορίζει τις παραμέτρους απόδοσης PNG, συμπεριλαμβανομένης της υποστήριξης διαφανών φόντων. Ο κώδικας δημιουργεί αυτόματα ένα PNG ανά σελίδα.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### Πώς να μετατρέψετε cdr σε pdf με GroupDocs.Viewer

Η μετατροπή ενός αρχείου CDR σε PDF σας παρέχει ένα έγγραφο που διαβάζεται παντού και είναι έτοιμο για εκτύπωση. Το `PdfViewOptions` διαχειρίζεται εσωτερικά τη μετατροπή vector σε raster, διατηρώντας τη διάταξη και τις γραμματοσειρές χωρίς να απαιτείται Adobe Illustrator.

#### Απόδοση εγγράφου cdr σε PDF
**Επισκόπηση:** Μετατρέψτε τα αρχεία CDR σας σε PDF που διαβάζονται παντού.

**Βήμα 1 – ρύθμιση διαδρομών αρχείων**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Βήμα 2 – αρχικοποίηση viewer και απόδοση**

Το `PdfViewOptions` ελέγχει τη δημιουργία PDF, επιτρέποντας ενσωμάτωση γραμματοσειρών και προσαρμογή διάταξης σελίδας. Το snippet δημιουργεί ένα ενιαίο PDF που περιέχει όλες τις σελίδες.

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Πρακτικές εφαρμογές

- **Ιστοσελίδες:** Χρησιμοποιήστε τη μετατροπή HTML για ενσωμάτωση σχεδίων CDR απευθείας στον ιστότοπό σας.  
- **Γκαλερί εικόνων:** Αναπτύξτε εξόδους JPG/PNG για γκαλερί με γρήγορη φόρτωση ή καταλόγους προϊόντων.  
- **Κοινή χρήση εγγράφων:** Παρέχετε PDF για πελάτες που χρειάζονται εκτυπώσιμη, μόνο για ανάγνωση έκδοση.  
- **Αρχειοθέτηση:** Αποθηκεύστε πολλαπλές μορφές για να εγγυηθείτε τη μελλοντική προσβασιμότητα ανεξάρτητα από αλλαγές λογισμικού.  
- **Διασύνδεση πολλαπλών πλατφορμών:** Ενσωματώστε τα παραγόμενα αρχεία σε downstream υπηρεσίες όπως OCR, analytics ή συστήματα διαχείρισης ψηφιακών περιουσιακών στοιχείων.

## Σκέψεις απόδοσης

- **Αποδέσμευση παρουσιών Viewer** άμεσα (όπως φαίνεται με try‑with‑resources) για ελευθέρωση μνήμης.  
- **Μαζική επεξεργασία:** Κάντε βρόχο πάνω από μια συλλογή αρχείων CDR χρησιμοποιώντας την ίδια διαμόρφωση Viewer για μείωση του κόστους.  
- **Κατανομή πόρων:** Το GroupDocs.Viewer μπορεί να αποδώσει έγγραφα έως 500 σελίδες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, αλλά πολύπλοκα σχέδια μπορεί να ωφεληθούν από αυξημένο heap size. Παρακολουθείτε τη χρήση CPU και RAM κατά τις μεγάλες μετατροπές.

## Συνηθισμένα προβλήματα και συμβουλές αντιμετώπισης

- **Απουσία γραμματοσειρών:** Αν η έξοδος φαίνεται διαφορετική, βεβαιωθείτε ότι οι απαιτούμενες γραμματοσειρές είναι διαθέσιμες στον server ή ενσωματώστε τες μέσω `PdfViewOptions`.  
- **Μεγάλα αρχεία:** Για αρχεία CDR άνω των 200 MB, εξετάστε την επεξεργασία σελίδα‑προς‑σελίδα για αποφυγή `OutOfMemoryError`.  
- **Λανθασμένη ποιότητα εικόνας:** Ρυθμίστε την τιμή `setQuality` στο `JpgViewOptions` αν τα JPEG φαίνονται υπερβολικά συμπιεσμένα.  
- **Σφάλματα άδειας:** Επαληθεύστε ότι η διαδρομή του αρχείου άδειας είναι σωστή και ότι η έκδοση της άδειας ταιριάζει με την έκδοση της βιβλιοθήκης Viewer.

## Συμπέρασμα

Σας δείξαμε πώς να **convert cdr to html**, καθώς και σε JPG, PNG και PDF, χρησιμοποιώντας το GroupDocs.Viewer for Java. Ακολουθώντας τα σύντομα αποσπάσματα κώδικα και τις βέλτιστες πρακτικές, μπορείτε να ενσωματώσετε αυτές τις μετατροπές σε οποιαδήποτε ροή εργασίας Java, παρέχοντας ευέλικτες, υψηλής ποιότητας εξόδους στους χρήστες σας.

### Επόμενα βήματα
- Δοκιμάστε προχωρημένες επιλογές απόδοσης όπως προσαρμοσμένα μεγέθη σελίδας ή υδατογραφήματα.  
- Συνδυάστε τη γραμμή μετατροπής με ένα REST API για προσφορά μετασχηματισμού αρχείων κατά απαίτηση.  
- Ενταχθείτε στην κοινότητα και θέστε ερωτήσεις στο [Φόρουμ GroupDocs](https://forum.groupdocs.com/c/viewer).

## Συχνές ερωτήσεις

**Ε: Μπορώ να μετατρέψω αρχεία CDR με προστασία κωδικού;**  
Α: Ναι. Φορτώστε το αρχείο με μια παρουσία `Viewer` που δέχεται παράμετρο κωδικού (δείτε την τεκμηρίωση API).

**Ε: Υπάρχει όριο στον αριθμό των σελίδων που μπορούν να μετατραπούν ταυτόχρονα;**  
Α: Δεν υπάρχει σκληρό όριο, αλλά πολύ μεγάλα αρχεία μπορεί να απαιτούν περισσότερη μνήμη· εξετάστε την επεξεργασία σελίδα‑προς‑σελίδα.

**Ε: Περιλαμβάνει η έξοδος HTML ενσωματωμένες γραμματοσειρές;**  
Α: Όταν χρησιμοποιείτε `HtmlViewOptions.forEmbeddedResources`, οι γραμματοσειρές ενσωματώνονται ως Base64, εξασφαλίζοντας συνεπή απόδοση σε browsers.

**Ε: Πώς ελέγχω την ποιότητα JPEG;**  
Α: Το `JpgViewOptions` παρέχει τη μέθοδο `setQuality(int)` όπου μπορείτε να ορίσετε τιμή από 1‑100.

**Ε: Μπορώ να μετατρέψω αρχεία CDR σε διακομιστή Linux;**  
Α: Απόλυτα—το GroupDocs.Viewer είναι πλατφόρμα‑ανεξάρτητο εφόσον είναι εγκατεστημένο το JDK.

**Last Updated:** 2026-08-19  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## Σχετικά μαθήματα

- [Πώς να Μετατρέψετε Excel σε HTML, JPG, PNG και PDF Χρησιμοποιώντας το GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [Πώς να Μετατρέψετε CF2 σε PDF, HTML, JPG, PNG με GroupDocs.Viewer για Java](/viewer/java/rendering-basics/render-cf2-files-groupdocs-java/)
- [Πώς να μετατρέψετε pdf σε html και να βελτιστοποιήσετε την ποιότητα εικόνας σε Java με GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)