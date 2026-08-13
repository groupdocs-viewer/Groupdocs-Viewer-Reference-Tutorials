---
date: '2026-05-26'
description: Apprenez à convertir nsf en pdf et d’autres formats (HTML, JPG, PNG)
  avec GroupDocs.Viewer for Java. Guide pas à pas avec des conseils de bonnes pratiques.
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: Convertir nsf en pdf avec GroupDocs.Viewer for Java
type: docs
url: /fr/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# Convertir des fichiers NSF en plusieurs formats avec GroupDocs.Viewer pour Java

Dans ce guide complet, vous apprendrez **comment convertir nsf en pdf** et également rendre les fichiers NSF en HTML, JPG et PNG avec GroupDocs.Viewer pour Java. Que vous ayez besoin d'archiver des bases de données Lotus Notes, de les afficher dans un navigateur ou de générer des aperçus d'images, ce tutoriel vous guide à travers tout—de la configuration de l'environnement aux détails au niveau du code—pour que vous puissiez mettre en œuvre la conversion en quelques minutes.

![Convertir des fichiers NSF en HTML, JPG, PNG et PDF avec GroupDocs.Viewer pour Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[Convertir des fichiers NSF en HTML, JPG, PNG et PDF avec GroupDocs.Viewer pour Java](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## Réponses rapides
- **Quel est le cas d'utilisation principal ?** Rendu des fichiers NSF en PDF, HTML, JPG ou PNG pour le web, l'archivage ou le partage.  
- **Quelle bibliothèque gère la conversion ?** GroupDocs.Viewer pour Java.  
- **Ai‑je besoin d’une licence ?** Un essai gratuit est disponible ; une licence complète est requise pour la production.  
- **Quelle version de Java est requise ?** JDK 8 ou supérieur.  
- **Puis‑je traiter plusieurs fichiers NSF en lot ?** Oui – encapsulez la logique de rendu dans une boucle et gérez les ressources avec try‑with‑resources.

## Qu’est‑ce que « convertir nsf en pdf » ?

Convertir un fichier NSF (base de données Lotus Notes) en PDF produit un document statique, lisible universellement, qui préserve la mise en page, les polices et les graphiques d’origine sans nécessiter le client Notes. Ce format est idéal pour l’archivage juridique, la distribution sécurisée et le stockage à long terme, car les fichiers PDF peuvent être ouverts sur n’importe quel système d’exploitation ou appareil.

## Pourquoi convertir NSF en PDF et autres formats ?

Transformer les fichiers NSF en PDF, HTML, JPG ou PNG permet une accessibilité universelle, conserve la fidélité visuelle et facilite l’intégration avec les applications web et mobiles modernes. Le PDF maintient la mise en page exacte, le HTML offre une visualisation instantanée dans le navigateur, et le JPG/PNG fournissent des captures d’image haute résolution pour les vignettes ou l’intégration.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

- **Java Development Kit (JDK) 8+** – JDK 11 ou plus récent est recommandé pour de meilleures performances de collecte des déchets.  
- **Maven** – pour la gestion des dépendances.  
- **GroupDocs.Viewer pour Java** – version d’essai ou sous licence.  
- Une connaissance de base des I/O de fichiers Java et de la structure d’un projet Maven.

## Configuration de GroupDocs.Viewer pour Java

### Configuration Maven

Ajoutez la dépendance GroupDocs.Viewer à votre `pom.xml`. Cela récupère tous les binaires requis ainsi que les bibliothèques transitives.

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

Pour débloquer toutes les fonctionnalités, vous pouvez :

- **Essai gratuit :** Évaluer les fonctionnalités principales sans clé de licence.  
- **Licence temporaire :** Demander une clé à durée limitée pour les tests.  
- **Achat complet :** Obtenir une licence de production pour une utilisation illimitée.

### Initialisation de base

`Viewer` est la classe principale qui rend les documents au format de sortie souhaité. Initialise‑la avec votre licence et le chemin du fichier à l’intérieur d’un bloc try‑with‑resources afin d’assurer une libération correcte des ressources.

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## Comment convertir NSF en PDF

Pour convertir un document NSF en PDF, créez d’abord une instance `Viewer` pointant vers le fichier source. Puis configurez `PdfViewOptions` pour définir les caractéristiques de sortie telles que la taille de page, le niveau de compression et l’inclusion des polices. Enfin, appelez `viewer.view(pdfOptions)` qui rend l’ensemble du document dans un seul fichier PDF prêt à être distribué.

`PdfViewOptions` spécifie les paramètres spécifiques au PDF comme la taille de page et la compression.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## Rendu de NSF en HTML

### Vue d'ensemble

Convertissez les documents NSF en pages HTML autonomes, en incorporant images et CSS pour une représentation à l’écran précise.

### Guide étape par étape

#### 1. Configurer le répertoire de sortie et le chemin du fichier

Définissez le dossier où les fichiers HTML seront enregistrés.

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. Configurer les options de chargement

`LoadOptions` vous permet d’ajuster le chargement des ressources, par exemple en définissant un délai d’attente pour les actifs externes.

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. Initialiser le Viewer et rendre

`Viewer` traite le NSF et écrit les fichiers HTML dans le répertoire cible.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## Rendu de NSF en JPG

### Vue d'ensemble

Générez des images JPG de haute qualité à partir de chaque page d’un document NSF, utiles pour les aperçus ou l’intégration dans des flux de travail centrés sur les images.

#### 1. Définir le chemin de sortie

Spécifiez un modèle de nommage tel que `output_page_{0}.jpg` où `{0}` représente le numéro de page.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. Configurer et rendre

`JpgViewOptions` définit les paramètres de sortie JPEG, incluant la résolution et la qualité. Créez `JpgViewOptions`, définissez le DPI souhaité, puis invoquez `viewer.view(options)`.

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## Rendu de NSF en PNG

### Vue d'ensemble

Produisez des images PNG sans perte qui conservent chaque détail des pages NSF d’origine.

#### 1. Définir le chemin de sortie

Utilisez un modèle tel que `nsf_page_{0}.png` pour la pagination automatique.

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. Rendre le document

`PngViewOptions` configure les paramètres de sortie PNG comme la résolution et la profondeur de couleur. Configurez `PngViewOptions` (par ex., `setResolution(300)`) puis lancez le rendu.

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## Applications pratiques

1. **Partage de documents basé sur le web :** Convertir NSF en HTML pour une visualisation instantanée dans le navigateur sans installer Notes.  
2. **Archivage d’images :** Stocker des instantanés JPG/PNG page par page pour des galeries de vignettes ou des pipelines OCR.  
3. **Accès universel :** Utiliser la conversion PDF pour fournir un fichier unique et sécurisé qui peut être ouvert sur n’importe quel appareil, répondant aux exigences de conformité.

## Considérations de performance

- **Chargement des ressources :** Ajustez `setResourceLoadingTimeout` en fonction de la latence réseau pour éviter les blocages.  
- **Gestion de la mémoire :** Utilisez try‑with‑resources pour les instances `Viewer` ; cela libère automatiquement les ressources natives.  
- **Traitement par lots :** Pour de grands volumes, traitez les fichiers séquentiellement ou avec des flux parallèles, en surveillant l’utilisation du tas afin de rester en dessous des limites de mémoire de la JVM.

## Section FAQ

**Quel est le meilleur format pour convertir les documents NSF ?**  
- Cela dépend de l’utilisation en aval : HTML pour les portails web, PDF pour la distribution universelle, JPG/PNG pour les flux de travail basés sur les images.

**Comment gérer efficacement les gros fichiers NSF ?**  
- Ajustez `LoadOptions` (par ex., augmentez `setResourceLoadingTimeout`), traitez les fichiers par lots plus petits et réutilisez une même instance `Viewer` lorsque cela est possible.

**Puis‑je personnaliser la qualité de sortie dans les formats image ?**  
- Oui. Définissez le DPI, le niveau de compression et la profondeur de couleur via `JpgViewOptions` ou `PngViewOptions` avant le rendu.

**Que faire si la conversion échoue ?**  
- Vérifiez les chemins de fichiers, assurez‑vous que le fichier NSF n’est pas corrompu et consultez les journaux de GroupDocs.Viewer pour des codes d’erreur détaillés. Mettre à jour vers la dernière version de la bibliothèque résout souvent les problèmes de compatibilité.

**La conversion par lots est‑elle prise en charge ?**  
- Absolument. Encapsulez la logique de rendu dans une boucle `for` ou un Stream Java pour traiter automatiquement plusieurs fichiers NSF.

## Questions fréquemment posées

**Q : Comment convertir un fichier NSF en PDF sans perdre les annotations ?**  
R : `PdfViewOptions` préserve la plupart des annotations automatiquement ; il suffit de rendre le document avec ces options et le PDF résultant reflétera la mise en page originale.

**Q : Puis‑je convertir des fichiers NSF protégés par mot de passe ?**  
R : Oui. Fournissez les informations d’identification via `LoadOptions` avant de créer l’instance `Viewer`.

**Q : Quelle version de Java offre les meilleures performances ?**  
R : JDK 11 ou plus récent offre une collecte des déchets et une concurrence améliorées, ce qui accélère les conversions par lots.

**Q : Est‑il possible de définir un DPI personnalisé pour la sortie JPG/PNG ?**  
R : Configurez `JpgViewOptions.setResolution(int dpi)` ou `PngViewOptions.setResolution(int dpi)` avant d’appeler `viewer.view(options)`.

**Q : GroupDocs.Viewer prend‑il en charge le streaming direct du résultat vers une réponse HTTP ?**  
R : Oui. Utilisez la surcharge `Stream` des options de vue pour écrire le résultat directement dans `HttpServletResponse.getOutputStream()`.

## Conclusion

Vous disposez maintenant d’une feuille de route complète pour **convertir nsf en pdf** et rendre les fichiers NSF en HTML, JPG et PNG avec GroupDocs.Viewer pour Java. En suivant les étapes ci‑dessus, vous pouvez intégrer une conversion de documents robuste dans n’importe quelle application Java, automatiser les travaux par lots et fournir du contenu dans le format qui correspond le mieux aux besoins de vos utilisateurs. Explorez les fonctionnalités supplémentaires du Viewer telles que le filigrane, les polices personnalisées et la gestion multi‑pages pour enrichir davantage votre solution.

---

**Dernière mise à jour :** 2026-05-26  
**Testé avec :** GroupDocs.Viewer 25.2  
**Auteur :** GroupDocs

## Tutoriels associés

- [groupdocs viewer java : Convertir des documents en PDF – Guide complet](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – Convertir ODF en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Convertir PST en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour Java](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)