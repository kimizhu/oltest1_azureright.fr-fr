---
description: na
keywords: na
title: Activating Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f8707e01-b239-4d1a-a1ea-0d1cf9a8d214
---
# Activation d&#39;Azure Rights Management
Lorsque vous activez [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS), votre organisation peut commencer à protéger des données importantes à l'aide d'applications et services prenant en charge cette solution de protection des informations. Les administrateurs peuvent également gérer et surveiller les fichiers et messages électroniques protégés de votre organisation. Vous devez activer [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] avant de commencer à utiliser les fonctionnalités de gestion des droits relatifs à l'information (IRM) dans Office, SharePoint et Exchange pour protéger tout fichier sensible ou confidentiel.

Si vous souhaitez en savoir plus sur la gestion des droits Azure avant d'activer le service (par exemple, les problèmes métier qu'il résout, certains scénarios d'utilisation classiques et son fonctionnement), consultez [Qu'est-ce qu'Azure Rights Management ?](../Topic/What_is_Azure_Rights_Management_.md).

> [!IMPORTANT]
> Avant d'activer [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)], assurez-vous que votre organisation dispose d'un plan de services incluant les services [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]. Si ce n'est pas le cas, vous ne pouvez pas activer Azure RMS.
> 
> Pour plus d'informations, consultez la section [Abonnements au cloud prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) de la rubrique [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md).

