---
categories:
- Java Development
date: '2026-08-19'
description: Apprenez à faire pivoter les pages PDF, à convertir le DOCX en HTML Java
  et à personnaliser la qualité d'image du PDF à l'aide de GroupDocs.Viewer pour Java.
  Comprend l'optimisation des performances et des conseils de rendu.
keywords:
- how to rotate pdf
- docx to html java
- java document viewer
- specific pdf page rotation
- customize pdf image quality
lastmod: '2026-08-19'
linktitle: Tutoriels avancés de rendu
og_description: Apprenez à faire pivoter les pages PDF et à convertir le DOCX en HTML
  Java avec GroupDocs.Viewer pour Java. Optimisez la qualité d'image et les performances
  dans vos applications Java.
og_image_alt: Guide showing rotation of specific PDF pages using GroupDocs.Viewer
  Java
og_title: Comment faire pivoter les pages PDF avec GroupDocs.Viewer Java – guide avancé
schemas:
- author: GroupDocs
  dateModified: '2026-08-19'
  description: Learn how to rotate pdf pages, convert docx to html java, and customize
    pdf image quality using GroupDocs.Viewer for Java. Includes performance tuning
    and rendering tips.
  headline: How to rotate pdf pages with GroupDocs.Viewer Java – advanced rendering
    guide
  type: TechArticle
- description: Learn how to rotate pdf pages, convert docx to html java, and customize
    pdf image quality using GroupDocs.Viewer for Java. Includes performance tuning
    and rendering tips.
  name: How to rotate pdf pages with GroupDocs.Viewer Java – advanced rendering guide
  steps:
  - name: '**Initialize the Viewer** – supply your license and create the `Viewer`
      object.'
    text: '**Initialize the Viewer** – supply your license and create the `Viewer`
      object.'
  - name: '**Load the DOCX file** – provide a `File` or `InputStream`.'
    text: '**Load the DOCX file** – provide a `File` or `InputStream`.'
  - name: '**Configure rendering options** – enable external resource handling, set
      image quality, and choose the output format.'
    text: '**Configure rendering options** – enable external resource handling, set
      image quality, and choose the output format.'
  - name: '**Execute the conversion** – invoke `viewer.render` with `HtmlOptions`.'
    text: '**Execute the conversion** – invoke `viewer.render` with `HtmlOptions`.'
  - name: '**Process the result** – save HTML files and any extracted resources to
      your desired location.'
    text: '**Process the result** – save HTML files and any extracted resources to
      your desired location.'
  - name: '**Create a PdfOptions object** – this holds all PDF‑specific settings.'
    text: '**Create a PdfOptions object** – this holds all PDF‑specific settings.'
  - name: '**Specify the pages to rotate** – use `setPages(Arrays.asList(2, 5, 7))`
      for pages 2, 5, 7.'
    text: '**Specify the pages to rotate** – use `setPages(Arrays.asList(2, 5, 7))`
      for pages 2, 5, 7.'
  - name: '**Set the rotation angle** – `setRotationAngle(RotationAngle.ROTATE_90)`
      rotates the selected pages 90°.'
    text: '**Set the rotation angle** – `setRotationAngle(RotationAngle.ROTATE_90)`
      rotates the selected pages 90°.'
  - name: '**Render the document** – `viewer.render(pdfFile, pdfOptions)` writes the
      rotated pages to the output folder.'
    text: '**Render the document** – `viewer.render(pdfFile, pdfOptions)` writes the
      rotated pages to the output folder.'
  type: HowTo
- questions:
  - answer: Yes. Initialize the `Viewer` bean with your license, then call `viewer.render`
      with `HtmlOptions` inside any service or controller.
    question: Can I use GroupDocs.Viewer to convert DOCX to HTML in a Spring Boot
      application?
  - answer: Use `PdfOptions` to enable page‑by‑page rendering and configure `setCacheFolder`
      to store intermediate results, reducing memory pressure.
    question: How does the library handle large PDFs when rendering to images?
  - answer: Absolutely. Set the `pages` collection in `RenderOptions` to the specific
      page numbers you need.
    question: Is it possible to render only selected pages of a document?
  - answer: DOCX, PPTX, XLSX, PDF, and many others are supported. Use `HtmlOptions.setResourcesPath`
      to control where images and CSS are saved.
    question: What formats can be rendered to HTML with embedded resources?
  - answer: Yes, but each `Viewer` instance should be used per thread or you should
      implement proper synchronization to avoid race conditions.
    question: Does GroupDocs.Viewer support multi‑threaded rendering?
  type: FAQPage
