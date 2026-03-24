---
date: '2026-03-24'
description: Apprenez à convertir les e‑mails en HTML et à renommer les champs d’e‑mail
  en utilisant GroupDocs Viewer pour Java. Ce guide montre comment rendre les e‑mails
  en HTML avec des en‑têtes personnalisés.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Convertir l'e-mail en HTML et renommer les champs – GroupDocs Viewer Java
type: docs
url: /fr/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Convertir les e‑mails en HTML et renommer les champs – GroupDocs Viewer Java

Si vous devez **convertir un e‑mail en HTML** tout en donnant aux en‑têtes d’e‑mail un aspect personnalisé, vous êtes au bon endroit. Dans ce tutoriel, nous parcourrons les étapes exactes pour renommer les champs d’e‑mail, **convertir un e‑mail en HTML**, et personnaliser les en‑têtes d’e‑mail à l’aide de GroupDocs.Viewer pour Java. À la fin, vous disposerez d’une représentation HTML propre avec les noms d’en‑tête que vous préférez, rendant la sortie plus facile à lire et à intégrer dans vos applications.

![Renommer les champs d’e‑mail lors de la conversion d’e‑mails en HTML avec GroupDocs.Viewer pour Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Ce que vous apprendrez
- Comment utiliser GroupDocs.Viewer pour Java pour **convertir un e‑mail en HTML**.  
- Techniques pour **renommer les champs d’e‑mail** tels que « From », « To », « Sent » et « Subject ».  
- Meilleures pratiques pour configurer Maven et la licence.  
- Scénarios réels où **personnaliser les en‑têtes d’e‑mail** ajoute de la valeur.

## Réponses rapides
- **Que signifie « convertir un e‑mail en HTML » ?** Cela signifie rendre un fichier e‑mail (MSG/EML) sous forme de document HTML prêt pour le web.  
- **Quelle bibliothèque gère la conversion ?** GroupDocs.Viewer pour Java (v25.2+).  
- **Ai‑je besoin d’une licence ?** Un essai fonctionne pour l’évaluation ; une licence complète est requise pour la production.  
- **Puis‑je modifier n’importe quel nom d’en‑tête ?** Oui, tout en‑tête d’e‑mail standard peut être remappé via `fieldTextMap`.  
- **Le résultat est‑il du HTML ou des ressources incorporées ?** Vous pouvez choisir des ressources incorporées pour un seul fichier autonome.

## Qu’est‑ce que « convertir un e‑mail en HTML » dans le contexte de GroupDocs.Viewer ?
Convertir un e‑mail en HTML consiste à prendre un fichier e‑mail brut et à produire une page HTML affichant le corps du message ainsi que ses métadonnées. Lorsque vous **renommez également les champs d’e‑mail**, les libellés par défaut (p. ex., « From ») sont remplacés par du texte personnalisé (p. ex., « Sender »), ce qui vous aide à aligner la terminologie d’entreprise ou à améliorer la cohérence de l’interface utilisateur.

## Pourquoi convertir les e‑mails en HTML et renommer les champs ?
- **Cohérence de la marque :** Aligner la sortie avec le langage de votre organisation.  
- **Meilleure recherchabilité :** Les en‑têtes personnalisés peuvent être indexés plus efficacement dans les systèmes d’archivage.  
- **Intégration UI améliorée :** Adapter le fragment HTML pour qu’il s’intègre parfaitement aux portails web ou aux tableaux de bord de support.

## Prérequis

### Bibliothèques requises, versions et dépendances
- **GroupDocs.Viewer pour Java** – version 25.2 ou ultérieure.  
- **Java Development Kit (JDK)** – version 8+.

### Exigences de configuration de l’environnement
- **Maven** pour la gestion des dépendances.  
- Un IDE tel qu’IntelliJ IDEA, Eclipse ou VS Code.

### Prérequis de connaissances
Une familiarité de base avec Java et Maven vous aidera à suivre rapidement.

## Configuration de GroupDocs.Viewer pour Java

### Configuration Maven
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

### Étapes d’obtention de licence
- **Essai gratuit :** Téléchargez un essai gratuit depuis [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Licence temporaire :** Obtenez une licence temporaire pour explorer toutes les fonctionnalités sans limitations sur [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Achat :** Pour une utilisation continue, envisagez d’acheter une licence via [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Initialisation et configuration de base
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Ajustez le chemin du fichier pour qu’il pointe vers votre fichier `.msg`.

## Comment convertir un e‑mail en HTML et renommer les champs – Étape par étape

### 1. Configurer le chemin du répertoire de sortie
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Remplacez `"YOUR_OUTPUT_DIRECTORY"` par le dossier où vous souhaitez enregistrer les fichiers HTML.*

### 2. Définir le format du chemin de fichier de page
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` sera remplacé par le numéro de page lors du rendu.*

### 3. Créer une correspondance des champs d’e‑mail vers de nouveaux noms
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Ici nous changeons les libellés par défaut en libellés personnalisés.*

### 4. Configurer les options d’affichage HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` regroupe le CSS/JS à l’intérieur du HTML, tandis que `setFieldTextMap` applique les noms d’en‑tête personnalisés.*

### 5. Rendre l’e‑mail en HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Remplacez `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` par le chemin réel vers votre fichier MSG.*

#### Conseils de dépannage
- Vérifiez que le répertoire de sortie est accessible en écriture.  
- Assurez‑vous que le fichier MSG d’entrée existe et que le chemin est correct.  
- Utilisez la même version de GroupDocs.Viewer (25.2) que celle déclarée dans Maven.

## Applications pratiques
1. **Rapports d’e‑mail personnalisés :** Aligner les en‑têtes d’e‑mail avec la terminologie d’entreprise pour des rapports plus clairs.  
2. **Systèmes d’archivage d’e‑mail :** Améliorer la recherchabilité en utilisant des noms d’en‑tête standardisés.  
3. **Plateformes de support client :** Présenter les tickets avec des libellés d’en‑tête personnalisés pour une meilleure expérience des agents.

## Considérations de performance
- Libérez les objets `Viewer` avec try‑with‑resources pour libérer rapidement la mémoire.  
- Profilez les gros lots et envisagez de traiter les e‑mails en flux parallèles si nécessaire.

## Conclusion
Vous savez maintenant **comment convertir un e‑mail en HTML** tout en **renommant les champs d’e‑mail** et **personnalisant les en‑têtes d’e‑mail** avec GroupDocs.Viewer pour Java. Cette technique vous donne un contrôle complet sur la présentation des métadonnées d’e‑mail dans les sorties HTML.

### Prochaines étapes
- Expérimentez avec des correspondances de champs supplémentaires (p. ex., CC, BCC).  
- Explorez d’autres formats de rendu tels que PDF ou PNG.  
- Consultez [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) pour des informations plus approfondies sur l’API.

## Questions fréquentes

**Q : Cette approche fonctionne‑t‑elle avec d’autres formats d’e‑mail comme EML ?**  
R : Oui, GroupDocs.Viewer prend en charge les fichiers MSG et EML ; la même logique de correspondance des champs s’applique.

**Q : Puis‑je générer le HTML sans ressources incorporées ?**  
R : Vous pouvez utiliser `HtmlViewOptions.forExternalResources(...)` si vous préférez des fichiers CSS/JS séparés.

**Q : Quelle version de GroupDocs.Viewer a été testée ?**  
R : Le code a été testé avec GroupDocs.Viewer **25.2**.

**Q : Est‑il possible de changer la police ou le style des en‑têtes personnalisés ?**  
R : Le style peut être appliqué via CSS après le rendu, ou vous pouvez injecter du CSS personnalisé en utilisant `HtmlViewOptions.getResourcesPath()`.

**Q : Comment récupérer programmatique le chemin du fichier HTML généré ?**  
R : Le chemin du fichier suit le modèle défini dans `pageFilePathFormat` ; vous pouvez le construire en utilisant `String.format` avec le numéro de page.

## Ressources
- **Documentation :** Des guides complets sont disponibles sur [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Référence API :** Des informations détaillées sur l’API sont disponibles sur [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Télécharger GroupDocs.Viewer :** Accédez à la dernière version via la [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Dernière mise à jour :** 2026-03-24  
**Testé avec :** GroupDocs.Viewer 25.2  
**Auteur :** GroupDocs