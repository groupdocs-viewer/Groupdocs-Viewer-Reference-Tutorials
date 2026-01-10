---
date: '2026-01-10'
description: Apprenez à convertir les fichiers EML en HTML avec un format de date
  et heure personnalisé et à définir le décalage horaire en Java en utilisant GroupDocs.Viewer.
  Idéal pour l'archivage des e‑mails et les systèmes de support.
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: Convertir EML en HTML avec DateTime personnalisé en Java en utilisant GroupDocs.Viewer
type: docs
url: /fr/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# Convertir EML en HTML avec DateTime personnalisée en Java à l'aide de GroupDocs.Viewer

## Introduction

Dans le monde numérique d'aujourd'hui, où tout va très vite, pouvoir **convertir EML en HTML** rapidement et avec la bonne présentation de la date‑heure est essentiel pour l'archivage, les portails d'assistance et la conformité légale. Ce tutoriel vous guide dans le rendu des messages électroniques en HTML tout en appliquant un **format de date‑heure personnalisé** et un **décalage de fuseau horaire** à l'aide de GroupDocs.Viewer pour Java. À la fin, vous disposerez d'une solution réutilisable qui maintient les horodatages précis et lisibles.

![Rendu des e‑mails avec DateTime personnalisée avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**Ce que vous apprendrez**
- Comment configurer GroupDocs.Viewer dans un projet Java  
- Comment rendre les e‑mails en HTML avec des ressources intégrées  
- Comment **personnaliser le format de date‑heure** de vos messages électroniques (custom datetime format java)  
- Comment **définir le décalage de fuseau horaire** pour des horodatages corrects (set timezone offset java)  

## Réponses rapides
- **GroupDocs.Viewer peut‑il convertir EML en HTML ?** Oui, il rend les fichiers EML directement en HTML.  
- **Ai‑je besoin d'une licence ?** Un essai gratuit suffit pour les tests ; une licence payante est requise pour la production.  
- **Quelle version de Java est requise ?** Java 8 ou plus récente.  
- **Comment changer le format de date affiché ?** Utilisez `options.getEmailOptions().setDateTimeFormat(...)`.  
- **Puis‑je ajuster le fuseau horaire ?** Oui, avec `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`.

## Qu’est‑ce que « convertir EML en HTML » ?

Convertir un fichier EML en HTML transforme l'e‑mail brut (en‑têtes, corps et pièces jointes) en un format web‑compatible que les navigateurs peuvent afficher sans plugins supplémentaires. Cela facilite l'intégration des e‑mails dans des applications web, des archives ou des tableaux de bord de support.

## Pourquoi utiliser GroupDocs.Viewer pour cette tâche ?

- **Rendu sans dépendance** – pas besoin d'Outlook ou de parseurs de courrier externes.  
- **Support intégré pour les ressources intégrées** (images, pièces jointes).  
- **Contrôle fin** du formatage de la date‑heure et de la gestion des fuseaux horaires.  

## Prérequis

- **GroupDocs.Viewer pour Java** version 25.2 ou supérieure.  
- **Java Development Kit (JDK)** 8+ et un IDE (IntelliJ IDEA, Eclipse, etc.).  
- Connaissances de base en Java et familiarité avec Maven.

## Configuration de GroupDocs.Viewer pour Java

### Configuration Maven
Add the GroupDocs repository and dependency to your `pom.xml`:

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
Commencez avec un essai gratuit ou demandez une licence temporaire pour des tests prolongés. Achetez une licence complète pour la production.

### Initialisation de base
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## Convertir EML en HTML avec DateTime personnalisée en Java

Le guide étape par étape suivant montre comment **convertir EML en HTML** tout en appliquant un format de date‑heure personnalisé et un décalage de fuseau horaire.

### Étape 1 : Configurer le répertoire de sortie et le chemin du fichier
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*Explication :* `Path.of()` crée une référence au dossier où le HTML sera enregistré. `resolve()` ajoute le nom du fichier.

### Étape 2 : Initialiser le Viewer avec le fichier e‑mail
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*Explication :* L'instance `Viewer` pointe vers le fichier EML que vous souhaitez convertir.

### Étape 3 : Configurer HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*Explication :* `forEmbeddedResources()` regroupe les images et autres ressources directement dans la sortie HTML.

### Étape 4 : Définir le format de DateTime personnalisé *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*Explication :* Ce modèle affiche le mois, le jour, l'année, l'heure, les minutes, le marqueur AM/PM et le décalage de fuseau horaire (`zzz`).

### Étape 5 : Définir le décalage de fuseau horaire *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*Explication :* Ajuste les horodatages rendus au fuseau horaire souhaité. Remplacez `"GMT+1"` par tout identifiant de zone valide.

### Étape 6 : Rendre le document
```java
viewer.view(options);
```
*Explication :* Exécute la conversion, produisant un fichier HTML avec vos paramètres de date‑heure personnalisés.

## Conseils de dépannage
- **FileNotFoundException :** Vérifiez à nouveau les chemins utilisés dans `Viewer` et `Path.of()`.  
- **Horodatages incorrects :** Vérifiez que l'ID `TimeZone` correspond à votre région cible.  
- **Images manquantes :** Assurez‑vous d'avoir utilisé `HtmlViewOptions.forEmbeddedResources()` ; sinon, les ressources externes pourraient ne pas être incluses.  

## Applications pratiques
1. **Archivage des e‑mails :** Stocker des instantanés HTML recherchables des e‑mails pour la conformité.  
2. **Portails de support client :** Afficher les tickets entrants avec des heures locales précises.  
3. **Documentation juridique :** Produire des dossiers d'e‑mail prêts pour le tribunal avec des horodatages standardisés.  

## Considérations de performance
- Déployer sur un serveur dédié pour les conversions en masse.  
- Surveiller l'utilisation du tas Java ; augmentez `-Xmx` si vous rencontrez `OutOfMemoryError`.  
- Mettre en cache le HTML rendu lorsque le même e‑mail est demandé à plusieurs reprises.  

## Conclusion
Vous disposez maintenant d'une méthode complète, prête pour la production, pour **convertir EML en HTML** avec un format de date‑heure personnalisé et un décalage de fuseau horaire en utilisant GroupDocs.Viewer pour Java. Cela améliore la lisibilité, garantit la précision des horodatages et s'intègre parfaitement aux flux de travail d'archivage ou de support.

**Prochaines étapes :** Explorez d'autres options du Viewer comme le style CSS, la pagination ou la conversion PDF pour adapter davantage la sortie à vos besoins.

## Foire aux questions

**Q : Comment gérer les fichiers EML avec pièces jointes ?**  
R : Les pièces jointes sont automatiquement intégrées lorsque vous utilisez `HtmlViewOptions.forEmbeddedResources()`. Vous pouvez également les extraire via l'API Viewer si nécessaire.

**Q : Puis‑je modifier le modèle HTML ou ajouter du CSS personnalisé ?**  
R : Oui, après le rendu vous pouvez modifier le fichier HTML généré ou injecter du CSS programmatiquement avant l'enregistrement.

**Q : Est‑il possible de rendre plusieurs fichiers EML en lot ?**  
R : Encapsulez la logique de rendu dans une boucle et réutilisez la même instance `HtmlViewOptions` pour chaque fichier.

**Q : Que faire si je dois prendre en charge d'autres formats d'e‑mail comme MSG ?**  
R : GroupDocs.Viewer prend également en charge MSG, PST et d'autres conteneurs d'e‑mail—il suffit de changer l'extension du fichier dans le constructeur `Viewer`.

**Q : Ai‑je besoin d'une licence distincte pour chaque serveur ?**  
R : La licence est par déploiement ; consultez le guide de licence GroupDocs pour les scénarios multi‑serveurs.

## Ressources

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [Référence API](https://reference.groupdocs.com/viewer/java/)
- [Téléchargement](https://releases.groupdocs.com/viewer/java/)
- [Achat](https://purchase.groupdocs.com/buy)
- [Essai gratuit](https://releases.groupdocs.com/viewer/java/)
- [Licence temporaire](https://purchase.groupdocs.com/temporary-license/)
- [Forum d'assistance](https://forum.groupdocs.com/c/viewer/9)

---

**Dernière mise à jour :** 2026-01-10  
**Testé avec :** GroupDocs.Viewer 25.2 (Java)  
**Auteur :** GroupDocs  

---