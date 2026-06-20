---
date: '2026-06-20'
description: Tutoriel GroupDocs Viewer Java qui montre comment rendre les fichiers
  APNG en HTML, JPG, PNG et PDF. Inclut setup, code snippets et practical use cases.
keywords:
- groupdocs viewer java tutorial
- render animated png
- how to convert apng to jpg
schemas:
- author: GroupDocs
  dateModified: '2026-06-20'
  description: GroupDocs Viewer Java tutorial that shows how to render APNG files
    to HTML, JPG, PNG, and PDF. Includes setup, code snippets, and practical use cases.
  headline: 'GroupDocs Viewer Java Tutorial: Render Animated PNGs'
  type: TechArticle
- description: GroupDocs Viewer Java tutorial that shows how to render APNG files
    to HTML, JPG, PNG, and PDF. Includes setup, code snippets, and practical use cases.
  name: 'GroupDocs Viewer Java Tutorial: Render Animated PNGs'
  steps:
  - name: '**Set Up Paths** – define where the HTML file and its resources will be
      saved.'
    text: '**Set Up Paths** – define where the HTML file and its resources will be
      saved.'
  - name: '**Initialize Viewer** – create a `Viewer` object with the APNG path.'
    text: '**Initialize Viewer** – create a `Viewer` object with the APNG path.'
  - name: '**Configure Options** – use `HtmlViewOptions.forEmbeddedResources` to embed
      CSS, JS, and images directly into the HTML file, eliminating external dependencies.'
    text: '**Configure Options** – use `HtmlViewOptions.forEmbeddedResources` to embed
      CSS, JS, and images directly into the HTML file, eliminating external dependencies.'
  - name: '**Render** – call `viewer.view(documentPath, htmlOptions)`.'
    text: '**Render** – call `viewer.view(documentPath, htmlOptions)`.'
  - name: '**Configure Paths** – specify the output folder for the generated JPG files.'
    text: '**Configure Paths** – specify the output folder for the generated JPG files.'
  - name: '**Render to JPG** – invoke `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.'
    text: '**Render to JPG** – invoke `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.'
  - name: '**Result** – each frame becomes `output_1.jpg`, `output_2.jpg`, … preserving
      the original animation sequence.'
    text: '**Result** – each frame becomes `output_1.jpg`, `output_2.jpg`, … preserving
      the original animation sequence.'
  - name: '**Set Output Paths** – choose a folder for the PNG sequence.'
    text: '**Set Output Paths** – choose a folder for the PNG sequence.'
  - name: '**Execute Rendering** – call `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.'
    text: '**Execute Rendering** – call `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.'
  - name: '**Outcome** – you receive a series of PNG files that can be recombined
      or used individually.'
    text: '**Outcome** – you receive a series of PNG files that can be recombined
      or used individually.'
  type: HowTo
- questions:
  - answer: Yes, it supports GIF, WebP, and even animated SVG, providing the same
      HTML, image, and PDF output options.
    question: Can GroupDocs Viewer render other animated formats like GIF or WebP?
  - answer: There’s no hard limit, but performance may degrade after ~500 frames;
      consider down‑sampling for very large animations.
    question: Is there a limit to the number of frames an APNG can have?
  - answer: APNG does not support encryption, but if the file is inside a ZIP archive,
      supply the password via `Viewer`’s `load` method.
    question: How do I handle password‑protected APNG files?
  - answer: Absolutely—use `JpgViewOptions.setResolution(300)` and `setQuality(90)`
      before calling `view`.
    question: Can I customize the DPI or quality of the generated JPGs?
  - answer: Yes, GroupDocs Viewer is pure Java and runs on any OS with a compatible
      JRE, making it ideal for Docker deployments.
    question: Does the library work on Linux containers?
  type: FAQPage
title: 'Tutoriel GroupDocs Viewer Java : Rendu des PNG animés'
type: docs
url: /fr/java/rendering-basics/render-apng-groupdocs-viewer-java/
weight: 1
---

