---
title: Ορισμός μορφής ημερομηνίας ώρας και μετατόπισης ζώνης ώρας (email)
linktitle: Ορισμός μορφής ημερομηνίας ώρας και μετατόπισης ζώνης ώρας (email)
second_title: GroupDocs.Viewer .NET API
description: Ενσωματώστε απρόσκοπτα το GroupDocs.Viewer για .NET στις εφαρμογές σας για ισχυρές δυνατότητες προβολής εγγράφων. Βελτιώστε την εμπειρία χρήστη με προσαρμόσιμες επιλογές.
type: docs
weight: 11
url: /el/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Εισαγωγή
Το GroupDocs.Viewer για .NET είναι ένα ισχυρό εργαλείο που επιτρέπει στους προγραμματιστές να ενσωματώνουν απρόσκοπτα τις δυνατότητες προβολής εγγράφων στις εφαρμογές τους .NET. Με το GroupDocs.Viewer, μπορείτε να εμφανίσετε ένα ευρύ φάσμα μορφών εγγράφων, συμπεριλαμβανομένων των PDF, εγγράφων του Microsoft Office, εικόνων και πιο άμεσα εντός της εφαρμογής σας, χωρίς να χρειάζεστε εξωτερικές προσθήκες ή προγράμματα προβολής. Σε αυτό το ολοκληρωμένο σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία ρύθμισης του GroupDocs.Viewer για .NET, εξερευνώντας τις δυνατότητές του και δείχνοντας πώς να το χρησιμοποιήσετε αποτελεσματικά για να βελτιώσετε τις δυνατότητες προβολής εγγράφων της εφαρμογής σας.
## Προαπαιτούμενα
Πριν προχωρήσετε σε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:
1. Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο σύστημά σας. Το GroupDocs.Viewer για .NET είναι πλήρως συμβατό με το Visual Studio, επιτρέποντας την απρόσκοπτη ενσωμάτωση στα έργα σας .NET.
2.  GroupDocs.Viewer για .NET: Κατεβάστε και εγκαταστήστε το GroupDocs.Viewer για .NET από το[σύνδεσμος λήψης](https://releases.groupdocs.com/viewer/net/). Ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται για να ρυθμίσετε τη βιβλιοθήκη στο περιβάλλον ανάπτυξης σας.
3. .NET Framework: Βεβαιωθείτε ότι έχετε εγκατεστημένη την κατάλληλη έκδοση του .NET Framework. Το GroupDocs.Viewer για .NET υποστηρίζει διάφορες εκδόσεις του .NET Framework, συμπεριλαμβανομένων των .NET Core και .NET Standard.

## Εισαγωγή χώρων ονομάτων
Για να χρησιμοποιήσετε αποτελεσματικά το GroupDocs.Viewer για .NET, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας. Ακολουθήστε αυτά τα βήματα για να εισαγάγετε τους απαιτούμενους χώρους ονομάτων:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλά βήματα για να κατανοήσουμε κάθε στοιχείο και τη λειτουργικότητά του.
## Βήμα 1: Ορίστε τον κατάλογο εξόδου και τη διαδρομή αρχείου
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
Σε αυτό το βήμα, ορίζουμε τον κατάλογο εξόδου όπου θα αποθηκευτεί το αποδοθέν έγγραφο και καθορίζουμε τη διαδρομή αρχείου για το αρχείο HTML εξόδου.
## Βήμα 2: Δημιουργία αντικειμένου προγράμματος προβολής
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Εδώ, δημιουργούμε μια νέα παρουσία του`Viewer` κλάση, περνώντας τη διαδρομή του εγγράφου που θα προβληθεί (σε αυτήν την περίπτωση, ένα δείγμα αρχείου EML) ως παράμετρος.
## Βήμα 3: Ορίστε τις επιλογές προβολής HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
Σε αυτό το βήμα, διαμορφώνουμε τις επιλογές προβολής HTML για την απόδοση του εγγράφου, καθορίζοντας τη διαδρομή αρχείου εξόδου για το έγγραφο HTML που αποδίδεται.
## Βήμα 4: Ορίστε τη μορφή ημερομηνίας ώρας και τη μετατόπιση ζώνης ώρας
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Εδώ, προσαρμόζουμε τη μορφή ημερομηνίας και ώρας για τα μηνύματα email και ορίζουμε τη μετατόπιση ζώνης ώρας σύμφωνα με την επιθυμητή ζώνη ώρας.
## Βήμα 5: Απόδοση εγγράφου
```csharp
viewer.View(options);
```
 Τέλος, ονομάζουμε το`View` μέθοδος του`Viewer` αντικείμενο, περνώντας τις διαμορφωμένες επιλογές προβολής HTML για απόδοση του εγγράφου σε μορφή HTML.
## Βήμα 6: Εμφάνιση καταλόγου εξόδου
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Αυτό το βήμα απλώς εμφανίζει ένα μήνυμα που υποδεικνύει την επιτυχή απόδοση του εγγράφου και παρέχει τη διαδρομή προς τον κατάλογο εξόδου όπου βρίσκεται το αποδοθέν έγγραφο HTML.

## συμπέρασμα
Το GroupDocs.Viewer για .NET προσφέρει μια ισχυρή λύση για την ενσωμάτωση δυνατοτήτων προβολής εγγράφων στις εφαρμογές σας .NET. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε εύκολα να ρυθμίσετε το GroupDocs.Viewer, να εισαγάγετε τους απαραίτητους χώρους ονομάτων και να χρησιμοποιήσετε τις δυνατότητές του για την απόδοση εγγράφων με προσαρμόσιμες επιλογές. Είτε εργάζεστε με αρχεία PDF, έγγραφα του Microsoft Office ή άλλες μορφές, το GroupDocs.Viewer απλοποιεί τη διαδικασία προβολής εγγράφων, βελτιώνοντας την εμπειρία χρήστη των εφαρμογών σας.
## Συχνές ερωτήσεις
### Είναι το GroupDocs.Viewer συμβατό με .NET Core;
Ναι, το GroupDocs.Viewer για .NET υποστηρίζει .NET Core, επιτρέποντας τη συμβατότητα μεταξύ πλατφορμών για τις εφαρμογές σας.
### Μπορώ να προσαρμόσω την εμφάνιση των αποδοθέντων εγγράφων;
Απολύτως! Το GroupDocs.Viewer παρέχει διάφορες επιλογές προσαρμογής, συμπεριλαμβανομένων των επιπέδων ζουμ, της περιστροφής σελίδας και πολλά άλλα για να προσαρμόσετε την εμπειρία προβολής σύμφωνα με τις προτιμήσεις σας.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για δοκιμαστικούς σκοπούς;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης του GroupDocs.Viewer για .NET από το[Σύνδεσμος ιστοσελίδας](https://releases.groupdocs.com/viewer/net/) για να αξιολογήσετε τα χαρακτηριστικά του πριν κάνετε μια αγορά.
### Υποστηρίζει το GroupDocs.Viewer την απόδοση εγγράφων που προστατεύονται με κωδικό πρόσβασης;
Ναι, το GroupDocs.Viewer διαθέτει ενσωματωμένη υποστήριξη για την απόδοση εγγράφων που προστατεύονται με κωδικό πρόσβασης, διασφαλίζοντας την ασφαλή προβολή εγγράφων στις εφαρμογές σας.
### Πού μπορώ να βρω πρόσθετη υποστήριξη ή βοήθεια με το GroupDocs.Viewer;
 Για οποιαδήποτε τεχνική απορία ή βοήθεια, μπορείτε να επισκεφτείτε το GroupDocs.Viewer[δικαστήριο](https://forum.groupdocs.com/c/viewer/9) ή απευθυνθείτε στην ομάδα υποστήριξής τους για άμεση βοήθεια και καθοδήγηση.