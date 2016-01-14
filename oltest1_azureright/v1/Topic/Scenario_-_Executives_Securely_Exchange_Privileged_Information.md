---
description: na
keywords: na
title: Scenario - Executives Securely Exchange Privileged Information
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e18cf5df-859e-4028-8d19-39b0842df33d
---
# Sc&#233;nario - Des cadres &#233;changent des informations confidentielles
Cette section contient les instructions pour les administrateurs et des directives relatives aux instructions pour les utilisateurs.Vous devez appliquer les instructions pour les administrateurs avant d’informer vos utilisateurs de cette configuration.

## Instructions pour les administrateurs
![](../Image/AzRMS_AdminBanner.png)

Utilisez ces instructions afin que les cadres puissent s’échanger en toute sécurité des courriers électroniques et des pièces jointes et pour que les stratégies limitent automatiquement l’accès aux cadres, sans que ceux-ci aient à réaliser d’action spéciale.Les courriers électroniques et les pièces jointes seront protégés par Azure Rights Management.

Les instructions conviennent pour l’ensemble des situations suivantes :

-   Les cadres s’échangent des informations confidentielles qui ne doivent pas être partagées avec d’autres utilisateurs.

-   Les cadres n’ont pas à changer leurs habitudes lorsqu’ils envoient ces messages. Ils doivent simplement les envoyer à une adresse électronique professionnelle plutôt qu’une adresse personnelle.

## Conditions requises pour ce scénario
Pour pouvoir appliquer les instructions de ce scénario, les éléments suivants doivent être en place :

|Check|Condition requise|Si vous avez besoin d’informations supplémentaires|
|---------|---------------------|------------------------------------------------------|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Vous avez préparé des comptes et des groupes pour Office 365 ou Azure Active Directory.<br /><br />-   Un groupe nommé **Cadres** ayant accès aux e-mails<br />-   Tous les cadres sont membres du groupe **Cadres**|[Préparation pour Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Votre clé de locataire Azure Rights Management est gérée par Microsoft ; vous n’utilisez pas BYOK|[Planification et implémentation de la clé de locataire Azure Rights Management](https://technet.microsoft.com/library/dn440580.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Azure Rights Management est activé|[Activation d'Azure Rights Management](https://technet.microsoft.com/library/jj658941.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Exchange Online est activé pour Azure Rights Management|Développez la section [Exchange Online : Configuration IRM](https://technet.microsoft.com/library/jj585031.aspx) dans [Configuration des applications pour Azure Rights Management](https://technet.microsoft.com/library/jj585031.aspx).|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Vous avez configuré un modèle personnalisé comme décrit ci-après|[Configuration de modèles personnalisés pour Azure Rights Management](https://technet.microsoft.com/library/dn642472.aspx)|
|![](../Image/4d269a30-a873-45c5-87de-30ee6558e7b0.gif)|Vous avez configuré une règle de protection de transport pour IRM, comme décrit ci-après|[Créez une règle de protection de transport](https://technet.microsoft.com/library/dd302432.aspx)|

#### Pour configurer le modèle personnalisé pour les e-mails des cadres :

1.  Dans le portail Azure : Créez un nouveau modèle personnalisé pour Azure Rights Management qui contient ces valeurs et ces paramètres :

    -   Nom : **Cadres**

    -   Droits :  Accordez au groupe de messagerie Cadres des droits de **Copropriétaire**

2.  Publiez le nouveau modèle.

3.  Actualisez les modèles pour Exchange Online à l’aide de la commande Windows PowerShell pour Exchange Online :

    ```
    Import-RMSTrustedPublishingDomain -Name "RMS Online -1" -RefreshTemplates –RMSOnline
    ```

#### Pour configurer et protéger automatiquement les e-mails envoyés et reçus par les cadres :

-   Dans le centre d’administration Exchange : Créez une nouvelle règle de flux de messagerie qui contient ces valeurs et ces paramètres :

    -   Cliquez sur l’icône Nouveau, puis sélectionnez **Appliquer la protection des droits aux messages**

    -   Sur la page **nouvelle règle** :

        -   Spécifiez un nom, comme **Appliquer les modèles Cadres aux e-mails des cadres**

        -   Pour **Appliquer cette règle si**, sélectionnez **L’expéditeur** .... **est un membre de ce groupe** et sélectionnez **Cadres**.

        -   Cliquez sur **ajouter une condition**, sélectionnez **Le destinataire** .... **est un membre de ce groupe** et sélectionnez **Cadres**.

        -   Pour **Actions**, assurez-vous que **Appliquer la protection des droits au message avec** est sélectionné et cliquez sur **Sélectionner une option** pour sélectionner le modèle **Cadres**.

        -   Veillez à ce que **Appliquer** soit sélectionné pour **Choisir un mode pour cette règle**.

        -   Cliquez sur **Enregistrer**.

## Instructions pour l’utilisateur
Il n’existe aucune instruction spécifique destinée aux utilisateurs pour ce scénario, car la protection des courriers électroniques envoyés et reçus par les cadres ne nécessite aucune action spéciale de leur part.Les messages électroniques et les pièces jointes sont automatiquement protégés de manière à ce que seuls les membres du groupe Cadres puissent y accéder.Toutefois, vous devrez informer les cadres et le support technique que ces messages électroniques seront automatiquement protégés et de quelle manière cela peut en limiter leur utilisation.Par exemple, ces messages ne peuvent pas être lus par d’autres personnes s’ils, ou leurs pièces jointes, sont transférés par la suite à d’autres utilisateurs.

L’exemple suivant peut être envoyé comme message électronique standard aux cadres, après qu’Exchange Online a été configuré pour ce scénario.

### Exemple de documentation utilisateur
![](../Image/AzRMS_ExampleBanner.png)

##### Annonce de l’équipe informatique : Les e-mails des cadres sont désormais automatiquement protégés

-   Dès lors, chaque fois que vous envoyez des e-mails à un autre cadre de l’entreprise, le contenu de ces messages et les pièces jointes seront automatiquement protégés de manière à ce que seul un autre cadre de l’entreprise puisse y avoir accès et lire, imprimer ou encore copier les informations.Cette restriction s’applique même si vous transférez le message à d’autres personnes ou enregistrez les pièces jointes.Cette protection permet d’éviter la perte de données pour les informations confidentielles ou sensibles.

    Notez que si vous souhaitez que d’autres utilisateurs puissent lire et modifier les informations contenues dans ces e-mails, vous devez les envoyer séparément.

    Lors de l’envoi d’informations confidentielles de votre société à un autre cadre, pensez à les envoyer à une adresse de messagerie professionnelle et non à une adresse personnelle.

**Vous avez besoin d'aide ?**

-   Contactez le support technique : helpdesk@vanarsdelltd.com

