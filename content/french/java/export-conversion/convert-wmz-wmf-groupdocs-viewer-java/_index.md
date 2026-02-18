---
date: '2026-02-18'
description: Apprenez à convertir les fichiers WMZ et WMF en PDF, HTML, JPG et PNG
  à l'aide de GroupDocs Viewer pour Java. Ce guide couvre GroupDocs Viewer Java et
  la conversion Java de graphiques vectoriels.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Comment convertir WMZ en PDF et autres formats avec GroupDocs Viewer pour Java
type: docs
url: /fr/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 => "**Auteur :** GroupDocs"

Make sure to keep markdown formatting.

Now produce final output with all translations. Ensure code block placeholders remain unchanged.

Let's assemble.# Comment convertir WMZ en PDF et autres formats avec GroupDocs Viewer pour Java

Convertir les fichiers WMZ (Web Metafile) et WMF (Windows Metafile) en formats plus accessibles—en particulier **convert WMZ to PDF**—peut être délicat car ces formats graphiques vectoriels stockent des instructions de dessin plutôt que des données de pixels. Avec **GroupDocs Viewer for Java**, vous pouvez rendre les documents WMZ/WMF en HTML, JPG, PNG, **PDF**, et d’autres formats populaires en quelques lignes de code.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

Dans ce tutoriel, vous apprendrez comment configurer la bibliothèque, rendre les fichiers WMZ/WMF dans le format souhaité, et gérer les problèmes courants. À la fin, vous pourrez intégrer **groupdocs viewer java** dans vos applications Java pour **java convert vector graphics** rapidement et de manière fiable.

## Réponses rapides
- **Quels formats WMZ/WMF peuvent être convertis ?** HTML, JPG, PNG et PDF sont entièrement pris en charge.  
- **Ai-je besoin d’une licence pour le développement ?** Un essai gratuit suffit pour les tests ; une licence commerciale supprime les limites d’évaluation.  
- **Quelle version de Java est requise ?** Java 8 ou ultérieure est recommandée.  
- **Puis-je rendre uniquement des pages spécifiques ?** Oui, vous pouvez spécifier des plages de pages dans les options d’affichage.  
- **L’utilisation de la mémoire est‑elle un problème pour les gros fichiers ?** Utilisez try‑with‑resources et ne rendez que les pages nécessaires pour garder la mémoire basse.

## Qu’est‑ce que “convert WMZ to PDF” ?
Convertir WMZ en PDF signifie prendre le fichier WMZ basé sur des vecteurs et le rasteriser (ou en conserver les données vectorielles) dans un conteneur PDF. Le PDF est universellement visualisable, interrogeable et imprimable, ce qui le rend idéal pour l’archivage et le partage des graphiques WMZ.

## Pourquoi utiliser GroupDocs Viewer pour Java pour convertir des graphiques vectoriels ?
- **Haute fidélité** : La bibliothèque préserve la qualité de dessin originale, que vous exportiez en PDF ou PNG.  
- **Aucune dépendance externe** : Pas besoin de bibliothèques Windows natives ; tout fonctionne sur n’importe quelle plateforme avec un JDK.  
- **API simple** : Une instance `Viewer` et un appel unique à `view` gèrent toute la conversion.  
- **Scalable** : Fonctionne aussi bien pour des icônes d’une seule page que pour des dessins techniques multi‑pages.

## Prérequis

### Bibliothèques requises
- **GroupDocs.Viewer for Java** – le moteur de rendu principal.  
- Java Development Kit (JDK) 8+.

### Configuration de l’environnement
- IDE tel qu’IntelliJ IDEA ou Eclipse.  
- Maven pour la gestion des dépendances (ou Gradle si vous préférez).

### Prérequis de connaissances
- Familiarité avec le I/O de fichiers Java (`java.nio.file.Path`).  
- Compréhension de base du fonctionnement du rendu des visionneuses de documents.

## Configuration de GroupDocs.Viewer pour Java

Ajoutez le dépôt et la dépendance à votre `pom.xml` :

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

> **Conseil licence :** Utilisez un essai gratuit pour l’évaluation, puis appliquez une licence temporaire ou achetée pour débloquer toutes les fonctionnalités.

Une fois la dépendance résolue, vous pouvez créer une instance `Viewer` qui sera réutilisée pour chaque étape de conversion.

