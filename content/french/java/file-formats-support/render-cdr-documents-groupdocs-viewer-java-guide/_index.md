---
date: '2026-02-28'
description: Apprenez à convertir les fichiers CDR en HTML, JPG, PNG et PDF à l'aide
  de GroupDocs.Viewer pour Java. Comprend l'installation, des exemples de code et
  des conseils de performance.
keywords:
- render CDR files
- GroupDocs.Viewer Java
- HTML conversion
title: convertir cdr en html, jpg, png, pdf avec GroupDocs.Viewer Java
type: docs
url: /fr/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/
weight: 1
---

# convertir cdr en html, jpg, png, pdf avec GroupDocs.Viewer Java

Si vous avez besoin de **convertir CDR en HTML** (ou en JPG, PNG et PDF) rapidement et de manière fiable, vous êtes au bon tutoriel. Dans ce guide, nous passerons en revue tout ce dont vous avez besoin — de l'installation de GroupDocs.Viewer pour Java à la génération de fichiers CorelDRAW (CDR) en pages HTML compatibles web, images de haute qualité et PDF lisibles universellement. À la fin, vous pourrez intégrer ces conversions dans n'importe quelle application Java avec seulement quelques lignes de code.

![Rendu des fichiers CDR avec GroupDocs.Viewer pour Java](/viewer/file-formats-support/render-cdr-files.png)

## Réponses rapides
- **Quelle bibliothèque convertit CDR en HTML ?** GroupDocs.Viewer for Java.  
- **Puis-je également convertir CDR en JPG, PNG et PDF ?** Oui — même API Viewer avec différentes options de vue.  
- **Ai-je besoin d'une licence ?** Un essai gratuit ou une licence temporaire fonctionne pour les tests ; une licence complète est requise pour la production.  
- **Quelle version de Java est requise ?** JDK 8 ou plus récent.  
- **La conversion par lots est‑elle prise en charge ?** Absolument — il suffit de boucler sur les fichiers avec la même instance de Viewer.

## Qu’est‑ce que « convertir CDR en HTML » ?
Convertir CDR en HTML signifie transformer un fichier vectoriel CorelDRAW en balisage HTML standard, en incorporant éventuellement des images et des styles afin que le design puisse être visualisé directement dans un navigateur web sans nécessiter le logiciel de conception original.

## Pourquoi convertir CDR en HTML, JPG, PNG ou PDF ?
- **HTML** vous permet d'intégrer des graphiques dans des portails web et de les partager instantanément.  
- **JPG** et **PNG** vous fournissent des images raster pour les galeries, les vignettes ou les pièces jointes d'e‑mail.  
- **PDF** offre une version imprimable, indépendante de la plateforme, pour l'archivage ou les systèmes de partage de documents.  

Disposer des quatre formats à portée de main signifie que vous pouvez fournir le type de fichier approprié à chaque audience, améliorer les performances et préparer vos actifs pour le futur.

## Prérequis

Avant de commencer, assurez‑vous d’avoir :

1. **Bibliothèques et dépendances** – GroupDocs.Viewer ajouté à votre projet Maven.  
2. **Java Development Kit (JDK)** – version 8 ou plus récente installée.  
3. **Connaissances de base en Java** – pour comprendre les extraits de code.

### Bibliothèques requises, versions et dépendances

Ajoutez la configuration Maven suivante à votre `pom.xml` (identique au tutoriel original) :

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

### Étapes d’obtention de licence

GroupDocs.Viewer offre un essai gratuit, des licences temporaires pour les tests, ou des options d’achat complet :

- **Essai gratuit** – Téléchargez depuis la [Page de version GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Licence temporaire** – Demandez‑en une sur la [Page de licence temporaire GroupDocs](https://purchase.groupdocs.com/temporary-license/).  
- **Achat** – Obtenez une licence permanente via la [Page d'achat GroupDocs](https://purchase.groupdocs.com/buy).

## Configuration de GroupDocs.Viewer pour Java

### Installation avec Maven
Le fragment Maven ci‑dessus récupérera automatiquement tous les JAR requis. Il suffit d'exécuter `mvn clean install` après avoir enregistré le fichier.

### Initialisation de la licence
Initialisez votre licence avant de rendre tout document :

```java
import com.groupdocs.viewer.License;

License lic = new License();
lic.setLicense("path/to/your/license/file.lic");
```

## Guide d’implémentation

Vous trouverez ci‑dessous des exemples étape par étape pour chaque format de sortie. Les blocs de code sont identiques au tutoriel original ; nous n'avons ajouté que du texte explicatif autour d'eux.

### Comment convertir CDR en HTML avec GroupDocs.Viewer

#### Rendu du document CDR en HTML
**Vue d’ensemble :** Convertissez vos fichiers CDR en HTML compatible web pour un partage facile.

**Étape 1 – Configurer les chemins de fichiers**

```java
import java.nio.file.Path;

Path outputDirectory = TestFiles.getOutputDirectoryPath("RenderingCdr");
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.html");
```

**Étape 2 – Initialiser le Viewer et rendre**

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options); // Render the document into HTML format
}
```

### Comment convertir CDR en JPG avec GroupDocs.Viewer

#### Rendu du document CDR en JPG
**Vue d’ensemble :** Produisez des images JPEG de haute qualité à partir de votre source CDR.

**Étape 1 – Configurer les chemins de fichiers**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.jpg");
```

**Étape 2 – Initialiser le Viewer et rendre**

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into JPG format
}
```

### Comment convertir CDR en PNG avec GroupDocs.Viewer

#### Rendu du document CDR en PNG
**Vue d’ensemble :** Générez des images PNG sans perte pour l’archivage ou les besoins de conception.

**Étape 1 – Configurer les chemins de fichiers**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result_{0}.png");
```

