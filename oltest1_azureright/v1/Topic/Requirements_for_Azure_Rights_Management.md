---
description: na
keywords: na
title: Requirements for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: dc78321d-d759-4653-8818-80da74b6cdeb
---
# Conditions requises pour Azure Rights Management
Pour déployer Microsoft Azure Rights Management (Azure RMS) dans votre organisation, vérifiez d’abord que vous disposez des prérequis suivants. Vous pourrez ensuite suivre la [feuille de route pour le déploiement d'Azure Rights Management](../Topic/Azure_Rights_Management_Deployment_Roadmap.md) pour déployer Rights Management pour votre organisation.

|Condition requise|Plus d’informations|
|---------------------|-----------------------|
|Un abonnement au cloud pour RMS|Votre organisation doit posséder un abonnement au cloud prenant en charge RMS.<br /><br />Pour plus d’informations sur les licences, voir la section [Abonnements au cloud prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) de cette rubrique.|
|Annuaire Azure AD|Votre organisation doit disposer d’un annuaire Azure AD pour la prise en charge de l’authentification utilisateur pour RMS. De plus, si vous souhaitez utiliser vos comptes d’utilisateur à partir de votre annuaire local (AD DS), vous devez également configurer une intégration d’annuaire.<br /><br />La solution Multi-Factor Authentication (MFA) est prise en charge avec Azure RMS si vous disposez du logiciel client requis et avez correctement configuré l’infrastructure de support de MFA.<br /><br />Pour plus d’informations, voir la section [Annuaire Azure AD](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_AzureADTenant) de cette rubrique.|
|Périphériques client|Les utilisateurs doivent posséder des périphériques client (ordinateurs ou appareils mobiles) exécutant un système d’exploitation qui prend en charge RMS.<br /><br />Pour plus d’informations, voir la section [Périphériques client prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedDevices) de cette rubrique.|
|Applications|Les utilisateurs doivent exécuter des applications prenant en charge RMS.<br /><br />Pour plus d’informations, voir la section [Applications prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedApplications) de cette rubrique.|
|Infrastructure prenant en charge la connexion Internet et les services cloud dépendants|Si vous avez un pare-feu ou des périphériques réseau intervenants similaires qui nécessitent une configuration pour autoriser des connexions spécifiques, voir [URL et plages d’adresses IP Office 365](https://support.office.com/en-US/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).<br /><br />La liste d’URL et d’adresses IP figurant dans la section **Portail Office 365 et identité** s’applique au portail Office 365, aux ressources Azure Active Directory et à Azure Rights Management. Suivez les instructions fournies dans cet article pour être tenu au courant des modifications apportées à ces informations, en vous abonnant à un flux RSS.<br /><br />En plus des informations de l’article relatif à Office, voici des informations spécifiques pour Azure RMS :<br /><br />-   N’interrompez pas la connexion du client au service TLS (par exemple, pour effectuer un inspection au niveau du paquet). Cela a pour effet d’interrompre l’épinglage de certificat que les clients RMS utilisent avec les autorités de certification gérées par Microsoft pour sécuriser leur communication avec Azure RMS.<br />-   N’utilisez pas de configuration de proxy web qui s’authentifie pour le compte d’un utilisateur.|

Si vous souhaitez utiliser Azure RMS avec des serveurs locaux, les produits pris en charge sont les suivants :

-   Exchange Server

-   SharePoint Server

-   Serveurs de fichiers Windows Server prenant en charge l’infrastructure de classification des fichiers

Pour plus d’informations sur les exigences Azure RMS supplémentaires pour ce scénario, voir la section [Serveurs locaux prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedServers) de cette rubrique.

> [!IMPORTANT]
> Le scénario de déploiement suivant n’est pas pris en charge :
> 
> -   Exécution côte à côte d’AD RMS et d’Azure RMS dans la même organisation, sauf pendant la migration, comme décrit dans [Migration d'AD RMS vers Azure Rights Management](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md).
> 
> Il existe un chemin de migration pris en charge, [d’AD RMS à Azure RMS](http://technet.microsoft.com/library/Dn858447.aspx) et [d’Azure RMS à AD RMS](http://msdn.microsoft.com/library/azure/dn629429.aspx). Si vous déployez Azure RMS et décidez ensuite que vous ne souhaitez plus utiliser ce service cloud, voir [Désaffectation et désactivation de Gestion des droits Azure](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md).

Utilisez les informations des sections suivantes pour en savoir plus sur les exigences d’Azure RMS.

## <a name="BKMK_SupportedSubscriptions"></a>Abonnements au cloud prenant en charge Azure RMS
Pour utiliser Azure RMS, votre organisation doit disposer d’au moins un des abonnements suivants, avec un nombre suffisant de licences pour les utilisateurs et des services qui protègent les fichiers et les messages électroniques. Si vous avez un service qui applique une protection pour les utilisateurs (propriétaires des fichiers ou des messages électroniques), ces utilisateurs doivent avoir une de ces licences. Les utilisateurs qui se contentent de consommer (par exemple, lire et modifier) ces données protégées n’ont pas besoin de licence

-   Office 365

-   Gestion des droits Azure Premium (anciennement Azure RMS autonome)

-   Enterprise Mobility Suite

-   RMS for individuals

Pour plus d’informations et d’options d’inscription, voir les sections suivantes.

Pour une comparaison des licences des fonctionnalités Azure RMS pour les abonnements payants, voir [Comparaison des offres Rights Management Services (RMS)](http://technet.microsoft.com/dn858608).

### Abonnement Office 365
[Version d’évaluation gratuite de 30 jours : Entreprise E3](http://go.microsoft.com/fwlink/p/?LinkID=403802)

Cet abonnement est destiné aux organisations qui souhaitent utiliser les services Office en ligne et leurs fonctionnalités de gestion des droits relatifs à l’information, qui font appel à Azure RMS. Cependant, les abonnements Office 365 n’incluent pas tous Azure RMS.

|Option de licence|Office 365 Business Essentials|Office 365 Business Premium|Office 365 Entreprise E1<br /><br />Office 365 Éducation A1|Office 365 Entreprise E3<br /><br />Office 365 Éducation A3<br /><br />Office 365 pour le gouvernement G3|Office 365 Entreprise E4<br /><br />Office 365 Éducation A4<br /><br />Office 365 Secteur public G4|Office 365 Entreprise E5<br /><br />Office 365 Éducation A5<br /><br />Office 365 Secteur public G5|Office 365 Entreprise K1|SharePoint (plan 1)<br />SharePoint (plan 2)|Exchange Online (plan 1)<br />Exchange Online (plan 2)|
|---------------------|----------------------------------|-------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|----------------------------|--------------------------------------------|------------------------------------------------------|
|Protection des droits relatifs à l’information|Non|Non|Non|Oui|Oui|Oui|Non|Non|Non|

### Abonnement Gestion des droits Azure Premium
[Version d’évaluation gratuite de 30 jours](https://portal.microsoftonline.com/Signup/MainSignUp15.aspx?&amp;OfferId=A43415D3-404C-4df3-B31B-AAD28118A778&amp;dl=RIGHTSMANAGEMENT&amp;ali=1)

Cet abonnement, anciennement nommé Azure RMS autonome, est conçu pour les organisations désireuses d’utiliser Azure RMS mais ne disposant pas d’un abonnement l’incluant. Par exemple, si vous avez un abonnement à Office 365 Business Essentials ou Office 365 Entreprise E1, ces abonnements n’incluent pas Azure RMS (voir le tableau dans la section précédente). Pour pouvoir utiliser Azure RMS, vous pouvez acheter un abonnement Gestion des droits Azure Premium (ou un autre abonnement incluant Azure RMS, tel Office 365 Entreprise E4).

Pour plus d’informations, voir [Microsoft Azure Rights Management](http://products.office.com/business/microsoft-azure-rights-management).

Cet abonnement inclut également une période d’essai pour vous permettre de tester gratuitement Azure RMS (25 utilisateurs). Si l’abonnement expire avant que vous n’ayez acheté un abonnement de remplacement, voir la section « Que se passe-t-il lorsque l’abonnement d’essai arrive à expiration ? »

|Option de licence|Office 365 Business Essentials|Office 365 Business Premium|Office 365 Entreprise E1<br /><br />Office 365 Éducation A1|Office 365 Entreprise E3<br /><br />Office 365 Éducation A3<br /><br />Office 365 pour le gouvernement G3|Office 365 Entreprise E4<br /><br />Office 365 Éducation A4<br /><br />Office 365 Secteur public G4|Office 365 Entreprise E5<br /><br />Office 365 Éducation A5<br /><br />Office 365 Secteur public G5|Office 365 Entreprise K1|SharePoint Plan 1<br />SharePoint Plan 2|Exchange Online (plan 1)<br />Exchange Online (plan 2)|
|---------------------|----------------------------------|-------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|----------------------------|----------------------------------------|------------------------------------------------------|
|Protection des droits relatifs à l’information|Oui|Oui<sup>1</sup>|Oui|Oui|Oui|Oui|Oui|Oui|Oui|
<sup>1</sup> Pour Business Premium, il existe certaines restrictions au niveau du client : Vous pouvez protéger le contenu et consommer du contenu protégé avec RMS à l’aide d’Outlook Web App et de l’application de partage RMS. Vous pouvez consommer du contenu protégé à l’aide de toutes les autres applications Office, y compris Office Online et les applications clientes d’Office 365 Business Premium.

#### <a name="BKMK_TrialExpiryBehavior"></a>Que se passe-t-il lorsque l’abonnement d’essai arrive à expiration ?
Si votre abonnement d’essai arrive à expiration, vous n’aurez plus accès au contenu qui a été protégé à l’aide de votre abonnement d’essai Azure RMS. Toutefois, l’accès est automatiquement restauré si vous achetez un abonnement prenant en charge Azure RMS.

La seule exception qui vous permet de ne pas perdre l’accès lorsque votre abonnement arrive à expiration est si votre organisation a utilisé Azure RMS avec un abonnement RMS for Individuals avant d’avoir obtenu l’abonnement d’évaluation. Dans ce cas, l’accès au contenu auparavant protégé est conservé, même après l’expiration de l’abonnement d’évaluation.

### Abonnement Enterprise Mobility Suite
[Version d’évaluation gratuite de 30 jours](http://go.microsoft.com/fwlink/?LinkId=615385)

Cet abonnement est destiné aux organisations qui souhaitent associer Azure Active Directory Premium, Windows Intune et Azure Rights Management. Pour plus d’informations, voir la [Vue d’ensemble de Microsoft Enterprise Mobility](http://go.microsoft.com/fwlink/?LinkId=615386).

|Option de licence|Office 365 Business Essentials|Office 365 Business Premium|Office 365 Entreprise E1<br /><br />Office 365 Éducation A1|Office 365 Entreprise E3<br /><br />Office 365 Éducation A3<br /><br />Office 365 pour le gouvernement G3|Office 365 Entreprise E4<br /><br />Office 365 Éducation A4<br /><br />Office 365 Secteur public G4|Office 365 Entreprise E5<br /><br />Office 365 Éducation A5<br /><br />Office 365 Secteur public G5|Office 365 Entreprise K1|SharePoint Plan 1<br />SharePoint Plan 2|Exchange Online (plan 1)<br />Exchange Online (plan 2)|
|---------------------|----------------------------------|-------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|----------------------------|----------------------------------------|------------------------------------------------------|
|Protection des droits relatifs à l’information|Oui|Oui<sup>1</sup>|Oui|Oui|Oui|Oui|Oui|Oui|Oui|
<sup>1</sup> Pour Business Premium, il existe certaines restrictions au niveau du client : Vous pouvez protéger le contenu et consommer du contenu protégé avec RMS à l’aide d’Outlook Web App et de l’application de partage RMS. Vous pouvez consommer du contenu protégé à l’aide de toutes les autres applications Office, y compris Office Online et les applications clientes d’Office 365 Business Premium.

### Abonnement RMS for individuals
Cet abonnement est destiné aux membres d’une organisation n’ayant pas déployé Azure RMS ni AD RMS. Il permet à ces personnes de lire du contenu protégé par une organisation qui utilise Azure RMS, mais aussi de protéger leur propre contenu.

Pour plus d’informations, voir [RMS for Individuals et Azure Rights Management](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md).

## <a name="BKMK_AzureADTenant"></a>Annuaire Azure AD
Pour pouvoir utiliser Azure RMS, vous devez disposer d’un annuaire Azure AD. Vous devez utiliser le compte de votre organisation correspondant à cet annuaire pour vous connecter au portail Azure Classic, où vous pouvez, par exemple, configurer et gérer les modèles Rights Management.

Si vous n’avez pas d’abonnement Azure pour votre organisation, vous pouvez en obtenir un en vous inscrivant pour une évaluation gratuite : Consultez la page [Mise en route Azure](https://account.windowsazure.com/organization) et suivez les instructions.

Pour plus d’informations, reportez-vous aux ressources suivantes dans la documentation Azure Active Directory :

-   [Qu’est-ce qu’un annuaire Azure AD ?](http://msdn.microsoft.com/en-us/library/185da266-58a9-43e6-9c66-2c8f702545c6)

-   [Comment sont associés les abonnements Azure et Azure AD ?](http://msdn.microsoft.com/en-us/library/edf05c2e-944a-4da5-a330-dc9dc479f127)

Si vous souhaitez intégrer votre annuaire Azure AD à vos forêts AD locales, voir [Intégration d’annuaire](http://msdn.microsoft.com/en-us/library/bf82bdff-2467-403b-8c1a-0e9eebcf31e8).

> [!NOTE]
> Si vous avez des appareils mobiles ou des ordinateurs Mac qui s’authentifient localement par le biais des services AD FS ou d’un fournisseur d’authentification équivalent :
> 
> -   Vous devez utiliser soit les services AD FS sur la version serveur minimale de **Windows Server 2012 R2**, soit un autre fournisseur d’authentification prenant en charge le protocole OAuth 2.0.

### <a name="BKMK_MFA"></a>Multi-Factor Authentication (MFA) et Azure RMS
L’utilisation de Multi-Factor Authentication avec Azure RMS requiert au moins l’un des éléments suivants :

-   Office 2013 (version minimale) :

    -   Si vous avez Office 2013, vous devez également installer la [mise à jour du 9 juin 2015 pour Office 2013 (KB3054853)](https://support.microsoft.com/kb/3054853). Pour plus d’informations sur cette mise à jour et la manière dont l’authentification moderne introduit la connexion basée sur Azure Active Directory Authentication Library (ADAL) à Office 2013, voir [Office 2013 modern authentication public preview announced](https://blogs.office.com/2015/03/23/office-2013-modern-authentication-public-preview-announced/) (en anglais) sur le blog Office.

-   Application de partage Rights Management pour Windows :

    -   Vous devez avoir installé la version minimale 1.0.1908.0, ce que vous pouvez vérifier dans la rubrique Programmes et fonctionnalités du Panneau de configuration. Pour plus d’informations sur l’application de partage, voir  [Application de partage Rights Management pour Windows](../Topic/Rights_Management_Sharing_Application_for_Windows.md).

-   Application de partage Rights Management pour appareils mobiles et ordinateurs Mac :

    -   Assurez-vous que vous avez installé la dernière version. La prise en charge de MFA a été introduite dans la version de septembre 2015 de l’application de partage RMS.

Ensuite, configurez votre solution MFA :

-   Pour les clients gérés par Microsoft (disposant d’Azure Active Directory ou d’Office 365) :

    -   Configurez Azure MAF pour appliquer l’authentification MFA aux utilisateurs. Pour obtenir des instructions, voir [Prise en main avec Azure Multi-Factor Authentication dans le cloud](https://azure.microsoft.com/documentation/articles/multi-factor-authentication-get-started-cloud/) dans la documentation sur Azure.

        Pour plus d’informations sur Azure MFA, voir [Présentation d’Azure Multi-Factor Authentication](https://azure.microsoft.com/documentation/articles/multi-factor-authentication/)

-   Pour les clients fédérés (utilisant des serveurs de fédération locaux) :

    -   Configurez vos serveurs de fédération pour Azure Active Directory ou Office 365. Par exemple, si vous utilisez AD FS, voir [Configurer des méthodes d’authentification supplémentaires pour AD FS](https://technet.microsoft.com/library/dn758113.aspx) sur TechNet.

        Pour plus d’informations sur ce scénario, voir  [The Works with Office 365 – Identity program now streamlined](https://blogs.office.com/2014/01/30/the-works-with-office-365-identity-program-now-streamlined/) (en anglais) sur le blog Office.

## <a name="BKMK_SupportedDevices"></a>Périphériques client prenant en charge Azure RMS
Utilisez les sections suivantes pour identifier les appareils qui prennent en charge Azure Rights Management (RMS) ainsi que les fonctionnalités prises en charge :

-   [Ordinateurs](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_RMSSupportedComputers)

-   [Appareils mobiles](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_RMSSupportedMobileDevices)

-   [Fonctionnalités d’un appareil client](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_ClientCapabilities)

### <a name="BKMK_RMSSupportedComputers"></a>Ordinateurs
Les systèmes d’exploitation pour ordinateurs prenant en charge Azure Rights Management sont les suivants :

-   **Windows 7** (x86, x64)

-   **Windows 8** (x86, x64)

-   **Windows 8.1** (x86, x64)

-   **Windows 10** (x86, x64)

-   **Mac OS X** : version minimale de Mac OS X 10.8 (Mountain Lion)

### <a name="BKMK_RMSSupportedMobileDevices"></a>Appareils mobiles
Les systèmes d’exploitation pour appareils mobiles prenant en charge Azure Rights Management sont les suivants :

-   **Windows Phone** : Windows Phone 8.1

-   **Téléphones et tablettes Android** : version minimum d’Android 4.0.3

-   **iPhone et iPad** : version minimum d’iOS 7.0

-   **Tablettes Windows RT** : Windows 8 RT, Windows 8.1 RT

### <a name="BKMK_ClientCapabilities"></a>Fonctionnalités d’un appareil client
Tous les appareils client pris en charge ne peuvent pas tous utiliser les fonctionnalités RMS actuellement. Le tableau suivant vous permet d’identifier les applications qui prennent en charge les fonctionnalités RMS ainsi que les exceptions.

Sauf spécification contraire, les fonctionnalités prises en charge s’appliquent à Azure RMS et à AD RMS. Par ailleurs, la prise en charge d’AD RMS sur iOS, Android, OS X et Windows Phone 8.1 nécessite [Active Directory Rights Management Services Mobile Device Extension](http://technet.microsoft.com/library/a69ead9d-7dd3-4b38-9830-4728e9757341).

Informations sur les colonnes du tableau :

-   **PDF protégé** : fichiers avec l’extension de nom de fichier .ppdf qui sont créés automatiquement lorsque vous utilisez l’application de partage RMS pour partager des fichiers Office et des fichiers PDF par message électronique. L’application de partage RMS comprend un lecteur de fichiers PDF protégés. Si vous avez déjà créé des fichiers PDF protégés avec Azure RMS ou AD RMS, utilisez Foxit Reader ou Nitro Pro pour continuer à lire ces fichiers sur des appareils Windows, iOS et Android.

-   **E-mail :** les clients de messagerie répertoriés peuvent protéger le message électronique, ce qui a pour effet de protéger automatiquement tout fichier joint. Dans ce scénario, la fonctionnalité d’aperçu du client peut afficher le contenu protégé (message et pièce jointe) aux destinataires autorisés. Cependant, si une pièce jointe est protégée mais pas le message électronique qui la contient, la fonctionnalité d’aperçu du client ne peut pas afficher la pièce jointe protégée aux destinataires autorisés.

-   **Autres types de fichiers** : les fichiers texte et image incluent les fichiers ayant une extension de nom de fichier .txt, .xml, .jpg et jpeg. Ces fichiers changent d’extension de nom de fichier une fois qu’ils sont protégés en mode natif par RMS et ils basculent en lecture seule. Les fichiers qui ne peuvent pas être protégés en mode natif ont une extension de nom de fichier .pfile une fois qu’ils sont protégés de manière générique par RMS. Pour plus d’informations, voir les sections [Niveaux de protection : native et générique](https://technet.microsoft.com/library/dn339003.aspx) et [Types de fichiers pris en charge et extensions de nom de fichier](https://technet.microsoft.com/library/dn339003.aspx) du [Guide de l’administrateur de l’application de partage Rights Management](http://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx).

|**Système d’exploitation de l’appareil**|Word, Excel, PowerPoint|PDF protégé|Courrier électronique|Autres types de fichiers|
|--------------------------------------------|---------------------------|---------------|-------------------------|----------------------------|
|**Windows**|Office 2010<br /><br />Office 2013<br /><br />Applications Office Mobile (Azure RMS uniquement) <sup>1</sup><br /><br />Office Online<sup>2</sup>|Gaaiho Doc<br /><br />Client PDF GigaTrust Desktop pour Adobe<br /><br />Foxit Reader<br /><br />Nitro PDF Reader<br /><br />Application de partage RMS|Outlook 2010<br /><br />Outlook 2013<br /><br />Outlook Web App (OWA)<sup>3</sup><br /><br />Windows Mail<sup>4</sup>|Application de partage RMS pour Windows : texte, images, pfile<br /><br />Siemens JT2Go : fichiers JT (Windows 10 uniquement)|
|**iOS**|Office pour iPad et iPhone<sup>5</sup><br /><br />Office Online<sup>2</sup><br /><br />TITUS Docs|Foxit Reader<br /><br />Application de partage RMS<sup>1</sup><br /><br />TITUS Docs|NitroDesk<sup>4</sup><br /><br />Office pour iPad et iPhone<sup>4</sup><br /><br />OWA pour iOS<sup>3</sup><br /><br />Secure Islands IQProtector <sup>1</sup><br /><br />TITUS Mail|Application de partage RMS<sup>1</sup> : texte, images, pfile<br /><br />Docs TITUS : Pfile|
|**Android**|GigaTrust App pour Android<br /><br />Office Online<sup>2</sup>|GigaTrust App pour Android<br /><br />Foxit Reader<br /><br />Application de partage RMS<sup>1</sup>|9Folders<sup>4</sup><br /><br />GigaTrust App pour Android<sup>4</sup><br /><br />NitroDesk<sup>4</sup><br /><br />OWA pour Android<sup>3</sup> <sup>6</sup><br /><br />Samsung Email (S3 et version ultérieure)<sup>6</sup><br /><br />Secure Islands IQProtector <sup>1</sup><br /><br />TITUS Classification for Mobile|Application de partage RMS<sup>1</sup> : texte, images, pfile|
|**OS X**|Office 2011 (AD RMS uniquement)<br /><br />Office 2016 pour Mac<br /><br />Office Online<sup>2</sup>|Foxit Reader<br /><br />Application de partage RMS<sup>1</sup>|Outlook 2011 (AD RMS uniquement)<br /><br />Outlook 2016 pour Mac<br /><br />Outlook pour Mac|Application de partage RMS<sup>1</sup> : texte, images, pfile|
|**Windows RT**|Office 2013 RT<br /><br />Office Online<sup>2</sup>|Non prise en charge|Outlook 2013 RT<br /><br />Application de messagerie pour Windows<br /><br />Windows Mail<sup>4</sup>|Siemens JT2Go : fichiers JT|
|**Windows Phone 8.1**|Office Mobile (AD RMS uniquement)|Application de partage RMS<sup>1</sup>|Outlook Mobile<sup>4</sup>|Application de partage RMS<sup>1</sup> : texte, images, pfile|
|**Blackberry 10**|Non prise en charge|Non prise en charge|Messagerie Blackberry<sup>4</sup>|Non prise en charge|
<sup>1</sup> Prend en charge l’affichage de contenu protégé.

<sup>2</sup> Prend en charge l’affichage de contenu protégé dans SharePoint Online, OneDrive Entreprise et Outlook Web Access.

<sup>3</sup> Si un destinataire possédant une boîte aux lettres Exchange sur site reçoit un message électronique protégé, il ne peut ouvrir ce contenu que dans un client de messagerie riche, tel qu’Outlook.  Ce contenu ne peut être ouvert à partir d’Outlook Web Access.

<sup>4</sup> Utilise l’IRM Exchange ActiveSync, qui doit être activée par l’administrateur Exchange. Les utilisateurs peuvent afficher, répondre et répondre à tous pour les messages électroniques protégés, mais ne peuvent pas protéger eux-mêmes de nouveaux messages.

Si un destinataire possédant une boîte aux lettres Exchange sur site reçoit un message électronique protégé en provenance d’une autre organisation utilisant Exchange, il ne peut ouvrir ce contenu que dans un client de messagerie riche, tel qu’Outlook.  Ce contenu ne peut être ouvert à partir sur un appareil utilisant l’IRM Exchange ActiveSync.

<sup>5</sup> Prend en charge l’affichage et l’édition de documents protégés. Pour plus d’informations, voir la publication suivante sur le blog Office : [La prise en charge d’Azure Rights Management est fournie pour Office pour iPad et iPhone](https://blogs.office.com/2015/07/22/azure-rights-management-support-comes-to-office-for-ipad-and-iphone-2/)

<sup>6</sup> Pour plus d’informations, voir le billet suivant sur le blog Office : [OWA for Android now available on select devices](http://blogs.office.com/2014/06/11/owa-for-android-now-available-on-select-devices/)

> [!TIP]
> Pour plus d’informations sur la prise en charge de RMS à venir dans Office pour différentes plateformes, voir le billet suivant sur le blog Office : [Office everywhere, encryption everywhere](http://blogs.office.com/2015/02/18/office-everywhere-encryption-everywhere/)

## <a name="BKMK_SupportedApplications"></a>Applications prenant en charge Azure RMS
Les applications suivantes prennent en charge Azure RMS en mode natif. RMS est étroitement intégré à ces applications grâce à l’utilisation d’API RMS pour la prise en charge des restrictions d’utilisation. Ces applications sont également connues comme étant compatibles avec RMS :

-   **Des applications Microsoft Office** (Word, Excel, PowerPoint et Outlook) des suites suivantes peuvent protéger du contenu à l’aide d’Azure RMS :

    -   Office 365 ProPlus

    -   Office 365 Entreprise E3

    -   Office 365 Entreprise E4

    -   Office 365 Entreprise E5

    -   Office Professionnel Plus 2016

    -   Office Professionnel Plus 2013

    -   Office Professionnel Plus 2010

    D’autres éditions d’Office (à l’exception d’Office 2007) peuvent utiliser du contenu protégé.

    > [!NOTE]
    > Azure RMS avec Office Professionnel Plus 2010 ou Office Professionnel 2010 :
    > 
    > -   Requiert l’application de partage Rights Management pour Windows
    > -   Non pris en charge sur Windows 10

-   **Application de partage Rights Management pour Windows**

    Pour plus d’informations sur l’application de partage Rights Management pour Windows, reportez-vous aux ressources suivantes :

    -   [guide de l’administrateur de l’application de partage Rights Management](http://technet.microsoft.com/library/dn339003.aspx)

    -   [Guide d’utilisation de l’application de partage Rights Management](http://technet.microsoft.com/library/dn339006.aspx)

-   **Application de partage Rights Management pour plateformes mobiles**

    Pour plus d’informations sur l’application de partage Rights Management pour plateformes mobiles, reportez-vous aux ressources suivantes :

    -   Téléchargez l’application correspondante en utilisant les liens figurant sur la page [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970)

    -   Si vous gérez des appareils mobiles à l’aide de Microsoft Intune, vous pouvez déployer et configurer l’application sur des [appareils iOS et Android en tant qu’application gérée de stratégie](https://technet.microsoft.com/library/dn878026.aspx).

    -   [FAQ relatif à l’application de partage Microsoft Rights Management pour plateformes mobiles](http://technet.microsoft.com/dn451248)

-   **Autres applications prenant en charge les API RMS :**:

    -   Applications métier écrites en interne grâce au kit de développement logiciel (SDK) RMS

    -   Applications de fournisseurs de logiciels écrites grâce au kit de développement logiciel (SDK) RMS

    Pour plus d’informations sur le Kit de développement logiciel (SDK), voir le [Kit de développement logiciel (SDK) Microsoft Rights Management](http://msdn.microsoft.com/library/hh552972%28v=vs.85%29.aspx).

> [!IMPORTANT]
> Les applications suivantes ne sont actuellement pas prises en charge par Azure RMS :
> 
> -   Microsoft Office pour Mac 2011
> -   Microsoft OneDrive Entreprise pour SharePoint Server 2013
> -   Visionneuse XPS
> 
> De plus, l’application de partage RMS présente les restrictions suivantes :
> 
> -   Pour les ordinateurs Windows : nécessite une version Windows 7 Service Pack 1 minimum

Pour plus d’informations sur la prise en charge d’Azure RMS par ces applications, voir [Mode de prise en charge d'Azure Rights Management par les applications](../Topic/How_Applications_Support_Azure_Rights_Management.md).

Pour plus d’informations sur leur configuration, voir [Configuration d'applications pour Azure Rights Management](../Topic/Configuring_Applications_for_Azure_Rights_Management.md).

## <a name="BKMK_SupportedServers"></a>Serveurs locaux prenant en charge Azure RMS
Les produits de serveurs locaux suivants sont acceptés avec le connecteur Azure RMS, qui agit en tant qu’interface de communication (relais) entre les serveurs locaux et Azure RMS. De plus, cette configuration nécessite que vous configuriez la synchronisation des annuaires entre vos forêts Active Directory et Azure Active Directory.

-   **Exchange Server** :

    -   Exchange Server 2013

    -   Exchange Server 2010

-   **Office SharePoint Server** :

    -   Office SharePoint Server 2013

    -   Office SharePoint Server 2010

-   **Serveurs de fichiers qui exécutent Windows Server et utilisent l’infrastructure de classification des fichiers (ICF)** :

    -   Windows Server 2012 R2

    -   Windows Server 2012

    > [!NOTE]
    > Les serveurs de fichiers qui exécutent Windows Server 2008 R2 n’ont pas d’action de tâche de gestion de fichiers intégrée pour appliquer une protection RMS. Par conséquent, vous ne pouvez pas utiliser le connecteur RMS pour ce scénario. En revanche, vous pouvez utiliser l’infrastructure de classification des fichiers et Azure RMS sur ces systèmes d’exploitation si vous configurez une tâche de gestion de fichiers personnalisée de sorte qu’elle exécute un exécutable ou un script capable de protéger les fichiers à l’aide d’Azure RMS. Par exemple, un script Windows PowerShell utilisant les [applets de commande de protection RMS](https://msdn.microsoft.com/library/azure/mt433195.aspx).
    > 
    > Vous pouvez également utiliser ces applets de commande avec des serveurs exécutant des versions ultérieures de Windows Server, l’avantage étant que ces applets de commande peuvent protéger tous les types de fichiers. Le connecteur RMS protège uniquement les fichiers Office. Pour obtenir des instructions, voir [Protection RMS avec l'infrastructure de classification des fichiers &#40;ICF&#41; de Windows Server](../Topic/RMS_Protection_with_Windows_Server_File_Classification_Infrastructure__FCI_.md).

Le connecteur RMS est pris en charge sur Windows Server 2012 R2, Windows Server 2012 et Windows Server 2008 R2.

Pour plus d’informations sur la configuration du connecteur RMS pour ces serveurs locaux, voir [Déploiement du connecteur Azure Rights Management](../Topic/Deploying_the_Azure_Rights_Management_Connector.md).

## Voir aussi
[Prise en main d'Azure Rights Management](../Topic/Getting_Started_with_Azure_Rights_Management.md)

