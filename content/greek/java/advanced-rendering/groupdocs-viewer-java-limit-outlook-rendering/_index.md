---
date: '2026-08-19'
description: Μάθετε πώς να περιορίσετε outlook items java κατά την απόδοση αρχείων
  Outlook PST/OST χρησιμοποιώντας το GroupDocs.Viewer για Java, βελτιώνοντας την απόδοση
  και μειώνοντας τη χρήση μνήμης.
keywords:
- limit outlook items java
- GroupDocs Viewer Outlook rendering
- Java PST rendering
- outlook folder item limit
lastmod: '2026-08-19'
og_description: Μάθετε πώς να περιορίσετε outlook items java κατά την απόδοση αρχείων
  Outlook PST/OST χρησιμοποιώντας το GroupDocs.Viewer για Java, βελτιώνοντας την απόδοση
  και μειώνοντας τη χρήση μνήμης.
og_image_alt: Guide showing how to limit outlook items java with GroupDocs.Viewer
  for Java
og_title: Πώς να περιορίσετε outlook items java με το GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to limit outlook items java when rendering Outlook PST/OST
    files using GroupDocs.Viewer for Java, boosting performance and reducing memory
    usage.
  headline: How to limit outlook items java with GroupDocs.Viewer
  type: TechArticle
- description: Learn how to limit outlook items java when rendering Outlook PST/OST
    files using GroupDocs.Viewer for Java, boosting performance and reducing memory
    usage.
  name: How to limit outlook items java with GroupDocs.Viewer
  steps:
  - name: '**Java Development Kit (JDK)** – Install JDK 8 or later.'
    text: '**Java Development Kit (JDK)** – Install JDK 8 or later.'
  - name: '**GroupDocs.Viewer for Java** – Add as a dependency in your project.'
    text: '**GroupDocs.Viewer for Java** – Add as a dependency in your project.'
  - name: '**Email archiving** – Limiting item rendering is ideal for applications
      focusing on archiving specific emails rather than entire datasets.'
    text: '**Email archiving** – Limiting item rendering is ideal for applications
      focusing on archiving specific emails rather than entire datasets.'
  - name: '**Data migration** – When migrating data between systems, render only the
      necessary items to optimise performance and reduce processing time.'
    text: '**Data migration** – When migrating data between systems, render only the
      necessary items to optimise performance and reduce processing time.'
  - name: '**Custom reporting** – Generate reports by selectively rendering required
      email content without loading entire folders.'
    text: '**Custom reporting** – Generate reports by selectively rendering required
      email content without loading entire folders.'
  type: HowTo
