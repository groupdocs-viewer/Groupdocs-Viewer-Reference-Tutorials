---
"description": "Μάθετε πώς να αποδίδετε εικόνες FODG και ODG σε HTML, JPG, PNG και PDF χρησιμοποιώντας το GroupDocs.Viewer για .NET. Βελτιώστε τον χειρισμό των εγγράφων σας."
"linktitle": "Απόδοση εικόνων FODG και ODG"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση εικόνων FODG και ODG"
"url": "/el/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# Απόδοση εικόνων FODG και ODG

## Εισαγωγή
Στον κόσμο της ανάπτυξης λογισμικού, ο αποτελεσματικός χειρισμός μορφών εγγράφων είναι ύψιστης σημασίας. Το GroupDocs.Viewer για .NET είναι ένα ισχυρό εργαλείο που έχει σχεδιαστεί για να απλοποιεί τη διαδικασία απόδοσης εικόνων FODG και ODG σε εφαρμογές .NET. Αυτό το σεμινάριο θα σας καθοδηγήσει στα βήματα που απαιτούνται για την απόδοση αυτών των εικόνων σε διάφορες μορφές, όπως HTML, JPG, PNG και PDF, χρησιμοποιώντας το GroupDocs.Viewer για .NET.

![Απόδοση εικόνων FODG και ODG με το GroupDocs.Viewer για .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. GroupDocs.Viewer για .NET: Λήψη και εγκατάσταση του GroupDocs.Viewer για .NET από [εδώ](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Βεβαιωθείτε ότι έχετε εγκαταστήσει το .NET Framework στο σύστημά σας.
3. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι χρήσιμη.

## Εισαγωγή χώρων ονομάτων
Πριν ξεκινήσετε την υλοποίηση, εισαγάγετε τους απαραίτητους χώρους ονομάτων:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Βήμα 1: Ορισμός καταλόγου εξόδου
```csharp
string outputDirectory = "Your Document Directory";
```
Αντικαθιστώ `"Your Document Directory"` με τη διαδρομή καταλόγου όπου θέλετε να αποθηκεύσετε τις εικόνες που αποδίδονται.
## Βήμα 2: Απόδοση σε HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Αυτό το βήμα αποδίδει την εικόνα FODG σε μορφή HTML.
## Βήμα 3: Απόδοση σε JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Εδώ, η εικόνα FODG αποδίδεται σε μορφή JPG.
## Βήμα 4: Απόδοση σε PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Αυτό το βήμα μετατρέπει την εικόνα FODG σε μορφή PNG.
## Βήμα 5: Απόδοση σε PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Τέλος, η εικόνα FODG αποδίδεται σε μορφή PDF.

## Σύναψη
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο απόδοσης εικόνων FODG και ODG σε διάφορες μορφές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να ενσωματώσετε απρόσκοπτα δυνατότητες απόδοσης εγγράφων στις εφαρμογές .NET που διαθέτετε.
## Συχνές ερωτήσεις
### Είναι το GroupDocs.Viewer για .NET συμβατό με όλες τις εκδόσεις του .NET Framework;
Το GroupDocs.Viewer για .NET είναι συμβατό με ένα ευρύ φάσμα εκδόσεων του .NET Framework, συμπεριλαμβανομένων των πιο πρόσφατων.
### Μπορώ να αποδώσω έγγραφα ασύγχρονα με το GroupDocs.Viewer για .NET;
Ναι, το GroupDocs.Viewer για .NET παρέχει δυνατότητες ασύγχρονης απόδοσης για βελτιωμένη απόδοση.
### Υποστηρίζει το GroupDocs.Viewer για .NET την απόδοση κρυπτογραφημένων εγγράφων;
Ναι, το GroupDocs.Viewer για .NET υποστηρίζει την απόδοση κρυπτογραφημένων εγγράφων με τα κατάλληλα κλειδιά αποκρυπτογράφησης.
### Είναι δυνατή η προσαρμογή της απόδοσης με το GroupDocs.Viewer για .NET;
Απολύτως, το GroupDocs.Viewer για .NET προσφέρει διάφορες επιλογές προσαρμογής για να προσαρμόσετε την έξοδο απόδοσης σύμφωνα με τις απαιτήσεις σας.
### Μπορώ να εμφανίσω έγγραφα από απομακρυσμένες τοποθεσίες αποθήκευσης χρησιμοποιώντας το GroupDocs.Viewer για .NET;
Ναι, το GroupDocs.Viewer για .NET υποστηρίζει την απόδοση εγγράφων τόσο από τοπικές όσο και από απομακρυσμένες τοποθεσίες αποθήκευσης.