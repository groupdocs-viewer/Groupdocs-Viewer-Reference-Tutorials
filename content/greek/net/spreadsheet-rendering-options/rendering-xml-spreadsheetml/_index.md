---
title: Απόδοση XML SpreadSheetML
linktitle: Απόδοση XML SpreadSheetML
second_title: GroupDocs.Viewer .NET API
description: Εξερευνήστε την απρόσκοπτη απόδοση αρχείων XML SpreadSheetML σε διάφορες μορφές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ενσωματωθείτε χωρίς κόπο στις εφαρμογές σας.
weight: 16
url: /el/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---
## Εισαγωγή
Καλώς ήρθατε στον κόσμο του GroupDocs.Viewer για .NET! Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στην απόδοση αρχείων XML SpreadSheetML με ευκολία χρησιμοποιώντας το GroupDocs.Viewer, μια ισχυρή βιβλιοθήκη .NET. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτός ο οδηγός βήμα προς βήμα θα σας βοηθήσει να ενσωματώσετε αβίαστα την απόδοση XML SpreadSheetML στις εφαρμογές σας.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:
- Ένα περιβάλλον ανάπτυξης με υποστήριξη .NET.
-  Εγκαταστάθηκε το GroupDocs.Viewer για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.groupdocs.com/viewer/net/).
- Βασική κατανόηση του προγραμματισμού C#.
## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στο έργο σας C#. Αυτό διασφαλίζει ότι έχετε πρόσβαση στις λειτουργίες που παρέχονται από το GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων σας
Καθορίστε τη διαδρομή προς τον κατάλογο των εγγράφων σας όπου θα αποθηκευτεί η έξοδος.
```csharp
string outputDirectory = "Your Document Directory";
```
## Βήμα 2: Καθορίστε τις διαδρομές αρχείου εξόδου
Ρυθμίστε τις πλήρεις διαδρομές για τα αρχεία εξόδου HTML, JPG, PNG και PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Βήμα 3: Καθορίστε τις επιλογές φόρτωσης
Καθορίστε ρητά τον τύπο αρχείου ως Excel 2003 XML SpreadSheetML για να το αποδώσετε με ακρίβεια.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Βήμα 4: Απόδοση σε HTML πολλών σελίδων
Χρησιμοποιήστε τις επιλογές προβολής HTML για να αποδώσετε το αρχείο XML SpreadSheetML σε ένα πολυσέλιδο έγγραφο HTML.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 5: Απόδοση σε JPG
Αποδώστε το αρχείο XML SpreadSheetML σε μια εικόνα JPG χρησιμοποιώντας τις καθορισμένες επιλογές.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 6: Απόδοση σε PNG
Ομοίως, αποδώστε το αρχείο σε εικόνα PNG με τις καθορισμένες επιλογές.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 7: Απόδοση σε PDF
Τέλος, αποδώστε το αρχείο XML SpreadSheetML σε ένα έγγραφο PDF χρησιμοποιώντας τις καθορισμένες επιλογές.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## συμπέρασμα
Συγχαρητήρια! Έχετε μάθει με επιτυχία πώς να αποδίδετε αρχεία XML SpreadSheetML χρησιμοποιώντας το GroupDocs.Viewer για .NET. Βελτιώστε τις δυνατότητες προβολής των εγγράφων σας εξερευνώντας περισσότερες δυνατότητες και επιλογές που παρέχονται από αυτήν την ευέλικτη βιβλιοθήκη.
## Συχνές ερωτήσεις
### Είναι το GroupDocs.Viewer συμβατό με άλλες μορφές αρχείων;
Ναι, το GroupDocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, συμπεριλαμβανομένων των PDF, Word, Excel και άλλων.
### Μπορώ να προσαρμόσω την εμφάνιση των αποδοθέντων εγγράφων;
Απολύτως! Το GroupDocs.Viewer προσφέρει διάφορες επιλογές προσαρμογής, επιτρέποντάς σας να προσαρμόσετε το αποτέλεσμα στις συγκεκριμένες ανάγκες σας.
### Πού μπορώ να βρω πρόσθετη υποστήριξη και πόρους;
 Επισκέψου το[GroupDocs.Viewer φόρουμ](https://forum.groupdocs.com/c/viewer/9) για υποστήριξη της κοινότητας και να εξερευνήσετε το[τεκμηρίωση](https://tutorials.groupdocs.com/viewer/net/)για αναλυτικές πληροφορίες.
### Υπάρχει δωρεάν δοκιμή διαθέσιμη;
 Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή[εδώ](https://releases.groupdocs.com/).
### Πώς μπορώ να αποκτήσω προσωρινή άδεια;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.groupdocs.com/temporary-license/).