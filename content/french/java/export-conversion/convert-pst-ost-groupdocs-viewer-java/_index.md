---
date: '2026-02-15'
description: Apprenez à convertir les fichiers PST en HTML et d’autres formats tels
  que JPG, PNG, PDF en utilisant GroupDocs.Viewer pour Java. Ce guide couvre toutes
  les étapes et configurations nécessaires.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Convertir PST en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour Java
type: docs
url: /fr/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

 "Quick Answers" maybe "Réponses rapides". Keep heading.

Also bullet points.

Also "What library handles PST conversion?" etc.

We need to translate the Q&A.

Also "Conclusion" heading.

Also "Last Updated:" etc.

Make sure to keep the date as is.

Now produce final output.

# Convertir PST en HTML, JPG, PNG, PDF avec GroupDocs.Viewer pour Java

Vous cherchez à **convertir pst en html** ou d’autres formats comme JPG, PNG ou PDF ? Avec la puissante bibliothèque GroupDocs.Viewer pour Java, cette tâche est simple et efficace. Dans ce tutoriel, vous apprendrez à rendre les fichiers Outlook PST/OST en HTML compatible web, fichiers image ou PDF unique, facilitant le partage et l’archivage de vos courriels.

![Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Ce que vous allez apprendre**
- Comment configurer GroupDocs.Viewer pour Java dans un projet Maven.  
- Instructions étape par étape pour **java convert pst** en HTML, JPG, PNG et PDF.  
- Conseils de configuration pour des performances optimales et les pièges courants.

## Réponses rapides
- **Quelle bibliothèque gère la conversion PST ?** GroupDocs.Viewer pour Java.  
- **Puis‑je convertir directement PST en PDF ?** Oui, en utilisant `PdfViewOptions`.  
- **Une licence est‑elle requise pour la production ?** Une licence GroupDocs valide est nécessaire.  
- **Quelle version de Java est prise en charge ?** JDK 8 ou supérieur.  
- **Dois‑je extraire les pièces jointes manuellement ?** Non, le visualiseur les rend automatiquement.

## Comment convertir pst en html avec GroupDocs.Viewer pour Java
Vous trouverez ci‑dessous un aperçu concis du processus de conversion avant de plonger dans les exemples de code détaillés.

### Pourquoi choisir GroupDocs.Viewer ?
- **Rendu haute fidélité** du corps des courriels, des pièces jointes et du formatage.  
- **Multiples formats de sortie** (HTML, JPG, PNG, PDF) depuis une seule API.  
- **Aucune dépendance externe** – tout fonctionne à l’intérieur de votre application Java.

## Prérequis

- **GroupDocs.Viewer pour Java** – version 25.2 ou ultérieure.  
- **Java Development Kit (JDK)** – 8 ou plus récent.  
- Maven pour la gestion des dépendances.  
- Connaissances de base en Java et familiarité avec Maven.

## Configuration de GroupDocs.Viewer pour Java

Ajoutez le dépôt GroupDocs et la dépendance à votre `pom.xml` :

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
- **Essai gratuit** – explorez toutes les fonctionnalités sans frais.  
- **Licence temporaire** – prolongez la période d’évaluation si besoin.  
- **Licence complète** – requise pour les déploiements en production.

### Initialisation de base

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Guide d’implémentation

Les sections suivantes vous guident pas à pas pour rendre les fichiers PST/OST dans chaque format pris en charge.

### Rendu des documents PST/OST en HTML

#### Étape 1 : Configurer le répertoire de sortie

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Étape 2 : Configurer les options de chargement

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Étape 3 : Initialiser le Viewer et rendre le HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendu des documents PST/OST en JPG

#### Étape 1 : Configurer le répertoire de sortie

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Étape 2 : Configurer les options de chargement

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Étape 3 : Initialiser le Viewer et rendre le JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendu des documents PST/OST en PNG

#### Étape 1 : Configurer le répertoire de sortie

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Étape 2 : Configurer les options de chargement

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Étape 3 : Initialiser le Viewer et rendre le PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Rendu des documents PST/OST en PDF

#### Étape 1 : Configurer le répertoire de sortie

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Étape 2 : Configurer les options de chargement

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Étape 3 : Initialiser le Viewer et rendre le PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Applications pratiques

- **Archivage des courriels** : Transformez de grands archives PST en HTML ou PDF consultables pour la conformité.  
- **Systèmes de gestion documentaire** : Stockez les fichiers convertis dans des systèmes qui n’acceptent que PDF, PNG ou JPG.  
- **Plateformes de collaboration** : Partagez les courriels convertis sous forme d’images dans Slack ou Teams.  
- **Examen juridique** : Fournissez aux tribunaux des versions PDF des preuves par courriel.  
- **Stratégies de sauvegarde** : Conservez des instantanés légers en PNG ou JPG des messages critiques.

## Considérations de performance

- **Gestion des ressources** : Réutilisez les instances `Viewer` lors du traitement de plusieurs fichiers afin de réduire la surcharge.  
- **Ajustement de la mémoire** : Modifiez `loadOptions.setResourceLoadingTimeout` en fonction de la capacité du serveur.  
- **Traitement asynchrone** : Déléguez la conversion à des threads d’arrière‑plan pour des interfaces réactives.  

## Questions fréquemment posées

**Q : Comment **convert pst to pdf** avec la même base de code ?**  
R : Utilisez `PdfViewOptions` comme indiqué dans la section de rendu PDF ; le reste du code reste identique.

**Q : GroupDocs.Viewer peut‑il gérer les fichiers PST chiffrés ?**  
R : Oui, fournissez le mot de passe via `LoadOptions.setPassword("yourPassword")` avant le rendu.

**Q : Quelle est la différence entre **java convert pst** en PNG vs JPG ?**  
R : PNG conserve une qualité sans perte, idéale pour les captures d’écran, tandis que JPG offre des tailles de fichier plus petites pour les aperçus de courriels.

**Q : Existe‑t‑il un moyen de **how to convert pst** en masse ?**  
R : Enveloppez la logique de rendu dans une boucle qui parcourt un répertoire de fichiers PST ; réutilisez la même configuration `Viewer` pour chaque fichier.

## Conclusion

Vous disposez maintenant d’un guide complet, prêt pour la production, pour **convertir pst en html**, JPG, PNG et PDF avec GroupDocs.Viewer pour Java. En suivant les étapes ci‑dessus, vous pouvez intégrer la conversion d’e‑mails dans n’importe quel flux de travail Java, améliorer l’accessibilité et répondre aux exigences de conformité.

---

**Dernière mise à jour :** 2026-02-15  
**Testé avec :** GroupDocs.Viewer pour Java 25.2  
**Auteur :** GroupDocs