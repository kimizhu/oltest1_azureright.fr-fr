---
description: na
keywords: na
title: How Applications Support Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2cdc7bde-4044-4021-b887-11476f99afd9
---
# Mode de prise en charge d&#39;Azure Rights Management par les applications
Utilisez les informations suivantes pour mieux comprendre comment les applications (notamment les applications Office comme Word, Excel, PowerPoint et Outlook) et les services (tels qu’Exchange et SharePoint) de vos utilisateurs finaux peuvent utiliser la [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] Microsoft pour protéger les données de votre organisation :

-   [Application de partage RMS pour Windows et les plateformes mobiles](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_SharingAppIntro)

-   [Applications Office : Word, Excel, PowerPoint, Outlook](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_OfficeAppsIntro)

    -   [Exchange Online et Exchange Server](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_ExchangeIntro)

    -   [SharePoint Online et SharePoint Server](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_SharePointIntro)

-   [Serveurs de fichiers qui exécutent Windows Server et utilisent l’infrastructure de classification des fichiers (ICF)](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_FCIIntro)

-   [Autres applications prenant en charge les API RMS](../Topic/How_Applications_Support_Azure_Rights_Management.md#BKMK_APIAppsIntro)

> [!NOTE]
> Pour vérifier les applications et versions que la [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] (Azure RMS) prend en charge, voir [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md).

Dans certains cas, la protection des informations est automatiquement appliquée, conformément aux stratégies que vous configurez. Par exemple, c’est le cas avec les bibliothèques SharePoint, les fichiers classifiés et les règles de transport Exchange. Dans d’autres cas, les utilisateurs doivent appliquer eux-mêmes la protection des informations depuis les applications, soit en sélectionnant un modèle, soit en sélectionnant des options spécifiques. Par exemple, c’est le cas quand les utilisateurs partagent un fichier par messagerie électronique ou protègent un fichier en place en restreignant l’accès ou l’utilisation aux utilisateurs sélectionnés ou aux utilisateurs extérieurs à l’organisation.

Les modèles permettent aux utilisateurs (et administrateurs qui configurent des stratégies) d’appliquer facilement le niveau adéquat de protection et de restreindre l’accès aux personnes internes de l’organisation. Bien que [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] soit assorti de deux modèles par défaut, vous aurez probablement besoin de créer des modèles personnalisés pour réduire le temps passé par ces personnes à spécifier des options individuelles. Pour plus d’informations, voir [Configuration de modèles personnalisés pour Azure Rights Management](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md).

Quand les utilisateurs doivent appliquer eux-mêmes la protection des informations, veillez à leur fournir des instructions et des conseils sur la manière de le faire et le moment auquel le faire. Ces instructions doivent être appropriées à l’application et aux versions qu’ils utilisent et à la manière dont ils les utilisent. Les conseils sur l’application de la protection des informations doivent refléter votre secteur d’activité. Pour plus d’informations, voir [Aide aux utilisateurs sur la protection de fichiers grâce à Azure Rights Management](../Topic/Helping_Users_to_Protect_Files_by_Using_Azure_Rights_Management.md).

Pour plus d’informations sur la configuration de ces applications pour Azure RMS, voir [Configuration d'applications pour Azure Rights Management](../Topic/Configuring_Applications_for_Azure_Rights_Management.md).

> [!TIP]
> Pour des exemples détaillés et des captures d’écran d’applications utilisant Azure RMS, voir la section [Azure RMS en action : ce que voient les utilisateurs et les administrateurs](../Topic/What_is_Azure_Rights_Management_.md#BKMK_RMSpictures) de la rubrique [Qu'est-ce qu'Azure Rights Management ?](../Topic/What_is_Azure_Rights_Management_.md).

## <a name="BKMK_SharingAppIntro"></a>Application de partage RMS pour Windows et les plateformes mobiles
L’application de partage RMS est une application téléchargeable gratuitement qui est nécessaire pour prendre en charge Office 2010, mais également recommandée pour les ordinateurs Windows et Mac, ainsi que les appareils mobiles. L’un de ses avantages est qu’elle est capable d’appliquer une protection générique aux applications et fichiers qui ne prennent pas en charge [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] de manière native, ce qui signifie que tous les fichiers peuvent être protégés. Pour plus d’informations sur les différents niveaux de protection, voir la section [Niveaux de protection : native et générique](http://technet.microsoft.com/library/dn339003.aspx) du [Guide de l’administrateur sur l’application de partage Rights Management](http://technet.microsoft.com/library/dn339003.aspx).

Lorsque les utilisateurs protègent leurs fichiers à l’aide de l’application de partage RMS, ils peuvent également suivre les documents protégés et, si nécessaire, révoquer l’accès à ceux-ci. Ils doivent pour cela utiliser le [site de suivi des documents](http://go.microsoft.com/fwlink/?LinkId=529562).

Pour les ordinateurs Windows, l’application de partage RMS s’intègre discrètement dans les applications que les utilisateurs utilisent déjà et ainsi les améliorent :

-   Un complément Office pour Word, Excel, PowerPoint et Outlook est installé. Il fournit aux utilisateurs un bouton **Partage protégé** sur le ruban, qui permet d’appeler une boîte de dialogue pratique de paramètres couramment utilisés pour protéger des fichiers à envoyer par messagerie électronique. Ce bouton fournit également un moyen rapide d’accéder au site de suivi des documents.

-   Une nouvelle option par clic droit pour l’Explorateur de fichiers. Celle-ci fournit aux utilisateurs une option **Protéger sur place**, qui permet d’appeler une boîte de dialogue pratique de paramètres couramment utilisés pour protéger des fichiers stockés sur un disque.

-   Une visionneuse pour ouvrir des fichiers qui ont été protégés par [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)]. Cette visionneuse est automatiquement appelée quand aucune autre application installée n’est capable d’ouvrir le fichier protégé.

-   Une configuration principale d’Office 2010 qui permet à Word, Excel, PowerPoint et Outlook inclus dans cette suite de fonctionner de manière transparente avec [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)].

Bien que l’application de partage RMS pour Windows puisse être téléchargée et installée pour un seul ordinateur via la page [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970), elle prend également en charge un déploiement d’entreprise avec une installation sans assistance et une configuration personnalisée. Pour plus d’informations, consultez les ressources suivantes :

-   [guide de l’administrateur de l’application de partage Rights Management](http://technet.microsoft.com/library/dn339003.aspx)

-   [Guide d’utilisation de l’application de partage Rights Management](http://technet.microsoft.com/library/dn339006.aspx)

L’application de partage RMS pour les appareils mobiles prend en charge les appareils mobiles les plus couramment utilisés, comme les iPad et iPhone, les appareils Android, Windows Phone et Windows RT. Les utilisateurs peuvent télécharger cette application auprès de la boutique adéquate. Des liens vers celle-ci sont également disponibles dans la [page Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970).

## <a name="BKMK_OfficeAppsIntro"></a>Applications Office : Word, Excel, PowerPoint, Outlook
Ces applications prennent en charge la Gestion des droits de manière native grâce au service de Gestion des droits relatifs à l’information (IRM), et permettent aux utilisateurs d’appliquer une protection à un document enregistré ou à un message électronique à envoyer. Les utilisateurs peuvent appliquer des modèles ou choisir des paramètres personnalisés pour l’accès, les droits et les restrictions d’utilisation. Par exemple, ils peuvent configurer un fichier pour qu’il puisse être accessible uniquement par les personnes de votre organisation. Ils peuvent également déterminer si le fichier peut être modifié, s’il est disponible en lecture seule uniquement ou empêcher son impression. Pour les fichiers sensibles, ils peuvent configurer une date d’expiration (directement ou en appliquant un modèle) à laquelle le fichier ne sera plus accessible. Pour Outlook, les utilisateurs peuvent également choisir l’option **Ne pas transférer** pour éviter toute fuite de données.

### <a name="BKMK_ExchangeIntro"></a>Exchange Online et Exchange Server
Quand vous utilisez Exchange Online ou Exchange Server, vous pouvez utiliser l’intégration de la Gestion des droits relatifs à l’information (IRM), laquelle propose des solutions supplémentaires de protection des informations :

-   **Exchange ActiveSync IRM** pour que les appareils mobiles puissent protéger des messages électroniques et utiliser des messages électroniques protégés.

-   Prise en charge par RMS d’**Outlook Web App**, implémenté de manière similaire au client Outlook, pour que les utilisateurs puissent protéger des messages électroniques par des modèles ou en spécifiant des options individuelles, et qu’ils puissent lire et utiliser les messages électroniques protégés qui leur sont envoyés.

-   **Règles de protection** pour les clients Outlook qu’un administrateur configure pour appliquer automatiquement des modèles RMS aux messages électroniques envoyés à des destinataires spécifiés. Par exemple, quand des messages électroniques internes sont envoyés à votre service juridique, ils peuvent uniquement être lus par les membres du service juridique et ne peuvent pas être transférés. Les utilisateurs voient la protection appliquée au message électronique avant de l’envoyer et, par défaut, ils peuvent la supprimer s’ils décident qu’elle est inutile. Les messages électroniques sont chiffrés avant d’être envoyés. Pour plus d’informations, voir [Règles de protection Outlook](http://technet.microsoft.com/library/dd638178%28v=exchg.150%29.aspx) et [Créer une règle de protection d’Outlook](http://technet.microsoft.com/library/dd638196%28v=exchg.150%29.aspx) dans la bibliothèque Exchange.

-   **Règles de transport** qu’un administrateur configure pour appliquer automatiquement des modèles RMS aux messages électroniques en fonction de propriétés telles que l’expéditeur, le destinataire, l’objet du message et son contenu. Ces règles sont similaires par leur concept aux règles de protection, mais elles ne permettent pas aux utilisateurs de supprimer la protection, elles sont applicables à Outlook Web Access et aux messages électroniques envoyés par des appareils mobiles et elles ne chiffrent pas les messages avant leur envoi depuis le client. Pour plus d’informations, voir [Créer une règle de protection de transport](http://technet.microsoft.com/library/dd302432.aspx) dans la bibliothèque Exchange.

-   **Stratégies de protection contre la perte de données (DLP)** qui contiennent des ensembles de conditions permettant de filtrer des messages électroniques et de prendre des mesures de prévention contre la perte de données pour le contenu confidentiel ou sensible (par exemple, les informations personnelles ou de carte de crédit). Vous pouvez utiliser des conseils de stratégie quand des données sensibles sont détectées, pour alerter les utilisateurs de l’éventuel besoin d’appliquer une protection des informations, en fonction des informations contenues dans le message électronique. Pour plus d’informations, voir [Protection contre la perte de données](http://technet.microsoft.com/library/jj150527%28v=exchg.150%29.aspx) dans la bibliothèque Exchange.

-   **Chiffrement de messages Office 365** qui utilise des règles de transport pour envoyer des messages électroniques chiffrés aux personnes extérieures à votre entreprise. Ces messages sont lus dans un navigateur doté d’une interface similaire à celle d’Outlook Web App. Vous pouvez personnaliser le texte de la clause d’exclusion de responsabilité et le texte d’en-tête dans les messages électroniques chiffrés de votre entreprise, et même ajouter son logo. Pour plus d’informations, voir [Chiffrement de messages Office 365](http://office.microsoft.com/o365-message-encryption-FX104179182.aspx) sur le site web Office.

Si vous utilisez Exchange Server, vous pouvez utiliser les fonctionnalités de protection des informations avec [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] en déployant le connecteur RMS, qui joue le rôle de relais entre vos serveurs locaux et le service cloud RMS. Pour plus d’informations, voir [Déploiement du connecteur Azure Rights Management](../Topic/Deploying_the_Azure_Rights_Management_Connector.md).

### <a name="BKMK_SharePointIntro"></a>SharePoint Online et SharePoint Server
Quand vous utilisez SharePoint Online ou SharePoint Server, vous pouvez utiliser l’intégration de la Gestion des droits relatifs à l’information (IRM), qui permet aux administrateurs de protéger des listes ou bibliothèques pour que, quand un utilisateur extrait un document, le fichier soit protégé afin que seules les personnes autorisées puissent l’afficher et l’utiliser conformément aux stratégies de protection des informations que vous spécifiez. Par exemple, le fichier peut être en lecture seule, vous pouvez désactiver la copie du texte, vous pouvez empêcher l’enregistrement d’une copie locale et l’impression du fichier.

Pour les listes et bibliothèques, la protection des informations est toujours appliquée par un administrateur, jamais un utilisateur final. Et elle est appliquée au niveau de la liste ou bibliothèque de tous les documents inclus dans le conteneur, plutôt qu’à des fichiers individuels.  Si vous utilisez SharePoint Online, les utilisateurs peuvent également appliquer l’IRM à leur bibliothèque OneDrive Entreprise.

Le service IRM doit d’abord être activé pour SharePoint. Ensuite, vous spécifiez la Gestion des droits relatifs à l’information pour une bibliothèque. Pour SharePoint Online et OneDrive Entreprise, les utilisateurs peuvent également spécifier la Gestion des droits relatifs à l’information pour leur bibliothèque OneDrive Entreprise. SharePoint n’utilise pas de modèle de stratégie de droits, même s’il existe des paramètres de configuration de SharePoint que vous pouvez sélectionner, qui correspondent étroitement aux paramètres que vous pouvez spécifier dans des modèles.

Si vous utilisez SharePoint Server, vous pouvez utiliser les fonctionnalités de protection des informations avec [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] en déployant le connecteur RMS, qui joue le rôle de relais entre vos serveurs locaux et le service cloud RMS. Pour plus d’informations, voir [Déploiement du connecteur Azure Rights Management](../Topic/Deploying_the_Azure_Rights_Management_Connector.md).

> [!NOTE]
> La Gestion des droits relatifs à l’information avec SharePoint est actuellement soumise à certaines limitations :
> 
> -   Vous ne pouvez pas utiliser les modèles personnalisés ou par défaut que vous gérez dans le portail Azure Classic.
> -   Les fichiers comportant une extension .PPDF pour les fichiers PDF protégés ne sont pas pris en charge. Les fichiers comportant une extension .PDF et protégés par RMS en mode natif sont pris en charge lorsque vous utilisez un lecteur PDF qui prend en charge RMS en mode natif.
> -   Office sur les appareils mobiles ne prenant pas encore en charge RMS, ces appareils doivent utiliser un navigateur pour afficher les fichiers protégés par RMS, qui sont en lecture seule.

Azure RMS applique des restrictions d’utilisation et un chiffrement de données aux documents téléchargés à partir de SharePoint, mais pas aux documents créés dans SharePoint ou chargés sur la bibliothèque. Pour plus d’informations sur la façon dont les documents sont protégés avant leur téléchargement, voir [Chiffrement de données dans OneDrive Entreprise et SharePoint Online](https://technet.microsoft.com/library/dn905447.aspx) dans la documentation SharePoint.

Pour plus d’informations sur l’utilisation d’Azure RMS avec SharePoint, voir la publication suivante sur le blog Office : [Nouveautés du service de Gestion des droits relatifs à l’information dans SharePoint et SharePoint Online](http://blogs.office.com/2012/11/09/whats-new-with-information-rights-management-in-sharepoint-and-sharepoint-online/)

## <a name="BKMK_FCIIntro"></a>Serveurs de fichiers qui exécutent Windows Server et utilisent l’infrastructure de classification des fichiers (ICF)
Quand vous configurez Windows Server pour utiliser l’infrastructure de classification des fichiers, la fonctionnalité Outils de gestion de ressources pour serveur de fichiers (FSRM) peut analyser les fichiers locaux pour déterminer s’ils contiennent des données sensibles. Quand les fichiers répondent à ces critères, ils sont balisés avec des propriétés de classification définies par un administrateur. L’infrastructure de classification des fichiers peut effectuer automatiquement une action, selon la classification. L’une de ces actions inclut l’application de la protection des informations à l’aide de la [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] et le déploiement du connecteur Rights Management (également appelé connecteur RMS). Les fichiers Office sont alors automatiquement protégés par Azure RMS.

Pour protéger tous les types de fichiers, au lieu d’utiliser le connecteur RMS, exécutez un script Windows PowerShell, en utilisant les applets de commande de l’[outil de protection RMS](https://www.microsoft.com/en-us/download/details.aspx?id=47256).

Les stratégies de classification sont entièrement configurables et très extensibles pour vous permettre d’empêcher d’éventuelles fuites de données par des utilisateurs autorisés ou non autorisés. L’outil de protection peut même contribuer à réduire le risque de fuite de données dues aux administrateurs réseau, car vous pouvez configurer des stratégies qui n’exigent pas que ceux-ci aient accès aux fichiers.

Pour obtenir des instructions relatives au déploiement et à la configuration du connecteur RMS pour les fichiers Office, voir [Déploiement du connecteur Azure Rights Management](../Topic/Deploying_the_Azure_Rights_Management_Connector.md).

Pour obtenir des instructions sur l’utilisation de scripts Windows PowerShell pour tous types de fichiers, voir [Protection RMS avec l'infrastructure de classification des fichiers &#40;ICF&#41; de Windows Server](../Topic/RMS_Protection_with_Windows_Server_File_Classification_Infrastructure__FCI_.md).

## <a name="BKMK_APIAppsIntro"></a>Autres applications prenant en charge les API RMS
À l’aide du Kit de développement logiciel (SDK) RMS, vos développeurs internes peuvent écrire des applications métiers pour prendre en charge [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] de manière native. Le mode d’intégration de la protection des informations à ces applications dépend de la manière dont elles sont écrites. Par exemple, l’intégration peut être automatiquement appliquée en demandant un minimum d’interaction utilisateur, ou pour une expérience plus personnalisée, les utilisateurs peuvent être invités à configurer des paramètres pour appliquer la protection des informations à des fichiers. Pour plus d’informations sur le Kit de développement logiciel (SDK), voir le [Kit de développement logiciel (SDK) Microsoft Rights Management](http://msdn.microsoft.com/library/hh552972%28v=vs.85%29.aspx).

De même, de nombreux éditeurs de logiciels proposent des applications pour fournir des solutions de protection des informations, également appelées produits de gestion des droits d’entreprise. Un lecteur PDF qui prend en charge [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)] pour des plateformes spécifiques en est un exemple type. Pour identifier les applications qui prennent en charge RMS, reportez-vous au tableau de la section [Fonctionnalités d’un appareil client](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_ClientCapabilities) de la rubrique [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md), puis effectuez une recherche sur le web pour acheter ou télécharger l’application.

> [!TIP]
> Pour obtenir les dernières versions des applications, consultez les canaux de la communauté RMS, répertoriés dans [Informations et support technique pour Azure Rights Management](../Topic/Information_and_Support_for_Azure_Rights_Management.md).

## Voir aussi
[Prise en main d'Azure Rights Management](../Topic/Getting_Started_with_Azure_Rights_Management.md)

