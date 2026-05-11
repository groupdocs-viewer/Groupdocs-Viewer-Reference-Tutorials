---
date: '2026-02-15'
description: Μάθετε πώς να μετατρέπετε αρχεία pst σε html και άλλες μορφές όπως JPG,
  PNG, PDF χρησιμοποιώντας το GroupDocs.Viewer για Java. Αυτός ο οδηγός καλύπτει όλα
  τα βήματα και τις απαιτούμενες ρυθμίσεις.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Μετατροπή PST σε HTML, JPG, PNG, PDF χρησιμοποιώντας το GroupDocs.Viewer για
  Java
type: docs
url: /el/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

 Q: "How do I **convert pst to pdf** with the same code base?" The bold phrase is technical term; keep unchanged. So keep same.

Similarly other bold phrases.

Now produce final markdown.

Let's craft.

# Μετατροπή PST σε HTML, JPG, PNG, PDF χρησιμοποιώντας το GroupDocs.Viewer για Java

Αναζητάτε να **μετατρέψετε pst σε html** ή σε άλλες μορφές όπως JPG, PNG ή PDF; Με τη δυνατή βιβλιοθήκη GroupDocs.Viewer για Java, αυτή η εργασία είναι απλή και αποδοτική. Σε αυτό το tutorial θα μάθετε πώς να αποδίδετε αρχεία Outlook PST/OST σε φιλικά προς το web HTML, αρχεία εικόνας ή ένα ενιαίο PDF, κάνοντας τα αρχεία email σας εύκολα στην κοινή χρήση και την αρχειοθέτηση.

