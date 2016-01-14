---
description: na
keywords: na
title: Active Directory Rights Management Services Mobile Device Extension
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.assetid: a69ead9d-7dd3-4b38-9830-4728e9757341
robots: noindex,nofollow
---
# Extension Appareils mobiles AD&#160;RMS (Active Directory Rights Management Services)
L'extension Appareils mobiles AD RMS (Active Directory Rights Management Services) s'exécute sur un déploiement AD RMS existant. Elle permet aux utilisateurs qui possèdent des appareils mobiles de protéger et de consommer des données sensibles quand leur appareil prend en charge la dernière version du client RMS et utilise des applications qui présentent un état d'éveil à la présence d'un environnement virtualisé pour RMS. Les utilisateurs de ces appareils peuvent, par exemple, effectuer les opérations suivantes :

-   utiliser l'application de partage RMS pour consommer des fichiers texte protégés sous différents formats (y compris .xml, .txt et .csv) ;

-   utiliser l'application de partage RMS pour consommer des fichiers image protégés (y compris .jpg, .gif, et .tif) ;

-   utiliser l'application de partage RMS pour ouvrir les fichiers qui ont été protégés de façon générique (format .pfile) ;

-   utiliser l'application de partage RMS pour protéger les fichiers image sur l'appareil ;

-   utiliser une visionneuse PDF présentant un état d'éveil à la présence d'un environnement virtualisé pour RMS pour les appareils mobiles afin d'ouvrir les fichiers PDF protégés avec l'application de partage RMS pour Windows, ou une autre application présentant cet état ;

-   utiliser d'autres applications d'éditeurs de logiciels qui fournissent des applications présentant un état d'éveil à la présence d'un environnement virtualisé pour RMS et prenant en charge les types de fichiers qui prennent en charge RMS en mode natif ;

-   utiliser les applications présentant un état d'éveil à la présence d'un environnement virtualisé pour RMS développées en interne et écrites à l'aide du Kit de développement logiciel (SDK) RMS.

> [!NOTE]
> Vous pouvez télécharger l'application de partage RMS à partir de la page [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) sur le site web Microsoft.
> 
> Pour plus d'informations sur les différents types de fichiers pris en charge par RMS, consultez la section [Types de fichiers pris en charge et extensions de nom de fichier](http://technet.microsoft.com/library/dn339003.aspx) dans le guide de l'administrateur de l'application de partage Rights Management.

Vous n'avez pas besoin de l'extension Appareils mobiles pour recevoir ou créer des messages électroniques protégés sur les appareils s'ils utilisent des applications de messagerie qui prennent en charge la Gestion des droits relatifs à l'information (IRM) Exchange ActiveSync. Cette prise en charge native pour RMS et les appareils mobiles a été introduite avec Exchange 2010 Service Pack 1.

Utilisez les sections suivantes pour déployer l'extension Appareils mobiles AD RMS (Active Directory Rights Management Services) :

