---
"date": "2025-04-25"
"description": "Μάθετε πώς να μετατρέπετε αρχεία TXT σε πολλαπλές μορφές όπως HTML, JPG, PNG και PDF χρησιμοποιώντας το GroupDocs.Viewer για .NET με αυτόν τον ολοκληρωμένο οδηγό."
"title": "Μετατροπή TXT σε HTML, JPG, PNG, PDF χρησιμοποιώντας το GroupDocs.Viewer .NET™ Ένας πλήρης οδηγός"
"url": "/el/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
---

# Μετατροπή TXT σε πολλαπλές μορφές με το GroupDocs.Viewer .NET

## Εισαγωγή

Θέλετε να μετατρέψετε έγγραφα κειμένου σε διάφορες μορφές όπως HTML, JPG, PNG ή PDF χωρίς κόπο; Η διαχείριση μετατροπών εγγράφων μπορεί να είναι δύσκολη, ειδικά όταν πρόκειται για πολλαπλές σελίδες ή συγκεκριμένες απαιτήσεις μορφής. **GroupDocs.Viewer για .NET** απλοποιεί τη διαδικασία απόδοσης αρχείων TXT σε διάφορες μορφές εξόδου, διασφαλίζοντας ότι τα δεδομένα σας είναι προσβάσιμα και οπτικά ελκυστικά.

