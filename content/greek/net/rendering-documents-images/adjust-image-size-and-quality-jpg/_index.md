---
title: Προσαρμογή μεγέθους και ποιότητας εικόνας (JPG)
linktitle: Προσαρμογή μεγέθους και ποιότητας εικόνας (JPG)
second_title: GroupDocs.Viewer .NET API
description: Μάθετε πώς να βελτιστοποιείτε το μέγεθος και την ποιότητα της εικόνας σε μορφή JPEG χρησιμοποιώντας το Groupdocs.Viewer για .NET. Βελτιώστε την εμπειρία προβολής εγγράφων σας.
weight: 11
url: /el/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---

# Προσαρμογή μεγέθους και ποιότητας εικόνας (JPG)

## Εισαγωγή
Το Groupdocs.Viewer για .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να ενσωματώνουν απρόσκοπτα τη λειτουργία προβολής εγγράφων στις εφαρμογές τους .NET. Μια κοινή απαίτηση στις εφαρμογές προβολής εγγράφων είναι η δυνατότητα προσαρμογής του μεγέθους και της ποιότητας των εικόνων, ιδιαίτερα όταν πρόκειται για εικόνες JPEG (JPG). Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία προσαρμογής του μεγέθους και της ποιότητας της εικόνας χρησιμοποιώντας το Groupdocs.Viewer για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Βασική κατανόηση της γλώσσας προγραμματισμού C#.
2. Το Visual Studio είναι εγκατεστημένο στο σύστημά σας.
3.  Εγκαταστάθηκε το Groupdocs.Viewer για τη βιβλιοθήκη .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.groupdocs.com/viewer/net/).

## Εισαγωγή χώρων ονομάτων
Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στον κώδικα C#. Αυτοί οι χώροι ονομάτων παρέχουν πρόσβαση στις κλάσεις και τις μεθόδους που απαιτούνται για την εργασία με το Groupdocs.Viewer.
## Βήμα 1: Εισαγωγή χώρων ονομάτων
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Τώρα, ας αναλύσουμε το παράδειγμα κώδικα που παρέχεται σε πολλά βήματα για καλύτερη κατανόηση.
## Βήμα 2: Ορίστε τον κατάλογο εξόδου και τη μορφή διαδρομής αρχείου σελίδας
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
Σε αυτό το βήμα, καθορίζουμε τον κατάλογο εξόδου όπου θα αποθηκευτούν οι εικόνες που αποδίδονται και ορίζουμε τη μορφή για τη διαδρομή αρχείου κάθε εικόνας σελίδας.
## Βήμα 3: Αρχικοποιήστε το πρόγραμμα προβολής και διαμορφώστε τις επιλογές προβολής JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Εδώ, αρχικοποιούμε το αντικείμενο Viewer με τη διαδρομή προς το έγγραφο που πρόκειται να προβληθεί. Στη συνέχεια, δημιουργούμε μια παρουσία του JpgViewOptions και ορίζουμε το επιθυμητό πλάτος και ύψος για τις εικόνες JPEG.
## Βήμα 4: Απόδοση εγγράφου πηγής
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Τέλος, εκτυπώνουμε ένα μήνυμα που υποδεικνύει την επιτυχή απόδοση του εγγράφου προέλευσης και τη θέση όπου αποθηκεύονται οι εικόνες εξόδου.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να προσαρμόζουμε το μέγεθος και την ποιότητα των εικόνων JPEG χρησιμοποιώντας το Groupdocs.Viewer για .NET. Ακολουθώντας τα βήματα που περιγράφονται παραπάνω, μπορείτε εύκολα να ενσωματώσετε αυτήν τη λειτουργία στις εφαρμογές σας .NET, παρέχοντας στους χρήστες βελτιστοποιημένη εμπειρία προβολής εικόνων.
## Συχνές ερωτήσεις
### Μπορώ να ρυθμίσω και την ποιότητα της εικόνας;
Ναι, μπορείτε να προσαρμόσετε την ποιότητα της εικόνας ορίζοντας την ιδιότητα Ποιότητα στις Επιλογές JpgView.
### Ποιες μορφές εγγράφων υποστηρίζονται από το Groupdocs.Viewer για .NET;
Το Groupdocs.Viewer για .NET υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, συμπεριλαμβανομένων των DOCX, PDF, PPTX, XLSX και άλλων.
### Είναι το Groupdocs.Viewer για .NET συμβατό με .NET Core;
Ναι, το Groupdocs.Viewer για .NET είναι συμβατό με το .NET Core μαζί με το παραδοσιακό .NET Framework.
### Μπορώ να προσαρμόσω τη μορφή ονομασίας του αρχείου εξόδου;
Ναι, μπορείτε να προσαρμόσετε τη μορφή ονομασίας του αρχείου εξόδου τροποποιώντας τη μεταβλητή pageFilePathFormat στον κώδικα.
### Το Groupdocs.Viewer για .NET υποστηρίζει σχολιασμούς εγγράφων;
Ναι, το Groupdocs.Viewer για .NET παρέχει ολοκληρωμένη υποστήριξη για σχολιασμούς εγγράφων, όπως επισήμανση κειμένου, υπογράμμιση και σχολιασμό.