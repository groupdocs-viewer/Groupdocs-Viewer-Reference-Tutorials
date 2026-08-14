---
date: '2026-06-30'
description: Μάθετε πώς να ανακτήσετε και να αποθηκεύσετε αποτελεσματικά συνημμένα
  εγγράφων σε εφαρμογές Java χρησιμοποιώντας java file output stream και το ισχυρό
  GroupDocs.Viewer API.
keywords:
- java file output stream
- how to save attachment
- GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  headline: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to efficiently retrieve and save document attachments in
    Java applications using java file output stream and the powerful GroupDocs.Viewer
    API.
  name: How to Retrieve and Save Document Attachments Using java file output stream
    with GroupDocs.Viewer for Java
  steps:
  - name: '**Create a Viewer Instance**'
    text: '**Create a Viewer Instance**'
  - name: '**Retrieve Attachments**'
    text: '**Retrieve Attachments**'
  - name: '**Understanding Parameters and Methods**'
    text: '**Understanding Parameters and Methods**'
  - name: '**Define the Output Directory**'
    text: '**Define the Output Directory**'
  - name: '**Save Attachments**'
    text: '**Save Attachments**'
  - name: '**Explain Parameters and Methods**'
    text: '**Explain Parameters and Methods**'
  - name: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
    text: '**Email Clients** – Automatically extract attachments from email archives
      for processing or archiving.'
  - name: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
    text: '**Document Management Systems** – Enhance DMS by retrieving and organizing
      attached files.'
  - name: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
    text: '**Legal Departments** – Extract evidence‑related attachments from legal
      documents securely.'
  type: HowTo
- questions:
  - answer: Add the Maven dependency shown earlier; the repository URL and version
      are all you need for a quick start.
    question: How do I install GroupDocs.Viewer in my Java project?
  - answer: It supports 50+ input and output formats—including PDF, DOCX, PPTX, MSG,
      and many image types—so most common business files are covered.
    question: Can GroupDocs.Viewer handle all document types?
  - answer: Verify that the output path is correct, the directory exists, and your
      process has write permissions. Also ensure you’re using `FileOutputStream` correctly
      as shown.
    question: What if I encounter errors while saving attachments?
  - answer: Yes, a valid GroupDocs.Viewer license is required for production deployments.
      A free trial is available for evaluation.
    question: Is a license required for production use?
  - answer: Using `java file output stream` with buffered I/O efficiently handles
      large binaries; monitor memory usage and consider streaming in chunks for files
      larger than 200 MB.
    question: Does this approach work with large attachment files?
  type: FAQPage
title: Πώς να ανακτήσετε και να αποθηκεύσετε συνημμένα εγγράφων χρησιμοποιώντας java
  file output stream με GroupDocs.Viewer for Java
type: docs
url: /el/java/custom-rendering/retrieve-save-document-attachments-groupdocs-viewer-java/
weight: 1
---

# Πώς να Ανακτήσετε και να Αποθηκεύσετε Συνημμένα Εγγράφων Χρησιμοποιώντας java file output stream με GroupDocs.Viewer for Java

## Εισαγωγή

Αναζητάτε να εξάγετε και να διαχειριστείτε προγραμματιστικά τα συνημμένα εγγράφων στις εφαρμογές Java χρησιμοποιώντας **java file output stream**; Με την άνοδο της ψηφιακής διαχείρισης εγγράφων, είναι κρίσιμο να έχετε εργαλεία που βελτιστοποιούν αυτές τις διαδικασίες αποδοτικά. Γνωρίστε το GroupDocs.Viewer for Java—τη λύση σας για την απρόσκοπτη ανάκτηση και αποθήκευση συνημμένων εγγράφων με ευκολία.

