---
date: '2026-03-29'
description: Apprenez à faire pivoter une page de 90 degrés en Java avec GroupDocs
  Viewer, incluant la configuration, le code et les conseils de performance.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Faire pivoter la page de 90 degrés avec GroupDocs Viewer pour Java
type: docs
url: /fr/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Faire pivoter la page de 90 degrés avec GroupDocs Viewer pour Java

Lorsque vous devez **faire pivoter une page de 90 degrés** dans un document—qu’il s’agisse d’un PDF, d’un fichier Word ou d’une feuille de calcul—le faire de manière programmatique fait gagner du temps et élimine les erreurs manuelles. Dans ce guide avancé, nous parcourrons les étapes exactes pour faire pivoter la première page de tout document pris en charge en utilisant **GroupDocs Viewer pour Java**. À la fin, vous disposerez d’un extrait réutilisable que vous pourrez intégrer à vos propres projets.  
Nous aborderons également pourquoi la rotation des pages en Java est importante, les scénarios courants où cette technique brille, et comment garder l’opération légère.

![Faire pivoter la première page d’un document avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Réponses rapides
- **Que signifie « faire pivoter la page de 90 degrés » ?** Cela tourne la page sélectionnée dans le sens des aiguilles d’une montre d’un quart de tour.  
- **Quelle bibliothèque gère la rotation ?** GroupDocs Viewer pour Java fournit la méthode `rotatePage`.  
- **Puis-je faire pivoter des pages PDF avec Java ?** Oui—utilisez le même appel `rotatePage` ; cela fonctionne pour PDF, DOCX, XLSX, et plus encore.  
- **Ai-je besoin d’une licence ?** Un essai gratuit fonctionne pour le développement ; une licence payante est requise pour la production.  
- **L’opération est‑elle gourmande en mémoire ?** Pas lorsque vous fermez rapidement l’instance `Viewer` ; consultez les conseils de performance ci‑dessous.

## Qu’est‑ce que « faire pivoter la page de 90 degrés » ?
Faire pivoter une page de 90 degrés réoriente la page du portrait au paysage (ou inversement) sans modifier le contenu sous‑jacent. C’est particulièrement pratique pour les présentations, l’impression de graphiques uniquement en paysage, ou la correction de documents numérisés qui ont été capturés de travers.

## Pourquoi faire pivoter les pages de manière programmatique avec GroupDocs Viewer pour Java ?
GroupDocs Viewer abstrait les complexités de la gestion de dizaines de formats de fichiers. Il vous permet d’appliquer des transformations au niveau de la page—comme la rotation—tout en conservant le fichier original intact. L’API est fluide, thread‑safe, et fonctionne sur n’importe quel runtime Java 8+, ce qui en fait un choix fiable pour l’automatisation de niveau entreprise.

## Prérequis
- **GroupDocs.Viewer pour Java** (dernière version)
- **JDK 8** ou plus récent
- **Maven** (ou Gradle) pour la gestion des dépendances
- Un IDE tel qu’IntelliJ IDEA ou Eclipse
- Familiarité de base avec Java I/O

## Configurer GroupDocs.Viewer pour Java
Ajoutez le dépôt GroupDocs et la dépendance à votre `pom.xml`. Cet extrait est identique à celui du tutoriel original :

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

### Obtention de licence
- **Essai gratuit** – téléchargez depuis le site GroupDocs.  
- **Licence temporaire** – demandez-la si vous avez besoin d’une période d’évaluation prolongée.  
- **Licence complète** – achetez-la pour les déploiements en production.

### Initialisation de base du Viewer
Le code suivant montre la façon minimale de créer une instance `Viewer`. Conservez-le exactement tel quel :

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Comment faire pivoter une page PDF en Java avec GroupDocs Viewer
Même si l’API fonctionne avec de nombreux formats, le PDF est le cas d’utilisation le plus courant pour la rotation de page. La même méthode `rotatePage` est utilisée, il suffit donc d’indiquer au viewer un fichier PDF et de spécifier le numéro de page.

## Implémentation étape par étape : faire pivoter la première page de 90 degrés

### 1. Importer les packages requis
Ces imports vous donnent accès aux options de rendu PDF et à l’énumération de rotation.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Définir les emplacements de sortie et créer le Viewer
Remplacez les chemins de substitution par vos répertoires réels.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Configurer les options d’affichage PDF et appliquer la rotation
La méthode `rotatePage` prend le numéro de page (indexé à partir de 1) et une valeur d’énumération `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Rendre le document
Enfin, appelez `view` pour générer le PDF pivoté.

```java
viewer.view(viewOptions);
```

#### Comment ça fonctionne
- **PdfViewOptions** indique au Viewer de produire un fichier PDF.  
- **rotatePage(int, Rotation)** fait pivoter uniquement la page que vous spécifiez, laissant le reste intact.  
- La méthode prend en charge `ON_90_DEGREE`, `ON_180_DEGREE` et `ON_270_DEGREE`.

## Problèmes courants et solutions

| Symptôme | Cause probable | Solution |
|----------|----------------|----------|
| **FileNotFoundException** | Chemin incorrect ou dossier manquant | Vérifiez que `YOUR_OUTPUT_DIRECTORY` et `YOUR_DOCUMENT_DIRECTORY` existent et sont lisibles. |
| **Unsupported file format** | Tentative de rotation d’un format non pris en charge par le Viewer | Consultez la page [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Utilisation du mauvais numéro de page (indexé à partir de 0) | Rappelez‑vous que `rotatePage` utilise un index **à partir de 1**. |
| **Out‑of‑memory errors on large docs** | Rendu de nombreux gros fichiers dans un seul thread | Traitez les documents séquentiellement ou utilisez un pool de threads avec une concurrence limitée. |

## Applications pratiques
1. **Ajustements de présentation** – Convertir une diapositive portrait en paysage à la volée.  
2. **Correction massive de documents** – Automatiser la correction de PDFs numérisés qui ont été capturés de travers.  
3. **Sortie prête à imprimer** – Garantir que les graphiques en paysage s’impriment correctement sur du papier orienté portrait.

## Conseils de performance
- **Fermer les ressources rapidement** – Le bloc `try‑with‑resources` libère automatiquement le `Viewer`.  
- **Traitement par lots** – Lors du traitement de nombreux fichiers, réutilisez une seule instance `Viewer` par thread pour réduire la surcharge.  
- **Surveiller la mémoire** – Pour les documents de plus de 100 Mo, envisagez de diffuser la sortie vers le disque plutôt que de la garder en mémoire.

## Questions fréquentes

**Q : Puis-je faire pivoter plusieurs pages à la fois ?**  
A : Oui—appelez `rotatePage()` pour chaque numéro de page que vous devez faire pivoter.

**Q : Existe‑t‑il un moyen d’annuler la rotation après le rendu ?**  
A : Pas directement. Vous devrez rendre le document à nouveau sans les options de rotation.

**Q : Quels formats de fichier prennent en charge la rotation de page dans GroupDocs Viewer ?**  
A : DOCX, PDF, PPTX, XLSX, et de nombreux autres formats listés dans la documentation officielle.

**Q : Comment puis‑je faire pivoter les pages d’un lot de documents automatiquement ?**  
A : Enveloppez le code dans une boucle qui itère sur une collection de chemins de fichiers, en appliquant la même logique `rotatePage` à chacun.

**Q : Quelle est la meilleure pratique pour gérer les erreurs lors de la rotation ?**  
A : Encapsulez l’utilisation du Viewer dans un bloc `try‑catch`, consignez l’exception, et éventuellement continuez le traitement du fichier suivant.

## Ressources
- **Documentation** : [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Référence API** : [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Téléchargement** : [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Achat** : [Buy a License](https://purchase.groupdocs.com/buy)  
- **Essai gratuit** : [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licence temporaire** : [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Support** : [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Dernière mise à jour :** 2026-03-29  
**Testé avec :** GroupDocs Viewer 25.2 for Java  
**Auteur :** GroupDocs