---
title: Ακύρωση απόδοσης με διακριτικό ακύρωσης
linktitle: Ακύρωση απόδοσης με διακριτικό ακύρωσης
second_title: GroupDocs.Viewer .NET API
description: Ενσωματώστε απρόσκοπτα το Groupdocs.Viewer για .NET στα έργα σας .NET για αποτελεσματική προβολή εγγράφων.
weight: 11
url: /el/net/rendering-options/cancel-render-cancellation-token/
---
## Εισαγωγή
Το Groupdocs.Viewer για .NET είναι ένα ισχυρό εργαλείο που έχει σχεδιαστεί για να απλοποιεί την προβολή και την επεξεργασία εγγράφων σε εφαρμογές .NET. Είτε ασχολείστε με αρχεία PDF, έγγραφα του Microsoft Office ή άλλες κοινές μορφές, αυτή η βιβλιοθήκη προσφέρει ισχυρή λειτουργικότητα για την απρόσκοπτη ενσωμάτωση των δυνατοτήτων προβολής εγγράφων στα έργα σας .NET.
## Προαπαιτούμενα
Πριν ξεκινήσετε την ενσωμάτωση του Groupdocs.Viewer για .NET, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Εγκατάσταση: Κατεβάστε και εγκαταστήστε τη βιβλιοθήκη Groupdocs.Viewer για .NET από την παρεχόμενη[σύνδεσμος λήψης](https://releases.groupdocs.com/viewer/net/).
   
2.  Άδεια χρήσης: Λάβετε άδεια από[Groupdocs](https://purchase.groupdocs.com/buy) για να ξεκλειδώσετε πλήρως τις δυνατότητες της βιβλιοθήκης. Εναλλακτικά, μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμή χρησιμοποιώντας το[προσωρινή άδεια](https://purchase.groupdocs.com/temporary-license/).
   
3. Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα συμβατό περιβάλλον ανάπτυξης, συμπεριλαμβανομένου του Visual Studio ή οποιουδήποτε άλλου .NET IDE της επιλογής σας.

## Εισαγωγή χώρων ονομάτων
Για να χρησιμοποιήσετε αποτελεσματικά το Groupdocs.Viewer για .NET, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων στο έργο σας. Ακολουθήστε αυτά τα βήματα:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Τώρα, ας αναλύσουμε το παρεχόμενο παράδειγμα σε πολλαπλά βήματα για καλύτερη κατανόηση και εφαρμογή:
## Βήμα 1: Ορισμός καταλόγου εξόδου
```csharp
string outputDirectory = "Your Document Directory";
```
Αυτό το βήμα ορίζει τον κατάλογο όπου θα αποθηκευτούν οι σελίδες εγγράφων που έχουν αποδοθεί.
## Βήμα 2: Ορισμός μορφής διαδρομής αρχείου σελίδας
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Εδώ, ορίζουμε τη μορφή για τις διαδρομές αρχείων μεμονωμένων σελίδων εγγράφων.
## Βήμα 3: Αρχικοποιήστε το CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
Το CancellationTokenSource χρησιμοποιείται για τη δημιουργία παρουσιών CancellationToken που μπορούν να χρησιμοποιηθούν για την ακύρωση ασύγχρονων λειτουργιών.
## Βήμα 4: Λήψη CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Αυτό το βήμα ανακτά το διακριτικό από το CancellationTokenSource, το οποίο θα χρησιμοποιηθεί για την ακύρωση της λειτουργίας απόδοσης.
## Βήμα 5: Απόδοση σελίδων εγγράφου
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Εδώ, ξεκινάμε την απόδοση των σελίδων του εγγράφου ασύγχρονα χρησιμοποιώντας την Task.Run(). Η παρουσία του Viewer δημιουργείται με το καθορισμένο αρχείο εγγράφου (SAMPLE_DOCX) και διαμορφώνονται οι επιλογές απόδοσης. Στη συνέχεια, ξεκινά η διαδικασία απόδοσης χρησιμοποιώντας τη μέθοδο View της κλάσης Viewer.
## Βήμα 6: Ορίστε το χρονικό όριο απόδοσης
```csharp
cancellationTokenSource.CancelAfter(10);
```
Αυτό το βήμα ορίζει ένα χρονικό όριο 10 χιλιοστών του δευτερολέπτου για τη λειτουργία απόδοσης. Εάν η λειτουργία υπερβεί αυτό το χρονικό όριο, θα ακυρωθεί αυτόματα.
## Βήμα 7: Εμφάνιση μηνύματος επιτυχίας
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Τέλος, εμφανίζεται ένα μήνυμα επιτυχίας που υποδεικνύει ότι το έγγραφο έχει αποδοθεί με επιτυχία.

## συμπέρασμα
Σε αυτό το σεμινάριο, καλύψαμε τα βασικά για την ενσωμάτωση του Groupdocs.Viewer για .NET στα έργα σας. Ακολουθώντας τα βήματα που περιγράφονται παραπάνω, μπορείτε να ενσωματώσετε απρόσκοπτα τις δυνατότητες προβολής εγγράφων στις εφαρμογές σας .NET, βελτιώνοντας την εμπειρία χρήστη και την παραγωγικότητα.
## Συχνές ερωτήσεις
### Είναι το Groupdocs.Viewer για .NET συμβατό με όλες τις μορφές εγγράφων;
Το Groupdocs.Viewer για .NET υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, όπως PDF, έγγραφα του Microsoft Office, εικόνες και άλλα.
### Μπορώ να προσαρμόσω την εμφάνιση των σελίδων του παρατιθέμενου εγγράφου;
Ναι, μπορείτε να προσαρμόσετε διάφορες πτυχές της διαδικασίας απόδοσης, όπως το μέγεθος σελίδας, η ποιότητα, η υδατοσήμανση και άλλα.
### Απαιτεί το Groupdocs.Viewer για .NET σύνδεση στο Διαδίκτυο;
Όχι, το Groupdocs.Viewer για .NET λειτουργεί τοπικά στο περιβάλλον .NET σας και δεν απαιτεί σύνδεση στο διαδίκτυο για την προβολή εγγράφων.
### Είναι διαθέσιμη τεχνική υποστήριξη για το Groupdocs.Viewer για .NET;
 Ναι, η τεχνική υποστήριξη είναι διαθέσιμη μέσω του[φόρουμ Groupdocs](https://forum.groupdocs.com/c/viewer/9), όπου μπορείτε να κάνετε ερωτήσεις, να αναφέρετε προβλήματα και να αλληλεπιδράτε με την κοινότητα.
### Μπορώ να δοκιμάσω το Groupdocs.Viewer για .NET πριν το αγοράσω;
 Ναι, μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμή χρησιμοποιώντας τα παρεχόμενα[δοκιμαστική έκδοση](https://releases.groupdocs.com/).