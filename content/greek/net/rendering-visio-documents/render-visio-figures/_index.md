---
"description": "Μάθετε πώς να αποδίδετε στοιχεία του Visio χρησιμοποιώντας το GroupDocs.Viewer για .NET με αυτό το ολοκληρωμένο πρόγραμμα. Βελτιώστε τις δυνατότητες προβολής εγγράφων στις εφαρμογές .NET που διαθέτετε."
"linktitle": "Απόδοση φιγούρων Visio"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση φιγούρων Visio"
"url": "/el/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
---

# Απόδοση φιγούρων Visio

## Εισαγωγή
Στη σημερινή ψηφιακή εποχή, η απόδοση εγγράφων παίζει κρίσιμο ρόλο σε διάφορες εφαρμογές. Είτε πρόκειται για την εμφάνιση εγγράφων σε έναν ιστότοπο είτε για τη μετατροπή τους σε διαφορετικές μορφές, η αποτελεσματική απόδοση είναι απαραίτητη. Το GroupDocs.Viewer για .NET παρέχει μια ισχυρή λύση για την προβολή και τον χειρισμό εγγράφων σε εφαρμογές .NET. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στην απόδοση σχημάτων Visio χρησιμοποιώντας το GroupDocs.Viewer για .NET, αναλύοντας τη διαδικασία σε απλά βήματα.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Ρύθμιση περιβάλλοντος: Βεβαιωθείτε ότι έχετε ένα λειτουργικό περιβάλλον για ανάπτυξη .NET.
2. GroupDocs.Viewer για .NET: Κατεβάστε και εγκαταστήστε το GroupDocs.Viewer για .NET από το [σύνδεσμος λήψης](https://releases.groupdocs.com/viewer/net/).
3. Βασική Κατανόηση της C#: Εξοικειωθείτε με τις βασικές αρχές της γλώσσας προγραμματισμού C#.
4. Δείγμα εγγράφου του Visio: Να έχετε ένα δείγμα εγγράφου του Visio έτοιμο για απόδοση.

## Εισαγωγή χώρων ονομάτων
Στο έργο σας σε C#, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Απόδοση σε HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Κατάλογος εξόδου: Ορίστε τον κατάλογο όπου θα αποθηκευτεί το HTML που αποδίδεται.
- Μορφή διαδρομής αρχείου σελίδας: Καθορίστε τη μορφή διαδρομής για τη σελίδα HTML.
- Αρχικοποίηση προγράμματος προβολής: Αρχικοποιήστε το αντικείμενο Προβολή με τη διαδρομή προς το έγγραφο του Visio.
- Επιλογές προβολής HTML: Ρυθμίστε τις παραμέτρους επιλογών για την απόδοση HTML.
- Επιλογές απόδοσης Visio: Ορίστε επιλογές που αφορούν συγκεκριμένα την απόδοση του Visio, όπως απόδοση μόνο σχημάτων και πλάτος σχήματος.
## 2. Απόδοση σε JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Όπως και με την απόδοση σε HTML, διαμορφώστε τις επιλογές για την απόδοση σε μορφή JPG.
## 3. Απόδοση σε PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Η διαμόρφωση για την απόδοση σε μορφή PNG ακολουθεί παρόμοιο μοτίβο με την απόδοση JPG.
## 4. Απόδοση σε PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Για την απόδοση σε PDF, διαμορφώστε επιλογές ειδικά για τη μορφή PDF.

## Σύναψη
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο απόδοσης αριθμών Visio χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ακολουθώντας τον αναλυτικό οδηγό, μπορείτε να ενσωματώσετε απρόσκοπτα δυνατότητες απόδοσης εγγράφων στις εφαρμογές .NET, βελτιώνοντας την εμπειρία χρήστη και την παραγωγικότητα.
## Συχνές ερωτήσεις
### Μπορώ να προσαρμόσω τις επιλογές απόδοσης για τα σχήματα του Visio;
Ναι, το GroupDocs.Viewer για .NET παρέχει εκτεταμένες επιλογές για την προσαρμογή της απόδοσης, όπως το πλάτος του σχήματος, την απόδοση μόνο σχημάτων και πολλά άλλα.
### Είναι το GroupDocs.Viewer για .NET κατάλληλο για απόδοση εγγράφων μεγάλης κλίμακας;
Απολύτως, το GroupDocs.Viewer για .NET έχει βελτιστοποιηθεί για την αποτελεσματική διαχείριση της απόδοσης εγγράφων μεγάλης κλίμακας.
### Υποστηρίζει το GroupDocs.Viewer άλλες μορφές εγγράφων εκτός από το Visio;
Ναι, το GroupDocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, όπως PDF, Microsoft Office, AutoCAD και άλλα.
### Μπορώ να ενσωματώσω το GroupDocs.Viewer σε εφαρμογές web;
Ναι, το GroupDocs.Viewer μπορεί να ενσωματωθεί απρόσκοπτα σε εφαρμογές web για προβολή και χειρισμό εγγράφων.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για δοκιμή πριν από την αγορά;
Ναι, μπορείτε να επωφεληθείτε από μια δωρεάν δοκιμή από το [δικτυακός τόπος](https://releases.groupdocs.com/) για να ελέγξετε τις δυνατότητες του GroupDocs.Viewer για .NET.