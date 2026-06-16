---
date: '2026-03-08'
description: Apprenez comment obtenir une licence temporaire, configurer GroupDocs.Viewer
  pour Java à l’aide de fichiers locaux ou d’URL, et vérifier la disponibilité du
  chemin de licence.
keywords:
- GroupDocs.Viewer Java license
- setting license in Java
- HTTP URL-based licenses
title: Comment obtenir une licence temporaire et configurer les licences dans GroupDocs.Viewer
  Java
type: docs
url: /fr/java/getting-started/groupdocs-viewer-java-license-setup/
weight: 1
---

# Comment obtenir une licence temporaire et définir les licences dans GroupDocs.Viewer Java

Gérer les licences efficacement est crucial lors de l'intégration de bibliothèques tierces comme **GroupDocs.Viewer for Java** dans vos applications. Ce guide vous montre **comment obtenir une licence temporaire**, la définir à partir d'un fichier local ou d'une URL HTTP, et vérifier que le chemin de la licence est correct. À la fin de ce tutoriel, vous disposerez d'une configuration de licence fiable et prête pour la production, qui maintient votre application conforme et performante.

![File and URL Setup with GroupDocs.Viewer for Java](/viewer/getting-started/file-and-url-setup-png.png)

## Réponses rapides
- **Comment obtenir une licence temporaire ?** Demandez‑en une sur la page de licence temporaire de GroupDocs et téléchargez le fichier *.lic*.  
- **Puis‑je charger la licence depuis une URL ?** Oui – il suffit de pointer `License.setLicense` vers une adresse HTTP qui renvoie un fichier de licence valide.  
- **Que se passe‑t‑il si le chemin de la licence est manquant ?** Implémentez une vérification pour afficher des instructions et empêcher le lancement du visualiseur.  
- **Dois‑je redémarrer l'application après avoir changé la licence ?** Non, `License.setLicense` peut être appelé à l'exécution.  
- **Quelle version de Java est requise ?** JDK 8 ou supérieur est recommandé.

## Qu'est‑ce qu'une licence temporaire ?
Une **licence temporaire** est une clé à durée limitée délivrée par GroupDocs qui vous permet d'évaluer le produit sans acheter une licence complète. Elle se comporte exactement comme une licence permanente tant qu'elle est valide, vous permettant de tester toutes les fonctionnalités dans un environnement réel.

## Pourquoi obtenir une licence temporaire ?
- **Évaluation rapide :** Obtenez toutes les fonctionnalités instantanément pour des projets de preuve de concept.  
- **Aucun engagement financier :** Testez avant d'acheter.  
- **Intégration facile :** Fonctionne avec les mêmes appels d'API qu'une licence permanente.

## Prérequis
1. **Java Development Kit (JDK) :** Version 8 ou supérieure.  
2. **IDE :** IntelliJ IDEA, Eclipse ou tout IDE compatible Java.  
3. **Bibliothèque GroupDocs.Viewer for Java :** Ajoutée à votre projet (voir la configuration Maven ci‑dessous).  
4. **Connaissances de base en Java :** Familiarité avec les classes, les imports et la gestion des exceptions.

## Configuration de GroupDocs.Viewer pour Java
Pour commencer, incluez la bibliothèque dans votre projet Maven.

### Configuration Maven
Ajoutez la configuration suivante à votre fichier `pom.xml` :
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

### Obtention d'une licence
Pour utiliser GroupDocs.Viewer, obtenez une licence :

