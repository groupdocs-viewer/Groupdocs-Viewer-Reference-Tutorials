---
date: '2026-08-30'
description: Apprenez à convertir DWG en PNG, à définir la couleur d'arrière‑plan
  en Java, et à personnaliser la taille de l'image avec GroupDocs.Viewer for Java.
keywords:
- convert dwg to png
- set background color java
- change cad background color
- java convert cad png
lastmod: '2026-08-30'
og_description: Convertir DWG en PNG avec GroupDocs.Viewer for Java tout en définissant
  une largeur d'image personnalisée et une couleur d'arrière‑plan. Ce guide fournit
  une configuration étape par étape, des extraits de code et des conseils de dépannage.
og_image_alt: 'Guide: converting DWG to PNG with custom size and background color
  using GroupDocs.Viewer for Java'
og_title: Convertir DWG en PNG avec taille personnalisée, couleur d'arrière‑plan en
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-30'
  description: Learn how to convert DWG to PNG, set background color Java, and customize
    image size with GroupDocs.Viewer for Java.
  headline: How to convert DWG to PNG with custom size & background color using GroupDocs.Viewer
    for Java
  type: TechArticle
- questions:
  - answer: Yes, GroupDocs.Viewer supports DXF, DWF, and several additional CAD formats.
    question: Can I render other CAD formats besides DWG?
  - answer: Instantiate a new `Color` with `new Color(123, 45, 67)` and pass it to
      `setBackgroundColor`.
    question: How do I use a custom RGB color instead of a predefined constant?
  - answer: You can specify layout or layer options via `CadOptions` before calling
      `viewer.view`.
    question: Is it possible to render only a specific layout or layer?
  - answer: Set the background color to `new Color(0,0,0,0)` for full transparency
      if the output format supports it.
    question: Does the library support transparent backgrounds?
  - answer: The tutorial uses version 25.2, but newer releases retain the same API
      surface.
    question: What version of GroupDocs.Viewer is required?
  type: FAQPage
tags:
- convert dwg
- GroupDocs.Viewer
- Java CAD rendering
- custom PNG output
title: Comment convertir DWG en PNG avec une taille personnalisée et une couleur d'arrière‑plan
  en utilisant GroupDocs.Viewer for Java
type: docs
url: /fr/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Comment convertir DWG en PNG avec taille personnalisée et couleur d'arrière‑plan en utilisant GroupDocs.Viewer pour Java

Dans ce tutoriel, vous apprendrez **comment convertir DWG en PNG** tout en contrôlant les dimensions de sortie et la couleur d'arrière‑plan, en utilisant GroupDocs.Viewer pour Java. Que vous ayez besoin d'intégrer des dessins CAO dans un rapport, de générer des vignettes pour un portail web ou d'automatiser le rendu par lots, les étapes ci‑dessous vous offrent un contrôle total sur l'apparence visuelle de chaque fichier PNG.

## Réponses rapides
- **Que signifie « convertir DWG en PNG » ?** C’est le processus de transformation d’un fichier DWG CAD en image PNG via du code, en conservant les détails vectoriels sous forme de pixels raster.  
- **Puis‑je définir une largeur personnalisée ?** Oui – appelez `CadOptions.forRenderingByWidth(int width)` pour définir la largeur exacte en pixels dont vous avez besoin.  
- **Comment changer la couleur d'arrière‑plan ?** Utilisez `cadOptions.setBackgroundColor(Color.YOUR_COLOR)` avant le rendu.  
- **Quelle bibliothèque est requise ?** GroupDocs.Viewer pour Java (version 25.2 ou supérieure).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou complète supprime les limites d’évaluation et permet un rendu illimité.

