---
date: '2026-09-25'
description: Apprenez à créer html view mpp avec GroupDocs Viewer for Java, rendering
  les documents de projet par intervalles de temps avec du code step‑by‑step.
keywords:
- create html view mpp
- set start end date
- GroupDocs Viewer Java
- render project documents
lastmod: '2026-09-25'
og_description: Créer html view mpp avec GroupDocs Viewer for Java pour render Microsoft
  Project files par intervalles de temps spécifiques. Suivez le setup step‑by‑step,
  licensing, et code snippets pour une visualisation précise du timeline.
og_image_alt: 'GroupDocs Viewer Java example: rendering project documents to HTML
  by time interval'
og_title: Créer html view mpp avec GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-25'
  description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  headline: Create html view mpp with GroupDocs Viewer (Java)
  type: TechArticle
- description: Learn how to create html view mpp with GroupDocs Viewer for Java, rendering
    project documents by time intervals with step‑by‑step code.
  name: Create html view mpp with GroupDocs Viewer (Java)
  steps:
  - name: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
    text: '**Free trial** – Download a trial version from [GroupDocs'' download page](https://releases.groupdocs.com/viewer/java/).'
  - name: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
    text: '**Temporary license** – Obtain a temporary license for extended testing
      via the [temporary‑license page](https://purchase.groupdocs.com/temporary-license/).'
  - name: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
    text: '**Purchase** – For unrestricted production use, buy a license at the [GroupDocs
      Purchase Page](https://purchase.groupdocs.com/buy).'
  - name: '**Project timeline analysis** – Show stakeholders only the current phase.'
    text: '**Project timeline analysis** – Show stakeholders only the current phase.'
  - name: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
    text: '**Automated reporting** – Generate time‑bound HTML reports for weekly status
      updates.'
  - name: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
    text: '**Integration with dashboards** – Embed the rendered pages into BI tools
      or custom portals.'
  - name: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
    text: '**Archival** – Store a web‑friendly snapshot of a project’s schedule for
      future reference.'
  type: HowTo
- questions:
  - answer: GroupDocs.Viewer supports 100+ input formats, including PDF, DOCX, XLSX,
      PPTX, and Microsoft Project files, enabling universal document visualization.
    question: What file formats does GroupDocs.Viewer support?
  - answer: You can download the trial version from the [GroupDocs Viewer Java download
      page](https://releases.groupdocs.com/viewer/java/).
    question: How do I get started with a free trial of GroupDocs.Viewer?
  - answer: Yes, you can choose a different HTML view option that references external
      resources instead of embedding them.
    question: Can I render documents without embedding resources?
  - answer: Consider splitting the document into smaller sections or rendering only
      the required date range, as demonstrated above.
    question: What if my document is too large for rendering?
  - answer: Verify all configuration settings, ensure you have a valid license, and
      consult the GroupDocs documentation for detailed error codes.
    question: How do I handle rendering errors?
  type: FAQPage
tags:
- render project documents
- GroupDocs Viewer
- Java rendering
- project timeline
- html view mpp
title: Créer html view mpp avec GroupDocs Viewer (Java)
type: docs
url: /fr/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Comment utiliser GroupDocs Viewer pour rendre les documents de projet par intervalles de temps en Java

Dans ce tutoriel, vous apprendrez comment **create html view mpp** avec GroupDocs Viewer pour Java, vous permettant de rendre uniquement les parties d'un fichier Microsoft Project qui se situent dans une plage de dates de début et de fin spécifique. Nous parcourrons la configuration Maven, la licence, et les appels d'API exacts dont vous avez besoin pour intégrer des vues de chronologie précises directement dans vos applications.

![Rendu des documents de projet par intervalles de temps avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

Pour un aperçu, voir le [Rendu des documents de projet par intervalles de temps avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png).

## Réponses rapides
- **Que fait la fonctionnalité ?** Elle rend uniquement la partie d'un fichier Microsoft Project qui se situe entre une date de début et une date de fin.  
- **Quel format de sortie est utilisé ?** HTML avec ressources intégrées, parfait pour l'intégration web.  
- **Ai-je besoin d'une licence ?** Un essai gratuit fonctionne pour l'évaluation ; une licence complète est requise pour la production.  
- **Puis-je modifier la plage de dates à l'exécution ?** Oui — ajustez les valeurs `setStartDate` et `setEndDate` dans les options de rendu.  
- **Cette fonctionnalité est-elle prise en charge sur toutes les versions de Java ?** Fonctionne avec Java 8+ tant que vous utilisez GroupDocs.Viewer 25.2 ou une version plus récente.

## Qu'est-ce que create html view mpp ?
`create html view mpp` est le processus de conversion d'un fichier Microsoft Project (`.mpp` ou `.mpt`) en un ensemble de pages HTML qui représentent le planning. GroupDocs Viewer effectue la conversion côté serveur, vous permettant d'afficher la chronologie dans n'importe quel navigateur sans installer Microsoft Project.

## Pourquoi rendre les documents de projet avec des intervalles de temps ?
Rendre uniquement l'intervalle de temps requis réduit la taille du HTML généré, accélère le chargement des pages et vous permet de vous concentrer sur la phase de projet spécifique que vous devez analyser. Cette vue ciblée est idéale pour les tableaux de bord, les rapports d'état ou l'intégration dans des outils de gestion de projet personnalisés où les données du projet complet seraient écrasantes.

## Prérequis
- **GroupDocs.Viewer for Java** version 25.2 ou supérieure.  
- Java Development Kit (JDK) 8 ou plus récent.  
- Un IDE tel qu'IntelliJ IDEA ou Eclipse.  
- Connaissances de base en Maven.  

## Configuration de GroupDocs.Viewer pour Java

### Dépendance Maven
Ajoutez le référentiel et la dépendance à votre `pom.xml` :

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

### Étapes d'obtention de licence
1. **Free trial** – Téléchargez une version d'essai depuis la [page de téléchargement de GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary license** – Obtenez une licence temporaire pour des tests prolongés via la [page de licence temporaire](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Pour une utilisation en production sans restriction, achetez une licence sur la [page d'achat de GroupDocs](https://purchase.groupdocs.com/buy).

## Initialisation de base du viewer
`Viewer` est la classe principale de GroupDocs.Viewer pour Java qui charge un document et fournit des capacités de rendu.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Récupérer les informations de vue pour les fichiers de projet
`ProjectManagementViewInfo` fournit des métadonnées sur un fichier Microsoft Project, y compris les dates de début et de fin du planning global.

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

## Configurer les options de rendu HTML (générer du HTML à partir du projet)
`HtmlViewOptions` configure la façon dont GroupDocs rend le HTML, vous permettant de définir la plage de dates, d'intégrer les ressources et de personnaliser l'apparence.

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

## Exécuter le processus de rendu
`viewer.render` exécute la conversion en fonction des options fournies et écrit les fichiers HTML résultants dans le dossier cible.

```java
viewer.view(viewOptions);
```

## Pièges courants et dépannage
- **Incorrect file paths** – Vérifiez que le fichier source `.mpp` et le répertoire de sortie existent.  
- **Unsupported file type** – Assurez-vous que le document est dans un format Project pris en charge (par ex., `.mpp`, `.mpt`).  
- **License errors** – Une licence d'essai peut imposer des limites de rendu ; passez à une licence complète pour une utilisation sans restriction.  

## Applications pratiques
1. **Project timeline analysis** – Montrez aux parties prenantes uniquement la phase actuelle.  
2. **Automated reporting** – Générez des rapports HTML limités dans le temps pour les mises à jour hebdomadaires.  
3. **Integration with dashboards** – Intégrez les pages rendues dans les outils BI ou les portails personnalisés.  
4. **Archival** – Conservez un instantané web‑compatible du planning du projet pour référence future.  

## Conseils de performance
- Utilisez l'option *embedded resources* pour que chaque page HTML soit autonome, réduisant ainsi les requêtes HTTP.  
- Pour les projets très volumineux, envisagez de rendre le projet par petits intervalles de dates afin de limiter l'utilisation de la mémoire. Rendre une tranche d'un an peut réduire la taille du HTML jusqu'à 80 % par rapport à une exportation du projet complet, diminuant le temps de chargement de plusieurs secondes à moins d'une seconde sur des serveurs typiques.  
- Nettoyez les fichiers temporaires après les avoir servis pour éviter l'encombrement du disque.  

## Conclusion
Vous savez maintenant **how to use GroupDocs** Viewer pour rendre les documents de projet dans un intervalle de temps spécifique et **generate HTML from project** data en Java. Cette capacité simplifie les visualisations de chronologie, améliore l'efficacité des rapports et s'intègre parfaitement aux applications web modernes.

### Prochaines étapes
- Explorez les fonctionnalités supplémentaires du Viewer telles que le filigrane, la protection par mot de passe ou la personnalisation du style CSS.  
- Combinez ce pipeline de rendu avec une API REST pour fournir des vues de chronologie à la demande.  

## Questions fréquemment posées
**Q: Quels formats de fichiers GroupDocs.Viewer prend‑il en charge ?**  
A: GroupDocs.Viewer prend en charge plus de 100 formats d'entrée, y compris PDF, DOCX, XLSX, PPTX et les fichiers Microsoft Project, permettant une visualisation universelle des documents.

**Q: Comment démarrer avec un essai gratuit de GroupDocs.Viewer ?**  
A: Vous pouvez télécharger la version d'essai depuis la [page de téléchargement de GroupDocs Viewer Java](https://releases.groupdocs.com/viewer/java/).

**Q: Puis-je rendre les documents sans intégrer les ressources ?**  
A: Oui, vous pouvez choisir une autre option de vue HTML qui référence des ressources externes au lieu de les intégrer.

**Q: Que faire si mon document est trop volumineux pour le rendu ?**  
A: Envisagez de diviser le document en sections plus petites ou de rendre uniquement la plage de dates requise, comme démontré ci‑dessus.

**Q: Comment gérer les erreurs de rendu ?**  
A: Vérifiez tous les paramètres de configuration, assurez‑vous de disposer d'une licence valide, et consultez la documentation GroupDocs pour les codes d'erreur détaillés.

## Ressources
- **Documentation** : [Documentation GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Référence API** : [Référence API GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Téléchargement** : [Téléchargements GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Achat** : [Acheter une licence GroupDocs](https://purchase.groupdocs.com/buy)
- **Essai gratuit** : [Essayer la version gratuite](https://releases.groupdocs.com/viewer/java/)
- **Licence temporaire** : [Obtenir une licence temporaire](https://purchase.groupdocs.com/temporary-license/)
- **Support** : [Forum GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Dernière mise à jour :** 2026-09-25  
**Testé avec :** GroupDocs.Viewer 25.2 for Java  
**Auteur :** GroupDocs  

---

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

## Tutoriels associés
- [Comment rendre les fichiers MS Project en HTML, JPG, PNG et PDF avec notes en utilisant GroupDocs.Viewer pour Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Export HTML MS Project : ajuster les unités de temps via GroupDocs Java](/viewer/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/)
- [Rendu HTML réactif Groupdocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)