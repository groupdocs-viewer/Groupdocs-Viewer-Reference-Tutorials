---
additionalTitle: GroupDocs API References
date: 2025-12-15
description: Μάθετε πώς να προσθέτετε υδατογράφημα σε έγγραφα χρησιμοποιώντας το GroupDocs.Viewer
  και να αποδίδετε αρχεία PDF .NET. Κατακτήστε την προβολή περισσότερων από 170 μορφών
  σε .NET και Java.
is_root: true
linktitle: GroupDocs.Viewer Tutorials
title: Προσθήκη Υδατογραφήματος σε Έγγραφο με Οδηγίες GroupDocs.Viewer
type: docs
url: /el/
weight: 11
---

# GroupDocs.Viewer Οδηγοί

Καλώς ήρθατε στο κέντρο των οδηγών του GroupDocs.Viewer. Εδώ θα βρείτε μια ολοκληρωμένη συλλογή από οδηγούς και εγχειρίδια για να σας βοηθήσουν να **add watermark document** και να κατακτήσετε τα ισχυρά APIs προβολής εγγράφων μας για .NET και Java. Είτε δημιουργείτε μια web εφαρμογή, μια εφαρμογή για υπολογιστή, είτε μια κινητή λύση, το GroupDocs.Viewer σας επιτρέπει να αποδίδετε και να εμφανίζετε αβίαστα μια μεγάλη ποικιλία μορφών εγγράφων, συμπεριλαμβανομένων PDF, Microsoft Office (Word, Excel, PowerPoint), CAD, εικόνες και άλλα.

## Γρήγορες Απαντήσεις
- **What does “add watermark document” mean?** Αναφέρεται στην ενσωμάτωση ενός ημιδιαφανή κειμένου ή εικόνας πάνω από κάθε σελίδα του αποδοθέντος εγγράφου.  
- **Which formats support watermarks?** Όλες οι μορφές που αποδίδονται από το GroupDocs.Viewer, συμπεριλαμβανομένων PDF, DOCX, XLSX, CAD και μηνυμάτων email.  
- **Do I need a license?** Απαιτείται έγκυρη άδεια GroupDocs.Viewer για παραγωγική χρήση· διατίθεται δωρεάν δοκιμή.  
- **Can I combine watermarks with other features?** Ναι—τα υδατογραφήματα μπορούν να εφαρμοστούν μαζί με caching, προσαρμοσμένη απόδοση και ρυθμίσεις ασφαλείας.  
- **Is it compatible with .NET Core?** Απολύτως—το GroupDocs.Viewer λειτουργεί με .NET Framework, .NET Core και .NET 5/6+.

## GroupDocs.Viewer για .NET Οδηγούς

{{% alert color="primary" %}}
Ενδυναμώστε τις .NET εφαρμογές σας με δυνατότητες προβολής εγγράφων υψηλής πιστότητας. Οι οδηγίες μας για GroupDocs.Viewer για .NET παρέχουν όλα όσα χρειάζεστε για να ενσωματώσετε έναν ισχυρό προβολέα εγγράφων. Μάθετε πώς να αποδίδετε πάνω από 170 μορφές εγγράφων σε HTML, JPEG, PNG και PDF. Εξερευνήστε προχωρημένα θέματα όπως η απόδοση συγκεκριμένων διατάξεων σε CAD σχέδια, η διαχείριση συνημμένων εγγράφων και η βελτιστοποίηση της απόδοσης. Ξεκινήστε να δημιουργείτε στιβαρές και επαγγελματικές εμπειρίες προβολής εγγράφων σε C#, ASP.NET και άλλα .NET πλαίσια.
{{% /alert %}}

These are links to some useful .NET resources:
 
- [Loading Documents](./net/loading-documents/)
- [Advanced Loading Options](./net/advanced-loading/)
- [Advanced Usage (Caching)](./net/advanced-usage-caching/)
- [Rendering Options](./net/rendering-options/)
- [Rendering Archive Files](./net/rendering-archive-files/)
- [Rendering CAD Drawings](./net/rendering-cad-drawings/)
- [Getting Started](./net/getting-started/)
- [Rendering Email Messages](./net/rendering-email-messages/)
- [Image Rendering](./net/image-rendering/)
- [Rendering Documents to PDF](./net/rendering-documents-pdf/)
- [Rendering Documents to Images](./net/rendering-documents-images/)
- [Rendering Documents to HTML](./net/rendering-documents-html/)
- [Processing Document Attachments](./net/processing-document-attachments/)
- [Rendering Text Files](./net/rendering-text-files/)
- [Rendering Visio Documents](./net/rendering-visio-documents/)
- [Rendering Web Documents](./net/rendering-web-documents/)
- [Rendering Word Processing Documents](./net/rendering-word-processing-documents/)
- [Spreadsheet Rendering Options](./net/spreadsheet-rendering-options/)
- [PDF Rendering Options](./net/pdf-rendering-options/)
- [Rendering Outlook Data Files (PST, OST)](./net/rendering-outlook-data-files/)
- [Rendering Microsoft Project Documents](./net/rendering-ms-project-documents/)
- [Document Loading](./net/document-loading/)
- [Rendering Basics](./net/rendering-basics/)
- [Advanced Rendering](./net/advanced-rendering/)
- [Performance Optimization](./net/performance-optimization/)
- [Security & Permissions](./net/security-permissions/)
- [Watermarks & Annotations](./net/watermarks-annotations/)
- [File Formats Support](./net/file-formats-support/)
- [Cloud & Remote Document Rendering](./net/cloud-remote-document-rendering/)
- [Caching & Resource Management](./net/caching-resource-management/)
- [Metadata & Properties](./net/metadata-properties/)
- [Export & Conversion](./net/export-conversion/)
- [Custom Rendering](./net/custom-rendering/)

