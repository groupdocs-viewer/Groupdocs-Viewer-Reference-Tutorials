---
date: '2026-03-16'
description: Apprenez à convertir DWG en PNG avec une taille personnalisée et une
  couleur d'arrière-plan en utilisant GroupDocs.Viewer pour Java.
keywords:
- render CAD drawings PNG
- GroupDocs.Viewer for Java setup
- custom image size and background color
title: Comment convertir un DWG en PNG avec une taille personnalisée et une couleur
  d’arrière‑plan en utilisant GroupDocs.Viewer pour Java
type: docs
url: /fr/java/advanced-rendering/render-cad-drawings-custom-png-groupdocs-java/
weight: 1
---

# Comment convertir DWG en PNG avec taille personnalisée et couleur d'arrière‑plan en utilisant GroupDocs.Viewer pour Java

Si vous cherchez à **convertir DWG en PNG** tout en conservant un contrôle total sur les dimensions de l'image et le style de l'arrière‑plan, vous êtes au bon endroit. Dans ce tutoriel, nous vous guiderons à travers le rendu de fichiers CAD en PNG, la personnalisation de la largeur et le changement de la couleur d'arrière‑plan afin que le résultat corresponde à vos exigences de rapport, de présentation ou de prévisualisation Web.

## Réponses rapides
- **Que signifie « convertir DWG en PNG » ?** C’est le processus de transformation d’un fichier CAD DWG en image PNG à l’aide de code.  
- **Puis‑je définir une largeur personnalisée ?** Oui – utilisez `CadOptions.forRenderingByWidth(int width)`.  
- **Comment changer la couleur d'arrière‑plan ?** Appelez `cadOptions.setBackgroundColor(Color.YOUR_COLOR)`.  
- **Quelle bibliothèque est requise ?** GroupDocs.Viewer pour Java (version 25.2 ou ultérieure).  
- **Ai‑je besoin d’une licence ?** Une licence temporaire ou achetée supprime les limites d’évaluation.

