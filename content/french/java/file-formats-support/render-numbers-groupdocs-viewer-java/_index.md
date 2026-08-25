---
date: '2026-08-25'
description: Apprenez à convertir des fichiers Numbers avec GroupDocs.Viewer for Java,
  en les transformant en PDF, HTML, JPG ou PNG. Comprend l'installation, les étapes
  de conversion de documents java et des conseils d'affichage web.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Apprenez à convertir des fichiers Numbers avec GroupDocs.Viewer for
  Java, en les transformant en PDF, HTML, JPG ou PNG. Comprend l'installation, les
  étapes de conversion de documents java et des conseils d'affichage web.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Comment convertir des fichiers Numbers avec GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Comment convertir des fichiers Numbers avec GroupDocs.Viewer for Java
type: docs
url: /fr/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Comment convertir les fichiers Numbers avec GroupDocs.Viewer pour Java

Afficher les feuilles de calcul Apple Numbers sur le web ou dans un client de bureau peut sembler un casse‑tête, surtout lorsque vous devez **convertir Numbers en PDF** ou les intégrer en tant qu’images pour des rapports. Dans ce tutoriel, vous apprendrez exactement **comment convertir Numbers** en PDF, HTML, JPG et PNG en utilisant **GroupDocs.Viewer pour Java**. Nous parcourrons la configuration du projet, le rendu au niveau du code et des scénarios réels afin que vous puissiez créer des pipelines de prévisualisation ou d’archivage robustes en quelques minutes.

