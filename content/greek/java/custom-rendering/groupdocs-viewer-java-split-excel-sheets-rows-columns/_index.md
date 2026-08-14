---
date: '2026-06-15'
description: Μάθετε πώς να μετατρέψετε Excel σε PDF Java και να διαχωρίσετε φύλλα
  Excel ανά σειρές και στήλες χρησιμοποιώντας το GroupDocs Viewer. Περιλαμβάνει εγκατάσταση,
  κώδικα και βέλτιστες πρακτικές.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Μετατροπή Excel σε PDF Java & Split Sheets ανά Σειρές & Στήλες
type: docs
url: /el/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Μετατροπή Excel σε PDF Java & Διαίρεση Φύλλων ανά Γραμμές & Στήλες (Java)

Τα μεγάλα βιβλία εργασίας Excel συχνά περιέχουν περισσότερα δεδομένα από ό,τι μπορούν να εμφανιστούν άνετα σε μία οθόνη ή σε μία εκτυπωμένη σελίδα. **convert excel to pdf java** είναι μια κοινή απαίτηση όταν χρειάζεστε μια στατική, διαμοιραζόμενη μορφή, ενώ **splitting Excel sheets by rows and columns** κάνει τα δεδομένα πιο εύκολα στην κατανόηση σε διαδικτυακές ή έντυπες διατάξεις. Σε αυτόν τον οδηγό θα περάσουμε από τις δύο εργασίες χρησιμοποιώντας το **GroupDocs Viewer for Java**, θα σας δείξουμε πώς να διαμορφώσετε την σελιδοποίηση και θα εξηγήσουμε συμβουλές βέλτιστων πρακτικών για απόδοση και αντιμετώπιση προβλημάτων.

