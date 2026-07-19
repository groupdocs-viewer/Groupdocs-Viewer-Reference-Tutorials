---
date: '2026-07-19'
description: Découvrez comment convertir PST en HTML et d’autres formats tels que
  JPG, PNG, PDF à l’aide de GroupDocs.Viewer for Java. Ce guide couvre toutes les
  étapes et configurations nécessaires.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Convertissez rapidement PST en HTML avec GroupDocs.Viewer for Java.
  Apprenez étape par étape comment exporter également vers JPG, PNG et PDF dans un
  guide prêt pour la production.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Convertir PST en HTML avec GroupDocs.Viewer for Java – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Convertir PST en HTML, JPG, PNG, PDF avec GroupDocs.Viewer for Java
type: docs
url: /fr/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Convertir PST en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour Java

Vous cherchez à **convertir pst en html** ou d'autres formats comme JPG, PNG ou PDF ? Avec la puissante bibliothèque GroupDocs.Viewer pour Java, cette tâche est simple et efficace. Dans ce tutoriel, vous apprendrez comment rendre les fichiers Outlook PST/OST en HTML compatible web, fichiers image, ou un PDF unique, facilitant le partage et l'archivage de vos archives d'e‑mail.

![Convertir PST/OST en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Convertir PST/OST en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Ce que vous apprendrez**
- Comment configurer GroupDocs.Viewer pour Java dans un projet Maven.  
- Instructions étape par étape pour **java convert pst** les fichiers en HTML, JPG, PNG et PDF.  
- Conseils de configuration pour des performances optimales et les pièges courants.

## Réponses rapides
- **Quelle bibliothèque gère la conversion PST ?** GroupDocs.Viewer for Java.  
- **Puis-je convertir PST en PDF directement ?** Oui, en utilisant `PdfViewOptions`.  
- **Une licence est‑elle requise pour la production ?** Une licence GroupDocs valide est nécessaire.  
- **Quelle version de Java est prise en charge ?** JDK 8 ou supérieure.  
- **Dois‑je extraire les pièces jointes manuellement ?** Non, le visualiseur les rend automatiquement.

## Qu’est‑ce que GroupDocs.Viewer pour Java ?
GroupDocs.Viewer pour Java est une API côté serveur qui charge plus de 100 formats de documents et d’e‑mails et les rend en sortie HTML, image ou PDF sans logiciel externe. Elle traite les fichiers PST jusqu’à 2 GB tout en maintenant l’utilisation de la mémoire sous 200 MB.

## Comment convertir pst en html avec GroupDocs.Viewer pour Java ?
Chargez le fichier PST avec `new Viewer("source.pst")`, configurez `HtmlViewOptions` pour pointer vers un dossier de sortie, et appelez `viewer.view(htmlOptions)`. L’API extrait chaque e‑mail, préserve le formatage, les pièces jointes et les métadonnées, et écrit une page HTML séparée par message — le tout en un seul appel de méthode.

### Pourquoi choisir GroupDocs.Viewer ?
- **Rendu haute fidélité** – 99,9 % du contenu des e‑mails (y compris les corps en texte enrichi, les tableaux et les images intégrées) est reproduit avec précision.  
- **Formats de sortie multiples** – Un appel d’API peut générer HTML, JPG, PNG ou PDF, couvrant plus de 50 options d’exportation.  
- **Aucune dépendance externe** – Aucun besoin d’Outlook, Exchange Server ou de convertisseurs tiers ; tout s’exécute dans votre runtime Java.

## Prérequis
- **GroupDocs.Viewer pour Java** – version 25.2 ou ultérieure.  
- **Java Development Kit (JDK)** – 8 ou plus récent.  
- Maven pour la gestion des dépendances.  
- Connaissances de base en Java et familiarité avec Maven.

## Configuration de GroupDocs.Viewer pour Java
`Viewer` est la classe principale de GroupDocs.Viewer pour Java qui charge un document et le rend dans le format choisi. Ajoutez le dépôt GroupDocs et la dépendance à votre `pom.xml` :

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

### Acquisition de licence
- **Essai gratuit** – explorez toutes les fonctionnalités sans frais.  
- **Licence temporaire** – prolongez la période d’évaluation si besoin.  
- **Licence complète** – requise pour les déploiements en production.

### Initialisation de base
Les instances de `Viewer` sont légères ; vous pouvez réutiliser une même instance pour de nombreux fichiers afin de minimiser la surcharge de création d’objets.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Guide d’implémentation
Les sections suivantes vous guident dans le rendu des fichiers PST/OST dans chaque format supporté.

### Rendu des documents PST/OST en HTML
#### Étape 1 : Configurer le répertoire de sortie
Définissez un dossier où les pages HTML seront écrites. GroupDocs crée un sous‑dossier pour chaque e‑mail afin de garder les ressources organisées.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Étape 2 : Configurer les options de chargement
`LoadOptions` vous permet de spécifier la gestion des mots de passe, les délais d’attente de chargement des ressources et le rendu sélectif des pages. Un délai de 30 secondes fonctionne bien pour la plupart des environnements serveur.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Étape 3 : Définir les options de vue HTML
`HtmlViewOptions` spécifie le dossier de sortie, la gestion des ressources et les paramètres CSS optionnels pour la conversion HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Étape 4 : Initialiser le Viewer et rendre le HTML
Créez un objet `Viewer`, passez le chemin du fichier PST, et appelez `view` avec les `HtmlViewOptions`. L’API itère automatiquement sur tous les messages du PST et génère une hiérarchie HTML propre.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Rendu des documents PST/OST en JPG
#### Étape 1 : Configurer le répertoire de sortie
Créez un dossier dédié aux instantanés JPG ; chaque e‑mail deviendra un ou plusieurs fichiers image selon sa longueur.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Étape 2 : Configurer les options de chargement
Les mêmes `LoadOptions` utilisées pour le HTML peuvent être réutilisées ici, assurant une gestion cohérente des mots de passe entre les formats.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Étape 3 : Définir les options de vue JPG
`JpgViewOptions` contrôle la résolution de l’image, la qualité et le dossier de sortie pour la conversion JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Étape 4 : Initialiser le Viewer et rendre le JPG
Utilisez `viewer.view(jpgOptions)` pour générer des fichiers JPEG de haute qualité prêts pour la prévisualisation web.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Rendu des documents PST/OST en PNG
#### Étape 1 : Configurer le répertoire de sortie
La sortie PNG est utile lorsque vous avez besoin d’une qualité sans perte pour l’archivage ou le traitement OCR.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Étape 2 : Configurer les options de chargement
Aucun paramètre supplémentaire n’est requis au-delà de la configuration du mot de passe et du délai d’attente.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Étape 3 : Définir les options de vue PNG
`PngViewOptions` vous permet de définir un arrière‑plan transparent et le dossier de sortie pour les images PNG sans perte.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Étape 4 : Initialiser le Viewer et rendre le PNG
Instanciez `viewer.view(pngOptions)` pour produire des instantanés PNG de chaque e‑mail.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendu des documents PST/OST en PDF
#### Étape 1 : Configurer le répertoire de sortie
Un seul fichier PDF par PST simplifie les flux de travail de révision juridique et réduit l’encombrement de stockage.

CODE_BLOCK_PLACEHOLDER_14_END

#### Étape 2 : Configurer les options de chargement
Lors de la conversion en PDF, vous pouvez activer `setEmbedFonts(true)` pour garantir la fidélité visuelle sur n’importe quelle machine.

CODE_BLOCK_PLACEHOLDER_15_END

#### Étape 3 : Définir les options de vue PDF
`PdfViewOptions` vous permet de choisir le niveau de compression, d’incorporer les polices et de définir le nom du fichier de sortie pour la conversion PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### Étape 4 : Initialiser le Viewer et rendre le PDF
Créez `PdfViewOptions`, choisissez éventuellement un niveau de compression, et appelez `viewer.view(pdfOptions)`. L’API fusionne tous les e‑mails en un seul document PDF consultable.

CODE_BLOCK_PLACEHOLDER_17_END

## Applications pratiques
- **Archivage d’e‑mail :** Transformez les grandes archives PST en HTML ou PDF consultables pour la conformité.  
- **Systèmes de gestion de documents :** Stockez les fichiers convertis dans des systèmes qui n’acceptent que PDF, PNG ou JPG.  
- **Plateformes de collaboration :** Partagez les e‑mails convertis sous forme d’images dans Slack ou Teams.  
- **Révision juridique :** Fournissez aux tribunaux des versions PDF des preuves d’e‑mail.  
- **Stratégies de sauvegarde :** Conservez des instantanés PNG ou JPG légers des messages critiques.

## Considérations de performance
- **Gestion des ressources :** Réutilisez les instances `Viewer` lors du traitement de plusieurs fichiers pour réduire la surcharge.  
- **Optimisation de la mémoire :** Ajustez `loadOptions.setResourceLoadingTimeout` en fonction de la capacité du serveur.  
- **Traitement asynchrone :** Déléguez la conversion à des threads en arrière‑plan pour des interfaces réactives.

## Questions fréquemment posées
**Q : Comment **convertir pst en pdf** avec la même base de code ?**  
R : Utilisez `PdfViewOptions` comme indiqué dans la section de rendu PDF ; le reste du code reste identique.

**Q : GroupDocs.Viewer peut‑il gérer les fichiers PST chiffrés ?**  
R : Oui, fournissez le mot de passe via `LoadOptions.setPassword("yourPassword")` avant le rendu.

**Q : Quelle est la différence entre **java convert pst** en PNG vs JPG ?**  
R : PNG conserve une qualité sans perte, idéale pour les captures d’écran, tandis que JPG offre des tailles de fichier plus petites pour les aperçus d’e‑mail.

**Q : Existe‑t‑il un moyen de **how to convert pst** des fichiers en masse ?**  
R : Encapsulez la logique de rendu dans une boucle qui parcourt un répertoire de fichiers PST ; réutilisez la même configuration `Viewer` pour chaque fichier.

**Q : L’API prend‑elle en charge la conversion de fichiers PST supérieurs à 1 GB ?**  
R : Oui, GroupDocs.Viewer diffuse les données et peut traiter des fichiers jusqu’à 2 GB sans charger l’ensemble de l’archive en mémoire.

## Conclusion
Vous disposez maintenant d’un guide complet, prêt pour la production, pour **convertir pst en html**, JPG, PNG et PDF en utilisant GroupDocs.Viewer pour Java. En suivant les étapes ci‑dessus, vous pouvez intégrer la conversion d’e‑mail dans n’importe quel flux de travail basé sur Java, améliorer l’accessibilité et répondre aux exigences de conformité.

---

**Dernière mise à jour :** 2026-07-19  
**Testé avec :** GroupDocs.Viewer pour Java 25.2  
**Auteur :** GroupDocs

## Tutoriels associés
- [Convertir NSF en PDF, HTML, JPG, PNG avec GroupDocs.Viewer pour Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Convertir ODF en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Comment convertir DOCX en HTML avec GroupDocs.Viewer pour Java : guide étape par étape](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)