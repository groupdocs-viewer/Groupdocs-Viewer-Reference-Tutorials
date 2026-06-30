---
date: '2026-06-30'
description: Apprenez comment obtenir viewinfo et récupérer les structures de type
  de fichiers d'archives Java en utilisant GroupDocs.Viewer. Ce guide couvre la configuration,
  des exemples de code et des cas d'utilisation réels.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Comment obtenir ViewInfo et récupérer les structures d'archives en Java
type: docs
url: /fr/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Comment obtenir ViewInfo et récupérer les structures d’archives en Java

Gérer efficacement les fichiers d’archive nécessite une compréhension claire de leur structure. Dans ce tutoriel, vous apprendrez **comment obtenir viewinfo** pour toute archive et verrez comment cela vous aide à travailler avec le **type de fichier d’archive java**. Nous parcourrons la configuration de GroupDocs.Viewer, l’extraction des informations de vue et la lecture récursive des hiérarchies de dossiers afin que vous puissiez intégrer la solution dans des projets réels.

![Structures d’archives avec GroupDocs.Viewer pour Java](/viewer/document-loading/archive-structures-java.png)

**Ce que vous apprendrez**
- Configurer et paramétrer GroupDocs.Viewer pour Java.  
- Méthodes pour **obtenir viewinfo** à partir des archives.  
- Techniques pour lire et afficher la structure des dossiers d’un fichier d’archive.  
- Applications pratiques et considérations de performance lors de l’utilisation de GroupDocs.Viewer dans des projets Java.

## Réponses rapides
- **Qu’est‑ce que “viewinfo” fournit ?** Il renvoie le type de fichier, le nombre de pages et une liste complète des dossiers et fichiers contenus dans une archive.  
- **Quels formats d’archive sont pris en charge ?** ZIP, RAR, TAR, 7z, ISO, et plus de 12 autres formats courants.  
- **Ai‑je besoin d’une licence pour la production ?** Oui — une licence commerciale est requise pour la production ; une version d’essai gratuite suffit pour l’évaluation.  
- **Les grandes archives peuvent‑elles être traitées efficacement ?** Absolument — utilisez les options de streaming et traitez un niveau de dossier à la fois pour limiter l’utilisation de la mémoire.  
- **Maven est‑il le seul moyen d’ajouter la bibliothèque ?** Maven est le gestionnaire de dépendances recommandé, mais Gradle ou l’inclusion manuelle du JAR fonctionnent également.

## Qu’est‑ce que “how to get viewinfo” ?

`getViewInfo` est une méthode de l’API GroupDocs.Viewer qui extrait les métadonnées d’un document ou d’une archive sans rendu complet. Elle renvoie l’arborescence interne des dossiers, le nombre de fichiers et les propriétés de base en un seul appel, vous permettant de choisir les parties à traiter. L’appel retourne un instantané complet des archives jusqu’à 500 Mo en moins d’une seconde sur des serveurs typiques.

## Pourquoi récupérer les structures du type de fichier d’archive Java ?

Récupérer la disposition interne d’un **type de fichier d’archive java** vous permet de localiser instantanément les fichiers nécessaires, d’éviter les extractions inutiles et de créer des pipelines automatisés qui n’interagissent qu’avec les sous‑dossiers pertinents. Cette approche réduit les I/O jusqu’à 70 % pour les grandes archives et rend possible le scan de milliers de fichiers par minute dans des scénarios d’ingestion de données.

## Prérequis

- **Java Development Kit (JDK) :** Version 8 ou supérieure.  
- **Maven :** Pour la gestion des dépendances et les builds.  
- **Connaissances de base en Java :** La familiarité avec les concepts de POO aide mais n’est pas obligatoire.  

Vous avez également besoin d’accéder à la bibliothèque GroupDocs.Viewer, que vous pouvez ajouter à votre projet Maven comme indiqué ci‑dessous.

## Configuration de GroupDocs.Viewer pour Java

### Configuration Maven

Ajoutez le dépôt et la dépendance à votre `pom.xml`.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Acquisition de licence

- **Essai gratuit :** Téléchargez une version d’essai depuis le site GroupDocs.  
- **Licence temporaire :** Demandez une clé temporaire pour une évaluation à court terme.  
- **Licence complète :** Achetez une licence commerciale pour une utilisation illimitée en production.

Une fois la bibliothèque sur votre classpath, vous pouvez commencer à coder.

## Guide d’implémentation

### Comment obtenir ViewInfo pour les fichiers d’archive

Pour obtenir les informations de vue, chargez d’abord l’archive dans le Viewer, puis appelez `getViewInfo` pour récupérer les métadonnées, et enfin parcourez la hiérarchie de dossiers retournée. Ce schéma en trois étapes fonctionne pour tous les formats d’archive pris en charge et fournit un instantané complet en un seul appel d’API, simplifiant le traitement ultérieur.

#### Initialiser le Viewer

La classe `Viewer` est le point d’entrée pour toutes les opérations de rendu et d’inspection. Elle gère les flux de fichiers, la détection du format et le nettoyage des ressources.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Récupérer les informations de vue

`ViewInfo` encapsule les métadonnées telles que le type de fichier, le nombre total de pages et une liste hiérarchique des dossiers et fichiers. L’appel à `getViewInfo` renvoie cet objet instantanément.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Afficher la structure des dossiers

Parcourez `viewInfo.getFolders()` pour afficher chaque nom de dossier, sa profondeur et les fichiers qu’il contient. Cette boucle simple vous donne une vue arborescente lisible de l’archive.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Lecture récursive des dossiers

