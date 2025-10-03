---
"description": "Μάθετε πώς να αποδίδετε συγκεκριμένες μορφές CAD όπως CF2 σε HTML, JPG, PNG και PDF χρησιμοποιώντας το Groupdocs.Viewer για .NET."
"linktitle": "Μορφές CAD ειδικά για απόδοση (CF2)"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Μορφές CAD ειδικά για απόδοση (CF2)"
"url": "/el/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
type: docs
---
# Μορφές CAD ειδικά για απόδοση (CF2)

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο απόδοσης συγκεκριμένων μορφών CAD χρησιμοποιώντας το Groupdocs.Viewer για .NET. Το Groupdocs.Viewer είναι ένα ισχυρό API προβολής εγγράφων που επιτρέπει στους προγραμματιστές να εμφανίζουν πάνω από 170 τύπους εγγράφων στις εφαρμογές τους χωρίς να απαιτούνται εξωτερικές εγκαταστάσεις λογισμικού. Συγκεκριμένα, θα επικεντρωθούμε στην απόδοση μορφών CAD όπως το CF2 σε διάφορες μορφές εξόδου όπως HTML, JPG, PNG και PDF.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Το Visual Studio είναι εγκατεστημένο στο σύστημά σας.
- Groupdocs.Viewer για .NET SDK. Μπορείτε να το κατεβάσετε από [εδώ](https://releases.groupdocs.com/viewer/net/).
- Βασική γνώση της γλώσσας προγραμματισμού C#.
## Εισαγωγή χώρων ονομάτων
Αρχικά, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων που απαιτούνται για την απόδοση μορφών CAD.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Τώρα, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα:
## Απόδοση CF2 σε HTML
### Βήμα 1: Ορίστε τον κατάλογο εξόδου όπου θα αποθηκευτεί το HTML που αποδίδεται.
```csharp
string outputDirectory = "Your Document Directory";
```
### Βήμα 2: Ορίστε τη μορφή διαδρομής αρχείου για την έξοδο HTML.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Βήμα 3: Αρχικοποιήστε το αντικείμενο Viewer και καθορίστε το αρχείο εισόδου CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Ορίστε πρόσθετες επιλογές απόδοσης, εάν απαιτείται
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Απόδοση CF2 σε JPG
### Βήμα 1: Ορίστε τη μορφή διαδρομής αρχείου για την έξοδο JPG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Βήμα 2: Αρχικοποιήστε το αντικείμενο Viewer και καθορίστε το αρχείο εισόδου CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Ορίστε πρόσθετες επιλογές απόδοσης, εάν απαιτείται
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Απόδοση CF2 σε PNG

### Βήμα 1: Ορίστε τη μορφή διαδρομής αρχείου για την έξοδο PNG.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Βήμα 2: Αρχικοποιήστε το αντικείμενο Viewer και καθορίστε το αρχείο εισόδου CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Ορίστε πρόσθετες επιλογές απόδοσης, εάν απαιτείται
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Απόδοση CF2 σε PDF
### Βήμα 1: Ορίστε τη μορφή διαδρομής αρχείου για το αποτέλεσμα PDF.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Βήμα 2: Αρχικοποιήστε το αντικείμενο Viewer και καθορίστε το αρχείο εισόδου CF2.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Ορίστε πρόσθετες επιλογές απόδοσης, εάν απαιτείται
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Σύναψη
Σε αυτό το σεμινάριο, μάθαμε πώς να αποδίδουμε συγκεκριμένες μορφές CAD, όπως το CF2, χρησιμοποιώντας το Groupdocs.Viewer για .NET. Ακολουθώντας τον αναλυτικό οδηγό, μπορείτε εύκολα να ενσωματώσετε δυνατότητες απόδοσης εγγράφων στις εφαρμογές .NET που διαθέτετε.
## Συχνές ερωτήσεις
### Μπορεί το Groupdocs.Viewer να αποδώσει και άλλες μορφές CAD εκτός από το CF2;
Ναι, το Groupdocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών CAD, συμπεριλαμβανομένων των DWG, DXF, DGN και άλλων.
### Είναι το Groupdocs.Viewer κατάλληλο για την απόδοση εγγράφων σε εφαρμογές web;
Απολύτως, το Groupdocs.Viewer μπορεί να ενσωματωθεί απρόσκοπτα σε εφαρμογές ιστού για την απόδοση εγγράφων απευθείας στο πρόγραμμα περιήγησης.
### Απαιτεί το Groupdocs.Viewer εξωτερικές εξαρτήσεις για την απόδοση;
Όχι, το Groupdocs.Viewer είναι ένα αυτόνομο API και δεν απαιτεί εξωτερικές εξαρτήσεις ή εγκαταστάσεις λογισμικού.
### Μπορώ να προσαρμόσω τις επιλογές απόδοσης σύμφωνα με τις απαιτήσεις μου;
Ναι, το Groupdocs.Viewer παρέχει διάφορες επιλογές απόδοσης που μπορούν να προσαρμοστούν ώστε να καλύπτουν τις συγκεκριμένες ανάγκες σας.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Groupdocs.Viewer;
Ναι, μπορείτε να αποκτήσετε μια δωρεάν δοκιμαστική έκδοση του Groupdocs.Viewer από [εδώ](https://releases.groupdocs.com/).