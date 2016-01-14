---
description: na
keywords: na
title: Scenario - Share an Office File with Users in Another Organization
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: c10a4d7b-f57a-4a43-b66e-477777be59cc
---
# Sc&#233;nario - Partage d’un fichier Office avec les utilisateurs d’une autre organisation
Cette section contient des instructions pour l'administrateur, un modèle d'instructions pour l'utilisateur et un exemple de la façon dont les instructions pour l'utilisateur final peuvent se présenter.Avant de transmettre la documentation pour l'utilisateur final à vos utilisateurs, vous devez prendre connaissance des instructions pour l'administrateur.

## Instructions pour l'administrateur
![](../Image/AzRMS_AdminBanner.png)

Utilisez ces instructions et le modèle suivant pour créer vos propres instructions pour l'utilisateur final afin d'aider les utilisateurs à envoyer en toute sécurité par courrier électronique un fichier Office à des personnes d'une autre organisation.Le fichier Office peut être un document Word, une feuille de calcul Excel ou une présentation PowerPoint contenant, par exemple, des informations tarifaires pour un partenaire, une liste de produits pour un revendeur ou une liste de délais de livraison pour un client potentiel.Lorsque les utilisateurs suivent les instructions, le fichier joint au message électronique est protégé par Azure Rights Management.

Les instructions conviennent pour l'ensemble des situations suivantes :

-   L'employé doit envoyer des informations à l'extérieur de l'organisation, sous la forme d'un document Office.

-   Le document contient des informations qui, sans être publiques, ne sont pas réservées à une utilisation interne.

-   Les utilisateurs destinataires n'ont pas besoin de partager ces informations avec d'autres, de les imprimer ou de les utiliser dans le cadre de leur propre documentation.Si tel n'est pas le cas, vous pouvez modifier les instructions de l'utilisateur, en passant des autorisations d'affichage en lecture seule à une autre option permettant au destinataire de modifier la pièce jointe.

-   L'employé est soucieux de savoir quand ce document est ouvert par l'utilisateur externe.

Dans les instructions pour l'utilisateur ci-après, remplacez*&lt;nom du type de document Office&gt;* par le type de document que vos utilisateurs enverront.Utilisez une formulation spécifique de leurs flux de travail qui leur est familière, telle que « tarifs », « délais de livraison » ou « soumission d'appel d'offres », plutôt que « document Word » ou « Feuille de calcul Excel ».Remplacez *&lt;coordonnées&gt;* par des informations sur la manière dont vos utilisateurs peuvent contacter le support technique, telles qu'un lien de site web, une adresse de messagerie ou un numéro de téléphone.

Ensuite, apportez les modifications supplémentaires de votre choix aux instructions, puis transmettez celles-ci aux utilisateurs.Par exemple, chargez le document sur un site SharePoint ou expédiez-le par courrier électronique.

Modifications que vous pouvez apporter aux instructions :

