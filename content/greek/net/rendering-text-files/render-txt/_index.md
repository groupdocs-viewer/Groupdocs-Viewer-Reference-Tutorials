---
"description": "Εξερευνήστε την απρόσκοπτη μετατροπή αρχείων κειμένου σε πολλαπλές μορφές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Βελτιώστε τις δυνατότητες διαχείρισης εγγράφων σας χωρίς κόπο."
"linktitle": "Απόδοση αρχείων κειμένου (.txt)"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση αρχείων κειμένου (.txt)"
"url": "/el/net/rendering-text-files/render-txt/"
"weight": 10
---

# Απόδοση αρχείων κειμένου (.txt)

## Εισαγωγή
Στον τομέα της διαχείρισης και χειρισμού εγγράφων, το GroupDocs.Viewer για .NET αναδεικνύεται ως ένα ισχυρό εργαλείο, προσφέροντας μια πληθώρα λειτουργιών για την αποτελεσματική απόδοση διαφόρων μορφών εγγράφων. Αυτό το άρθρο εμβαθύνει στις περιπλοκές της χρήσης του GroupDocs.Viewer για .NET για την απόδοση αρχείων κειμένου (.txt) σε πολλαπλές μορφές. Είτε σκοπεύετε να μετατρέψετε αρχεία κειμένου σε HTML, JPG, PNG ή PDF, το GroupDocs.Viewer σας εξοπλίζει με τα απαραίτητα εργαλεία για να ολοκληρώσετε αυτές τις εργασίες απρόσκοπτα.
## Προαπαιτούμενα
Πριν ξεκινήσετε τη διαδικασία μετατροπής, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Εγκατάσταση του GroupDocs.Viewer για .NET
Βεβαιωθείτε ότι έχετε εγκαταστήσει το GroupDocs.Viewer για .NET στο περιβάλλον ανάπτυξής σας. Μπορείτε να κατεβάσετε τα απαραίτητα αρχεία από το [δικτυακός τόπος](https://releases.groupdocs.com/viewer/net/).
### 2. Βασική εξοικείωση με το .NET Framework
Εξοικειωθείτε με τα βασικά του .NET framework, συμπεριλαμβανομένου του τρόπου δημιουργίας ενός έργου και χρήσης βιβλιοθηκών εντός της βάσης κώδικα.
### 3. Δείγματα αρχείων κειμένου
Προετοιμάστε δείγματα αρχείων κειμένου (.txt) που σκοπεύετε να μετατρέψετε. Αυτά τα αρχεία θα χρησιμεύσουν ως δεδομένα εισόδου για τη διαδικασία μετατροπής.

## Εισαγωγή χώρων ονομάτων
Πριν ξεκινήσετε τη διαδικασία μετατροπής, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων στο έργο σας. Αυτό σας επιτρέπει να έχετε απρόσκοπτη πρόσβαση στις λειτουργίες που παρέχονται από το GroupDocs.Viewer για .NET.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα για να σας καθοδηγήσουμε αποτελεσματικά στη διαδικασία μετατροπής:

## Βήμα 1: Ορισμός διαδρομής εξόδου HTML
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου HTML.
## Βήμα 2: Απόδοση αρχείων κειμένου σε HTML πολλαπλών σελίδων
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
Δημιουργήστε ένα υπόδειγμα `Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Ρύθμιση παραμέτρων `HtmlViewOptions` για ενσωματωμένους πόρους και απόδοση του αρχείου κειμένου σε HTML πολλαπλών σελίδων.
## Βήμα 3: Ορισμός διαδρομής εξόδου HTML μίας σελίδας
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου HTML μίας σελίδας.
## Βήμα 4: Απόδοση αρχείων κειμένου σε HTML μίας σελίδας
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
Δημιουργήστε ένα υπόδειγμα `Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Ρύθμιση παραμέτρων `HtmlViewOptions` για ενσωματωμένους πόρους και σύνολο `RenderToSinglePage` σε true. Αποδώστε το αρχείο κειμένου σε HTML μίας σελίδας.
## Βήμα 5: Ορισμός διαδρομής εξόδου JPG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου JPG.
## Βήμα 6: Απόδοση αρχείων κειμένου σε JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Δημιουργήστε ένα υπόδειγμα `Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Ρύθμιση παραμέτρων `JpgViewOptions` για τη διαδρομή εξόδου και να αποδώσετε το αρχείο κειμένου σε μορφή JPG.
## Βήμα 7: Ορισμός διαδρομής εξόδου PNG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου PNG.
## Βήμα 8: Απόδοση αρχείων κειμένου σε PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Δημιουργήστε ένα υπόδειγμα `Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Ρύθμιση παραμέτρων `PngViewOptions` για τη διαδρομή εξόδου και να αποδώσετε το αρχείο κειμένου σε μορφή PNG.
## Βήμα 9: Ορισμός διαδρομής εξόδου PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου PDF.
## Βήμα 10: Απόδοση αρχείων κειμένου σε PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Δημιουργήστε ένα υπόδειγμα `Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Ρύθμιση παραμέτρων `PdfViewOptions` για τη διαδρομή εξόδου και να αποδώσετε το αρχείο κειμένου σε μορφή PDF.

## Σύναψη
Συμπερασματικά, το GroupDocs.Viewer για .NET δίνει τη δυνατότητα στους προγραμματιστές να αποδίδουν εύκολα αρχεία κειμένου σε διάφορες μορφές, όπως HTML, JPG, PNG και PDF. Ακολουθώντας τον αναλυτικό οδηγό που περιγράφεται σε αυτό το άρθρο, μπορείτε να ενσωματώσετε απρόσκοπτα το GroupDocs.Viewer στις εφαρμογές .NET σας, βελτιώνοντας τις δυνατότητες διαχείρισης εγγράφων.
## Συχνές ερωτήσεις
### Ε: Είναι το GroupDocs.Viewer για .NET συμβατό με όλες τις εκδόσεις του .NET framework;
Ναι, το GroupDocs.Viewer για .NET έχει σχεδιαστεί ώστε να είναι συμβατό με ένα ευρύ φάσμα εκδόσεων του .NET framework, εξασφαλίζοντας ευελιξία και ευελιξία στην ανάπτυξη.
### Ε: Μπορώ να προσαρμόσω την εμφάνιση εξόδου των εγγράφων που έχουν αποδοθεί;
Απολύτως! Το GroupDocs.Viewer προσφέρει εκτεταμένες επιλογές προσαρμογής, επιτρέποντας στους προγραμματιστές να προσαρμόσουν την εμφάνιση των εγγράφων που αποδίδονται σύμφωνα με τα πνευματικά τους δικαιώματα και τις απαιτήσεις τους.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το GroupDocs.Viewer για .NET;
Ναι, μπορείτε να εξερευνήσετε τις λειτουργίες του GroupDocs.Viewer για .NET αποκτώντας πρόσβαση στη δωρεάν δοκιμαστική έκδοση που είναι διαθέσιμη στο [δικτυακός τόπος]( https://releases.groupdocs.com/).
### Ε: Πώς μπορώ να λάβω υποστήριξη ή να ζητήσω βοήθεια με το GroupDocs.Viewer για .NET;
Για οποιεσδήποτε ερωτήσεις, υποστήριξη ή βοήθεια σχετικά με το GroupDocs.Viewer για .NET, μπορείτε να επισκεφθείτε το ειδικό φόρουμ υποστήριξης που είναι προσβάσιμο [εδώ](https://forum.groupdocs.com/c/viewer/9).
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το GroupDocs.Viewer για .NET;
Ναι, διατίθενται προσωρινές άδειες χρήσης προς αγορά, παρέχοντας στους χρήστες ευελιξία και ευκολία στη χρήση του GroupDocs.Viewer για .NET για συγκεκριμένες χρονικές περιόδους.