![Μετατροπή PST/OST σε HTML, JPG, PNG, PDF με το GroupDocs.Viewer για Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Τι θα μάθετε**
- Πώς να ρυθμίσετε το GroupDocs.Viewer για Java σε ένα έργο Maven.  
- Οδηγίες βήμα‑βήμα για **java convert pst** αρχεία σε HTML, JPG, PNG και PDF.  
- Συμβουλές διαμόρφωσης για βέλτιστη απόδοση και κοινά προβλήματα.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή PST;** GroupDocs.Viewer για Java.  
- **Μπορώ να μετατρέψω PST σε PDF απευθείας;** Ναι, χρησιμοποιώντας `PdfViewOptions`.  
- **Απαιτείται άδεια για παραγωγή;** Απαιτείται έγκυρη άδεια GroupDocs.  
- **Ποια έκδοση Java υποστηρίζεται;** JDK 8 ή νεότερη.  
- **Πρέπει να εξάγω τα συνημμένα χειροκίνητα;** Όχι, ο viewer τα αποδίδει αυτόματα.

## Πώς να μετατρέψετε pst σε html χρησιμοποιώντας το GroupDocs.Viewer για Java
Παρακάτω θα βρείτε μια συνοπτική επισκόπηση της διαδικασίας μετατροπής πριν βυθιστείτε στα λεπτομερή παραδείγματα κώδικα.

### Γιατί να επιλέξετε το GroupDocs.Viewer;
- **High fidelity** rendering of email bodies, attachments, and formatting.  
- **Multiple output formats** (HTML, JPG, PNG, PDF) from a single API.  
- **No external dependencies** – everything runs inside your Java application.

## Προαπαιτούμενα

- **GroupDocs.Viewer για Java** – έκδοση 25.2 ή νεότερη.  
- **Java Development Kit (JDK)** – 8 ή νεότερη.  
- Maven για διαχείριση εξαρτήσεων.  
- Βασικές γνώσεις Java και εξοικείωση με Maven.

## Ρύθμιση του GroupDocs.Viewer για Java

Προσθέστε το αποθετήριο GroupDocs και την εξάρτηση στο `pom.xml`:

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
- **Free trial** – explore all features without cost.  
- **Temporary license** – extend evaluation time if needed.  
- **Full license** – required for production deployments.

### Βασική Αρχικοποίηση

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Οδηγός Υλοποίησης

Οι παρακάτω ενότητες σας καθοδηγούν στη μετατροπή αρχείων PST/OST σε κάθε υποστηριζόμενη μορφή.

### Απόδοση εγγράφων PST/OST σε HTML

#### Βήμα 1: Ρύθμιση καταλόγου εξόδου

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Βήμα 2: Διαμόρφωση επιλογών φόρτωσης

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Βήμα 3: Αρχικοποίηση Viewer και απόδοση HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Απόδοση εγγράφων PST/OST σε JPG

#### Βήμα 1: Ρύθμιση καταλόγου εξόδου

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Βήμα 2: Διαμόρφωση επιλογών φόρτωσης

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Βήμα 3: Αρχικοποίηση Viewer και απόδοση JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Απόδοση εγγράφων PST/OST σε PNG

#### Βήμα 1: Ρύθμιση καταλόγου εξόδου

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Βήμα 2: Διαμόρφωση επιλογών φόρτωσης

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Βήμα 3: Αρχικοποίηση Viewer και απόδοση PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Απόδοση εγγράφων PST/OST σε PDF

#### Βήμα 1: Ρύθμιση καταλόγου εξόδου

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Βήμα 2: Διαμόρφωση επιλογών φόρτωσης

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Βήμα 3: Αρχικοποίηση Viewer και απόδοση PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Πρακτικές Εφαρμογές

- **Email Archiving:** Μετατρέψτε μεγάλα αρχεία PST σε αναζητήσιμα HTML ή PDF για συμμόρφωση.  
- **Document Management Systems:** Αποθηκεύστε τα μετατρεπόμενα αρχεία σε συστήματα που δέχονται μόνο PDF, PNG ή JPG.  
- **Collaboration Platforms:** Μοιραστείτε μετατρεπόμενα email ως εικόνες στο Slack ή Teams.  
- **Legal Review:** Παρέχετε στα δικαστήρια εκδόσεις PDF αποδεικτικών email.  
- **Backup Strategies:** Διατηρήστε ελαφριές στιγμιότυπες PNG ή JPG κρίσιμων μηνυμάτων.

## Σκέψεις για την Απόδοση

- **Resource Management:** Επαναχρησιμοποιήστε στιγμιότυπα `Viewer` όταν επεξεργάζεστε πολλαπλά αρχεία για μείωση του φόρτου.  
- **Memory Tuning:** Προσαρμόστε το `loadOptions.setResourceLoadingTimeout` ανάλογα με τις δυνατότητες του διακομιστή.  
- **Asynchronous Processing:** Μεταφέρετε τη μετατροπή σε background threads για πιο ανταποκρινόμενα UI.  

## Συχνές Ερωτήσεις

**Q: Πώς μπορώ να **convert pst to pdf** με την ίδια βάση κώδικα;**  
A: Χρησιμοποιήστε το `PdfViewOptions` όπως φαίνεται στην ενότητα απόδοσης PDF· το υπόλοιπο του κώδικα παραμένει ίδιο.

**Q: Μπορεί το GroupDocs.Viewer να διαχειριστεί κρυπτογραφημένα αρχεία PST;**  
A: Ναι, παρέχετε τον κωδικό μέσω `LoadOptions.setPassword("yourPassword")` πριν από την απόδοση.

**Q: Ποια είναι η διαφορά μεταξύ **java convert pst** σε PNG vs JPG;**  
A: Το PNG διατηρεί απώλεια‑απώλειας ποιότητα, ιδανικό για στιγμιότυπα οθόνης, ενώ το JPG προσφέρει μικρότερα μεγέθη αρχείων για προεπισκοπήσεις email.

**Q: Υπάρχει τρόπος **how to convert pst** αρχείων μαζικά;**  
A: Τυλίξτε τη λογική απόδοσης σε βρόχο που διατρέχει έναν φάκελο με αρχεία PST· επαναχρησιμοποιήστε την ίδια διαμόρφωση `Viewer` για κάθε αρχείο.

## Συμπέρασμα

Τώρα έχετε έναν πλήρη, έτοιμο για παραγωγή οδηγό για **convert pst to html**, JPG, PNG και PDF χρησιμοποιώντας το GroupDocs.Viewer για Java. Ακολουθώντας τα παραπάνω βήματα μπορείτε να ενσωματώσετε τη μετατροπή email σε οποιαδήποτε ροή εργασίας βασισμένη σε Java, να βελτιώσετε την προσβασιμότητα και να καλύψετε απαιτήσεις συμμόρφωσης.

---

**Τελευταία ενημέρωση:** 2026-02-15  
**Δοκιμασμένο με:** GroupDocs.Viewer για Java 25.2  
**Συγγραφέας:** GroupDocs