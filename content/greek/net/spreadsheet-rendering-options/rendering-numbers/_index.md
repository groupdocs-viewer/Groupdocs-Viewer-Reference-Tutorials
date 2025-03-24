---
title: Απόδοση αριθμών
linktitle: Απόδοση αριθμών
second_title: GroupDocs.Viewer .NET API
description: Εξερευνήστε τη δύναμη του Groupdocs.Viewer για .NET στην απρόσκοπτη απόδοση των αρχείων Numbers. Μετατρέψτε σε HTML, JPG, PNG και PDF χωρίς κόπο.
weight: 15
url: /el/net/spreadsheet-rendering-options/rendering-numbers/
---

# Απόδοση αριθμών

## Εισαγωγή
Καλώς ήρθατε σε αυτόν τον αναλυτικό οδηγό για την απόδοση αρχείων Numbers χρησιμοποιώντας το Groupdocs.Viewer για .NET. Είτε είστε έμπειρος προγραμματιστής είτε αρχάριος, αυτός ο οδηγός θα σας καθοδηγήσει στη διαδικασία μετατροπής εγγράφων Numbers σε διάφορες μορφές. Το Groupdocs.Viewer για .NET είναι ένα ισχυρό εργαλείο που σας επιτρέπει να ενσωματώνετε απρόσκοπτα τις δυνατότητες προβολής εγγράφων στις εφαρμογές σας .NET.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Γνώση εργασίας για ανάπτυξη C# και .NET.
-  Εγκαταστάθηκε το Groupdocs.Viewer για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε[εδώ](https://releases.groupdocs.com/viewer/net/).
- Διαδρομή καταλόγου εγγράφου όπου θα αποθηκευτούν τα αρχεία εξόδου.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, βεβαιωθείτε ότι εισάγετε τους απαραίτητους χώρους ονομάτων για να χρησιμοποιήσετε τη βιβλιοθήκη Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Βήμα 1: Ρύθμιση καταλόγου εξόδου
Πριν ξεκινήσετε την απόδοση, ορίστε τον κατάλογο εξόδου όπου θα αποθηκευτούν τα αρχεία που έχουν μετατραπεί. Αντικαταστήστε το "Ο Κατάλογος Εγγράφων σας" με την πραγματική διαδρομή:
```csharp
string outputDirectory = "Your Document Directory";
```
## Βήμα 2: Απόδοση σε HTML πολλών σελίδων
Χρησιμοποιήστε τον ακόλουθο κώδικα για να μετατρέψετε το αρχείο Numbers σε πολυσέλιδο HTML:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 3: Απόδοση σε JPG
Μετατρέψτε το αρχείο Numbers σε μορφή JPG με τον ακόλουθο κώδικα:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 4: Απόδοση σε PNG
Μετατρέψτε το αρχείο Numbers σε μορφή PNG χρησιμοποιώντας τον ακόλουθο κώδικα:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Βήμα 5: Απόδοση σε PDF
Τέλος, μετατρέψτε το αρχείο Numbers σε μορφή PDF χρησιμοποιώντας τον ακόλουθο κώδικα:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Συγχαρητήρια! Έχετε αποδώσει με επιτυχία τα αρχεία Numbers σε διάφορες μορφές χρησιμοποιώντας το Groupdocs.Viewer για .NET.
## συμπέρασμα
Σε αυτό το σεμινάριο, καλύψαμε τα βασικά για την απόδοση των αρχείων Numbers χρησιμοποιώντας το Groupdocs.Viewer για .NET. Αυτή η ισχυρή βιβλιοθήκη παρέχει απρόσκοπτη ενσωμάτωση για την προβολή και τη μετατροπή εγγράφων στις εφαρμογές σας .NET.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Groupdocs.Viewer για .NET με άλλους τύπους εγγράφων;
Ναι, το Groupdocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, συμπεριλαμβανομένων των Word, Excel, PDF και άλλων.
### Είναι διαθέσιμη μια προσωρινή άδεια για σκοπούς δοκιμής;
 Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια[εδώ](https://purchase.groupdocs.com/temporary-license/) για δοκιμή.
### Πού μπορώ να βρω υποστήριξη για το Groupdocs.Viewer για .NET;
 Επισκέψου το[Groupdocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) για βοήθεια και συζητήσεις.
### Πώς μπορώ να αγοράσω την πλήρη έκδοση του Groupdocs.Viewer για .NET;
 Μπορείτε να αγοράσετε την πλήρη έκδοση[εδώ](https://purchase.groupdocs.com/buy).
### Υπάρχει διαθέσιμη δωρεάν δοκιμαστική έκδοση;
 Ναι, μπορείτε να εξερευνήσετε τη δωρεάν δοκιμαστική έκδοση[εδώ](https://releases.groupdocs.com/).