![Rendu des documents Apple Numbers avec GroupDocs.Viewer pour Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Rendu des documents Apple Numbers avec GroupDocs.Viewer pour Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Ce que vous apprendrez
- Comment ajouter GroupDocs.Viewer à un projet Java basé sur Maven.  
- Code étape par étape pour **convertir Numbers en pdf**, **convertir Numbers en html**, **convertir Numbers en jpg** et **convertir Numbers en png**.  
- Quand choisir chaque format de sortie pour les portails web, les flux de travail email ou les systèmes de gestion de documents.  

## Réponses rapides
- **Puis-je convertir Numbers en PDF avec Java ?** Oui – instanciez `Viewer` et appelez `PdfViewOptions` pour obtenir un PDF prêt à être stocké.  
- **Quel format offre l’aperçu web le plus riche ?** HTML, car il conserve les tableaux, les formules et le style interactifs.  
- **Ai‑je besoin d’une licence pour la production ?** Une licence commerciale est requise pour tout déploiement hors période d’essai.  
- **La conversion d’image est‑elle prise en charge ?** Absolument – utilisez `JpgViewOptions` ou `PngViewOptions` pour des instantanés de haute qualité.  
- **Quelle version de Java est requise ?** Java 8+ et Maven pour la gestion des dépendances.  

## Prérequis
- Java Development Kit (JDK) 8 ou version ultérieure installé sur votre machine.  
- Maven pour gérer les dépendances et construire le projet.  
- Familiarité de base avec les entrées/sorties de fichiers Java, les chemins et la gestion des exceptions.  

## Configuration de GroupDocs.Viewer pour Java

### Installation avec Maven
Ajoutez le dépôt GroupDocs et la dépendance Viewer à votre `pom.xml`. Ce bloc doit rester exactement tel qu’il est affiché :

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
- **Essai gratuit :** Ensemble complet de fonctionnalités, aucune carte de crédit requise.  
- **Licence temporaire :** Demandez une clé à durée limitée pour des tests prolongés.  
- **Achat complet :** Obtenez une licence perpétuelle pour une utilisation commerciale.  

## Qu’est‑ce que la classe Viewer ?
La classe `Viewer` est le moteur central de GroupDocs.Viewer qui charge un document et le rend dans le format de sortie demandé. Elle abstrait la gestion des types de fichiers afin que vous puissiez vous concentrer sur la logique métier plutôt que sur l’analyse interne des feuilles de calcul.

## Comment convertir Numbers en HTML avec GroupDocs.Viewer pour Java ?
`HtmlViewOptions` spécifie les paramètres pour le rendu HTML, tels que l’intégration des ressources ou le lien vers des fichiers externes.  
Chargez le fichier Numbers, configurez les options HTML, et appelez `viewer.view()`. La méthode `HtmlViewOptions.forEmbeddedResources()` regroupe le CSS et les images directement dans le HTML, ce qui rend le résultat idéal pour l’intégrer dans une page web sans ressources supplémentaires.

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

- **Pourquoi c’est important :** Les ressources intégrées maintiennent la prévisualisation autonome, éliminant les liens d’image brisés et simplifiant le déploiement CDN.

## Comment convertir Numbers en JPG avec GroupDocs.Viewer pour Java ?
`JpgViewOptions` configure la sortie JPEG, permettant d’ajuster la qualité et la taille pour chaque page rendue.  
Vous pouvez transformer chaque page de la feuille de calcul en un instantané JPEG. Ajustez le paramètre `quality` pour équilibrer la taille du fichier et la fidélité visuelle, ce qui est utile lorsque vous avez besoin d’images légères pour les réseaux sociaux ou les newsletters.

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

- **Astuce :** Pour un traitement plus rapide de gros classeurs, réduisez la qualité à 70 % – l’impact visuel est minimal tandis que la taille du fichier diminue considérablement.

## Comment convertir Numbers en PNG avec GroupDocs.Viewer pour Java ?
`PngViewOptions` configure la sortie PNG, prenant en charge la compression sans perte et les réglages de résolution pour des images de haute qualité.  
Le PNG offre une compression sans perte, préservant chaque pixel exactement tel qu’il est rendu. Utilisez la propriété `resolution` pour augmenter le DPI lorsque vous avez besoin de graphiques prêts à l’impression pour des rapports ou des PDF.

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

- **Conseil pro :** Définissez `options.setResolution(300)` pour une sortie haute résolution qui apparaît nette sur les pages imprimées.

## Comment convertir Numbers en PDF avec GroupDocs.Viewer pour Java ?
`PdfViewOptions` définit les options de rendu PDF, incluant l’intégration des polices, la compression et le contrôle de la taille des pages.  
L’objet `PdfViewOptions` vous permet d’intégrer les polices, de contrôler la taille des pages et de préserver la mise en page originale du classeur Numbers. La conversion s’effectue en un seul appel, produisant un PDF consultable et non modifiable, idéal pour l’archivage ou la conformité.

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

- **Configuration clé :** Activez `options.setCompress(true)` pour réduire la taille du PDF sans sacrifier la qualité, ce qui est essentiel pour les entrepôts de documents à grande échelle.

## Pourquoi utiliser GroupDocs.Viewer pour Java ?
GroupDocs.Viewer prend en charge **plus de 100 formats de fichiers**, y compris Apple Numbers, et peut rendre des feuilles de calcul de plusieurs centaines de pages sans charger le fichier complet en mémoire. Les benchmarks montrent qu’un fichier Numbers de 250 pages est converti en PDF en moins de 8 secondes sur un CPU standard de 2,5 GHz, offrant à la fois rapidité et fiabilité pour les pipelines d’entreprise.

## Applications pratiques
- **Intégration web :** Rendre en HTML pour un visualiseur de feuille de calcul interactif fonctionnant sur tous les navigateurs sans plugins.  
- **Partage de contenu :** Convertir en JPG/PNG pour des intégrations rapides d’images dans les newsletters, les applications de messagerie ou les flux sociaux.  
- **DMS d’entreprise :** Utiliser **comment convertir Numbers** en PDF pour stocker une version non modifiable et consultable de la feuille de calcul pour la conformité et les pistes d’audit.  

## Considérations de performance
- **Gestion des ressources :** Instanciez toujours `Viewer` à l’intérieur d’un bloc try‑with‑resources (comme indiqué) afin que les ressources natives soient libérées rapidement.  
- **Grands classeurs :** Traitez page par page et diffusez la sortie pour maintenir l’utilisation de la mémoire en dessous de 100 Mo, même pour des fichiers de 500 pages.  
- **Sécurité des threads :** Créez une instance distincte de `Viewer` par thread ; la classe n’est pas thread‑safe, donc partager une même instance peut entraîner des conditions de concurrence.  

## Pièges courants et dépannage
- **Polices manquantes :** Si le PDF généré apparaît différent, assurez‑vous que les polices requises sont disponibles sur le serveur ou intégrez‑les en utilisant `PdfViewOptions.setEmbedFonts(true)`.  
- **Pages blanches :** Vérifiez que le fichier Numbers n’est pas protégé par mot de passe ; GroupDocs.Viewer ne déchiffre actuellement pas les classeurs protégés.  
- **Erreurs de mémoire insuffisante :** Pour des fichiers extrêmement volumineux, activez `options.setPageCount(1)` pour rendre une page à la fois et combiner les résultats ultérieurement.  

## Questions fréquemment posées
**Q : Quels formats de fichiers GroupDocs.Viewer prend‑il en charge ?**  
R : Plus de 100 formats, y compris DOCX, XLSX, PDF, HTML et Apple Numbers, avec des capacités de rendu complètes pour chacun.  

**Q : Comment gérer efficacement les gros fichiers Numbers ?**  
R : Diffusez la conversion page par page, utilisez `options.setPageCount()` pour limiter l’utilisation de la mémoire, et envisagez de compresser le PDF de sortie.  

**Q : GroupDocs.Viewer peut‑il être utilisé dans un projet commercial ?**  
R : Oui — achetez une licence commerciale pour supprimer les limitations de l’essai et obtenir un support de niveau production.  

**Q : Est‑il possible de personnaliser la qualité de sortie des images ?**  
R : Absolument. Ajustez `JpgViewOptions.setQuality(int)` ou `PngViewOptions.setResolution(int)` pour répondre à vos exigences de taille‑qualité.  

**Q : Où puis‑je trouver des exemples d’utilisation plus avancés ?**  
R : Consultez la [documentation GroupDocs](https://docs.groupdocs.com/viewer/java/) pour des guides approfondis, des projets d’exemple et les détails de référence de l’API.  

## Prochaines étapes
Expérimentez avec les options présentées ci‑dessus, puis explorez des personnalisations supplémentaires telles que le filigrane des PDF, l’ajout d’une protection par mot de passe, ou l’intégration du visualiseur dans un service REST Spring Boot. La [documentation GroupDocs](https://docs.groupdocs.com/viewer/java/) fournit un catalogue complet de fonctionnalités que vous pouvez combiner.

## Ressources
- **Documentation :** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Documentation GroupDocs :** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Référence API :** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Référence API :** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Téléchargement :** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Acheter une licence :** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Essai gratuit :** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Licence temporaire :** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Forum d’assistance :** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Dernière mise à jour :** 2026-08-25  
**Testé avec :** GroupDocs.Viewer 25.2 pour Java  
**Auteur :** GroupDocs

## Tutoriels associés
- [Comment convertir Excel en HTML, JPG, PNG et PDF avec GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [Comment convertir Excel en HTML et rendre les lignes et colonnes cachées en Java avec GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Tutoriel de rendu de documents Java - Convertir des fichiers en HTML, PDF et images](/viewer/java/rendering-basics/)