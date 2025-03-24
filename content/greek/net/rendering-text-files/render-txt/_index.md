---
title: Απόδοση αρχείων κειμένου (.txt)
linktitle: Απόδοση αρχείων κειμένου (.txt)
second_title: GroupDocs.Viewer .NET API
description: Εξερευνήστε την απρόσκοπτη μετατροπή αρχείων κειμένου σε πολλαπλές μορφές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Βελτιώστε τις δυνατότητες διαχείρισης εγγράφων σας χωρίς κόπο.
weight: 10
url: /el/net/rendering-text-files/render-txt/
---

# Απόδοση αρχείων κειμένου (.txt)

## Εισαγωγή
Στον τομέα της διαχείρισης και χειρισμού εγγράφων, το GroupDocs.Viewer για .NET αναδεικνύεται ως ένα ισχυρό εργαλείο, προσφέροντας μια πληθώρα λειτουργιών για την αποτελεσματική απόδοση διαφόρων μορφών εγγράφων. Αυτό το άρθρο εμβαθύνει στις περιπλοκές της χρήσης του GroupDocs.Viewer για .NET για την απόδοση αρχείων κειμένου (.txt) σε πολλές μορφές. Είτε σκοπεύετε να μετατρέψετε αρχεία κειμένου σε HTML, JPG, PNG ή PDF, το GroupDocs.Viewer σάς εξοπλίζει με τα απαραίτητα εργαλεία για την απρόσκοπτη εκτέλεση αυτών των εργασιών.
## Προαπαιτούμενα
Πριν εμβαθύνετε στη διαδικασία μετατροπής, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Εγκατάσταση του GroupDocs.Viewer για .NET
 Βεβαιωθείτε ότι έχετε εγκαταστήσει το GroupDocs.Viewer για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να κατεβάσετε τα απαραίτητα αρχεία από το[δικτυακός τόπος](https://releases.groupdocs.com/viewer/net/).
### 2. Βασική εξοικείωση με το .NET Framework
Εξοικειωθείτε με τα βασικά του πλαισίου .NET, συμπεριλαμβανομένου του τρόπου ρύθμισης ενός έργου και χρήσης βιβλιοθηκών στη βάση κωδίκων σας.
### 3. Δείγματα αρχείων κειμένου
Προετοιμάστε δείγματα αρχείων κειμένου (.txt) που σκοπεύετε να μετατρέψετε. Αυτά τα αρχεία θα χρησιμεύσουν ως είσοδος για τη διαδικασία μετατροπής.

## Εισαγωγή χώρων ονομάτων
Πριν ξεκινήσετε τη διαδικασία μετατροπής, φροντίστε να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας. Αυτό σας επιτρέπει να έχετε απρόσκοπτη πρόσβαση στις λειτουργίες που παρέχονται από το GroupDocs.Viewer για .NET.
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
string outputDirectory = "Your Document Directory";
```
Ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα για να σας καθοδηγήσουμε αποτελεσματικά στη διαδικασία μετατροπής:

## Βήμα 1: Ορίστε τη διαδρομή εξόδου HTML
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου HTML.
## Βήμα 2: Αποδώστε αρχεία κειμένου σε HTML πολλών σελίδων
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
 Στιγμιότυπο α`Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Διαμορφώστε`HtmlViewOptions` για ενσωματωμένους πόρους και αποδώστε το αρχείο κειμένου σε πολυσέλιδο HTML.
## Βήμα 3: Καθορίστε Μονοπάτι Εξόδου HTML μιας σελίδας
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου HTML μιας σελίδας.
## Βήμα 4: Αποδώστε αρχεία κειμένου σε HTML μίας σελίδας
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_2_TXT))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    options.RenderToSinglePage = true;
    viewer.View(options);
}
```
 Στιγμιότυπο α`Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Διαμορφώστε`HtmlViewOptions` για ενσωματωμένους πόρους και σύνολο`RenderToSinglePage` στο αληθινό. Αποδώστε το αρχείο κειμένου σε HTML μιας σελίδας.
