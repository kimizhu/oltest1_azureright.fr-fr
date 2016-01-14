---
description: na
keywords: na
title: Rights Management sharing application: Version release history
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6751bd90-959f-4eba-91ed-6588ac983762
---
# Application de partage Rights Management&#160;: Historique de publication des versions
L’équipe Rights Management met régulièrement à jour l’application de partage du même nom à l’aide de correctifs et de nouvelles fonctionnalités. Pour déterminer les nouveautés ou modifications apportées à une version, utilisez les informations suivantes. La dernière version est répertoriée en première position.

Les versions antérieures au 1er janvier 2015 ne sont pas répertoriées.

> [!NOTE]
> Si vous avez des commentaires ou une question concernant l’application de partage RMS, envoyez un message électronique à [AskIPTeam](mailto:AskIPTeam@microsoft.com?subject=RMS%20sharing%20app:%20Feedback%20or%20question).

## Version 1.0.2004.0
**Publiée le** : 11/12/2015

**Correctifs** :

-   Améliorations pour les messages d’erreur (précision et clarté).

-   Amélioration des performances de chiffrement et de déchiffrement de contenu.

**Nouvelles fonctionnalités** :

-   Prise en charge de l’installation sans intervention de l’administrateur, afin que des utilisateurs standard puissent installer l’application de partage RMS.

    Certaines restrictions s’appliquent aux utilisateurs standards exécutant Office 2010. Pour plus d’informations, voir la section [Si vous n’êtes pas administrateur local et utilisez Office 2010](../Topic/Download_and_install_the_Rights_Management_sharing_application.md#BKMK_SetupOffice2010) des instructions utilisateur [Télécharger et installer l'application de partage Rights Management](../Topic/Download_and_install_the_Rights_Management_sharing_application.md).

## Version 1.0.1908.0
**Publiée le** : 16/9/2015

**Correctifs** :

-   Prise en charge de Multi-Factor Authentication (MFA) pour Azure RMS, ayant également pour effet d’éliminer la dépendance vis-à-vis de l’Assistant de connexion Microsoft pour les applications qui utilisent l’authentification moderne.

    Pour plus d’informations, voir la section [Multi-Factor Authentication (MFA) et Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_MFA) dans [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md).

## Version 1.0.1784.0
**Publiée le** : 30/7/2015

**Correctifs** :

-   La valeur par défaut de l’intervalle d’actualisation pour les modèles de stratégie des droits est réduite de 7 à 1 jour.

-   Petit nombre de bogues mineurs et régressions.

## Version 1.0.1770.0
**Publiée le** : 25/4/2015

**Correctifs** :

-   Désormais, seul le propriétaire et les copropriétaires d’un fichier peuvent supprimer sa protection. Des coauteurs ne le peuvent pas.

-   Des fichiers se trouvant sur un partage réseau peuvent désormais être protégés.

**Nouvelles fonctionnalités** :

-   Prise en charge du suivi et de la révocation de documents. Pour plus d’informations, voir [Suivre et révoquer vos documents lorsque vous utilisez l’application de partage RMS](../Topic/Track_and_revoke_your_documents_when_you_use_the_RMS_sharing_application.md).

-   Prise en charge de modèle lorsque vous choisissez **Partage protégé** :

    -   Vous pouvez désormais sélectionner des modèles.

    -   À la place du curseur, vous voyez une zone de liste contenant des modèles et des autorisations personnalisées.

    -   Vous ne voyez plus les options **Autoriser l’utilisation sur tous les périphériques** et **Appliquer les restrictions d’utilisation**. Au lieu de cela, l’option **Protection générique** est automatiquement sélectionnée en fonction du type de fichier.

    Pour plus d’informations, voir [Options de boîte de dialogue pour l'application de partage Rights Management](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md).

## Version 1.0.1667.0
**Publiée le** : 19/1/2015

**Correctifs** :

-   Prise en charge des polices de caractères chinois dans la visionneuse PPDF de l’application de partage RMS.

-   Gestion des erreurs et messagerie améliorées.

-   Résolution d’un problème lié à la notification automatique de mise à jour quand une version plus récente de l’application est disponible en téléchargement.

**Nouvelles fonctionnalités** :

-   **Prise en charge de plusieurs domaines de messagerie au sein de votre organisation** : Si vous utilisez AD RMS et que des utilisateurs au sein de votre organisation disposent de plusieurs domaines de messagerie, cette mise à jour leur permet de consommer du contenu protégé par des utilisateurs d’autres domaines au sein de votre organisation. Pour plus d’informations, voir la section [AD RMS uniquement : prise en charge de plusieurs domaines de messagerie au sein de votre organisation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_FederatedDomains) du [guide de l'administrateur de l'application de partage Rights Management](../Topic/Rights_Management_sharing_application_administrator_guide.md).

