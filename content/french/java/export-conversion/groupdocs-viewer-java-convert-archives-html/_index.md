---
date: '2026-02-23'
description: Apprenez à définir le nombre d'éléments par page, à intégrer les ressources
  HTML et à convertir en lot des archives en HTML à page unique ou multi‑pages avec
  GroupDocs.Viewer Java.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Définir le nombre d''éléments par page : Convertir les archives en HTML avec
  GroupDocs.Viewer Java'
type: docs
url: /fr/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Définir le nombre d'éléments par page : Convertir des archives en HTML avec GroupDocs.Viewer Java

Convertir des fichiers d'archive tels que ZIP ou RAR en HTML compatible avec le Web est un besoin fréquent lorsque vous souhaitez partager ou examiner des documents directement dans un navigateur. Dans ce guide, vous apprendrez **comment définir le nombre d'éléments par page** lors du rendu des archives, comment intégrer les ressources HTML pour une sortie autonome, et comment convertir des archives en lot de manière efficace avec GroupDocs.Viewer Java.

![Convertir des archives en HTML avec GroupDocs.Viewer pour Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Réponses rapides
- **Que contrôle « set items per page » ?** Il détermine combien de fichiers ou dossiers d’une archive apparaissent sur chaque page HTML générée.  
- **Puis‑je intégrer des images et du CSS directement dans le HTML ?** Oui – utilisez l’option `forEmbeddedResources` pour intégrer les ressources HTML.  
- **La conversion en lot est‑elle possible ?** Absolument ; vous pouvez parcourir une collection d’archives et rendre chacune avec les mêmes paramètres.  
- **Ai‑je besoin de Maven pour utiliser GroupDocs.Viewer ?** Oui, ajoutez la dépendance `maven groupdocs viewer` comme indiqué ci‑dessous.  
- **Quels formats de sortie sont pris en charge ?** Les formats HTML Java à page unique et HTML Java multi‑pages sont tous deux disponibles.

## Qu’est‑ce que « set items per page » dans GroupDocs.Viewer ?
Le paramètre **set items per page** appartient aux options de rendu d’archive. Il indique au viewer combien d’entrées d’archive (fichiers ou dossiers) doivent être affichées sur chaque page HTML lorsque vous générez un document HTML multi‑pages. Ajuster cette valeur vous aide à équilibrer la taille des pages et la vitesse de navigation, surtout pour les archives volumineuses.

## Pourquoi intégrer les ressources HTML ?
Intégrer les ressources (images, CSS, polices) directement dans le fichier HTML crée un document unique et portable qui peut être ouvert sans fichiers externes. Cela est idéal pour les pièces jointes d’e‑mail, la visualisation hors ligne, ou l’intégration de la sortie dans d’autres pages Web.

## Prérequis

- **Bibliothèques requises :** Inclure GroupDocs.Viewer version 25.2 ou ultérieure.  
- **Environnement :** Java Development Kit (JDK) installé et configuré.  
- **Connaissances :** Java de base et gestion des dépendances Maven.  

## Configuration Maven de GroupDocs Viewer

Ajoutez le dépôt GroupDocs et la dépendance du viewer à votre `pom.xml` :

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
GroupDocs.Viewer propose un **lien d’essai gratuit**, une licence temporaire, ou une option d’achat complet. Choisissez celle qui correspond à votre planning de projet.

### Initialisation de base
Après la configuration Maven, importez le viewer dans votre code :

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Comment rendre les archives en HTML à page unique

### Étape 1 : Définir le répertoire de sortie
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Étape 2 : Définir le nom de fichier pour la sortie à page unique
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Étape 3 : Initialiser le Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Étape 4 : Configurer les options de rendu (intégrer les ressources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Étape 5 : Rendre en une seule page
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Comment rendre les archives en HTML multi‑pages et définir le nombre d’éléments par page

### Étape 1 : Réutiliser le répertoire de sortie
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Étape 2 : Définir le format du nom de fichier pour plusieurs pages
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Étape 3 : Réinitialiser le Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Étape 4 : Configurer les options multi‑pages (intégrer les ressources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Étape 5 : Définir le nombre d’éléments par page (mot‑clé principal en action)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Applications pratiques

- **Systèmes de gestion de documents :** Ajoutez une fonctionnalité d’aperçu d’archives sans installer de visionneuses supplémentaires.  
- **Portails Web :** Offrez aux utilisateurs un moyen rapide, sans téléchargement, d’explorer des documents groupés.  
- **Outils de collaboration :** Permettez aux équipes d’inspecter les archives partagées directement dans le navigateur.

## Considérations de performance

- **Gestion des ressources :** Surveillez l’utilisation de la mémoire ; envisagez d’ajuster le ramasse‑miettes du JVM pour les gros lots.  
- **Conversion en lot d’archives :** Parcourez une liste de fichiers d’archive et appelez la même logique de rendu pour maximiser le débit.  
- **Stratégie de mise en cache :** Stockez le HTML rendu dans un cache si la même archive est fréquemment consultée.

## Questions fréquemment posées

**Q : Qu’est‑ce que GroupDocs.Viewer Java ?**  
**A :** Une bibliothèque polyvalente pour rendre les documents—y compris les archives—dans des formats tels que HTML, PDF et images.

**Q : Comment obtenir un essai gratuit de GroupDocs.Viewer ?**  
**A :** Visitez le [lien d’essai gratuit](https://releases.groupdocs.com/viewer/java/) pour télécharger et tester.

**Q : Puis‑je convertir d’autres types de documents que les archives ?**  
**A :** Oui, le viewer prend en charge les PDFs, Word, Excel et bien d’autres formats.

**Q : Que faire si le rendu est lent ?**  
**A :** Réduisez le nombre d’éléments par page, activez le streaming, ou traitez les archives en lots plus petits.

**Q : Où puis‑je obtenir de l’aide ou du support ?**  
**A :** Contactez‑nous via le [forum de support](https://forum.groupdocs.com/c/viewer/9).

**Q : Est‑il possible d’intégrer le CSS et les images directement dans le HTML ?**  
**A :** Absolument—utilisez `HtmlViewOptions.forEmbeddedResources` comme montré dans les exemples.

**Q : Comment convertir en lot un dossier d’archives ?**  
**A :** Parcourez chaque fichier avec une boucle `for`, en appliquant la même configuration `Viewer` et `HtmlViewOptions` à chaque itération.

## Ressources

- **Documentation :** Approfondissez les fonctionnalités avec la [documentation GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Référence API :** Explorez l’API complète sur le [site API GroupDocs](https://reference.groupdocs.com/viewer/java/).  
- **Téléchargement :** Obtenez les derniers binaires depuis la [page de téléchargement](https://releases.groupdocs.com/viewer/java/).  
- **Achat et licences :** Consultez les options sur la [page d’achat](https://purchase.groupdocs.com/buy).  
- **Support et communauté :** Rejoignez les discussions sur le [forum GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Dernière mise à jour :** 2026-02-23  
**Testé avec :** GroupDocs.Viewer 25.2  
**Auteur :** GroupDocs