![Rendu des dessins CAO en PNG avec taille personnalisée et couleur d'arrière‑plan avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Qu’est‑ce que GroupDocs.Viewer pour Java ?
GroupDocs.Viewer pour Java est une API côté serveur qui rend plus de 150 formats de fichiers — y compris les fichiers CAD — en images, PDF ou HTML. Elle fonctionne sans nécessiter de logiciel tiers tel qu’AutoCAD, ce qui la rend idéale pour les pipelines automatisés.

## Comment convertir DWG en PNG avec taille personnalisée et couleur d'arrière‑plan ?
Chargez le fichier DWG avec une instance `Viewer`, configurez `CadOptions` pour la largeur et l'arrière‑plan souhaités, puis appelez `viewer.view` avec `PngViewOptions`. Ce flux en trois étapes gère la lecture/écriture de fichiers, le rendu et la nomination des sorties en une seule opération à faible consommation de mémoire.

Viewer est la classe principale qui charge un document et effectue le rendu.  
CadOptions configure les paramètres spécifiques à la CAO tels que la largeur de l’image et la couleur d’arrière‑plan.  
PngViewOptions définit le format de sortie PNG et le modèle de nommage pour les pages rendues.

Vous pouvez désormais rendre n’importe quel dessin DWG en PNG avec exactement la largeur que vous spécifiez, et choisir n’importe quelle couleur unie (ou transparente) d’arrière‑plan pour correspondre à votre marque ou thème d’interface.

## Pourquoi définir une couleur d'arrière‑plan personnalisée ?
Définir une couleur d’arrière‑plan garantit que le PNG rendu s’intègre parfaitement aux éléments d’interface environnants, évite les marges blanches indésirables et peut mettre en évidence des détails du dessin qui seraient autrement perdus sur une toile blanche par défaut. GroupDocs.Viewer prend en charge n’importe quel `java.awt.Color`, y compris les valeurs RGB personnalisées, vous offrant un contrôle pixel‑parfait.

`java.awt.Color` représente une valeur de couleur utilisée pour le rendu des arrière‑plans.

## Prérequis
- **Java Development Kit (JDK) 8+** – l’API cible Java 8 et versions ultérieures.  
- **Maven** – pour la gestion des dépendances.  
- **IDE** – IntelliJ IDEA, Eclipse ou tout éditeur de votre choix.  
- **Connaissances de base en gestion de fichiers Java** – pour lire les fichiers DWG source et écrire les sorties PNG.

## Configuration de GroupDocs.Viewer pour Java
Ajoutez le dépôt GroupDocs et la dépendance Viewer à votre `pom.xml` Maven :

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
Obtenez une clé de licence temporaire ou complète depuis le portail GroupDocs et placez le fichier `license.lic` dans le dossier des ressources de votre projet. Cela supprime la limite d’évaluation de 20 pages et débloque le rendu en pleine résolution.

### Initialisation et configuration de base
Créez une instance `Viewer` qui pointe vers le dossier contenant vos fichiers DWG :

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Fonctionnalité 1 : rendu des dessins CAD avec taille d’image personnalisée et couleur d’arrière‑plan

### Comment changer la couleur d’arrière‑plan CAD
Pour changer la couleur d’arrière‑plan CAD, configurez l’objet CadOptions avant le rendu. Définissez la largeur souhaitée avec `forRenderingByWidth` et appliquez le nouvel arrière‑plan à l’aide de `setBackgroundColor`. Le viewer génère alors des images PNG qui reflètent la couleur spécifiée, assurant une cohérence visuelle sur tous les fichiers de sortie.

#### Implémentation étape par étape

##### Importer les packages requis
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurer le répertoire de sortie et le format du chemin de fichier
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

##### Initialiser le viewer avec des options de rendu personnalisées
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    // Specify the width for rendering
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);

    viewer.view(options);
}
```

**Explication des paramètres**  
- `PngViewOptions` – définit le format de sortie PNG et le modèle de nommage.  
- `forRenderingByWidth(int width)` – force le moteur de rendu à produire une image dont la largeur correspond à la valeur en pixels fournie ; la hauteur est mise à l’échelle proportionnellement.  
- `setBackgroundColor(Color color)` – remplace la toile blanche par défaut par la couleur que vous choisissez, améliorant la cohérence visuelle des actifs générés.

#### Conseils de dépannage
- Assurez‑vous que le dossier de sortie existe ; utilisez `Files.createDirectories(outputDir)` s’il n’existe pas.  
- Vérifiez que le chemin du fichier d’entrée est correct et que l’application dispose des permissions de lecture.  

## Fonctionnalité 2 : définition de la couleur d’arrière‑plan dans les options de rendu

### Comment définir la couleur d’arrière‑plan PNG
Définir la couleur d’arrière‑plan PNG consiste à créer une instance `Color` et à l’assigner à `CadOptions` avant le rendu. Cela garantit que chaque PNG généré utilise l’arrière‑plan spécifié, correspondant à vos directives de marque ou thème d’interface. Vous pouvez utiliser des constantes prédéfinies ou définir des valeurs RGB personnalisées pour un contrôle précis.

`java.awt.Color` représente une valeur de couleur utilisée pour le rendu des arrière‑plans.

#### Implémentation étape par étape

##### Importer les packages requis
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurer les options de rendu avec la couleur d’arrière‑plan
```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SetImageBackgroundColor");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS")) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    CadOptions cadOptions = CadOptions.forRenderingByWidth(800);
    cadOptions.setBackgroundColor(Color.GREEN);
    
    options.setCadOptions(cadOptions);
    
    viewer.view(options);
}
```

**Options de configuration clés**  
- Ajustez `forRenderingByWidth(int width)` pour différentes dimensions, comme 800 px pour les vignettes web ou 1920 px pour les impressions haute résolution.  
- Utilisez n’importe quelle constante `Color` prédéfinie (par ex., `Color.LIGHT_GRAY`) ou créez une instance personnalisée avec `new Color(r, g, b)` pour un branding précis.

## Applications pratiques

### 1. Documentation technique
Le rendu personnalisé garantit que chaque dessin respecte le guide de style de l’entreprise, éliminant ainsi l’édition manuelle d’images après l’exportation.

### 2. Visualisation architecturale
Présentez les plans avec un arrière‑plan qui correspond aux présentations ou aux portails destinés aux clients, améliorant la cohésion visuelle.

### 3. Prototypage en fabrication
Générez des PNG pour les flux de travail de prototypage rapide où les outils en aval attendent une taille d’image et un arrière‑plan spécifiques.

### Possibilités d’intégration
Associez ce pipeline de rendu à un système de gestion de documents (par ex., SharePoint) pour générer automatiquement des images d’aperçu chaque fois qu’un fichier DWG est téléchargé.

## Considérations de performance

### Optimisation des performances
- **Traitement par lots :** Parcourez un répertoire de fichiers DWG et rendez chaque fichier séquentiellement afin d’amortir les coûts de mise en route de la JVM.  
- **Gestion des ressources :** Pour les dessins volumineux (500 + pages), augmentez le tas JVM (`-Xmx2g`) ou traitez les fichiers par lots plus petits afin d’éviter les erreurs de mémoire insuffisante.

### Directives d’utilisation des ressources
Surveillez l’utilisation du CPU et de la mémoire avec des outils comme VisualVM ; libérez rapidement les instances `Viewer` en utilisant try‑with‑resources.

### Bonnes pratiques de gestion de la mémoire Java
- Utilisez try‑with‑resources (comme montré) pour fermer automatiquement `Viewer`.  
- Évitez de conserver de grands objets `Path` au‑delà de leur utilisation immédiate.  

## Problèmes courants et solutions

| Problème | Solution |
|----------|----------|
| Dossier de sortie introuvable | Créez le répertoire au préalable ou ajoutez `Files.createDirectories(outputDirectory);` |
| Image blanche | Assurez‑vous que `cadOptions.setBackgroundColor` est appelé après `forRenderingByWidth`. |
| Erreurs de mémoire insuffisante | Augmentez l’option JVM `-Xmx` ou traitez les fichiers par lots plus petits. |

## Questions fréquemment posées

**Q : Puis‑je rendre d’autres formats CAD en plus de DWG ?**  
A : Oui, GroupDocs.Viewer prend en charge DXF, DWF et plusieurs formats CAD supplémentaires.

**Q : Comment utiliser une couleur RGB personnalisée au lieu d’une constante prédéfinie ?**  
A : Instanciez un nouveau `Color` avec `new Color(123, 45, 67)` et passez‑le à `setBackgroundColor`.

**Q : Est‑il possible de rendre uniquement une mise en page ou un calque spécifique ?**  
A : Vous pouvez spécifier les options de mise en page ou de calque via `CadOptions` avant d’appeler `viewer.view`.

**Q : La bibliothèque prend‑elle en charge les arrière‑plans transparents ?**  
A : Définissez la couleur d’arrière‑plan à `new Color(0,0,0,0)` pour une transparence totale si le format de sortie le prend en charge.

**Q : Quelle version de GroupDocs.Viewer est requise ?**  
A : Le tutoriel utilise la version 25.2, mais les versions plus récentes conservent la même surface d’API.

---

**Dernière mise à jour :** 2026-08-30  
**Testé avec :** GroupDocs.Viewer 25.2 pour Java  
**Auteur :** GroupDocs

## Tutoriels associés

- [groupdocs viewer dwg – Comment rendre des dessins CAD spécifiques en Java avec GroupDocs.Viewer](/viewer/java/rendering-basics/render-cad-groupdocs-viewer-java/)
- [Rendu des calques CAD Java avec GroupDocs.Viewer – Guide complet](/viewer/java/advanced-rendering/render-cad-layers-java-groupdocs-viewer/)
- [Comment convertir pdf en html et optimiser la qualité d’image en Java avec GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)