![Rendu des dessins CAD en PNG avec taille personnalisée et couleur d'arrière‑plan avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/render-cad-drawings-as-png-with-custom-size-background-color-java.png)

## Comment convertir DWG en PNG – Vue d'ensemble
Dans cette section, nous développons l’objectif principal : **comment convertir DWG en PNG** tout en contrôlant la taille et l’arrière‑plan. Vous verrez la configuration complète, le code exact dont vous avez besoin et des conseils pratiques pour éviter les pièges courants.

## Ce que vous apprendrez
- Configurer GroupDocs.Viewer pour Java dans un projet Maven  
- **Convertir DWG en PNG** avec des dimensions personnalisées  
- **Modifier la couleur d'arrière‑plan CAD** pendant le rendu pour un rendu soigné  
- Scénarios réels où le rendu personnalisé apporte de la valeur  

## Prérequis

### Bibliothèques et dépendances requises
- Java Development Kit (JDK) 8+  
- Maven pour la gestion des dépendances  

### Exigences de configuration de l'environnement
- IDE tel qu'IntelliJ IDEA ou Eclipse  
- Connaissances de base en Java  

### Prérequis de connaissances
- Familiarité avec la manipulation de fichiers en Java  

## Configuration de GroupDocs.Viewer pour Java
Ajoutez le dépôt GroupDocs et la dépendance à votre `pom.xml` Maven :

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
Obtenez une licence temporaire ou complète pour supprimer les restrictions d’évaluation.

### Initialisation et configuration de base
Créez une instance `Viewer` qui pointe vers votre fichier CAD :

```java
import com.groupdocs.viewer.Viewer;
import java.nio.file.Path;

Path documentPath = Path.of("YOUR_DOCUMENT_DIRECTORY/SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS");
try (Viewer viewer = new Viewer(documentPath.toString())) {
    // Rendering operations go here
}
```

## Fonctionnalité 1 : Rendu des dessins CAD avec taille d'image personnalisée et couleur d'arrière‑plan

### Comment changer la couleur d'arrière‑plan CAD
Cette fonctionnalité vous permet de **convertir DWG en PNG** tout en spécifiant une largeur personnalisée et en appliquant une nouvelle teinte d’arrière‑plan.

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

##### Initialiser le Viewer avec des options de rendu personnalisées
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
- `PngViewOptions` – définit le format de sortie et la dénomination.  
- `forRenderingByWidth(int width)` – définit la largeur d’image personnalisée.  
- `setBackgroundColor(Color color)` – **définit la couleur d'arrière‑plan PNG** pour améliorer la cohérence visuelle.

#### Conseils de dépannage
- Vérifiez que le dossier de sortie existe ; créez‑le si nécessaire.  
- Revérifiez le chemin du fichier d’entrée et les permissions.  

## Fonctionnalité 2 : Définir la couleur d'arrière‑plan dans les options de rendu

### Comment définir la couleur d'arrière‑plan PNG
Ici, nous nous concentrons sur l’option **set background color PNG** afin que chaque image rendue corresponde à votre palette de marque.

#### Implémentation étape par étape

##### Importer les packages requis
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.CadOptions;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;
import java.awt.Color;
```

##### Configurer les options de rendu avec la couleur d'arrière‑plan
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
- Ajustez `forRenderingByWidth(int width)` pour différentes dimensions.  
- Utilisez n’importe quelle constante `Color` ou un `new Color(r,g,b)` personnalisé pour des arrière‑plans sur‑mesure.  

## Applications pratiques

### 1. Documentation d'ingénierie
Le rendu personnalisé garantit que les dessins d’ingénierie respectent les guides de style d’entreprise.

### 2. Visualisation architecturale
Présentez les plans avec un arrière‑plan épuré qui correspond aux présentations.

### 3. Prototypage de fabrication
Générez des PNG précis pour les flux de travail de prototypage rapide.

### Possibilités d'intégration
Combinez ce pipeline de rendu avec des systèmes de gestion documentaire pour automatiser la génération d’actifs visuels.

## Considérations de performance

### Optimisation des performances
- **Traitement par lots :** Rendre plusieurs fichiers CAD dans une boucle.  
- **Gestion des ressources :** Ajustez la taille du tas JVM pour les dessins volumineux.

### Directives d'utilisation des ressources
Surveillez le CPU et la mémoire ; libérez les instances `Viewer` rapidement.

### Bonnes pratiques pour la gestion de la mémoire Java
- Utilisez try‑with‑resources (comme montré) pour fermer automatiquement le `Viewer`.  
- Évitez de conserver de gros objets `Path` plus longtemps que nécessaire.

## Problèmes courants et solutions
| Problème | Solution |
|----------|----------|
| **Dossier de sortie introuvable** | Créez le répertoire au préalable ou ajoutez `Files.createDirectories(outputDirectory);` |
| **Image blanche** | Assurez‑vous que `cadOptions.setBackgroundColor` est défini après `forRenderingByWidth`. |
| **Erreurs de mémoire insuffisante** | Augmentez l’option JVM `-Xmx` ou traitez les fichiers par lots plus petits. |

## Questions fréquentes

**Q : Puis‑je rendre d’autres formats CAD que le DWG ?**  
R : Oui, GroupDocs.Viewer prend en charge DXF, DWF et plusieurs autres types de fichiers CAD.

**Q : Comment utiliser une couleur RGB personnalisée au lieu d’une constante prédéfinie ?**  
R : Créez une nouvelle instance `Color`, par ex. `new Color(123, 45, 67)` et transmettez‑la à `setBackgroundColor`.

**Q : Est‑il possible de rendre uniquement une mise en page ou un calque spécifique ?**  
R : Vous pouvez spécifier les options de mise en page ou de calque via `CadOptions` avant d’appeler `viewer.view`.

**Q : La bibliothèque prend‑elle en charge les arrière‑plans transparents ?**  
R : Définissez la couleur d’arrière‑plan à `new Color(0,0,0,0)` pour une transparence totale si le format cible le supporte.

**Q : Quelle version de GroupDocs.Viewer est requise ?**  
R : Le tutoriel utilise la version 25.2, mais les versions plus récentes conservent la même API.

---

**Dernière mise à jour :** 2026-03-16  
**Testé avec :** GroupDocs.Viewer 25.2 pour Java  
**Auteur :** GroupDocs