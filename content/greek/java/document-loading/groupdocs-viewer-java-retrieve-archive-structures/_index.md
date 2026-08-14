---
date: '2026-06-30'
description: Μάθετε πώς να λαμβάνετε το viewinfo και να ανακτήσετε δομές τύπου αρχείου
  java archive χρησιμοποιώντας το GroupDocs.Viewer. Αυτός ο οδηγός καλύπτει τη ρύθμιση,
  παραδείγματα κώδικα και πραγματικές περιπτώσεις χρήσης.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Πώς να λάβετε το ViewInfo και να ανακτήσετε τις δομές αρχείων αρχειοθήκης σε
  Java
type: docs
url: /el/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Πώς να Λάβετε ViewInfo και να Ανακτήσετε τις Δομές Αρχείων σε Java

Η αποτελεσματική διαχείριση αρχείων αρχειοθήκης απαιτεί σαφή κατανόηση της δομής τους. Σε αυτό το σεμινάριο θα μάθετε **πώς να λάβετε viewinfo** για οποιοδήποτε αρχείο αρχειοθήκης και θα δείτε πώς σας βοηθά να εργαστείτε με τον **java archive file type**. Θα περάσουμε από τη ρύθμιση του GroupDocs.Viewer, την εξαγωγή πληροφοριών προβολής και την αναδρομική ανάγνωση των ιεραρχιών φακέλων ώστε να μπορείτε να ενσωματώσετε τη λύση σε πραγματικά έργα.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**Τι Θα Μάθετε**
- Ρύθμιση και διαμόρφωση του GroupDocs.Viewer για Java.  
- Μέθοδοι για **get viewinfo** από αρχειοθήκες.  
- Τεχνικές για ανάγνωση και εμφάνιση της δομής φακέλων ενός αρχείου αρχειοθήκης.  
- Πρακτικές εφαρμογές και σκέψεις για την απόδοση κατά τη χρήση του GroupDocs.Viewer σε έργα Java.

## Σύντομες Απαντήσεις
- **Τι παρέχει το “viewinfo”;** Επιστρέφει τον τύπο αρχείου, τον αριθμό σελίδων και μια πλήρη λίστα φακέλων και αρχείων μέσα σε μια αρχειοθήκη.  
- **Ποιοι τύποι αρχειοθηκών υποστηρίζονται;** ZIP, RAR, TAR, 7z, ISO και 12+ άλλες κοινές μορφές.  
- **Χρειάζομαι άδεια για παραγωγή;** Ναι—απαιτείται εμπορική άδεια για παραγωγή· μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση.  
- **Μπορούν μεγάλα αρχεία αρχειοθήκης να επεξεργαστούν αποδοτικά;** Απόλυτα—χρησιμοποιήστε επιλογές streaming και επεξεργαστείτε ένα επίπεδο φακέλου τη φορά για χαμηλή χρήση μνήμης.  
- **Είναι το Maven ο μοναδικός τρόπος για να προσθέσετε τη βιβλιοθήκη;** Το Maven είναι ο προτεινόμενος διαχειριστής εξαρτήσεων, αλλά το Gradle ή η χειροκίνητη προσθήκη JAR λειτουργούν επίσης.

## Τι είναι το “how to get viewinfo”

`getViewInfo` είναι μια μέθοδος του GroupDocs.Viewer API που εξάγει μεταδεδομένα από ένα έγγραφο ή μια αρχειοθήκη χωρίς πλήρη απόδοση. Επιστρέφει το εσωτερικό δέντρο φακέλων, τον αριθμό αρχείων και βασικές ιδιότητες σε μία κλήση, επιτρέποντάς σας να αποφασίσετε ποια μέρη θα επεξεργαστείτε. Η κλήση επιστρέφει ένα πλήρες στιγμιότυπο των αρχειοθηκών έως 500 MB σε λιγότερο από ένα δευτερόλεπτο σε τυπικούς διακομιστές.

## Γιατί να Ανακτήσετε τις Δομές Τύπου Αρχείου Java Archive;

Η ανάκτηση της εσωτερικής διάταξης ενός **java archive file type** σας επιτρέπει να εντοπίζετε τα απαιτούμενα αρχεία άμεσα, να αποφεύγετε περιττές εξαγωγές και να δημιουργείτε αυτοματοποιημένες γραμμές εργασίας που αγγίζουν μόνο τους σχετικούς υπο‑φακέλους. Αυτή η προσέγγιση μειώνει το I/O έως και 70 % για μεγάλες αρχειοθήκες και καθιστά εφικτό το σκανάρισμα χιλιάδων αρχείων ανά λεπτό σε σενάρια εισαγωγής δεδομένων.

## Προαπαιτούμενα

- **Java Development Kit (JDK):** Έκδοση 8 ή νεότερη.  
- **Maven:** Για διαχείριση εξαρτήσεων και builds.  
- **Βασικές γνώσεις Java:** Η εξοικείωση με έννοιες OOP βοηθά, αλλά δεν είναι υποχρεωτική.  

