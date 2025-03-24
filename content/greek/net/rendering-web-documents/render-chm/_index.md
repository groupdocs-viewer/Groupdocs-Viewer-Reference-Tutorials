---
title: Απόδοση αρχείων CHM
linktitle: Απόδοση αρχείων CHM
second_title: GroupDocs.Viewer .NET API
description: Μάθετε πώς να αποδίδετε αρχεία CHM στο .NET χρησιμοποιώντας το GroupDocs.Viewer. Μετατρέψτε το CHM σε μορφές HTML, JPG, PNG και PDF χωρίς κόπο.
weight: 10
url: /el/net/rendering-web-documents/render-chm/
---

# Απόδοση αρχείων CHM

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο απόδοσης αρχείων CHM (Compiled HTML Help) χρησιμοποιώντας το GroupDocs.Viewer για .NET. Το GroupDocs.Viewer για .NET είναι ένα ισχυρό API απόδοσης εγγράφων που επιτρέπει στους προγραμματιστές να εμφανίζουν πάνω από 170 τύπους εγγράφων στις εφαρμογές τους .NET χωρίς να απαιτούν εγκατάσταση εξωτερικού λογισμικού.

## Προαπαιτούμενα

Πριν ξεκινήσουμε την απόδοση αρχείων CHM, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

### Εγκατάσταση του GroupDocs.Viewer για .NET

 Για να ξεκινήσετε, πρέπει να εγκαταστήσετε το GroupDocs.Viewer για .NET. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από το[Ιστότοπος GroupDocs](https://releases.groupdocs.com/viewer/net/) ή εγκαταστήστε το μέσω του NuGet Package Manager εκτελώντας την ακόλουθη εντολή στην Κονσόλα Package Manager:

```bash
Install-Package GroupDocs.Viewer
```

## Εισαγωγή χώρων ονομάτων

Βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων στο έργο σας:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Τώρα ας αναλύσουμε τη διαδικασία απόδοσης σε πολλά βήματα:

## Βήμα 1: Ορισμός καταλόγου εξόδου

Καθορίστε τον κατάλογο στον οποίο θέλετε να αποθηκευτούν τα αποδοθέντα αρχεία:

```csharp
string outputDirectory = "Your Document Directory";
```

## Βήμα 2: Απόδοση σε HTML

Για να αποδώσετε αρχεία CHM σε HTML, χρησιμοποιήστε το ακόλουθο απόσπασμα κώδικα:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Ορίστε το σε true για να μετατρέψετε όλο το περιεχόμενο CHM σε μία σελίδα

    viewer.View(options); //Μετατροπή όλων των σελίδων
}
```

## Βήμα 3: Απόδοση σε JPG

Για να αποδώσετε αρχεία CHM σε εικόνες JPG, χρησιμοποιήστε το ακόλουθο απόσπασμα κώδικα:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Μετατροπή μόνο των σελίδων 1, 2, 3
}
```

## Βήμα 4: Απόδοση σε PNG

Για να αποδώσετε αρχεία CHM σε εικόνες PNG, χρησιμοποιήστε το ακόλουθο απόσπασμα κώδικα:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Μετατροπή μόνο των σελίδων 1, 2, 3
}
```

## Βήμα 5: Απόδοση σε PDF

Για να αποδώσετε αρχεία CHM σε ένα έγγραφο PDF, χρησιμοποιήστε το ακόλουθο απόσπασμα κώδικα:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Μετατροπή όλων των σελίδων
}
```

## Βήμα 6: Ελέγξτε την έξοδο

Μόλις ολοκληρωθεί η διαδικασία απόδοσης, ελέγξτε τον καθορισμένο κατάλογο εξόδου για τα αρχεία που έχουν αποδοθεί:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## συμπέρασμα

Η απόδοση αρχείων CHM χρησιμοποιώντας το GroupDocs.Viewer για .NET είναι μια απλή διαδικασία. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να μετατρέψετε αποτελεσματικά έγγραφα CHM σε διάφορες μορφές όπως HTML, εικόνες (JPG, PNG) και PDF στις εφαρμογές σας .NET.

## Συχνές ερωτήσεις

### Ε1: Μπορεί το GroupDocs.Viewer να αποδώσει άλλες μορφές εγγράφων εκτός από το CHM;

A1: Ναι, το GroupDocs.Viewer υποστηρίζει την απόδοση περισσότερων από 170 μορφών εγγράφων, συμπεριλαμβανομένων των PDF, DOCX, XLSX, PPTX και άλλων.

### Ε2: Είναι το GroupDocs.Viewer συμβατό με .NET Core;

A2: Ναι, το GroupDocs.Viewer υποστηρίζει .NET Core εκτός από το παραδοσιακό .NET Framework.

### Ε3: Μπορώ να προσαρμόσω τις επιλογές απόδοσης για διαφορετικές μορφές εξόδου;

A3: Ναι, το GroupDocs.Viewer παρέχει διάφορες επιλογές για την προσαρμογή της διαδικασίας απόδοσης, όπως καθορισμό αριθμών σελίδων, ρύθμιση ποιότητας εικόνας και διαμόρφωση διαδρομών εξόδου.

### Ε4: Απαιτεί το GroupDocs.Viewer εξωτερικές εξαρτήσεις για την απόδοση εγγράφων;

A4: Όχι, το GroupDocs.Viewer είναι μια αυτόνομη βιβλιοθήκη και δεν απαιτεί εξωτερικές εξαρτήσεις ή εγκαταστάσεις λογισμικού τρίτων.

### Ε5: Υπάρχει διαθέσιμη δωρεάν δοκιμή για το GroupDocs.Viewer;

 A5: Ναι, μπορείτε να επωφεληθείτε από μια δωρεάν δοκιμή του GroupDocs.Viewer μεταβαίνοντας στο[δικτυακός τόπος](https://releases.groupdocs.com/).