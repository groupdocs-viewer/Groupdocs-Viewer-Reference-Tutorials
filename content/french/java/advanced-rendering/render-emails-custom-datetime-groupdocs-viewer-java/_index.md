---
date: '2026-09-15'
description: Apprenez comment convertir eml en html avec un format de date et heure
  personnalisé et un décalage de fuseau horaire en utilisant GroupDocs.Viewer pour
  Java — idéal pour l’archivage des e‑mails et les portails d’assistance.
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: Convertissez eml en html avec un format de date et heure personnalisé
  et un décalage de fuseau horaire en utilisant GroupDocs.Viewer pour Java. Suivez
  ce guide étape par étape pour un rendu précis des e‑mails.
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: Convertir eml en html avec une date et heure personnalisées en java avec
  GroupDocs.Viewer
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: Convertir eml en html avec une date et heure personnalisées en java avec GroupDocs.Viewer
type: docs
url: /fr/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Convertir eml en html avec datetime personnalisé en java en utilisant GroupDocs.Viewer

Dans les systèmes modernes de support et d'archivage, **convertir eml en html** rapidement tout en préservant les horodatages exacts est une capacité indispensable. Ce tutoriel vous montre comment rendre un e‑mail EML en HTML, appliquer un **format datetime personnalisé**, et définir un **décalage de fuseau horaire** en utilisant GroupDocs.Viewer pour Java. À la fin, vous disposerez d'un extrait réutilisable qui produit des vues d'e‑mail précises et prêtes pour le web pour tout flux de **conversion d'e‑mail en html**.

