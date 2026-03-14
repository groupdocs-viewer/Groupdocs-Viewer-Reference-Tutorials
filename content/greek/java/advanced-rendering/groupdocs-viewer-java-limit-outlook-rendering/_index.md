---
date: '2026-02-21'
description: Μάθετε πώς να ορίζετε το μέγιστο αριθμό στοιχείων ανά φάκελο κατά την
  απόδοση αρχείων Outlook με το GroupDocs.Viewer για Java, βελτιώνοντας την απόδοση
  για μεγάλα αρχεία PST/OST.
keywords:
- GroupDocs.Viewer Java
- Outlook item rendering
- PST file rendering
title: Πώς να ορίσετε το μέγιστο αριθμό στοιχείων ανά φάκελο στην απόδοση Outlook
  με το GroupDocs.Viewer για Java
type: docs
url: /el/java/advanced-rendering/groupdocs-viewer-java-limit-outlook-rendering/
weight: 1
---

# Περιορισμός Απόδοσης Στοιχείων Outlook σε Java χρησιμοποιώντας το GroupDocs.Viewer

Η διαχείριση τεράστιων αρχείων δεδομένων Outlook (PST ή OST) μπορεί γρήγορα να γίνει εμπόδιο στην απόδοση. Σε αυτόν τον οδηγό θα ανακαλύψετε πώς να **set max items** ανά φάκελο κατά την απόδοση με το GroupDocs.Viewer for Java, ώστε να επεξεργάζεστε μόνο τα δεδομένα που χρειάζεστε πραγματικά. Εφαρμόζοντας την τεχνική **limit items per folder**, η εφαρμογή σας παραμένει ανταποκρινόμενη ακόμη και με γιγαμπάιτ δεδομένων email.

![Περιορισμός Απόδοσης Στοιχείων Outlook με το GroupDocs.Viewer για Java](/viewer/advanced-rendering/limit-outlook-item-rendering-java.png)

### Τι Θα Μάθετε
- Ρύθμιση του GroupDocs.Viewer για Java  
- Διαμόρφωση της βιβλιοθήκης για **set max items** ανά φάκελο σε αρχεία Outlook  
- Πραγματικά σενάρια όπου ο περιορισμός στοιχείων ανά φάκελο βελτιώνει την ταχύτητα και μειώνει τη χρήση μνήμης  

## Γρήγορες Απαντήσεις
- **What does “set max items per folder” do?** Περιορίζει την απόδοση σε έναν ορισμένο αριθμό στοιχείων email μέσα σε κάθε φάκελο Outlook.  
- **Why limit Outlook items?** Για να μειωθεί ο χρόνος επεξεργασίας και η κατανάλωση μνήμης για μεγάλα γραμματοκιβώτια.  
- **Which version supports this feature?** GroupDocs.Viewer 25.2 και νεότερες.  
- **Do I need a license?** Ναι, απαιτείται δοκιμαστική ή αγορασμένη άδεια για παραγωγική χρήση.  
- **Can I change the limit at runtime?** Απόλυτα – απλώς τροποποιήστε την τιμή `setMaxItemsInFolder` πριν από την απόδοση.

## Πώς να ορίσετε max items per folder στην απόδοση Outlook
Παρακάτω θα βρείτε έναν βήμα‑βήμα οδηγό που εξηγεί **why** μπορεί να θέλετε να περιορίσετε τα στοιχεία Outlook, **what** κάνει η ρύθμιση, και **how** να την διαμορφώσετε στο έργο σας Java.

### Τι είναι το “set max items per folder”;
Η επιλογή **set max items** λέει στον viewer να σταματήσει αφού έχει αποδώσει έναν συγκεκριμένο αριθμό στοιχείων σε κάθε φάκελο. Αυτό είναι ιδιαίτερα χρήσιμο όταν χρειάζεστε μόνο μια προεπισκόπηση των πρόσφατων email ή όταν δημιουργείτε αναφορές που δεν απαιτούν ολόκληρο το γραμματοκιβώτιο.

### Γιατί να χρησιμοποιήσετε την προσέγγιση limit items per folder;
- **Performance:** Ταχύτεροι χρόνοι απόδοσης και χαμηλότερη χρήση CPU.  
- **Scalability:** Διαχείριση μεγαλύτερων γραμματοκιβωτίων χωρίς εξάντληση μνήμης JVM.  
- **Flexibility:** Προσαρμογή του ορίου βάσει προτιμήσεων χρήστη ή δυνατοτήτων συσκευής.  

## Προαπαιτούμενα
Βεβαιωθείτε ότι έχετε τα παρακάτω πριν ξεκινήσετε:

### Απαιτούμενες Βιβλιοθήκες και Εξαρτήσεις
1. **Java Development Kit (JDK)** – Εγκαταστήστε JDK 8 ή νεότερο.  
2. **GroupDocs.Viewer for Java** – Προσθέστε το ως εξάρτηση στο έργο σας.