tags:
- rotate pdf
- GroupDocs Viewer
- Java document rendering
- pdf processing
title: Comment faire pivoter les pages PDF avec GroupDocs.Viewer Java – guide avancé
  de rendu
type: docs
url: /fr/java/advanced-rendering/
weight: 4
---

# Comment faire pivoter les pages pdf avec GroupDocs.Viewer Java – guide de rendu avancé

Dans ce tutoriel complet, vous découvrirez **comment faire pivoter les pages pdf** en utilisant GroupDocs.Viewer pour Java tout en maîtrisant des tâches connexes telles que la conversion de DOCX en HTML, la personnalisation de la qualité d'image PDF et le réglage fin des performances de rendu. Les exemples étape par étape ciblent les développeurs Java intermédiaires qui ont besoin d'un visionneur de documents fiable, prêt pour la production, capable de gérer de gros fichiers complexes sans sacrifier la vitesse.

![Rendu avancé de documents avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/img-java.png)

## Réponses rapides
- **Quel est le cas d'utilisation principal ?** Conversion de DOCX en HTML en Java tout en gérant les ressources externes et en faisant pivoter des pages PDF spécifiques.  
- **Quelle bibliothèque gère la conversion ?** GroupDocs.Viewer for Java fournit une API simple pour **convert docx to html java** efficacement.  
- **Ai-je besoin d'une licence ?** Une licence temporaire fonctionne pour l'évaluation ; une licence complète est requise pour la production.  
- **Puis-je rendre des fichiers PDF avec la même API ?** Oui – la bibliothèque prend également en charge les scénarios **render pdf images java**.  
- **Existe-t-il un réglage de performance intégré ?** Les tutoriels incluent la mise en cache, le rendu sélectif des pages et les ajustements de qualité d'image.

## Qu'est-ce que la rotation de pages pdf spécifiques ?
Faire pivoter des pages PDF spécifiques signifie changer l'orientation uniquement des pages choisies — par exemple, transformer une facture à l'envers en portrait — sans retraiter l'ensemble du document. Cela maintient une faible utilisation du CPU et de la mémoire, ce qui est essentiel pour les services à fort trafic. L'opération est effectuée pendant le rendu, de sorte que le fichier original reste inchangé et que seule la sortie reflète la nouvelle orientation.

## Pourquoi utiliser GroupDocs.Viewer Java pour le rendu avancé ?
GroupDocs.Viewer prend en charge **plus de 50 formats d'entrée et de sortie**, peut rendre des PDF de plusieurs centaines de pages sans charger le fichier complet en mémoire, et offre un contrôle au niveau de la page tel que la rotation, la gestion des calques et le rendu sélectif. Ces capacités quantifiées en font un choix de premier plan pour le traitement de documents de niveau entreprise.

## Prérequis
- Java 17 ou version ultérieure installé sur votre machine de développement.  
- Système de construction Maven ou Gradle pour gérer les dépendances.  
- Une licence valide de GroupDocs.Viewer pour Java (une licence temporaire fonctionne pour les tests).  
- Familiarité de base avec les classes `Viewer`, `PdfOptions` et `HtmlOptions`.

## Comment convertir docx en html java avec GroupDocs.Viewer

Chargez votre DOCX et rendez‑le en HTML en un seul appel.  
**Réponse directe :** Appelez `viewer.render(inputFile, new HtmlOptions())` – l'API lit le DOCX, extrait les images/CSS et écrit un dossier HTML autonome en une seule opération. Cette approche simplifie l'intégration et réduit la quantité de code boilerplate que vous devez écrire.

`Viewer` est la classe centrale qui orchestre toutes les actions de rendu. Après avoir créé une instance `Viewer`, vous transmettez le document source et un objet de configuration à la méthode `render`.

