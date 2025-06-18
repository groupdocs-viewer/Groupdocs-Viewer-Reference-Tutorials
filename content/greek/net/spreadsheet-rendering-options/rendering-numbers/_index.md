---
"description": "Εξερευνήστε τη δύναμη του Groupdocs.Viewer για .NET στην απρόσκοπτη απόδοση αρχείων Numbers. Μετατρέψτε τα σε HTML, JPG, PNG και PDF χωρίς κόπο."
"linktitle": "Απόδοση αριθμών"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση αριθμών"
"url": "/el/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# Απόδοση αριθμών

## Εισαγωγή
Καλώς ορίσατε σε αυτό το βήμα προς βήμα σεμινάριο για την απόδοση αρχείων Numbers χρησιμοποιώντας το Groupdocs.Viewer για .NET. Είτε είστε έμπειρος προγραμματιστής είτε αρχάριος, αυτός ο οδηγός θα σας καθοδηγήσει στη διαδικασία μετατροπής εγγράφων Numbers σε διάφορες μορφές. Το Groupdocs.Viewer για .NET είναι ένα ισχυρό εργαλείο που σας επιτρέπει να ενσωματώνετε απρόσκοπτα δυνατότητες προβολής εγγράφων στις εφαρμογές .NET που διαθέτετε.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Πρακτική γνώση ανάπτυξης C# και .NET.
- Το Groupdocs.Viewer για τη βιβλιοθήκη .NET είναι εγκατεστημένο. Μπορείτε να το κατεβάσετε. [εδώ](https://releases.groupdocs.com/viewer/net/).
- Η διαδρομή του καταλόγου εγγράφων σας όπου θα αποθηκευτούν τα αρχεία εξόδου.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας σε C#, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων για να χρησιμοποιήσετε τη βιβλιοθήκη Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Βήμα 1: Ρύθμιση καταλόγου εξόδου
Πριν ξεκινήσετε την απόδοση, ορίστε τον κατάλογο εξόδου όπου θα αποθηκευτούν τα αρχεία που έχουν μετατραπεί. Αντικαταστήστε τον "Κατάλογος Εγγράφων" με την πραγματική διαδρομή:
```csharp
string outputDirectory = "Your Document Directory";
```
## Βήμα 2: Απόδοση σε HTML πολλαπλών σελίδων
Χρησιμοποιήστε τον ακόλουθο κώδικα για να μετατρέψετε το αρχείο Numbers σε HTML πολλαπλών σελίδων:
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
Συγχαρητήρια! Ολοκληρώσατε με επιτυχία την απόδοση αρχείων Numbers σε διάφορες μορφές χρησιμοποιώντας το Groupdocs.Viewer για .NET.
## Σύναψη
Σε αυτό το σεμινάριο, καλύψαμε τα βασικά της απόδοσης αρχείων Numbers χρησιμοποιώντας το Groupdocs.Viewer για .NET. Αυτή η ισχυρή βιβλιοθήκη παρέχει απρόσκοπτη ενσωμάτωση για την προβολή και τη μετατροπή εγγράφων στις εφαρμογές .NET σας.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Groupdocs.Viewer για .NET με άλλους τύπους εγγράφων;
Ναι, το Groupdocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, όπως Word, Excel, PDF και άλλα.
### Υπάρχει διαθέσιμη προσωρινή άδεια για δοκιμαστικούς σκοπούς;
Ναι, μπορείτε να αποκτήσετε προσωρινή άδεια [εδώ](https://purchase.groupdocs.com/temporary-license/) για δοκιμή.
### Πού μπορώ να βρω υποστήριξη για το Groupdocs.Viewer για .NET;
Επισκεφθείτε το [Φόρουμ Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) για βοήθεια και συζητήσεις.
### Πώς μπορώ να αγοράσω την πλήρη έκδοση του Groupdocs.Viewer για .NET;
Μπορείτε να αγοράσετε την πλήρη έκδοση [εδώ](https://purchase.groupdocs.com/buy).
### Υπάρχει διαθέσιμη δωρεάν δοκιμαστική έκδοση;
Ναι, μπορείτε να εξερευνήσετε τη δωρεάν δοκιμαστική έκδοση [εδώ](https://releases.groupdocs.com/).