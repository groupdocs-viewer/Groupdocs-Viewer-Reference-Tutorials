---
"description": "Μάθετε πώς να αποδίδετε εύκολα εικόνες CMX σε διάφορες μορφές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Βελτιώστε τη διαχείριση εγγράφων."
"linktitle": "Απόδοση εικόνων CMX"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση εικόνων CMX"
"url": "/el/net/image-rendering/render-cmx-images/"
"weight": 13
type: docs
---
# Απόδοση εικόνων CMX

## Εισαγωγή
Στον τομέα της διαχείρισης και χειρισμού εγγράφων, η απόδοση εικόνων από διάφορες μορφές είναι μια κρίσιμη εργασία. Το GroupDocs.Viewer για .NET απλοποιεί αυτήν τη διαδικασία παρέχοντας ολοκληρωμένες λειτουργίες για την απόδοση εικόνων CMX σε διαφορετικές μορφές όπως HTML, JPG, PNG και PDF. Αυτό το σεμινάριο θα σας καθοδηγήσει στη βήμα προς βήμα διαδικασία απόδοσης εικόνων CMX χρησιμοποιώντας το GroupDocs.Viewer για .NET.

![Απόδοση εικόνων CMX με το GroupDocs.Viewer για .NET](/viewer/image-rendering/render-cmx-images.png)

## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Βιβλιοθήκη GroupDocs.Viewer για .NET: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη GroupDocs.Viewer για .NET από [εδώ](https://releases.groupdocs.com/viewer/net/).
2. Περιβάλλον Ανάπτυξης: Να έχετε ένα λειτουργικό περιβάλλον ανάπτυξης με .NET framework.
3. Αρχείο εικόνας CMX: Αποκτήστε ένα αρχείο εικόνας CMX που θέλετε να αποδώσετε.

## Εισαγωγή χώρων ονομάτων
Πριν προχωρήσετε, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων για να αποκτήσετε πρόσβαση στις λειτουργίες του GroupDocs.Viewer στην εφαρμογή .NET σας:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Απόδοση σε HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Ορισμός καταλόγου εξόδου: Ορίστε τον κατάλογο στον οποίο θέλετε να αποθηκεύσετε τα αρχεία HTML που έχουν αποδοθεί.
- Καθορισμός μορφής διαδρομής αρχείου: Ορίστε τη μορφή για τα αρχεία HTML εξόδου.
- Δημιουργία αντικειμένου Viewer: Δημιουργήστε μια παρουσία της κλάσης Viewer με το αρχείο εικόνας CMX.
- Επιλογές απόδοσης HTML: Διαμορφώστε τις επιλογές απόδοσης HTML, όπως τους πόρους ενσωμάτωσης.
- Απόδοση CMX σε HTML: Καλέστε τη μέθοδο View του αντικειμένου προβολής για να αποδώσετε την εικόνα CMX σε HTML.
## Απόδοση σε JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Ορισμός καταλόγου εξόδου: Ορίστε τον κατάλογο για την αποθήκευση των αρχείων JPG που έχουν αποδοθεί.
- Καθορισμός μορφής διαδρομής αρχείου: Ορίστε τη μορφή για τα αρχεία JPG εξόδου.
- Δημιουργία αντικειμένου Viewer: Δημιουργήστε μια παρουσία της κλάσης Viewer με το αρχείο εικόνας CMX.
- Επιλογές απόδοσης JPG: Διαμορφώστε τις επιλογές απόδοσης JPG.
- Απόδοση CMX σε JPG: Καλέστε τη μέθοδο View του αντικειμένου προβολής για να αποδώσετε την εικόνα CMX σε JPG.
## Απόδοση σε PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Ορισμός καταλόγου εξόδου: Ορίστε τον κατάλογο για την αποθήκευση των αρχείων PNG που έχουν αποδοθεί.
- Καθορισμός μορφής διαδρομής αρχείου: Ορίστε τη μορφή για τα αρχεία PNG εξόδου.
- Δημιουργία αντικειμένου Viewer: Δημιουργήστε μια παρουσία της κλάσης Viewer με το αρχείο εικόνας CMX.
- Επιλογές απόδοσης PNG: Διαμορφώστε τις επιλογές απόδοσης PNG.
- Απόδοση CMX σε PNG: Καλέστε τη μέθοδο View του αντικειμένου προβολής για να αποδώσετε την εικόνα CMX σε PNG.
## Απόδοση σε PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Ορισμός καταλόγου εξόδου: Ορίστε τον κατάλογο για την αποθήκευση του αποδοθέντος αρχείου PDF.
- Καθορισμός μορφής διαδρομής αρχείου: Ορίστε τη μορφή για το αρχείο PDF εξόδου.
- Δημιουργία αντικειμένου Viewer: Δημιουργήστε μια παρουσία της κλάσης Viewer με το αρχείο εικόνας CMX.
- Επιλογές απόδοσης PDF: Διαμορφώστε τις επιλογές απόδοσης PDF.
- Απόδοση CMX σε PDF: Καλέστε τη μέθοδο View του αντικειμένου προβολής για να αποδώσετε την εικόνα CMX σε PDF.

## Σύναψη
Συμπερασματικά, το GroupDocs.Viewer για .NET προσφέρει μια ισχυρή λύση για την απρόσκοπτη απόδοση εικόνων CMX σε διάφορες μορφές. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να ενσωματώσετε εύκολα δυνατότητες απόδοσης εικόνων CMX στις εφαρμογές .NET σας, βελτιώνοντας την αποτελεσματικότητα της διαχείρισης εγγράφων.
## Συχνές ερωτήσεις
### Μπορώ να αποδώσω συγκεκριμένες σελίδες μιας εικόνας CMX;
Ναι, μπορείτε να αποδώσετε συγκεκριμένες σελίδες καθορίζοντας τον αριθμό σελίδας στις επιλογές απόδοσης.
### Είναι το GroupDocs.Viewer για .NET συμβατό με όλα τα .NET frameworks;
Ναι, το GroupDocs.Viewer για .NET είναι συμβατό με πολλά .NET frameworks, συμπεριλαμβανομένων των .NET Core και .NET Framework.
### Υποστηρίζει το GroupDocs.Viewer την απόδοση κρυπτογραφημένων εικόνων CMX;
Ναι, το GroupDocs.Viewer υποστηρίζει την απόδοση κρυπτογραφημένων εικόνων CMX με τα κατάλληλα κλειδιά αποκρυπτογράφησης.
### Μπορώ να προσαρμόσω τις επιλογές απόδοσης για διαφορετικές μορφές εξόδου;
Απολύτως, το GroupDocs.Viewer παρέχει εκτεταμένες επιλογές για την προσαρμογή των παραμέτρων απόδοσης με βάση τις απαιτήσεις σας.
### Υπάρχει κάποιο φόρουμ κοινότητας για την υποστήριξη του GroupDocs.Viewer;
Ναι, μπορείτε να ζητήσετε βοήθεια και να αλληλεπιδράσετε με την κοινότητα GroupDocs.Viewer στο φόρουμ υποστήριξης. [εδώ](https://forum.groupdocs.com/c/viewer/9).