![Διαίρεση Φύλλων Excel ανά Γραμμές και Στήλες με το GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Διαίρεση Φύλλων Excel ανά Γραμμές και Στήλες με το GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη χρησιμοποιείται;** GroupDocs Viewer for Java.  
- **Μπορώ να διαχωρίσω τόσο ανά γραμμές όσο και ανά στήλες;** Ναι – μπορείτε να ορίσετε rows‑per‑page και columns‑per‑page μαζί.  
- **Χρειάζομαι άδεια;** Μια δοκιμαστική ή προσωρινή άδεια λειτουργεί για ανάπτυξη· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποιοι μορφές εξόδου υποστηρίζονται;** Εμφανίζεται HTML (ενσωματωμένοι πόροι); το PDF μπορεί να δημιουργηθεί με τις ίδιες επιλογές.  
- **Απαιτείται το Maven;** Το Maven είναι η συνιστώμενη μέθοδος διαχείρισης εξαρτήσεων.  
- **Μπορώ επίσης να μετατρέψω το Excel σε PDF;** Απόλυτα – απλώς αλλάξτε το `HtmlViewOptions` σε `PdfViewOptions` και χρησιμοποιήστε ξανά τις ίδιες ρυθμίσεις σελιδοποίησης.

## Τι είναι το «How to Split Excel»;
Η διαίρεση ενός φύλλου Excel σημαίνει το διαχωρισμό ενός μοναδικού φύλλου εργασίας σε πολλαπλές σελίδες ή αρχεία βάσει σταθερού αριθμού γραμμών, στηλών ή και των δύο. Αυτή η τεχνική είναι χρήσιμη όταν χρειάζεται να δημιουργήσετε σελιδοποιημένες αναφορές, να ενσωματώσετε δεδομένα σε ιστοσελίδες ή να παράγετε εκτυπώσιμα τμήματα χωρίς να φορτώνετε ολόκληρο το βιβλίο εργασίας ταυτόχρονα.

## Γιατί να χρησιμοποιήσετε το GroupDocs Viewer for Java;
Το GroupDocs Viewer επεξεργάζεται τα υπολογιστικά φύλλα σε μία μόνο διέλευση και τα σελιδοποιεί αυτόματα, εξαλείφοντας τις χειροκίνητες υπολογιστικές εργασίες. **Η γρήγορη απόδοση επεξεργάζεται ένα βιβλίο εργασίας XLSX 250 σελίδων σε λιγότερο από 2 δευτερόλεπτα σε έναν τυπικό διακομιστή 2‑πυρήνων**, και **η βιβλιοθήκη υποστηρίζει πάνω από 50 μορφές εισόδου και εξόδου**, συμπεριλαμβανομένων των XLS, XLSX, CSV, PDF και HTML. Λειτουργεί σε οποιαδήποτε πλατφόρμα συμβατή με JVM—Windows, Linux, macOS, Docker containers ή cloud‑based serverless runtimes—ώστε μπορείτε να το ενσωματώσετε όπου βρίσκεται η Java εφαρμογή σας.

## Προαπαιτούμενα
- Εγκατεστημένο Java 17 ή νεότερο.  
- Ένα IDE όπως IntelliJ IDEA ή Eclipse.  
- Maven για διαχείριση εξαρτήσεων.  
- Βασικές γνώσεις Java και εξοικείωση με τη διαχείριση αρχείων Excel.

### Απαιτούμενες Βιβλιοθήκες, Εκδόσεις και Εξαρτήσεις
Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση viewer στο `pom.xml`:

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
Αποκτήστε μια δωρεάν δοκιμαστική, προσωρινή άδεια ή αγοράστε πλήρη άδεια από [GroupDocs](https://purchase.groupdocs.com/buy).

## Πώς να Μετατρέψετε το Excel σε PDF Java;

Η κλάση `Viewer` είναι το κύριο συστατικό του GroupDocs Viewer που φορτώνει ένα έγγραφο και παρέχει μεθόδους απόδοσης για διάφορες μορφές εξόδου. Το `SpreadsheetOptions` σας επιτρέπει να ελέγξετε τις ρυθμίσεις σελιδοποίησης όπως rows‑per‑page και columns‑per‑page για την απόδοση του υπολογιστικού φύλλου.

Φορτώστε το αρχείο Excel με `new Viewer("source.xlsx")`, διαμορφώστε το `SpreadsheetOptions` για σελιδοποίηση και καλέστε `viewer.view(pdfOptions, stream)` – αυτή η ενιαία κλήση μετατρέπει το βιβλίο εργασίας σε PDF τηρώντας τα όρια γραμμών/στηλών που ορίσατε. Η μετατροπή διατηρεί τύπους, εικόνες και στυλ κελιών, παρέχοντας μια πιστή αναπαραγωγή PDF έτοιμη για διανομή.

## Πώς να Διαχωρίσετε Φύλλα Excel ανά Γραμμές

Η διαίρεση ανά γραμμές δημιουργεί μια σειρά σελίδων HTML, η κάθε μία με έναν σταθερό αριθμό γραμμών (π.χ., 15). Αυτή η προσέγγιση είναι ιδανική για πίνακες ελέγχου που εμφανίζουν περιορισμένο αριθμό εγγραφών ανά προβολή. Ο viewer θα δημιουργήσει ξεχωριστά αρχεία HTML όπως `page_0.html`, `page_1.html`, κ.λπ., το καθένα περιέχοντας τον καθορισμένο αριθμό γραμμών. Αυτό καθιστά εύκολο το φόρτωμα μόνο του απαιτούμενου τμήματος σε μια διεπαφή web, μειώνοντας το εύρος ζώνης και τον χρόνο απόδοσης.

### Ορισμός Anchor
`Viewer` είναι η βασική κλάση του GroupDocs Viewer που φορτώνει ένα έγγραφο και οργανώνει την απόδοση στην επιλεγμένη μορφή εξόδου.

### Υλοποίηση Βήμα‑Βήμα

#### Βήμα 1: Ρύθμιση Διαδρομών και Αρχικοποίηση του Viewer
Πρώτα, ορίστε πού θα αποθηκευτούν οι διαχωρισμένες σελίδες και δημιουργήστε μια παρουσία `Viewer` για το πηγαίο βιβλίο εργασίας.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Βήμα 2: Διαμόρφωση Γραμμών ανά Σελίδα
Πείτε στον viewer πόσες γραμμές πρέπει να περιέχει κάθε σελίδα.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Βήμα 3: Απόδοση του Εγγράφου
Τέλος, αποδώστε το βιβλίο εργασίας χρησιμοποιώντας τις ρυθμίσεις που ορίσατε.

```java
viewer.view(viewOptions);
```

## Πώς να Διαχωρίσετε Φύλλα Excel ανά Γραμμές και Στήλες

Μερικές φορές μια ενιαία σελίδα πρέπει να εμφανίζει ένα πλέγμα γραμμών **και** στηλών (π.χ., 15 γραμμές × 7 στήλες). Αυτό σας δίνει πλήρη έλεγχο της διάταξης κάθε σελίδας HTML. Οι παραγόμενες σελίδες εμφανίζουν ένα ορθογώνιο μπλοκ κελιών, για παράδειγμα γραμμές 1‑15 και στήλες A‑G στην πρώτη σελίδα, γραμμές 16‑30 και στήλες H‑N στην επόμενη. Η σελιδοποίηση στυλ πλέγματος είναι χρήσιμη για τη δημιουργία εκτυπώσιμων αναφορών που ταιριάζουν σε τυπικά μεγέθη χαρτιού.

### Ορισμός Anchor
`SpreadsheetOptions` διαμορφώνει πόσες γραμμές και στήλες εμφανίζονται σε κάθε παραγόμενη σελίδα.

### Υλοποίηση Βήμα‑Βήμα

#### Βήμα 1: Ρύθμιση Διαδρομών και Αρχικοποίηση του Viewer
Η ρύθμιση αντικατοπτρίζει το παράδειγμα μόνο με γραμμές, αλλά το όνομα του αρχείου αλλάζει.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Βήμα 2: Διαμόρφωση Γραμμών και Στηλών ανά Σελίδα
Καθορίστε και τις δύο διαστάσεις για να δημιουργήσετε διαίρεση στυλ πλέγματος.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Βήμα 3: Απόδοση του Εγγράφου
Αποδώστε χρησιμοποιώντας την ίδια κλήση `view`.

```java
viewer.view(options);
```

## Πρακτικές Εφαρμογές
- **Δημιουργία αναφοράς Excel Java**: Μετατρέψτε μεγάλα χρηματοοικονομικά μοντέλα σε σειρά σελιδοποιημένων αναφορών HTML.  
- **GroupDocs Viewer Excel**: Ενσωματώστε τις διαχωρισμένες σελίδες απευθείας σε μια διαδικτυακή πύλη για διαδραστική εξερεύνηση δεδομένων.  
- **Render Excel HTML Java**: Σερβίρετε τις παραγόμενες σελίδες HTML μέσω servlet ή Spring controller για γρήγορη απόδοση στην πλευρά του πελάτη.  

## Σκέψεις για την Απόδοση
- **Χρήση μνήμης** – Τα μεγάλα βιβλία εργασίας μπορούν να καταναλώσουν σημαντικό heap· εξετάστε την αύξηση της ρύθμισης JVM `-Xmx`.  
- **Μέγεθος τμήματος** – Επιλέξτε αριθμούς γραμμών/στηλών που ισορροπούν το μέγεθος της σελίδας και την ταχύτητα απόδοσης.  
- **Ενημερώσεις έκδοσης** – Διατηρήστε το GroupDocs Viewer ενημερωμένο για να επωφεληθείτε από βελτιώσεις στην απόδοση· η τελευταία έκδοση 25.2 βελτιώνει την ταχύτητα απόδοσης έως και 30 % σε σύγκριση με την 24.x.

## Συχνά Προβλήματα & Επίλυση
| Σύμπτωμα | Πιθανή Αιτία | Διόρθωση |
|---------|--------------|----------|
| `OutOfMemoryError` | Απόδοση πολύ μεγάλου φύλλου με πάρα πολλές γραμμές ανά σελίδα | Μειώστε το `countRowsPerPage` ή αυξήστε το heap της JVM |
| Κενά αρχεία εξόδου | Λανθασμένη διαδρομή αρχείου ή έλλειψη δικαιωμάτων εγγραφής | Επαληθεύστε ότι το `outputDirectory` υπάρχει και είναι εγγράψιμο |
| Οι πόροι HTML δεν φορτώνουν | Χρήση `forEmbeddedResources` ενώ τα αρχεία σερβίρονται από διαφορετικό base URL | Σερβίρετε ολόκληρο το φάκελο εξόδου ή αλλάξτε σε `forExternalResources` |

## Συχνές Ερωτήσεις

**Ε: Μπορώ να δημιουργήσω PDF αντί για HTML;**  
Α: Ναι. Αντικαταστήστε το `HtmlViewOptions` με `PdfViewOptions` και διατηρήστε την ίδια διαμόρφωση `SpreadsheetOptions`.

**Ε: Είναι δυνατόν να διαχωριστεί βάσει του περιεχομένου των κελιών αντί για σταθερές γραμμές/στήλες;**  
Α: Η διαίρεση βάσει περιεχομένου δεν είναι ενσωματωμένη στο GroupDocs Viewer, αλλά μπορείτε να προεπεξεργαστείτε το βιβλίο εργασίας με Apache POI για να δημιουργήσετε ξεχωριστά φύλλα πριν από την απόδοση.

**Ε: Υποστηρίζει το GroupDocs Viewer παλαιότερες μορφές Excel (XLS);**  
Α: Απόλυτα. Ο viewer χειρίζεται XLS, XLSX, CSV και άλλες μορφές υπολογιστικών φύλλων.

**Ε: Πώς ενσωματώνω το παραγόμενο HTML σε μια προβολή Spring MVC;**  
Α: Σερβίρετε το φάκελο εξόδου ως στατικό πόρο και αναφερθείτε στα παραγόμενα `page_0.html`, `page_1.html`, κ.λπ., από τα πρότυπα Thymeleaf ή JSP.

**Ε: Τι άδεια χρειάζομαι για εμπορική ανάπτυξη;**  
Α: Απαιτείται πλήρης άδεια παραγωγής από το GroupDocs· οι δοκιμαστικές άδειες προορίζονται μόνο για αξιολόγηση.

## Πόροι
- **Τεκμηρίωση**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Αναφορά API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Λήψη**: [GroupDocs Viewer Java Releases](https://releases.groupdocs.com/viewer/java/)
- **Αγορά Άδειας GroupDocs**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Δωρεάν Δοκιμή**: [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Προσωρινή Άδεια**: [Get Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Φόρουμ Υποστήριξης**: [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία Ενημέρωση:** 2026-06-15  
**Δοκιμάστηκε Με:** GroupDocs Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs  

## Σχετικά Μαθήματα

- [Απόδοση Κρυφών Γραμμών & Στηλών σε Java Spreadsheets Χρησιμοποιώντας το GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Παράλειψη Απόδοσης Κενών Γραμμών σε Java Χρησιμοποιώντας το GroupDocs.Viewer: Οδηγός Απόδοσης](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Πλήρης Οδηγός: Μετατροπή Excel 2003 XML σε HTML/JPG/PNG/PDF με το GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)