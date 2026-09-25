---
date: '2026-09-25'
description: Μάθετε πώς να δημιουργήσετε προβολή html mpp με GroupDocs Viewer για
  Java, αποδίδοντας έγγραφα έργου ανά χρονικά διαστήματα με κώδικα step‑by‑step.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Δημιουργήστε προβολή html mpp με GroupDocs Viewer για Java ώστε να
  αποδίδετε αρχεία Microsoft Project ανά συγκεκριμένα χρονικά διαστήματα. Ακολουθήστε
  τη ρύθμιση, την αδειοδότηση και τα αποσπάσματα κώδικα step‑by‑step για ακριβή οπτικοποίηση
  χρονοδιαγράμματος.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: Δημιουργία προβολής html mpp με GroupDocs Viewer για Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: Δημιουργία προβολής html mpp με GroupDocs Viewer (Java)
type: docs
url: /el/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Πώς να χρησιμοποιήσετε το GroupDocs Viewer για την απόδοση εγγράφων έργου ανά χρονικά διαστήματα σε Java

Σε αυτό το tutorial θα μάθετε πώς να **create html view mpp** με το GroupDocs Viewer for Java, επιτρέποντάς σας να αποδίδετε μόνο τα τμήματα ενός αρχείου Microsoft Project που εμπίπτουν σε ένα συγκεκριμένο εύρος ημερομηνίας έναρξης και λήξης. Θα περάσουμε από τη ρύθμιση του Maven, την αδειοδότηση και τις ακριβείς κλήσεις API που χρειάζεστε για να ενσωματώσετε ακριβείς προβολές χρονοδιαγράμματος απευθείας στις εφαρμογές σας.

