---
date: '2026-09-30'
description: Μάθετε πώς να προβάλετε αρχείο ms project και να δημιουργήσετε αναφορά
  έργου σε Java χρησιμοποιώντας το GroupDocs.Viewer. Εξάγετε δεδομένα, διαχειριστείτε
  κωδικούς πρόσβασης και δημιουργήστε πίνακες ελέγχου.
keywords:
- view ms project file
- how to read ms project
- extract ms project data
lastmod: '2026-09-30'
og_description: Μάθετε πώς να προβάλετε αρχείο ms project και να δημιουργήσετε αναφορά
  έργου σε Java χρησιμοποιώντας το GroupDocs.Viewer. Εξάγετε δεδομένα, διαχειριστείτε
  κωδικούς πρόσβασης και δημιουργήστε πίνακες ελέγχου.
og_image_alt: 'Java guide: view ms project file and generate report with GroupDocs.Viewer'
og_title: Πώς να προβάλετε αρχείο ms project και να δημιουργήσετε αναφορά σε Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to view ms project file and generate a project report in
    Java using GroupDocs.Viewer. Extract data, handle passwords, and build dashboards.
  headline: How to view ms project file and generate report in Java
  type: TechArticle
- description: Learn how to view ms project file and generate a project report in
    Java using GroupDocs.Viewer. Extract data, handle passwords, and build dashboards.
  name: How to view ms project file and generate report in Java
  steps:
  - name: define document path
    text: 'Specify where your MS Project file lives:'
  - name: initialize view‑info options
    text: 'Configure the options to request HTML‑style view information:'
  - name: retrieve and output project details
    text: 'Create a `Viewer`, fetch the `ProjectManagementViewInfo`, and print the
      key fields that form a typical project report: **Explanation** - `getViewInfo(viewInfoOptions)`
      pulls metadata based on the supplied options. - The returned `info` object contains
      the file type, page count, and crucial dates—exa'
  - name: configure load options
    text: '`LoadOptions` lets you define additional parameters such as passwords,
      ensuring secure access to protected files.'
  - name: initialize viewer with load options
    text: 'Pass the `loadOptions` when constructing the `Viewer`: **Explanation**
      `LoadOptions` lets you define additional parameters such as passwords, ensuring
      secure access to protected files.'
  type: HowTo
- questions:
  - answer: It’s a Java library that renders and extracts information from over 100
      file formats, including MS Project documents.
    question: What is GroupDocs.Viewer Java?
  - answer: Use the `LoadOptions` class to set the password before creating the `Viewer`
      instance.
    question: How do I handle password‑protected MS Project files?
  - answer: Yes, once you obtain a proper license from GroupDocs.
    question: Can I use GroupDocs.Viewer in commercial projects?
  - answer: Incorrect file paths, using an outdated library version, or attempting
      to read unsupported MS Project features.
    question: What are common pitfalls when retrieving view info?
  - answer: Implement caching, reuse `Viewer` instances where safe, and tune JVM memory
      settings.
    question: How can I improve performance with large MS Project files?
  type: FAQPage
tags:
- ms project
- groupdocs.viewer
- java reporting
title: Πώς να προβάλετε αρχείο ms project και να δημιουργήσετε αναφορά σε Java
type: docs
url: /el/java/file-formats-support/mastering-ms-project-viewing-groupdocs-java/
weight: 1
---

# Πώς να προβάλετε αρχείο ms project και να δημιουργήσετε αναφορά σε Java

Η δημιουργία αναφοράς έργου από ένα αρχείο MS Project είναι συχνή απαίτηση για διαχειριστές έργων και προγραμματιστές. Με το **GroupDocs.Viewer for Java** μπορείτε να **προβάλετε το περιεχόμενο του αρχείου ms project**, να εξάγετε βασικά μεταδεδομένα και να δημιουργήσετε περιεκτικούς πίνακες ελέγχου χωρίς να εγκαταστήσετε το Microsoft Project. Αυτός ο οδηγός σας καθοδηγεί μέσω της ρύθμισης του περιβάλλοντος, παραδειγμάτων κώδικα και πραγματικών σεναρίων, ώστε να αρχίσετε να παρέχετε σήμερα δεδομενο‑οδηγούμενες πληροφορίες έργου.

