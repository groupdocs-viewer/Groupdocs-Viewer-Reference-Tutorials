---
title: Απόδοση εικόνων CMX
linktitle: Απόδοση εικόνων CMX
second_title: GroupDocs.Viewer .NET API
description: Μάθετε πώς να αποδίδετε εύκολα εικόνες CMX σε διάφορες μορφές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Βελτιώστε τη διαχείριση των εγγράφων σας.
weight: 13
url: /el/net/image-rendering/render-cmx-images/
---
## Εισαγωγή
Στον τομέα της διαχείρισης και χειρισμού εγγράφων, η απόδοση εικόνων από διάφορες μορφές είναι μια κομβική εργασία. Το GroupDocs.Viewer για .NET απλοποιεί αυτή τη διαδικασία παρέχοντας ολοκληρωμένες λειτουργίες για την απόδοση εικόνων CMX σε διαφορετικές μορφές όπως HTML, JPG, PNG και PDF. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία βήμα προς βήμα απόδοσης εικόνων CMX χρησιμοποιώντας το GroupDocs.Viewer για .NET.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  GroupDocs.Viewer για .NET Library: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη GroupDocs.Viewer για .NET από[εδώ](https://releases.groupdocs.com/viewer/net/).
2. Αναπτυξιακό περιβάλλον: Δημιουργήστε ένα εργασιακό περιβάλλον ανάπτυξης με .NET Framework.
3. Αρχείο εικόνας CMX: Αποκτήστε ένα αρχείο εικόνας CMX που θέλετε να αποδώσετε.

## Εισαγωγή χώρων ονομάτων
Πριν συνεχίσετε, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων για πρόσβαση στις λειτουργίες του GroupDocs.Viewer στην εφαρμογή σας .NET:
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
- Ορισμός καταλόγου εξόδου: Ορίστε τον κατάλογο στον οποίο θέλετε να αποθηκεύσετε τα αποδοθέντα αρχεία HTML.
- Καθορίστε τη μορφή διαδρομής αρχείου: Καθορίστε τη μορφή για τα αρχεία HTML εξόδου.
- Αντικείμενο Instantiate Viewer: Δημιουργήστε ένα στιγμιότυπο της κλάσης Viewer με το αρχείο εικόνας CMX.
- Επιλογές απόδοσης HTML: Διαμορφώστε τις επιλογές απόδοσης HTML, όπως η ενσωμάτωση πόρων.
- Απόδοση CMX σε HTML: Επικαλέστε τη μέθοδο Προβολή του αντικειμένου προβολής για απόδοση της εικόνας CMX σε HTML.
## Απόδοση σε JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Ορισμός καταλόγου εξόδου: Ορίστε τον κατάλογο για την αποθήκευση των αποδοθέντων αρχείων JPG.
- Καθορισμός μορφής διαδρομής αρχείου: Καθορίστε τη μορφή για τα αρχεία JPG εξόδου.
- Αντικείμενο Instantiate Viewer: Δημιουργήστε ένα στιγμιότυπο της κλάσης Viewer με το αρχείο εικόνας CMX.
- Επιλογές απόδοσης JPG: Διαμορφώστε τις επιλογές απόδοσης JPG.
- Απόδοση CMX σε JPG: Επικαλέστε τη μέθοδο View του αντικειμένου προβολής για απόδοση της εικόνας CMX σε JPG.
## Απόδοση σε PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Ορισμός καταλόγου εξόδου: Ορίστε τον κατάλογο για την αποθήκευση των αποδιδόμενων αρχείων PNG.
- Καθορισμός μορφής διαδρομής αρχείου: Καθορίστε τη μορφή για τα αρχεία PNG εξόδου.
- Αντικείμενο Instantiate Viewer: Δημιουργήστε ένα στιγμιότυπο της κλάσης Viewer με το αρχείο εικόνας CMX.
- Επιλογές απόδοσης PNG: Διαμορφώστε τις επιλογές απόδοσης PNG.
- Απόδοση CMX σε PNG: Επικαλέστε τη μέθοδο View του αντικειμένου προβολής για απόδοση της εικόνας CMX σε PNG.
## Απόδοση σε PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Ορισμός καταλόγου εξόδου: Ορίστε τον κατάλογο για την αποθήκευση του αποδιδόμενου αρχείου PDF.
- Καθορίστε τη μορφή διαδρομής αρχείου: Καθορίστε τη μορφή για το αρχείο PDF εξόδου.
- Αντικείμενο Instantiate Viewer: Δημιουργήστε ένα στιγμιότυπο της κλάσης Viewer με το αρχείο εικόνας CMX.
- Επιλογές απόδοσης PDF: Διαμορφώστε τις επιλογές απόδοσης PDF.
- Απόδοση CMX σε PDF: Επικαλέστε τη μέθοδο Προβολή του αντικειμένου προβολής για απόδοση της εικόνας CMX σε PDF.

## συμπέρασμα
Εν κατακλείδι, το GroupDocs.Viewer για .NET προσφέρει μια ισχυρή λύση για την απρόσκοπτη απόδοση εικόνων CMX σε διάφορες μορφές. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να ενσωματώσετε αβίαστα τις δυνατότητες απόδοσης εικόνων CMX στις εφαρμογές σας .NET, βελτιώνοντας την αποτελεσματικότητα της διαχείρισης εγγράφων.
## Συχνές ερωτήσεις
### Μπορώ να αποδώσω συγκεκριμένες σελίδες μιας εικόνας CMX;
Ναι, μπορείτε να αποδώσετε συγκεκριμένες σελίδες καθορίζοντας τον αριθμό σελίδας στις επιλογές απόδοσης.
### Είναι το GroupDocs.Viewer για .NET συμβατό με όλα τα πλαίσια .NET;
Ναι, το GroupDocs.Viewer για .NET είναι συμβατό με πολλά πλαίσια .NET, συμπεριλαμβανομένων των .NET Core και .NET Framework.
### Το GroupDocs.Viewer υποστηρίζει την απόδοση κρυπτογραφημένων εικόνων CMX;
Ναι, το GroupDocs.Viewer υποστηρίζει την απόδοση κρυπτογραφημένων εικόνων CMX με κατάλληλα κλειδιά αποκρυπτογράφησης.
### Μπορώ να προσαρμόσω τις επιλογές απόδοσης για διαφορετικές μορφές εξόδου;
Οπωσδήποτε, το GroupDocs.Viewer παρέχει εκτενείς επιλογές για την προσαρμογή των παραμέτρων απόδοσης με βάση τις απαιτήσεις σας.
### Υπάρχει κάποιο φόρουμ κοινότητας για υποστήριξη GroupDocs.Viewer;
 Ναι, μπορείτε να ζητήσετε βοήθεια και να συνεργαστείτε με την κοινότητα GroupDocs.Viewer στο φόρουμ υποστήριξης[εδώ](https://forum.groupdocs.com/c/viewer/9).