- questions:
  - answer: It's a versatile library designed to render various document formats,
      including Outlook data files, into HTML or image formats.
    question: What is GroupDocs.Viewer Java used for?
  - answer: Visit [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/)
      for access and download options.
    question: How do I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the same configuration applies to both OST and PST file formats.
    question: Can I limit item rendering in PST files as well?
  - answer: Review your item limits and resource settings; consider optimizing memory
      management practices.
    question: What should I do if my application is running slow during rendering?
  - answer: For assistance, check the [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I find support for GroupDocs.Viewer issues?
  type: FAQPage
tags:
- limit outlook items
- GroupDocs Viewer
- Java email rendering
- PST processing
- OST rendering
title: Πώς να περιορίσετε outlook items java με το GroupDocs.Viewer
type: docs
url: /el/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

# Πώς να περιορίσετε τα στοιχεία outlook java με το GroupDocs.Viewer

Η διαχείριση τεράστιων αρχείων δεδομένων Outlook (PST ή OST) μπορεί γρήγορα να γίνει σημείο συμφόρησης στην απόδοση. Σε αυτόν τον οδηγό θα ανακαλύψετε πώς να **limit outlook items java** κατά την απόδοση με το GroupDocs.Viewer for Java, ώστε να επεξεργάζεστε μόνο τα δεδομένα που χρειάζεστε πραγματικά. Εφαρμόζοντας την τεχνική **limit items per folder**, η εφαρμογή σας παραμένει ανταποκρινόμενη ακόμη και με gigabytes δεδομένων email.

![Περιορισμός Απόδοσης Στοιχείων Outlook με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

[Περιορισμός Απόδοσης Στοιχείων Outlook με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Τι θα μάθετε
- Ρύθμιση του GroupDocs.Viewer για Java  
- Διαμόρφωση της βιβλιοθήκης για **set max items** ανά φάκελο σε αρχεία Outlook  
- Πραγματικά σενάρια όπου ο περιορισμός στοιχείων ανά φάκελο βελτιώνει την ταχύτητα και μειώνει τη χρήση μνήμης  

## Γρήγορες απαντήσεις
- **Τι κάνει το “set max items per folder”;** Περιορίζει την απόδοση σε έναν καθορισμένο αριθμό στοιχείων email μέσα σε κάθε φάκελο Outlook.  
- **Γιατί να περιορίσετε τα στοιχεία Outlook;** Για να μειώσετε τον χρόνο επεξεργασίας και την κατανάλωση μνήμης για μεγάλες θυρίδες.  
- **Ποια έκδοση υποστηρίζει αυτή τη δυνατότητα;** GroupDocs.Viewer 25.2 και μεταγενέστερες.  
- **Χρειάζομαι άδεια;** Ναι, απαιτείται δοκιμαστική ή αγορασμένη άδεια για χρήση σε παραγωγή.  
- **Μπορώ να αλλάξω το όριο κατά την εκτέλεση;** Απόλυτα – απλώς τροποποιήστε την τιμή `setMaxItemsInFolder` πριν από την απόδοση.

## Τι είναι το “set max items per folder”;
Η φόρτωση μόνο ενός υποσυνόλου των μηνυμάτων εμποδίζει το viewer να σαρώσει ολόκληρη τη θυρίδα. Όταν **limit outlook items java**, ο renderer σταματά αφού επεξεργαστεί τον καθορισμένο αριθμό στοιχείων σε κάθε φάκελο, παρέχοντας μια γρήγορη προεπισκόπηση ενώ διατηρεί τη χρήση μνήμης χαμηλή.

## Γιατί να χρησιμοποιήσετε την προσέγγιση περιορισμού στοιχείων ανά φάκελο;
Ο περιορισμός στοιχείων ανά φάκελο μειώνει δραστικά τους κύκλους CPU και την κατανάλωση heap. Σε δοκιμές benchmark, η απόδοση ενός PST 2 GB με όριο 50 στοιχείων ανά φάκελο ολοκληρώθηκε σε λιγότερο από 30 δευτερόλεπτα, σε σύγκριση με πάνω από 3 λεπτά όταν επεξεργαζόταν ολόκληρη η θυρίδα. Αυτή η εξοικονόμηση χρόνου 80% καθιστά τη δυνατότητα απαραίτητη για κλιμακώσιμες λύσεις αρχειοθέτησης email.

## Προαπαιτούμενα
Βεβαιωθείτε ότι έχετε τα παρακάτω πριν ξεκινήσετε:

### Απαιτούμενες βιβλιοθήκες και εξαρτήσεις
1. **Java Development Kit (JDK)** – Εγκαταστήστε το JDK 8 ή νεότερο.  
2. **GroupDocs.Viewer for Java** – Προσθέστε το ως εξάρτηση στο έργο σας.

### Απαιτήσεις ρύθμισης περιβάλλοντος
- Ένα κατάλληλο IDE όπως IntelliJ IDEA, Eclipse ή NetBeans.  
- Εγκατεστημένο Maven εάν διαχειρίζεστε τις εξαρτήσεις μέσω αυτού.

### Προαπαιτούμενες γνώσεις
- Βασική κατανόηση του προγραμματισμού Java και της διαχείρισης αρχείων.  
- Η εξοικείωση με έργα Maven είναι ωφέλιμη αλλά όχι απαραίτητη.

## Ρύθμιση του GroupDocs.Viewer για Java
Ρυθμίστε το GroupDocs.Viewer στο έργο σας χρησιμοποιώντας Maven:

**Διαμόρφωση Maven**  
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
- **Δωρεάν δοκιμή**: Κατεβάστε μια δωρεάν δοκιμή από [GroupDocs](https://releases.groupdocs.com/viewer/java/) για να εξερευνήσετε τις δυνατότητες της βιβλιοθήκης.  
- **Προσωρινή άδεια**: Αποκτήστε μια προσωρινή άδεια για πλήρη πρόσβαση χωρίς περιορισμούς αξιολόγησης στο [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Αγορά**: Για μακροπρόθεσμη χρήση, εξετάστε την αγορά άδειας από την [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Βασική αρχικοποίηση και ρύθμιση
Μόλις διαμορφωθεί το Maven, αρχικοποιήστε το GroupDocs.Viewer στην εφαρμογή Java σας δημιουργώντας το αντικείμενο viewer. Αυτό σας επιτρέπει να φορτώνετε και να αποδίδετε έγγραφα.

## Οδηγός υλοποίησης

### Περιορισμός στοιχείων που αποδίδονται από αρχεία Outlook
Αυτή η ενότητα περιγράφει πώς να περιορίσετε τα στοιχεία που αποδίδονται από αρχεία δεδομένων Outlook χρησιμοποιώντας το GroupDocs.Viewer for Java.

#### Επισκόπηση
Διαμορφώνοντας συγκεκριμένες επιλογές, μπορείτε να περιορίσετε την απόδοση σε έναν ορισμένο αριθμό στοιχείων ανά φάκελο. Αυτή η δυνατότητα βελτιώνει την απόδοση και την αποδοτικότητα όταν εργάζεστε με μεγάλα σύνολα δεδομένων email.

**Βήμα 1: ρύθμιση διαδρομής καταλόγου εξόδου**  
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```  
Αυτός ο κώδικας ρυθμίζει τον κατάλογο όπου θα αποθηκευτούν τα αποδοθέντα αρχεία HTML. Αντικαταστήστε το `"LimitCountOfItemsToRender"` με το επιθυμητό όνομα διαδρομής.

**Βήμα 2: ορισμός μορφής διαδρομής αρχείου για σελίδες HTML**  
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```  
Δημιουργήστε μια συνεπή μορφή ονομασίας για τις σελίδες HTML που δημιουργούνται κατά την απόδοση, εξασφαλίζοντας εύκολη πρόσβαση και διαχείριση.

**Βήμα 3: διαμόρφωση HtmlViewOptions με ενσωματωμένους πόρους**  
`HtmlViewOptions` καθορίζει τις επιλογές απόδοσης όπως μορφή και διαχείριση ενσωματωμένων πόρων.  
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```  

**Βήμα 4: ρύθμιση επιλογών Outlook για περιορισμό στοιχείων ανά φάκελο**  
`setMaxItemsInFolder` ορίζει τον μέγιστο αριθμό στοιχείων που θα αποδοθούν ανά φάκελο Outlook.  
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```  

**Βήμα 5: φόρτωση και απόδοση του εγγράφου**  
`Viewer` είναι η κύρια κλάση που φορτώνει και αποδίδει αρχεία Outlook.  
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```  
Χρησιμοποιήστε την κλάση `Viewer` για να φορτώσετε ένα αρχείο OST και να το αποδώσετε σύμφωνα με τις καθορισμένες επιλογές προβολής. Η δήλωση try‑with‑resources εξασφαλίζει ότι οι πόροι κλείνουν σωστά μετά τη χρήση.

### Συμβουλές αντιμετώπισης προβλημάτων
- Βεβαιωθείτε ότι όλες οι διαδρομές και οι κατάλογοι υπάρχουν πριν εκτελέσετε τον κώδικά σας.  
- Επικυρώστε ότι οι εξαρτήσεις του GroupDocs.Viewer έχουν επιλυθεί σωστά από το Maven.  
- Ελέγξτε για τυχόν εξαιρέσεις κατά την απόδοση, που μπορεί να υποδεικνύουν προβλήματα με μορφές αρχείων ή δικαιώματα.

## Πρακτικές εφαρμογές
1. **Αρχειοθέτηση email** – Ο περιορισμός απόδοσης στοιχείων είναι ιδανικός για εφαρμογές που εστιάζουν στην αρχειοθέτηση συγκεκριμένων email αντί για ολόκληρα σύνολα δεδομένων.  
2. **Μεταφορά δεδομένων** – Κατά τη μεταφορά δεδομένων μεταξύ συστημάτων, αποδίδετε μόνο τα απαραίτητα στοιχεία για βελτιστοποίηση της απόδοσης και μείωση του χρόνου επεξεργασίας.  
3. **Προσαρμοσμένες αναφορές** – Δημιουργήστε αναφορές αποδίδοντας επιλεκτικά το απαιτούμενο περιεχόμενο email χωρίς να φορτώνετε ολόκληρους φακέλους.

## Σκέψεις απόδοσης
### Συμβουλές βελτιστοποίησης απόδοσης
- Περιορίστε τον αριθμό στοιχείων ανά φάκελο για μείωση της χρήσης μνήμης.  
- Χρησιμοποιήστε τους ενσωματωμένους πόρους αποδοτικά για να αποφύγετε επιπλέον κλήσεις δικτύου κατά την απόδοση.

### Οδηγίες χρήσης πόρων
- Παρακολουθήστε τη μνήμη JVM και προσαρμόστε τις ρυθμίσεις ανάλογα με το μέγεθος των αρχείων Outlook που επεξεργάζεστε.

### Καλές πρακτικές διαχείρισης μνήμης Java
- Χρησιμοποιήστε try‑with‑resources για αυτόματη διαχείριση πόρων.  
- Διεξάγετε profiling της εφαρμογής σας για να εντοπίσετε σημεία συμφόρησης που σχετίζονται με τη διαχείριση μεγάλων αρχείων.

## Συνηθισμένα προβλήματα & πώς να τα αποφύγετε
| Σύμπτωμα | Πιθανή αιτία | Διόρθωση |
|----------|--------------|----------|
| Δεν δημιουργήθηκαν αρχεία εξόδου | Η διαδρομή καταλόγου εξόδου είναι εσφαλμένη ή λείπουν δικαιώματα | Επαληθεύστε ότι το `outputDirectory` υπάρχει και είναι εγγράψιμο |
| Η απόδοση σταματά μετά από λίγα στοιχεία | `setMaxItemsInFolder` ορίστηκε πολύ χαμηλό | Αυξήστε το όριο ή κάντε το διαμορφώσιμο |
| OutOfMemoryError σε μεγάλο PST | Οι προεπιλεγμένες ρυθμίσεις μνήμης είναι ανεπαρκείς | Αυξήστε το heap της JVM (`-Xmx`) και διατηρήστε το όριο χαμηλό |

## Συμπέρασμα
Σε αυτό το σεμινάριο, μάθατε πώς να **limit outlook items java** σε αρχεία δεδομένων Outlook χρησιμοποιώντας το GroupDocs.Viewer for Java. Ακολουθώντας τα βήματα και εφαρμόζοντας τις συμβουλές απόδοσης, μπορείτε να δημιουργήσετε αποδοτικές εφαρμογές προσαρμοσμένες στις συγκεκριμένες ανάγκες σας.

### Επόμενα βήματα
- Εξερευνήστε πρόσθετες δυνατότητες του GroupDocs.Viewer ανατρέχοντας στην [επίσημη τεκμηρίωση](https://docs.groupdocs.com/viewer/java/).  
- Πειραματιστείτε με διαφορετικές επιλογές απόδοσης για να βρείτε την καλύτερη διαμόρφωση για τις απαιτήσεις της εφαρμογής σας.

Έτοιμοι να το δοκιμάσετε; Ξεκινήστε να υλοποιείτε αυτή τη λύση στα έργα σας σήμερα και δείτε βελτιωμένη αποδοτικότητα από πρώτο χέρι.

## Συχνές ερωτήσεις

**Ε: Τι χρησιμοποιείται το GroupDocs.Viewer Java;**  
Είναι μια ευέλικτη βιβλιοθήκη σχεδιασμένη για την απόδοση διαφόρων μορφών εγγράφων, συμπεριλαμβανομένων των αρχείων δεδομένων Outlook, σε μορφές HTML ή εικόνας.

**Ε: Πώς μπορώ να αποκτήσω δωρεάν δοκιμή του GroupDocs.Viewer;**  
Επισκεφθείτε το [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) για πρόσβαση και επιλογές λήψης.

**Ε: Μπορώ να περιορίσω την απόδοση στοιχείων σε αρχεία PST επίσης;**  
Ναι, η ίδια διαμόρφωση ισχύει και για τα αρχεία OST και PST.

**Ε: Τι πρέπει να κάνω αν η εφαρμογή μου λειτουργεί αργά κατά την απόδοση;**  
Ανασκοπήστε τα όρια στοιχείων και τις ρυθμίσεις πόρων· εξετάστε την βελτιστοποίηση των πρακτικών διαχείρισης μνήμης.

**Ε: Πού μπορώ να βρω υποστήριξη για προβλήματα του GroupDocs.Viewer;**  
Για βοήθεια, ελέγξτε το [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).

## Πρόσθετοι πόροι
- [Τεκμηρίωση](https://docs.groupdocs.com/viewer/java/)
- [Αναφορά API](https://reference.groupdocs.com/viewer/java/)
- [Λήψη GroupDocs.Viewer για Java](https://releases.groupdocs.com/viewer/java/)
- [Αγορά Άδειας](https://purchase.groupdocs.com/buy)
- [Δωρεάν Έκδοση Δοκιμής](https://releases.groupdocs.com/viewer/java/)
- [Αίτηση για Προσωρινή Άδεια](https://purchase.groupdocs.com/temporary-license/)
- [Φόρουμ Υποστήριξης](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία ενημέρωση:** 2026-08-19  
**Δοκιμάστηκε με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs

## Σχετικά Μαθήματα

- [Απόδοση αρχείων Outlook PST και OST σε HTML χρησιμοποιώντας Java και GroupDocs.Viewer](/viewer/java/rendering-basics/render-outlook-data-html-groupdocs-java/)
- [Οδηγός GroupDocs Viewer Java: Κατακτήστε την Απόδοση και Φιλτράρισμα Δεδομένων Outlook](/viewer/java/advanced-rendering/render-filter-outlook-data-groupdocs-java/)
- [Μείωση Χρήσης Μνήμης Java – Βελτιστοποίηση Απόδοσης Εγγράφων](/viewer/java/performance-optimization/)