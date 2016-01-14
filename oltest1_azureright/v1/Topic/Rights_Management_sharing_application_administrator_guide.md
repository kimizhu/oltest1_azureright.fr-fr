---
description: na
keywords: na
title: Rights Management sharing application administrator guide
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d9992e30-f3d1-48d5-aedc-4e721f7d7c25
---
# guide de l&#39;administrateur de l&#39;application de partage Rights Management
Utilisez les informations suivantes si vous êtes responsable de l'application de partage Microsoft Rights Management sur un réseau d'entreprise, ou si vous souhaitez des informations plus techniques que celles qui figurent dans le [Guide d’utilisation de l’application de partage Rights Management](../Topic/Rights_Management_sharing_application_user_guide.md) ou le [Forum Aux Questions sur l’application de partage Microsoft Rights Management pour Windows](http://go.microsoft.com/fwlink/?LinkId=303971) :

-   [Déploiement automatique de l'application de partage Microsoft Rights Management](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ScriptedInstall)

    -   [Vérification de la réussite de l'installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted)

    -   [Commandes de désinstallation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_uninstallscripted)

    -   [Suppression des mises à jour automatiques](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SuppressAutomaticUpdates)

    -   [Azure RMS uniquement : configuration du suivi des documents](#BKMK_DocumentTracking)

    -   [AD RMS uniquement : prise en charge de plusieurs domaines de messagerie au sein de votre organisation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_FederatedDomains)

-   [Présentation technique de l'application de partage Microsoft Rights Management](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_AdminOverview)

    -   [Niveaux de protection : natif et générique](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_LevelsofProtection)

    -   [Types de fichier pris en charge et extensions de nom de fichier](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SupportFileTypes)

    -   [Modification du niveau de protection par défaut des fichiers](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ChangeDefaultProtection)

> [!TIP]
> Si vous ne connaissez pas l'application de partage RMS ou que vous recherchez plus d'informations, consultez [How RMS protects all file types – by using the RMS sharing app](https://curah.microsoft.com/191031/how-rms-protects-all-file-types-by-using-the-rms-sharing-app).

L'application de partage RMS est mieux adaptée au travail avec Azure RMS, car cette configuration de déploiement prend en charge l'envoi de pièces jointes protégées à des utilisateurs d'une autre organisation et des options telles que les notifications par courrier électronique et le suivi des document avec révocation.  Toutefois, elle fonctionne également avec la version locale, AD RMS, avec certaines limitations. Pour une comparaison complète des fonctionnalités prises en charge par Azure RMS et AD RMS, voir [Comparaison d'Azure Rights Management avec AD RMS](https://technet.microsoft.com/library/jj739831.aspx). Si vous avez AD RMS et que vous souhaitez migrer vers Azure RMS, consultez [Migration d'AD RMS vers Azure Rights Management](https://technet.microsoft.com/library/dn858447.aspx).

## <a name="BKMK_ScriptedInstall"></a>Déploiement automatique de l'application de partage Microsoft Rights Management
La version Windows de l'application de partage RMS prend en charge une installation scriptée, ce qui la rend appropriée pour les déploiements d'entreprise.

Les seules conditions préalables à l'installation sont que les ordinateurs exécutent une version minimale de Windows 7 Service Pack 1 et que Microsoft Framework, version minimale 4.0, soit installé. Si vous devez installer Microsoft .NET Framework 4.0, vous pouvez le [télécharger pour installation à partir du Centre de téléchargement Microsoft](http://www.microsoft.com/download/details.aspx?id=17718).

#### Pour télécharger l’application de partage RMS pour un déploiement automatique

1.  Accédez à la page [Microsoft Rights Management sharing application for Windows - Français](http://www.microsoft.com/download/details.aspx?id=40857) dans le Centre de téléchargement Microsoft, puis cliquez sur **Télécharger**.

2.  Sélectionnez et téléchargez les fichiers dont vous avez besoin. Il existe deux packages d'installation client : un pour Windows 64 bits (Microsoft Rights Management sharing application x64.zip) et l'autre pour Windows 32 bits (Microsoft Rights Management sharing application x86.zip)

3.  Extrayez les fichiers des packages d'installation compressés, par exemple en double-cliquant dessus. Copiez ensuite les fichiers extraits à un emplacement réseau auquel les ordinateurs clients peuvent accéder.

Les packages d'installation pour l'application de partage RMS prennent en charge différents scénarios de déploiement et incluent les éléments suivants :

|Description|Scénario de déploiement|
|---------------|---------------------------|
|Assistant de connexion Microsoft Online Services|Requis pour les éléments suivants :<br /><br />-   Office 2010 et Azure RMS<br />-   Office 2013 et Azure RMS si vous n'avez pas installé la [mise à jour du 9 juin 2015 pour Office 2013](https://support.microsoft.com/kb/3054853) (KB3054853)|
|Correctif pour Office (KB2596501)|Requis pour les éléments suivants :<br /><br />-   Office 2010 et Azure RMS<br />-   Office 2010 et Active Directory RMS|
|Correctif d'activation du client AD RMS 1.0 pour le travail avec Azure RMS (KB2843630)|Requis pour les éléments suivants :<br /><br />-   Office 2010 et Azure RMS<br />-   Office 2010 et Active Directory RMS|
|Client AD RMS et application de partage RMS|Requis pour les éléments suivants :<br /><br />-   Office 2016 ou Office 2013 et Azure RMS ou Active Directory RMS<br />-   Office 2010 et Azure RMS<br />-   Office 2010 et Active Directory RMS<br />-   Application de partage RMS et complément Office uniquement|
|Complément Office pour le ruban|Requis pour les éléments suivants :<br /><br />-   Office 2016 ou Office 2013 et Azure RMS ou Active Directory RMS<br />-   Office 2010 et Azure RMS<br />-   Office 2010 et Active Directory RMS<br />-   Application de partage RMS et complément Office uniquement|
|Outil de préparation Azure Active Directory Rights Management|Requis pour les éléments suivants :<br /><br />-   Office 2010 et Azure RMS|
Utilisez les procédures suivantes afin d'identifier les commandes nécessaires au déploiement de l'application de partage RMS pour les scénarios de déploiement suivants :

-   **Office 2016 ou Office 2013 et Azure RMS ou Active Directory RMS**

    Vos utilisateurs exécutent Office 2016 ou Office 2013, votre organisation utilise Azure RMS ou Active Directory RMS et les utilisateurs collaborent avec d'autres organisations qui utilisent Azure RMS ou Active Directory RMS.

-   **Office 2010 et Azure RMS**

    Vos utilisateurs exécutent Office 2010, votre organisation utilise Azure RMS et les utilisateurs collaborent avec d'autres organisations qui utilisent Azure RMS ou Active Directory RMS.

-   **Office 2010 et Active Directory RMS**

    Vos utilisateurs exécutent Office 2010, votre organisation utilise AD RMS et les utilisateurs collaborent avec d'autres organisations qui utilisent Azure RMS.

-   **Application de partage RMS et complément Office uniquement**

    Vos utilisateurs exécutent Office 2016, Office 2013 ou Office 2010, votre organisation utilise AD RMS et les utilisateurs n'ont pas besoin de collaborer avec d'autres organisations qui utilisent Azure RMS. Cette installation vous permet d'installer uniquement l’application de partage et le complément Office.

> [!NOTE]
> Dans ces scénarios, si votre organisation exécute AD RMS, vos utilisateurs peuvent recevoir du contenu protégé d'autres organisations qui utilisent Azure RMS, mais ils ne peuvent pas envoyer du contenu protégé aux utilisateurs d'une organisation qui utilise Azure RMS. Toutefois, si votre organisation exécute Azure RMS, vos utilisateurs peuvent envoyer et recevoir du contenu protégé d'autres organisations.

Pour terminer l'installation relative à chaque procédure, vous devez redémarrer l'ordinateur. Vous pouvez lancer un redémarrage automatique à l'aide d'une commande telle que shutdown /i.

#### Pour déployer l'application de partage RMS pour Office 2016 ou Office 2013 et Azure RMS ou Active Directory RMS

-   Sur chaque ordinateur sur lequel vous souhaitez installer l'application de partage RMS et les composants associés, exécutez la commande suivante avec des privilèges élevés :

    ```
    setup.exe /s
    ```

Pour vérifier que l'opération a réussi, voir la section [Vérification de la réussite de l'installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) de cette rubrique.

#### Pour déployer l'application de partage RMS pour Office 2010 et Azure RMS

1.  Vous devez être l'administrateur général de votre locataire Office 365 ou Azure Active Directory pour pouvoir obtenir l'URL du service de certification de votre organisation en exécutant l'outil de préparation Active Directory Azure Rights Management. Vous ne devez exécuter cet outil qu'une seule fois, sur un seul ordinateur. Vous allez utiliser l'URL du service de certification lors de l'installation de l'application de partage RMS sur chaque ordinateur :

    1.  Connectez-vous à un ordinateur à l'aide d'un compte d'administrateur local.

    2.  Sur cet ordinateur, [téléchargez et installez l'Assistant d'inscription en ligne Microsoft](http://www.microsoft.com/download/details.aspx?id=28177).

    3.  Exécutez la commande suivante pour afficher l'URL du service de certification à l'écran, que vous pouvez ensuite copier et enregistrer pour l'étape suivante :

        -   Pour Windows 8.1 et Windows 8, 64 bits :

            ```
            x64\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Pour Windows 8.1 et Windows 8, 32 bits :

            ```
            X86\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Pour Windows 7, 64 bits :

            ```
            x64\win7\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        > [!NOTE]
        > Cette commande peut vous inviter à entrer vos informations d'identification pour Azure. Si l'ordinateur n'est pas joint à un domaine, ces informations vous seront demandées. Si l'ordinateur est joint à un domaine, l'outil devrait pouvoir utiliser les informations d'identification mises en cache.

2.  Sur chaque ordinateur sur lequel vous allez installer l'application de partage RMS, exécutez la commande suivante avec des privilèges élevés :

    ```
    setup.exe /s /configureO2010Admin /certificationUrl <certification_url>
    ```

3.  Sur chaque ordinateur sur lequel vous allez installer l'application de partage RMS, les utilisateurs doivent exécuter la commande suivante (aucun besoin de privilèges élevés). Il existe différentes manières d'effectuer cette opération, y compris en demandant aux utilisateurs d'exécuter la commande (par exemple, un lien dans un message électronique ou un lien sur le portail du support technique), ou vous pouvez l'ajouter à leur script d'ouverture de session :

    ```
    bin\RMSSetup.exe /configureO2010Only
    ```

Pour vérifier que l'opération a réussi, voir la section [Vérification de la réussite de l'installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) de cette rubrique.

#### Pour déployer l'application de partage RMS pour Office 2010 et Active Directory RMS

1.  Sur chaque ordinateur sur lequel vous allez installer l'application de partage RMS, exécutez la commande suivante avec des privilèges élevés :

    ```
    setup.exe /s /configureO2010Admin
    ```

2.  Sur chaque ordinateur sur lequel vous allez installer l'application de partage RMS, les utilisateurs doivent exécuter la commande suivante (aucun besoin de privilèges élevés). Il existe différentes manières d'effectuer cette opération, y compris en demandant aux utilisateurs d'exécuter la commande (par exemple, un lien dans un message électronique ou un lien sur le portail du support technique), ou vous pouvez l'ajouter à leur script d'ouverture de session :

    -   Pour Windows 10, Windows 8.1 et Windows 8, 64 bits :

        ```
        x64\aadrmprep.exe /configureO2010
        ```

    -   Pour Windows 10, Windows 8.1 et Windows 8, 32 bits :

        ```
        X86\aadrmprep.exe /configureO2010
        ```

    -   Pour Windows 7, 64 bits :

        ```
        x64\win7\aadrmpep.exe /configureO2010
        ```

Pour vérifier que l'opération a réussi, voir la section [Vérification de la réussite de l'installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) de cette rubrique.

#### Pour installer l'application de partage RMS et le complément Office uniquement

1.  Installez le client AD RMS et l'application de partage RMS en utilisant la commande suivante :

    -   Pour Windows 64 bits :

        ```
        x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    -   Pour Windows 32 bits :

        ```
        X86\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    Par exemple : `\\server5\apps\rms\x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "C:\Log files\ipviewerinstall.log"`

2.  Installez le complément Office en utilisant les commandes suivantes :

    -   Pour la version 64 bits d'Office :

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "<log file path and name>"
        ```

    -   Pour la version 32 bits d'Office :

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x86\Setup.msi" /L*v "<log file path and name>"
        ```

    Par exemple : `\\server5\apps\rms\msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "C:\Log files\rmsofficeinstall.log"`

Pour vérifier que l'opération a réussi, voir la section [Vérification de la réussite de l'installation](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_verifyscripted) de cette rubrique.

### <a name="BKMK_verifyscripted"></a>Vérification de la réussite de l'installation
Vous pouvez utiliser les fichiers journaux d'installation pour vérifier que l'installation a réussi.

##### Pour vérifier la réussite de l'installation de l'application de partage RMS pour Office 2016 ou Office 2013 et Azure RMS ou Active Directory RMS

-   Pour vérifier la réussite de la commande Setup.exe sur chaque ordinateur, recherchez le fichier journal d'installation **RMInstaller.log** dans le dossier *%temp%\RMS_installer_&lt;guid&gt;*, puis identifiez le code de sortie.

    Une installation réussie a le code de sortie 0, et tout autre numéro indique l'échec de l'installation.

    Exemple de nom de fichier journal : **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0\RMInstaller.log**

##### Pour vérifier la réussite de l'installation de l'application de partage RMS pour Office 2010 et Azure RMS

1.  Pour vérifier la réussite de la commande Setup.exe sur chaque ordinateur, recherchez le fichier journal d'installation **RMInstaller.log** dans le dossier *%temp%\RMS_installer_&lt;guid&gt;*, puis identifiez le code de sortie.

    Une installation réussie a le code de sortie 0, et tout autre numéro indique l'échec de l'installation.

    Exemple de nom de fichier journal : **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  Pour vérifier la réussite de la commande RMSSetup.exe, l'utilisateur doit avoir les fichiers suivants créés dans le dossier *%localappdata%\microsoft\drm* :

    -   CERT-ordinateur-2048.drm

    -   CERT-Machine.drm

    -   CLC-&#42;.drm

    -   GIC-&#42;.drm

    Exemple de fichier CLC-&#42;.drm :

    **CLC-alice@isvtenant999.onmicrosoft.com-{1b9cfccf;k5b11;k4a10;kac15;k29b2b6980f4c}.drm**

##### Pour vérifier la réussite de l'installation de l'application de partage RMS pour Office 2010 et Active Directory RMS

1.  Pour vérifier la réussite de la commande Setup.exe sur chaque ordinateur, recherchez le fichier journal d'installation dans le dossier *%temp%\RMS_installer_&lt;guid&gt;*, puis identifiez le code de sortie.

    Une installation réussie a le code de sortie 0, et tout autre numéro indique l'échec de l'installation.

    Exemple de nom de fichier journal : **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  Pour vérifier la réussite de la commande aadrmprep.exe sur chaque ordinateur, recherchez le texte suivant dans le fichier journal d'installation : **aadrmprep.exe exited with status SUCCESS**

    > [!NOTE]
    > Dans certains cas, cette installation peut s'exécuter deux fois : la première échoue et la seconde réussit.

    Si vous souhaitez vérifier manuellement les modifications de Registre effectuées par cet outil, les voici :

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\ServiceLocation\Activation]

        @="&lt;url de certification&gt;"

    -   [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\14.0\Common\DRM]

        DefaultUser="&lt;utilisateur_par_défaut&gt;"

##### Pour vérifier la réussite de l'installation de l'application de partage RMS et du complément Office uniquement

1.  Pour vérifier la réussite de la commande Setup_ipviewer.exe, recherchez le texte suivant dans le fichier journal d'installation : **Installation success or error status: 0**

    Exemples de lignes pour une installation réussie :

    **MSI (s) (F0:B8) [14:19:57:854]: Product: Active Directory Rights Management Services Client 2.1 -- Installation completed successfully.**

    **MSI (s) (F0:B8) [14:19:57:854]: Windows Installer installed the product. Product Name: Active Directory Rights Management Services Client 2.1. Product Version: 1.0.1179.1. Product Language: 1033. Fabricant : Microsoft Corporation. Installation success or error status: 0.**

2.  Pour vérifier la réussite du complément Office, sur chaque ordinateur, recherchez le texte suivant dans le fichier journal d'installation : **Installation success or error status: 0**

    Exemples de lignes pour une installation réussie :

    **MSI (s) (9C:88) [18:49:04:007]: Product: Microsoft RMS Office Addins -- Installation completed successfully.**

    **MSI (s) (9C:88) [18:49:04:007]: Windows Installer installed the product. Product Name: Microsoft RMS Office Addins. Product Version: 1.0.7. Product Language: 1033. Fabricant : Microsoft. Installation success or error status: 0.**

### <a name="BKMK_uninstallscripted"></a>Commandes de désinstallation
Certaines des commandes d'installation requises pour ces déploiements ne prennent pas de commande de désinstallation en charge. Vous pouvez désinstaller le client AD RMS et l'application de partage, ainsi que le complément Office. Utilisez les commandes suivantes pour désinstaller ces éléments.

##### Pour désinstaller le client AD RMS et l'application de partage RMS

-   Utilisez les commandes suivantes :

    -   Pour Windows 64 bits :

        ```
        x64\setup_ipviewer.exe /uninstall /quiet
        ```

    -   Pour Windows 32 bits :

        ```
        x86\setup_ipviewer.exe /uninstall /quiet
        ```

##### Pour désinstaller le complément Office

-   Utilisez les commandes suivantes :

    -   Pour la version 64 bits d'Office :

        ```
        msiexec /x \x64\Setup[64].msi /quiet
        ```

    -   Pour la version 32 bits d'Office :

        ```
        msiexec /x \x86\Setup.msi /quiet
        ```

### <a name="BKMK_SuppressAutomaticUpdates"></a>Suppression des mises à jour automatiques
Par défaut, les utilisateurs sont avertis s'il existe une version ultérieure de l'application de partage RMS et sont invités à la télécharger. Vous pouvez supprimer cette notification en apportant la modification suivante au Registre :

1.  Accédez à **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC** et, si elle n'est pas déjà présente, créez une clé nommée **RmsSharingApp**.

2.  Sélectionnez **RmsSharingApp**, créez une valeur DWORD de **AllowUpdatePrompt** et définissez la valeur sur **0**.

Étant donné que l'application de partage RMS n'est pas prise en charge par WSUS, vous pouvez utiliser la technique suivante pour tester les nouvelles versions de l'application de partage RMS avant de les déployer vers tous les utilisateurs :

1.  Sur les ordinateurs de tous les utilisateurs, exécutez un script pour supprimer les mises à jour automatiques. Sur les ordinateurs que les administrateurs utilisent pour tester les nouvelles versions, n'exécutez pas ce script.

2.  Lorsqu'une nouvelle version est disponible, les administrateurs la téléchargent et la testent.

3.  Quand le test est terminé et que les problèmes sont résolus, déployez la dernière version vers tous les utilisateurs à l'aide des instructions de déploiement automatique de ce guide.

### <a name="BKMK_DocumentTracking"></a>Azure RMS uniquement : configuration du suivi des documents
Si votre [abonnement prend en charge le suivi des documents](https://technet.microsoft.com/en-us/dn858608), le site de suivi des documents est activé par défaut pour tous les utilisateurs de votre organisation.  Le suivi des documents fournit des informations telles que les adresses de messagerie des personnes qui ont tenté d'accéder aux documents protégés que les utilisateurs ont partagés et indique quand ces personnes ont tenté d'y accéder, ainsi que leur emplacement. Si l'affichage de ces informations est interdit dans votre organisation pour des raisons de confidentialité, vous pouvez désactiver l'accès au site de suivi des document à l'aide de l'applet de commande [Disable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623032). Vous pouvez réactiver l'accès au site à tout moment en utilisant [Enable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037) et vérifier si l'accès est actuellement activé ou désactivé à l'aide de [Get-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037).

 Pour exécuter ces applets de commande, vous devez disposer au moins de la version **2.3.0.0** du module Azure RMS pour Windows PowerShell.  Pour obtenir des instructions d'installation, voir [Installation de Windows PowerShell pour Azure Rights Management](https://technet.microsoft.com/library/jj585012.aspx).

> [!TIP]
> Si vous avez précédemment téléchargé et installé le module, vérifiez le numéro de version en exécutant : `(Get-Module aadrm –ListAvailable).Version`

Les URL suivantes sont utilisées pour le suivi des documents et doivent être autorisées (par exemple, ajoutez-les à vos sites approuvés si vous utilisez Internet Explorer avec sécurité renforcée) :

-   https://&#42;.azurerms.com

-   https://ecn.dev.virtualearth.net

    > [!NOTE]
    > Cette URL est pour Bing Maps.

-   https://&#42;.microsoftonline.com

-   https://&#42;.microsoftonline-p.com

### <a name="BKMK_FederatedDomains"></a>AD RMS uniquement : prise en charge de plusieurs domaines de messagerie au sein de votre organisation
Si vous utilisez les services AD RMS et que les utilisateurs de votre organisation disposent de plusieurs domaines de messagerie, suite à une fusion ou une acquisition par exemple, vous devez apporter la modification suivante au Registre :

1.  Accédez à **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC** et, si elle n'est pas déjà présente, créez une clé nommée **RmsSharingApp**.

2.  Sélectionnez **RmsSharingApp**, créez une valeur de chaînes multiples nommée **FederatedDomains**, puis ajoutez les domaines et tous les sous-domaines utilisés par votre organisation. Les caractères génériques ne sont pas pris en charge.

    Par exemple : la société Coho Vineyard &amp; Winery dispose du domaine de messagerie standard **cohovineyardandwinery.com** mais, à la suite de fusions, elles utilisent également les domaines de messagerie **cohowinery.com**, **eastcoast.cohowinery.com** et **cohovineyard**. Pour les données de valeur **FederatedDomains**, l’administrateur entre **cohowinery.com; eastcoast.cohowinery.com; cohovineyard**

Si vous n'apportez pas cette modification au Registre, les utilisateurs risquent de ne pas pouvoir consommer le contenu qui a été protégé par d'autres utilisateurs de leur organisation. Cette modification du Registre n'est pas nécessaire si vous utilisez Azure RMS.

## <a name="BKMK_AdminOverview"></a>Présentation technique de l'application de partage Microsoft Rights Management
L'application de partage Microsoft Rights Management est une application téléchargeable facultative pour Microsoft Windows et d’autres plateformes. Elle offre les fonctionnalités suivantes :

-   Protection d'un seul fichier ou protection en bloc de plusieurs fichiers ainsi que de tous les fichiers d'un dossier sélectionné.

-   Prise en charge complète de la protection de tous les types de fichier et intégration d'une visionneuse pour les types de fichier texte et image couramment utilisés.

-   Protection générique des fichiers qui ne prennent pas en charge la protection RMS.

-   Interopérabilité complète avec les fichiers protégés à l'aide de la Gestion des droits relatifs à l'information (IRM).

-   Interopérabilité complète avec les fichiers PDF protégés à l'aide de SharePoint, l'ICF et les outils de création de fichiers PDF pris en charge.

L'application de partage Microsoft Rights Management utilise le nouveau [runtime du client AD RMS 2.1](http://www.microsoft.com/download/details.aspx?id=38396). Grâce aux fonctionnalités d'AD RMS 2.1, l'application de partage Microsoft Rights Management fournit aux utilisateurs finaux une expérience simple de protection et de consommation.

Avec la version d'octobre 2013 de RMS, vous pouvez protéger des documents en mode natif à l'aide d'Office 2010 et les envoyer à des personnes d'une autre entreprise, celles-ci pouvant alors les utiliser dans Azure RMS. En outre, avec cette version, si vous utilisez AD RMS en mode de chiffrement 2, vous pouvez utiliser RMS for Individuals et utiliser du contenu provenant de personnes d'une autre entreprise utilisant Azure RMS. Pour plus d'informations sur le mode de chiffrement 2, voir [AD RMS Cryptographic Modes](http://technet.microsoft.com/library/hh867439%28v=ws.10%29.aspx).

### <a name="BKMK_LevelsofProtection"></a>Niveaux de protection : natif et générique
L’application de partage Microsoft Rights Management prend en charge la protection à deux niveaux différents, comme décrit dans le tableau suivant.

|Type de protection|Natif|Générique|
|----------------------|---------|-------------|
|Description|Dans le cas de fichiers texte, image, Microsoft Office (Word, Excel, PowerPoint), .pdf et d'autres types de fichier d'application qui prennent en charge AD RMS, la protection native fournit un niveau de protection élevé, qui comprend le chiffrement et la mise en application de droits (autorisations).|Pour toutes les autres applications et tous les autres types de fichier, la protection générique fournit un niveau de protection qui inclut à la fois l’encapsulation de fichier avec le type de fichier .pfile et l’authentification pour déterminer si un utilisateur est autorisé à ouvrir le fichier.|
|Protection|Les fichiers sont entièrement chiffrés et la protection est appliquée comme suit :<br /><br />-   Pour que le contenu protégé soit affiché, les personnes qui reçoivent le fichier par courrier électronique ou obtiennent un accès à celui-ci grâce aux autorisations de fichier ou de partage doivent être authentifiées.<br />-   De plus, la stratégie et les droits d'utilisation définis par le propriétaire du contenu lorsque les fichiers sont protégés sont entièrement appliqués quand le contenu est affiché dans IP Viewer (pour les fichiers texte et image protégés) ou dans l’application associée (pour tous les autres types de fichier pris en charge).|La protection des fichiers est appliquée comme suit :<br /><br />-   Pour que le contenu protégé soit affiché, les personnes autorisées à ouvrir le fichier et qui ont la possibilité d'y accéder doivent être authentifiées. Si l'autorisation échoue, le fichier ne s'ouvre pas.<br />-   Les droits d'utilisation et la stratégie définis par le propriétaire du contenu sont affichés pour informer les utilisateurs autorisés de la stratégie d'utilisation prévue.<br />-   Un enregistrement d'audit des utilisateurs autorisés qui ouvrent les fichiers et y accèdent est réalisé, mais aucun droit d'utilisation n'est appliqué par les applications qui ne prennent pas cette fonctionnalité en charge.|
|Valeur par défaut pour les types de fichier|Il s'agit du niveau de protection par défaut pour les types de fichiers suivants :<br /><br />-   Fichiers texte et image<br />-   Fichiers Microsoft Office (Word, Excel, PowerPoint)<br />-   Fichiers PDF (Portable Document Format) (.pdf)<br /><br />Pour plus d'informations, consultez la section suivante, [Types de fichier pris en charge et extensions de nom de fichier](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_SupportFileTypes).|Il s'agit de la protection par défaut pour tous les autres types de fichier (comme .vsdx, .rtf, etc.) non pris en charge pour une protection complète.|
Vous pouvez modifier le niveau de protection par défaut appliqué par l'application de partage RMS. Vous pouvez remplacer le niveau de protection native par défaut par une protection générique, et inversement, et même empêcher que l'application de partage RMS n'applique la protection. Pour plus d'informations, consultez la section [Modification du niveau de protection par défaut des fichiers](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_ChangeDefaultProtection) dans cette rubrique.

### <a name="BKMK_SupportFileTypes"></a>Types de fichier pris en charge et extensions de nom de fichier
Le tableau suivant répertorie les types de fichier pris en charge en mode natif par l'application de partage Microsoft Rights Management. Pour ces types de fichier, l'extension de nom de fichier d'origine est modifiée lorsque la protection native est appliquée, et ces fichiers sont alors en lecture seule.

En outre, quand l'application de partage RMS protège en mode natif un fichier Word, Excel ou PowerPoint que les utilisateurs protègent par le partage, cette action crée automatiquement un deuxième fichier, qui est une copie du fichier d'origine avec le même nom, mais avec une extension de nom de fichier **.ppdf** ¹. Cette version du fichier permet de garantir que les destinataires qui installent l'application de partage RMS peuvent toujours ouvrir le fichier auquel une protection native est appliquée.

Pour les fichiers protégés de manière générique, l'extension de nom de fichier d'origine est toujours remplacée par .pfile.

> [!WARNING]
> Si vous disposez de pare-feu, proxys web ou logiciels de sécurité qui contrôlent et prennent des mesures en fonction des extensions de nom de fichier, vous devrez peut-être les reconfigurer pour qu'ils prennent en charge ces nouvelles extensions de nom de fichier.

|Extension de nom de fichier d'origine|Extension de nom d'un fichier protégé par RMS|
|-----------------------------------------|-------------------------------------------------|
|.txt|.ptxt|
|.xml|.pxml|
|.jpg|.pjpg|
|.jpeg|.ppng|
|.pdf|.ppdf|
|.png|.ppng|
|.tiff|.ptiff|
|.bmp|.pbmp|
|.gif|.pgif|
|.giff|.pgiff|
|.jpe|.pjpe|
|.jfif|.pjfif|
|.jif|.pjif|
|.jt|.pjt|
¹ Rendu PDF avec Foxit. Copyright © 2003-2014 Foxit Corporation.

Le tableau suivant répertorie les types de fichier pris en charge en mode natif par l'application de partage Microsoft Rights Management dans Microsoft Office 2016, Office 2013 et Office 2010. Pour ces fichiers, l'extension de nom de fichier reste la même une fois que le fichier est protégé par RMS.

|Types de fichier pris en charge par Office|Types de fichier pris en charge par Office|
|----------------------------------------------|----------------------------------------------|
|.doc<br /><br />.docm<br /><br />.docx<br /><br />.dot<br /><br />.dotm<br /><br />.dotx<br /><br />.potm<br /><br />.potx<br /><br />.pps<br /><br />.ppsm<br /><br />.ppsx<br /><br />.ppt<br /><br />.pptm|.pptx<br /><br />.thmx<br /><br />.xla<br /><br />.xlam<br /><br />.xls<br /><br />.xlsb<br /><br />.xlt<br /><br />.xlsm<br /><br />.xlsx<br /><br />.xltm<br /><br />.xltx<br /><br />.xps|

### <a name="BKMK_ChangeDefaultProtection"></a>Modification du niveau de protection par défaut des fichiers
Vous pouvez modifier la façon dont l'application de partage RMS protège les fichiers en modifiant le Registre. Par exemple, vous pouvez forcer les fichiers qui prennent en charge la protection native à être protégés de manière générique par l'application de partage RMS.

Raisons pour lesquelles vous pourriez vouloir procéder ainsi :

-   Pour vous assurer que tous les utilisateurs peuvent ouvrir le fichier à partir de leurs appareils mobiles.

-   Pour vous assurer que tous les utilisateurs peuvent ouvrir le fichier s'ils ne possèdent pas d'application prenant en charge la protection native.

-   Pour tenir compte des systèmes de sécurité qui agissent sur les fichiers selon leur extension de nom de fichier et peuvent être reconfigurés pour prendre en charge l'extension de nom de fichier .pfile, mais ne peuvent pas être reconfigurés pour prendre en charge plusieurs extensions de nom de fichier pour la protection native.

De même, vous pouvez forcer l'application de partage RMS à appliquer une protection native aux fichiers qui auraient une protection générique par défaut. Cela peut être approprié si vous avez une application qui prend en charge les API RMS, par exemple une application métier écrite par vos développeurs internes ou une application achetée auprès d'un éditeur de logiciels indépendant.

Vous pouvez également forcer l'application de partage RMS à bloquer la protection des fichiers (ne pas appliquer de protection native ou générique). Par exemple, cela peut être nécessaire si vous avez une application automatisée ou un service qui doit être en mesure d'ouvrir un fichier spécifique pour traiter son contenu. Quand vous bloquez la protection pour un type de fichier particulier, les utilisateurs ne peuvent pas utiliser l'application de partage RMS pour protéger les fichiers de ce type. Quand ils essaient de le faire, un message indiquant que l'administrateur a empêché la protection s'affiche, et ils doivent annuler leur action pour protéger le fichier.

Pour configurer l'application de partage RMS afin qu'elle applique une protection générique à tous les fichiers qui auraient par défaut une protection native, apportez les modifications suivantes au Registre :

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection** : créez une clé nommée **&#42;**.

    Ce réglage désigne les fichiers avec une extension de nom de fichier quelconque.

2.  Dans la clé nouvellement ajoutée **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\ &#42;**, créez une valeur de chaîne (REG_SZ) nommée **Encryption** avec la valeur de données **Pfile**.

    Ce réglage entraîne l'application de la protection générique par l'application de partage RMS.

Ces deux réglages entraînent l'application de la protection générique par l'application de partage RMS à tous les fichiers ayant une extension de nom de fichier. Si c'est l'objectif que vous recherchez, aucune configuration supplémentaire n'est requise. Toutefois, vous pouvez définir des exceptions pour des types de fichier spécifiques, afin qu'ils soient protégés en mode natif. Pour cela, vous devez effectuer trois modifications supplémentaires dans le Registre pour chaque type de fichier :

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection** : ajoutez une nouvelle clé dont le nom correspond à l'extension de nom de fichier (sans le point en préfixe).

    Par exemple, pour les fichiers qui ont une extension de nom de fichier .docx, créez une clé nommée **DOCX**.

2.  Dans la clé nouvellement ajoutée (par exemple **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**, créez une valeur DWORD nommée **AllowPFILEEncryption** avec la valeur **0**.

3.  Dans la clé de type de fichier nouvellement ajoutée (par exemple **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**, créez une valeur de chaîne nommée **Encryption** avec la valeur **Native**.

Suite à ces réglages, tous les fichiers sont protégés de façon générique, à l'exception des fichiers qui ont une extension de nom de fichier .docx, qui sont protégés en mode natif par l'application de partage RMS.

Répétez ces trois étapes pour les autres types de fichier que vous souhaitez définir en tant qu'exceptions car ils prennent en charge la protection native et vous ne souhaitez pas qu'ils soient protégés de manière générique par l'application de partage RMS.

Vous pouvez apporter des modifications similaires au Registre pour d'autres scénarios en modifiant la valeur de la chaîne **Encryption** qui prend en charge les valeurs suivantes :

-   **Pfile** : protection générique

-   **Native** : protection native

-   **Off** : bloquer la protection

## Voir aussi
[Guide d’utilisation de l’application de partage Rights Management](../Topic/Rights_Management_sharing_application_user_guide.md)