![Προβολή MS Project με το GroupDocs.Viewer για Java](/viewer/file‑formats-support/ms-project-viewing.png)

Με το τέλος αυτού του σεμιναρίου θα μπορείτε να:

- Να ρυθμίσετε το GroupDocs.Viewer για Java σε ένα έργο Maven.  
- Να ανακτήσετε πληροφορίες προβολής που αποτελούν τη βάση μιας αναφοράς έργου.  
- Να διαμορφώσετε επιλογές φόρτωσης για αρχεία προστατευμένα με κωδικό.  

Ας βουτήξουμε και να μεταμορφώσουμε τον τρόπο με τον οποίο χειρίζεστε τα δεδομένα MS Project!

## Γρήγορες απαντήσεις
- **Τι σημαίνει «δημιουργία αναφοράς έργου» εδώ;** Εξαγωγή βασικών μεταδεδομένων του έργου (ημερομηνίες, αριθμός εργασιών κ.λπ.) για τροφοδοσία εργαλείων αναφοράς.  
- **Ποια βιβλιοθήκη απαιτείται;** GroupDocs.Viewer for Java (v25.2 ή νεότερη).  
- **Μπορώ να προβάλλω ένα αρχείο MS Project χωρίς άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση, αλλά απαιτείται άδεια για παραγωγή.  
- **Πώς να διαχειριστώ αρχεία προστατευμένα με κωδικό;** Χρησιμοποιήστε το `LoadOptions` για να παρέχετε τον κωδικό κατά τη δημιουργία του `Viewer`.  
- **Ποια έκδοση Java υποστηρίζεται;** JDK 8 ή νεότερη.

## Τι σημαίνει «δημιουργία αναφοράς έργου» με το GroupDocs.Viewer;
Η δημιουργία αναφοράς έργου σημαίνει εξαγωγή δομημένων πληροφοριών — όπως ημερομηνίες έναρξης/λήξης, αριθμός εργασιών και κατανομές πόρων — από ένα έγγραφο MS Project. Το GroupDocs.Viewer παρέχει ένα αντικείμενο `ProjectManagementViewInfo` που περιέχει όλες αυτές τις λεπτομέρειες, καθιστώντας εύκολη την ενσωμάτωσή τους σε πίνακες ελέγχου αναφοράς ή την εξαγωγή σε άλλες μορφές.

## Γιατί να προβάλετε λεπτομέρειες αρχείου ms project με το GroupDocs.Viewer;
Η προβολή δεδομένων αρχείου ms project με το GroupDocs.Viewer είναι γρήγορη, ασφαλής και ανεξάρτητη από πλατφόρμα. Η βιβλιοθήκη υποστηρίζει **πάνω από 100 μορφές αρχείων**, επεξεργάζεται αρχεία έως **500 MB** χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη, και λειτουργεί σε οποιοδήποτε περιβάλλον συμβατό με Java — από τοπικούς διακομιστές έως λειτουργίες cloud.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε:

1. **Βιβλιοθήκες και εξαρτήσεις**  
   - Βιβλιοθήκη GroupDocs.Viewer Java (έκδοση 25.2 ή νεότερη).  
   - Εγκατεστημένο Maven για διαχείριση εξαρτήσεων.  

2. **Ρύθμιση περιβάλλοντος**  
   - Ένα IDE όπως IntelliJ IDEA ή Eclipse.  
   - JDK 8 ή νεότερο.  

3. **Προαπαιτούμενες γνώσεις**  
   - Βασικές γνώσεις Java και Maven.  
   - Εξοικείωση με μορφές αρχείων MS Project (βοηθητικό αλλά όχι απαραίτητο).  

## Ρύθμιση του GroupDocs.Viewer για Java

### Εγκατάσταση μέσω Maven

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

### Απόκτηση άδειας

Για να ξεκλειδώσετε πλήρη λειτουργικότητα, εξετάστε μία από τις παρακάτω επιλογές αδειοδότησης:

