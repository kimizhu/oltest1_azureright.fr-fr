---
description: na
keywords: na
title: RMS Client Deployment Notes
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 03cc8c6f-3b63-4794-8d92-a5df4cdf598f
---
# Notes sur le d&#233;ploiement du client RMS
Le client du service Rights Management (client RMS) version 2 est également appelé client MSIPC. Il s'agit d'un logiciel pour ordinateurs Windows, qui communique avec les services Microsoft Rights Management localement ou dans le cloud pour protéger l'accès aux informations et leur utilisation quand celles-ci transitent par des applications et appareils, à l'intérieur ou à l'extérieur des limites managées de votre organisation. En plus de l'envoi de journaux avec l'[application de partage Microsoft Rights Management pour Windows](https://technet.microsoft.com/library/dn919648.aspx), le client RMS est disponible sous la forme d'un [téléchargement facultatif](http://www.microsoft.com/download/details.aspx?id=38396) qui peut, après réception et acceptation de son contrat de licence, être distribué gratuitement avec des logiciels tiers afin que les clients puissent protéger et utiliser du contenu protégé par les services RMS.

Cette rubrique comprend les sections suivantes :

-   [Redistribution du client RMS](#BKMK_RedistributeInstaller)

-   [Installation du client RMS](#BKMK_InstallClient)

-   [Questions et réponses sur le client RMS](#BKMK_QA)

-   [Paramètres du client RMS.](#BKMK_Settings)

-   [AD RMS uniquement : Limitation du client RMS à l'utilisation de serveurs AD RMS de confiance](#BKMK_UsingTrustedServers)

-   [Découverte du service RMS](#BKMK_ServiceDiscovery)

## <a name="BKMK_RedistributeInstaller"></a>Redistribution du client RMS
Le client RMS peut être librement redistribué et regroupé avec d'autres applications et solutions informatiques. Si vous êtes développeur d'applications ou fournisseur de solutions, et souhaitez redistribuer le client RMS, vous avez deux options :

-   Recommandé : Incorporez le programme d'installation du client RMS dans votre installation d'application et exécutez-le en mode silencieux (commutateur **/quiet**, détaillé dans la section suivante).

-   Faites du client RMS une condition préalable pour votre application. Avec cette option, vous devrez peut-être fournir aux utilisateurs des instructions supplémentaires pour obtenir, installer et mettre à jour leurs ordinateurs avec le client avant de pouvoir utiliser votre application.

## <a name="BKMK_InstallClient"></a>Installation du client RMS
Le client RMS est contenu dans un fichier exécutable d'installation nommé**setup_msipc_***&lt;arch&gt;***.exe**, où *&lt;arch&gt;* est **x86** (pour les ordinateurs clients 32 bits) ou **x64** (pour les ordinateurs clients 64 bits). Le package d'installation 64 bits (x64) installe un exécutable runtime 32 bits pour la compatibilité avec les applications 32 bits qui s'exécutent sur une installation de système d'exploitation 64 bits, ainsi qu'un exécutable runtime 64 bits pour la prise en charge des applications 64 bits natives. Le programme d'installation 32 bits (x86) ne s'exécute pas sur une installation de  Windows 64 bits.

> [!NOTE]
> Pour installer le client RMS, vous avez besoin de privilèges élevés, tel ceux d'un membre du groupe Administrateurs sur l'ordinateur local.

Vous pouvez installer le client RMS à l'aide de l'une des méthodes d'installation suivantes :

-   **Mode silencieux.** L'utilisation du commutateur **/quiet** parmi les options de ligne de commande permet d'installer le client RMS en mode silencieux sur des ordinateurs. L'exemple suivant illustre une installation en mode silencieux du client RMS sur un ordinateur client 64 bits :

    ```
    setup_msipc_x64.exe /quiet
    ```

-   **Mode interactif.** Autrement, vous pouvez installer le client RMS en utilisant le programme d'installation basé sur l'interface graphique utilisateur fourni par l'Assistant Installation du client RMS. Pour ce faire, double-cliquez sur le package d'installation du client RMS (**setup_msipc_***&lt;arch&gt;***.exe**) dans le dossier dans lequel il a été copié ou téléchargé sur votre ordinateur local.

## <a name="BKMK_QA"></a>Questions et réponses sur le client RMS
La section suivante contient des questions fréquemment posées sur le client RMS et les réponses à celles-ci.

### Quels systèmes d'exploitation prennent en charge le client RMS ?
Le client RMS est pris en charge par les systèmes d'exploitation suivants :

|Système d'exploitation Windows Server|Système d'exploitation Windows Client|
|-----------------------------------------|-----------------------------------------|
|Windows Server 2012 R2|Windows 8.1|
|Windows Server 2012|Windows 8|
|Windows Server 2008 R2|Windows 7 avec au minimum SP1|
|Windows Server 2008 (AD RMS uniquement)|Windows Vista avec au minimum SP2 (AD RMS uniquement)|

### Quels processeurs ou plates-formes prennent en charge le client RMS ?
Le client RMS est pris en charge sur les plates-formes de calcul x86 et x64.

### Où est installé le client RMS ?
Par défaut, le client RMS est installé dans %ProgramFiles%\Active Directory Rights Management Services Client 2.&lt;numéro de version mineur&gt;.

### Quels fichiers sont associés au logiciel du client RMS ?
Les fichiers installés en même temps que le logiciel du client RMS sont les suivants :

-   Msipc.dll

-   Ipcsecproc.dll

-   Ipcsecproc_ssp.dll

-   MSIPCEvents.man

Outre ces fichiers, le client RMS installe des fichiers de prise en charge d'interface utilisateur multilingue (MUI) dans 44 langues. Pour vérifier les langues prises en charge, exécutez l'installation du client RMS, puis, une fois l'installation terminée, examinez le contenu des dossiers de prise en charge multilingue sous le chemin d'accès par défaut.

### Le client RMS est-il inclus par défaut lors de l'installation d'un système d'exploitation pris en charge ?
Non. Cette version du client RMS est fournie en tant que téléchargement facultatif pouvant être installé séparément sur des ordinateurs exécutant les versions prises en charge du système d'exploitation Microsoft Windows.

### Le client RMS est-il automatiquement mis à jour par Microsoft Update ?
Si vous avez utilisé l'option d'installation silencieuse pour installer ce client RMS, celui-ci hérite des paramètres actuels de Microsoft Update. Si vous avez installé le client RMS à l'aide du programme d'installation basé sur l'interface graphique utilisateur, l'Assistant Installation du client RMS vous invite à activer Microsoft Update.

## <a name="BKMK_Settings"></a>Paramètres du client RMS.
La section suivante contient des informations de paramètres sur le client RMS. Ces informations peuvent être utiles si vous rencontrez des problèmes avec des applications ou services utilisant le client RMS.

> [!NOTE]
> Certains paramètres varient selon que l'application compatible avec RMS s'exécute en tant qu'application en mode client (par exemple, Microsoft Word et Outlook, ou l'application de partage RMS), ou en mode serveur (par exemple, SharePoint et Exchange).  Dans les tableaux suivants, ces paramètres sont identifiés respectivement comme **Mode Client** et **Mode serveur**.

### Où le client RMS stocke-t-il les licences sur les ordinateurs clients ?
Le client RMS stocke les licences sur le disque local et met également en cache des informations dans le Registre Windows.

|Description|Chemins d'accès du mode client|Chemins d'accès du mode serveur|
|---------------|----------------------------------|-----------------------------------|
|Emplacement du magasin de licences|%localappdata%\Microsoft\MSIPC|%allusersprofile%\Microsoft\MSIPC\Server\*&lt;SID&gt;*\|
|Emplacement du magasin de modèles|%localappdata%\Microsoft\MSIPC\Templates|%allusersprofile%\Microsoft\MSIPC\Server\Templates\*&lt;SID&gt;*\|
|Emplacement du Registre|HKEY_CURRENT_USER<br /> \Software<br /> \Classes<br /> \Local Settings<br /> \Software<br /> \Microsoft<br /> \MSIPC|HKEY_CURRENT_USER<br /> \Software<br /> \Microsoft<br /> \MSIPC<br /> \Server<br /> \*&lt;SID&gt;*|
> [!NOTE]
> *&lt; SID &gt;* est l'identificateur sécurisé (SID) du compte sous lequel s'exécute l'application serveur. Par exemple, si l'application s'exécute sous le compte de service réseau intégré, remplacez*&lt;SID&gt;* par la valeur du SID connu pour ce compte (S-1-5-20).

### Paramètres du Registre Windows pour le client RMS
Vous pouvez utiliser des clés de Registre Windows pour définir ou modifier des configurations de client RMS. Par exemple, en tant qu'administrateur d'applications compatibles avec RMS qui communiquent avec des serveurs AD RMS, il se peut que vous souhaitiez mettre à jour l'emplacement du service d'entreprise (pour remplacer le serveur AD RMS actuellement sélectionné pour la publication) en fonction de l'emplacement actuel de l'ordinateur client dans votre topologie Active Directory. Vous pouvez également activer le suivi RMS sur l'ordinateur client pour faciliter la résolution d'un problème lié à une application compatible avec RMS. Utilisez le tableau suivant pour identifier les paramètres de Registre que vous pouvez modifier pour le client RMS.

|Tâche|Paramètres|
|---------|--------------|
|AD RMS uniquement : Pour mettre à jour l'emplacement du service d'entreprise pour un ordinateur client|Modifiez la clé de Registre suivante :<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterpriseCertification<br />    REG_SZ: default<br />    **Value :**&lt;http ou https&gt;:// *RMS_Cluster_Name*/_wmcs/Certification<br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterprisePublishing<br />    REG_SZ: default<br />    **Value :** &lt;http ou https&gt;:// *RMS_Cluster_Name*/_wmcs/Licensing|
|Pour activer et désactiver le suivi|Mettez à jour la clé de registre suivante :<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC<br />    REG_DWORD: Suivi<br />    **Value :** 1 pour activer le traçage, 0 pour le désactiver (par défaut)|
|Pour modifier la fréquence en jours d'actualisation des modèles|Les valeurs de Registre suivantes spécifient la fréquence à laquelle les modèles sont actualisés sur l'ordinateur de l'utilisateur si la valeur TemplateUpdateFrequencyInSeconds n'est pas définie.  Si aucune de ces valeurs n'est définie, l'intervalle d'actualisation par défaut pour les applications utilisant le client RMS (version 1.0.1784.0) pour télécharger des modèles est de 1 jour. La valeur par défaut définie dans les versions antérieures à celle-ci est de 7 jours.<br /><br />**Mode client :**<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: TemplateUpdateFrequency<br />    **Value :** Valeur entière spécifiant le nombre de jours (au minimum 1) entre les téléchargements.<br /><br />**Mode serveur :**<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*&lt;SID&gt;*<br />    REG_DWORD: TemplateUpdateFrequency<br />    **Value :** Valeur entière spécifiant le nombre de jours (au minimum 1) entre les téléchargements.|
|Pour modifier la fréquence en secondes d'actualisation des modèles **Important:** Si cette valeur est spécifiée, la valeur d'actualisation en jours des modèles est ignorée. Spécifiez une ou l'autre, pas les deux.|Les valeurs de Registre suivantes spécifient la fréquence à laquelle les modèles sont actualisés sur l'ordinateur de l'utilisateur. Si cette valeur ou la valeur modifiant la fréquence en jours (TemplateUpdateFrequency) ne sont pas définies, l'intervalle d'actualisation par défaut pour les applications utilisant le client RMS (version 1.0.1784.0) pour télécharger des modèles est de 1 jour. La valeur par défaut définie dans les versions antérieures à celle-ci est de 7 jours.<br /><br />**Mode client :**<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: TemplateUpdateFrequencyInSeconds<br />    **Value :** Valeur entière spécifiant le nombre de secondes (au minimum 1) entre les téléchargements.<br /><br />**Mode serveur :**<br /><br />-   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*&lt;SID&gt;*<br />    REG_DWORD: TemplateUpdateFrequencyInSeconds<br />    **Value :** Valeur entière spécifiant le nombre de secondes (au minimum 1) entre les téléchargements.|
|AD RMS uniquement : Pour télécharger les modèles immédiatement à la prochaine demande de publication|Durant les tests et évaluations, il se peut que vous souhaitiez que le client RMS télécharge les modèles dès que possible. Pour ce faire, supprimez la clé de Registre suivante. Le client RMS téléchargera alors les modèles immédiatement à la prochaine demande de publication au lieu d'attendre l'heure spécifiée par le paramètre de Registre TemplateUpdateFrequency :<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\&lt;Nom de serveur&gt;\Template **Note:** &lt;Nom de serveur&gt; peut avoir des URL externe (corprights.contoso.com) et interne (corprights), et donc deux entrées différentes.|
|AD RMS uniquement : Pour activer la prise en charge de l'authentification fédérée|Si l'ordinateur client RMS se connecte à un cluster AD RMS en utilisant une approbation fédérée, vous devez configurer le domaine d'accueil de fédération.<br /><br />-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />    REG_SZ: FederationHomeRealm<br />    **Value :** La valeur de cette entrée de Registre est l'URI (Uniform Resource Identifier) du service de fédération (par exemple, « https://fs-01.contoso.com »).|
|AD RMS uniquement : Pour prendre en charge les serveurs de fédération de partenaires qui requièrent une authentification basée sur les formulaires pour l'entrée utilisateur|Par défaut, le client RMS fonctionne en mode silencieux et l'entrée utilisateur n'est pas nécessaire. Toutefois, les serveurs de fédération de partenaires peuvent être configurés pour exiger une entrée utilisateur, telle qu'une authentification basée sur les formulaires. Dans ce cas, vous devez configurer le client RMS pour ignorer le mode silencieux afin que le formulaire d'authentification fédérée s'affiche dans une fenêtre de navigateur et que l'utilisateur soit invité à s'authentifier.<br /><br />-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />    REG_DWORD: EnableBrowser **Note:** Si le serveur de fédération est configuré pour utiliser l'authentification basée sur les formulaires, cette clé est obligatoire. Si le serveur de fédération est configuré pour utiliser l'authentification intégrée de Windows, cette clé n'est pas requise.|
|AD RMS uniquement : Pour bloquer la consommation de services ILS|Par défaut, le client RMS autorise la consommation de contenu protégé par le service ILS, mais vous pouvez configurer le client pour bloquer ce service en définissant la clé de Registre suivante. Si cette clé de Registre est définie pour bloquer le service ILS, toute tentative d'ouvrir et de consommer du contenu protégé par le service ILS retourne l'erreur suivante :<br />HRESULT_FROM_WIN32(ERROR_ACCESS_DISABLED_BY_POLICY)<br /><br />-   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />    REG_DWORD: **DisablePassportCertification**<br />    **Value :** 1 pour bloquer la consommation ILS, 0 pour l'autoriser ILS (par défaut)|

### Gestion de la distribution de modèles pour le client RMS
Les modèles aident les utilisateurs et administrateurs à appliquer rapidement la protection Rights Management. Le client RMS télécharge automatiquement les modèles à partir de ses serveurs ou de son service RMS. Si vous placez les modèles dans l'emplacement de dossier suivant, le client RMS ne télécharge pas de modèles à partir de l'emplacement par défaut, mais télécharge les modèles que vous avez placés dans ce dossier. Il se peut que le client RMS continue à télécharger des modèles à partir d'autres serveurs RMS disponibles.

**Mode client :**%localappdata%\Microsoft\MSIPC\UnmanagedTemplates

**Mode serveur :**%allusersprofile%\Microsoft\MSIPC\Server\UnmanagedTemplates\*&lt;SID&gt;*

Lorsque vous utilisez ce dossier, aucune convention d'affectation de noms particulière ne s'impose, sauf que les modèles doivent être émis par le serveur ou le service RMS, et doivent avoir l'extension de nom de fichier .xml. Par exemple, Contoso-Confidential.xml ou Contoso-ReadOnly.xml sont des noms valides.

## <a name="BKMK_UsingTrustedServers"></a>AD RMS uniquement : Limitation du client RMS à l'utilisation de serveurs AD RMS de confiance
Vous pouvez limiter le client RMS à l'utilisation exclusive de serveurs AD RMS de confiance spécifiques en apportant les modifications suivantes au Registre Windows sur des ordinateurs locaux.

**Pour activer la limitation du client RMS à l'utilisation exclusive de serveurs AD RMS de confiance**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_DWORD: AllowTrustedServersOnly

    **Value :** Si une valeur différente de zéro est spécifiée, le client RMS approuve uniquement les serveurs spécifiés configurés dans la liste de TrustedServers et le service Azure Rights Management.

**Pour ajouter des membres à la liste des serveurs AD RMS de confiance**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_SZ: *&lt;URL_ou_HostName&gt;*

    **Value :** Les valeurs de chaîne ajoutées à cet emplacement de clé de Registre peuvent être au format de nom de domaine DNS (par exemple, **adrms.contoso.com**) ou des URL complètes de serveurs AD RMS de confiance (par exemple, **https://adrms.contoso.com**). Si une URL spécifiée commence par **https://**, le client RMS utilise le protocole SSL ou TLS pour contacter le serveur AD RMS spécifié.

## <a name="BKMK_ServiceDiscovery"></a>Découverte du service RMS
La découverte du service RMS permet au client RMS de vérifier le serveur ou service RMS avec lequel communiquer avant de protéger le contenu. Une découverte du service peut également se produire quand le client RMS consomme du contenu protégé mais il est peu probable que cela se produise, car la stratégie associée au contenu contient le serveur ou service RMS par défaut, et ce n'est qu'en cas d'échec que le client exécute la découverte du service.

La découverte du service recherche d'abord une version locale de Rights Management (AD RMS). Si cela ne fonctionne pas, la découverte du service recherche automatiquement la version cloud de Rights Management (Azure RMS).

Pour effectuer la découverte du service sur un déploiement local, le client RMS vérifie les éléments suivants :

1.  Le Registre Windows sur l'ordinateur local : si des paramètres de découverte du service sont configurés dans le Registre, ces paramètres sont essayés en premier.  Par défaut, ces paramètres ne sont pas configurés dans le Registre.

2.  Services de domaine Active Directory : Un ordinateur appartenant à un domaine interroge Active Directory pour un point de connexion de service (SCP). Si un SCP est inscrit, l'URL du serveur RMS est renvoyée au client RMS pour utilisation.

### AD RMS uniquement : Activation de la découverte du service côté serveur à l'aide d'Active Directory
Si votre compte dispose de privilèges suffisants (Administrateurs de l'entreprise et administrateur local pour le serveur AD RMS), vous pouvez inscrire automatiquement un point de connexion de service (SCP) lorsque vous installez le serveur de clusters racine AD RMS. S'il existe déjà un SCP dans la forêt, vous devez le supprimer avant de pouvoir en inscrire un nouveau.

Vous pouvez inscrire et supprimer un SCP une fois AD RMS installé à l'aide de la procédure suivante. Avant de commencer, assurez-vous que votre compte dispose des privilèges requis (Administrateurs de l'entreprise et administrateur local pour le serveur AD RMS).

##### Pour activer la découverte du service AD RMS en inscrivant un SCP dans Active Directory

1.  Ouvrez la console Services AD RMS (Active Directory Rights Management Services) sur le serveur AD RMS :

    -   Si vous utilisez Windows Server 2008 R2 ou Windows Server 2008, cliquez sur **Démarrer**, sur **Outils d'administration**, puis sur **Services AD RMS (Active Directory Rights Management Services)**.

    -   Si vous utilisez Windows Server 2012 R2 ou Windows Server 2012, dans Gestionnaire de serveur, cliquez sur **Outils**, puis sur **Services AD RMS (Active Directory Rights Management Services)**.

2.  Dans la console AD RMS, cliquez avec le bouton droit sur le cluster AD RMS, puis cliquez sur **Propriétés**.

3.  Cliquez sur l'onglet **SCP**.

4.  Activez la case à cocher **Modifier le point de connexion de service**.

5.  Sélectionnez l'option **Définir le point de connexion de service sur le cluster de certification actuel**, puis cliquez sur **OK**.

### Activation de la découverte du service côté Client à l'aide du Registre Windows
Une alternative à l'utilisation d'un SCP, ou à défaut de SCP, vous pouvez configurer le Registre sur l'ordinateur client afin que le client RMS puisse localiser son serveur AD RMS.

##### Pour activer la découverte du service AD RMS côté client à l'aide du Registre Windows

1.  Ouvrez l'Éditeur du Registre Windows, Regedit.exe :

    -   Sur l'ordinateur client, dans la fenêtre Exécuter, tapez **regedit**, puis appuyez sur ENTRÉE pour ouvrir l'Éditeur du Registre.

2.  Dans l'Éditeur du Registre, accédez à **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC**.

    > [!IMPORTANT]
    > Si vous exécutez une application 32 bits sur un ordinateur 64 bits, le chemin d'accès est le suivant : 
    > **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC**

3.  Pour créer la sous-clé ServiceLocation, cliquez avec le bouton droit sur **MSIPC**, pointez sur **Nouveau**, cliquez sur**Clé**, puis tapez **ServiceLocation**.

4.  Pour créer la sous-clé EnterpriseCertification, cliquez avec le bouton droit sur **ServiceLocation**, pointez sur **Nouveau**, cliquez sur **Clé**, puis tapez **EnterpriseCertification**.

5.  Pour définir l'URL de certification d'entreprise, double-cliquez sur la valeur **(par défaut)** sous la sous-clé **EnterpriseCertification**, puis, lorsque la boîte de dialogue **Modifier la chaîne** s'affiche, dans **Données de la valeur**, tapez &lt;http or https&gt;://*AD RMS_cluster_name*/_wmcs/Certification, puis cliquez sur **OK**.

6.  Pour créer la sous-clé EnterprisePublishing, cliquez avec le bouton droit sur **ServiceLocation**, pointez sur **Nouveau**, cliquez sur **Clé**, puis tapez EnterprisePublishing.

7.  Pour définir l'URL de publication d'entreprise, sous la sous-clé **EnterprisePublishing**, double-cliquez sur **(par défaut)**, puis, lorsque la boîte de dialogue **Modifier la chaîne** s'affiche, dans **Données de la valeur**, tapez &lt;http or https&gt;://*AD RMS_cluster_name*/_wmcs/Licensing, puis cliquez sur**OK**.

8.  Fermez l'Éditeur du Registre.

Si le client RMS ne peut pas trouver de SCP en interrogeant Active Directory et si le SCP n'est pas spécifié dans le Registre, les appels de découverte du service pour AD RMS échouent.

### Redirection du trafic du serveur de licences
Dans certains cas, il se peut que vous deviez rediriger le trafic pendant la découverte du service, par exemple, lorsque deux organisations sont fusionnées, que l'ancien serveur de licences dans une organisation est retiré, et que les clients doivent être redirigés vers un nouveau serveur de licences. Vous pouvez également migrer d'AD RMS vers Azure RMS. Pour activer la redirection de licences, procédez comme suit.

##### Pour activer la redirection de licences RMS à l'aide du Registre Windows

1.  Ouvrez l'Éditeur du Registre Windows, Regedit.exe :

    -   Sur l'ordinateur client, dans la fenêtre Exécuter, tapez **regedit**, puis appuyez sur ENTRÉE pour ouvrir l'Éditeur du Registre.

2.  Dans l'Éditeur du Registre, accédez à l'un des éléments suivants :

    -   Pour la version 64 bits d'Office sur une plateforme x64 : HKLM\SOFTWARE\Microsoft\MSIPC\Servicelocation

    -   Pour la version 32 bits d'Office sur une plateforme x64 : HKLM\SOFTWARE\Wow6432Node\Microsoft\MSIPC\Servicelocation

3.  Créez une sous-clé LicensingRedirection, cliquez avec le bouton droit sur **Servicelocation**, pointez sur **Nouveau**, cliquez sur **Clé**, puis tapez **LicensingRedirection**.

4.  Pour définir la redirection de licences, cliquez avec le bouton droit sur la sous-clé **LicensingRedirection**, sélectionnez**Nouveau**, puis sélectionnez **Valeur de chaîne**.  Pour **Nom**, spécifiez l'URL de licence de serveur précédente, et pour **Valeur**, spécifiez la nouvelle URL de licence de serveur.

    Par exemple, pour rediriger la gestion des licences d'un serveur de Contoso.com vers un serveur de Fabrikam.com, vous pouvez entrer les valeurs suivantes :

    **Nom :**`https://contoso.com/_wmcs/licensing`

    **Valeur :**`https://fabrikam.com/_wmcs/licensing`

    > [!NOTE]
    > Si l'ancien serveur de licences a une URL intranet et extranet spécifiées, un nouveau nom et un mappage de valeur doivent être définis pour ces deux URL sous la clé LicensingRedirection.

5.  Répétez l'étape précédente pour tous les serveurs à rediriger.

6.  Fermez l'Éditeur du Registre.