1. **Initialiser le Viewer** – fournissez votre licence et créez l'objet `Viewer`.  
2. **Charger le fichier DOCX** – fournissez un `File` ou un `InputStream`.  
3. **Configurer les options de rendu** – activez la gestion des ressources externes, définissez la qualité d'image et choisissez le format de sortie.  
4. **Exécuter la conversion** – invoquez `viewer.render` avec `HtmlOptions`.  
5. **Traiter le résultat** – enregistrez les fichiers HTML et toutes les ressources extraites à l'emplacement souhaité.

Ces étapes sont démontrées dans le premier lien de tutoriel ci‑dessous, qui montre également comment gérer les images externes et les fichiers CSS.

## Comment rendre pdf java avec GroupDocs.Viewer

Rendre les PDF en images, HTML ou autres formats tout en contrôlant la sortie page par page.  
**Réponse directe :** Utilisez `PdfOptions` avec `setPages` pour spécifier les pages dont vous avez besoin, puis appelez `viewer.render(pdfFile, options)` – cela diffuse chaque page sous forme d'image sans charger le PDF complet en mémoire.

`PdfOptions` est l'objet de configuration qui vous permet d'affiner le rendu PDF, y compris la sélection de pages, la rotation et la qualité d'image.

Les techniques clés couvertes dans la liste de tutoriels incluent la désactivation du groupement de caractères pour une extraction de texte précise, le rendu en couches pour préserver l'index Z, et la réorganisation des pages pour des flux de documents personnalisés.

## Comment faire pivoter des pages pdf spécifiques avec GroupDocs.Viewer Java

Faire pivoter uniquement les pages que vous sélectionnez, en laissant le reste intact.  
**Réponse directe :** Créez une instance `PdfOptions`, appelez `setPages(List<Integer>)` pour les pages cibles, appliquez `setRotationAngle(RotationAngle.ROTATE_90)` (ou 180/270), puis rendez avec `viewer.render`. Cette opération met à jour les pages choisies en un seul passage et évite le re‑rendu complet du document.

`PdfOptions` est la classe d'options qui contrôle les détails du rendu PDF tels que la plage de pages, la rotation et la qualité d'image. En la configurant page par page, vous maintenez le temps de traitement au minimum.

Étapes typiques d'implémentation :

1. **Créer un objet PdfOptions** – cela contient tous les paramètres spécifiques au PDF.  
2. **Spécifier les pages à faire pivoter** – utilisez `setPages(Arrays.asList(2, 5, 7))` pour les pages 2, 5, 7.  
3. **Définir l'angle de rotation** – `setRotationAngle(RotationAngle.ROTATE_90)` fait pivoter les pages sélectionnées de 90°.  
4. **Rendre le document** – `viewer.render(pdfFile, pdfOptions)` écrit les pages pivotées dans le dossier de sortie.

## Catégories de tutoriels

### Rendu PDF & optimisation
Maîtrisez les défis de rendu spécifiques aux PDF, de la gestion efficace de gros fichiers à la personnalisation de la qualité de sortie et à la gestion de mises en page complexes.