**Étape 2 – Initialiser le Viewer et rendre**

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PNG format
}
```

### Comment convertir CDR en PDF avec GroupDocs.Viewer

#### Rendu du document CDR en PDF
**Vue d’ensemble :** Transformez vos fichiers CDR en PDF lisibles universellement.

**Étape 1 – Configurer les chemins de fichiers**

```java
Path pageFilePathFormat = outputDirectory.resolve("cdr_result.pdf");
```

**Étape 2 – Initialiser le Viewer et rendre**

```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options); // Render the document into PDF format
}
```

## Applications pratiques

- **Portails web :** Utilisez la conversion HTML pour intégrer les conceptions CDR directement sur votre site.  
- **Galeries d'images :** Déployez les sorties JPG/PNG pour des galeries d'images à chargement rapide.  
- **Partage de documents :** Fournissez des PDF aux clients qui ont besoin d’une version imprimable et en lecture seule.  
- **Archivage :** Stockez plusieurs formats pour garantir l’accessibilité future.  
- **Intégration multiplateforme :** Alimentez les fichiers générés dans d’autres services (p. ex., OCR, analyses).

## Considérations de performance

- **Libérez les instances de Viewer** rapidement (comme montré avec try‑with‑resources) pour libérer la mémoire.  
- **Traitement par lots :** Parcourez une collection de fichiers CDR en utilisant la même configuration de Viewer pour réduire la surcharge.  
- **Allocation des ressources :** Allouez suffisamment de CPU/RAM pour les fichiers CDR volumineux ou complexes ; les outils de surveillance peuvent vous aider à affiner les réglages.

## Conclusion

Nous vous avons montré comment **convertir CDR en HTML**, ainsi qu’en JPG, PNG et PDF, en utilisant GroupDocs.Viewer pour Java. En suivant les extraits de code concis et les conseils de bonnes pratiques, vous pouvez intégrer ces conversions dans n'importe quel flux de travail basé sur Java, offrant des sorties flexibles et de haute qualité à vos utilisateurs.

### Prochaines étapes
- Expérimentez avec des options de rendu avancées comme des tailles de page personnalisées ou des filigranes.  
- Combinez le pipeline de conversion avec une API REST pour offrir une transformation de fichiers à la demande.  
- Rejoignez la communauté et posez des questions sur le [GroupDocs Forum](https://forum.groupdocs.com/c/viewer).

## Questions fréquentes

**Q : Puis‑je convertir des fichiers CDR protégés par mot de passe ?**  
R : Oui. Chargez le fichier avec une instance `Viewer` qui accepte un paramètre de mot de passe (voir la documentation de l'API).

**Q : Existe‑t‑il une limite au nombre de pages pouvant être converties en une fois ?**  
R : Aucun plafond strict, mais les fichiers très volumineux peuvent nécessiter plus de mémoire ; envisagez un traitement page par page.

**Q : La sortie HTML inclut‑elle les polices intégrées ?**  
R : Lors de l'utilisation de `HtmlViewOptions.forEmbeddedResources`, les polices sont intégrées en Base64, garantissant un rendu cohérent.

**Q : Comment contrôler la qualité JPEG ?**  
R : `JpgViewOptions` propose une méthode `setQuality(int)` où vous pouvez spécifier une valeur de 1 à 100.

**Q : Puis‑je convertir des fichiers CDR sur un serveur Linux ?**  
R : Absolument — GroupDocs.Viewer est indépendant de la plateforme tant que le JDK est installé.

---

**Dernière mise à jour :** 2026-02-28  
**Testé avec :** GroupDocs.Viewer 25.2 pour Java  
**Auteur :** GroupDocs