---
"description": "Μάθετε πώς να καθορίζετε τον τύπο αρχείου κατά τη φόρτωση εγγράφων χρησιμοποιώντας το GroupDocs.Viewer για .NET. Αποδώστε με ακρίβεια διάφορες μορφές στις εφαρμογές .NET."
"linktitle": "Καθορισμός τύπου αρχείου κατά τη φόρτωση εγγράφων"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Καθορισμός τύπου αρχείου κατά τη φόρτωση εγγράφων"
"url": "/el/net/advanced-loading/specify-file-type/"
"weight": 10
---

# Καθορισμός τύπου αρχείου κατά τη φόρτωση εγγράφων

## Εισαγωγή
Το GroupDocs.Viewer για .NET είναι ένα ευέλικτο API απόδοσης εγγράφων που υποστηρίζει ένα ευρύ φάσμα μορφών αρχείων, όπως DOCX, PDF, PPTX και άλλα. Καθορίζοντας τον τύπο αρχείου κατά τη φόρτωση εγγράφων, μπορείτε να εξασφαλίσετε ακριβή απόδοση και ομαλή εμπειρία προβολής για τους χρήστες σας.

![Καθορισμός τύπου αρχείου κατά τη φόρτωση εγγράφων στο GroupDocs.Viewer για .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασική γνώση C# και .NET framework.
- Το Visual Studio είναι εγκατεστημένο στο σύστημά σας.
- Το GroupDocs.Viewer για .NET είναι εγκατεστημένο στο έργο σας. Μπορείτε να το κατεβάσετε από [εδώ](https://releases.groupdocs.com/viewer/net/).
##
## Εισαγωγή χώρων ονομάτων
Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στον κώδικα C# σας. Αυτοί οι χώροι ονομάτων παρέχουν πρόσβαση στις κλάσεις και τις μεθόδους που απαιτούνται για την απόδοση εγγράφων.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Βήμα 1: Ρύθμιση καταλόγου εξόδου
Ορίστε τον κατάλογο όπου θέλετε να αποθηκεύσετε τις σελίδες του εγγράφου που έχουν αποδοθεί.
```csharp
string outputDirectory = "Your Document Directory";
```
## Βήμα 2: Ορισμός μορφής διαδρομής αρχείου σελίδας
Καθορίστε τη μορφή ονομασίας των αρχείων HTML εξόδου για κάθε σελίδα του εγγράφου.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Βήμα 3: Καθορισμός επιλογών φόρτωσης
Δημιουργήστε μια παρουσία του `LoadOptions` κλάση και ορίστε τον επιθυμητό τύπο αρχείου.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Βήμα 4: Φόρτωση εγγράφου και απόδοση
Χρησιμοποιήστε το `Viewer` κλάση για να φορτώσετε το έγγραφο και να το αποδώσετε σε μορφή HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Βήμα 5: Εμφάνιση μηνύματος επιτυχίας
Ενημερώστε τον χρήστη ότι το έγγραφο έχει αποδοθεί με επιτυχία και καθορίστε τη θέση των αρχείων εξόδου.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Σύναψη
Σε αυτό το σεμινάριο, μάθαμε πώς να χρησιμοποιούμε το GroupDocs.Viewer για .NET για να καθορίσουμε τον τύπο αρχείου κατά τη φόρτωση εγγράφων. Ακολουθώντας αυτά τα απλά βήματα, μπορείτε να διασφαλίσετε την ακριβή απόδοση διαφόρων μορφών εγγράφων στις εφαρμογές .NET που διαθέτετε.
## Συχνές ερωτήσεις
### Μπορώ να εμφανίσω έγγραφα εκτός από το DOCX χρησιμοποιώντας το GroupDocs.Viewer για .NET;
Ναι, το GroupDocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών αρχείων, όπως PDF, PPTX, XLSX και άλλα.
### Είναι το GroupDocs.Viewer για .NET συμβατό με το .NET Core;
Ναι, το GroupDocs.Viewer για .NET είναι συμβατό τόσο με το .NET Framework όσο και με το .NET Core.
### Μπορώ να προσαρμόσω τα αρχεία HTML εξόδου που δημιουργούνται από το GroupDocs.Viewer;
Ναι, μπορείτε να προσαρμόσετε την έξοδο HTML χρησιμοποιώντας διάφορες επιλογές που παρέχονται από το API.
### Απαιτεί το GroupDocs.Viewer για .NET εξωτερικές εξαρτήσεις;
Όχι, το GroupDocs.Viewer για .NET είναι μια αυτόνομη βιβλιοθήκη και δεν απαιτεί εξωτερικές εξαρτήσεις.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το GroupDocs.Viewer για .NET;
Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση από [εδώ](https://releases.groupdocs.com/viewer/net/).