- [Convertir DOCX en HTML avec ressources externes en utilisant GroupDocs.Viewer pour Java](./render-docx-html-external-resources-groupdocs-java/)
- [Désactiver le groupement de caractères dans les PDF avec GroupDocs.Viewer pour Java : techniques de rendu précises](./groupdocs-viewer-java-disable-character-grouping-pdf/)
- [Rendu PDF en couches efficace en Java avec GroupDocs.Viewer](./pdf-layered-rendering-java-groupdocs-viewer/)
- [Réorganisation efficace des pages PDF avec GroupDocs.Viewer pour Java : guide complet](./master-pdf-page-reorder-groupdocs-java/)
- [Rendu PDF Java avec GroupDocs.Viewer : implémentation des sauts de page dans les feuilles de calcul](./java-pdf-rendering-groupdocs-viewer-page-breaks/)
- [Optimiser la qualité JPG dans les PDF en utilisant GroupDocs.Viewer pour Java](./optimize-jpg-quality-groupdocs-viewer-java/)
- [Optimiser la qualité d'image PDF en Java avec GroupDocs.Viewer](./adjust-image-quality-groupdocs-viewer-java/)
- [Faire pivoter des pages PDF spécifiques avec GroupDocs.Viewer en Java : guide complet](./rotate-pdf-pages-groupdocs-viewer-java/)

### Documents Office & feuilles de calcul
Gérez les documents Microsoft Office avec un formatage avancé, des configurations personnalisées et des options de rendu spécialisées.

- [Comment ajuster le débordement de texte dans les feuilles de calcul Excel avec GroupDocs.Viewer pour Java](./groupdocs-viewer-java-adjust-text-overflow-spreadsheets/)
- [Rendu des zones d'impression des feuilles de calcul Java avec GroupDocs.Viewer pour Java : guide complet](./java-groupdocs-viewer-render-print-areas-spreadsheet/)
- [Rendre les lignes et colonnes cachées dans les feuilles de calcul Java avec GroupDocs.Viewer](./render-hidden-rows-columns-java-groupdocs-viewer/)
- [Ignorer le rendu des lignes vides en Java avec GroupDocs.Viewer : guide de performance](./skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Comment rendre les modifications suivies dans les documents Word avec GroupDocs.Viewer pour Java : guide complet](./render-tracked-changes-word-docs-groupdocs-viewer-java/)

### Traitement des dessins CAD
Travaillez avec des fichiers CAD complexes, gérez plusieurs mises en page et implémentez des options de rendu personnalisées pour les dessins techniques.

- [Comment rendre les dessins CAD en PNG avec taille personnalisée et couleur d'arrière-plan en utilisant GroupDocs.Viewer pour Java](./render-cad-drawings-custom-png-groupdocs-java/)
- [Rendre efficacement toutes les mises en page CAD avec GroupDocs.Viewer pour Java](./render-cad-drawings-layouts-groupdocs-viewer-java/)
- [Rendre des couches CAD spécifiques en Java avec GroupDocs.Viewer : guide complet](./render-cad-layers-java-groupdocs-viewer/)
- [Diviser les dessins CAD en tuiles avec GroupDocs.Viewer Java pour un rendu efficace](./split-cad-drawings-into-tiles-groupdocs-viewer-java/)

### Documents email & communication
Traitez les fichiers email, gérez les pièces jointes et personnalisez le rendu des métadonnées pour les applications centrées sur la communication.

- [Comment renommer les champs d'email lors de la conversion d'emails en HTML avec GroupDocs.Viewer Java](./rename-email-fields-html-groupdocs-viewer-java/)
- [Rendre les emails avec une date/heure personnalisée en Java avec GroupDocs.Viewer](./render-emails-custom-datetime-groupdocs-viewer-java/)
- [Limiter le rendu des éléments Outlook en Java avec GroupDocs.Viewer : guide complet](./groupdocs-viewer-java-limit-outlook-rendering/)
- [Maîtriser le rendu et le filtrage des données Outlook avec GroupDocs.Viewer pour Java](./render-filter-outlook-data-groupdocs-java/)

### Présentations & médias visuels
Gérez les fichiers PowerPoint, les notes de diapositives et traitez les présentations visuelles avec des options de rendu avancées.

- [Comment rendre les documents FODP avec GroupDocs.Viewer pour Java : guide complet](./render-fodp-groupdocs-viewer-java/)
- [Comment rendre les présentations avec notes en utilisant GroupDocs.Viewer pour Java : guide complet](./groupdocs-viewer-java-presentation-notes-rendering/)
- [Java : comment rendre les pages cachées avec GroupDocs.Viewer](./java-render-hidden-pages-groupdocs-viewer/)

### Archivage & gestion de fichiers
Traitez les fichiers compressés, gérez des structures de dossiers spécifiques et administrez de grandes collections d'archives efficacement.

- [Rendu des dossiers d'archive en Java avec GroupDocs.Viewer : guide étape par étape](./render-archive-folders-groupdocs-viewer-java/)
- [Maîtriser GroupDocs.Viewer Java : noms de fichiers personnalisés pour le rendu PDF des archives](./groupdocs-viewer-java-custom-filenames-rendering-archives/)

### Gestion de documents & métadonnées
Extrayez les informations de documents, gérez les pièces jointes et implémentez des flux de travail avancés de traitement de documents.

- [Comment rendre les documents avec commentaires en Java avec GroupDocs.Viewer](./mastering-document-rendering-comments-groupdocs-viewer-java/)
- [Comment rendre les pages sélectionnées d'un document avec GroupDocs.Viewer pour Java](./render-selected-pages-groupdocs-viewer-java/)
- [Maîtriser GroupDocs.Viewer pour Java : récupérer les informations et insights de vue de document](./groupdocs-viewer-java-document-views/)
- [Maîtriser GroupDocs.Viewer pour Java : récupérer et imprimer les pièces jointes du document](./groupdocs-viewer-java-retrieve-print-attachments/)

### Techniques de rendu spécialisées
Scénarios avancés incluant le formatage personnalisé, les types de fichiers spécialisés et les stratégies d'optimisation des performances.

- [Rendu HPG Java avec GroupDocs.Viewer : guide complet](./java-hpg-rendering-groupdocs-viewer-guide/)
- [Rendre des documents texte en Shift_JIS avec GroupDocs.Viewer pour Java](./render-shift-jis-text-documents-groupdocs-java/)
- [Rendre les documents en images avec couche texte en Java avec GroupDocs.Viewer](./render-documents-to-images-with-text-layer-java/)
- [Rendre les documents de projet par intervalles de temps avec GroupDocs.Viewer pour Java](./render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Rendu HTML responsive avec GroupDocs.Viewer pour Java : guide complet](./groupdocs-viewer-java-responsive-html-rendering/)
- [Faire pivoter la première page d'un document avec GroupDocs.Viewer pour Java (guide avancé)](./rotate-first-page-document-groupdocs-viewer-java/)

## Défis courants d'implémentation

### Optimisation des performances
Les gros documents peuvent ralentir considérablement votre application. La clé est d'implémenter des stratégies de mise en cache intelligentes et d'utiliser des techniques de rendu sélectif. De nombreux tutoriels incluent des astuces de performance spécifiques – portez une attention particulière aux guides de rendu basé sur les tuiles et de rendu sélectif de pages.

### Gestion de la mémoire
Le rendu de documents peut être gourmand en mémoire, surtout avec de gros fichiers ou de multiples utilisateurs simultanés. Implémentez toujours des modèles de libération appropriés et envisagez des approches de streaming pour les ensembles de documents volumineux.

### Problèmes spécifiques aux formats
Chaque type de document présente des défis uniques. Les PDF peuvent comporter des couches complexes, les fichiers CAD exigent une gestion précise des calques, et les feuilles de calcul nécessitent une gestion attentive des débordements. Chaque tutoriel aborde les considérations propres à son format.

### Considérations d'intégration
Lors de l'intégration de GroupDocs.Viewer dans des systèmes existants, pensez aux modèles de threading, aux schémas de gestion des erreurs et à la gestion de la configuration. Les tutoriels avancés démontrent des modèles d'intégration prêts pour la production.

## Bonnes pratiques pour le rendu avancé

- **Commencer simplement** – commencez par des exigences de rendu de base et ajoutez progressivement des fonctionnalités avancées. Cette approche vous aide à comprendre les mécanismes sous‑jacents avant d'aborder des scénarios complexes.  
- **Tester avec des données réelles** – testez toujours vos implémentations de rendu avec des documents réels provenant de votre environnement cible. Les fichiers d'exemple ne révèlent souvent pas les problèmes de performance ou les cas limites du monde réel.  
- **Surveiller l'utilisation des ressources** – les techniques de rendu avancées peuvent consommer des ressources système importantes. Mettez en place une surveillance pour suivre l'utilisation de la mémoire, le temps de traitement et l'impact sur le système.  
- **Planifier l'échelle** – considérez comment votre solution de rendu fonctionnera sous charge. De nombreuses techniques avancées fonctionnent bien pour des documents individuels mais peuvent nécessiter une optimisation pour des utilisateurs concurrents ou de gros volumes de documents.  
- **Gestion des erreurs** – implémentez une gestion robuste des erreurs pour les formats non pris en charge, les fichiers corrompus et les contraintes de ressources. Les tutoriels incluent des modèles de gestion des erreurs que vous pouvez adapter à vos besoins spécifiques.

## Quand utiliser les techniques de rendu avancées
Les techniques de rendu avancées sont idéales lorsque vous avez besoin d'un contrôle précis sur la sortie du document, comme la rotation de pages, l'ajustement de la qualité d'image ou le rendu de sections sélectionnées. Elles aident à répondre aux exigences de performance, de conformité et d'expérience utilisateur tout en maintenant une consommation de ressources prévisible dans les environnements de production actuels.

- **Systèmes de gestion de documents** – un contrôle précis de l'apparence du document est crucial pour la collaboration et la conformité.  
- **Traitement automatisé** – les scénarios de traitement par lots exigent une sortie cohérente et prévisible à travers de nombreux types de documents.  
- **Visionneuses personnalisées** – les applications spécialisées nécessitent souvent des comportements de rendu non disponibles dans les visionneuses standard.  
- **Applications critiques en performance** – environnements à haut volume où la vitesse de rendu impacte directement l'expérience utilisateur.  
- **Exigences de conformité** – les industries réglementées ont besoin d'un rendu précis et complet pour répondre aux normes d'audit.

## Prochaines étapes

Prêt à implémenter le rendu avancé GroupDocs.Viewer Java dans vos applications ? Commencez par le tutoriel qui correspond le mieux à vos besoins immédiats, puis élargissez vos connaissances avec les techniques connexes. Chaque guide s'appuie sur des concepts fondamentaux, vous permettant ainsi de développer une compréhension complète de l'ensemble de l'écosystème de rendu.

Rappelez‑vous que le rendu avancé consiste souvent à résoudre des problèmes métier spécifiques plutôt qu'à utiliser des fonctionnalités complexes pour elles‑mêmes. Concentrez‑vous sur les tutoriels qui répondent directement aux exigences de votre application, et n'hésitez pas à combiner des techniques de plusieurs guides pour créer des solutions personnalisées.

Pour un support continu et des insights communautaires, visitez le forum GroupDocs.Viewer où des développeurs expérimentés partagent leurs expériences d'implémentation réelles et des astuces de dépannage.

## Ressources supplémentaires

- [Documentation GroupDocs.Viewer pour Java](https://docs.groupdocs.com/viewer/java/)
- [Référence API GroupDocs.Viewer pour Java](https://reference.groupdocs.com/viewer/java/)
- [Télécharger GroupDocs.Viewer pour Java](https://releases.groupdocs.com/viewer/java/)
- [Forum GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9)
- [Support gratuit](https://forum.groupdocs.com/)
- [Licence temporaire](https://purchase.groupdocs.com/temporary-license/)

## Questions fréquemment posées

**Q : Puis-je utiliser GroupDocs.Viewer pour convertir DOCX en HTML dans une application Spring Boot ?**  
**R :** Oui. Initialise le bean `Viewer` avec votre licence, puis appelez `viewer.render` avec `HtmlOptions` dans n'importe quel service ou contrôleur.

**Q : Comment la bibliothèque gère‑t‑elle les gros PDF lors du rendu en images ?**  
**R :** Utilisez `PdfOptions` pour activer le rendu page par page et configurez `setCacheFolder` afin de stocker les résultats intermédiaires, réduisant ainsi la pression sur la mémoire.

**Q : Est‑il possible de rendre uniquement les pages sélectionnées d’un document ?**  
**R :** Absolument. Définissez la collection `pages` dans `RenderOptions` aux numéros de pages spécifiques dont vous avez besoin.

**Q : Quels formats peuvent être rendus en HTML avec ressources intégrées ?**  
**R :** DOCX, PPTX, XLSX, PDF et bien d'autres sont pris en charge. Utilisez `HtmlOptions.setResourcesPath` pour contrôler l'emplacement où les images et le CSS sont enregistrés.

**Q : GroupDocs.Viewer prend‑il en charge le rendu multi‑threadé ?**  
**R :** Oui, mais chaque instance `Viewer` doit être utilisée par thread ou vous devez implémenter une synchronisation appropriée pour éviter les conditions de concurrence.

---

**Dernière mise à jour :** 2026-08-19  
**Testé avec :** GroupDocs.Viewer for Java 23.11  
**Auteur :** GroupDocs

## Tutoriels associés

- [Comment convertir pdf en html et optimiser la qualité d'image en Java avec GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [Convertir DOCX en HTML Java – Pages avec GroupDocs.Viewer](/viewer/java/advanced-rendering/render-selected-pages-groupdocs-viewer-java/)
- [Modifier la séquence des pages PDF avec GroupDocs.Viewer pour Java – Guide](/viewer/java/advanced-rendering/master-pdf-page-reorder-groupdocs-java/)