Une fois Azure RMS activé, tous les utilisateurs de votre organisation peuvent appliquer la protection des informations à leurs fichiers, et tous les utilisateurs peuvent ouvrir (consommer) des fichiers protégés par Azure RMS. Toutefois, si vous préférez, vous pouvez restreindre les personnes autorisées à appliquer la protection des informations, en utilisant des contrôles d'intégration pour un déploiement échelonné. Pour plus d'informations, consultez la section [Configuration de contrôles d'intégration pour un déploiement échelonné](../Topic/Activating_Azure_Rights_Management.md#BKMK_OnboardingControls) de cette rubrique.

## Activation de Rights Management
Exécutez l'une des procédures suivantes pour activer [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)].

> [!TIP]
> Vous pouvez également utiliser l'applet de commande Windows PowerShell [Enable-Aadrm](http://msdn.microsoft.com/library/windowsazure/dn629412.aspx) pour activer [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)].

#### Pour activer Rights Management à partir du centre d’administration Office 365

1.  Après avoir souscrit un plan Office 365 incluant Rights Management, [connectez-vous à Office 365 avec votre compte professionnel ou scolaire](https://portal.office.com/) qui est administrateur de votre déploiement d’Office 365.

2.  Si le centre d'administration Office 365 ne s'affiche pas automatiquement, sélectionnez l'icône de lancement d'application dans l'angle supérieur gauche, puis choisissez **Admin**. La vignette **Admin** s'affiche uniquement pour les administrateurs Office 365.

    > [!TIP]
    > Pour obtenir l'aide du centre d'administration, consultez [À propos du Centre d'administration Office 365 - Aide de l'administrateur](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547).

3.  Dans le volet gauche, développez **PARAMÈTRES DE SERVICE**.

4.  Cliquez sur **Rights Management**.

    > [!NOTE]
    > Si cette option n'est pas disponible, il est possible que votre version de produit ou votre plan de services ne prenne pas en charge Rights Management, ou n'a pas encore été mis à jour pour prendre en charge Rights Management.
    > 
    > Utilisez les informations de la section [Abonnements au cloud prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) de la rubrique [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md) pour confirmer la prise en charge. Si votre version de produit ou votre plan de services est pris en charge mais que l'option Gestion des droits n'est pas disponible, il est possible que le service n'ait pas encore été mis à jour. Pour obtenir de l'aide, envoyez un courrier électronique à [askipteam](mailto:askipteam@microsoft.com?subject=I%20cannot%20activate%20RMS).

5.  Dans la page **RIGHTS MANAGEMENT**, cliquez sur **Gérer**.

6.  Dans la page **Rights Management**, cliquez sur **Activer**.

7.  À l'invite **Voulez-vous activer Rights Management ?**, cliquez sur **Activer**.

Vous devez maintenant voir **Rights Management est activé**, ainsi qu'une option de désactivation.

#### Pour activer Rights Management à partir du portail Azure Classic

1.  Après avoir créé votre compte Azure, [connectez-vous au portail Azure Classic](http://go.microsoft.com/fwlink/p/?LinkID=275081).

2.  Dans le volet gauche, cliquez sur **Active Directory**.

3.  Dans la page **Active Directory**, cliquez sur **RIGHTS MANAGEMENT**.

4.  Sélectionnez l'annuaire à gérer pour [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)], cliquez sur **Activer**, puis confirmez.

    > [!NOTE]
    > Si une erreur d'activation est levée, il est possible que votre plan de services ou votre version de produit ne prenne pas en charge [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)].
    > 
    > Utilisez les informations de la section [Abonnements au cloud prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) de la rubrique [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md) pour confirmer la prise en charge RMS. Pour obtenir de l'aide, envoyez un courrier électronique à [askipteam](mailto:askipteam?subject=I%20cannot%20activate%20RMS).

**Statut de Rights Management** doit désormais afficher l’état **Actif** et l’option **ACTIVER** est remplacée par **DÉSACTIVER**.

### Descriptions et valeurs d’état du service Rights Management dans le portail Azure Classic
En plus de l'état **Actif** qui indique que le service Rights Management est activé et opérationnel, vous pouvez également voir les états **Inactif**, **Indisponible** ou **Non autorisé**.

|Valeur d'état|Description|
|-----------------|---------------|
|**Active**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] est activé et opérationnel.|
|**Inactif**|[!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] est désactivé et doit être activé pour permettre à votre organisation de protéger les fichiers.|
|**Indisponible**|Le service [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] est indisponible. Réessayez plus tard.|
|**Non autorisé**|Vous n'êtes pas autorisé à consulter l'état du service [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]. Par exemple, votre compte est verrouillé ou vous êtes l'administrateur global du locataire sélectionné.|

## <a name="BKMK_OnboardingControls"></a>Configuration de contrôles d'intégration pour un déploiement échelonné
Si vous ne souhaitez pas que tous les utilisateurs puissent protéger des fichiers immédiatement à l'aide d'Azure RMS, vous pouvez configurer des contrôles d'intégration d'utilisateur à l'aide de la commande Windows PowerShell [Set-AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857521.aspx). Vous pouvez exécuter cette commande avant ou après avoir activé Azure RMS.

> [!IMPORTANT]
> Pour utiliser cette commande, vous devez disposer au moins de la version **2.1.0.0** du [module Azure RMS Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=257721).
> 
> Pour déterminer la version installée, exécutez la commande suivante : **(Get-Module aadrm –ListAvailable).Version**

Par exemple, si vous souhaitez initialement que seuls les administrateurs du groupe « Département informatique » (dont l'ID d'objet est fbb99ded-32a0-45f1-b038-38b519009503) puissent protéger du contenu à des fins de test, utilisez la commande suivante :

```
Set-AadrmOnboardingControlPolicy – SecurityGroupObjectId fbb99ded-32a0-45f1-b038-38b519009503
```
Notez que pour cette option de configuration, vous devez spécifier un groupe. Vous ne pouvez pas spécifier des utilisateurs individuels.

Ou bien, si vous souhaitez vous assurer que seuls les utilisateurs disposant d'une licence appropriée pour utiliser Azure RMS puissent protéger du contenu :

```
Set-AadrmOnboardingControlPolicy -UseRmsUserLicense $true
```
Lorsque vous utilisez ces contrôles d'intégration, tous les utilisateurs de l'organisation peuvent toujours consommer du contenu protégé par votre sous-ensemble d'utilisateurs, mais ils ne peuvent pas appliquer la protection des informations à eux-mêmes à partir d'applications clientes. Par exemple, dans leurs clients Office, ils ne voient pas les modèles par défaut qui sont automatiquement publiés lors de l'activation d'Azure RMS, ou les modèles personnalisés que vous pourriez configurer.  Les applications côté serveur, telles qu'Exchange, peuvent implémenter leurs propres contrôles utilisateur pour l'intégration de RMS et obtenir le même résultat.

## Étapes suivantes
[!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] étant à présent activé pour votre organisation, reportez-vous à la [feuille de route pour le déploiement d'Azure Rights Management](../Topic/Azure_Rights_Management_Deployment_Roadmap.md) pour déterminer si d'autres étapes de configuration peuvent s'avérer nécessaires avant de mettre [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] à disposition des utilisateurs et des administrateurs. Par exemple, vous pouvez utiliser des [modèles personnalisés](http://technet.microsoft.com/library/dn642472.aspx) pour faciliter l'application de la protection des informations aux fichiers, connecter vos serveurs locaux pour utiliser [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] via l'installation du [connecteur RMS](http://technet.microsoft.com/library/dn375964.aspx) et déployer l’[application de partage Rights Management](http://technet.microsoft.com/library/jj585031.aspx) afin de pouvoir protéger n'importe quel type de fichier sur tous les appareils. Les services Office, tels qu'Exchange Online et SharePoint Online, nécessitent une configuration supplémentaire avant que vous puissiez utiliser leurs fonctionnalités de gestion des droits relatifs à l'information (IRM). Toutefois, si aucune étape de configuration supplémentaire n'est requise, consultez la rubrique [Utilisation d'Azure Rights Management](../Topic/Using_Azure_Rights_Management.md) pour savoir comment réussir le déploiement pour votre organisation.

Pour plus d'informations sur la façon dont vos applications fonctionnent avec [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)], consultez [Mode de prise en charge d'Azure Rights Management par les applications](../Topic/How_Applications_Support_Azure_Rights_Management.md).

## Voir aussi
[Configuration d'Azure Rights Management](../Topic/Configuring_Azure_Rights_Management.md)