![Απόδοση εγγράφων έργου ανά χρονικά διαστήματα με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Για προεπισκόπηση, δείτε το [Απόδοση εγγράφων έργου ανά χρονικά διαστήματα με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Γρήγορες Απαντήσεις
- **Τι κάνει η λειτουργία;** Αποδίδει μόνο το τμήμα ενός αρχείου Microsoft Project που εμπίπτει μεταξύ μιας ημερομηνίας έναρξης και λήξης.  
- **Ποια μορφή εξόδου χρησιμοποιείται;** HTML με ενσωματωμένους πόρους, ιδανική για ενσωμάτωση στο web.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Μπορώ να αλλάξω το εύρος ημερομηνιών κατά την εκτέλεση;** Ναι—προσαρμόστε τις τιμές `setStartDate` και `setEndDate` στις επιλογές απόδοσης.  
- **Υποστηρίζεται σε όλες τις εκδόσεις Java;** Λειτουργεί με Java 8+ εφόσον χρησιμοποιείτε το GroupDocs.Viewer 25.2 ή νεότερο.

## Τι είναι το create html view mpp;
`create html view mpp` είναι η διαδικασία μετατροπής ενός αρχείου Microsoft Project (`.mpp` ή `.mpt`) σε ένα σύνολο σελίδων HTML που αντιπροσωπεύουν το χρονοδιάγραμμα. Το GroupDocs Viewer εκτελεί τη μετατροπή στην πλευρά του διακομιστή, ώστε να μπορείτε να εμφανίζετε το χρονοδιάγραμμα σε οποιονδήποτε περιηγητή χωρίς εγκατάσταση του Microsoft Project.

## Γιατί να αποδίδετε έγγραφα έργου με χρονικά διαστήματα;
Η απόδοση μόνο του απαιτούμενου χρονικού διαστήματος μειώνει το μέγεθος του παραγόμενου HTML, επιταχύνει τη φόρτωση της σελίδας και σας επιτρέπει να εστιάσετε στη συγκεκριμένη φάση του έργου που χρειάζεται ανάλυση. Αυτή η στοχευμένη προβολή είναι ιδανική για πίνακες ελέγχου, αναφορές κατάστασης ή ενσωμάτωση σε προσαρμοσμένα εργαλεία PM όπου τα πλήρη δεδομένα του έργου θα ήταν υπερβολικά.

## Προαπαιτούμενα

- **GroupDocs.Viewer for Java** έκδοση 25.2 ή νεότερη.  
- Java Development Kit (JDK) 8 ή νεότερο.  
- Ένα IDE όπως IntelliJ IDEA ή Eclipse.  
- Βασικές γνώσεις Maven.  

## Ρύθμιση του GroupDocs.Viewer για Java

### Εξάρτηση Maven

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

### Βήματα απόκτησης άδειας

1. **Free trial** – Κατεβάστε μια δοκιμαστική έκδοση από τη [σελίδα λήψης του GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary license** – Αποκτήστε προσωρινή άδεια για εκτεταμένη δοκιμή μέσω της [σελίδας temporary‑license](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Για απεριόριστη χρήση σε παραγωγή, αγοράστε άδεια στη [σελίδα αγοράς του GroupDocs](https://purchase.groupdocs.com/buy).

## Βασική αρχικοποίηση του viewer

`Viewer` είναι η κύρια κλάση στο GroupDocs.Viewer for Java που φορτώνει ένα έγγραφο και παρέχει δυνατότητες απόδοσης.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Ανάκτηση πληροφοριών προβολής για αρχεία έργου

`ProjectManagementViewInfo` παρέχει μεταδεδομένα σχετικά με ένα αρχείο Microsoft Project, συμπεριλαμβανομένων των συνολικών ημερομηνιών έναρξης και λήξης του χρονοδιαγράμματος.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## Διαμόρφωση επιλογών απόδοσης HTML (δημιουργία HTML από το έργο)

`HtmlViewOptions` διαμορφώνει τον τρόπο με τον οποίο το GroupDocs αποδίδει HTML, επιτρέποντάς σας να ορίσετε το εύρος ημερομηνιών, να ενσωματώσετε πόρους και να προσαρμόσετε την εμφάνιση.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Εκτέλεση της διαδικασίας απόδοσης

`viewer.render` εκτελεί τη μετατροπή βάσει των παρεχόμενων επιλογών και γράφει τα παραγόμενα αρχεία HTML στον φάκελο προορισμού.

```java
viewer.view(viewOptions);
```

## Συνηθισμένα προβλήματα & αντιμετώπιση

- **Incorrect file paths** – Ελέγξτε ξανά ότι τόσο το αρχείο πηγής `.mpp` όσο και ο φάκελος εξόδου υπάρχουν.  
- **Unsupported file type** – Βεβαιωθείτε ότι το έγγραφο είναι σε υποστηριζόμενη μορφή Project (π.χ., `.mpp`, `.mpt`).  
- **License errors** – Μια δοκιμαστική άδεια μπορεί να επιβάλλει περιορισμούς απόδοσης· μεταβείτε σε πλήρη άδεια για απεριόριστη χρήση.  

## Πρακτικές εφαρμογές

1. **Project timeline analysis** – Εμφανίστε στα ενδιαφερόμενα μόνο τη τρέχουσα φάση.  
2. **Automated reporting** – Δημιουργήστε HTML αναφορές με χρονικό περιορισμό για εβδομαδιαίες ενημερώσεις κατάστασης.  
3. **Integration with dashboards** – Ενσωματώστε τις παραγόμενες σελίδες σε εργαλεία BI ή προσαρμοσμένες πύλες.  
4. **Archival** – Αποθηκεύστε ένα φιλικό στο web στιγμιότυπο του χρονοδιαγράμματος του έργου για μελλοντική αναφορά.  

## Συμβουλές απόδοσης

- Χρησιμοποιήστε την επιλογή *embedded resources* για να διατηρήσετε κάθε σελίδα HTML αυτόνομη, μειώνοντας τα αιτήματα HTTP.  
- Για πολύ μεγάλα έργα, εξετάστε την απόδοση σε μικρότερα χρονικά τμήματα για να διατηρήσετε τη χρήση μνήμης χαμηλή. Η απόδοση ενός τμήματος ενός έτους μπορεί να μειώσει το μέγεθος του HTML έως και 80 % σε σύγκριση με την εξαγωγή ολόκληρου του έργου, μειώνοντας τον χρόνο φόρτωσης από αρκετά δευτερόλεπτα σε κάτω από ένα δευτερόλεπτο σε τυπικούς διακομιστές.  
- Καθαρίστε τα προσωρινά αρχεία μετά την εξυπηρέτηση τους για να αποφύγετε την υπερφόρτωση του δίσκου.  

## Συμπέρασμα

Τώρα γνωρίζετε **πώς να χρησιμοποιήσετε το GroupDocs** Viewer για την απόδοση εγγράφων έργου εντός ενός συγκεκριμένου χρονικού διαστήματος και **να δημιουργήσετε HTML από δεδομένα έργου** σε Java. Αυτή η δυνατότητα απλοποιεί τις οπτικοποιήσεις χρονοδιαγραμμάτων, βελτιώνει την αποδοτικότητα των αναφορών και ενσωματώνεται ομαλά με σύγχρονες web εφαρμογές.

### Επόμενα βήματα
- Εξερευνήστε πρόσθετες δυνατότητες του Viewer όπως υδατογράφημα, προστασία με κωδικό ή προσαρμοσμένο στυλ CSS.  
- Συνδυάστε αυτή τη διαδικασία απόδοσης με ένα REST API για να παρέχετε χρονοδιαγράμματα κατόπιν ζήτησης.  

## Συχνές ερωτήσεις

**Q: Ποιοι τύποι αρχείων υποστηρίζει το GroupDocs.Viewer;**  
A: Το GroupDocs.Viewer υποστηρίζει πάνω από 100 μορφές εισόδου, συμπεριλαμβανομένων των PDF, DOCX, XLSX, PPTX και αρχείων Microsoft Project, επιτρέποντας καθολική οπτικοποίηση εγγράφων.

**Q: Πώς μπορώ να ξεκινήσω με μια δωρεάν δοκιμή του GroupDocs.Viewer;**  
A: Μπορείτε να κατεβάσετε τη δοκιμαστική έκδοση από τη [σελίδα λήψης του GroupDocs Viewer Java](https://releases.groupdocs.com/viewer/java/).

**Q: Μπορώ να αποδώσω έγγραφα χωρίς ενσωμάτωση πόρων;**  
A: Ναι, μπορείτε να επιλέξετε μια διαφορετική επιλογή προβολής HTML που αναφέρεται σε εξωτερικούς πόρους αντί για ενσωμάτωση.

**Q: Τι γίνεται αν το έγγραφό μου είναι πολύ μεγάλο για απόδοση;**  
A: Σκεφτείτε να χωρίσετε το έγγραφο σε μικρότερα τμήματα ή να αποδώσετε μόνο το απαιτούμενο εύρος ημερομηνιών, όπως δείχνεται παραπάνω.

**Q: Πώς να αντιμετωπίσω σφάλματα απόδοσης;**  
A: Επαληθεύστε όλες τις ρυθμίσεις διαμόρφωσης, βεβαιωθείτε ότι έχετε έγκυρη άδεια και συμβουλευτείτε την τεκμηρίωση του GroupDocs για λεπτομερείς κωδικούς σφαλμάτων.

## Πόροι
- **Τεκμηρίωση**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Αναφορά API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Λήψη**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Αγορά**: [Αγορά άδειας GroupDocs](https://purchase.groupdocs.com/buy)
- **Δωρεάν δοκιμή**: [Δοκιμάστε τη δωρεάν έκδοση](https://releases.groupdocs.com/viewer/java/)
- **Προσωρινή άδεια**: [Αποκτήστε προσωρινή άδεια](https://purchase.groupdocs.com/temporary-license/)
- **Υποστήριξη**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Τελευταία ενημέρωση:** 2026-09-25  
**Δοκιμή με:** GroupDocs.Viewer 25.2 for Java  
**Συγγραφέας:** GroupDocs  

---

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Σχετικά Μαθήματα

- [Πώς να αποδώσετε αρχεία MS Project ως HTML, JPG, PNG και PDF με σημειώσεις χρησιμοποιώντας το GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Εξαγωγή HTML MS Project: Προσαρμογή μονάδων χρόνου μέσω GroupDocs Java](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [Groupdocs Viewer Java Ανταποκρινόμενη απόδοση Html](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)