# Tutoriel GroupDocs Viewer Java : Rendu des PNG animés

Dans ce **tutoriel GroupDocs Viewer Java**, vous découvrirez comment transformer des fichiers Animated PNG (APNG) en formats HTML, JPG, PNG et PDF en utilisant la robuste bibliothèque GroupDocs.Viewer. Que vous construisiez un portail web, un outil de reporting ou une chaîne de publication numérique, le rendu correct des APNG est essentiel pour préserver la qualité de l'animation sur toutes les plateformes.

![Rendu des PNG animés avec GroupDocs.Viewer pour Java](/viewer/rendering-basics/render-animated-pngs-java.png)  
[Rendu des PNG animés avec GroupDocs.Viewer pour Java](/viewer/rendering-basics/render-animated-pngs-java.png)

## Réponses rapides
- **Que fait GroupDocs.Viewer ?** Il rend plus de 70 types de fichiers—y compris les APNG—en HTML, images et PDF sans nécessiter de logiciel externe.  
- **Combien de lignes de code sont nécessaires pour convertir un APNG en JPG ?** Juste deux lignes : créez une instance `Viewer` et appelez `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.  
- **Ai-je besoin d'une licence pour le développement ?** Une licence d'essai fonctionne pour les tests ; une licence commerciale est requise pour la production.  
- **Puis-je rendre de grands APNG (plus de 100 images) efficacement ?** Oui—utilisez try‑with‑resources et diffusez la sortie pour maintenir une faible utilisation de la mémoire.  
- **Maven est-il le seul moyen d'ajouter la bibliothèque ?** Maven est recommandé, mais vous pouvez également utiliser Gradle ou ajouter manuellement les JAR.

## Qu'est-ce que GroupDocs Viewer ?
**GroupDocs Viewer** est un composant Java qui convertit plus de 70 formats de documents et d'images en représentations compatibles web telles que HTML, JPG, PNG et PDF. Il gère les mises en page complexes, conserve les graphiques vectoriels et prend en charge les formats animés comme APNG sans dépendances externes.

## Pourquoi rendre les PNG animés avec GroupDocs Viewer ?
GroupDocs Viewer offre un moyen fiable et haute performance de convertir les APNG tout en préservant le timing et la transparence de l'animation. Il élimine le besoin d'outils tiers, fonctionne sur n'importe quelle plateforme et s'intègre facilement aux applications Java.

- **Large prise en charge des formats :** plus de 70 formats d'entrée, y compris APNG, PDF, DOCX et SVG.  
- **Optimisé pour la performance :** traite des documents de plusieurs centaines de pages ou des animations de 200 images en utilisant moins de 150 Mo de RAM sur un serveur typique.  
- **Zero‑install :** aucune nécessité de bibliothèques natives ou de codecs spécifiques au système d'exploitation, ce qui simplifie le déploiement sur des conteneurs.  
- **Sortie cohérente :** garantit un rendu pixel‑parfait, préservant la transparence et le timing de l'animation.

## Prérequis
- **Java Development Kit (JDK) 8+** – assure la compatibilité avec les fonctionnalités modernes du langage.  
- **Maven** – simplifie la gestion des dépendances ; Gradle fonctionne également.  
- **Un fichier APNG** – placez-le dans le dossier `resources` de votre projet (par ex., `src/main/resources/sample.apng`).  

## Configuration de GroupDocs Viewer pour Java

### Configuration Maven
Ajoutez la dépendance suivante à votre `pom.xml` pour récupérer la dernière version stable :

```xml
<repositories>
   <repository>
      <id>groupdocs-repo</id>
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
Pour évaluer GroupDocs Viewer, vous pouvez :