- **Δωρεάν δοκιμή** — Δοκιμάστε όλες τις λειτουργίες χωρίς πιστωτική κάρτα.  
- **Προσωρινή άδεια** — Επέκταση πρόσβασης για περιόδους αξιολόγησης.  
- **Πλήρης άδεια** — Χρήση έτοιμη για παραγωγή με απεριόριστη υποστήριξη.  

Για οδηγίες βήμα‑βήμα σχετικά με την αδειοδότηση, επισκεφθείτε τη [GroupDocs purchase page](https://purchase.groupdocs.com/buy).

### Βασική αρχικοποίηση

Η κλάση `Viewer` είναι το κύριο συστατικό που φορτώνει ένα έγγραφο και παρέχει πληροφορίες προβολής. Υλοποιεί το `AutoCloseable`, επομένως θα πρέπει να τη χρησιμοποιείτε μέσα σε ένα μπλοκ try‑with‑resources για να εξασφαλίσετε σωστό καθαρισμό.

## Οδηγός υλοποίησης

### Ανάκτηση πληροφοριών προβολής για έγγραφο MS Project

Αυτή η λειτουργία εξάγει τα βασικά δεδομένα που χρειάζεστε για το περιεχόμενο **δημιουργίας αναφοράς έργου**.

#### Βήμα 1: ορισμός διαδρομής εγγράφου

Καθορίστε πού βρίσκεται το αρχείο MS Project σας:

```java
String documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP";
```

#### Βήμα 2: αρχικοποίηση επιλογών προβολής‑πληροφοριών

Διαμορφώστε τις επιλογές για να ζητήσετε πληροφορίες προβολής σε μορφή HTML:

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
```

#### Βήμα 3: ανάκτηση και έξοδος λεπτομερειών έργου

Δημιουργήστε ένα `Viewer`, ανακτήστε το `ProjectManagementViewInfo` και εκτυπώστε τα βασικά πεδία που σχηματίζουν μια τυπική αναφορά έργου:

```java
try (Viewer viewer = new Viewer(documentPath)) {
    ProjectManagementViewInfo info = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);

    System.out.println("Document type: " + info.getFileType());
    System.out.println("Pages count: " + info.getPages().size());
    System.out.println("Project start date: " + info.getStartDate());
    System.out.println("Project end date: " + info.getEndDate());
}
```

**Επεξήγηση**  
- Το `getViewInfo(viewInfoOptions)` αντλεί μεταδεδομένα βάσει των παρεχόμενων επιλογών.  
- Το επιστρεφόμενο αντικείμενο `info` περιέχει τον τύπο αρχείου, τον αριθμό σελίδων και κρίσιμες ημερομηνίες — ακριβώς τα στοιχεία που χρειάζεστε για δεδομένα **δημιουργίας αναφοράς έργου**.

### Ρύθμιση διαμόρφωσης GroupDocs.Viewer

Εάν τα αρχεία MS Project σας είναι προστατευμένα με κωδικό, θα χρειαστεί να παρέχετε τον κωδικό μέσω των επιλογών φόρτωσης.

#### Βήμα 1: διαμόρφωση επιλογών φόρτωσης

`LoadOptions` σας επιτρέπει να ορίσετε πρόσθετες παραμέτρους όπως κωδικούς πρόσβασης, εξασφαλίζοντας ασφαλή πρόσβαση σε προστατευμένα αρχεία.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setPassword("your_password_if_needed");
```

#### Βήμα 2: αρχικοποίηση viewer με επιλογές φόρτωσης

Περάστε το `loadOptions` κατά την κατασκευή του `Viewer`:

```java
try (Viewer viewer = new Viewer(documentPath, loadOptions)) {
    // Viewer is now ready for use with the specified document and options.
}
```

**Επεξήγηση**  
`LoadOptions` σας επιτρέπει να ορίσετε πρόσθετες παραμέτρους όπως κωδικούς πρόσβασης, εξασφαλίζοντας ασφαλή πρόσβαση σε προστατευμένα αρχεία.

## Πρακτικές εφαρμογές