- **Essai gratuit :** Téléchargez depuis le [site GroupDocs](https://releases.groupdocs.com/viewer/java/).  
- **Licence temporaire :** Demandez‑en une sur la [page de licence temporaire](https://purchase.groupdocs.com/temporary-license/).  
- **Achat :** Pour une solution permanente, envisagez d'acheter une licence sur la [page d'achat GroupDocs](https://purchase.groupdocs.com/buy).

### Initialisation de base
Une fois la bibliothèque ajoutée, vous pouvez initialiser le visualiseur :
```java
import com.groupdocs.viewer.License;

public class InitializeViewer {
    public static void main(String[] args) {
        License license = new License();
        // Set the path to your license file or URL here
        license.setLicense("YOUR_LICENSE_PATH");
        System.out.println("GroupDocs.Viewer initialized successfully.");
    }
}
```

## Comment obtenir une licence temporaire et la définir à partir d'un fichier
### Vue d'ensemble
Définir une licence à partir d'un fichier local est l'approche la plus simple et fonctionne même lorsque l'application s'exécute hors ligne.

### Étapes d'implémentation
1. **Définir le chemin de la licence** – pointez vers le fichier *.lic* que vous avez reçu après avoir demandé une licence temporaire :
```java
final String licensePath = "YOUR_DOCUMENT_DIRECTORY/your-license-file.lic";
```
2. **Appliquer la licence** – utilisez la classe `License` pour la charger :
```java
import com.groupdocs.viewer.License;

public class SetLicenseFromFile {
    public static void run() {
        if (licensePath != null && !licensePath.startsWith("http")) {
            License license = new License();
            license.setLicense(licensePath);
            System.out.println("License set successfully.");
        } else {
            // Handle cases where the path is not valid
            System.err.println(
                "We do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Conseils :**  
- Vérifiez que le chemin du fichier est absolu ou relatif au répertoire de travail.  
- Assurez‑vous que le fichier possède les permissions de lecture pour l'utilisateur exécutant la JVM.

## Comment gérer une URL de licence
### Vue d'ensemble
Une licence basée sur une URL est pratique pour les déploiements cloud où le fichier de licence se trouve dans un bucket de stockage sécurisé.

### Étapes d'implémentation
1. **Définir l'URL de la licence** – remplacez le placeholder par votre point de terminaison réel :
```java
final String licensePath = "http://example.com/license.lic";
```
2. **Détecter et consigner l'utilisation de l'URL** – l'exemple ci‑dessous vous indique simplement qu'une URL a été fournie :
```java
public class HandleLicenseURL {
    public static void run() {
        if (licensePath != null && licensePath.startsWith("http")) {
            System.err.println("License path was not provided, license URL is found instead!");
        }
    }
}
```
**Conseils :**  
- En production, vous téléchargeriez le fichier (par ex., avec `java.net.HttpURLConnection`) puis appelleriez `license.setLicense(stream)`.  
- Ajoutez une logique de nouvelle tentative et de gestion des délais d'attente pour faire face aux problèmes réseau transitoires.

## Comment vérifier la disponibilité de la licence (vérifier le chemin de la licence)
### Vue d'ensemble
Avant d'essayer de charger une licence, il est recommandé de **vérifier la disponibilité de la licence** afin de pouvoir guider les développeurs ou les utilisateurs pour obtenir une licence temporaire si nécessaire.

### Étapes d'implémentation
1. **Simuler un chemin de licence manquant** :
```java
final String licensePath = null;
```
2. **Fournir des instructions claires si le chemin est absent** :
```java
public class CheckLicensePathAvailability {
    public static void run() {
        if (licensePath == null) {
            System.out.println(
                "\nWe do not ship any license with this example.\n" +
                "Visit the GroupDocs site to obtain either a temporary or permanent license.\n" +
                "Learn more about licensing at https://purchase.groupdocs.com/faqs/licensing.\n" +
                "Lear how to request temporary license at https://purchase.groupdocs.com/temporary-license.");
        }
    }
}
```
**Conseils :**  
- Consignez ce message au démarrage afin que les équipes d'exploitation sachent qu'une licence est manquante.  
- Envisagez de quitter l'application ou de désactiver les fonctionnalités du visualiseur jusqu'à ce qu'une licence valide soit fournie.

## Applications pratiques
Comprendre comment **obtenir une licence temporaire**, la définir à partir d'un fichier ou d'une URL, et **vérifier la disponibilité du chemin de licence** ouvre plusieurs scénarios réels :

1. **Systèmes de gestion de documents** – intégrez un visualiseur qui valide automatiquement sa licence à chaque lancement.  
2. **Plateformes SaaS cloud** – stockez la licence dans un stockage blob protégé et chargez‑la via URL pour des mises à jour sans interruption.  
3. **Déploiements d'entreprise** – utilisez une licence temporaire pendant les phases pilotes avant d'acheter une licence à grande échelle.

## Considérations de performance
- **Utilisation des ressources :** Chargez la licence une fois au démarrage de l'application ; les appels répétés ajoutent des I/O inutiles.  
- **Gestion de la mémoire :** L'objet `License` conserve un état minimal, mais fermez toujours les flux si vous téléchargez la licence manuellement.

## Conclusion
En suivant les étapes ci‑dessus, vous pouvez **obtenir une licence temporaire**, configurer GroupDocs.Viewer pour Java en utilisant soit un fichier local, soit une URL HTTP, et **vérifier la disponibilité de la licence** pour garder votre application conforme. Cette base solide de gestion des licences évite les erreurs d'exécution et vous offre la flexibilité de passer entre les environnements de développement, de test et de production en toute confiance.

### FAQ

1. **Comment définir un fichier de licence local dans GroupDocs.Viewer Java ?**  

   Utilisez `license.setLicense("path/to/license.lic")` avec le chemin de fichier correct pour appliquer une licence locale.

2. **Puis‑je charger une licence directement depuis une URL ?**  

   Oui, mais assurez‑vous que votre code gère l'accès à l'URL, éventuellement en téléchargeant la licence à l'exécution ou en gérant les problèmes réseau.

3. **Que faire si le chemin de la licence est invalide ou manquant ?**  

   Implémentez des vérifications pour les valeurs nulles ou les chemins invalides et fournissez des instructions ou des invites de secours pour obtenir une licence valide.

4. **Est‑il possible de basculer dynamiquement entre le fichier de licence et l'URL ?**  

   Absolument, en ajoutant une logique conditionnelle pour gérer les deux scénarios selon votre environnement ou les paramètres d'exécution.

5. **Quelles sont les meilleures pratiques de gestion des licences en production ?**  

   Stockez les licences de manière sécurisée, vérifiez régulièrement leur validité et implémentez une gestion des erreurs pour les problèmes de licence afin d'assurer un service ininterrompu.

## Questions fréquemment posées

**Q : Combien de temps dure une licence temporaire ?**  
**R :** En général 30 jours, après quoi vous pouvez demander un renouvellement ou passer à une licence permanente.

**Q : Ai‑je besoin d’une connexion Internet pour utiliser une licence basée sur un fichier ?**  
**R :** Non. Un fichier *.lic* local fonctionne complètement hors ligne une fois chargé.

**Q : Puis‑je chiffrer le fichier de licence pour plus de sécurité ?**  
**R :** Le fichier de licence est déjà signé par GroupDocs ; un chiffrement supplémentaire est optionnel mais non requis.

**Q : Que se passe‑t‑il si la licence expire pendant que l'application fonctionne ?**  
**R :** Les opérations du visualiseur commenceront à lancer des exceptions de licence ; il est recommandé de vérifier l'expiration au démarrage.

**Q : Est‑il sûr de stocker l'URL de la licence dans le contrôle de version ?**  
**R :** Évitez de commettre des URL sensibles ; utilisez plutôt des variables d'environnement ou des magasins de configuration sécurisés.

---

**Dernière mise à jour :** 2026-03-08  
**Testé avec :** GroupDocs.Viewer 25.2 for Java  
**Auteur :** GroupDocs