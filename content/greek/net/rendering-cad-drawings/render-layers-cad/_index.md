---
"description": "Αποδώστε σχέδια CAD απρόσκοπτα σε εφαρμογές .NET με το GroupDocs.Viewer για .NET. Εξερευνήστε επιλογές απόδοσης, προσαρμόστε επίπεδα και πολλά άλλα."
"linktitle": "Απόδοση επιπέδων σε σχέδια CAD"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση επιπέδων σε σχέδια CAD"
"url": "/el/net/rendering-cad-drawings/render-layers-cad/"
"weight": 13
type: docs
---
# Απόδοση επιπέδων σε σχέδια CAD

## Εισαγωγή
Το GroupDocs.Viewer για .NET είναι ένα ισχυρό εργαλείο που επιτρέπει στους προγραμματιστές να ενσωματώνουν απρόσκοπτα δυνατότητες απόδοσης εγγράφων στις εφαρμογές .NET. Είτε χρειάζεται να αποδώσετε σχέδια CAD, PDF, έγγραφα του Microsoft Office ή άλλα, το GroupDocs.Viewer παρέχει μια ολοκληρωμένη λύση.
## Προαπαιτούμενα
Πριν ξεκινήσετε να χρησιμοποιείτε το GroupDocs.Viewer για .NET, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασική κατανόηση της γλώσσας προγραμματισμού C#.
- Το περιβάλλον ανάπτυξης .NET έχει ρυθμιστεί στον υπολογιστή σας.
- Το GroupDocs.Viewer για .NET είναι εγκατεστημένο. Μπορείτε να το κατεβάσετε από [εδώ](https://releases.groupdocs.com/viewer/net/).
- Πρόσβαση στην τεκμηρίωση του GroupDocs.Viewer για .NET για εκπαιδευτικά βίντεο, την οποία μπορείτε να βρείτε [εδώ](https://tutorials.groupdocs.com/viewer/net/).

## Εισαγωγή χώρων ονομάτων
Για να ξεκινήσετε να χρησιμοποιείτε το GroupDocs.Viewer για .NET, πρέπει να εισαγάγετε τους απαιτούμενους χώρους ονομάτων στο έργο σας. Ακολουθήστε τα παρακάτω βήματα:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Ας αναλύσουμε το παράδειγμα που δίνεται σε πολλά βήματα:
## Βήμα 1: Ορισμός καταλόγου εξόδου
```csharp
string outputDirectory = "Your Document Directory";
```
## Βήμα 2: Ορισμός μορφής διαδρομής αρχείου σελίδας
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Βήμα 3: Αρχικοποίηση αντικειμένου προβολής
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Το μπλοκάρισμα κώδικα συνεχίζεται...
}
```
## Βήμα 4: Ορισμός επιλογών προβολής HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Βήμα 5: Ορισμός επιπέδων CAD
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## Βήμα 6: Απόδοση εγγράφου
```csharp
viewer.View(options);
```
## Βήμα 7: Εμφάνιση της τοποθεσίας του εγγράφου που έχει αποδοθεί
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Σύναψη
Με το GroupDocs.Viewer για .NET, η απόδοση σχεδίων CAD στις εφαρμογές .NET γίνεται μια απρόσκοπτη διαδικασία. Ακολουθώντας τα βήματα που περιγράφονται σε αυτόν τον οδηγό, μπορείτε εύκολα να ενσωματώσετε δυνατότητες απόδοσης εγγράφων στα έργα σας.
## Συχνές ερωτήσεις
### Είναι το GroupDocs.Viewer συμβατό με όλους τους τύπους σχεδίων CAD;
Ναι, το GroupDocs.Viewer υποστηρίζει την απόδοση ενός ευρέος φάσματος μορφών σχεδίασης CAD, συμπεριλαμβανομένων των DWG και DXF.
### Μπορώ να προσαρμόσω τις επιλογές απόδοσης για σχέδια CAD;
Απολύτως, το GroupDocs.Viewer προσφέρει διάφορες επιλογές προσαρμογής, όπως τον καθορισμό επιπέδων για απόδοση ή τον ορισμό μορφών εξόδου.
### Απαιτείται σύνδεση στο διαδίκτυο για την απόδοση εγγράφων από το GroupDocs.Viewer;
Όχι, το GroupDocs.Viewer εκτελεί απόδοση τοπικά χωρίς να χρειάζεται σύνδεση στο διαδίκτυο.
### Υπάρχει διαθέσιμη δωρεάν δοκιμαστική έκδοση για το GroupDocs.Viewer για .NET;
Ναι, μπορείτε να αποκτήσετε πρόσβαση σε μια δωρεάν δοκιμαστική έκδοση του GroupDocs.Viewer για .NET [εδώ](https://releases.groupdocs.com/).
### Πού μπορώ να λάβω υποστήριξη για το GroupDocs.Viewer για .NET;
Για οποιαδήποτε τεχνική βοήθεια ή απορίες, μπορείτε να επισκεφθείτε το φόρουμ GroupDocs.Viewer [εδώ](https://forum.groupdocs.com/c/viewer/9).