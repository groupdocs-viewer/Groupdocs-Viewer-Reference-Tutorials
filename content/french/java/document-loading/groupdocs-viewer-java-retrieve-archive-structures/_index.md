---
date: '2026-02-05'
description: Apprenez comment obtenir viewinfo et récupérer les structures de type
  fichier d’archive Java en utilisant GroupDocs.Viewer. Ce guide couvre la configuration,
  des exemples de code et des cas d’utilisation réels.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Comment obtenir ViewInfo et récupérer les structures d’archive en Java
type: docs
url: /fr/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Comment obtenir ViewInfo et récupérer les structures d'archive en Java

Gérer efficacement les fichiers d'archive nécessite une compréhension claire de leur structure. Dans ce tutoriel, vous apprendrez **comment obtenir viewinfo** pour n'importe quelle archive et verrez comment cela vous aide à travailler avec le **type de fichier d'archive java**. Nous parcourrons la configuration de GroupDocs.Viewer, l'extraction des informations de vue, et la lecture récursive des hiérarchies de dossiers afin que vous puissiez intégrer la solution dans des projets réels.

![Structures d'archive avec GroupDocs.Viewer pour Java](/viewer/document-loading/archive-structures-java.png)

**Ce que vous apprendrez**
- Configurer et paramétrer GroupDocs.Viewer pour Java.  
- Méthodes pour **obtenir viewinfo** à partir des archives.  
- Techniques pour lire et afficher la structure de dossiers d'un fichier d'archive.  
- Applications pratiques et considérations de performance lors de l'utilisation de GroupDocs.Viewer dans des projets Java.

## Réponses rapides
- **Que fournit “viewinfo” ?** Elle renvoie le type de fichier, le nombre de pages et la liste des dossiers de l'archive.  
- **Quelles archives sont prises en charge ?** ZIP, RAR, TAR et d'autres formats courants.  
- **Ai-je besoin d'une licence ?** Un essai gratuit suffit pour l'évaluation ; une licence commerciale est requise pour la production.  
- **Puis-je traiter de grandes archives ?** Oui – utilisez le streaming et une gestion appropriée de la mémoire comme indiqué plus loin.  
- **Maven est-il requis ?** Maven est la méthode recommandée pour gérer la dépendance GroupDocs.Viewer.

## Qu’est‑ce que “how to get viewinfo” ?
`getViewInfo` est une méthode de l'API GroupDocs.Viewer qui extrait les métadonnées d'un document ou d'une archive sans rendre le contenu complet. Pour les archives, elle révèle l'arborescence interne des dossiers, vous permettant de décider quelles parties rendre ou traiter davantage.

## Pourquoi récupérer les structures de type de fichier d'archive Java ?
Comprendre la disposition interne d’un **type de fichier d'archive java** (par ex., ZIP, RAR) vous permet de :
- Localiser rapidement les fichiers nécessaires sans tout extraire.  
- Construire des pipelines automatisés qui ne traitent que les sous‑dossiers pertinents.  
- Intégrer la navigation d'archive dans les systèmes de gestion de contenu ou d’ingestion de données.

## Prérequis

- **Java Development Kit (JDK) :** Version 8 ou supérieure.  
- **Maven :** Pour la gestion des dépendances et les builds.  
- **Connaissances de base en Java :** La familiarité avec les concepts de POO aide mais n’est pas obligatoire.

Vous avez également besoin d’accéder à la bibliothèque GroupDocs.Viewer, que vous pouvez ajouter à votre projet Maven comme indiqué ci‑dessous.

## Configuration de GroupDocs.Viewer pour Java

### Maven Configuration

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

- **Essai gratuit :** Téléchargez une version d'essai depuis le site Web de GroupDocs.  
- **Licence temporaire :** Demandez une clé temporaire pour une évaluation à court terme.  
- **Licence complète :** Achetez une licence commerciale pour une utilisation en production illimitée.

Une fois la bibliothèque sur votre classpath, vous pouvez commencer à coder.

## Guide d'implémentation

### Comment obtenir ViewInfo pour les fichiers d'archive

Cette section montre les étapes exactes pour appeler `getViewInfo` et lire la hiérarchie des dossiers.

#### Initialiser le Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Récupérer les informations de vue

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Afficher la structure des dossiers

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Lecture récursive des dossiers

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

### Fonctionnalité 2 : Récupérer la structure des dossiers d'archive

Cette fonctionnalité se concentre sur l'affichage de la structure des dossiers d'un fichier d'archive. Elle est similaire à la première fonctionnalité mais met l'accent sur l'exploration récursive.

#### Configurer les options ViewInfo

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Exploration récursive

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Applications pratiques

1. **Gestion des données :** Organisez rapidement de grands ensembles de données en comprenant les structures d'archive.  
2. **Traitement automatisé de fichiers :** Traitez par lots les fichiers archivés sans les extraire entièrement.  
3. **Intégration CMS :** Améliorez les systèmes de gestion de contenu avec une navigation d'archive à la volée.

## Considérations de performance

- **Optimiser l'utilisation de la mémoire :** Traitez les dossiers un niveau à la fois et fermez rapidement l'instance `Viewer`.  
- **Restez à jour :** Utilisez la dernière version de GroupDocs.Viewer et les versions récentes du JDK pour améliorer les performances.

## Problèmes courants et solutions

| Problème | Pourquoi cela se produit | Solution |
|----------|--------------------------|----------|
| `NullPointerException` lors de la lecture des dossiers | `viewInfo.getFolders()` renvoie null pour les répertoires vides | Vérifiez la nullité ou la vacuité de la liste avant d'itérer. |
| Traitement lent de gros fichiers ZIP | L'archive entière est chargée en mémoire | Utilisez les options de streaming disponibles dans les versions plus récentes de GroupDocs. |
| Licence non trouvée | Le chemin du fichier de licence est incorrect | Placez le fichier de licence à la racine de l'application ou définissez `License.setLicense("path/to/license.json")`. |

## Questions fréquentes

**Q : Qu’est‑ce que GroupDocs.Viewer ?**  
R : C’est une puissante bibliothèque Java pour rendre les documents, y compris les archives, sous des formats tels que HTML, image et PDF.

**Q : Puis‑je utiliser GroupDocs.Viewer avec d’autres langages de programmation ?**  
R : Oui, GroupDocs propose des SDK pour plusieurs plateformes, mais ce tutoriel se concentre sur l’implémentation Java.

**Q : Comment gérer les gros fichiers d'archive ?**  
R : Utilisez des pratiques de gestion efficace de la mémoire et envisagez de diviser les archives si nécessaire.

**Q : Quels types d'archives GroupDocs.Viewer prend‑il en charge ?**  
R : Il prend en charge divers formats dont ZIP, RAR, TAR, entre autres.

**Q : Existe‑t‑il une limite de taille pour les archives que je peux traiter ?**  
R : Les limites dépendent des ressources de votre système. Testez dans votre environnement cible pour déterminer les limites pratiques.

**Q : “how to get viewinfo” fonctionne‑t‑il avec des archives protégées par mot de passe ?**  
R : Oui, vous pouvez fournir le mot de passe via `ArchiveOptions.setPassword("yourPassword")` avant d’appeler `getViewInfo`.

## Conclusion

En suivant ce guide, vous savez maintenant **comment obtenir viewinfo** pour toute archive prise en charge et comment parcourir sa hiérarchie de dossiers à l’aide de GroupDocs.Viewer pour Java. Ces techniques vous permettent de créer des pipelines de traitement de données plus intelligents, d’améliorer les intégrations CMS et de gérer de grandes collections de fichiers archivés avec confiance. Ensuite, explorez le rendu de fichiers individuels depuis l'archive ou leur conversion en PDF/HTML à l’aide d’autres fonctionnalités du Viewer.

---

**Last Updated:** 2026-02-05  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Resources**
- **Documentation :** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Référence API :** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Télécharger GroupDocs.Viewer :** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Acheter une licence :** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Essai gratuit et licence temporaire :** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)