---
description: na
keywords: na
title: Preparing for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: afbca2d6-32a7-4bda-8aaf-9f93f5da5abc
---
# Pr&#233;paration pour Azure Rights Management
Après avoir souscrit un abonnement au cloud et avoir assigné à votre organisation un compte pour [!INCLUDE[o365_1](../Token/o365_1_md.md)] ou Azure Active Directory, vous êtes prêt à activer le service [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)].

Toutefois, commencez par vous assurer que les éléments suivants sont en place :

-   Les comptes d’utilisateurs et groupes du cloud créés manuellement ou qui sont automatiquement créés et synchronisés par les services de domaine Active Directory (AD DS).

    Lorsque vous synchronisez vos comptes et groupes locaux, certains attributs ne doivent pas être synchronisés. Pour obtenir la liste des attributs qui doivent être synchronisés pour Azure RMS, voir cette [section relative à Azure RMS](https://azure.microsoft.com/documentation/articles/active-directory-aadconnectsync-attributes-synchronized/) de la documentation d'Azure Active Directory. Pour faciliter le déploiement, nous vous conseillons d'utiliser [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) pour connecter vos répertoires locaux à Azure Active Directory, mais vous pouvez utiliser toute méthode de synchronisation d'annuaires permettant d'obtenir le même résultat.

-   Les groupes à extension messagerie du cloud que vous utiliserez avec Rights Management. Ceux-ci peuvent être des groupes intégrés ou des groupes créés manuellement contenant les utilisateurs qui utiliseront Rights Management.

    Si vous avez Exchange Online, vous pouvez créer et utiliser des groupes à extension messagerie à l’aide du Centre d’administration Exchange. Si vous disposez d’AD DS et synchronisez sur Azure AD, vous pouvez créer et utiliser des groupes à extension messagerie qui sont des groupes de sécurité ou de distribution.

## Activation de Rights Management
Par défaut, [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] est désactivé lorsque vous créez votre compte [!INCLUDE[o365_2](../Token/o365_2_md.md)] ou Azure AD. Pour activer [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] pour votre organisation, vous devez activer le service. Pour plus d'informations, consultez [Activation d'Azure Rights Management](../Topic/Activating_Azure_Rights_Management.md).

## Voir aussi
[Configuration d'Azure Rights Management](../Topic/Configuring_Azure_Rights_Management.md)

