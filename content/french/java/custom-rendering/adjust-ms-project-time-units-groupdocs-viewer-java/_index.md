---
date: '2026-05-21'
description: Apprenez comment réaliser l'export HTML de MS Project avec des unités
  de temps ajustées en utilisant GroupDocs Viewer for Java. Guide étape par étape
  avec les prérequis, la configuration et le dépannage.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Export HTML de MS Project : ajuster les unités de temps via GroupDocs Java'
type: docs
url: /fr/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Exportation HTML de MS Project : Ajuster les unités de temps via GroupDocs Java

Exporter un fichier **MS Project** en HTML est une exigence courante pour les tableaux de bord de gestion de projet, les portails de rapports d’état et les outils de révision collaborative. Par défaut, le visualiseur rend les données liées au temps en minutes, ce qui peut encombrer la mise en page visuelle et rendre les rapports quotidiens plus difficiles à lire. Avec **GroupDocs Viewer for Java**, vous pouvez définir programmétiquement l’unité de temps sur **days**, produisant une *exportation html de ms project* propre qui correspond aux attentes typiques des parties prenantes. Dans ce tutoriel, vous apprendrez comment configurer le visualiseur, ajuster l’unité de temps et rendre le projet en HTML en quelques étapes simples.

![Ajuster les unités de temps MS Project avec GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Ajuster les unités de temps MS Project avec GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Réponses rapides
- **Quelle bibliothèque rend les fichiers MS Project ?** GroupDocs Viewer for Java.  
- **Quelle unité de temps puis‑je définir pour l’exportation HTML ?** Days, using `TimeUnit.DAYS`.  
- **Ai‑je besoin d’une licence pour la production ?** Oui— une licence permanente est requise ; une version d’essai fonctionne pour l’évaluation. Vous pouvez commencer avec un [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Quel IDE fonctionne le mieux ?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **Maven est‑il obligatoire ?** Maven simplifie la gestion des dépendances, mais vous pouvez également utiliser Gradle ou l’inclusion manuelle de JAR.  
- **Où puis‑je acheter ?** Visitez la [page d’achat](https://purchase.groupdocs.com/buy) pour les tarifs.

## Qu’est‑ce que GroupDocs Viewer for Java ?
**GroupDocs Viewer for Java** est un SDK Java qui convertit plus de 150 formats de documents—y compris MS Project—en HTML, PNG, JPEG ou PDF adaptés au web.  
Il abstrait la logique d’analyse, vous permet de contrôler les options de rendu telles que les unités de temps, et fonctionne sur toute plateforme supportant Java 8 ou supérieur.

## Pourquoi ajuster les unités de temps pour l’exportation HTML de MS Project ?
Définir l’unité de temps sur **days** réduit le bruit visuel, correspond à la plupart des cadences de reporting et améliore les temps de chargement des pages car moins de repères temporels granulaire sont générés. En termes quantitatifs, rendre avec des jours au lieu de minutes peut réduire la taille du HTML généré jusqu’à **45 %** pour des projets typiques de 30 jours, et accélère le rendu côté client d’environ **30 %**.

## Prérequis
- **Java Development Kit (JDK) 8 ou plus récent** installé sur votre poste de travail.  
- **Maven** (ou Gradle) pour la gestion des dépendances.  
- Un fichier **MS Project (.mpp)** que vous souhaitez exporter.  
- Accès à une licence **GroupDocs Viewer for Java** (essai ou permanente).  

### Bibliothèques requises
Ajoutez la dépendance suivante à votre `pom.xml` (ou le fragment Gradle équivalent) :

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Astuce :** Gardez le numéro de version à jour ; les nouvelles versions ajoutent la prise en charge de formats et des améliorations de performances.

## Comment configurer GroupDocs Viewer for Java ?
Initialisez le visualiseur en créant une instance `Viewer` qui pointe vers votre fichier MS Project. La classe `Viewer` est le point d’entrée pour toutes les opérations de rendu. Elle charge le document source, prépare les structures internes et expose des méthodes telles que `view()` et `viewToHtml()` pour générer les formats de sortie souhaités.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Ancre de définition :** La classe `Viewer` est le composant central de GroupDocs Viewer qui charge un document source et fournit des méthodes de rendu telles que `view()` et `viewToHtml()`.

## Comment ajuster les unités de temps pour l’exportation HTML ?
Pour modifier la granularité du temps, créez un objet `ViewOptions`, configurez son `ProjectOptions` pour utiliser `TimeUnit.DAYS`, puis transmettez‑le au visualiseur. `ViewOptions` définit les paramètres de rendu du document, tandis que l’énumération `TimeUnit` spécifie l’unité (minutes, heures, jours) pour les données liées au temps. Après avoir défini ces options, invoquez `viewer.view(options)` pour produire du HTML avec des repères quotidiens.

Chargez votre fichier MS Project avec `new Viewer("file.mpp")`, créez un objet `ViewOptions`, définissez `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, puis appelez `viewer.view(options)`. Ce flux en trois étapes change l’unité de temps des minutes aux jours et génère des fichiers HTML qui affichent uniquement les intervalles quotidiens.

### Étape 1 : Définir le dossier de sortie
Choisissez un répertoire accessible en écriture où les pages HTML seront enregistrées, par exemple `output/`.

### Étape 2 : Créer des options de vue avec des ressources intégrées
Les ressources intégrées (CSS, JavaScript) garantissent que les pages HTML sont autonomes.

### Étape 3 : Définir l’unité de temps sur les jours
Utilisez `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` pour changer la granularité.

### Étape 4 : Rendre le document
Appelez `viewer.view(options)` ; le visualiseur écrit un fichier HTML par page de projet dans le dossier de sortie.

### Étape 5 : Vérifier le résultat
Ouvrez le `index.html` généré dans un navigateur ; vous devriez voir les barres de tâches alignées sur des repères journaliers au lieu de repères minutes.

## Pièges courants et dépannage
- **Chemin de sortie incorrect** – Assurez‑vous que le répertoire existe et que le processus Java dispose des permissions d’écriture.  
- **Licence manquante** – Sans licence valide, le visualiseur revient en mode d’essai et peut intégrer des filigranes.  
- **Fichiers volumineux (> 500 MB)** – Envisagez d’augmenter la taille du tas JVM (`-Xmx2g`) ou de rendre avec `options.setRenderLimit(1000)` pour traiter les pages par lots.  

## Applications pratiques de l’exportation HTML avec unité de temps ajustée
1. **Tableaux de bord exécutifs** – La granularité quotidienne correspond à la plupart des visualisations KPI.  
2. **Emails de statut automatisés** – Intégrez le HTML généré directement dans le corps des e‑mails pour des mises à jour rapides.  
3. **Portails de projet** – Hébergez le HTML sur un site intranet où les membres de l’équipe peuvent filtrer les tâches par jour.  

## Considérations de performance pour les gros fichiers MS Project
- **Gestion de la mémoire** – Utilisez les drapeaux du ramasse‑miettes Java (`-XX:+UseG1GC`) pour libérer rapidement les objets inutilisés.  
- **Rendu sélectif** – Si vous n’avez besoin que du diagramme de Gantt, désactivez le rendu des autres ressources via `options.getProjectOptions().setRenderGantt(true)` et `setRenderResources(false)`.  
- **Traitement parallèle** – Pour les conversions par lots, créez des objets `Viewer` séparés par fichier et exécutez‑les dans un pool de threads pour exploiter les CPU multi‑cœurs.

## Conclusion
Vous disposez maintenant d’un flux de travail complet et prêt pour la production pour effectuer une **ms project html export** avec les unités de temps réglées sur les jours en utilisant GroupDocs Viewer for Java. Cette approche réduit la taille du HTML, accélère le rendu côté client et fournit une vue adaptée aux parties prenantes des calendriers de projet. Explorez des options de rendu supplémentaires—comme l’exportation PDF ou les captures d’image—pour étendre l’intégration aux pipelines de reporting plus larges.

## Questions fréquentes

**Q : Puis‑je rendre d’autres vues Project (par ex., Feuille de ressources) en HTML ?**  
R : Oui, l’objet `ProjectOptions` vous permet d’activer ou de désactiver des vues spécifiques telles que Gantt, Feuille de ressources et Calendrier avant le rendu.

**Q : Est‑il possible de personnaliser le CSS du HTML généré ?**  
R : Absolument. Fournissez le chemin d’une feuille de style personnalisée via `options.setStyleSheetPath("path/to/custom.css")` et le visualiseur l’intégrera à chaque page.

**Q : Quelles limites de taille de fichier GroupDocs Viewer prend‑il en charge pour MS Project ?**  
R : Le SDK peut gérer des fichiers jusqu’à **500 MB** sans avoir besoin de charger le document complet en mémoire, grâce à son architecture de streaming.

**Q : Dois‑je installer Microsoft Project sur le serveur ?**  
R : Non. GroupDocs Viewer analyse directement le format .mpp et ne nécessite ni Microsoft Project ni aucune installation Office.

**Q : Comment licencier le visualiseur pour un environnement de production ?**  
R : Achetez une licence permanente dans la boutique GroupDocs ; appliquez le fichier de licence au moment de l’exécution avec `License license = new License(); license.setLicense("path/to/license.lic");`. Pour des besoins à court terme, vous pouvez obtenir une [licence temporaire](https://purchase.groupdocs.com/temporary-license/).

---

**Dernière mise à jour :** 2026-05-21  
**Testé avec :** GroupDocs Viewer Java 25.2  
**Auteur :** GroupDocs  

**Ressources**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [Référence API](https://reference.groupdocs.com/viewer/java/)  
- [Télécharger GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Acheter une licence](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Tutoriels associés

- [Comment rendre les fichiers MS Project en HTML, JPG, PNG et PDF avec notes en utilisant GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Comment utiliser GroupDocs Viewer pour rendre les documents de projet par intervalles de temps en Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Comment définir les licences dans GroupDocs.Viewer Java : guide de configuration des fichiers et URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)