### Απαιτήσεις Ρύθμισης Περιβάλλοντος
- Ένα κατάλληλο IDE όπως IntelliJ IDEA, Eclipse ή NetBeans.  
- Maven εγκατεστημένο εάν διαχειρίζεστε εξαρτήσεις μέσω αυτού.

### Προαπαιτούμενες Γνώσεις
- Βασική κατανόηση του προγραμματισμού Java και της διαχείρισης αρχείων.  
- Εξοικείωση με έργα Maven είναι επωφελής αλλά όχι απαραίτητη.

## Ρύθμιση του GroupDocs.Viewer για Java
Ρυθμίστε το GroupDocs.Viewer στο έργο σας χρησιμοποιώντας Maven:

**Maven Configuration:**
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

### Βήματα Απόκτησης Άδειας
- **Free Trial**: Κατεβάστε μια δωρεάν δοκιμή από [GroupDocs](https://releases.groupdocs.com/viewer/java/) για να εξερευνήσετε τις δυνατότητες της βιβλιοθήκης.  
- **Temporary License**: Αποκτήστε προσωρινή άδεια για πλήρη πρόσβαση χωρίς περιορισμούς αξιολόγησης στο [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Purchase**: Για μακροπρόθεσμη χρήση, σκεφτείτε να αγοράσετε άδεια από τη [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Βασική Αρχικοποίηση και Ρύθμιση
Μόλις το Maven είναι διαμορφωμένο, αρχικοποιήστε το GroupDocs.Viewer στην εφαρμογή Java δημιουργώντας το αντικείμενο viewer. Αυτό σας επιτρέπει να φορτώνετε και να αποδίδετε έγγραφα.

## Οδηγός Υλοποίησης

### Περιορισμός Στοιχείων που Αποδίδονται από Αρχεία Outlook
Αυτή η ενότητα εξηγεί πώς να περιορίσετε τα στοιχεία που αποδίδονται από αρχεία δεδομένων Outlook χρησιμοποιώντας το GroupDocs.Viewer for Java.

#### Επισκόπηση
Με τη διαμόρφωση συγκεκριμένων επιλογών, μπορείτε να περιορίσετε την απόδοση σε έναν ορισμένο αριθμό στοιχείων ανά φάκελο. Αυτή η δυνατότητα βελτιώνει την απόδοση και την αποδοτικότητα όταν εργάζεστε με μεγάλα σύνολα email.

**Βήμα 1: Ρύθμιση Διαδρομής Καταλόγου Εξόδου**
```java
Path outputDirectory = Utils.getOutputDirectoryPath("LimitCountOfItemsToRender");
```
Αυτός ο κώδικας ορίζει τον κατάλογο όπου θα αποθηκευτούν τα παραγόμενα HTML αρχεία. Αντικαταστήστε το `"LimitCountOfItemsToRender"` με το επιθυμητό όνομα διαδρομής.

**Βήμα 2: Ορισμός Μορφής Διαδρομής Αρχείου για Σελίδες HTML**
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
Δημιουργήστε μια συνεπή μορφή ονομασίας για τις HTML σελίδες που παράγονται κατά την απόδοση, εξασφαλίζοντας εύκολη πρόσβαση και διαχείριση.

**Βήμα 3: Διαμόρφωση HtmlViewOptions με Ενσωματωμένους Πόρους**
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```
Αυτή η επιλογή καθορίζει πώς αποδίδονται τα έγγραφα με ενσωματωμένους πόρους, επιτρέποντας καλύτερη ενσωμάτωση εικόνων και στυλ.

**Βήμα 4: Ρύθμιση Outlook Options για Περιορισμό Στοιχείων ανά Φάκελο**
```java
viewOptions.getOutlookOptions().setMaxItemsInFolder(3); // Render only the first 3 items in each folder
```
Εδώ, **set max items** είναι τρία. Προσαρμόστε τον αριθμό βάσει των απαιτήσεών σας για το σενάριο **limit items per folder**.

**Βήμα 5: Φόρτωση και Απόδοση του Εγγράφου**
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST)) {
    viewer.view(viewOptions); // Execute rendering with specified options
}
```
Χρησιμοποιήστε την κλάση `Viewer` για να φορτώσετε ένα αρχείο OST και να το αποδώσετε σύμφωνα με τις καθορισμένες επιλογές προβολής. Η δήλωση try‑with‑resources εξασφαλίζει ότι οι πόροι κλείνουν σωστά μετά τη χρήση.

### Συμβουλές Επίλυσης Προβλημάτων
- Βεβαιωθείτε ότι όλες οι διαδρομές και οι φάκελοι υπάρχουν πριν εκτελέσετε τον κώδικά σας.  
- Επαληθεύστε ότι οι εξαρτήσεις του GroupDocs.Viewer έχουν επιλυθεί σωστά από το Maven.  
- Ελέγξτε για τυχόν εξαιρέσεις κατά την απόδοση, που μπορεί να υποδεικνύουν προβλήματα με μορφές αρχείων ή δικαιώματα.

## Πρακτικές Εφαρμογές
1. **Email Archiving** – Ο περιορισμός απόδοσης στοιχείων είναι ιδανικός για εφαρμογές που εστιάζουν στην αρχειοθέτηση συγκεκριμένων email αντί ολόκληρων συνόλων δεδομένων.  
2. **Data Migration** – Κατά τη μεταφορά δεδομένων μεταξύ συστημάτων, αποδώστε μόνο τα απαραίτητα στοιχεία για βελτιστοποίηση απόδοσης και μείωση του χρόνου επεξεργασίας.  
3. **Custom Reporting** – Δημιουργήστε αναφορές αποδίδοντας επιλεκτικά το απαιτούμενο περιεχόμενο email χωρίς να φορτώνετε ολόκληρους φακέλους.

## Σκέψεις Απόδοσης
### Συμβουλές για Βελτιστοποίηση Απόδοσης
- Περιορίστε τον αριθμό στοιχείων ανά φάκελο για μείωση της χρήσης μνήμης.  
- Χρησιμοποιήστε ενσωματωμένους πόρους αποδοτικά ώστε να αποφύγετε επιπλέον κλήσεις δικτύου κατά την απόδοση.

### Οδηγίες Χρήσης Πόρων
- Παρακολουθείτε τη μνήμη JVM και προσαρμόζετε τις ρυθμίσεις βάσει του μεγέθους των αρχείων Outlook που επεξεργάζεστε.

### Καλές Πρακτικές για Διαχείριση Μνήμης Java
- Εκμεταλλευτείτε το try‑with‑resources για αυτόματη διαχείριση πόρων.  
- Προφίλτε την εφαρμογή σας για να εντοπίσετε σημεία συμφόρησης που σχετίζονται με τη διαχείριση μεγάλων αρχείων.

## Συνηθισμένα Πίπτα και Πώς να τα Αποφύγετε
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| No output files generated | Output directory path is incorrect or missing permissions | Verify `outputDirectory` exists and is writable |
| Rendering stops after a few items | `setMaxItemsInFolder` set too low | Increase the limit or make it configurable |
| OutOfMemoryError on large PST | Default memory settings insufficient | Increase JVM heap (`-Xmx`) and keep the limit low |

## Συμπέρασμα
Σε αυτό το σεμινάριο, μάθατε πώς να **set max items per folder** σε αρχεία δεδομένων Outlook χρησιμοποιώντας το GroupDocs.Viewer for Java. Ακολουθώντας τα βήματα και εφαρμόζοντας τις συμβουλές απόδοσης, μπορείτε να δημιουργήσετε αποδοτικές εφαρμογές προσαρμοσμένες στις συγκεκριμένες ανάγκες σας.

### Επόμενα Βήματα
- Εξερευνήστε πρόσθετες δυνατότητες του GroupDocs.Viewer ανατρέχοντας στην [official documentation](https://docs.groupdocs.com/viewer/java/).  
- Πειραματιστείτε με διαφορετικές επιλογές απόδοσης για να βρείτε την καλύτερη διαμόρφωση για τις απαιτήσεις της εφαρμογής σας.

Έτοιμοι να το δοκιμάσετε; Ξεκινήστε να εφαρμόζετε αυτή τη λύση στα έργα σας σήμερα και παρατηρήστε βελτιωμένη αποδοτικότητα άμεσα.

## Συχνές Ερωτήσεις

**Q: What is GroupDocs.Viewer Java used for?**  
A: Είναι μια ευέλικτη βιβλιοθήκη σχεδιασμένη για την απόδοση διαφόρων μορφών εγγράφων, συμπεριλαμβανομένων των αρχείων δεδομένων Outlook, σε HTML ή μορφές εικόνας.

**Q: How do I obtain a free trial of GroupDocs.Viewer?**  
A: Επισκεφθείτε το [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) για πρόσβαση και επιλογές λήψης.

**Q: Can I limit item rendering in PST files as well?**  
A: Ναι, η ίδια διαμόρφωση ισχύει και για τα αρχεία OST και PST.

**Q: What should I do if my application is running slow during rendering?**  
A: Ελέγξτε τα όρια στοιχείων και τις ρυθμίσεις πόρων· σκεφτείτε τη βελτιστοποίηση πρακτικών διαχείρισης μνήμης.

**Q: Where can I find support for GroupDocs.Viewer issues?**  
A: Για βοήθεια, ελέγξτε το [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9).

## Πρόσθετοι Πόροι
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs.Viewer for Java](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-02-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs