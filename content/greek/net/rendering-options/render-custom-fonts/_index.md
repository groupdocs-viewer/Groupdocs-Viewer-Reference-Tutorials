---
title: Απόδοση με προσαρμοσμένες γραμματοσειρές
linktitle: Απόδοση με προσαρμοσμένες γραμματοσειρές
second_title: GroupDocs.Viewer .NET API
description: Μάθετε πώς να αποδίδετε έγγραφα με προσαρμοσμένες γραμματοσειρές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Βελτιώστε τις οπτικές παρουσιάσεις χωρίς κόπο.
type: docs
weight: 18
url: /el/net/rendering-options/render-custom-fonts/
---
## Εισαγωγή
Στον τομέα της ανάπτυξης .NET, το GroupDocs.Viewer προσφέρει μια ισχυρή λύση για την απόδοση εγγράφων διαφόρων μορφών. Μεταξύ των πολλών δυνατοτήτων του, το GroupDocs.Viewer επιτρέπει την απόδοση εγγράφων με προσαρμοσμένες γραμματοσειρές, προσθέτοντας ένα επίπεδο εξατομίκευσης και ευελιξίας στις εφαρμογές σας.
## Προαπαιτούμενα
Πριν ξεκινήσετε την απόδοση εγγράφων με προσαρμοσμένες γραμματοσειρές χρησιμοποιώντας το GroupDocs.Viewer για .NET, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Εγκαταστήστε το GroupDocs.Viewer για .NET
Για να χρησιμοποιήσετε το GroupDocs.Viewer για .NET, πρέπει να το έχετε εγκαταστήσει στο περιβάλλον ανάπτυξης σας. Μπορείτε να κατεβάσετε το απαραίτητο πακέτο από τον παρεχόμενο σύνδεσμο:
[Κατεβάστε το GroupDocs.Viewer για .NET](https://releases.groupdocs.com/viewer/net/)
### 2. Λήψη γραμματοσειρών
Προετοιμάστε τις προσαρμοσμένες γραμματοσειρές που θέλετε να χρησιμοποιήσετε για την απόδοση εγγράφων. Βεβαιωθείτε ότι αυτές οι γραμματοσειρές είναι προσβάσιμες στο περιβάλλον της εφαρμογής σας.
### 3. Δημιουργήστε ένα περιβάλλον ανάπτυξης
Δημιουργήστε ένα λειτουργικό περιβάλλον ανάπτυξης .NET στο σύστημά σας. Βεβαιωθείτε ότι έχετε εγκαταστήσει τα απαραίτητα εργαλεία και πλαίσια.
### 4. Βασική κατανόηση της C# και του .NET
Εξοικειωθείτε με τη γλώσσα προγραμματισμού C# και τα βασικά του πλαισίου .NET για να ακολουθήσετε αποτελεσματικά μαζί με το σεμινάριο.

## Εισαγωγή χώρων ονομάτων
Για να αποδώσετε έγγραφα με προσαρμοσμένες γραμματοσειρές χρησιμοποιώντας το GroupDocs.Viewer για .NET, πρέπει να εισαγάγετε τους απαιτούμενους χώρους ονομάτων στο έργο σας.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Fonts;
using GroupDocs.Viewer.Options;
```

## Βήμα 1: Ρύθμιση πηγών γραμματοσειράς
Αρχικά, ορίστε τις πηγές γραμματοσειράς που θα χρησιμοποιηθούν για την απόδοση εγγράφων. Αυτό το βήμα διασφαλίζει ότι το GroupDocs.Viewer μπορεί να έχει πρόσβαση στις προσαρμοσμένες γραμματοσειρές.
```csharp
FontSettings.SetFontSources(
    new FolderFontSource(Utils.FontsPath, Fonts.SearchOption.TopFolderOnly));
```
## Βήμα 2: Ορισμός καταλόγου εξόδου
Καθορίστε τον κατάλογο στον οποίο θέλετε να αποθηκευτούν τα αποδοθέντα έγγραφα.
```csharp
string outputDirectory = "Your Document Directory";
```
## Βήμα 3: Καθορίστε τη μορφή διαδρομής αρχείου σελίδας
Ορίστε τη μορφή για την ονομασία των αρχείων HTML εξόδου που περιέχουν τις σελίδες εγγράφου που έχουν αποδοθεί.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Βήμα 4: Απόδοση εγγράφου με προσαρμοσμένες γραμματοσειρές
 Χρησιμοποιήστε το GroupDocs.Viewer API για απόδοση του εγγράφου με προσαρμοσμένες γραμματοσειρές. Αντικαθιστώ`TestFiles.MISSING_FONT_ODG` με τη διαδρομή προς το έγγραφό σας.
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_ODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Βήμα 5: Εμφάνιση καταλόγου εξόδου
Ενημερώστε τον χρήστη σχετικά με τη θέση όπου αποθηκεύονται οι σελίδες του παραστατικού εγγράφου.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο απόδοσης εγγράφων με προσαρμοσμένες γραμματοσειρές χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ακολουθώντας τον οδηγό βήμα προς βήμα και αξιοποιώντας το παρεχόμενο παράδειγμα, μπορείτε να βελτιώσετε την οπτική παρουσίαση των εγγράφων στις εφαρμογές σας .NET.
## Συχνές ερωτήσεις
### Ε: Μπορώ να αποδώσω έγγραφα με προσαρμοσμένες γραμματοσειρές χρησιμοποιώντας το GroupDocs.Viewer για .NET σε εφαρμογές web;
Ναι, το GroupDocs.Viewer για .NET μπορεί να ενσωματωθεί τόσο σε επιτραπέζιους υπολογιστές όσο και σε εφαρμογές web για απόδοση εγγράφων με προσαρμοσμένες γραμματοσειρές.
### Ε: Είναι το GroupDocs.Viewer για .NET συμβατό με διάφορες μορφές εγγράφων;
Απολύτως! Το GroupDocs.Viewer υποστηρίζει ένα ευρύ φάσμα μορφών εγγράφων, όπως PDF, αρχεία Microsoft Office, εικόνες και άλλα.
### Ε: Υπάρχουν περιορισμοί στους τύπους προσαρμοσμένων γραμματοσειρών που μπορούν να χρησιμοποιηθούν;
Εφόσον οι προσαρμοσμένες γραμματοσειρές είναι προσβάσιμες στο περιβάλλον εφαρμογής, το GroupDocs.Viewer για .NET μπορεί να αποδίδει έγγραφα με αυτές τις γραμματοσειρές χωρίς περιορισμούς.
### Ε: Μπορώ να προσαρμόσω τη μορφή εξόδου των παραγόμενων εγγράφων;
Ναι, το GroupDocs.Viewer για .NET παρέχει επιλογές για την προσαρμογή της μορφής εξόδου, συμπεριλαμβανομένων HTML, μορφών εικόνας και PDF.
### Ε: Το GroupDocs.Viewer για .NET προσφέρει υποστήριξη και τεκμηρίωση για προγραμματιστές;
Σίγουρα! Το GroupDocs παρέχει ολοκληρωμένη τεκμηρίωση, φόρουμ για υποστήριξη και πόρους για να βοηθήσει τους προγραμματιστές να χρησιμοποιήσουν αποτελεσματικά το GroupDocs.Viewer.