![Render Emails with Custom DateTime with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## Réponses rapides
- **GroupDocs.Viewer peut‑il convertir EML en HTML ?** Oui – l'API rend les fichiers EML directement en HTML sans clients de messagerie externes.  
- **Ai‑je besoin d'une licence pour la production ?** Un essai gratuit suffit pour les tests ; une licence payante est requise pour les déploiements en production.  
- **Quelle version de Java est prise en charge ?** Java 8 ou supérieur est entièrement supporté.  
- **Comment modifier le format de date affiché ?** Appelez `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`.  
- **Puis‑je ajuster le fuseau horaire ?** Oui, utilisez `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`.

## Qu’est‑ce que « convertir eml en html » ?
`Convertir eml en html` est le processus de transformation d'un fichier e‑mail EML en un document HTML pour le rendu dans un navigateur. Convertir un fichier EML en HTML transforme l'e‑mail brut (y compris les en‑têtes, le corps et les pièces jointes) en un format adapté au web que les navigateurs peuvent afficher sans plugins supplémentaires. Cela facilite l'intégration des e‑mails dans les applications web, les archives ou les tableaux de bord de support.

## Pourquoi utiliser GroupDocs.Viewer pour cette tâche ?
GroupDocs.Viewer prend en charge **plus de 50 formats d’entrée et de sortie**, y compris EML, MSG, PST et PDF, et peut rendre des e‑mails de plusieurs centaines de pages sans charger le fichier complet en mémoire. Son moteur sans dépendance élimine le besoin d’Outlook ou de parseurs tiers, vous offrant un contrôle total sur le **format datetime personnalisé** et le **décalage de fuseau horaire** tout en maintenant une faible utilisation des ressources.

## Prérequis
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ et un IDE Java (IntelliJ IDEA, Eclipse, VS Code)  
- Maven pour la gestion des dépendances  

## Configuration de GroupDocs.Viewer pour Java

### Configuration Maven
Ajoutez le dépôt GroupDocs et la dépendance Viewer à votre fichier `pom.xml`.

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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

### Acquisition de licence
Commencez avec un essai gratuit ou demandez une licence temporaire pour des tests prolongés. Achetez une licence complète pour une utilisation en production.

### Initialisation de base
Créez une instance `Viewer` qui pointe vers le fichier EML que vous souhaitez convertir.

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Convertir eml en html avec datetime personnalisé en java

Les étapes suivantes vous guident dans le rendu d'un fichier EML en HTML tout en appliquant un format datetime personnalisé et un décalage de fuseau horaire.

### Étape 1 : configurer le répertoire de sortie et le chemin du fichier
Définissez où le HTML généré sera enregistré.

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Explication :* `Path.of()` crée une référence au dossier où le HTML sera enregistré. `resolve()` ajoute le nom du fichier.

### Étape 2 : initialiser le viewer avec le fichier e‑mail
Instanciez la classe `Viewer` pour le fichier EML cible.

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Explication :* L'instance `Viewer` pointe vers le fichier EML que vous souhaitez convertir.

### Étape 3 : configurer HtmlViewOptions
Créez un objet `HtmlViewOptions` qui regroupe les images et autres ressources directement dans la sortie HTML.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Explication :* `forEmbeddedResources()` regroupe les images et autres ressources directement dans la sortie HTML.

### Étape 4 : définir le format datetime personnalisé *(custom datetime java)*
`setDateTimeFormat` définit le modèle de date‑heure utilisé lors du rendu des horodatages des e‑mails.  
Définissez le modèle qui sera utilisé pour tous les horodatages dans le HTML rendu.

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Explication :* Ce modèle affiche le mois, le jour, l'année, l'heure, les minutes, le marqueur AM/PM et le décalage de fuseau horaire (`zzz`).

### Étape 5 : définir le décalage de fuseau horaire *(timezone offset java)*
`setTimeZoneOffset` spécifie le fuseau horaire qui sera appliqué à tous les horodatages des e‑mails.  
Ajustez les horodatages au fuseau horaire souhaité.

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Explication :* Ajuste les horodatages rendus au fuseau horaire souhaité. Remplacez `"GMT+1"` par tout identifiant de zone valide.

### Comment ajuster le fuseau horaire d'un e‑mail en java
Si vous devez **ajuster le fuseau horaire d'un e‑mail** au-delà de simples décalages — comme gérer les changements d'heure d'été — vous pouvez récupérer l'objet `TimeZone` approprié depuis l'API `java.util.TimeZone` en utilisant des identifiants de région tels que `"Europe/Paris"` ou `"America/New_York"` et le transmettre à `setTimeZoneOffset`. Cela garantit que les horodatages des e‑mails reflètent toujours l'heure locale correcte.

### Étape 6 : rendre le document
Exécutez la conversion et générez le fichier HTML final.

```java
viewer.view(options);
```
*Explication :* Exécute la conversion, produisant un fichier HTML avec vos paramètres de date‑heure personnalisés.

## Comment le format datetime personnalisé impacte‑t‑il le HTML rendu ?
Le format datetime personnalisé détermine la façon dont chaque horodatage d'e‑mail apparaît dans le HTML généré, affectant la lisibilité et la conformité locale. En spécifiant un modèle tel que `"MMM dd, yyyy hh:mm a zzz"`, vous assurez que chaque date soit affichée de manière cohérente, incluant l'abréviation du mois, le jour, l'année, l'heure, les minutes, le marqueur AM/PM et le décalage de fuseau horaire explicite, ce qui est crucial pour les équipes de support mondiales.

## Quels formats de fichiers GroupDocs.Viewer prend‑il en charge pour le rendu d'e‑mail ?
GroupDocs.Viewer peut rendre les fichiers **EML, MSG, PST, MBOX et EMLX** en HTML, PDF, PNG et JPEG. Il prend en charge plus de 50 formats de documents et d'images au total, vous permettant de convertir les e‑mails en n'importe quel format web‑friendly le plus courant sans convertisseurs supplémentaires.

## Comment puis‑je convertir en lot plusieurs fichiers eml ?
Placez tous les fichiers EML dans un même répertoire, parcourez chaque fichier avec une construction `for` ou `foreach`, réutilisez la même instance `HtmlViewOptions`, et appelez `viewer.view` pour chaque fichier. Cette approche minimise la surcharge de création d'objets et accélère les conversions en masse.

## Conseils de dépannage
- **FileNotFoundException :** Vérifiez les chemins utilisés dans `Viewer` et `Path.of()`.  
- **Horodatages incorrects :** Assurez‑vous que l'ID `TimeZone` correspond à votre région cible.  
- **Images manquantes :** Confirmez que vous avez utilisé `HtmlViewOptions.forEmbeddedResources()` ; sinon les ressources externes peuvent être omises.  

## Applications pratiques
1. **Archivage d'e‑mail :** Stockez des instantanés HTML recherchables des e‑mails pour les audits de conformité.  
2. **Portails de support client :** Affichez les tickets entrants avec des heures locales précises pour les agents du monde entier.  
3. **Documentation juridique :** Produisez des dossiers d'e‑mail prêts pour le tribunal avec des horodatages standardisés.  

## Considérations de performance
- Déployez sur un serveur dédié pour les conversions en masse.  
- Surveillez l'utilisation du tas Java ; augmentez `-Xmx` si vous rencontrez `OutOfMemoryError`.  
- Mettez en cache le HTML rendu lorsque le même e‑mail est demandé à plusieurs reprises afin de réduire la charge CPU.  

## Conclusion
Vous disposez maintenant d’une méthode complète, prête pour la production, pour **convertir eml en html** avec un format datetime personnalisé et un décalage de fuseau horaire en utilisant GroupDocs.Viewer pour Java. Cette solution améliore la lisibilité, garantit la précision des horodatages, et s’intègre parfaitement aux flux de travail d'archivage, de support ou juridiques.

**Prochaines étapes :** Explorez d’autres options du Viewer telles que l’injection de CSS personnalisée, la pagination ou la conversion PDF pour adapter davantage la sortie aux besoins de votre application.

## Questions fréquentes

**Q : Comment gérer les fichiers eml avec pièces jointes ?**  
R : Les pièces jointes sont automatiquement intégrées lorsque vous utilisez `HtmlViewOptions.forEmbeddedResources()`. Vous pouvez également les extraire via l’API Viewer si vous avez besoin de fichiers séparés.

**Q : Puis‑je modifier le modèle HTML ou ajouter du CSS personnalisé ?**  
R : Oui, après le rendu vous pouvez modifier le fichier HTML généré ou injecter du CSS programmé avant l’enregistrement.

**Q : Est‑il possible de rendre plusieurs fichiers eml en lot ?**  
R : Encapsulez la logique de rendu dans une boucle et réutilisez la même instance `HtmlViewOptions` pour chaque fichier.

**Q : Que faire si je dois prendre en charge d’autres formats d’e‑mail comme msg ?**  
R : GroupDocs.Viewer prend également en charge MSG, PST et d’autres conteneurs d’e‑mail — il suffit de changer l’extension du fichier dans le constructeur `Viewer`.

**Q : Ai‑je besoin d’une licence distincte pour chaque serveur ?**  
R : La licence est par déploiement ; consultez le guide de licence GroupDocs pour les scénarios multi‑serveurs.

## Ressources

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [Référence API](https://reference.groupdocs.com/viewer/java/)
- [Téléchargement](https://releases.groupdocs.com/viewer/java/)
- [Acheter](https://purchase.groupdocs.com/buy)
- [Essai gratuit](https://releases.groupdocs.com/viewer/java/)
- [Licence temporaire](https://purchase.groupdocs.com/temporary-license/)
- [Forum de support](https://forum.groupdocs.com/c/viewer/9)

---

**Dernière mise à jour :** 2026-09-15  
**Testé avec :** GroupDocs.Viewer 25.2 (Java)  
**Auteur :** GroupDocs

## Tutoriels associés

- [Convertir l'e‑mail en HTML & renommer les champs – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java convertir msg en pdf – Optimiser le rendu Email‑to‑PDF avec GroupDocs.Viewer](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [GroupDocs Viewer Java rendu HTML réactif](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)