![Μετατροπή TXT σε HTML, JPG, PNG, PDF με το GroupDocs.Viewer για .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

Σε αυτόν τον οδηγό, θα εξερευνήσουμε πώς να χρησιμοποιήσετε το GroupDocs.Viewer για .NET για να μετατρέψετε έγγραφα TXT σε HTML πολλαπλών σελίδων, HTML μίας σελίδας, JPG, PNG και PDF. Στο τέλος, θα είστε εξοικειωμένοι με:
- Μετατροπή αρχείων TXT χρησιμοποιώντας C# με το GroupDocs.Viewer
- Υλοποίηση διαφορετικών επιλογών απόδοσης για τις ανάγκες σας
- Βελτιστοποίηση απόδοσης κατά τη διάρκεια μετατροπών

Ας εμβαθύνουμε στην επίλυση των προκλήσεων μετατροπής εγγράφων σας.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε έτοιμα τα εξής:
- **Περιβάλλον Ανάπτυξης**Visual Studio 2019 ή νεότερη έκδοση.
- **Πλαίσιο .NET**Έκδοση 4.6.1 ή νεότερη.
- **GroupDocs.Viewer για τη βιβλιοθήκη .NET**:
  - Μέσω της κονσόλας NuGet Package Manager: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Χρησιμοποιώντας το .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Συνιστάται η εξοικείωση με τον προγραμματισμό C# και τις βασικές λειτουργίες αρχείων σε .NET για εύκολη παρακολούθηση.

## Ρύθμιση του GroupDocs.Viewer για .NET

### Εγκατάσταση

Για να ξεκινήσετε, εγκαταστήστε το **GroupDocs.Viewer** βιβλιοθήκη χρησιμοποιώντας τον προτιμώμενο διαχειριστή πακέτων σας:

#### Κονσόλα διαχείρισης πακέτων NuGet
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Αδειοδότηση

Μπορείτε να ξεκινήσετε με ένα **δωρεάν δοκιμή** ή να αποκτήσετε ένα **προσωρινή άδεια** για να εξερευνήσετε όλες τις δυνατότητες του GroupDocs.Viewer για .NET χωρίς περιορισμούς αξιολόγησης:
- Δωρεάν δοκιμή: [Λήψη εδώ](https://releases.groupdocs.com/viewer/net/)
- Προσωρινή Άδεια: [Αίτημα εδώ](https://purchase.groupdocs.com/temporary-license/)

Για συνεχή χρήση, σκεφτείτε να αγοράσετε μια άδεια χρήσης απευθείας από [GroupDocs](https://purchase.groupdocs.com/buy).

### Βασική Αρχικοποίηση

Για να ρυθμίσετε το GroupDocs.Viewer στο έργο σας:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Αρχικοποιήστε το αντικείμενο Viewer με μια διαδρομή αρχείου TXT.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Ο κώδικας απόδοσης θα τοποθετηθεί εδώ.
}
```

## Οδηγός Εφαρμογής

Τώρα, ας εμβαθύνουμε σε κάθε χαρακτηριστικό και ας δούμε πώς μπορείτε να το εφαρμόσετε.

### Απόδοση εγγράφου TXT σε HTML πολλαπλών σελίδων

#### Επισκόπηση
Αυτή η λειτουργία επιδεικνύει τη μετατροπή ενός εγγράφου TXT σε μορφή HTML πολλαπλών σελίδων. Κάθε σελίδα του αρχείου κειμένου αποδίδεται ως ξεχωριστό αρχείο HTML με ενσωματωμένους πόρους.

#### Βήμα 1: Ρύθμιση του προγράμματος προβολής

Δημιουργήστε ένα `Viewer` αντικείμενο για το αρχείο TXT πηγής σας:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Αρχικοποιήστε το πρόγραμμα προβολής με ένα δείγμα αρχείου κειμένου.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Συνεχίστε στο βήμα 2...
```

#### Βήμα 2: Ρύθμιση παραμέτρων επιλογών προβολής HTML

Στήνω `HtmlViewOptions` για να αποδώσετε κάθε σελίδα ξεχωριστά:

```csharp
// Ρυθμίστε τις επιλογές προβολής HTML για απόδοση πολλαπλών σελίδων.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Αποδώστε το έγγραφο ως HTML πολλαπλών σελίδων.
viewer.View(options);
}
```

**Εξήγηση**: Το `ForEmbeddedResources()` Η μέθοδος διασφαλίζει ότι πόροι όπως εικόνες και στυλ ενσωματώνονται απευθείας στο αρχείο HTML, διευκολύνοντας την εύκολη κοινή χρήση.

### Απόδοση εγγράφου TXT σε HTML μίας σελίδας

#### Επισκόπηση
Μετατρέψτε ένα έγγραφο TXT σε μία μόνο σελίδα HTML, ιδανικό για έγγραφα που πρέπει να εμφανίζονται ως μία συνεχής ιστοσελίδα.

#### Βήμα 1: Ρύθμιση του προγράμματος προβολής

Αρχικοποίηση του `Viewer` αντικείμενο:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Αρχικοποιήστε μια νέα παρουσία Viewer για ένα διαφορετικό αρχείο κειμένου.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Συνεχίστε στο βήμα 2...
```

#### Βήμα 2: Ρύθμιση παραμέτρων επιλογών HTML μίας σελίδας

Ρύθμιση παραμέτρων `HtmlViewOptions` με ενεργοποιημένη τη ρύθμιση μίας σελίδας:

```csharp
// Ορίστε επιλογές για απόδοση σε μία μόνο σελίδα HTML.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Απόδοση ως μία σελίδα HTML.
viewer.View(options);
}
```

**Εξήγηση**: Το `RenderToSinglePage` Η ιδιότητα διασφαλίζει ότι ολόκληρο το περιεχόμενο αποδίδεται σε μία σελίδα.

### Απόδοση εγγράφου TXT σε JPG

#### Επισκόπηση
Αυτή η λειτουργία σάς επιτρέπει να μετατρέψετε ένα έγγραφο κειμένου σε εικόνα JPEG, κάτι που είναι χρήσιμο για οπτικές παρουσιάσεις ή σκοπούς αρχειοθέτησης.

#### Βήμα 1: Ρύθμιση του προγράμματος προβολής

Προετοιμάστε το δικό σας `Viewer` αντικείμενο:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Αρχικοποιήστε το πρόγραμμα προβολής με ένα δείγμα αρχείου.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Συνεχίστε στο βήμα 2...
```

#### Βήμα 2: Ρύθμιση παραμέτρων επιλογών προβολής JPG

Στήνω `JpgViewOptions` για την απόδοση εικόνας:

```csharp
// Ορίστε επιλογές για απόδοση ως εικόνα JPG.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Αποδώστε το έγγραφο ως αρχείο JPEG.
viewer.View(options);
}
```

**Εξήγηση**: Το `JpgViewOptions` Η κλάση καθορίζει τον τρόπο απόδοσης και αποθήκευσης κάθε σελίδας του εγγράφου σας σε μορφή JPEG.

### Απόδοση εγγράφου TXT σε PNG

#### Επισκόπηση
Μετατρέψτε ένα έγγραφο κειμένου σε μορφή PNG, προσφέροντας υψηλής ποιότητας εικόνα με υποστήριξη διαφάνειας.

#### Βήμα 1: Ρύθμιση του προγράμματος προβολής

Αρχικοποίηση του `Viewer` αντικείμενο:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Δημιουργήστε μια παρουσία προβολής για το αρχείο TXT σας.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Συνεχίστε στο βήμα 2...
```

#### Βήμα 2: Ρύθμιση παραμέτρων επιλογών προβολής PNG

Στήνω `PngViewOptions`:

```csharp
// Ορίστε επιλογές προβολής για απόδοση ως εικόνα PNG.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Αποδώστε το έγγραφο σε μορφή PNG.
viewer.View(options);
}
```

**Εξήγηση**: Το `PngViewOptions` Η κλάση επιτρέπει την απόδοση κάθε σελίδας με διαφάνεια, καθιστώντας την κατάλληλη για γραφικά σε στρώσεις.

### Απόδοση εγγράφου TXT σε PDF

#### Επισκόπηση
Αυτή η λειτουργία είναι ιδανική για τη μετατροπή εγγράφων κειμένου σε μια καθολικά προσβάσιμη μορφή PDF.

#### Βήμα 1: Ρύθμιση του προγράμματος προβολής

Προετοιμάστε το δικό σας `Viewer` αντικείμενο:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Αρχικοποιήστε μια παρουσία προβολής για το αρχείο δείγματος κειμένου σας.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Συνεχίστε στο βήμα 2...
```

#### Βήμα 2: Ρύθμιση παραμέτρων επιλογών προβολής PDF

Στήνω `PdfViewOptions`:

```csharp
// Ορίστε επιλογές προβολής για απόδοση ως έγγραφο PDF.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Αποδώστε το έγγραφο σε αρχείο PDF.
viewer.View(options);
}
```

**Εξήγηση**: Το `PdfViewOptions` Η κλάση καθορίζει τον τρόπο μετατροπής και αποθήκευσης των αρχείων TXT ως εγγράφων PDF.

## Σύναψη

Με το GroupDocs.Viewer για .NET, η μετατροπή εγγράφων κειμένου σε διάφορες μορφές είναι απλή. Αυτός ο οδηγός καλύπτει τη μετατροπή αρχείων TXT σε HTML πολλαπλών σελίδων, HTML μίας σελίδας, JPG, PNG και PDF χρησιμοποιώντας C#. Είτε θέλετε να βελτιώσετε την προσβασιμότητα είτε τη συμβατότητα των εγγράφων, αυτές οι μέθοδοι παρέχουν ισχυρές λύσεις.

Για περαιτέρω βοήθεια ή πιο προηγμένες λειτουργίες, ανατρέξτε στο [επίσημη τεκμηρίωση του GroupDocs.Viewer](https://docs.groupdocs.com/viewer/net/)Καλή κωδικοποίηση!