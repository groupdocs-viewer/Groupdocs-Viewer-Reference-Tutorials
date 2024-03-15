---
title: Φόρτωση εγγράφων που προστατεύονται με κωδικό πρόσβασης
linktitle: Φόρτωση εγγράφων που προστατεύονται με κωδικό πρόσβασης
second_title: GroupDocs.Viewer .NET API
description: Ενσωματώστε εύκολα την προβολή εγγράφων που προστατεύεται με κωδικό πρόσβασης σε εφαρμογές .NET χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ακολουθήστε το βήμα προς βήμα σεμινάριο μας για απρόσκοπτη.
type: docs
weight: 12
url: /el/net/advanced-loading/load-password-protected-document/
---
## Εισαγωγή
Στη σημερινή ψηφιακή εποχή, η διαχείριση και η απρόσκοπτη προβολή διαφόρων μορφών εγγράφων είναι μια αναγκαιότητα για πολλές επιχειρήσεις και ιδιώτες. Ευτυχώς, το GroupDocs.Viewer για .NET παρέχει μια ολοκληρωμένη λύση για τους προγραμματιστές .NET ώστε να ενσωματώνουν αβίαστα τις δυνατότητες προβολής εγγράφων στις εφαρμογές τους. Σε αυτό το σεμινάριο, θα εμβαθύνουμε σε μία από τις βασικές λειτουργίες του GroupDocs.Viewer: τη φόρτωση εγγράφων που προστατεύονται με κωδικό πρόσβασης. Θα αναλύσουμε τη διαδικασία βήμα προς βήμα, διασφαλίζοντας ότι οι προγραμματιστές μπορούν εύκολα να ακολουθήσουν και να εφαρμόσουν αυτήν τη δυνατότητα στα έργα τους.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:
### 1. Εγκαταστήστε το GroupDocs.Viewer για .NET
 Βεβαιωθείτε ότι έχετε εγκαταστήσει το GroupDocs.Viewer για .NET στο περιβάλλον ανάπτυξης σας. Μπορείτε να το κατεβάσετε από το[δικτυακός τόπος](https://releases.groupdocs.com/viewer/net/).
### 2. Αποκτήστε ένα έγγραφο που προστατεύεται με κωδικό πρόσβασης
Για λόγους δοκιμής, έχετε διαθέσιμο ένα έγγραφο που προστατεύεται με κωδικό πρόσβασης. Αυτό θα μας επιτρέψει να δείξουμε αποτελεσματικά τη διαδικασία φόρτωσης.

## Εισαγωγή χώρων ονομάτων
Πριν προχωρήσουμε με το σεμινάριο, ας εισάγουμε τους απαραίτητους χώρους ονομάτων στο έργο μας:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Βήμα 1: Ορισμός καταλόγου εξόδου
Αρχικά, καθορίστε τον κατάλογο στον οποίο θέλετε να αποθηκευτεί η απόδοση που αποδίδεται:
```csharp
string outputDirectory = "Your Document Directory";
```
 Αντικαθιστώ`"Your Document Directory"` με τη διαδρομή του καταλόγου που επιθυμείτε.
## Βήμα 2: Ορισμός μορφής διαδρομής αρχείου σελίδας
Στη συνέχεια, ορίστε τη μορφή για τη διαδρομή αρχείου κάθε σελίδας που αποδίδεται:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Αυτή η μορφή θα δημιουργήσει διαδρομές αρχείων όπως`"Your Document Directory/page_1.html"`, `"Your Document Directory/page_2.html"`, και ούτω καθεξής.
## Βήμα 3: Διαμόρφωση επιλογών φόρτωσης
Διαμορφώστε τις επιλογές φόρτωσης για το έγγραφο που προστατεύεται με κωδικό πρόσβασης, συμπεριλαμβανομένου του κωδικού πρόσβασης:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    Password = "12345"
};
```
 Αντικαθιστώ`"12345"` με τον πραγματικό κωδικό πρόσβασης του εγγράφου σας.
## Βήμα 4: Ξεκινήστε το πρόγραμμα προβολής
Εκκινήστε το GroupDocs.Viewer με τις επιλογές εγγράφου και φόρτωσης:
```csharp
using (Viewer viewer = new Viewer("Path_to_your_document", loadOptions))
{
    // Ο κώδικας για τις επιλογές προβολής θα προστεθεί στο επόμενο βήμα.
}
```
 Αντικαθιστώ`"Path_to_your_document"` με τη διαδρομή προς το έγγραφο που προστατεύεται με κωδικό πρόσβασης.
## Βήμα 5: Διαμορφώστε τις επιλογές προβολής HTML
Διαμορφώστε τις επιλογές προβολής HTML για την απόδοση του εγγράφου με ενσωματωμένους πόρους:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Βήμα 6: Απόδοση εγγράφου
Αποδώστε το έγγραφο χρησιμοποιώντας τις διαμορφωμένες επιλογές προβολής και προβολής:
```csharp
viewer.View(options);
```
## Βήμα 7: Εμφάνιση μηνύματος επιτυχίας
Ενημερώστε τον χρήστη ότι το έγγραφο έχει αποδοθεί με επιτυχία:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να φορτώνουμε έγγραφα που προστατεύονται με κωδικό πρόσβασης χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα, οι προγραμματιστές μπορούν να ενσωματώσουν απρόσκοπτα αυτή τη λειτουργία στις εφαρμογές τους .NET, επιτρέποντας στους χρήστες να βλέπουν προστατευμένα έγγραφα με ευκολία.
## Συχνές ερωτήσεις
### Μπορεί το GroupDocs.Viewer να χειριστεί άλλες μορφές εγγράφων εκτός από έγγραφα που προστατεύονται με κωδικό πρόσβασης;
Ναι, το GroupDocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, συμπεριλαμβανομένων των PDF, DOCX, XLSX, PPTX και άλλων.
### Είναι το GroupDocs.Viewer συμβατό με .NET Core;
Ναι, το GroupDocs.Viewer προσφέρει συμβατότητα με περιβάλλοντα .NET Framework και .NET Core.
### Μπορώ να προσαρμόσω τις επιλογές απόδοσης για τα έγγραφα;
Απολύτως! Το GroupDocs.Viewer παρέχει διάφορες επιλογές απόδοσης, επιτρέποντας στους προγραμματιστές να προσαρμόσουν την εμπειρία προβολής σύμφωνα με τις απαιτήσεις τους.
### Το GroupDocs.Viewer υποστηρίζει σχολιασμούς εγγράφων;
Ναι, το GroupDocs.Viewer υποστηρίζει σχολιασμούς εγγράφων, επιτρέποντας στους χρήστες να προσθέτουν σχόλια, επισημάνσεις και άλλους σχολιασμούς στα έγγραφα.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το GroupDocs.Viewer;
 Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή του GroupDocs.Viewer από το[δικτυακός τόπος](https://releases.groupdocs.com/).