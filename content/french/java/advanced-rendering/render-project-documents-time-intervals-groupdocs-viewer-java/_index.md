---
date: '2026-03-29'
description: Apprenez à créer une vue HTML MPP avec GroupDocs Viewer en Java, en affichant
  les documents de projet par intervalles de temps avec un code pas à pas.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Créer une vue HTML MPP avec GroupDocs Viewer (Java)
type: docs
url: /fr/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Comment utiliser GroupDocs Viewer pour rendre les documents de projet par intervalles de temps en Java

Dans ce tutoriel, vous apprendrez comment **create html view mpp** avec GroupDocs Viewer pour Java, vous permettant de rendre uniquement les parties d'un fichier Microsoft Project qui se situent dans un intervalle de temps spécifique. Nous parcourrons la configuration Maven, la configuration du code et des scénarios réels afin que vous puissiez intégrer des vues de chronologie précises directement dans vos applications.

![Rendu des documents de projet par intervalles de temps avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Réponses rapides
- **Que fait la fonctionnalité ?** Elle rend uniquement la partie d'un fichier Microsoft Project qui se situe entre une date de début et une date de fin.  
- **Quel format de sortie est utilisé ?** HTML avec ressources intégrées, parfait pour l'intégration web.  
- **Ai-je besoin d'une licence ?** Un essai gratuit fonctionne pour l'évaluation ; une licence complète est requise pour la production.  
- **Puis-je changer la plage de dates à l'exécution ?** Oui — ajustez les valeurs `setStartDate` et `setEndDate` dans les options de rendu.  
- **Cette fonctionnalité est‑elle prise en charge sur toutes les versions de Java ?** Fonctionne avec Java 8+ tant que vous utilisez GroupDocs.Viewer 25.2 ou une version plus récente.

## Comment créer html view mpp pour les documents de projet
GroupDocs Viewer peut convertir les fichiers Microsoft Project (`.mpp`, `.mpt`) en pages HTML. En configurant les dates de début et de fin dans les options de rendu, vous limitez la sortie à la tranche temporelle qui vous intéresse, ce qui réduit la taille du fichier et accélère le chargement des pages.

## Qu’est‑ce que « How to Use GroupDocs » dans ce contexte ?
GroupDocs Viewer est une bibliothèque Java qui convertit plus de 100 formats de fichiers en représentations adaptées au web. Lorsque vous **how to use GroupDocs** pour les fichiers de projet, vous obtenez la capacité d'extraire, de visualiser et de partager les données de planification sans nécessiter Microsoft Project côté client.

## Pourquoi rendre les documents de projet avec des intervalles de temps ?
- **Analyse ciblée :** Affichez uniquement la phase qui vous intéresse (par ex., T3 2024).  
- **Performance :** Une sortie HTML plus petite signifie des chargements de page plus rapides.  
- **Intégration :** Intégrez des vues de chronologie dans les tableaux de bord, les portails de reporting ou les outils PM personnalisés.  

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

1. **Essai gratuit** – Téléchargez une version d'essai depuis [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Licence temporaire** – Obtenez une licence temporaire pour des tests prolongés via [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Achat** – Pour une utilisation en production sans restriction, achetez une licence sur [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Initialisation de base du Viewer

Le fragment suivant montre comment créer une instance `Viewer` qui pointe vers un fichier Microsoft Project (`.mpp`) :

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

## Guide d'implémentation étape par étape

### 1. Définir le répertoire de sortie

Créez un dossier où les pages HTML générées seront enregistrées :

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Pourquoi ?* Garder les fichiers rendus organisés facilite leur diffusion depuis un serveur web ou leur intégration dans une interface utilisateur.

### 2. Initialiser le Viewer avec votre fichier de projet

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Pourquoi ?* Le chargement du document prépare le parseur interne et rend les métadonnées spécifiques au projet accessibles.

### 3. Récupérer les informations de vue pour les fichiers de projet

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Pourquoi ?* `ProjectManagementViewInfo` vous fournit les dates de début et de fin du planning, que vous utiliserez ensuite pour limiter la portée du rendu.

### 4. Configurer les options de rendu HTML (Générer du HTML à partir du projet)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Pourquoi ?* Définir `StartDate` et `EndDate` indique à GroupDocs de **generate html view mpp** uniquement dans cette fenêtre.

### 5. Exécuter le processus de rendu

```java
viewer.view(viewOptions);
```

*Pourquoi ?* Cette appel produit une série de pages HTML autonomes qui représentent la tranche temporelle sélectionnée de votre planning de projet.

## Problèmes courants et dépannage
- **Chemins de fichiers incorrects** – Vérifiez que le fichier source `.mpp` et le répertoire de sortie existent.  
- **Type de fichier non pris en charge** – Assurez‑vous que le document est dans un format Project supporté (par ex., `.mpp`, `.mpt`).  
- **Erreurs de licence** – Une licence d'essai peut imposer des limites de rendu ; passez à une licence complète pour une utilisation sans restriction.  

## Applications pratiques
1. **Analyse de la chronologie du projet** – Montrer aux parties prenantes uniquement la phase actuelle.  
2. **Reporting automatisé** – Générer des rapports HTML limités dans le temps pour les mises à jour hebdomadaires.  
3. **Intégration avec les tableaux de bord** – Intégrer les pages rendues dans les outils BI ou les portails personnalisés.  
4. **Archivage** – Conserver une capture web‑friendly du planning du projet pour référence future.  

## Conseils de performance
- Utilisez l'option *embedded resources* pour que chaque page HTML soit autonome, réduisant ainsi les requêtes HTTP.  
- Pour les projets très volumineux, envisagez de rendre en plus petites tranches de dates afin de maintenir une faible consommation de mémoire.  
- Nettoyez les fichiers temporaires après les avoir servis pour éviter l'encombrement du disque.  

## Conclusion
Vous savez maintenant **how to use GroupDocs** Viewer pour rendre les documents de projet dans un intervalle de temps spécifique et **generate HTML from project** en Java. Cette capacité simplifie les visualisations de chronologie, améliore l'efficacité du reporting et s'intègre parfaitement aux applications web modernes.

### Prochaines étapes
- Explorez des fonctionnalités supplémentaires du Viewer telles que le filigrane, la protection par mot de passe ou la personnalisation du style CSS.  
- Combinez ce pipeline de rendu avec une API REST pour fournir des vues de chronologie à la demande.  

## Questions fréquentes

**Q : Quels formats de fichiers GroupDocs.Viewer prend‑il en charge ?**  
R : GroupDocs.Viewer prend en charge un large éventail de formats incluant Microsoft Project (MPP), PDF, Word, Excel, PowerPoint, et bien d’autres.

**Q : Comment démarrer avec un essai gratuit de GroupDocs.Viewer ?**  
R : Vous pouvez télécharger la version d'essai depuis [here](https://releases.groupdocs.com/viewer/java/).

**Q : Puis‑je rendre des documents sans intégrer les ressources ?**  
R : Oui, vous pouvez choisir une autre option de vue HTML qui référence des ressources externes au lieu de les intégrer.

**Q : Que faire si mon document est trop volumineux pour le rendu ?**  
R : Envisagez de diviser le document en sections plus petites ou de ne rendre que la plage de dates requise, comme démontré ci‑dessus.

**Q : Comment gérer les erreurs de rendu ?**  
R : Vérifiez tous les paramètres de configuration, assurez‑vous de disposer d’une licence valide, et consultez la documentation GroupDocs pour les codes d’erreur détaillés.

## Ressources
- **Documentation** : [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Référence API** : [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Téléchargement** : [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Achat** : [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Essai gratuit** : [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Licence temporaire** : [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support** : [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Dernière mise à jour :** 2026-03-29  
**Testé avec :** GroupDocs.Viewer 25.2 for Java  
**Auteur :** GroupDocs