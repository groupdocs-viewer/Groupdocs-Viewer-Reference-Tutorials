---
date: '2026-09-15'
description: Μάθετε πώς να μετατρέψετε email σε HTML και να μετονομάσετε τα πεδία
  email χρησιμοποιώντας το GroupDocs Viewer για Java. Αυτός ο οδηγός δείχνει τη μετατροπή
  του email σε HTML με προσαρμοσμένες κεφαλίδες.
keywords:
- convert email to html
- rename email fields java
- render emails html groupdocs viewer
- customize email headers
- customize email metadata
lastmod: '2026-09-15'
og_description: Μετατρέψτε email σε HTML και μετονομάστε τα πεδία email σε Java με
  το GroupDocs Viewer. Μάθετε βήμα‑βήμα τη ρύθμιση, τη χαρτογράφηση πεδίων και τις
  βέλτιστες πρακτικές για καθαρό αποτέλεσμα HTML.
og_image_alt: Guide showing how to convert email to HTML and rename fields using GroupDocs
  Viewer for Java
og_title: Μετατροπή email σε HTML με προσαρμοσμένες κεφαλίδες χρησιμοποιώντας το GroupDocs
  Viewer για Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert email to HTML and rename email fields using GroupDocs
    Viewer for Java. This guide shows rendering email as HTML with custom headers.
  headline: Convert Email to HTML & Rename Fields – GroupDocs Viewer Java
  type: TechArticle
- description: Learn how to convert email to HTML and rename email fields using GroupDocs
    Viewer for Java. This guide shows rendering email as HTML with custom headers.
  name: Convert Email to HTML & Rename Fields – GroupDocs Viewer Java
  steps:
  - name: '**Custom email reports:** Align email headers with corporate terminology
      for clearer reports.'
    text: '**Custom email reports:** Align email headers with corporate terminology
      for clearer reports.'
  - name: '**Email archiving systems:** Improve searchability by using standardized
      header names.'
    text: '**Email archiving systems:** Improve searchability by using standardized
      header names.'
  - name: '**Customer support platforms:** Present tickets with personalized header
      labels for better agent experience.'
    text: '**Customer support platforms:** Present tickets with personalized header
      labels for better agent experience.'
  type: HowTo
- questions:
  - answer: Yes, GroupDocs.Viewer supports both MSG and EML files; the same field‑mapping
      logic applies.
    question: Does this approach work with other email formats like EML?
  - answer: You can use `HtmlViewOptions.forExternalResources(...)` if you prefer
      separate CSS/JS files.
    question: Can I output the HTML without embedded resources?
  - answer: The code was tested with GroupDocs.Viewer **25.2**.
    question: What version of GroupDocs.Viewer was tested?
  - answer: Styling can be applied via CSS after rendering, or you can inject custom
      CSS using `HtmlViewOptions.getResourcesPath()`.
    question: Is it possible to change the font or style of the custom headers?
  - answer: The file path follows the pattern defined in `pageFilePathFormat`; you
      can construct it using `String.format` with the page number.
    question: How do I programmatically retrieve the generated HTML file path?
  type: FAQPage
tags:
- convert email to html
- groupdocs viewer java
- email rendering
- html conversion
- java email processing
title: Μετατροπή Email σε HTML & Μετονομασία Πεδίων – GroupDocs Viewer Java
type: docs
url: /el/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή email σε HTML & μετονομασία πεδίων – GroupDocs Viewer Java

Αν χρειάζεστε **convert email to HTML** ενώ δίνετε στις κεφαλίδες του email μια προσαρμοσμένη εμφάνιση, βρίσκεστε στο σωστό μέρος. Σε αυτό το tutorial θα περάσουμε από τα ακριβή βήματα για να μετονομάσουμε τα πεδία του email, **convert email to HTML**, και να προσαρμόσουμε τις κεφαλίδες του email χρησιμοποιώντας το GroupDocs.Viewer for Java. Στο τέλος θα έχετε μια καθαρή αναπαράσταση HTML με τα ονόματα κεφαλίδων που προτιμάτε, καθιστώντας το αποτέλεσμα πιο εύκολο στην ανάγνωση και ενσωμάτωση στις εφαρμογές σας.

