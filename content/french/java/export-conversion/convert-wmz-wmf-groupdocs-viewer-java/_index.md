---
date: '2026-07-19'
description: Apprenez comment convertir WMZ en PDF, HTML, JPG et PNG avec GroupDocs
  Viewer for Java. Guide étape par étape pour la conversion java de graphiques vectoriels.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Convertir WMZ en PDF, HTML, JPG et PNG avec GroupDocs Viewer for Java.
  Ce tutoriel montre, étape par étape, la conversion java de graphiques vectoriels
  avec une haute fidélité.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Convertir WMZ en PDF avec GroupDocs Viewer for Java – Guide rapide
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Convertir WMZ en PDF et autres formats à l'aide de GroupDocs Viewer for Java
type: docs
url: /fr/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Convertir WMZ en PDF et autres formats avec GroupDocs Viewer pour Java

Convertir les fichiers WMZ (Web Metafile) et WMF (Windows Metafile) en formats plus accessibles—en particulier **convert WMZ to PDF**—peut être délicat car ces formats graphiques vectoriels stockent des instructions de dessin plutôt que des données pixel. Avec **GroupDocs Viewer for Java**, vous pouvez rendre les documents WMZ/WMF en HTML, JPG, PNG, **PDF**, et d’autres formats populaires en quelques lignes de code seulement, tout en conservant la fidélité visuelle originale.