-   [Configuration requise pour l'extension Appareils mobiles AD RMS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_Preqs)

    -   [Configuration des services AD FS pour l'extension Appareils mobiles AD RMS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS)

    -   [Configuration des services AD FS pour l'extension Appareils mobiles AD RMS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS)

-   [Spécification des enregistrements SRV DNS pour l'extension Appareils mobiles AD RMS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_SRV)

-   [Déploiement de l'extension Appareils mobiles AD RMS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_Deploy)

## <a name="BKMK_Preqs"></a>Configuration requise pour l'extension Appareils mobiles AD RMS
Avant d'installer l'extension Appareils mobiles AD RMS, assurez-vous que ces dépendances sont en place.

|Situation|Autres informations|
|-------------|-----------------------|
|Un déploiement AD RMS existant sur Windows Server 2012 R2 ou Windows Server 2012. **Note:** Les services AD RMS doivent utiliser une base de données complète basée sur Microsoft SQL Server sur un serveur distinct et non la base de données interne Windows qui est souvent utilisée pour le test sur le même serveur.|Pour obtenir une documentation sur AD RMS, consultez [Active Directory Rights Management Services](http://technet.microsoft.com/library/hh831364.aspx) dans la bibliothèque Windows Server.|
|Services AD FS déployés sur Windows Server 2012 R2|Pour obtenir une documentation sur AD FS, consultez [Guide de déploiement des services AD FS Windows Server 2012 R2](http://technet.microsoft.com/library/dn486820.aspx) dans la bibliothèque Windows Server.<br /><br />Les services AD FS doivent être configurés pour l'extension Appareils mobiles. Pour obtenir des instructions, consultez la section [Configuration des services AD FS pour l'extension Appareils mobiles AD RMS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_ADFS) dans cette rubrique.|
|Enregistrements SRV dans DNS|Créez un ou plusieurs enregistrements SRV dans le ou les domaines de votre entreprise :<br /><br />-   Un enregistrement pour chaque suffixe de domaine de messagerie employé par les utilisateurs<br />-   Un enregistrement pour chaque nom de domaine complet (FQDN) utilisé par les clusters RMS pour protéger le contenu<br /><br />Quand les utilisateurs fournissent leur adresse de messagerie à partir de leur appareil mobile, le suffixe de domaine est utilisé pour déterminer s'ils doivent utiliser une infrastructure AD RMS ou Azure RMS. Quand l'enregistrement SRV est trouvé, les clients sont redirigés vers le serveur AD RMS qui répond à cette URL.<br /><br />Quand les utilisateurs consomment du contenu protégé avec un appareil mobile, l'application cliente recherche dans DNS un enregistrement qui correspond au nom de domaine complet dans l'URL du cluster qui a protégé le contenu. L'appareil est ensuite dirigé vers le cluster AD RMS spécifié dans l'enregistrement DNS et obtient une licence pour ouvrir le contenu. Dans la plupart des cas, le cluster RMS sera le même cluster RMS qui a protégé le contenu.<br /><br />Pour plus d'informations sur la façon de spécifier les enregistrements SRV, consultez la section [Spécification des enregistrements SRV DNS pour l'extension Appareils mobiles AD RMS](../Topic/Active_Directory_Rights_Management_Services_Mobile_Device_Extension.md#BKMK_SRV) dans cette rubrique.|
|Clients actuellement pris en charge :<br /><br />-   Appareils Android utilisant la dernière version de l'application de partage RMS pour Android|Version minimale d'Android 4.0.3.<br /><br />Téléchargez l'application de partage RMS pour Android à partir du [site Microsoft Connect](https://connect.microsoft.com/site1170/Downloads) et chargez-en une version de test dans l'appareil.|

### <a name="BKMK_ADFS"></a>Configuration des services AD FS pour l'extension Appareils mobiles AD RMS
Vous devez tout d'abord configurer les services AD FS, puis autoriser l'application de partage RMS pour Android.

##### Étape 1 : Pour configurer les services AD FS

-   Vous pouvez exécuter un script Windows PowerShell pour configurer automatiquement les services AD FS pour prendre en charge l'extension Appareils mobiles AD RMS, ou vous pouvez spécifier manuellement les valeurs et options de configuration :

    -   Pour configurer automatiquement les services AD FS, copiez et collez ce qui suit dans un fichier de script Windows PowerShell, puis exécutez-le :

        ```
        # This Script Configures the Microsoft Rights Management Mobile Device Extension and Claims used in the ADFS Server

        # Check if Microsoft Rights Management Mobile Device Extension is configured on the Server 
        $CheckifConfigured = Get-AdfsRelyingPartyTrust -Identifier "api.rms.rest.com"
        if ($CheckifConfigured)
        {
        Write-Host "api.rms.rest.com Identifer used for Microsoft Rights Management Mobile Device Extension is already configured on this Server"
        Write-Host $CheckifConfigured 
        }
        else
        {
        Write-Host "Configuring  Microsoft Rights Management Mobile Device Extension "

        # TransformaRules used by Microsoft Rights Management Mobile Device Extension
        # Claims: E-mail, UPN and ProxyAddresses
        $TransformRules = @"
        @RuleTemplate = "LdapClaims"
        @RuleName = "Jwt Token"
        c:[Type ==
        "http://schemas.microsoft.com/ws/2008/06/identity/claims/windowsaccountname",
        Issuer == "AD AUTHORITY"]
         => issue(store = "Active Directory", types =
        ("http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress",
        "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn",
        "http://schemas.xmlsoap.org/claims/ProxyAddresses"), query =
        ";mail,userPrincipalName,proxyAddresses;{0}", param = c.Value);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through"
        c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/emailaddress"]
         => issue(claim = c);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through"
        c:[Type == "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/upn"]
         => issue(claim = c);

        @RuleTemplate = "PassThroughClaims"
        @RuleName = "JWT pass through Proxy addresses"
        c:[Type == "http://schemas.xmlsoap.org/claims/ProxyAddresses"]
         => issue(claim = c);
        "@

        # AuthorizationRules used by Microsoft Rights Management Mobile Device Extension
        # Allow All users
        $AuthorizationRules = @"
        @RuleTemplate = "AllowAllAuthzRule"
         => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit",
        Value = "true");
        "@

        # Add a Relying Part Truest with Name -"Microsoft Rights Management Mobile Device Extension" Identifier "api.rms.rest.com"
        Add-ADFSRelyingPartyTrust -Name "Microsoft Rights Management Mobile Device Extension" -Identifier "api.rms.rest.com" -IssuanceTransformRules $TransformRules -IssuanceAuthorizationRules  $AuthorizationRules

        Write-Host "Microsoft Rights Management Mobile Device Extension Configured"
        }
        ```

    -   Pour configurer manuellement les services AD FS, utilisez les paramètres suivants :

        |Configuration|Valeur|
        |-----------------|----------|
        |**Approbation de la partie de confiance**|api.rms.rest.com|
        |**Règle de revendication**|**Magasin d'attributs** :  Active Directory<br /><br />**Adresses de messagerie** :  Adresse de messagerie<br /><br />**User-Principal-Name** :  UPN<br /><br />**Proxy-Address** :  https://schemas.xmlsoap.org/claims/ProxyAddresses|

##### Étape 2 : Autoriser l'application de partage RMS pour Android

-   Exécutez la commande Windows PowerShell suivante pour ajouter la prise en charge pour les appareils Android :

    ```
    Add-AdfsClient -Name "RMSsharingAndroid" -ClientId "com.microsoft.ipviewer" -RedirectUri @("com.microsoft.ipviewer://authorize")
    ```

### <a name="BKMK_SRV"></a>Spécification des enregistrements SRV DNS pour l'extension Appareils mobiles AD RMS
Vous devez créer des enregistrements SRV DNS pour chaque domaine de messagerie employé par les utilisateurs. Si tous vos utilisateurs emploient des domaines enfants depuis un domaine parent unique et que tous les utilisateurs de cet espace de noms contigu emploient le même cluster RMS, vous pouvez utiliser un seul enregistrement SRV dans le domaine parent et RMS trouvera les enregistrements DNS appropriés.

Les enregistrements SRV ont le format suivant : _rmsdisco._http._tcp. *&lt;suffixe_messagerie&gt;**&lt;numéro_port&gt;**&lt;FQDN_cluster_RMS&gt;*

Par exemple, si votre organisation a des utilisateurs avec les adresses de messagerie suivantes :

-   utilisateur@contoso.com

-   utilisateur@sales.contoso.com

-   utilisateur@fabrikam.com

et qu'aucun autre domaine enfant pour contoso.com n'utilise un cluster RMS différent de celui qui porte le nom **rmsserver.contoso.com**, créez deux enregistrements SRV DNS qui ont les valeurs suivantes :

-   _rmsdisco._http._tcp.contoso.com 443 rmsserver.contoso.com

-   _rmsdisco._http._tcp.fabrikam.com 443 rmsserver.contoso.com

En plus de ces enregistrements SRV DNS pour vos domaines de messagerie, vous devez créer un autre enregistrement SRV DNS dans les domaines d'utilisateurs. Cet enregistrement doit spécifier les URL de votre cluster RMS qui protège le contenu. Chaque fichier qui est protégé par RMS inclut une URL vers le cluster qui a protégé ce fichier. Les appareils mobiles utilisent l'enregistrement SRV DNS et le nom de domaine complet de l'URL spécifié dans l'enregistrement pour trouver le cluster RMS correspondant qui peut prendre en charge des appareils mobiles.

Par exemple, si votre cluster RMS est **rmsserver.contoso.com**, créez un enregistrement SRV DNS qui a les valeurs suivantes : **_rmsdisco._http._tcp.rmsserver.contoso.com 443 rmsserver.contoso.com**

## <a name="BKMK_Deploy"></a>Déploiement de l'extension Appareils mobiles AD RMS
Avant d'installer l'extension Appareils mobiles AD RMS, assurez-vous que les composants requis de la section précédente sont bien en place et que vous connaissez l'URL de votre serveur AD FS. Procédez ensuite comme suit :

1.  Téléchargez l'extension Appareils mobiles AD RMS à partir du [site Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=397245).

2.  Exécutez Setup.exe pour démarrer l'Assistant Installation de l'extension Appareils mobiles AD RMS (Active Directory Rights Management Services).

3.  Quand vous y êtes invité, entrez l'URL du serveur AD FS que vous avez configuré précédemment.

4.  Suivez toutes les étapes de l'Assistant.

Exécutez cet Assistant sur tous les nœuds de votre cluster RMS.