![Μετονομασία πεδίων email κατά τη μετατροπή email σε HTML με το GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Τι θα μάθετε
- Πώς να χρησιμοποιήσετε το GroupDocs.Viewer for Java για **convert email to HTML**.  
- Τεχνικές για **rename email fields** όπως “From”, “To”, “Sent” και “Subject”.  
- Καλές πρακτικές για τη ρύθμιση του Maven και την αδειοδότηση.  
- Πραγματικά σενάρια όπου **customizing email headers** προσθέτει αξία.

## Γρήγορες απαντήσεις
- **Τι σημαίνει “convert email to HTML”;** Σημαίνει την απόδοση ενός αρχείου email (MSG/EML) ως έγγραφο HTML έτοιμο για το web.  
- **Ποια βιβλιοθήκη διαχειρίζεται τη μετατροπή;** GroupDocs.Viewer for Java (v25.2+).  
- **Χρειάζομαι άδεια;** Μια δοκιμαστική έκδοση λειτουργεί για αξιολόγηση· απαιτείται πλήρης άδεια για παραγωγή.  
- **Μπορώ να αλλάξω οποιοδήποτε όνομα κεφαλίδας;** Ναι, οποιαδήποτε τυπική κεφαλίδα email μπορεί να επαναχαρτογραφηθεί μέσω του `fieldTextMap`.  
- **Είναι το αποτέλεσμα HTML ή ενσωματωμένοι πόροι;** Μπορείτε να επιλέξετε ενσωματωμένους πόρους για ένα ενιαίο αυτό-συμπεριλαμβανόμενο αρχείο.

## Τι είναι το “convert email to HTML” στο πλαίσιο του GroupDocs.Viewer;
**Convert email to HTML** είναι η διαδικασία λήψης ενός ακατέργαστου αρχείου email (MSG ή EML) και δημιουργίας μιας σελίδας HTML που εμφανίζει το σώμα του μηνύματος μαζί με τα μεταδεδομένα του. Όταν επίσης **rename email fields**, οι προεπιλεγμένες ετικέτες (π.χ., “From”) αντικαθίστανται με προσαρμοσμένο κείμενο (π.χ., “Sender”), το οποίο σας βοηθά να ταιριάξετε την εταιρική ορολογία ή να βελτιώσετε τη συνοχή του UI.

## Γιατί να μετατρέψετε email σε HTML και να μετονομάσετε τα πεδία email;
Η μετατροπή email σε HTML και η μετονομασία των πεδίων του σας δίνει πλήρη έλεγχο πάνω στο πώς παρουσιάζεται το μήνυμα στους τελικούς χρήστες. Οι προσαρμοσμένες κεφαλίδες ευθυγραμμίζουν το αποτέλεσμα με την εταιρική ορολογία, βελτιώνουν την ευρετηρίαση αναζήτησης και επιτρέπουν αδιάλειπτη ενσωμάτωση σε διαδικτυακές πύλες ή πίνακες ελέγχου υποστήριξης, ενώ η μορφή HTML εξασφαλίζει ευρεία συμβατότητα μεταξύ προγραμμάτων περιήγησης και συσκευών.
- **Συνεπής επωνυμία:** Ευθυγραμμίζει το αποτέλεσμα με τη γλώσσα του οργανισμού σας.  
- **Βελτιωμένη ευρετηρίαση:** Οι προσαρμοσμένες κεφαλίδες μπορούν να ευρετηριαστούν πιο αποτελεσματικά σε συστήματα αρχειοθέτησης.  
- **Καλύτερη ενσωμάτωση UI:** Προσαρμόστε το απόσπασμα HTML ώστε να ταιριάζει αδιάλειπτα σε διαδικτυακές πύλες ή πίνακες ελέγχου υποστήριξης.  
- **Πλεονέκτημα απόδοσης:** Το GroupDocs.Viewer επεξεργάζεται email έως 500 σελίδες σε λιγότερο από 2 δευτερόλεπτα σε έναν τυπικό διακομιστή, και υποστηρίζει **50+** μορφές εισόδου και εξόδου, συμπεριλαμβανομένων των MSG, EML, PDF και HTML.

## Προαπαιτούμενα
- **GroupDocs.Viewer for Java** – έκδοση 25.2 ή νεότερη.  
- **Java Development Kit (JDK)** – έκδοση 8+.  
- **Maven** για διαχείριση εξαρτήσεων.  
- Ένα IDE όπως IntelliJ IDEA, Eclipse ή VS Code.  
- Βασική εξοικείωση με Java και Maven θα επιταχύνει τη ρύθμιση.

## Ρύθμιση GroupDocs.Viewer για Java

### Διαμόρφωση Maven
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Βήματα απόκτησης άδειας
- **Δωρεάν δοκιμή:** Κατεβάστε μια δωρεάν δοκιμή από [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Προσωρινή άδεια:** Αποκτήστε μια προσωρινή άδεια για να εξερευνήσετε όλες τις δυνατότητες χωρίς περιορισμούς στο [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Αγορά:** Για συνεχή χρήση, εξετάστε την αγορά άδειας μέσω του [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Βασική αρχικοποίηση και ρύθμιση
Η κλάση `Viewer` είναι το σημείο εισόδου για όλες τις λειτουργίες απόδοσης στο GroupDocs.Viewer for Java. Διαχειρίζεται αυτόματα τη φόρτωση αρχείων, την ανίχνευση μορφής και τον καθαρισμό πόρων.  
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Ρυθμίστε τη διαδρομή αρχείου ώστε να δείχνει στο αρχείο `.msg` σας.

## Πώς να μετατρέψετε email σε HTML και να μετονομάσετε πεδία – βήμα‑βήμα

Φορτώστε το email σας, ορίστε ένα λεξικό αντιστοίχισης πεδίων, διαμορφώστε τις επιλογές προβολής HTML και καλέστε τη λειτουργία render. Ολόκληρη η ροή εργασίας μπορεί να εκφραστεί σε έξι σύντομα βήματα.

### 1. Ορίστε τη διαδρομή του καταλόγου εξόδου
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Αντικαταστήστε το `"YOUR_OUTPUT_DIRECTORY"` με το φάκελο όπου θέλετε να αποθηκευτούν τα αρχεία HTML.*

### 2. Ορίστε τη μορφή διαδρομής αρχείου σελίδας
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` θα αντικατασταθεί από τον αριθμό σελίδας κατά την απόδοση.*

### 3. Δημιουργήστε μια αντιστοίχιση πεδίων email σε νέα ονόματα
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Εδώ αλλάζουμε τις προεπιλεγμένες ετικέτες σε προσαρμοσμένες.*

### 4. Διαμορφώστε τις επιλογές προβολής HTML
Η κλάση `HtmlViewOptions` ελέγχει πώς δημιουργείται το τελικό HTML. Η ρύθμιση `forEmbeddedResources` ενσωματώνει CSS/JS μέσα στο HTML, ενώ το `setFieldTextMap` εφαρμόζει τα προσαρμοσμένα ονόματα κεφαλίδων που ορίσατε.  
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```

### 5. Αποδώστε το email σε HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Αντικαταστήστε το `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` με την πραγματική διαδρομή προς το αρχείο MSG σας.*

#### Συμβουλές αντιμετώπισης προβλημάτων
- Επαληθεύστε ότι ο κατάλογος εξόδου είναι εγγράψιμος.  
- Βεβαιωθείτε ότι το αρχείο εισόδου MSG υπάρχει και η διαδρομή είναι σωστή.  
- Χρησιμοποιήστε την ίδια έκδοση GroupDocs.Viewer (25.2) όπως δηλώνεται στο Maven.

## Πρακτικές εφαρμογές
1. **Προσαρμοσμένες αναφορές email:** Ευθυγραμμίζει τις κεφαλίδες email με την εταιρική ορολογία για πιο σαφείς αναφορές.  
2. **Συστήματα αρχειοθέτησης email:** Βελτιώνει την ευρετηρίαση χρησιμοποιώντας τυποποιημένα ονόματα κεφαλίδων.  
3. **Πλατφόρμες εξυπηρέτησης πελατών:** Παρουσιάζει τα εισιτήρια με εξατομικευμένες ετικέτες κεφαλίδων για καλύτερη εμπειρία των πρακτόρων.

## Παράγοντες απόδοσης
- Αποδεσμεύστε τα αντικείμενα `Viewer` με try‑with‑resources για άμεση απελευθέρωση μνήμης.  
- Διεξάγετε profiling μεγάλων παρτίδων και εξετάστε την επεξεργασία email σε παράλληλα streams αν χρειάζεται.  
- Το GroupDocs.Viewer μπορεί να αποδώσει email αρχείων **έως 200 MB** χωρίς να φορτώνει ολόκληρο το έγγραφο στη μνήμη, χάρη στην αρχιτεκτονική streaming.

## Συμπέρασμα
Τώρα γνωρίζετε **πώς να μετατρέψετε email σε HTML** ενώ **μετονομάζετε πεδία email** και **προσαρμόζετε τις κεφαλίδες email** με το GroupDocs.Viewer for Java. Αυτή η τεχνική σας δίνει πλήρη έλεγχο πάνω στην παρουσίαση των μεταδεδομένων email σε εξόδους HTML.

### Επόμενα βήματα
- Δοκιμάστε πρόσθετες αντιστοιχίες πεδίων (π.χ., CC, BCC).  
- Εξερευνήστε άλλες μορφές απόδοσης όπως PDF ή PNG.  
- Επισκεφθείτε το [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) για πιο λεπτομερείς πληροφορίες API.

## Συχνές ερωτήσεις

**Q: Λειτουργεί αυτή η προσέγγιση με άλλες μορφές email όπως το EML;**  
A: Ναι, το GroupDocs.Viewer υποστηρίζει τόσο αρχεία MSG όσο και EML· η ίδια λογική αντιστοίχισης πεδίων εφαρμόζεται.

**Q: Μπορώ να εξάγω το HTML χωρίς ενσωματωμένους πόρους;**  
A: Μπορείτε να χρησιμοποιήσετε το `HtmlViewOptions.forExternalResources(...)` εάν προτιμάτε ξεχωριστά αρχεία CSS/JS.

**Q: Ποια έκδοση του GroupDocs.Viewer δοκιμάστηκε;**  
A: Ο κώδικας δοκιμάστηκε με το GroupDocs.Viewer **25.2**.

**Q: Είναι δυνατόν να αλλάξω τη γραμματοσειρά ή το στυλ των προσαρμοσμένων κεφαλίδων;**  
A: Το στυλ μπορεί να εφαρμοστεί μέσω CSS μετά την απόδοση, ή μπορείτε να ενσωματώσετε προσαρμοσμένο CSS χρησιμοποιώντας το `HtmlViewOptions.getResourcesPath()`.

**Q: Πώς μπορώ προγραμματιστικά να ανακτήσω τη διαδρομή του παραγόμενου αρχείου HTML;**  
A: Η διαδρομή ακολουθεί το μοτίβο που ορίζεται στο `pageFilePathFormat`; μπορείτε να την κατασκευάσετε χρησιμοποιώντας `String.format` με τον αριθμό σελίδας.

## Πόροι
- **Τεκμηρίωση:** Πλήρεις οδηγίες είναι διαθέσιμες στο [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Αναφορά API:** Λεπτομερείς πληροφορίες API μπορούν να βρεθούν στο [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Λήψη GroupDocs.Viewer:** Πρόσβαση στην πιο πρόσφατη έκδοση μέσω της [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Τελευταία ενημέρωση:** 2026-09-15  
**Δοκιμάστηκε με:** GroupDocs.Viewer 25.2  
**Συγγραφέας:** GroupDocs

## Σχετικές οδηγίες

- [Μετατροπή EML σε HTML με προσαρμοσμένο DateTime σε Java χρησιμοποιώντας το GroupDocs.Viewer](/viewer/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/)
- [java μετατροπή msg σε pdf – Βελτιστοποίηση απόδοσης Email σε PDF με το GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Απόδοση συνημμένων εγγράφων HTML με GroupDocs.Viewer Java – Οδηγός βήμα‑βήμα](/viewer/java/rendering-basics/render-document-attachments-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}