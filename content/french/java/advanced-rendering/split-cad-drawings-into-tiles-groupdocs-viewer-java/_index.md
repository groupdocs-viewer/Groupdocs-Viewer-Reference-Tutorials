---
date: '2026-04-01'
description: Apprenez à diviser les dessins CAO en tuiles à l'aide de GroupDocs Viewer
  pour Java, améliorant les performances de rendu et simplifiant la gestion des gros
  fichiers.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Comment diviser les dessins CAO en tuiles avec GroupDocs Viewer
type: docs
url: /fr/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Comment diviser les dessins CAD en tuiles avec GroupDocs Viewer

Si vous vous demandez **comment diviser les fichiers CAD** en morceaux plus petits et plus faciles à gérer, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue les étapes exactes nécessaires pour diviser de grands dessins CAD en tuiles en utilisant **GroupDocs Viewer for Java**. À la fin, vous disposerez d’une solution prête à l’emploi qui améliore la vitesse de rendu, réduit la consommation de mémoire et facilite l’affichage des dessins dans des applications web ou mobiles.

![Split CAD Drawings with GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Réponses rapides
- **Quel est l'objectif du « splitting CAD » ?** Il divise un dessin massif en images plus petites (tuiles) qui se chargent plus rapidement et consomment moins de mémoire.  
- **Quel format est utilisé pour les tuiles ?** Les fichiers PNG sont générés par défaut, mais d’autres formats sont pris en charge via les options du Viewer.  
- **Ai-je besoin d’une licence ?** Un essai gratuit fonctionne pour le développement ; une licence payante est requise pour la production.  
- **Puis-je modifier la taille des tuiles ?** Oui – ajustez les calculs `tileWidth` et `tileHeight` selon vos besoins.  
- **Cette approche est‑elle thread‑safe ?** Le rendu de chaque tuile dans sa propre instance `Viewer` avec try‑with‑resources est sûr pour une exécution concurrente.

## Qu’est‑ce que le « splitting CAD » ?
Le splitting CAD consiste à diviser un seul dessin CAD, souvent très volumineux, en plusieurs sections rectangulaires (tuiles). Chaque tuile est rendue indépendamment, ce qui vous permet de charger uniquement les parties dont l'utilisateur a réellement besoin — idéal pour les cartes web, les portails de documents et les visionneuses mobiles.

## Pourquoi utiliser GroupDocs Viewer pour Java ?
GroupDocs Viewer offre un support prêt à l’emploi pour plus de 100 formats de fichiers, y compris DWG, DXF et DWF. Son API de tuiles vous permet de spécifier des coordonnées exactes, afin de rendre précisément la zone qui vous intéresse sans devoir traiter le fichier complet au préalable. Cela économise des cycles CPU, réduit la bande passante et offre une expérience utilisateur plus fluide.

## Prérequis
- **Bibliothèques** : GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK** : Tout JDK récent (Java 8+).  
- **IDE** : IntelliJ IDEA, Eclipse ou tout autre IDE compatible Java.  
- **Outil de construction** : Maven (d’autres outils de construction fonctionnent tant que la dépendance est ajoutée).  

## Configuration de GroupDocs.Viewer pour Java
Ajoutez le dépôt GroupDocs et la dépendance à votre `pom.xml` :

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
GroupDocs Viewer propose une licence d’essai gratuite pour l’évaluation :

- **Essai gratuit** : Visitez [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) pour télécharger la bibliothèque.  
- **Licence temporaire** : Faites la demande sur [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Licence complète** : Achetez une licence de production sur la [Purchase Page](https://purchase.groupdocs.com/buy).

### Initialisation de base
Créez une instance simple de `Viewer` pour vérifier que la bibliothèque se charge correctement :

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Guide étape par étape pour diviser les dessins CAD en tuiles

### Étape 1 : Définir le répertoire de sortie
Nous enregistrerons chaque tuile en tant que fichier PNG distinct. L’utilisation d’une méthode utilitaire garde la logique de chemin propre et réutilisable.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Étape 2 : Configurer les options d’affichage
Définissez le format de rendu sur PNG et indiquez au viewer de ne pas précharger chaque page (ce qui économise de la mémoire).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Étape 3 : Calculer les dimensions des tuiles
Tout d’abord, nous obtenons la largeur et la hauteur originales du dessin, puis nous le divisons en quatre quadrants égaux.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Étape 4 : Rendre et enregistrer les tuiles
Ajoutez les tuiles calculées aux options de rendu et laissez le `Viewer` générer les fichiers PNG.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Conseils de dépannage
- **Chemin de construction** – Assurez‑vous que les fichiers JAR de GroupDocs sont sur le classpath.  
- **Permissions** – Le dossier de sortie doit être accessible en écriture par le processus Java.  
- **Exceptions** – Si vous voyez `ViewerException`, vérifiez que le fichier DWG n’est pas corrompu et que la licence correcte est appliquée.

## Cas d’utilisation courants pour le découpage des tuiles CAD
1. **Cartographie web** – Charger uniquement la partie visible d’un plan d’étage lorsque l'utilisateur se déplace ou zoome.  
2. **Gestion de documents** – Stocker chaque tuile séparément pour une génération d’aperçu plus rapide.  
3. **Visualisation mobile** – Réduire la bande passante en téléchargeant uniquement les tuiles nécessaires à l’écran actuel.

## Considérations de performance
- **Taille des tuiles** – Des tuiles plus grandes signifient moins de fichiers mais un rendu plus lent ; trouvez un compromis selon les besoins de votre interface.  
- **Surveillance de la mémoire** – Utilisez les outils de profilage Java (par ex., VisualVM) pour observer l’utilisation du tas lors du traitement de très grands dessins.  
- **Nettoyage des ressources** – Le modèle try‑with‑resources présenté ci‑dessus libère automatiquement les ressources natives.

## Questions fréquemment posées

**Q : Puis‑je diviser d’autres types de fichiers (PDF, images) en tuiles en utilisant la même approche ?**  
R : Oui. GroupDocs Viewer prend en charge de nombreux formats ; il suffit d’utiliser la classe d’options correspondante (par ex., `PdfViewOptions`).

**Q : Comment modifier la qualité de l’image de sortie ?**  
R : Ajustez `viewOptions.setResolution(int dpi)` ou définissez les paramètres de compression sur l’objet `PngOptions`.

**Q : Mon application manque de mémoire sur des fichiers DWG très volumineux—que puis‑je faire ?**  
R : Réduisez les dimensions des tuiles, augmentez le tas JVM (`-Xmx`), ou rendez les tuiles séquentiellement dans des instances `Viewer` séparées.

**Q : Est‑il possible de rendre les tuiles de façon asynchrone ?**  
R : Absolument. Enveloppez chaque appel de rendu de tuile dans un `CompletableFuture` ou utilisez un service d’exécution pour paralléliser la charge de travail.

**Q : Ai‑je besoin d’une licence distincte pour chaque tuile ?**  
R : Non. Une seule licence valide de GroupDocs Viewer couvre toutes les opérations de rendu au sein de votre application.

## Ressources
- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [Référence API](https://reference.groupdocs.com/viewer/java/)
- [Télécharger GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Acheter une licence](https://purchase.groupdocs.com/buy)
- [Essai gratuit](https://releases.groupdocs.com/viewer/java/)
- [Licence temporaire](https://purchase.groupdocs.com/temporary-license/)
- [Forum d’assistance](https://forum.groupdocs.com/c/viewer/9)

---

**Dernière mise à jour :** 2026-04-01  
**Testé avec :** GroupDocs.Viewer 25.2 for Java  
**Auteur :** GroupDocs  

---