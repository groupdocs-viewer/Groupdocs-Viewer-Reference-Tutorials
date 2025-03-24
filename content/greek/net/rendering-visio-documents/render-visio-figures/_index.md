---
title: Render Visio Figures
linktitle: Render Visio Figures
second_title: GroupDocs.Viewer .NET API
description: Μάθετε πώς να αποδίδετε στοιχεία του Visio χρησιμοποιώντας το GroupDocs.Viewer για .NET με αυτό το περιεκτικό. Βελτιώστε τις δυνατότητες προβολής εγγράφων στις εφαρμογές σας .NET.
weight: 10
url: /el/net/rendering-visio-documents/render-visio-figures/
---
## Εισαγωγή
Στη σημερινή ψηφιακή εποχή, η απόδοση εγγράφων διαδραματίζει κρίσιμο ρόλο σε διάφορες εφαρμογές. Είτε πρόκειται για την εμφάνιση εγγράφων σε έναν ιστότοπο είτε για τη μετατροπή τους σε διαφορετικές μορφές, η αποτελεσματική απόδοση είναι απαραίτητη. Το GroupDocs.Viewer για .NET παρέχει μια ισχυρή λύση για την προβολή και τον χειρισμό εγγράφων εντός εφαρμογών .NET. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στην απόδοση των αριθμών του Visio χρησιμοποιώντας το GroupDocs.Viewer για .NET, αναλύοντας τη διαδικασία σε απλά βήματα.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Ρύθμιση περιβάλλοντος: Βεβαιωθείτε ότι έχετε ένα περιβάλλον εργασίας για την ανάπτυξη .NET.
2.  GroupDocs.Viewer για .NET: Κατεβάστε και εγκαταστήστε το GroupDocs.Viewer για .NET από το[σύνδεσμος λήψης](https://releases.groupdocs.com/viewer/net/).
3. Βασική κατανόηση της C#: Εξοικειωθείτε με τις βασικές αρχές της γλώσσας προγραμματισμού C#.
4. Δείγμα εγγράφου Visio: Έχετε ένα δείγμα εγγράφου Visio έτοιμο για απόδοση.

## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων:
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
- Κατάλογος εξόδου: Καθορίστε τον κατάλογο όπου θα αποθηκευτεί το αποδοθέν HTML.
- Μορφή διαδρομής αρχείου σελίδας: Καθορίστε τη μορφή διαδρομής για τη σελίδα HTML.
- Εκκίνηση προγράμματος προβολής: Εκκινήστε το αντικείμενο Viewer με τη διαδρομή προς το έγγραφο του Visio.
- Επιλογές προβολής HTML: Διαμόρφωση επιλογών για απόδοση HTML.
- Επιλογές απόδοσης Visio: Ορίστε επιλογές ειδικά για την απόδοση του Visio, όπως η απόδοση μόνο ψηφίων και το πλάτος του σχήματος.
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
- Παρόμοια με την απόδοση σε HTML, διαμορφώστε τις επιλογές για απόδοση σε μορφή JPG.
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
- Η διαμόρφωση για απόδοση σε μορφή PNG ακολουθεί παρόμοιο μοτίβο με την απόδοση JPG.
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
- Για απόδοση σε PDF, διαμορφώστε τις επιλογές ειδικά για τη μορφή PDF.

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο απόδοσης ψηφίων του Visio χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να ενσωματώσετε απρόσκοπτα τις δυνατότητες απόδοσης εγγράφων στις εφαρμογές σας .NET, βελτιώνοντας την εμπειρία χρήστη και την παραγωγικότητα.
## Συχνές ερωτήσεις
### Μπορώ να προσαρμόσω τις επιλογές απόδοσης για τα στοιχεία του Visio;
Ναι, το GroupDocs.Viewer για .NET παρέχει εκτενείς επιλογές για την προσαρμογή της απόδοσης, συμπεριλαμβανομένου του πλάτους σχήματος, της απόδοσης μόνο ψηφίων και πολλά άλλα.
### Είναι το GroupDocs.Viewer για .NET κατάλληλο για απόδοση εγγράφων μεγάλης κλίμακας;
Οπωσδήποτε, το GroupDocs.Viewer για .NET είναι βελτιστοποιημένο για αποτελεσματικό χειρισμό της απόδοσης εγγράφων μεγάλης κλίμακας.
### Το GroupDocs.Viewer υποστηρίζει άλλες μορφές εγγράφων εκτός από το Visio;
Ναι, το GroupDocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, συμπεριλαμβανομένων των PDF, Microsoft Office, AutoCAD και άλλων.
### Μπορώ να ενσωματώσω το GroupDocs.Viewer σε εφαρμογές web;
Ναι, το GroupDocs.Viewer μπορεί να ενσωματωθεί απρόσκοπτα σε εφαρμογές web για προβολή και χειρισμό εγγράφων.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για δοκιμή πριν την αγορά;
Ναι, μπορείτε να επωφεληθείτε από μια δωρεάν δοκιμή από το[δικτυακός τόπος](https://releases.groupdocs.com/) για να δοκιμάσετε τις δυνατότητες του GroupDocs.Viewer για .NET.