![Convertir les documents WMZ/WMF avec GroupDocs.Viewer pour Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Convertir les documents WMZ/WMF avec GroupDocs.Viewer pour Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Réponses rapides
- **Quels formats WMZ/WMF peuvent être convertis ?** HTML, JPG, PNG et PDF sont entièrement pris en charge.  
- **Ai-je besoin d'une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale supprime les limites d'évaluation.  
- **Quelle version de Java est requise ?** Java 8 ou ultérieure est recommandée.  
- **Puis-je rendre uniquement des pages spécifiques ?** Oui, vous pouvez spécifier des plages de pages dans les options d'affichage.  
- **L'utilisation de la mémoire est‑elle un problème pour les gros fichiers ?** Utilisez try‑with‑resources et ne rendez que les pages nécessaires pour garder la mémoire basse.

## Qu’est‑ce que “convert WMZ to PDF” ?
**Convert WMZ to PDF** signifie prendre un fichier vectoriel WMZ et intégrer ses instructions de dessin dans un conteneur PDF, produisant un document universellement affichable, interrogeable et imprimable. La conversion préserve la qualité des lignes et des formes, de sorte que le PDF résultant ressemble exactement au graphique original sur n'importe quel appareil.

## Pourquoi utiliser GroupDocs Viewer pour Java pour convertir des graphiques vectoriels ?
GroupDocs Viewer pour Java gère le rendu WMZ et WMF avec **high fidelity**, préservant le détail vectoriel que vous exportiez en PDF, PNG ou HTML. La bibliothèque fonctionne sur n'importe quelle plateforme avec un JDK, ne nécessite aucun composant Windows natif, et fournit une API à appel unique qui s'adapte des fichiers à icône unique aux dessins techniques multi‑pages. Dans les tests de référence, elle traite **plus de 200 pages WMZ en moins de 12 secondes** sur un serveur standard à 4 cœurs.

## Prérequis
- **GroupDocs.Viewer for Java** – moteur de rendu principal.  
- Java Development Kit (JDK) 8 ou plus récent.  
- Un IDE tel qu'IntelliJ IDEA ou Eclipse (optionnel mais recommandé).  
- Maven (ou Gradle) pour la gestion des dépendances.  

Une connaissance de Java NIO (`java.nio.file.Path`) et des opérations d'E/S de fichiers de base vous aidera à suivre les exemples sans problème.

## Configuration de GroupDocs.Viewer pour Java

La classe `Viewer` est le point d'entrée de toutes les opérations de rendu. Elle représente un moteur thread‑safe qui peut être réutilisé pour plusieurs conversions.

Ajoutez le dépôt et la dépendance à votre `pom.xml` (ou l'équivalent Gradle). Après que Maven ait résolu l'artifact, vous pouvez créer une instance `Viewer` qui sera réutilisée pour chaque étape de conversion.

> **Conseil de licence :** Utilisez un essai gratuit pour l'évaluation, puis appliquez une licence temporaire ou achetée pour débloquer toutes les fonctionnalités.

## Guide d'implémentation

Ci-dessous, nous parcourons quatre scénarios de conversion—HTML, JPG, PNG et PDF. Chaque scénario suit le même schéma en trois étapes :

1. **Définir le répertoire de sortie** où les fichiers rendus seront enregistrés.  
2. **Créer une instance `Viewer`** pointant vers le fichier source WMZ/WMF.  
3. **Configurer les options d'affichage spécifiques au format** et appeler la méthode `view`.  

La méthode `view` effectue le rendu en fonction des options fournies.

### Rendu WMZ/WMF en HTML

#### Vue d'ensemble
La sortie HTML vous permet d'intégrer le graphique directement dans des pages web, avec toutes les ressources (images, CSS) contenues dans un seul fichier.

**Étape 1 : Définir le chemin du répertoire de sortie**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Étape 2 : Initialiser le Viewer et rendre en HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Rendu WMZ/WMF en JPG

#### Vue d'ensemble
JPG est un format raster largement supporté, parfait pour les aperçus rapides ou les pièces jointes d'email.

**Étape 1 : Définir le chemin du répertoire de sortie**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Étape 2 : Initialiser le Viewer et rendre en JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendu WMZ/WMF en PNG

#### Vue d'ensemble
PNG prend en charge la transparence, ce qui le rend idéal pour les graphiques qui doivent se fondre avec différents arrière-plans.

**Étape 1 : Définir le chemin du répertoire de sortie**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Étape 2 : Initialiser le Viewer et rendre en PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendu WMZ/WMF en PDF

#### Vue d'ensemble
PDF fournit un document indépendant de la plateforme, interrogeable, qui conserve la mise en page originale.

**Étape 1 : Définir le chemin du répertoire de sortie**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Étape 2 : Initialiser le Viewer et rendre en PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Problèmes courants et solutions

`PageStreamViewOptions` permet de rendre des pages spécifiques en flux.  
`PdfViewOptions` configure les paramètres de sortie PDF tels que la plage de pages et le DPI.  
`FontSettings` vous permet de fournir des polices personnalisées lorsque le document source référence des polices manquantes.

| Problème | Cause | Solution |
|----------|-------|----------|
| **OutOfMemoryError** sur de gros fichiers WMZ | Viewer charge le document entier en mémoire | Rendre une page à la fois en utilisant `PageStreamViewOptions` ou augmenter le tas JVM (`-Xmx`). |
| **Polices manquantes** dans le PDF | Police non intégrée dans le WMZ source | Installez les polices requises sur la machine hôte ou utilisez `FontSettings` pour fournir des polices personnalisées. |
| **Sortie PNG vide** | Chemin de sortie incorrect ou permissions d'écriture insuffisantes | Vérifiez que `outputDirectory` existe et que l'application a les droits d'écriture. |
| **Ressources HTML ne se chargent pas** | Utilisation de `forExternalResources` sans copier les fichiers | Utilisez `forEmbeddedResources` pour un fichier HTML autonome. |

## Questions fréquentes

**Q : Puis‑je convertir WMF en PNG avec le même code ?**  
R : Oui. L'exemple PNG fonctionne pour les fichiers WMZ et WMF ; il suffit de remplacer `TestFiles.SAMPLE_WMZ` par votre source WMF.

**Q : Est‑il possible de convertir seulement un sous‑ensemble de pages ?**  
R : Absolument. Utilisez `PdfViewOptions` (ou les options correspondantes pour les autres formats) et appelez `setPageNumbers(List<Integer>)` avant le rendu.

**Q : Ai‑je besoin d’une licence séparée pour chaque format de sortie ?**  
R : Non. Une licence unique GroupDocs Viewer couvre tous les formats supportés, y compris HTML, JPG, PNG et PDF.

**Q : Comment “java convert vector graphics” impacte‑t‑il les performances ?**  
R : La conversion vecteur‑vers‑raster est gourmande en CPU. Pour de gros lots, envisagez le multithreading et réutilisez une seule instance `Viewer` pour plusieurs fichiers.

**Q : Le PDF conservera‑t‑il la qualité vectorielle, ou sera‑t‑il rasterisé ?**  
R : Lors de la conversion WMZ/WMF en PDF, GroupDocs Viewer préserve les instructions vectorielles lorsque c’est possible, ce qui donne un PDF évolutif.

## Conclusion

Vous disposez maintenant d'un guide complet, prêt pour la production, pour **convert WMZ to PDF** et d'autres formats courants en utilisant **GroupDocs Viewer for Java**. Que vous construisiez un service web qui sert des graphiques à la volée ou un outil d'archivage qui stocke les documents en PDF, les étapes ci‑dessus vous aideront à y parvenir rapidement et de manière fiable. Explorez davantage l'API pour personnaliser les plages de pages, les paramètres DPI ou le filigrane selon les besoins de votre projet.

---

**Last Updated:** 2026-07-19  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

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

## Tutoriels associés

- [Comment convertir OBJ en HTML, JPG, PNG et PDF en Java avec GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Convertir IGS en PDF, HTML, JPG et PNG avec GroupDocs.Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java : Convertir des documents en PDF – Guide complet](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)