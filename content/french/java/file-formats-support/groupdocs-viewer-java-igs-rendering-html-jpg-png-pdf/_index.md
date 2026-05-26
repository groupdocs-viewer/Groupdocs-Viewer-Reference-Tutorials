---
date: '2026-02-23'
description: Apprenez à convertir les fichiers IGS en PDF, HTML, JPG et PNG avec GroupDocs.Viewer
  pour Java. Suivez ce guide étape par étape avec des exemples de code prêts à l'exécution.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Convertir IGS en PDF, HTML, JPG et PNG avec GroupDocs.Viewer Java
type: docs
url: /fr/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

 final content.# Convertir IGS en PDF, HTML, JPG et PNG avec GroupDocs.Viewer Java

Si vous devez **convertir IGS en PDF** (ou en HTML, JPG, PNG) directement depuis une application Java, vous êtes au bon endroit. Dans ce tutoriel, nous passerons en revue tout ce dont vous avez besoin — de la configuration de la bibliothèque au rendu du modèle 3 D dans le format qui convient à votre projet. Vous verrez pourquoi GroupDocs.Viewer est un choix solide pour des conversions rapides et fiables et vous obtiendrez du code pratique que vous pourrez intégrer à votre propre solution.

![Convertir des fichiers IGS en HTML, JPG, PNG et PDF avec GroupDocs.Viewer pour Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Réponses rapides
- **Puis-je convertir IGS en PDF avec Java ?** Oui, en utilisant `PdfViewOptions` de GroupDocs.Viewer.  
- **Quels formats de sortie sont pris en charge ?** HTML, JPG, PNG et PDF.  
- **Ai-je besoin d’une licence pour la production ?** Une licence commerciale est requise ; un essai gratuit est disponible pour les tests.  
- **Quelle version de Java est requise ?** JDK 8 ou supérieur.  
- **Maven est-il le seul moyen d’ajouter la bibliothèque ?** Non, vous pouvez également utiliser Gradle ou inclure manuellement le JAR.  

## Qu’est‑ce que « convertir IGS en PDF » ?
Convertir IGS (un format de fichier neutre pour les données CAD 3 D) en PDF consiste à transformer un modèle 3 D complexe en un document statique, largement visualisable. Cela est utile pour partager des conceptions avec des parties prenantes qui ne disposent pas d’outils CAD.

## Pourquoi utiliser GroupDocs.Viewer pour les conversions IGS ?
- **Zero‑code CAD rendering** – la bibliothèque gère le travail lourd d’analyse du format IGS.  
- **Multiple output options** – un appel d’API peut produire HTML, JPG, PNG ou PDF.  
- **Cross‑platform** – fonctionne sur tout OS supportant Java.  
- **Performance‑focused** – rendu rapide même pour les assemblages volumineux.  

## Prérequis
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** installé et configuré dans votre IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.)  
- Connaissances de base en Maven (optionnel mais recommandé)  

## Configuration de GroupDocs.Viewer pour Java

### Dépendance Maven
Ajoutez le dépôt GroupDocs et la dépendance Viewer à votre `pom.xml` :

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
GroupDocs.Viewer offre :
- **Free trial** – utilisation limitée, idéal pour des tests rapides.  
- **Temporary license** – ensemble complet de fonctionnalités pour une courte période d’évaluation.  
- **Commercial license** – utilisation en production sans restriction.  

### Initialisation de base du Viewer
L’extrait ci‑dessous montre comment créer une instance `Viewer` qui pointe vers votre fichier IGS :

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Rendu d’IGS en HTML

### Comment convertir IGS en HTML ?
La sortie HTML vous fournit une vue interactive, adaptée aux navigateurs, du modèle 3 D.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

**Point clé :** `HtmlViewOptions.forEmbeddedResources()` intègre toutes les ressources nécessaires (CSS, images) directement dans le fichier HTML, le rendant portable.

## Rendu d’IGS en JPG

### Comment convertir IGS en JPG ?
Les images JPG sont parfaites pour les vignettes ou les aperçus rapides.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Vous pouvez ajuster `JpgViewOptions` pour contrôler la résolution et la qualité de compression.

## Rendu d’IGS en PNG

### Comment convertir IGS en PNG ?
Le PNG prend en charge la transparence, ce qui est pratique pour superposer le modèle sur différents arrière-plans.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

Expérimentez avec `PngViewOptions` pour obtenir le meilleur équilibre entre la taille du fichier et la fidélité visuelle.

## Rendu d’IGS en PDF

### Comment convertir IGS en PDF ?
Le PDF est le format de référence pour partager une documentation de conception détaillée. Cette section répond directement au mot‑clé principal **convertir IGS en PDF**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

`PdfViewOptions` vous permet de contrôler la mise en page, la qualité des images et l’inclusion ou non des polices.

## Applications pratiques
- **Web portals** – intégrez les modèles rendus en HTML directement dans les configurateurs de produits.  
- **Marketing assets** – générez des images JPG/PNG haute résolution pour les brochures.  
- **Technical documentation** – incluez les rendus PDF des modèles CAD dans les manuels d’utilisation.  
- **Quality assurance** – automatisez la génération de vignettes pour de grands lots de fichiers IGS.  

## Problèmes courants & solutions

| Problème | Solution |
|----------|----------|
| **Dossier de sortie introuvable** | Vérifiez le chemin passé à `Path outputDirectory` et assurez‑vous que le processus Java dispose des permissions d’écriture. |
| **Pages blanches dans le PDF** | Assurez‑vous que le fichier IGS n’est pas corrompu ; essayez de l’ouvrir d’abord dans un visualiseur CAD. |
| **Rendu lent pour les grands assemblages** | Augmentez le tas JVM (`-Xmx2g` ou plus) et envisagez de rendre page par page en utilisant `viewer.getPageCount()` si nécessaire. |
| **Polices manquantes dans le PDF** | Utilisez `PdfViewOptions` pour intégrer les polices requises ou installez les polices manquantes sur le serveur. |

## Questions fréquentes

**Q : Puis‑je convertir plusieurs fichiers IGS en une seule exécution ?**  
R : Oui. Parcourez une liste de chemins de fichiers et invoquez la méthode `view` appropriée pour chacun.

**Q : Est‑il possible de personnaliser la taille de page du PDF ?**  
R : Absolument. `PdfViewOptions` propose `setPageSize(PageSize.A4)` et des méthodes similaires.

**Q : Ai‑je besoin d’une licence séparée pour chaque format de sortie ?**  
R : Non. Une seule licence GroupDocs.Viewer couvre tous les formats pris en charge.

**Q : Quelle taille maximale peut atteindre un fichier IGS avant que les performances ne se dégradent ?**  
R : La bibliothèque gère des fichiers de plusieurs centaines de mégaoctets, mais il peut être nécessaire d’allouer plus de mémoire JVM pour des modèles très volumineux.

**Q : Puis‑je rendre uniquement une vue ou orientation spécifique ?**  
R : GroupDocs.Viewer rend la vue par défaut. Pour des orientations personnalisées, pré‑traitez le fichier IGS avec un outil CAD avant la conversion.

---

**Dernière mise à jour :** 2026-02-23  
**Testé avec :** GroupDocs.Viewer 25.2 for Java  
**Auteur :** GroupDocs