## Guide d’implémentation

Nous parcourrons quatre scénarios de conversion : HTML, JPG, PNG et PDF. Chaque exemple suit le même schéma — définir un chemin de sortie, instancier `Viewer` avec le fichier WMZ source, configurer les options de vue appropriées, et appeler `view`.

### Rendu WMZ/WMF en HTML

#### Vue d’ensemble
La sortie HTML vous permet d’intégrer le graphique directement dans les pages web, avec toutes les ressources (images, CSS) contenues dans un seul fichier.

**Étape 1 : Définir le chemin du répertoire de sortie**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Étape 2 : Initialiser Viewer et rendre en HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Rendu WMZ/WMF en JPG

#### Vue d’ensemble
JPG est un format raster largement supporté, parfait pour des aperçus rapides ou des pièces jointes d’email.

**Étape 1 : Définir le chemin du répertoire de sortie**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Étape 2 : Initialiser Viewer et rendre en JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendu WMZ/WMF en PNG

#### Vue d’ensemble
PNG prend en charge la transparence, ce qui le rend idéal pour les graphiques qui doivent se fondre avec différents arrière-plans.

**Étape 1 : Définir le chemin du répertoire de sortie**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Étape 2 : Initialiser Viewer et rendre en PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendu WMZ/WMF en PDF

#### Vue d’ensemble
PDF fournit un document indépendant de la plateforme, interrogeable, qui conserve la mise en page originale.

**Étape 1 : Définir le chemin du répertoire de sortie**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Étape 2 : Initialiser Viewer et rendre en PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Problèmes courants et solutions

| Problème | Cause | Solution |
|-------|-------|----------|
| **OutOfMemoryError** sur de gros fichiers WMZ | Viewer charge tout le document en mémoire | Rendre une page à la fois avec `PageStreamViewOptions` ou augmenter le tas JVM (`-Xmx`). |
| **Polices manquantes** dans le PDF | Police non incorporée dans le WMZ source | Installez les polices requises sur la machine hôte ou utilisez `FontSettings` pour fournir des polices personnalisées. |
| **Sortie PNG vide** | Chemin de sortie incorrect ou permissions d’écriture insuffisantes | Vérifiez que `outputDirectory` existe et que l’application a les droits d’écriture. |
| **Ressources HTML non chargées** | Utilisation de `forExternalResources` sans copier les fichiers | Restez avec `forEmbeddedResources` pour un fichier HTML autonome. |

## Questions fréquentes

**Q : Puis‑je convertir WMF en PNG avec le même code ?**  
R : Oui. L’exemple PNG fonctionne pour les fichiers WMZ et WMF ; il suffit de remplacer `TestFiles.SAMPLE_WMZ` par votre source WMF.

**Q : Est‑il possible de convertir uniquement un sous‑ensemble de pages ?**  
R : Absolument. Utilisez `PdfViewOptions` (ou les options correspondantes pour les autres formats) et appelez `setPageNumbers(List<Integer>)` avant le rendu.

**Q : Ai‑je besoin d’une licence séparée pour chaque format de sortie ?**  
R : Non. Une seule licence GroupDocs Viewer couvre tous les formats pris en charge, y compris HTML, JPG, PNG et PDF.

**Q : Comment “java convert vector graphics” impacte‑t‑il les performances ?**  
R : La conversion vecteur‑vers‑raster est intensive en CPU. Pour de gros lots, envisagez le multithreading et la réutilisation d’une seule instance `Viewer` pour plusieurs fichiers.

**Q : Le PDF conservera‑t‑il la qualité vectorielle ou sera‑t‑il rasterisé ?**  
R : Lors de la conversion WMZ/WMF en PDF, GroupDocs Viewer préserve les instructions vectorielles lorsque c’est possible, ce qui donne un PDF évolutif.

## Conclusion

Vous avez maintenant un guide complet, prêt pour la production, pour **convert WMZ to PDF** et d’autres formats courants en utilisant **GroupDocs Viewer for Java**. Que vous construisiez un service web qui fournit des graphiques à la volée ou un outil d’archivage qui stocke les documents en PDF, les étapes ci‑dessus vous aideront à y parvenir rapidement.

---

**Dernière mise à jour :** 2026-02-18  
**Testé avec :** GroupDocs.Viewer 25.2 for Java  
**Auteur :** GroupDocs