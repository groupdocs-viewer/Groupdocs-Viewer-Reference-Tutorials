---
"description": "Μάθετε πώς να αποδίδετε εικόνες SVG και SVGZ χρησιμοποιώντας το GroupDocs.Viewer για .NET. Μετατρέψτε διανυσματικά γραφικά σε HTML, JPG, PNG και PDF χωρίς κόπο."
"linktitle": "Απόδοση εικόνων SVG και SVGZ"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση εικόνων SVG και SVGZ"
"url": "/el/net/image-rendering/render-svg-svgz-images/"
"weight": 16
type: docs
---
# Απόδοση εικόνων SVG και SVGZ

## Εισαγωγή
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία απόδοσης εικόνων SVG και SVGZ χρησιμοποιώντας το GroupDocs.Viewer για .NET. Το GroupDocs.Viewer για .NET είναι ένα ισχυρό API απόδοσης εγγράφων που επιτρέπει στους προγραμματιστές να αποδίδουν διάφορες μορφές εγγράφων στις εφαρμογές .NET τους. Τα SVG και SVGZ είναι δημοφιλείς μορφές εικόνας που χρησιμοποιούνται για διανυσματικά γραφικά και με το GroupDocs.Viewer για .NET, μπορείτε εύκολα να τις αποδώσετε σε διαφορετικές μορφές εξόδου όπως HTML, JPG, PNG και PDF.

![Απόδοση εικόνων SVG και SVGZ με το GroupDocs.Viewer για .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τις ακόλουθες προϋποθέσεις:
1. GroupDocs.Viewer για .NET: Λήψη και εγκατάσταση του GroupDocs.Viewer για .NET από [εδώ](https://releases.groupdocs.com/viewer/net/).
2. Περιβάλλον Ανάπτυξης: Βεβαιωθείτε ότι έχετε ένα λειτουργικό περιβάλλον ανάπτυξης για ανάπτυξη .NET, όπως το Visual Studio.
3. Δείγμα αρχείου SVGZ: Να έχετε ένα δείγμα αρχείου SVGZ έτοιμο για δοκιμή.

## Εισαγωγή χώρων ονομάτων
Πριν εμβαθύνουμε στον κώδικα, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Βήμα 1: Απόδοση SVGZ σε HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Βήμα 2: Απόδοση SVGZ σε JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Βήμα 3: Απόδοση SVGZ σε PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Βήμα 4: Απόδοση SVGZ σε PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Σύναψη
Σε αυτό το σεμινάριο, μάθαμε πώς να αποδίδουμε εικόνες SVG και SVGZ χρησιμοποιώντας το GroupDocs.Viewer για .NET. Με λίγα μόνο απλά βήματα, μπορείτε να μετατρέψετε εικόνες SVGZ σε διάφορες μορφές εξόδου όπως HTML, JPG, PNG και PDF, καθιστώντας τες προσβάσιμες και ορατές σε διαφορετικά περιβάλλοντα.
## Συχνές ερωτήσεις
### Μπορεί το GroupDocs.Viewer να αποδώσει άλλες μορφές εικόνας;
Ναι, το GroupDocs.Viewer υποστηρίζει την απόδοση διαφόρων μορφών εικόνας, όπως PNG, JPEG, BMP, TIFF, GIF και άλλα.
### Είναι το GroupDocs.Viewer συμβατό με το .NET Core;
Ναι, το GroupDocs.Viewer είναι συμβατό τόσο με το .NET Framework όσο και με το .NET Core.
### Μπορώ να προσαρμόσω τις επιλογές απόδοσης;
Ναι, το GroupDocs.Viewer παρέχει εκτεταμένες επιλογές απόδοσης που σας επιτρέπουν να προσαρμόσετε την έξοδο σύμφωνα με τις απαιτήσεις σας.
### Απαιτεί το GroupDocs.Viewer εξαρτήσεις τρίτων;
Όχι, το GroupDocs.Viewer είναι ένα αυτόνομο API και δεν απαιτεί εξαρτήσεις τρίτων για την απόδοση εγγράφων.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για δοκιμή;
Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση του GroupDocs.Viewer από [εδώ](https://releases.groupdocs.com/) για να αξιολογήσετε τα χαρακτηριστικά του πριν κάνετε μια αγορά.