-   À l'étape 2, nous vous suggérons de choisir l'autorisation **Visionneuse - Affichage seul**, qui a pour effet de rendre le document joint (pas l'original) accessible en lecture seule pour les destinataires.Si cette restriction n'est pas adaptée aux besoins de votre entreprise, modifiez cette option en choisissant un autre jeu d'autorisations, par exemple, **Réviseur – Affichage et modification**.

-   À l'étape 3, nous vous suggérons de sélectionner l'option **M'autoriser à révoquer de suite l'accès à ces document** afin qu'une décision éventuelle de vos utilisateurs de révoquer le document soit appliquée immédiatement, mais cette option nécessite que le destinataire dispose toujours d'une connexion Internet pour ouvrir la pièce jointe.Cette étape nécessite également que vous ayez un abonnement prenant en charge le suivi et la révocation des documents.Supprimez cette étape si elle n'est pas pertinente pour vos utilisateurs.

-   À l'étape 4, nous vous suggérons de sélectionner l'option **M'envoyer un message électronique quand quelqu'un tente d'ouvrir ce document**.Si les utilisateurs suivent leurs documents via le portail de suivi de document, vous pouvez décider que la notification par courrier électronique n'est pas nécessaire et supprimer cette étape.

-   Les étapes n'incluent pas la définition d'une date d'expiration.Si la pièce jointe est soumise à une contrainte de temps, ajoutez une autre étape pour définir un délai d'expiration approprié, par exemple de 90 jours après l'envoi du message électronique.

> [!NOTE]
> Pour plus d'informations sur chacune des options que les utilisateurs peuvent sélectionner, consultez [Options de boîte de dialogue pour l'application de partage Rights Management](https://technet.microsoft.com/library/dn574738.aspx)

## Conditions requises pour ce scénario
Pour que les instructions pour l'utilisateur décrites dans ce scénario fonctionnent, les éléments suivants doivent être en place :

|Check|Condition requise|Si vous avez besoin d'informations supplémentaires|
|---------|---------------------|------------------------------------------------------|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Vous avez préparé des comptes et des groupes pour Office 365 ou Azure Active Directory|[Préparation pour Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Azure Rights Management est activé|[Activation d'Azure Rights Management](https://technet.microsoft.com/library/jj658941.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|L'application de partage Rights Management est déployée sur les ordinateurs des utilisateurs qui exécutent Windows|[Déploiement automatique de l'application de partage Microsoft Rights Management](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Les utilisateurs disposent d'Outlook version Office 2013|Si les utilisateurs disposent d'Office 2010, remplacez la capture d'écran par une version équivalente afin que l'image corresponde à ce que les utilisateurs voient.|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Votre abonnement Azure RMS inclut le suivi de document|Si votre abonnement Azure RMS n'inclut pas le suivi et la révocation de document, les utilisateurs ne seront pas en mesure de suivre toutes les étapes des instructions pour l'utilisateur.Dans ce cas, achetez un abonnement ne prenant pas en charge ces fonctionnalités, ou modifiez les instructions pour l'utilisateur en supprimant les étapes qui utilisent ces fonctionnalités.<br /><br />Pour vérifier la prise en charge de votre abonnement : [Comparaison des offres Rights Management Services (RMS)](https://technet.microsoft.com/dn858608)|

## Instructions pour l'utilisateur :
Copiez et collez les instructions suivantes pour vos utilisateurs finaux, puis modifiez-les conformément aux instructions pour l'administrateur de ce scénario.L'exemple de documentation illustre la manière dont ces instructions se présentent aux utilisateurs une fois vos personnalisations effectuées.

![](../Image/AzRMS_UsersBanner.png)

#### Comment partager un &lt;nom du type de document Office&gt;

1.  Créez votre message électronique en spécifiant une ou plusieurs adresses de messagerie, tapez votre message, puis joignez le *&lt;nom du type de document Office&gt;* au message électronique.Ensuite, sous l'onglet **MESSAGE**, dans le groupe **RMS**, cliquez sur **Partager le fichier protégé**, puis de nouveau sur **Partager le fichier protégé** :

    ![](../Image/AzRMSUserInstructions_ShareProtectedRibbon2013.png)

2.  Dans la boîte de dialogue **Partager le fichier protégé**, sélectionnez **Visionneuse – Affichage uniquement** :

    ![](../Image/AzRMS_SharedProtected_ViewerOnly.PNG)

3.  Sélectionnez **M'autoriser à révoquer de suite l'accès à ces documents** :

    ![](../Image/AzRMS_SharedProtected_InstantRevoke.PNG)

4.  Sélectionnez **M'envoyer un message électronique quand quelqu'un tente d'ouvrir ce document** :

    ![](../Image/AzRMS_SharedProtected_EmailMe.PNG)

5.  Cliquez sur **Envoyer maintenant** :

    ![](../Image/AzRMS_ShareProtected_SendNow.PNG)

Quand une personne mentionnée sur la ligne **À**, **Cc**ou **Cci** reçoit ce courrier électronique, elle voit un message contenant des instructions sur la manière de lire le fichier joint *&lt;nom du type de document Office&gt;*.Elle peut lire le document sur de nombreux appareils tels que iPad, iPhone, tablettes et téléphones Android, ordinateurs Mac et ordinateurs Windows.

Utilisez le [portail de suivi de document](https://track.azurerms.com/) pour savoir si et quand elle ouvre le &lt;nom du type de document Office&gt; joint.Envisagez de la contacter à l'aide d'un appel téléphonique de suivi dès que vous voyez qu'elle a ouvert le &lt;nom du type de document Office&gt;.

**Vous avez besoin d'aide ?**

-   Pour plus d'informations :

    -   [Protéger un fichier que vous partagez par courrier électronique](https://technet.microsoft.com/library/dn574735%28v=ws.10%29.aspx)

    -   [Suivre et révoquer vos documents](https://technet.microsoft.com/library/dn986611.aspx)

-   Contactez le support technique :

    -   *&lt;coordonnées&gt;*

### Exemple de documentation utilisateur
![](../Image/AzRMS_ExampleBanner.png)

##### Comment partager une liste de prix avec votre client

1.  Créez votre message électronique en spécifiant les adresses de messagerie de votre client, tapez votre message, puis joignez la dernière liste de prix au message électronique.Ensuite, sous l'onglet **MESSAGE**, dans le groupe **RMS**, cliquez sur **Partager le fichier protégé**, puis de nouveau sur **Partager le fichier protégé** :

    ![](../Image/AzRMSUserInstructions_ShareProtectedRibbon2013.png)

2.  Dans la boîte de dialogue **Partager le fichier protégé**, sélectionnez **Visionneuse – Affichage uniquement** :

    ![](../Image/AzRMS_SharedProtected_ViewerOnly.PNG)

3.  Sélectionnez **M'autoriser à révoquer de suite l'accès à ces documents** :

    ![](../Image/AzRMS_SharedProtected_InstantRevoke.PNG)

4.  Sélectionnez **M'envoyer un message électronique quand quelqu'un tente d'ouvrir ce document** :

    ![](../Image/AzRMS_SharedProtected_EmailMe.PNG)

5.  Cliquez sur **Envoyer maintenant** :

    ![](../Image/AzRMS_ShareProtected_SendNow.PNG)

Quand une personne mentionnée sur la ligne **À**, **Cc**ou **Cci** reçoit ce courrier électronique, elle voit un message contenant des instructions sur la manière de lire la liste de prix jointe.Elle peut lire le document sur de nombreux appareils tels que iPad, iPhone, tablettes et téléphones Android, ordinateurs Mac et ordinateurs Windows.

Utilisez le [portail de suivi de document](https://track.azurerms.com/) pour savoir si et quand elle ouvre la liste de prix jointe.Envisagez de la contacter à l'aide d'un appel téléphonique de suivi dès que vous voyez qu'elle a ouvert la liste de prix.

**Vous avez besoin d'aide ?**

-   Pour plus d'informations :

    -   [Protéger un fichier que vous partagez par courrier électronique](https://technet.microsoft.com/library/dn574735%28v=ws.10%29.aspx)

    -   [Suivre et révoquer vos documents](https://technet.microsoft.com/library/dn986611.aspx)

-   Contactez le support technique :

    -   Adresse électronique : helpdesk@vanarsdelltd.com

