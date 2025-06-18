---
"description": "Δημιουργήστε master rendering εγγράφων MS Project με το GroupDocs.Viewer για .NET. Αποδώστε σημειώσεις, προσαρμόστε τις μονάδες χρόνου και εξερευνήστε διάφορες μορφές εξόδου χωρίς κόπο."
"linktitle": "Απόδοση σημειώσεων και προσαρμογή μονάδων χρόνου (MS Project)"
"second_title": "API .NET του GroupDocs.Viewer"
"title": "Απόδοση σημειώσεων και προσαρμογή μονάδων χρόνου (MS Project)"
"url": "/el/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# Απόδοση σημειώσεων και προσαρμογή μονάδων χρόνου (MS Project)

## Εισαγωγή
Το GroupDocs.Viewer για .NET είναι ένα ισχυρό API απόδοσης εγγράφων που επιτρέπει στους προγραμματιστές να προβάλλουν και να χειρίζονται διάφορες μορφές εγγράφων στις εφαρμογές .NET τους. Σε αυτό το σεμινάριο, θα επικεντρωθούμε στην απόδοση σημειώσεων και στην προσαρμογή των μονάδων χρόνου ειδικά για έγγραφα MS Project.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. GroupDocs.Viewer για .NET: Βεβαιωθείτε ότι έχετε κατεβάσει και εγκαταστήσει τη βιβλιοθήκη GroupDocs.Viewer για .NET. Μπορείτε να την κατεβάσετε από [εδώ](https://releases.groupdocs.com/viewer/net/).
2. Περιβάλλον Ανάπτυξης: Ρυθμίστε το προτιμώμενο περιβάλλον ανάπτυξης με υποστήριξη .NET.
3. Έγγραφο MS Project: Να έχετε έτοιμο ένα δείγμα εγγράφου MS Project για δοκιμή.
## Εισαγωγή χώρων ονομάτων
Αρχικά, ας εισαγάγουμε τους απαραίτητους χώρους ονομάτων για να ξεκινήσουμε με την απόδοση εγγράφων του MS Project:
## Βήμα 1: Εισαγωγή χώρων ονομάτων
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Τώρα που έχουμε εισαγάγει τους απαιτούμενους χώρους ονομάτων, ας αναλύσουμε κάθε παράδειγμα σε πολλά βήματα για μια ολοκληρωμένη κατανόηση.
## Απόδοση εγγράφου MS Project σε HTML
Για να αποδώσετε ένα έγγραφο του MS Project σε μορφή HTML με σημειώσεις, ακολουθήστε τα εξής βήματα:
### Βήμα 2: Ορισμός καταλόγου εξόδου και μορφής αρχείου
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Βήμα 3: Αρχικοποίηση αντικειμένου προβολής και ορισμός επιλογών
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Βήμα 4: Απόδοση εγγράφου σε HTML
```csharp
viewer.View(options);
```
## Απόδοση εγγράφου MS Project σε μορφές εικόνας
Μπορείτε επίσης να αποδώσετε έγγραφα MS Project σε μορφές εικόνας όπως JPG και PNG. Δείτε πώς:
### Βήμα 5: Ορίστε τον κατάλογο εξόδου και τη μορφή αρχείου για JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Βήμα 6: Αρχικοποίηση αντικειμένου προβολής και ορισμός επιλογών JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Βήμα 7: Απόδοση εγγράφου σε JPG
```csharp
viewer.View(options);
```
Επαναλάβετε παρόμοια βήματα για την απόδοση σε PNG και άλλες μορφές εικόνας.
## Απόδοση εγγράφου MS Project σε PDF
Για να αποδώσετε ένα έγγραφο του MS Project σε μορφή PDF, ακολουθήστε την εξής διαδικασία:
### Βήμα 8: Ορισμός καταλόγου εξόδου και μορφής αρχείου για PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Βήμα 9: Αρχικοποίηση αντικειμένου προβολής και ορισμός επιλογών PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Βήμα 10: Απόδοση εγγράφου σε PDF
```csharp
viewer.View(options);
```

## Σύναψη
Συγχαρητήρια! Μάθατε με επιτυχία πώς να αποδίδετε έγγραφα του MS Project και να προσαρμόζετε τις μονάδες χρόνου χρησιμοποιώντας το GroupDocs.Viewer για .NET. Ενσωματώστε αυτές τις γνώσεις στα έργα σας για να βελτιώσετε τις δυνατότητες προβολής εγγράφων.
## Συχνές ερωτήσεις
### Μπορώ να αποδώσω έγγραφα του MS Project σε άλλες μορφές εκτός από HTML, εικόνες και PDF;
Ναι, το GroupDocs.Viewer για .NET υποστηρίζει απόδοση σε διάφορες μορφές όπως DOCX, XLSX, PPTX και άλλες.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το GroupDocs.Viewer για .NET;
Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή από [εδώ](https://releases.groupdocs.com/).
### Πώς μπορώ να λάβω προσωρινή άδεια χρήσης για το GroupDocs.Viewer για .NET;
Επίσκεψη [αυτός ο σύνδεσμος](https://purchase.groupdocs.com/temporary-license/) για την απόκτηση προσωρινής άδειας.
### Πού μπορώ να βρω τεκμηρίωση για το GroupDocs.Viewer για .NET;
Ανατρέξτε στην τεκμηρίωση [εδώ](https://tutorials.groupdocs.com/viewer/net/).
### Πού μπορώ να αναζητήσω υποστήριξη ή να υποβάλω ερωτήσεις σχετικά με το GroupDocs.Viewer για .NET;
Μπορείτε να επισκεφθείτε το φόρουμ υποστήριξης [εδώ](https://forum.groupdocs.com/c/viewer/9).