## Βήμα 5: Καθορίστε τη διαδρομή εξόδου JPG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου JPG.
## Βήμα 6: Αποδώστε αρχεία κειμένου σε JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Στιγμιότυπο α`Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Διαμορφώστε`JpgViewOptions` για τη διαδρομή εξόδου και αποδώστε το αρχείο κειμένου σε μορφή JPG.
## Βήμα 7: Καθορίστε τη διαδρομή εξόδου PNG
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου PNG.
## Βήμα 8: Αποδώστε αρχεία κειμένου σε PNG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Στιγμιότυπο α`Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Διαμορφώστε`PngViewOptions` για τη διαδρομή εξόδου και αποδώστε το αρχείο κειμένου σε μορφή PNG.
## Βήμα 9: Καθορίστε τη διαδρομή εξόδου PDF
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");
```
Καθορίστε την πλήρη διαδρομή για το αρχείο εξόδου PDF.
## Βήμα 10: Αποδώστε αρχεία κειμένου σε PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_TXT))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
 Στιγμιότυπο α`Viewer` αντικείμενο με τη διαδρομή προς το αρχείο κειμένου. Διαμορφώστε`PdfViewOptions` για τη διαδρομή εξόδου και αποδώστε το αρχείο κειμένου σε μορφή PDF.

## συμπέρασμα
Εν κατακλείδι, το GroupDocs.Viewer για .NET δίνει τη δυνατότητα στους προγραμματιστές να αποδίδουν εύκολα αρχεία κειμένου σε διάφορες μορφές, όπως HTML, JPG, PNG και PDF. Ακολουθώντας τον οδηγό βήμα προς βήμα που περιγράφεται σε αυτό το άρθρο, μπορείτε να ενσωματώσετε απρόσκοπτα το GroupDocs.Viewer στις εφαρμογές σας .NET, βελτιώνοντας τις δυνατότητες διαχείρισης εγγράφων.
## Συχνές ερωτήσεις
### Ε: Είναι το GroupDocs.Viewer για .NET συμβατό με όλες τις εκδόσεις του πλαισίου .NET;
Ναι, το GroupDocs.Viewer για .NET έχει σχεδιαστεί για να είναι συμβατό με ένα ευρύ φάσμα εκδόσεων πλαισίου .NET, διασφαλίζοντας ευελιξία και ευελιξία στην ανάπτυξη.
### Ε: Μπορώ να προσαρμόσω την εμφάνιση εξόδου των παραγόμενων εγγράφων;
Απολύτως! Το GroupDocs.Viewer προσφέρει εκτενείς επιλογές προσαρμογής, επιτρέποντας στους προγραμματιστές να προσαρμόσουν την εμφάνιση των αποδοθέντων εγγράφων σύμφωνα με τις προτιμήσεις και τις απαιτήσεις τους.
### Ε: Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το GroupDocs.Viewer για .NET;
 Ναι, μπορείτε να εξερευνήσετε τις λειτουργίες του GroupDocs.Viewer για .NET αποκτώντας πρόσβαση στη δωρεάν δοκιμή που είναι διαθέσιμη στο[δικτυακός τόπος]( https://releases.groupdocs.com/).
### Ε: Πώς μπορώ να λάβω υποστήριξη ή να ζητήσω βοήθεια με το GroupDocs.Viewer για .NET;
 Για οποιαδήποτε απορία, υποστήριξη ή βοήθεια σχετικά με το GroupDocs.Viewer για .NET, μπορείτε να επισκεφτείτε το ειδικό φόρουμ υποστήριξης στο οποίο είναι προσβάσιμο[εδώ](https://forum.groupdocs.com/c/viewer/9).
### Ε: Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το GroupDocs.Viewer για .NET;
Ναι, οι προσωρινές άδειες είναι διαθέσιμες για αγορά, παρέχοντας στους χρήστες ευελιξία και ευκολία στη χρήση του GroupDocs.Viewer για .NET για συγκεκριμένες χρονικές περιόδους.