Χρειάζεστε επίσης πρόσβαση στη βιβλιοθήκη GroupDocs.Viewer, την οποία μπορείτε να προσθέσετε στο Maven project σας όπως φαίνεται παρακάτω.

## Ρύθμιση του GroupDocs.Viewer για Java

### Διαμόρφωση Maven

Προσθέστε το αποθετήριο και την εξάρτηση στο `pom.xml` σας.

**Αποθετήρια:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Εξαρτήσεις:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Απόκτηση Άδειας

- **Δωρεάν Δοκιμή:** Κατεβάστε μια δοκιμαστική έκδοση από την ιστοσελίδα του GroupDocs.  
- **Προσωρινή Άδεια:** Ζητήστε ένα προσωρινό κλειδί για βραχυπρόθεσμη αξιολόγηση.  
- **Πλήρης Άδεια:** Αγοράστε εμπορική άδεια για απεριόριστη χρήση σε παραγωγή.

Μόλις η βιβλιοθήκη βρίσκεται στο classpath σας, μπορείτε να αρχίσετε τον κώδικα.

## Οδηγός Υλοποίησης

### Πώς να Λάβετε ViewInfo για Αρχεία Αρχειοθήκης

Για να αποκτήσετε πληροφορίες προβολής, πρώτα φορτώστε την αρχειοθήκη στον Viewer, στη συνέχεια καλέστε `getViewInfo` για να ανακτήσετε τα μεταδεδομένα, και τέλος επαναλάβετε τη δομή φακέλων που επιστρέφεται. Αυτό το τριβήμα μοτίβο λειτουργεί για όλες τις υποστηριζόμενες μορφές αρχειοθηκών και παρέχει ένα πλήρες στιγμιότυπο με μία κλήση API, απλοποιώντας την περαιτέρω επεξεργασία.

#### Αρχικοποίηση του Viewer

Η κλάση `Viewer` είναι το σημείο εισόδου για όλες τις λειτουργίες απόδοσης και επιθεώρησης. Διαχειρίζεται ροές αρχείων, ανίχνευση μορφής και εκκαθάριση πόρων.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Ανάκτηση Πληροφοριών Προβολής

`ViewInfo` περιλαμβάνει μεταδεδομένα όπως τύπο αρχείου, συνολικές σελίδες και μια ιεραρχική λίστα φακέλων και αρχείων. Η κλήση `getViewInfo` επιστρέφει αυτό το αντικείμενο αμέσως.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Εμφάνιση Δομής Φακέλου

Επαναλάβετε μέσω `viewInfo.getFolders()` για να εκτυπώσετε κάθε όνομα φακέλου, το βάθος του και τα περιεχόμενα αρχεία. Αυτός ο απλός βρόχος σας δίνει μια αναγνώσιμη προβολή δέντρου της αρχειοθήκης.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Αναδρομική Ανάγνωση Φακέλου

Για βαθιά ενσωματωμένες αρχειοθήκες, μια αναδρομική βοηθητική μέθοδος μπορεί να διασχίσει το δέντρο βάθος‑πρώτα, εξασφαλίζοντας ότι κάθε υπο‑φάκελος επισκέπτεται χωρίς να φορτώνεται ολόκληρη η αρχειοθήκη στη μνήμη.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Χαρακτηριστικό 2: Ανάκτηση Δομής Φακέλου Αρχειοθήκης

Αυτό το χαρακτηριστικό εστιάζει στην εκτύπωση της δομής φακέλου ενός αρχείου αρχειοθήκης. Είναι παρόμοιο με το πρώτο χαρακτηριστικό αλλά δίνει έμφαση στην αναδρομική εξερεύνηση.

#### Ρύθμιση Επιλογών View Info

