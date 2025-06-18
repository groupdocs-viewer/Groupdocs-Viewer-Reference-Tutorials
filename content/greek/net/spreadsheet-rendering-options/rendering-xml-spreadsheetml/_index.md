---
"description": "Εξερευνήστε την απρόσκοπτη απόδοση αρχείων XML SpreadSheetML σε διάφορες μορφές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ενσωματώστε τα εύκολα στις εφαρμογές σας."
"linktitle": "Απόδοση XML SpreadSheetML"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση XML SpreadSheetML"
"url": "/el/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
---

# Απόδοση XML SpreadSheetML

## Εισαγωγή
Καλώς ορίσατε στον κόσμο του GroupDocs.Viewer για .NET! Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στην εύκολη απόδοση αρχείων XML SpreadSheetML χρησιμοποιώντας το GroupDocs.Viewer, μια ισχυρή βιβλιοθήκη .NET. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτός ο οδηγός βήμα προς βήμα θα σας βοηθήσει να ενσωματώσετε εύκολα την απόδοση XML SpreadSheetML στις εφαρμογές σας.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:
- Ένα περιβάλλον ανάπτυξης με υποστήριξη .NET.
- Εγκατεστημένο το GroupDocs.Viewer για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε. [εδώ](https://releases.groupdocs.com/viewer/net/).
- Βασική κατανόηση του προγραμματισμού C#.
## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στο έργο σας σε C#. Αυτό διασφαλίζει ότι έχετε πρόσβαση στις λειτουργίες που παρέχονται από το GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Βήμα 1: Ρύθμιση του καταλόγου εγγράφων σας
Ορίστε τη διαδρομή προς τον κατάλογο εγγράφων όπου θα αποθηκευτεί το αποτέλεσμα.
```csharp
string outputDirectory = "Your Document Directory";
```
## Βήμα 2: Καθορισμός διαδρομών αρχείων εξόδου
Ορίστε τις πλήρεις διαδρομές για τα αρχεία εξόδου HTML, JPG, PNG και PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Βήμα 3: Καθορισμός επιλογών φόρτωσης
Καθορίστε ρητά τον τύπο αρχείου ως Excel 2003 XML SpreadSheetML για να το αποδώσετε με ακρίβεια.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Βήμα 4: Απόδοση σε HTML πολλαπλών σελίδων
Χρησιμοποιήστε τις επιλογές προβολής HTML για να αποδώσετε το αρχείο XML SpreadSheetML σε ένα έγγραφο HTML πολλών σελίδων.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 5: Απόδοση σε JPG
Αποδώστε το αρχείο XML SpreadSheetML σε εικόνα JPG χρησιμοποιώντας τις καθορισμένες επιλογές.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 6: Απόδοση σε PNG
Ομοίως, μετατρέψτε το αρχείο σε εικόνα PNG με τις καθορισμένες επιλογές.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 7: Απόδοση σε PDF
Τέλος, μετατρέψτε το αρχείο XML SpreadSheetML σε έγγραφο PDF χρησιμοποιώντας τις καθορισμένες επιλογές.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Σύναψη
Συγχαρητήρια! Μάθατε με επιτυχία πώς να αποδίδετε αρχεία XML SpreadSheetML χρησιμοποιώντας το GroupDocs.Viewer για .NET. Βελτιώστε τις δυνατότητες προβολής εγγράφων σας εξερευνώντας περισσότερες δυνατότητες και επιλογές που παρέχονται από αυτήν την ευέλικτη βιβλιοθήκη.
## Συχνές ερωτήσεις
### Είναι το GroupDocs.Viewer συμβατό με άλλες μορφές αρχείων;
Ναι, το GroupDocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, όπως PDF, Word, Excel και άλλα.
### Μπορώ να προσαρμόσω την εμφάνιση των εγγράφων που αποδίδονται;
Απολύτως! Το GroupDocs.Viewer προσφέρει διάφορες επιλογές προσαρμογής, επιτρέποντάς σας να προσαρμόσετε την έξοδο στις συγκεκριμένες ανάγκες σας.
### Πού μπορώ να βρω επιπλέον υποστήριξη και πόρους;
Επισκεφθείτε το [Φόρουμ GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) για υποστήριξη από την κοινότητα και να εξερευνήσετε το [απόδειξη με έγγραφα](https://tutorials.groupdocs.com/viewer/net/) για λεπτομερείς πληροφορίες.
### Υπάρχει διαθέσιμη δωρεάν δοκιμαστική περίοδος;
Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμαστική περίοδο [εδώ](https://releases.groupdocs.com/).
### Πώς μπορώ να αποκτήσω προσωρινή άδεια οδήγησης;
Μπορείτε να λάβετε προσωρινή άδεια [εδώ](https://purchase.groupdocs.com/temporary-license/).