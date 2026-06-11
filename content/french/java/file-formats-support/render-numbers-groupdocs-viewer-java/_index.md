---
date: '2026-03-05'
description: Apprenez à convertir des nombres en PDF et d’autres formats tels que
  HTML, JPG, PNG à l’aide de GroupDocs.Viewer pour Java. Ce guide couvre l’installation,
  les techniques de rendu et les applications pratiques.
keywords:
- GroupDocs.Viewer for Java
- render Apple Numbers documents
- convert Numbers to HTML, JPG, PNG, PDF
title: Convertir les fichiers Numbers en PDF avec GroupDocs.Viewer pour Java
type: docs
url: /fr/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Convertir Numbers en PDF (et autres formats) avec GroupDocs.Viewer pour Java

Afficher les documents Apple Numbers sur le web ou dans des applications de bureau peut être délicat, surtout lorsque vous devez **convertir numbers en pdf** ou les intégrer en tant qu'images. Dans ce tutoriel, nous expliquerons comment utiliser **GroupDocs.Viewer for Java** pour rendre les fichiers Numbers en HTML, JPG, PNG, **et PDF** — vous offrant des options flexibles pour partager, prévisualiser ou archiver vos feuilles de calcul.

![Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Ce que vous apprendrez
- Comment configurer GroupDocs.Viewer dans un projet Java basé sur Maven  
- Code étape par étape pour **convertir numbers en pdf**, **convertir numbers en html**, et **convertir numbers en jpg**  
- Scénarios réels où la conversion de documents ajoute de la valeur aux portails web, aux flux de travail email et aux intégrations DMS  

## Réponses rapides
- **Puis-je convertir Numbers en PDF avec Java ?** Oui, en utilisant `PdfViewOptions` dans GroupDocs.Viewer.  
- **Quel format est le meilleur pour la prévisualisation web ?** HTML offre l'expérience la plus interactive.  
- **Ai‑je besoin d'une licence pour une utilisation en production ?** Une licence commerciale est requise pour les déploiements non‑essai.  
- **La conversion d'images est‑elle prise en charge ?** Absolument — utilisez `JpgViewOptions` ou `PngViewOptions` pour obtenir des images de haute qualité.  
- **Quelle version de Java est requise ?** Java 8+ et Maven pour la gestion des dépendances.

## Prérequis
- Java Development Kit (JDK) 8 ou supérieur installé.  
- Maven pour la gestion des dépendances.  
- Familiarité de base avec les I/O de fichiers Java et les chemins.  

## Configuration de GroupDocs.Viewer pour Java

### Installation avec Maven
Ajoutez le dépôt et la dépendance à votre `pom.xml`. Ce bloc doit rester exactement tel qu'affiché :

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
- **Essai gratuit :** Évaluez toutes les fonctionnalités sans frais.  
- **Licence temporaire :** Demandez une clé à durée limitée pour des tests prolongés.  
- **Achat :** Obtenez une licence complète pour les projets commerciaux.

## Rendu du document Numbers en HTML  
*Cas d'utilisation : intégrer une feuille de calcul directement dans une page web.*

### Étape 1 : Initialiser le Viewer et configurer les options HTML
Voici le code exact que vous exécuterez. Les commentaires expliquent chaque ligne, mais **ne modifiez pas le bloc de code**.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Pourquoi c'est important :** `HtmlViewOptions.forEmbeddedResources()` regroupe le CSS et les images dans le HTML, ce qui le rend parfait pour des aperçus web rapides.

## Rendu du document Numbers en JPG  
*Idéal pour partager un instantané d'une feuille de calcul sur les réseaux sociaux ou par email.*

### Étape 1 : Configurer le Viewer et les options JPG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Astuce :** Ajustez la qualité de l'image via `options.setQuality(int)` si vous avez besoin de fichiers plus petits.

## Rendu du document Numbers en PNG  
*Idéal lorsque vous avez besoin d'une image sans perte et haute résolution pour les rapports.*

### Étape 1 : Initialiser et configurer les options PNG
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Conseil pro :** Utilisez `options.setResolution(int)` pour contrôler le DPI des images prêtes à l'impression.

## Rendu du document Numbers en PDF  
*L'objectif principal pour de nombreux développeurs : **convertir numbers en pdf** pour l'archivage ou la distribution.*

### Étape 1 : Configurer le Viewer pour la conversion PDF
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Configuration clé :** `PdfViewOptions` vous permet d'incorporer des polices et de contrôler la taille de la page, garantissant que la sortie correspond aux exigences de votre identité visuelle.

## Applications pratiques
- **Intégration web :** Rendre en HTML pour un visualiseur de feuille de calcul interactif sur votre site.  
- **Partage de contenu :** Convertir en JPG/PNG pour des intégrations rapides d'images dans les newsletters ou les chats.  
- **DMS d'entreprise :** Utiliser **convertir numbers en pdf** pour stocker une version non modifiable et recherchable de la feuille de calcul.  

## Considérations de performance
- **Gestion des ressources :** Fermez toujours le `Viewer` dans un bloc try‑with‑resources (comme indiqué) pour libérer rapidement les ressources natives.  
- **Fichiers volumineux :** Pour les fichiers Numbers massifs, envisagez de traiter page par page et de diffuser les résultats afin d'éviter une consommation élevée de mémoire.  
- **Sécurité des threads :** Créez une instance distincte de `Viewer` par thread ; la classe n'est pas thread‑safe.

## Conclusion
Vous disposez maintenant d'une boîte à outils complète pour **convertir numbers en pdf**, ainsi que vers HTML, JPG et PNG, en utilisant GroupDocs.Viewer pour Java. Ces capacités vous permettent de créer des pipelines de documents flexibles — que vous alimentiez un portail web, génériez des rapports ou archiviez des feuilles de calcul.

### Prochaines étapes
Explorez d'autres options de personnalisation dans la [documentation GroupDocs](https://docs.groupdocs.com/viewer/java/) et expérimentez l'intégration de ces fonctionnalités dans vos propres applications.

## Section FAQ

**Q1 : Quels formats de fichiers GroupDocs.Viewer prend‑il en charge ?**  
R1 : Il prend en charge un large éventail de formats de documents, y compris DOCX, XLSX, PDF et d'autres.

**Q2 : Comment gérer efficacement les gros fichiers Numbers ?**  
R2 : Utilisez les techniques de gestion de mémoire de Java et optimisez votre code pour traiter efficacement les gros fichiers.

**Q3 : GroupDocs.Viewer peut‑il être utilisé dans un projet commercial ?**  
R4 : Oui, mais vous devrez acheter une licence pour une utilisation commerciale.

**Q4 : Est‑il possible de personnaliser la qualité de sortie des images ?**  
R5 : Absolument. Vous pouvez ajuster les paramètres dans `JpgViewOptions` et `PngViewOptions`.

**Q5 : Où puis‑je trouver des exemples d'utilisation avancés ?**  
R5 : Consultez la [référence API](https://reference.groupdocs.com/viewer/java/) pour une documentation détaillée.

## Questions fréquemment posées

**Q : Comment convertir un fichier Numbers en PDF sans perdre le formatage ?**  
R : Utilisez `PdfViewOptions` comme indiqué ci-dessus ; le viewer préserve automatiquement la mise en page, les polices et les styles de cellules.

**Q : Puis‑je convertir une feuille de calcul en image en un seul appel ?**  
R : Oui, `JpgViewOptions` ou `PngViewOptions` gèrent la conversion en une étape, vous permettant de spécifier la résolution et la qualité.

**Q : Existe‑t‑il un moyen de traiter par lots plusieurs fichiers Numbers ?**  
R : Enveloppez la logique du viewer dans une boucle, réinitialisez `Viewer` pour chaque fichier, et écrivez chaque sortie dans un dossier distinct.

**Q : Ai‑je besoin d'une licence distincte pour chaque format de sortie ?**  
R : Non, une seule licence GroupDocs.Viewer couvre tous les formats pris en charge.

**Q : Quelle version de GroupDocs.Viewer est requise pour ces fonctionnalités ?**  
R : Les exemples ciblent la version 25.2, qui inclut la prise en charge complète de la conversion Numbers en PDF/HTML/Image.

## Ressources
- **Documentation :** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)
- **Référence API :** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Téléchargement :** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- **Acheter une licence :** [Buy a License](https://purchase.groupdocs.com/buy)
- **Essai gratuit :** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Licence temporaire :** [Request Here](https://purchase.groupdocs.com/temporary-license/)
- **Forum de support :** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Dernière mise à jour :** 2026-03-05  
**Testé avec :** GroupDocs.Viewer 25.2 for Java  
**Auteur :** GroupDocs