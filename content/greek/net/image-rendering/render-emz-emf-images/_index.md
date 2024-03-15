---
title: Απόδοση εικόνων EMZ και EMF
linktitle: Απόδοση εικόνων EMZ και EMF
second_title: GroupDocs.Viewer .NET API
description: Μάθετε πώς να αποδίδετε εικόνες EMZ και EMF σε διάφορες μορφές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Εύκολο στην παρακολούθηση σεμινάριο για προγραμματιστές.
type: docs
weight: 14
url: /el/net/image-rendering/render-emz-emf-images/
---
## Εισαγωγή

Το GroupDocs.Viewer για .NET είναι ένα ισχυρό API απόδοσης εγγράφων που επιτρέπει στους προγραμματιστές να εμφανίζουν διάφορους τύπους εγγράφων, συμπεριλαμβανομένων εικόνων EMZ (Enhanced Metafile των Windows) και EMF (Enhanced Metafile), στις εφαρμογές τους .NET. Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να αποδίδουμε εικόνες EMZ και EMF σε διαφορετικές μορφές όπως HTML, JPG, PNG και PDF χρησιμοποιώντας το GroupDocs.Viewer για .NET.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  GroupDocs.Viewer για .NET: Μπορείτε να κάνετε λήψη της βιβλιοθήκης από[εδώ](https://releases.groupdocs.com/viewer/net/).
2. Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε δημιουργήσει ένα συμβατό περιβάλλον ανάπτυξης για την ανάπτυξη .NET.
3. Δείγματα εικόνων EMZ/EMF: Έχετε διαθέσιμα δείγματα εικόνων EMZ και EMF για απόδοση.

## Εισαγωγή χώρων ονομάτων

Πριν βουτήξουμε στον κώδικα, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα σε μια μορφή οδηγού βήμα προς βήμα:

## Απόδοση εικόνων EMZ/EMF σε HTML

### Βήμα 1: Ορισμός καταλόγου εξόδου:
```csharp
string outputDirectory = "Your Document Directory";
```
 Αντικαθιστώ`"Your Document Directory"`με τη διαδρομή όπου θέλετε να αποθηκεύσετε το αποδοθέν αρχείο HTML.

### Βήμα 2: Ορισμός μορφής διαδρομής αρχείου σελίδας:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Αυτό θα καθορίσει τη μορφή διαδρομής αρχείου για το αποδοθέν αρχείο HTML.

### Βήμα 3: Απόδοση σε HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Αυτός ο κώδικας αρχικοποιεί το`Viewer` αντικείμενο με το δείγμα εικόνας EMZ και το αποδίδει σε μορφή HTML χρησιμοποιώντας καθορισμένες επιλογές.

## Απόδοση εικόνων EMZ/EMF σε JPG, PNG και PDF

Επαναλάβετε τα παρακάτω βήματα για απόδοση σε μορφές JPG, PNG και PDF:

### Βήμα 1: Ορισμός μορφής διαδρομής αρχείου σελίδας:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Προσαρμόστε το όνομα και την επέκταση αρχείου σύμφωνα με την επιθυμητή μορφή εξόδου (`jpg`, `png` , ή`pdf`).

### Βήμα 2: Απόδοση σε αντίστοιχη μορφή:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Προσαρμόστε τις επιλογές ανάλογα με τη μορφή εξόδου (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Αντικαθιστώ`JpgViewOptions` με`PngViewOptions` ή`PdfViewOptions` με βάση την επιθυμητή μορφή εξόδου.

## συμπέρασμα

Συμπερασματικά, το GroupDocs.Viewer για .NET παρέχει μια απρόσκοπτη λύση για την απόδοση εικόνων EMZ και EMF σε διάφορες μορφές σε εφαρμογές .NET. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, οι προγραμματιστές μπορούν να ενσωματώσουν αβίαστα τις δυνατότητες απόδοσης εγγράφων στις εφαρμογές τους.

## Συχνές ερωτήσεις

### Ε: Μπορεί το GroupDocs.Viewer να αποδώσει άλλες μορφές εγγράφων εκτός από εικόνες EMZ και EMF;
Α: Ναι, το GroupDocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, συμπεριλαμβανομένων των PDF, DOCX, PPTX, XLSX και άλλων.

### Ε: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το GroupDocs.Viewer για .NET;
 Α: Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή[εδώ](https://releases.groupdocs.com/).

### Ε: Το GroupDocs.Viewer προσφέρει υποστήριξη για προγραμματιστές;
 Α: Ναι, το GroupDocs παρέχει υποστήριξη μέσω του[δικαστήριο](https://forum.groupdocs.com/c/viewer/9) όπου οι προγραμματιστές μπορούν να κάνουν ερωτήσεις και να ζητήσουν βοήθεια.

### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το GroupDocs.Viewer για .NET;
 Α: Ναι, οι προσωρινές άδειες είναι διαθέσιμες για αγορά[εδώ](https://purchase.groupdocs.com/temporary-license/).

### Ε: Πού μπορώ να βρω λεπτομερή τεκμηρίωση για το GroupDocs.Viewer για .NET;
 Α: Μπορείτε να ανατρέξετε στην τεκμηρίωση[εδώ](https://reference.groupdocs.com/viewer/net/)για ολοκληρωμένη καθοδήγηση σχετικά με τη χρήση του API.