## Πώς να Προσθέσετε Watermark Document με το GroupDocs.Viewer

Η προσθήκη υδατογραφήματος είναι συχνά απαραίτητη για branding, εμπιστευτικότητα ή κανονιστική συμμόρφωση. Με το GroupDocs.Viewer μπορείτε να εφαρμόσετε ένα υδατογράφημα κατά την απόδοση ενός εγγράφου σε HTML, PDF ή μορφές εικόνας. Η διαδικασία είναι απλή:

1. **Create a `WatermarkOptions` object** και ορίστε το κείμενο, το χρώμα, τη διαφάνεια και την περιστροφή.  
2. **Pass the options** στη σχετική μέθοδο απόδοσης (π.χ., `RenderToPdf`, `RenderToHtml` ή `RenderToImage`).  
3. **Render the document**—η έξοδος θα περιέχει το υδατογράφημα σε κάθε σελίδα.

Αυτή η προσέγγιση λειτουργεί σε όλους τους υποστηριζόμενους τύπους αρχείων, συμπεριλαμβανομένων σεναρίων **render pdf .net**, CAD σχεδίων και μηνυμάτων email.

## GroupDocs.Viewer για Java Οδηγούς

{{% alert color="primary" %}}
Ενσωματώστε έναν ευέλικτο και αποδοτικό προβολέα εγγράφων στις Java εφαρμογές σας με το GroupDocs.Viewer για Java. Οι οδηγίες μας θα σας καθοδηγήσουν σε κάθε βήμα, από τη ρύθμιση του περιβάλλοντος μέχρι την υλοποίηση προχωρημένων λειτουργιών απόδοσης. Μάθετε να εμφανίζετε πολυάριθμες μορφές αρχείων, συμπεριλαμβανομένων σύνθετων εγγράφων όπως αρχεία CAD πολλαπλών διατάξεων και αρχεία αρχειοθηκών προστατευμένα με κωδικό. Ακολουθήστε τα παραδείγματα μας για να αποδίδετε έγγραφα σε HTML5, εικόνες και PDF, επιτρέποντας εύκολη προβολή εγγράφων δια-πλατφόρμας.
{{% /alert %}}

These are links to some useful Java resources:

- [Getting Started](./java/getting-started/)
- [Document Loading](./java/document-loading/)
- [Rendering Basics](./java/rendering-basics/)
- [Advanced Rendering](./java/advanced-rendering/)
- [Performance Optimization](./java/performance-optimization/)
- [Security & Permissions](./java/security-permissions/)
- [Watermarks & Annotations](./java/watermarks-annotations/)
- [File Formats Support](./java/file-formats-support/)
- [Cloud & Remote Document Rendering](./java/cloud-remote-document-rendering/)
- [Caching & Resource Management](./java/caching-resource-management/)
- [Metadata & Properties](./java/metadata-properties/)
- [Export & Conversion](./java/export-conversion/)
- [Custom Rendering](./java/custom-rendering/)

## Συχνές Ερωτήσεις

**Q: Μπορώ να προσθέσω υδατογράφημα σε έγγραφα που αποδίδονται ως εικόνες;**  
A: Ναι—χρησιμοποιήστε το `WatermarkOptions` μαζί με το `RenderToImage` για να ενσωματώσετε υδατογραφήματα σε κάθε παραγόμενη σελίδα εικόνας.

**Q: Η προσθήκη υδατογραφήματος επηρεάζει την απόδοση της απόδοσης;**  
A: Η επίπτωση είναι ελάχιστη· το GroupDocs.Viewer βελτιστοποιεί τη διαδικασία επικάλυψης, ειδικά όταν συνδυάζεται με caching.

**Q: Υποστηρίζονται υδατογραφήματα κατά την απόδοση μηνυμάτων email;**  
A: Απόλυτα—τα υδατογραφήματα μπορούν να εφαρμοστούν στην έξοδο HTML ή PDF των αποδοθέντων μηνυμάτων email.

**Q: Πώς μπορώ να προσαρμόσω την εμφάνιση του υδατογραφήματος;**  
A: Μπορείτε να ορίσετε την οικογένεια γραμματοσειράς, το μέγεθος, το χρώμα, τη διαφάνεια, τη γωνία περιστροφής και ακόμη και να χρησιμοποιήσετε μια εικόνα ως υδατογράφημα.

**Q: Είναι δυνατόν να εφαρμόσετε διαφορετικά υδατογραφήματα σε διαφορετικές σελίδες;**  
A: Το τυπικό API εφαρμόζει ένα ενιαίο υδατογράφημα, αλλά μπορείτε να υλοποιήσετε προσαρμοσμένη λογική απόδοσης για να διαφοροποιήσετε τα υδατογραφήματα ανά σελίδα.

---

**Τελευταία Ενημέρωση:** 2025-12-15  
**Δοκιμάστηκε Με:** GroupDocs.Viewer 23.11 for .NET & Java  
**Συγγραφέας:** GroupDocs