1. **Πίνακες ελέγχου διαχείρισης έργου** — Τροφοδοτήστε τις εξαγόμενες ημερομηνίες και αριθμούς εργασιών σε πίνακες ελέγχου σε πραγματικό χρόνο για τα ενδιαφερόμενα μέρη.  
2. **Αυτοματοποιημένη αναφορά** — Επεξεργαστείτε πολλαπλά αρχεία `.mpp`, δημιουργήστε συνοπτικές αναφορές και στείλτε τις αυτόματα μέσω email.  
3. **Ενσωμάτωση CRM** — Συνδυάστε χρονοδιαγράμματα έργου με δεδομένα πελατών για βελτίωση προβλέψεων παράδοσης.

## Παράγοντες απόδοσης

- **Διαχείριση μνήμης** — Χρησιμοποιήστε try‑with‑resources (όπως φαίνεται) για να εγγυηθείτε ότι το `Viewer` κλείνει άμεσα.  
- **Caching** — Αποθηκεύστε συχνά προσπελάσιμες πληροφορίες προβολής σε cache για να αποφύγετε επαναλαμβανόμενες αναγνώσεις αρχείων.  
- **Παρακολούθηση** — Παρακολουθήστε τη χρήση μνήμης JVM κατά την επεξεργασία μεγάλων έργων και προσαρμόστε το μέγεθος heap ανάλογα.

## Κοινά προβλήματα και λύσεις

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| `File not found` error | Λανθασμένο `documentPath` | Επαληθεύστε τη απόλυτη ή σχετική διαδρομή και βεβαιωθείτε ότι το αρχείο υπάρχει. |
| No data returned for dates | Μη υποστηριζόμενη έκδοση MS Project | Αναβαθμίστε στην πιο πρόσφατη έκδοση του GroupDocs.Viewer ή μετατρέψτε το αρχείο σε υποστηριζόμενη μορφή. |
| `OutOfMemoryError` on large files | Ανεπαρκής heap JVM | Αυξήστε τη σημαία `-Xmx` ή επεξεργαστείτε το αρχείο σε τμήματα χρησιμοποιώντας επιλογές σελιδοποίησης. |

## Συχνές ερωτήσεις

**Q: Τι είναι το GroupDocs.Viewer Java;**  
A: Είναι μια βιβλιοθήκη Java που αποδίδει και εξάγει πληροφορίες από πάνω από 100 μορφές αρχείων, συμπεριλαμβανομένων των εγγράφων MS Project.

**Q: Πώς να διαχειριστώ αρχεία MS Project προστατευμένα με κωδικό;**  
A: Χρησιμοποιήστε την κλάση `LoadOptions` για να ορίσετε τον κωδικό πριν δημιουργήσετε το στιγμιότυπο `Viewer`.

**Q: Μπορώ να χρησιμοποιήσω το GroupDocs.Viewer σε εμπορικά έργα;**  
A: Ναι, αφού αποκτήσετε την κατάλληλη άδεια από το GroupDocs.

**Q: Ποια είναι τα κοινά εμπόδια κατά την ανάκτηση πληροφοριών προβολής;**  
A: Λανθασμένες διαδρομές αρχείων, χρήση παλιάς έκδοσης βιβλιοθήκης ή προσπάθεια ανάγνωσης μη υποστηριζόμενων λειτουργιών MS Project.

**Q: Πώς μπορώ να βελτιώσω την απόδοση με μεγάλα αρχεία MS Project;**  
A: Εφαρμόστε caching, επαναχρησιμοποιήστε στιγμιότυπα `Viewer` όπου είναι ασφαλές, και ρυθμίστε τις ρυθμίσεις μνήμης JVM.

## Σχετικοί πόροι
- [Τεκμηρίωση GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)
- [Αναφορά API](https://reference.groupdocs.com/viewer/java/)
- [Λήψη GroupDocs.Viewer για Java](https://releases.groupdocs.com/viewer/java/)
- [Αγορά Άδειας](https://purchase.groupdocs.com/buy)
- [Δωρεάν Έκδοση Δοκιμής](https://releases.groupdocs.com/viewer/java/)
- [Αίτηση για Προσωρινή Άδεια](https://purchase.groupdocs.com/temporary-license/)
- [Φόρουμ Υποστήριξης GroupDocs](https://forum.groupdocs.com/c/viewer/9)

**Τελευταία Ενημέρωση:** 2026-09-30  
**Δοκιμή Με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs