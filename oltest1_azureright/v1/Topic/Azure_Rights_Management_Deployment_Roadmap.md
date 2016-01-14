---
description: na
keywords: na
title: Azure Rights Management Deployment Roadmap
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 086600c2-c5d8-47ec-a4c0-c782e1797486
---
# feuille de route pour le d&#233;ploiement d&#39;Azure Rights Management
Procédez comme suit pour préparer, implémenter et gérer la Gestion des droits Azure (RMS) pour votre organisation.

Toutefois, si vous souhaitez uniquement tester rapidement Azure RMS pour vous-même, au lieu de le déployer dans un environnement de production, consultez [Didacticiel de démarrage rapide pour la Gestion des droits Azure](../Topic/Quick_Start_Tutorial_for_Azure_Rights_Management.md).

> [!IMPORTANT]
> Avant de suivre les étapes suivantes, prenez le temps de consulter [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md).

## Étape 1 : vérifier que vous disposez d'un abonnement incluant la Gestion des droits Azure
Il existe plusieurs types d'abonnement incluant [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)]. Consultez la section [Abonnements au cloud prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) de la rubrique [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md), et vérifiez que votre abonnement inclut les fonctionnalités que vous souhaitez utiliser au sein de votre organisation en vous reportant à la table figurant dans [Comparaison des offres de Rights Management Services (RMS)](https://technet.microsoft.com/dn858608).

## Étape 2 : préparer votre compte de locataire à l'utilisation de la Gestion des droits
Avant de commencer à utiliser [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)], effectuez la préparation suivante :

1.  Assurez-vous que votre client Azure ou Office 365 contient les comptes et groupes d'utilisateurs qu'Azure RMS utilisera pour authentifier les utilisateurs de votre organisation. Si nécessaire, créez ces comptes et groupes, ou synchroniser-les à partir de votre répertoire local. Pour plus d'informations, consultez [Préparation pour Azure Rights Management](../Topic/Preparing_for_Azure_Rights_Management.md).

2.  Déterminez si vous voulez que Microsoft gère votre clé de locataire (option par défaut) ou si vous voulez la générer et la gérer vous-même (option BYOK, Bring Your Own Key). Notez que vous ne pouvez pas actuellement utiliser l'option BYOK si vous utilisez Exchange Online. Pour plus d'informations, consultez [Planification et implémentation de la clé de locataire Azure Rights Management](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md).

3.  Installez le module Windows PowerShell pour [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] sur au moins un ordinateur doté d’un accès à Internet. Vous pouvez effectuer cette étape maintenant ou ultérieurement. Pour plus d'informations, consultez [Installation de Windows PowerShell pour Azure Rights Management](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md).

4.  Si vous utilisez actuellement des services Rights Management locaux : Effectuez une migration pour déplacer les clés, modèles et URL dans le cloud. Pour plus d'informations, consultez [Migration d'AD RMS vers Azure Rights Management](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md).

5.  Activez la Gestion des droits pour pouvoir commencer à utiliser le service. Si un déploiement échelonné est nécessaire, configurez les contrôles d'intégration pour restreindre l'utilisation à des utilisateurs spécifiques. Pour plus d'informations, consultez [Activation d'Azure Rights Management](../Topic/Activating_Azure_Rights_Management.md).

Configurez éventuellement les éléments suivants :

-   Des modèles personnalisés si les modèles de stratégie de droits par défaut ne suffisent pas à votre organisation. Vous pouvez effectuer cette étape maintenant ou ultérieurement. Pour plus d'informations, consultez [Configuration de modèles personnalisés pour Azure Rights Management](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md).

-   La journalisation de l'utilisation pour pouvoir surveiller l'usage que fait votre organisation de la Gestion des droits. Vous pouvez effectuer cette étape maintenant ou ultérieurement. Pour plus d'informations, consultez [Journalisation et analyse de l'utilisation d'Azure Rights Management](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md).

## Étape 3 : configurer vos applications et services pour Rights Management
La configuration de vos applications peut inclure l'installation de l'application de partage Microsoft Rights Management et l'activation de la prise en charge des fonctionnalités de Gestion des droits relatifs à l'information (IRM) dans SharePoint Online ou Exchange Online. Pour plus d'informations, consultez [Configuration d'applications pour Azure Rights Management](../Topic/Configuring_Applications_for_Azure_Rights_Management.md).

Si vous avez des services informatiques, tels que des solutions de protection contre la perte de données (DLP), des passerelles de chiffrement de contenu (CEG) et autres logiciels anti-programme malveillant, chargés d'inspecter les fichiers qu'Azure RMS doit protéger, configurez les comptes de service en tant que super utilisateurs pour Azure RMS. Pour plus d'informations, consultez [Configuration de super utilisateurs pour Azure Rights Management et les services de découverte ou la récupération de données](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md).

Si vous voulez utiliser des services locaux avec la Gestion des droits Azure, installez et configurez le connecteur Microsoft Rights Management. Pour plus d'informations, consultez [Déploiement du connecteur Azure Rights Management](../Topic/Deploying_the_Azure_Rights_Management_Connector.md).

## Étape 4 : publier et utiliser du contenu protégé par des droits
Vous êtes maintenant prêt à publier et à consommer du contenu protégé, ainsi qu'à journaliser la manière dont votre entreprise utilise Rights Management. Pour plus d'informations, consultez [Utilisation d'Azure Rights Management](../Topic/Using_Azure_Rights_Management.md).

## Étape 5 : administrer la Gestion des droits pour votre compte de locataire selon les besoins
Pour vous aider à utiliser [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)], vous pouvez faire appel au module [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] pour Windows PowerShell, qui est utile pour écrire ou automatiser les changements administratifs. Pour plus d'informations, consultez [Administration de la Gestion des droits Azure à l'aide de Windows PowerShell](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md).

## Voir aussi
[Configuration d'Azure Rights Management](../Topic/Configuring_Azure_Rights_Management.md)

