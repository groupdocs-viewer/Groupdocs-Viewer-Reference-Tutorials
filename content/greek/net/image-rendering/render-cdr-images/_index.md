---
title: Απόδοση εικόνων CDR
linktitle: Απόδοση εικόνων CDR
second_title: GroupDocs.Viewer .NET API
description: Μάθετε πώς να αποδίδετε εικόνες CDR σε HTML, JPG, PNG και PDF χρησιμοποιώντας το GroupDocs.Viewer για .NET. Μετατρέψτε εύκολα αρχεία CorelDRAW με αυτό το σεμινάριο.
weight: 12
url: /el/net/image-rendering/render-cdr-images/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία απόδοσης εικόνων CDR (CorelDRAW) χρησιμοποιώντας το GroupDocs.Viewer για .NET. Το CDR είναι μια μορφή αρχείου που σχετίζεται κυρίως με το CorelDRAW, ένα διανυσματικό πρόγραμμα επεξεργασίας γραφικών. Με το GroupDocs.Viewer, μπορείτε εύκολα να μετατρέψετε αρχεία CDR σε διάφορες μορφές όπως HTML, JPG, PNG και PDF.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  GroupDocs.Viewer για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει το GroupDocs.Viewer για .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.groupdocs.com/viewer/net/).
2. Κατάλογος εγγράφων: Προετοιμάστε έναν κατάλογο όπου θέλετε να αποθηκεύσετε τις εικόνες που αποδίδονται.
3. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# είναι απαραίτητη για την κατανόηση των παραδειγμάτων κώδικα.
## Εισαγωγή χώρων ονομάτων
Πριν βουτήξετε στα παραδείγματα κώδικα, εισαγάγετε τους απαραίτητους χώρους ονομάτων στο αρχείο C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα:
## Απόδοση σε HTML
1. Καθορίστε τον κατάλογο εξόδου όπου θέλετε να αποθηκεύσετε τα αποδοθέντα αρχεία HTML:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Καθορίστε τη μορφή διαδρομής αρχείου για αρχεία HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Χρησιμοποιήστε την κλάση Viewer για απόδοση του αρχείου CDR σε HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Απόδοση σε JPG
1. Καθορίστε τη μορφή διαδρομής αρχείου για αρχεία JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Χρησιμοποιήστε την κλάση Viewer για απόδοση του αρχείου CDR σε JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Απόδοση σε PNG
1. Καθορίστε τη μορφή διαδρομής αρχείου για αρχεία PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Χρησιμοποιήστε την κλάση Viewer για να αποδώσετε το αρχείο CDR σε PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Απόδοση σε PDF
1. Καθορίστε τη μορφή διαδρομής αρχείου για PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Χρησιμοποιήστε την κλάση Viewer για να αποδώσετε το αρχείο CDR σε PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  Προαιρετικά, μπορείτε να καθορίσετε επιλογές απόδοσης ή να αποδώσετε συγκεκριμένες σελίδες περνώντας πρόσθετες παραμέτρους στο`viewer.View()` μέθοδος.
## συμπέρασμα
Η απόδοση εικόνων CDR σε διάφορες μορφές όπως HTML, JPG, PNG και PDF χρησιμοποιώντας το GroupDocs.Viewer για .NET είναι μια απλή διαδικασία. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να μετατρέψετε αποτελεσματικά αρχεία CDR σε διαφορετικές μορφές με βάση τις απαιτήσεις σας.
## Συχνές ερωτήσεις
### Είναι το GroupDocs.Viewer για .NET συμβατό με όλες τις εκδόσεις αρχείων CDR;
Το GroupDocs.Viewer για .NET υποστηρίζει την απόδοση αρχείων CDR που δημιουργούνται από διαφορετικές εκδόσεις του CorelDRAW.
### Μπορώ να προσαρμόσω την έξοδο των rendered αρχείων;
Ναι, το GroupDocs.Viewer για .NET παρέχει διάφορες επιλογές για την προσαρμογή της εξόδου, όπως προσαρμογή ποιότητας εικόνας, ρύθμιση υδατογραφήματος κ.λπ.
### Απαιτεί το GroupDocs.Viewer για .NET εξωτερικές εξαρτήσεις;
Όχι, το GroupDocs.Viewer για .NET είναι μια αυτόνομη βιβλιοθήκη και δεν απαιτεί εξωτερικές εξαρτήσεις για την απόδοση εγγράφων.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το GroupDocs.Viewer για .NET;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του GroupDocs.Viewer για .NET από[εδώ](https://releases.groupdocs.com/).
### Πού μπορώ να λάβω υποστήριξη για το GroupDocs.Viewer για .NET;
 Μπορείτε να λάβετε υποστήριξη από το φόρουμ κοινότητας GroupDocs.Viewer[εδώ](https://forum.groupdocs.com/c/viewer/9).