![Ανάκτηση και Αποθήκευση Συνημμένων Εγγράφων με το GroupDocs.Viewer for Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

[Ανάκτηση και Αποθήκευση Συνημμένων Εγγράφων με το GroupDocs.Viewer for Java](/viewer/custom-rendering/retrieve-and-save-document-attachments-java.png)

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς μπορείτε να αξιοποιήσετε τη δύναμη του GroupDocs.Viewer για να ανακτήσετε συνημμένα από έγγραφα και να τα αποθηκεύσετε στον επιθυμητό σας φάκελο. Ακολουθώντας το οδηγό, θα αποκτήσετε πρακτικές δεξιότητες στη διαχείριση δεδομένων εγγράφων αποτελεσματικά σε περιβάλλον Java, και θα δείτε ακριβώς **πώς να αποθηκεύσετε αρχεία συνημμένων** χρησιμοποιώντας το τυπικό `java file output stream`.

## Γρήγορες Απαντήσεις
- **Τι κάνει το java file output stream;** Γράφει ροές byte απευθείας σε αρχεία, επιτρέποντας την αποθήκευση δυαδικών δεδομένων (όπως συνημμένα) στο δίσκο.  
- **Ποιο API ανακτά συνημμένα;** `Viewer.getAttachments()` επιστρέφει μια λίστα μεταδεδομένων συνημμένων.  
- **Μπορώ να ορίσω τον φάκελο εξόδου;** Ναι—χρησιμοποιήστε `Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");`.  
- **Χρειάζομαι άδεια;** Μια δωρεάν δοκιμή λειτουργεί για αξιολόγηση· απαιτείται πληρωμένη άδεια για παραγωγή.  
- **Είναι αυτή η προσέγγιση thread‑safe;** Δημιουργήστε ξεχωριστό αντικείμενο `Viewer` ανά νήμα ή συγχρονίστε την πρόσβαση.

## Τι είναι java file output stream;
`java.io.FileOutputStream` είναι μια βασική κλάση της Java που γράφει ακατέργαστα bytes σε αρχείο. Είναι η ιδανική επιλογή όταν χρειάζεται να διατηρήσετε δυαδικό περιεχόμενο όπως συνημμένα email, εικόνες ή οποιαδήποτε μη‑κείμενα δεδομένα που εξάγονται από ένα έγγραφο. Υποστηρίζει την αποδοτική εγγραφή τόσο μικρών όσο και μεγάλων αρχείων και μπορεί να συνδυαστεί με buffered streams για καλύτερη απόδοση, εξασφαλίζοντας αξιόπιστη αποθήκευση δυαδικών φορτίων στο δίσκο.

## Γιατί να χρησιμοποιήσετε java file output stream με GroupDocs.Viewer;
Η χρήση του `java.io.FileOutputStream` μαζί με το GroupDocs.Viewer επιτρέπει στους προγραμματιστές να γράψουν τα bytes των συνημμένων απευθείας στο δίσκο χωρίς ενδιάμεσα βήματα μετατροπής, διατηρώντας την αρχική ακεραιότητα του αρχείου. Αυτή η προσέγγιση μειώνει την κατανάλωση μνήμης, επιταχύνει την επεξεργασία μεγάλων συνημμένων και απλοποιεί τον κώδικα αξιοποιώντας το τυπικό Java I/O μαζί με τις ισχυρές δυνατότητες εξαγωγής του GroupDocs.Viewer.

- **Άμεση διαχείριση δυαδικών δεδομένων** – Δεν απαιτούνται ενδιάμεσες μετατροπές· τα bytes του συνημμένου γράφονται ακριβώς όπως εμφανίζονται στο αρχικό αρχείο.  
- **Απόδοση** – Οι εγγραφές μέσω ροής ελαχιστοποιούν το φορτίο μνήμης, ειδικά για μεγάλα συνημμένα.  
- **Απλότητα** – Το API ενσωματώνεται καθαρά με το τυπικό Java I/O, καθιστώντας τον κώδικα εύκολο στην ανάγνωση και συντήρηση.

## Προαπαιτούμενα
- **Απαιτούμενες Βιβλιοθήκες και Εξαρτήσεις**: Προσθέστε τη βιβλιοθήκη GroupDocs.Viewer στο έργο σας (δείτε το απόσπασμα Maven παρακάτω).  
- **Ρύθμιση Περιβάλλοντος**: Ένα IDE Java (IntelliJ IDEA, Eclipse κ.λπ.) με εγκατεστημένο JDK 8+.  
- **Προαπαιτούμενες Γνώσεις**: Εξοικείωση με Java I/O, ειδικά `FileOutputStream`, και βασική χρήση Maven.

## Ρύθμιση GroupDocs.Viewer για Java
Για να ξεκινήσετε τη χρήση του API GroupDocs.Viewer στο έργο σας, πρέπει να το εγκαταστήσετε μέσω Maven. Προσθέστε την παρακάτω διαμόρφωση στο αρχείο `pom.xml`:

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

**Βήματα Απόκτησης Άδειας:**
- **Δωρεάν Δοκιμή**: Ξεκινήστε με μια δωρεάν δοκιμή για να εξερευνήσετε τις δυνατότητες.  
- **Προσωρινή Άδεια**: Αποκτήστε μια προσωρινή άδεια για παρατεταμένη περίοδο αξιολόγησης.  
- **Αγορά**: Για παραγωγική χρήση, θα χρειαστείτε μια αγορασμένη άδεια.

### Βασική Αρχικοποίηση και Ρύθμιση
Μόλις το GroupDocs.Viewer προστεθεί ως εξάρτηση στο έργο σας, αρχικοποιήστε το στην εφαρμογή Java. Δείτε πώς:

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document")) {
            // Your code to interact with the document goes here.
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Οδηγός Υλοποίησης

### Ανάκτηση Συνημμένων Χρησιμοποιώντας java file output stream
Ας αναλύσουμε πώς μπορείτε να ανακτήσετε συνημμένα χρησιμοποιώντας το GroupDocs.Viewer. Αυτή η δυνατότητα σας επιτρέπει να εξάγετε μεταδεδομένα για κάθε συνημμένο που υπάρχει στο έγγραφό σας.

#### Επισκόπηση
Η ανάκτηση συνημμένων περιλαμβάνει την πρόσβαση στη μέθοδο `getAttachments`, η οποία επιστρέφει μια λίστα αντικειμένων `Attachment` που περιέχουν λεπτομέρειες όπως το όνομα αρχείου και το μέγεθος. **Attachment** αντιπροσωπεύει ένα αρχείο ενσωματωμένο στο πηγαίο έγγραφο, όπως μια εικόνα ή ένα ενσωματωμένο αρχείο.

#### Βήματα Υλοποίησης
1. **Δημιουργία Αντικειμένου Viewer**  
   `Viewer` είναι η κύρια κλάση του GroupDocs.Viewer που φορτώνει και επεξεργάζεται έγγραφα για απόδοση και εξαγωγή. Αρχικοποιήστε την κλάση `Viewer` με τη διαδρομή προς το έγγραφό σας:

   ```java
   import com.groupdocs.viewer.Viewer;
   import com.groupdocs.viewer.examples.TestFiles;
   import com.groupdocs.viewer.results.Attachment;

   public class FeatureRetrieveAttachments {
       public static void main(String[] args) {
           try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
               // Proceed to retrieve attachments
           } catch (Exception e) {
               throw new RuntimeException(e);
           }
       }
   }
   ```

2. **Ανάκτηση Συνημμένων**  
   Χρησιμοποιήστε τη μέθοδο `getAttachments`:

   ```java
   List<Attachment> attachments = viewer.getAttachments();
   for (Attachment attachment : attachments) {
       System.out.println(attachment.getFileName());
   }
   ```

3. **Κατανόηση Παραμέτρων και Μεθόδων**  
   - `Viewer`: Δέχεται διαδρομή αρχείου ή ροή προς το έγγραφο.  
   - `getAttachments()`: Ανακτά μια λίστα συνημμένων αρχείων, παρέχοντας λεπτομέρειες όπως τα ονόματα.

### Αποθήκευση Συνημμένων Εγγράφου σε Κατάλογο
Τώρα που έχετε μάθει πώς να ανακτήσετε συνημμένα, ας τα αποθηκεύσουμε στον επιθυμητό σας κατάλογο χρησιμοποιώντας το API του GroupDocs.Viewer και **java file output stream**.

#### Επισκόπηση
Αυτή η δυνατότητα περιλαμβάνει την αποθήκευση κάθε ανακτημένου αρχείου συνημμένου σε έναν καθορισμένο κατάλογο εξόδου.

#### Βήματα Υλοποίησης
1. **Ορισμός Καταλόγου Εξόδου**  
   Ορίστε μια διαδρομή `outputDirectory` όπου θα αποθηκευτούν τα αρχεία:

   ```java
   import java.nio.file.Path;
   import java.nio.file.Paths;

   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   ```

2. **Αποθήκευση Συνημμένων**  
   Χρησιμοποιήστε έναν βρόχο για να αποθηκεύσετε κάθε συνημμένο χρησιμοποιώντας τη μέθοδο `saveAttachment`. **saveAttachment** γράφει το δυαδικό περιεχόμενο ενός `Attachment` σε ένα παρεχόμενο `OutputStream`.

   ```java
   try (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS)) {
       List<Attachment> attachments = viewer.getAttachments();
       
       for (Attachment attachment : attachments) {
           final Path file = outputDirectory.resolve(attachment.getFileName());
           try (FileOutputStream outputStream = new FileOutputStream(file.toFile())) {
               viewer.saveAttachment(attachment, outputStream);
           }
       }
   } catch (Exception e) {
       throw new RuntimeException(e);
   }
   ```

3. **Επεξήγηση Παραμέτρων και Μεθόδων**  
   - `saveAttachment`: Δέχεται ένα αντικείμενο `Attachment` και ένα file output stream για την αποθήκευση του συνημμένου.  
   - `FileOutputStream`: Διαχειρίζεται τη γραφή δεδομένων σε αρχεία χρησιμοποιώντας τη σημασιολογία του **java file output stream**.

## Πώς να Αποθηκεύσετε Συνημμένο Χρησιμοποιώντας java file output stream;
Φορτώστε κάθε αντικείμενο `Attachment`, ανοίξτε ένα `FileOutputStream` για το αρχείο προορισμού και ρέξτε τα bytes του συνημμένου απευθείας στο δίσκο. Αυτή η προσέγγιση γράφει το ακριβές δυαδικό φορτίο χωρίς μετασχηματισμό και εγγυάται ότι το αποθηκευμένο αρχείο ταιριάζει με το αρχικό συνημμένο byte‑for‑byte. Για μεγάλα συνημμένα, τυλίξτε τη ροή σε ένα `BufferedOutputStream` για να βελτιώσετε το throughput και να μειώσετε τις κλήσεις I/O. **BufferedOutputStream** κάνει buffering των εγγραφών για να μειώσει τον αριθμό των λειτουργιών I/O, βελτιώνοντας την απόδοση για μεγάλα αρχεία.

### Συνηθισμένα Προβλήματα και Λύσεις
- **Ελλιπείς Εξαρτήσεις**: Βεβαιωθείτε ότι όλες οι εξαρτήσεις Maven έχουν προστεθεί σωστά.  
- **Σφάλματα Διαδρομής Αρχείου**: Ελέγξτε ξανά τις διαδρομές για τα έγγραφα και τους καταλόγους εξόδου.  
- **Δικαιώματα Πρόσβασης**: Επαληθεύστε ότι η εφαρμογή σας διαθέτει τα απαραίτητα δικαιώματα ανάγνωσης/εγγραφής.

## Πρακτικές Εφαρμογές
Η χρήση του GroupDocs.Viewer σε Java μπορεί να είναι ανεκτίμητη σε διάφορα σενάρια:

1. **Πελάτες Email** – Αυτόματη εξαγωγή συνημμένων από αρχεία email για επεξεργασία ή αρχειοθέτηση.  
2. **Συστήματα Διαχείρισης Εγγράφων** – Βελτιώστε το DMS ανακτώντας και οργανώνοντας τα συνημμένα αρχεία.  
3. **Νομικά Τμήματα** – Εξαγωγή συνημμένων σχετικών με αποδείξεις από νομικά έγγραφα με ασφάλεια.

Οι δυνατότητες ενσωμάτωσης με CRM, ERP ή προσαρμοσμένες μηχανές ροής εργασίας μπορούν περαιτέρω να βελτιώσουν τις επιχειρηματικές διαδικασίες, καθιστώντας τη διαχείριση συνημμένων απρόσκοπτη σε όλα τα τμήματα.

## Σκέψεις Απόδοσης
Για τη βελτιστοποίηση της απόδοσης κατά τη χρήση του GroupDocs.Viewer:

- **Βελτιστοποίηση Διαχείρισης Αρχείων** – Χρησιμοποιήστε buffered streams για μεγάλα αρχεία και κλείστε άμεσα τους πόρους.  
- **Διαχείριση Μνήμης** – Απελευθερώστε άμεσα τις στιγμιότυπες `Viewer` (try‑with‑resources) για να αποφύγετε διαρροές μνήμης.  
- **Ποσοτικοποιημένο Όφελος** – Το GroupDocs.Viewer μπορεί να επεξεργαστεί έγγραφα έως 500 MB και να διαχειριστεί έως 200 συνημμένα ανά αρχείο, διατηρώντας τη χρήση μνήμης κάτω από 150 MB σε τυπική JVM 8 GB.

Ακολουθώντας τις βέλτιστες πρακτικές της Java θα ενισχύσετε σημαντικά την αποδοτικότητα της γραμμής επεξεργασίας συνημμένων σας.

## Συμπέρασμα
Τώρα έχετε εξερευνήσει πώς να ανακτήσετε και να αποθηκεύσετε συνημμένα εγγράφων χρησιμοποιώντας **java file output stream** με το GroupDocs.Viewer for Java. Αυτό το ισχυρό API απλοποιεί τη διαχείριση δεδομένων εγγράφων, καθιστώντας το ένα απαραίτητο εργαλείο για προγραμματιστές που εργάζονται με ψηφιακά έγγραφα. Για να εξερευνήσετε περαιτέρω τις δυνατότητες του GroupDocs.Viewer, πειραματιστείτε με άλλες λειτουργίες του—όπως η απόδοση σελίδων, η μετατροπή μορφών ή η εξαγωγή κειμένου. Εάν έχετε ερωτήσεις ή χρειάζεστε υποστήριξη, μη διστάσετε να επικοινωνήσετε μέσω των επίσημων πόρων.

## Συχνές Ερωτήσεις

**Ε: Πώς εγκαθιστώ το GroupDocs.Viewer στο έργο Java μου;**  
Α: Προσθέστε την εξάρτηση Maven που εμφανίζεται παραπάνω· το URL του αποθετηρίου και η έκδοση είναι ό,τι χρειάζεστε για ένα γρήγορο ξεκίνημα.

**Ε: Μπορεί το GroupDocs.Viewer να διαχειριστεί όλους τους τύπους εγγράφων;**  
Α: Υποστηρίζει πάνω από 50 μορφές εισόδου και εξόδου—συμπεριλαμβανομένων PDF, DOCX, PPTX, MSG και πολλών τύπων εικόνων—οπότε καλύπτονται τα περισσότερα κοινά επιχειρηματικά αρχεία.

**Ε: Τι κάνω αν αντιμετωπίσω σφάλματα κατά την αποθήκευση των συνημμένων;**  
Α: Επαληθεύστε ότι η διαδρομή εξόδου είναι σωστή, ότι ο φάκελος υπάρχει και ότι η διαδικασία σας έχει δικαιώματα εγγραφής. Επίσης, βεβαιωθείτε ότι χρησιμοποιείτε σωστά το `FileOutputStream` όπως φαίνεται.

**Ε: Απαιτείται άδεια για παραγωγική χρήση;**  
Α: Ναι, απαιτείται έγκυρη άδεια GroupDocs.Viewer για παραγωγικές εγκαταστάσεις. Μια δωρεάν δοκιμή είναι διαθέσιμη για αξιολόγηση.

**Ε: Λειτουργεί αυτή η προσέγγιση με μεγάλα αρχεία συνημμένων;**  
Α: Η χρήση του `java file output stream` με buffered I/O διαχειρίζεται αποδοτικά μεγάλα δυαδικά αρχεία· παρακολουθείτε τη χρήση μνήμης και σκεφτείτε τη ροή σε τμήματα για αρχεία μεγαλύτερα από 200 MB.

**Τελευταία Ενημέρωση:** 2026-06-30  
**Δοκιμάστηκε Με:** GroupDocs.Viewer 25.2  
**Συγγραφέας:** GroupDocs  

## Σχετικά Μαθήματα

- [Πώς να Ανακτήσετε Συνημμένα και να Εκτυπώσετε Συνημμένα Εγγράφου με το GroupDocs.Viewer for Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Απόδοση Συνημμένων Εγγράφου σε HTML Χρησιμοποιώντας το GroupDocs.Viewer Java: Οδηγός Βήμα‑Βήμα](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)
- [Προσαρμοσμένος Διαχειριστής Απόδοσης Java – Οδηγός GroupDocs Viewer](/viewer/java/custom-rendering/)