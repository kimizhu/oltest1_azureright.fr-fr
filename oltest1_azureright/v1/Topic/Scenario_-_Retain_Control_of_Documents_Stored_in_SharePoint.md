---
description: na
keywords: na
title: Scenario - Retain Control of Documents Stored in SharePoint
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1b6244c7-5ab9-4881-bc8f-6fa960390d89
---
# Sc&#233;nario - Conserver le contr&#244;le des documents stock&#233;s dans SharePoint
Cette section contient les instructions pour les administrateurs et des directives concernant les instructions pour les utilisateurs.Vous devez appliquer les instructions pour les administrateurs avant d’informer vos utilisateurs de cette configuration.

## Instructions pour les administrateurs
![](../Image/AzRMS_AdminBanner.png)

Utilisez ces instructions pour garantir que les documents Office stockés dans SharePoint restent sous votre contrôle en utilisant des bibliothèques protégées.Par exemple, les documents sont automatiquement protégés contre les fuites accidentelles ou volontaires par les utilisateurs et vous pouvez bloquer l’accès au contenu même après qu’il a été téléchargé ou synchronisé.Les fichiers que vous souhaitez protéger peuvent être destinés à des actions de collaboration sur des documents de conception ou des plans ou pour des livrables.Lorsque vous configurez des bibliothèques protégées pour SharePoint, les fichiers Office enregistrés dans ces dernières seront protégés par Azure Rights Management.

Les instructions conviennent pour l’ensemble des situations suivantes :

-   Les employés collaborent et partagent des documents Office.

-   Les documents contiennent des informations qui, sans être publiques, ne sont pas exclusivement réservées à une utilisation interne.

-   Les employés n’ont pas besoin de définir ou de modifier les autorisations qu’un administrateur définit au niveau de la bibliothèque.

## Conditions requises pour ce scénario
Pour pouvoir appliquer ce scénario, les éléments suivants doivent être en place :

|Check|Condition requise|Si vous avez besoin d’informations supplémentaires|
|---------|---------------------|------------------------------------------------------|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Vous avez préparé des comptes et des groupes pour Office 365 ou Azure Active Directory|[Préparation pour Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Azure Rights Management est activé|[Activation d'Azure Rights Management](https://technet.microsoft.com/library/jj658941.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Si vous utilisez SharePoint Server : Déployez le connecteur RMS et configurez-le pour SharePoint|[Déploiement du connecteur Azure Rights Management](https://technet.microsoft.com/library/dn375964.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Configurez SharePoint pour IRM et les bibliothèques protégées|[Configuration de la gestion des droits relatifs à l'information dans le centre d'administration SharePoint](https://support.office.com/en-us/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239ce6eb-4e81-42db-bf86-a01362fed65c)<br /><br />[Activation de la gestion des droits relatifs à l'information pour une liste ou une bibliothèque](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)|

## Instructions pour les utilisateurs
Il n’existe aucune instruction spécifique destinée aux utilisateurs pour ce scénario, car les bibliothèques protégées ne nécessitent aucune action spéciale de leur part.Les documents sont automatiquement protégés en fonction des autorisations définies par un administrateur SharePoint pour le site.Toutefois, vous devrez informer les utilisateurs et votre support technique des bibliothèques qui sont protégées et comment cela peut limiter leur utilisation des documents.Par exemple, en raison des limitations actuelles, ces documents peuvent être affichés, mais pas modifiés avec des appareils mobiles.

L’exemple suivant peut être envoyé comme message standard à l’équipe ou au service concernés, après qu’une bibliothèque SharePoint a été configurée pour Azure RMS.

### Exemple de documentation utilisateur
![](../Image/AzRMS_ExampleBanner.png)

##### Annonce de l’équipe informatique : Modifications du site de rapports et de prévisions de ventes

-   Le site SharePoint **Rapports et prévisions de ventes** est désormais configuré pour une collaboration sécurisée.Dès lors, vous devez modifier directement les feuilles de calcul et les documents Word stockés sur ce site. Par exemple, vous ne pouvez pas les enregistrer à un emplacement différent pour les modifier ultérieurement ou les envoyer par courrier électronique à une autre personne.Vous pouvez les afficher sur des appareils mobiles, mais vous devez utiliser un ordinateur Windows pour les modifier.

**Vous avez besoin d'aide ?**

-   Contactez le support technique : helpdesk@vanarsdelltd.com