- **Télécharger une version d'essai** depuis le [site GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Demander une licence temporaire** pour tester toutes les fonctionnalités.  
- **Acheter une licence de production** pour une utilisation commerciale illimitée.  
- Pour des instructions détaillées, consultez la [documentation officielle](https://docs.groupdocs.com/viewer/java/).

### Initialisation de base
La classe `Viewer` est le point d'entrée pour toutes les opérations de rendu. Elle charge le fichier source et fournit des méthodes pour générer différents formats.

`Viewer` représente un document ou une image et orchestre le rendu vers le format de sortie choisi.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.*;
```

## Comment rendre un PNG animé en HTML ?
Chargez le fichier APNG, configurez les options HTML, et appelez `view`. Le processus est simple et ne nécessite généralement que quelques lignes de code, ce qui le rend idéal pour des intégrations rapides dans des services web ou des tâches par lots.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result.html");
   ```

### Ancre de définition – Instance Viewer
`Viewer` est la classe principale de GroupDocs.Viewer qui représente un document ou une image et orchestre le rendu vers le format de sortie choisi.

### Rendu HTML étape par étape
1. **Configurer les chemins** – définissez où le fichier HTML et ses ressources seront enregistrés.  
2. **Initialiser Viewer** – créez un objet `Viewer` avec le chemin de l'APNG.  
3. **Configurer les options** – utilisez `HtmlViewOptions.forEmbeddedResources` pour intégrer le CSS, le JS et les images directement dans le fichier HTML, éliminant les dépendances externes.  
4. **Rendre** – appelez `viewer.view(documentPath, htmlOptions)`.

## Comment convertir un APNG en JPG ?
GroupDocs Viewer peut extraire chaque image d'animation en tant qu'image JPG individuelle, ce qui est parfait pour les miniatures ou les aperçus statiques. La conversion conserve l'ordre original des images et vous permet de contrôler la qualité et la résolution de l'image.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result_{0}.jpg");
   ```

### Ancre de définition – JpgViewOptions
`JpgViewOptions` définit comment chaque image de l'APNG source est rendue dans un fichier JPEG séparé, vous permettant de définir la qualité, le DPI et les conventions de nommage.

### Conversion JPG étape par étape
1. **Configurer les chemins** – spécifiez le dossier de sortie pour les fichiers JPG générés.  
2. **Rendre en JPG** – invoquez `viewer.view(documentPath, JpgViewOptions.forEmbeddedResources(outputPath))`.  
3. **Résultat** – chaque image devient `output_1.jpg`, `output_2.jpg`, … en préservant la séquence d'animation originale.

## Comment convertir un APNG en PNG ?
Lorsque la qualité sans perte est requise, le PNG est le format cible idéal. GroupDocs Viewer extrait chaque image sans artefacts de compression, conservant la transparence intacte et assurant une fidélité pixel‑parfait.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result_{0}.png");
   ```

### Ancre de définition – PngViewOptions
`PngViewOptions` indique au viewer d'écrire chaque image d'animation en tant que fichier PNG séparé, en conservant la transparence et les données de pixels exactes.

### Extraction PNG étape par étape
1. **Définir les chemins de sortie** – choisissez un dossier pour la séquence PNG.  
2. **Exécuter le rendu** – appelez `viewer.view(documentPath, PngViewOptions.forEmbeddedResources(outputPath))`.  
3. **Résultat** – vous obtenez une série de fichiers PNG qui peuvent être recombinés ou utilisés individuellement.

## Comment convertir un APNG en PDF ?
Compiler une séquence animée en un seul PDF est utile pour la documentation imprimable ou les besoins d'archivage. Chaque image devient une page séparée, préservant l'ordre de l'animation dans un format statique et partageable.

```java
   Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
   Path pageFilePathFormat = outputDirectory.resolve("apng_result.pdf");
   ```

### Ancre de définition – PdfViewOptions
`PdfViewOptions` regroupe toutes les images de l'APNG en un PDF multipage, chaque image occupant une page distincte.

### Génération PDF étape par étape
1. **Définir les chemins** – indiquez le chemin du fichier PDF de destination.  
2. **Rendre en PDF** – exécutez `viewer.view(documentPath, PdfViewOptions.forEmbeddedResources(outputPath))`.  
3. **Résultat** – un PDF où chaque page reflète une image de l'animation originale.

## Applications pratiques
- **Développement web :** intégrez des APNG dans des blogs ou des pages produit sans recourir aux GIF, assurant une animation plus fluide et des tailles de fichier plus petites.  
- **Publication numérique :** convertissez des graphiques animés en documents PDF pour les conférences, préservant le récit visuel.  
- **Actifs marketing :** générez des captures JPG ou PNG haute résolution pour les bannières, publicités et publications sur les réseaux sociaux.  
- **Visualisation de données :** transformez des graphiques de séries temporelles en images image par image pour les tableaux de bord analytiques.

## Considérations de performance
- **Optimisation de la taille de l'image :** redimensionnez ou compressez l'APNG source avant le rendu pour réduire l'utilisation du CPU.  
- **Gestion des ressources :** encapsulez `Viewer` dans un bloc try‑with‑resources pour fermer automatiquement les flux et libérer les tampons natifs.  
- **Traitement par lots :** lors du traitement de dizaines d'APNG, traitez-les par lots de 10 à 20 pour éviter les pics de mémoire.

## Problèmes courants et solutions
- **Images manquantes :** assurez-vous que l'APNG respecte la spécification APNG ; certains outils anciens produisent des fichiers non standard.  
- **Timing incorrect :** utilisez `AnimatedPngOptions` (si disponible) pour ajuster le délai entre les images après le rendu.  
- **Erreurs de mémoire insuffisante :** activez `viewer.setCacheSize(50)` pour limiter la mise en cache en mémoire pour les grandes animations.

## Questions fréquemment posées

**Q : GroupDocs Viewer peut-il rendre d'autres formats animés comme GIF ou WebP ?**  
R : Oui, il prend en charge GIF, WebP et même SVG animé, offrant les mêmes options de sortie HTML, image et PDF.

**Q : Existe-t-il une limite au nombre d'images qu'un APNG peut contenir ?**  
R : Il n’y a pas de limite stricte, mais les performances peuvent diminuer après ~500 images ; envisagez un sous‑échantillonnage pour les très grandes animations.

**Q : Comment gérer les fichiers APNG protégés par mot de passe ?**  
R : L'APNG ne prend pas en charge le chiffrement, mais si le fichier est dans une archive ZIP, fournissez le mot de passe via la méthode `load` de `Viewer`.

**Q : Puis-je personnaliser le DPI ou la qualité des JPG générés ?**  
R : Absolument—utilisez `JpgViewOptions.setResolution(300)` et `setQuality(90)` avant d’appeler `view`.

**Q : La bibliothèque fonctionne-t-elle sur des conteneurs Linux ?**  
R : Oui, GroupDocs Viewer est purement Java et fonctionne sur tout OS avec une JRE compatible, ce qui le rend idéal pour les déploiements Docker.

---

**Dernière mise à jour :** 2026-06-20  
**Testé avec :** GroupDocs.Viewer 23.9 pour Java  
**Auteur :** GroupDocs

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
       // Render the APNG into HTML with embedded resources.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
       // Each frame becomes a separate JPG image.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       PngViewOptions options = new PngViewOptions(pageFilePathFormat);
       // Converts each frame to a separate PNG.
       viewer.view(options);
   }
   ```

```java
   try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_APNG")) {
       PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
       // Convert the APNG into a single PDF.
       viewer.view(options);
   }
   ```

## Tutoriels associés

- [Tutoriel de rendu de documents Java - Convertir des fichiers en HTML, PDF et images](/viewer/java/rendering-basics/)
- [Comment rendre un PDF en HTML et optimiser la qualité d'image en Java avec GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [Comment convertir des fichiers DOCX en PNG avec GroupDocs.Viewer pour Java](/viewer/java/rendering-basics/render-docx-png-groupdocs-viewer-java/)