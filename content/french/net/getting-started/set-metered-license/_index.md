---
title: Définir une licence limitée
linktitle: Définir une licence limitée
second_title: API GroupDocs.Viewer .NET
description: Améliorez vos applications .NET avec GroupDocs.Viewer pour une visualisation transparente des documents. Intégrez facilement des fonctionnalités de rendu de documents dans vos projets.
type: docs
weight: 12
url: /fr/net/getting-started/set-metered-license/
---
## Introduction
Dans le monde du développement .NET, l'intégration de puissantes fonctionnalités de visualisation de documents dans vos applications est essentielle pour améliorer l'expérience utilisateur et les fonctionnalités. GroupDocs.Viewer pour .NET offre une solution robuste pour intégrer de manière transparente les fonctionnalités de visualisation de documents dans vos projets .NET. Que vous travailliez avec des PDF, des documents Microsoft Office ou divers formats d'image, GroupDocs.Viewer simplifie le processus de rendu et d'affichage de ces documents dans vos applications.
## Conditions préalables
Avant de vous lancer dans la mise en œuvre de GroupDocs.Viewer pour .NET, assurez-vous que les conditions préalables suivantes sont en place :
### 1. Installez GroupDocs.Viewer pour .NET
 Pour commencer, vous devrez télécharger et installer GroupDocs.Viewer pour .NET. Vous pouvez trouver le lien de téléchargement[ici](https://releases.groupdocs.com/viewer/net/). Suivez les instructions d'installation fournies pour configurer la bibliothèque dans votre environnement de développement.
### 2. Obtenir une licence limitée
Afin d'utiliser GroupDocs.Viewer pour .NET, vous devez obtenir une licence limitée. Cette licence vous permet de contrôler et de surveiller votre utilisation de l'API en fonction de quotas prédéfinis. Suivez les étapes ci-dessous pour configurer votre licence limitée :

## Importer des espaces de noms
Tout d’abord, assurez-vous d’importer les espaces de noms nécessaires pour accéder aux fonctionnalités fournies par GroupDocs.Viewer pour .NET :
```csharp
using System;
```

Maintenant, décomposons l'exemple de code fourni en plusieurs étapes :
## Étape 1 : Déclarer les clés publiques et privées
Déclarez des variables pour stocker vos clés publiques et privées :
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Assurez-vous de remplacer`"YOUR_PUBLIC_KEY"` et`"YOUR_PRIVATE_KEY"` avec vos vraies clés.
## Étape 2 : Définir une licence limitée
Vérifiez si la clé publique est fournie. Sinon, invitez l'utilisateur à définir les clés :
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://buy.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Étape 3 : initialiser l'objet mesuré et définir la licence
Initialisez l'objet Metered et définissez la licence mesurée à l'aide de vos clés publiques et privées :
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Étape 4 : Message de confirmation
Afficher un message de confirmation indiquant que la licence a été définie avec succès :
```csharp
Console.WriteLine("License set successfully.");
```

## Conclusion
En conclusion, GroupDocs.Viewer pour .NET fournit une solution complète pour intégrer des fonctionnalités de visualisation de documents dans vos applications .NET. En suivant les étapes décrites, vous pouvez facilement configurer une licence limitée et commencer à tirer parti des capacités de GroupDocs.Viewer dans vos projets.
## FAQ
### Q : Où puis-je trouver de la documentation pour GroupDocs.Viewer pour .NET ?
 Vous pouvez trouver la documentation[ici](https://reference.groupdocs.com/viewer/net/).
### Q : Existe-t-il un essai gratuit disponible pour GroupDocs.Viewer pour .NET ?
 Oui, vous pouvez accéder à l'essai gratuit[ici](https://releases.groupdocs.com/).
### Q : Comment puis-je obtenir des licences temporaires à des fins de test ?
 Des licences temporaires peuvent être obtenues[ici](https://purchase.groupdocs.com/temporary-license/).
### Q : Où puis-je demander de l'aide ou poser des questions relatives à GroupDocs.Viewer pour .NET ?
 Vous pouvez demander de l'aide et poser des questions sur le forum GroupDocs.Viewer[ici](https://forum.groupdocs.com/c/viewer/9).
### Q : Où puis-je acheter une licence pour GroupDocs.Viewer pour .NET ?
 Vous pouvez acheter une licence[ici](https://purchase.groupdocs.com/buy).