---
description: na
keywords: na
title: Download and install the Rights Management sharing application
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2bf09690-9dba-43b7-9e0a-0110915d4081
---
# T&#233;l&#233;charger et installer l&#39;application de partage Rights Management
Pour installer l’application de partage RMS, vous ne devez pas nécessairement être administrateur local. Toutefois, si vous ne l’êtes pas et utilisez Office 2010, il existe quelques limitations. Pour plus d’informations, voir la section [Si vous n’êtes pas administrateur local et utilisez Office 2010](#BKMK_SetupOffice2010) de cette rubrique.

### Pour télécharger et installer l’application de partage Rights Management

1.  Accédez à la page [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) sur le site web Microsoft.

2.  Dans la section **Ordinateurs**, cliquez sur l’icône de l’**application RMS pour Windows** et enregistrez le fichier **Setup.exe** pour installer l’application de partage Microsoft Rights Management.

3.  Double-cliquez sur le fichier Setup.exe qui a été téléchargé. Si vous êtes invité à continuer, cliquez sur **Oui**.

4.  Dans la page **Installer Microsoft RMS**, cliquez sur **Suivant**, puis attendez que l’installation se termine.

    > [!NOTE]
    > L’application de partage RMS nécessite au minimum la version Microsoft .NET Framework 4.0. Le programme d’installation vérifie si elle est installée et, si ce n’est pas le cas, un message comportant un lien pour son installation s’affiche.

5.  Une fois l’installation terminée, cliquez sur **Redémarrer** pour redémarrer votre ordinateur et terminer l’installation. Vous pouvez également cliquer sur **Fermer** et redémarrer l’ordinateur ultérieurement pour terminer l’installation.

Vous pouvez à présent protéger vos fichiers et lire des fichiers protégés par d’autres personnes.

## <a name="BKMK_SetupOffice2010"></a>Si vous n’êtes pas administrateur local et utilisez Office 2010
Si vous vous connectez à votre ordinateur sans disposer de droits d’administration locale, et que le programme d’installation détecte qu’Office 2010 est installé, un message d’avertissement s’affiche, indiquant que certains scénarios ne fonctionnent pas avec cette configuration. Ces scénarios sont les suivants :

-   Si votre organisation utilise Azure RMS plutôt qu’une version locale de RMS :

    -   Les fonctionnalités de Gestion des droits relatifs à l’Information (IRM) d’Office ne sont pas disponibles. Par exemple, l’option **Ne pas transférer** pour les messages électroniques, et les **restrictions d’accès** que vous pouvez définir via les Autorisations dans le menu **Fichier** de Word et Excel. Vous pouvez utiliser l’option Protégé contre le partage accessible dans le ruban, et les options de clic droit de l’Explorateur de fichiers.

-   Si votre organisation utilise une version locale de RMS plutôt qu’Azure RMS :

    -   Vous ne pouvez pas lire un document protégé qui vous est envoyé par un membre d’une autre organisation utilisant Azure RMS.

Si vous n’êtes pas administrateur local et utilisez Office 365 ou Office 2013, vous ne voyez pas ce message et ces scénarios sont pris en charge.

Vous pouvez continuer l’installation avec ces limitations connues. Vous pouvez aussi l’arrêter, puis soit la relancer avec l’option **Exécuter en tant qu’administrateur** lors de l’exécution du fichier Setup.exe à l’étape 3, soit demander à un administrateur de l’installer pour vous. Des administrateurs peuvent [créer un script d’installation](https://technet.microsoft.com/library/dn339003.aspx) qui s’exécute automatiquement.

## Exemples et autres instructions
Pour obtenir des exemples et des instructions concernant l’utilisation de l’application de partage Rights Management, voir les sections suivantes dans le Guide d’utilisation de l’application de partage Rights Management :

-   [Exemples d’utilisation de l’application de partage RMS](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingExamples)

-   [Que souhaitez-vous faire ?](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingInstructions)

## Voir aussi
[Guide d’utilisation de l’application de partage Rights Management](../Topic/Rights_Management_sharing_application_user_guide.md)