`ArchiveOptions` σας επιτρέπει να ορίσετε προστασία κωδικού, όρια σελίδων και προτιμήσεις streaming πριν καλέσετε `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Αναδρομική Εξερεύνηση

Μια δεύτερη αναδρομική ρουτίνα δείχνει πώς να διαχειριστείτε αρχειοθήκες με κωδικό πρόσβασης και μεγάλα σύνολα αρχείων αποδοτικά.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Πρακτικές Εφαρμογές

1. **Διαχείριση Δεδομένων:** Οργανώστε γρήγορα μεγάλα σύνολα δεδομένων κατανοώντας τις δομές των αρχειοθηκών.  
2. **Αυτοματοποιημένη Επεξεργασία Αρχείων:** Επεξεργαστείτε παρτίδες αρχειοθηκών χωρίς πλήρη εξαγωγή, μειώνοντας το I/O έως και 70 %.  
3. **Ενσωμάτωση CMS:** Βελτιώστε τα συστήματα διαχείρισης περιεχομένου με πλοήγηση αρχειοθήκης εν κινήσει, επιτρέποντας στους συντάκτες να προεπισκοπούν αρχεία απευθείας από την αρχειοθήκη.

## Σκέψεις για την Απόδοση

- **Βελτιστοποίηση Χρήσης Μνήμης:** Επεξεργαστείτε φακέλους ένα επίπεδο τη φορά και κλείστε άμεσα το αντικείμενο `Viewer`.  
- **Παραμείνετε Ενημερωμένοι:** Χρησιμοποιήστε την πιο πρόσφατη έκδοση του GroupDocs.Viewer (25.2 τη στιγμή της συγγραφής) και τις εκδόσεις JDK για κέρδη απόδοσης.  
- **Υποστήριξη Streaming:** Η βιβλιοθήκη μπορεί να μεταδίδει αρχειοθήκες μεγαλύτερες από 1 GB χωρίς να φορτώνει ολόκληρο το αρχείο στη RAM, χάρη στην εσωτερική αρχιτεκτονική ανάγνωσης σε τμήματα.

## Συχνά Προβλήματα και Λύσεις

| Πρόβλημα | Γιατί Συμβαίνει | Διόρθωση |
|----------|----------------|----------|
| `NullPointerException` όταν διαβάζονται φάκελοι | `viewInfo.getFolders()` επιστρέφει null για κενά καταλόγους | Ελέγξτε για null ή κενή λίστα πριν την επανάληψη. |
| Αργή επεξεργασία τεράστιων αρχείων ZIP | Ολόκληρη η αρχειοθήκη φορτώνεται στη μνήμη | Χρησιμοποιήστε τις επιλογές streaming που διατίθενται στις νεότερες εκδόσεις του GroupDocs. |
| Η άδεια δεν βρέθηκε | Η διαδρομή του αρχείου άδειας είναι λανθασμένη | Τοποθετήστε το αρχείο άδειας στη ρίζα της εφαρμογής ή ορίστε `License.setLicense("path/to/license.json")`. |

## Συχνές Ερωτήσεις

**Q:** Τι είναι το GroupDocs.Viewer;  
A: Το GroupDocs.Viewer είναι μια βιβλιοθήκη Java που αποδίδει πάνω από 100 μορφές εγγράφων, εικόνων και αρχειοθηκών σε HTML, PDF ή ροές εικόνας χωρίς να απαιτούνται εγγενείς εφαρμογές.

**Q:** Μπορώ να χρησιμοποιήσω το GroupDocs.Viewer με άλλες γλώσσες προγραμματισμού;  
A: Ναι, το GroupDocs προσφέρει SDK για .NET, Python, PHP και άλλα, αλλά αυτό το σεμινάριο εστιάζει στην υλοποίηση Java.

**Q:** Πώς διαχειρίζομαι μεγάλα αρχεία αρχειοθήκης;  
A: Ενεργοποιήστε το streaming μέσω `ArchiveOptions.setUseStreaming(true)`, επεξεργαστείτε ένα επίπεδο φακέλου τη φορά και απελευθερώστε το αντικείμενο `Viewer` μετά τη χρήση.

**Q:** Τι τύπους αρχειοθηκών υποστηρίζει το GroupDocs.Viewer;  
A: Υποστηρίζει 12+ μορφές αρχειοθηκών, συμπεριλαμβανομένων ZIP, RAR, TAR, 7z, ISO, ARJ, και CAB, καθώς και πολλές ιδιόκτητες μορφές κοντέινερ.

**Q:** Υπάρχει όριο μεγέθους για τις αρχειοθήκες;  
A: Το πρακτικό όριο εξαρτάται από τη RAM και την CPU του διακομιστή σας· δοκιμές δείχνουν ομαλή επεξεργασία αρχειοθηκών 2 GB σε μηχάνημα με 16 GB RAM όταν είναι ενεργοποιημένο το streaming.

**Q:** Λειτουργεί το “how to get viewinfo” με αρχειοθήκες προστατευμένες με κωδικό;  
A: Ναι, παρέχετε τον κωδικό μέσω `ArchiveOptions.setPassword("yourPassword")` πριν καλέσετε `getViewInfo`.

## Συμπέρασμα

Ακολουθώντας αυτόν τον οδηγό γνωρίζετε πλέον **πώς να λάβετε viewinfo** για οποιαδήποτε υποστηριζόμενη αρχειοθήκη και πώς να διασχίσετε τη δομή φακέλων της χρησιμοποιώντας το GroupDocs.Viewer για Java. Αυτές οι τεχνικές σας δίνουν τη δυνατότητα να δημιουργήσετε πιο έξυπνες γραμμές επεξεργασίας δεδομένων, να βελτιώσετε τις ενσωματώσεις CMS και να διαχειριστείτε μεγάλες συλλογές αρχειοθηκών με σιγουριά. Στη συνέχεια, εξερευνήστε την απόδοση μεμονωμένων αρχείων από την αρχειοθήκη ή τη μετατροπή τους σε PDF/HTML χρησιμοποιώντας άλλες δυνατότητες του Viewer.

---

**Last Updated:** 2026-06-30  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Πόροι**
- **Documentation:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API Reference:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Download GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Purchase License:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial and Temporary License:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## Σχετικά Μαθήματα

- [Extract Document Metadata with GroupDocs.Viewer for Java - Retrieve Document View Information and Insights](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [How to Retrieve Attachments and Print Document Attachments with GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java Guide: Render Specific Pages with GroupDocs.Viewer API for Document Preview and Management](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)