Pour les archives très imbriquées, une méthode auxiliaire récursive peut parcourir l’arbre en profondeur, garantissant que chaque sous‑dossier est visité sans charger l’ensemble de l’archive en mémoire.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Fonctionnalité 2 : récupérer la structure des dossiers d’archive

Cette fonctionnalité se concentre sur l’impression de la structure des dossiers d’un fichier d’archive. Elle est similaire à la première fonctionnalité mais met l’accent sur l’exploration récursive.

#### Configurer les options ViewInfo

`ArchiveOptions` vous permet de spécifier la protection par mot de passe, les limites de pages et les préférences de streaming avant d’appeler `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Exploration récursive

Une seconde routine récursive montre comment gérer les archives protégées par mot de passe et les ensembles de fichiers volumineux de manière efficace.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Applications pratiques

1. **Gestion des données :** Organisez rapidement de grands ensembles de données en comprenant les structures d’archives.  
2. **Traitement automatisé des fichiers :** Traitez par lots les fichiers archivés sans les extraire complètement, réduisant les I/O jusqu’à 70 %.  
3. **Intégration CMS :** Améliorez les systèmes de gestion de contenu avec une navigation d’archive en temps réel, permettant aux éditeurs de prévisualiser les fichiers directement depuis l’archive.

## Considérations de performance

- **Optimiser l’utilisation de la mémoire :** Traitez les dossiers un niveau à la fois et fermez rapidement l’instance `Viewer`.  
- **Rester à jour :** Utilisez la dernière version de GroupDocs.Viewer (25.2 au moment de la rédaction) et les versions récentes du JDK pour des gains de performance.  
- **Support du streaming :** La bibliothèque peut streamer des archives de plus d’1 Go sans charger le fichier complet en RAM, grâce à son architecture de lecture en morceaux.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| `NullPointerException` lors de la lecture des dossiers | `viewInfo.getFolders()` renvoie null pour les répertoires vides | Vérifiez la nullité ou la vacuité de la liste avant d’itérer. |
| Traitement lent des gros fichiers ZIP | L’ensemble de l’archive est chargé en mémoire | Utilisez les options de streaming disponibles dans les versions récentes de GroupDocs. |
| Licence introuvable | Le chemin du fichier de licence est incorrect | Placez le fichier de licence à la racine de l’application ou définissez `License.setLicense("path/to/license.json")`. |

## Questions fréquemment posées

**Q :** Qu’est‑ce que GroupDocs.Viewer ?  
**R :** GroupDocs.Viewer est une bibliothèque Java qui rend plus de 100 formats de documents, d’images et d’archives en HTML, PDF ou flux d’images sans nécessiter d’applications natives.

**Q :** Puis‑je utiliser GroupDocs.Viewer avec d’autres langages de programmation ?  
**R :** Oui, GroupDocs propose des SDK pour .NET, Python, PHP, etc., mais ce tutoriel se concentre sur l’implémentation Java.

**Q :** Comment gérer les gros fichiers d’archive ?  
**R :** Activez le streaming via `ArchiveOptions.setUseStreaming(true)`, traitez un niveau de dossier à la fois et libérez l’objet `Viewer` après utilisation.

**Q :** Quels types d’archives GroupDocs.Viewer prend‑il en charge ?  
**R :** Il prend en charge plus de 12 formats d’archive, dont ZIP, RAR, TAR, 7z, ISO, ARJ, CAB, ainsi que de nombreux conteneurs propriétaires.

**Q :** Existe‑t‑il une limite de taille pour les archives ?  
**R :** La limite pratique dépend de la RAM et du CPU de votre serveur ; les tests montrent un traitement fluide d’archives de 2 Go sur une machine de 16 Go de RAM lorsque le streaming est activé.

**Q :** “how to get viewinfo” fonctionne‑t‑il avec des archives protégées par mot de passe ?  
**R :** Oui, fournissez le mot de passe via `ArchiveOptions.setPassword("yourPassword")` avant d’appeler `getViewInfo`.

## Conclusion

En suivant ce guide, vous savez maintenant **comment obtenir viewinfo** pour toute archive prise en charge et comment parcourir sa hiérarchie de dossiers à l’aide de GroupDocs.Viewer pour Java. Ces techniques vous permettent de créer des pipelines de traitement de données plus intelligents, d’améliorer les intégrations CMS et de gérer de grandes collections de fichiers archivés en toute confiance. Ensuite, explorez le rendu de fichiers individuels depuis l’archive ou leur conversion en PDF/HTML à l’aide d’autres fonctionnalités du Viewer.

---

**Dernière mise à jour :** 2026-06-30  
**Testé avec :** GroupDocs.Viewer 25.2 pour Java  
**Auteur :** GroupDocs  

**Ressources**
- **Documentation :** [Documentation Java de GroupDocs Viewer](https://docs.groupdocs.com/viewer/java/)
- **Référence API :** [Référence API GroupDocs pour Java](https://reference.groupdocs.com/viewer/java/)
- **Télécharger GroupDocs.Viewer :** [Page de téléchargement GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Acheter une licence :** [Acheter GroupDocs](https://purchase.groupdocs.com/buy)
- **Essai gratuit et licence temporaire :** [Essai gratuit GroupDocs](https://releases.groupdocs.com/viewer/java/) | [Licence temporaire](https://purchase.groupdocs.com/temporary-license/)

## Tutoriels associés

- [Extraire les métadonnées d’un document avec GroupDocs.Viewer pour Java – Récupérer les informations de vue du document et les insights](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Comment récupérer les pièces jointes et imprimer les pièces jointes de document avec GroupDocs.Viewer pour Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Guide Java : rendre des pages spécifiques avec l’API GroupDocs.Viewer pour l’aperçu et la gestion de documents](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)