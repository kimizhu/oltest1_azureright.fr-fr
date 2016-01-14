---
description: na
keywords: na
title: Logging and Analyzing Azure Rights Management Usage
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a735f3f7-6eb2-4901-9084-8c3cd3a9087e
---
# Journalisation et analyse de l&#39;utilisation d&#39;Azure Rights Management
Les informations de cette rubrique aident à comprendre comment utiliser la journalisation de l’utilisation avec le service Gestion des droits Azure (Azure RMS). Le service Gestion des droits Azure peut journaliser chaque demande effectuée pour votre organisation, notamment les demandes provenant d’utilisateurs, les actions effectuées par les administrateurs Rights Management au sein de votre organisation, ainsi que les actions effectuées par les opérateurs Microsoft pour prendre en charge votre déploiement du service Gestion des droits Azure.

Vous pouvez ensuite utiliser les journaux de Gestion des droits Azure dans le cadre des scénarios d’entreprise suivants :

-   Analyse pour gagner en visibilité.

    Le service Gestion des droits Azure écrit des journaux au format de journal étendu W3C dans un compte de stockage Azure que vous spécifiez. Vous pouvez ensuite diriger ces journaux vers le référentiel de votre choix (par exemple, une base de données, un système de traitement analytique en ligne (OLAP) ou un système MapReduce) pour y analyser les informations et générer des rapports. Par exemple, vous pourriez identifier les personnes qui accèdent à vos données protégées par RMS, déterminer quelles sont les données protégées par RMS auxquelles accèdent les utilisateurs, à partir de quels appareils et à partir de quel emplacement, savoir si les utilisateurs parviennent à consulter du contenu protégé, ou encore identifier les personnes qui ont lu un document important qui était protégé.

-   Surveiller les abus.

    Les informations de journalisation de Gestion des droits Azure mises à votre disposition quasiment en temps réel vous permettent de surveiller en continu l’utilisation de la gestion des droits au sein de votre entreprise. 99,9 % des journaux sont disponibles dans un délai de 15 minutes suivant le début d’une action initiée par RMS.

    Par exemple, vous souhaiteriez peut-être recevoir une alerte en cas d’augmentation soudaine du nombre de personnes qui consultent des données protégées par RMS en dehors des heures de travail, ce qui pourrait signifier qu’un utilisateur malveillant recueille des informations pour les revendre à des concurrents, ou si un même utilisateur accède visiblement à des données à partir d’adresses IP différentes dans un court laps de temps, cela peut indiquer qu’un compte d’utilisateur a été compromis.

-   Effectuer un audit légal.

    En cas de fuite d’informations, vous devrez très certainement fournir une liste des personnes qui ont accédé récemment à des documents spécifiques ainsi que le type d’informations auxquelles a pu accéder un individu suspecté. Vous pouvez répondre à ces types de questions lorsque vous utilisez le service Gestion des droits Azure et la journalisation, car les personnes qui consultent du contenu protégé doivent toujours obtenir une licence Rights Management pour ouvrir des documents et des images protégés par le service Gestion des droits Azure, même si ces fichiers sont déplacés par message électronique ou s’ils sont copiés sur des lecteurs USB ou d’autres dispositifs de stockage. Cela signifie que vous pouvez utiliser les journaux de Gestion des droits Azure en tant que source d’informations fiable pour une analyse légale si vous protégez vos données à l’aide du service Gestion des droits Azure.

> [!NOTE]
> Si vous vous intéressez uniquement à la journalisation des tâches d’administration pour le service Gestion des droits Azure, et ne souhaitez pas suivre la manière dont les utilisateurs utilisent Rights Management, vous pouvez utiliser l’applet de commande Windows PowerShell [Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx) pour Gestion des droits Azure.
> 
> Vous pouvez également utiliser le portail Azure Classic pour obtenir des rapports détaillés sur l’**utilisation de RMS**, les **utilisateurs de RMS les plus actifs**, l’**utilisation d’appareils RMS** et l’**utilisation d’applications compatibles avec RMS**. Pour accéder à ces rapports à partir du portail Azure Classic, cliquez sur **Active Directory**, sélectionnez et ouvrez un annuaire, puis cliquez sur **RAPPORTS**,

Pour plus d’informations sur la journalisation de l’utilisation du service Gestion des droits Azure, voir les sections suivantes :

-   [Comment activer la journalisation de l’utilisation du service Gestion des droits Azure](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_EnableRMSLogging)

-   [Comment accéder aux journaux d’utilisation du service Gestion des droits Azure et les utiliser](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_AccesAndUseLogs)

-   [Comment gérer l’espace de stockage des journaux du service Gestion des droits Azure](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_ManageStorage)

-   [Comment déléguer l’accès à vos journaux d’utilisation du service Gestion des droits Azure](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Delegate)

-   [Comment interpréter vos journaux d’utilisation du service Gestion des droits Azure](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Interpret)

-   [Référence Windows PowerShell](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_PowerShell)

## <a name="BKMK_EnableRMSLogging"></a>Comment activer la journalisation de l’utilisation du service Gestion des droits Azure
La journalisation de l’utilisation du service Gestion des droits Azure est facultative. Par conséquent, si vous souhaitez l’utiliser, vous devez prendre des mesures spécifiques. L’utilisation de la journalisation de l’utilisation du service Gestion des droits Azure ne change en rien le fonctionnement de Rights Management. Par ailleurs, le processus de journalisation proprement dit est gratuit. Cependant, vous devez fournir un compte de stockage Azure pour les journaux et ce stockage est payant.

Avant de commencer, vous devez vous assurer que les conditions préalables suivantes sont réunies pour utiliser la journalisation de l’utilisation du service Gestion des droits Azure :

|Condition requise|Plus d’informations|
|---------------------|-----------------------|
|Abonnement informatique incluant le Gestion des droits Azure|Vous devez disposer d’un abonnement Microsoft Azure Rights Management géré par votre organisation. Les organisations utilisant RMS for Individuals ne peuvent pas utiliser la journalisation de l’utilisation du service Gestion des droits Azure.<br /><br />Si des personnes au sein de votre organisation utilisent RMS for Individuals, la journalisation de l’utilisation du service Gestion des droits Azure constitue une bonne raison de convertir votre abonnement RMS for Individuals en abonnement Microsoft Azure Rights Management.<br /><br />Pour plus d’informations sur les abonnements incluant Azure RMS, voir la section [Abonnements au cloud prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) de la rubrique [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md).<br /><br />Pour plus d’informations sur RMS for Individuals, voir [RMS for Individuals et Azure Rights Management](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md).|
|Abonnement Azure|Vous devez disposer d’un abonnement Azure et d’un espace de stockage suffisant sur Azure pour y stocker vos journaux de Gestion des droits Azure.|
|Windows PowerShell pour la Gestion des droits Azure|Si ce n’est déjà fait, téléchargez et installez le module Windows PowerShell pour Gestion des droits Azure. Vous allez utiliser les applets de commande Windows PowerShell pour configurer et gérer vos journaux d’utilisation de Gestion des droits Azure.<br /><br />Pour plus d’informations, voir [Installation de Windows PowerShell pour Azure Rights Management](../Topic/Installing_Windows_PowerShell_for_Azure_Rights_Management.md).|
Pour activer la journalisation de l’utilisation du service Gestion des droits Azure, suivez la procédure ci-dessous, qui décrit les étapes permettant de créer un compte de stockage Azure et de configurer Azure afin d’utiliser ce dernier pour le stockage de vos journaux Rights Management.

> [!NOTE]
> Cette procédure suppose que vous avez déjà un compte Azure. La journalisation de l’utilisation du service Gestion des droits Azure prend en charge les comptes individuels, mais il est recommandé d’utiliser des comptes professionnels ou scolaires. De plus, nous vous recommandons de créer un compte de stockage dédié à vos journaux Rights Management. Vous devez partager les clés d’accès de stockage avec le service Gestion des droits Azure, voir avec d’autres personnes appelées à utiliser les fichiers journaux.
> 
> Pour plus d’informations sur le stockage Azure, voir la [documentation Azure sur le stockage](http://azure.microsoft.com/documentation/services/storage/).

#### Comment créer votre compte de stockage et activer la journalisation de l’utilisation du service Gestion des droits Azure

1.  Connectez-vous au [portail Azure](https://portal.azure.com/).

2.  Dans le menu hub, sélectionnez **Nouveau** -&gt; **Données + stockage** -&gt; **Compte de stockage**.

    > [!TIP]
    > Si vous ne voyez pas cette option, vérifiez que vous avez un abonnement Azure en plus de votre abonnement à Rights Management.

3.  Conservez le modèle de déploiement par défaut, **Classique**, puis cliquez sur **Créer**.

    Spécifiez le nom de votre compte de stockage et, si nécessaire, modifiez les options sélectionnées pour les paramètres **Niveau de tarification**, **Groupe de ressources**, **Abonnement** et **Épingler au tableau de bord**. Cliquez ensuite sur **CRÉER**. Attendez l’achèvement de l’activité **Création du compte de stockage**.

4.  Cliquez sur le compte de stockage nouvellement créé, puis sur **Paramètres**.

5.  Dans le panneau **Paramètres** , cliquez sur l’icône **Clés**.

6.  Dans le panneau **Gérer les clés**, copiez la valeur de la **CLÉ D’ACCÈS PRIMAIRE**, puis fermez le panneau.

7.  Démarrez Windows PowerShell avec l’option **Exécuter en tant qu’administrateur**. Exécutez la commande [Connect-AadrmService](https://msdn.microsoft.com/library/azure/dn629415.aspx) pour vous connecter au service Gestion des droits Azure :

    ```
    Connect-AadrmService
    ```

8.  Utilisez la commande [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx) pour spécifier l’emplacement dans lequel vous souhaitez stocker vos journaux d’utilisation du service Gestion des droits Azure, en remplaçant *&lt;Access_Key&gt;* par la clé d’accès primaire que vous avez copiée à l’étape 6, et *&lt;StorageAccount&gt;* par le nom du compte de stockage que vous avez créé à l’étape 3 :

    ```
    $accesskey = convertto-securestring -asplaintext -force –string <Access_Key> Set-AadrmUsageLogStorageAccount -AccessKey $accesskey -StorageAccount <StorageAccount>
    ```

9. Utilisez la commande [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx) pour activer la journalisation de l’utilisation du service Gestion des droits Azure :

    ```
    Enable-AadrmUsageLogFeature
    ```
    Le message suivant doit s’afficher : **La fonctionnalité de journalisation de l’utilisation est activée pour le service Rights Management.**

À présent que la journalisation de l’utilisation est activée, le service Gestion des droits Azure commence à journaliser toutes les actions au sein de votre organisation, et enregistre ces informations dans votre compte de stockage. Les informations de journalisation antérieures à l’activation ne sont pas disponibles.

Pour plus d’informations sur la création des comptes de stockage, voir la section [Créez un compte de stockage](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) de la rubrique [À propos des comptes de stockage Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) dans la documentation Azure.

## <a name="BKMK_AccesAndUseLogs"></a>Comment accéder aux journaux d’utilisation du service Gestion des droits Azure et les utiliser
Le service Gestion des droits Azure écrit des journaux enregistrés dans votre compte de stockage Azure sous la forme d’une série d’objets blob. Chaque objet blob contient un ou plusieurs enregistrements journal au format W3C étendu. Les noms des objets blob sont des chiffres et sont classés dans leur ordre de création. La section [Comment interpréter vos journaux d’utilisation du service Gestion des droits Azure](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Interpret) (plus loin dans ce document) contient plus d’informations sur le contenu des journaux et leur création.

Les journaux peuvent mettre un certain temps à apparaître dans votre compte de stockage après une action de Gestion des droits Azure. La plupart des journaux apparaissent dans un délai de 15 minutes.

Le compte de stockage que vous avez créé pour vos journaux d’utilisation du service Gestion des droits Azure fonctionne comme une boîte aux lettres, et prend en charge la lecture directe à partir du compte de stockage. Toutefois, ce mode d’utilisation n’est pas optimal. Pour obtenir de meilleures performances et pour réduire les coûts, nous vous conseillons de télécharger les journaux vers un espace de stockage local (par exemple, un dossier local, une base de données ou un référentiel MapReduce).

Vous pouvez télécharger vos journaux d’utilisation de deux façons :

-   Utilisez l’applet de commande Windows PowerShell [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx).

    Il s’agit de la façon la plus simple d’accéder à vos journaux d’utilisation. Cette applet de commande télécharge les journaux sur votre ordinateur. Chaque objet blob est téléchargé sous forme de fichier vers un emplacement spécifié.

-   Utilisez le [Kit de développement (SDK) Azure Storage](http://www.windowsazure.com/en-us/develop/net/) pour écrire votre propre application personnalisée pour télécharger les journaux.

    Une application personnalisée offre peut-être plus de flexibilité que l’applet de commande Get-AadrmUsageLogs, par exemple, si vous souhaitez déléguer le téléchargement des journaux à une personne ou à un processus qui ne doit pas utiliser vos informations d’identification d’administration du service Gestion des droits Azure, ou si vous voulez interroger les journaux en temps réel pour surveiller les utilisations incorrectes.

#### Pour télécharger vos journaux d’utilisation à l’aide de PowerShell

-   Démarrez Windows PowerShell avec l’option **Exécuter en tant qu’administrateur**, puis exécutez **Get-AadrmUsageLog –Path &lt;location&gt;**. Par exemple, après la création d’un dossier nommé **logs** sur votre lecteur E :

    -   Pour télécharger tous les journaux disponibles dans votre dossier E:\logs : `Get-AadrmUsageLog -Path "e:\logs"`

    -   Pour télécharger une plage d’objets blob spécifique : `Get-AadrmUsageLog –Path "e:\logs" –FromCounter 1024 –ToCounter 2047`

‎Lorsque vous exécutez ces applets de commande, Windows PowerShell affiche le nom du dernier objet blob téléchargé. Vous pouvez attribuer ce nom à une variable, ce qui vous permet d’exécuter la commande Get-AadrmUsageLog en boucle ou dans le cadre d’un travail planifié. Ainsi, seuls les journaux incrémentiels seront téléchargés à chaque fois.

Par exemple :

**PS C:\&gt; $LastBlobName = Get-AadrmUsageLog –Path "e:\logs"**

**1527**

**PS C:\&gt; $LastBlobName**

**1527**

> [!TIP]
> Vous pouvez regrouper vos fichiers journaux téléchargés dans un format CSV à l’aide de l’[analyseur de journal de Microsoft](http://www.microsoft.com/download/details.aspx?id=24659) qui est un outil de conversion de formats de fichiers journaux connus. Vous pouvez également utiliser cet outil pour convertir des données dans le format SYSLOG, ou les importer dans une base de données. Après avoir installé l’outil, exécutez **LogParser.exe /?** pour obtenir de l’aide et des informations sur l’utilisation de cet outil. Par exemple, vous pouvez exécuter la commande suivante pour importer toutes les informations dans un fichier au format .log : **logparser –i:w3c –o:csv “SELECT &#42; INTO AllLogs.csv FROM &#42;.log”**

Vous pouvez interrompre et reprendre la journalisation de l’utilisation. Lorsque vous interrompez la journalisation, le service Gestion des droits Azure conserve les informations de votre compte de stockage afin que vous puissiez reprendre facilement la journalisation.

#### Pour interrompre et reprendre la journalisation de l’utilisation

-   Pour interrompre la journalisation, utilisez l’applet de commande suivante : [Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   Pour reprendre la journalisation, utilisez l’applet de commande suivante : [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   Pour vérifier l’état d’activation de la journalisation, utilisez l’applet de commande suivante : [Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

    La valeur **True** signifie que la journalisation de l’utilisation est activée pour le service Gestion des droits Azure, tandis que la valeur **False** indique que cette fonctionnalité est désactivée.

## <a name="BKMK_ManageStorage"></a>Comment gérer l’espace de stockage des journaux du service Gestion des droits Azure
Vous payez pour l’espace de stockage utilisé pour conserver vos journaux du service Gestion des droits Azure.

Le service Gestion des droits Azure n’effectue aucune gestion automatique de vos fichiers journaux d’utilisation. Sans action de votre part, ils seront conservés dans votre compte de stockage. Cependant, pour conserver de l’espace et réduire les coûts de stockage, vous souhaiterez peut-être les supprimer après les avoir téléchargés. Vous pouvez également sélectionner les fichiers à supprimer. Notez cependant que, le service Gestion des droits Azure n’utilisant pas ces fichiers journaux, il n’existe donc aucune restriction concernant le moment de leur suppression.

Le fichier que vous ne devez pas supprimer (ou modifier) est nommé **metadata** (et se situe dans le conteneur **rms-metadata**). Le service Gestion des droits Azure utilise cet objet blob pour effectuer le suivi du dernier numéro d’objet blob utilisé. Si ce fichier est supprimé, le service Gestion des droits Azure crée un conteneur pour les journaux, et commence la numérotation des objets blob à partir de 1. Tous les téléchargements ultérieurs à l’aide de l’applet de commande Get-AadrmUsageLog utiliseront également ce nouveau conteneur pour télécharger les fichiers journaux. Par conséquent, les journaux restant dans le conteneur d’origine sont conservés, mais ils sont orphelins. La seule façon de télécharger ces journaux orphelins est d’utiliser le Kit de développement logiciel (SDK) Azure Storage.

> [!TIP]
> Au lieu de gérer vous-même votre espace de stockage des journaux du service Gestion des droits Azure, vous pouvez déléguer cette fonction à une autre entreprise en partageant le nom et la clé d’accès de votre compte de stockage. Pour plus d’informations, voir la section [Comment déléguer l’accès à vos journaux d’utilisation du service Gestion des droits Azure](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_Delegate), plus loin dans cette rubrique.

Dans certains cas, vous souhaiterez peut-être régénérer vos clés d’accès de stockage. Par exemple :

-   Vous modifiez la société qui gère vos journaux d’utilisation du service Gestion des droits Azure.

-   et vous soupçonnez que votre clé d’accès de stockage a été compromise.

Si cette situation se produit, vous devrez alors utiliser la clé d’accès secondaire (en admettant que vous utilisiez auparavant votre clé d’accès primaire) pour assurer la continuité du service. Lorsque vous régénérez la clé d’accès que vous n’utilisiez pas auparavant, vous devez configurer le service Gestion des droits Azure de manière à utiliser la nouvelle clé. Pour régénérer la clé d’accès secondaire et configurer le service Gestion des droits Azure afin qu’il l’utilise, procédez comme suit :

#### Pour régénérer la clé d’accès secondaire

1.  Connectez-vous au [portail Azure](https://portal.azure.com/).

2.  Cliquez sur **Toutes les ressources**, puis recherchez votre stockage en tapant le nom du stockage dans la zone de texte...

3.  Sélectionnez votre stockage, puis cliquez sur **Paramètres**.

4.  Cliquez sur le l’icône **Clés**.

5.  Dans la section **Gérer les clés**, cliquez sur **Régénérer la clé secondaire**, cliquez sur Oui pour confirmer que vous souhaitez régénérer la clé d’accès secondaire, puis copiez la nouvelle clé d’accès secondaire dans le Presse-papiers.

    Ne fermez pas le portail Azure.

6.  Démarrez Windows PowerShell avec l’option **Exécuter en tant qu’administrateur**, puis utilisez l’applet de commande [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx) pour configurer le service Gestion des droits Azure de manière à ce qu’il utilise cette nouvelle clé d’accès, en remplaçant *&lt;StorageAccount&gt;* par le nom de votre compte de stockage, et *&lt;Access_Key&gt;* par la clé d’accès secondaire régénérée que vous venez de copier :

    ```
    Set-AadrmUsageLogStorageAccount -StorageAccount <StorageAccount>-AccessKey <Access_Key>
    ```
    > [!WARNING]
    > Bien que vous puissiez passer à un autre compte de stockage lorsque vous exécutez cette commande, cette action rend vos anciens journaux orphelins et inaccessibles à l’applet de commande Set-AadrmUsageLogStorageAccount ou à d’autres commandes et fonctions de gestion similaires.

7.  De retour sur le portail Azure, dans la section **Gérer les touches**, régénérez votre clé d’accès primaire.

Pour plus d’informations sur la gestion de vos clés d’accès de stockage, voir la section [Gérer vos clés d’accès de stockage](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) de la rubrique [À propos des comptes de stockage Azure](https://azure.microsoft.com/documentation/articles/storage-create-storage-account/) dans la documentation Azure.

## <a name="BKMK_Delegate"></a>Comment déléguer l’accès à vos journaux d’utilisation du service Gestion des droits Azure
Vous pouvez déléguer l’accès à vos journaux RMS en partageant le nom et la clé d’accès de votre compte de stockage. Vous souhaitez peut-être déléguer l’accès à un autre utilisateur administratif, à un développeur de votre organisation ou à un éditeur de logiciels indépendant (ISV). Étant donné qu’ils ne disposent pas de vos informations d’identification d’administrateur RMS, ils ne peuvent pas utiliser l’applet de commande Get-AardrmUsageLog pour télécharger les journaux RMS. Au lieu de cela, ils doivent utiliser le Kit de développement logiciel (SDK) Windows Storage pour les télécharger. Ils peuvent également écrire une application permettant de lire les journaux directement à partir d’Azure Storage.

Vous pouvez partager la clé d’accès et le nom du compte de stockage en toute sécurité lorsque le compte de stockage est dédié à vos journaux RMS. Même si d’autres personnes possèdent la clé d’accès, ils ne pourront pas l’utiliser pour accéder à d’autres comptes de stockage ou utiliser le compte de votre client RMS.

## <a name="BKMK_Interpret"></a>Comment interpréter vos journaux d’utilisation du service Gestion des droits Azure
Pour interpréter les journaux d’utilisation du service Gestion des droits Azure, utilisez les informations suivantes.

### Structure du compte de stockage
La première fois que le service Gestion des droits Azure écrit des journaux dans votre compte de stockage, il crée les deux conteneurs suivants :

-   **Rms-metadata** : Ce conteneur est réservé au service Gestion des droits Azure. Ne modifiez pas ou ne supprimez pas ce conteneur.

-   **Rms-logs-&lt;guid&gt;**: Ce conteneur est l’emplacement dans lequel le service Gestion des droits Azure crée et conserve les journaux. Vous pouvez supprimer les fichiers de ce conteneur en toute sécurité si vous n’avez plus besoin des informations de journalisation qu’il contient.

Au fil du temps, le service Gestion des droits Azure peut créer des conteneurs **Rms-logs-&lt;guid&gt;** supplémentaires. Par exemple, si le conteneur **Rms-metadata** est endommagé ou supprimé accidentellement, le service Gestion des droits Azure réinitialise son contenu et crée un conteneur **Rms-logs-&lt;guid&gt;** pour les journaux à venir. Les anciens journaux de l’ancien conteneur ne sont pas supprimés, mais ils deviennent orphelins.

### Séquence du journal
Le service Gestion des droits Azure écrit les journaux sous forme de série d’objets blob. Chaque objet blob contient un ou plusieurs enregistrements journal au format W3C étendu.

Le nom de chaque objet blob est un numéro. Dans chaque conteneur de journal, le premier objet blob est nommé 000000001. Chaque objet blob est nommé de façon séquentielle dans l’ordre de sa création. Chaque objet blob contient un ou plusieurs enregistrements de journal. Chaque enregistrement de journal comprend un horodatage au format UTC, qui indique l’heure de traitement de la demande correspondante par le service Gestion des droits Azure.

> [!IMPORTANT]
> Le système de journalisation du service Gestion des droits Azure est optimisé de manière à vous fournir les journaux rapidement, plutôt que dans un ordre séquentiel strict. L’ordre des objets blob, ainsi que l’ordre des enregistrements de journal d’un objet blob, n’est peut-être pas chronologique. Les objets blob sont nommés de manière séquentielle pour vous permettre de les télécharger de façon incrémentielle.
> 
> Voici deux exemples de résultats potentiels de séquence de journal :
> 
> -   Les enregistrements de journal dans l’objet blob 000000004 peuvent chevaucher chronologiquement les enregistrements de journal dans l’objet blob 000000003. Dans des cas extrêmes, il peut arriver que tous les enregistrements de journal dans l’objet blob 000000004 aient été générés avant tous les enregistrements de journal dans l’objet blob 000000003.
> -   Le deuxième enregistrement de journal d’un objet blob peut avoir été généré avant le premier enregistrement de journal, mais il a peut-être été écrit dans l’espace de stockage après le premier enregistrement.

Avant d’analyser vos journaux d’utilisation du service Gestion des droits Azure, nous vous conseillons de télécharger et d’importer le journal dans un référentiel où vous pouvez trier les journaux sur la base de leur horodatage. Pour plus d’informations sur le téléchargement des journaux, voir la section [Comment accéder aux journaux d’utilisation du service Gestion des droits Azure et les utiliser](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md#BKMK_AccesAndUseLogs) de cette rubrique.

Étant donné que les journaux ne sont pas forcément classés par ordre chronologique, mais que la majorité d’entre eux sont écrits dans un délai de 15 minutes suivant la requête, nous vous conseillons d’ajouter 15 minutes à l’heure qui vous intéresse lorsque vous identifiez les journaux souhaités à l’aide de l’horodatage. Téléchargez ensuite ces journaux. Cette méthode vous permettra de récupérer pratiquement tous les journaux.

Notez également que l’horodatage de chaque enregistrements de journal indique l’heure locale du service Gestion des droits Azure qui a traité la demande. Étant donné que le service Gestion des droits Azure est exécuté sur plusieurs serveurs répartis dans plusieurs centres de données, la séquence des journaux peut parfois sembler incohérente, même si ces derniers sont classés en fonction de leur horodatage. Toutefois, la différence est mineure et souvent inférieure à une minute. Dans la plupart des cas, cela ne risque pas de poser de problème lors de l’analyse des journaux.

### Format des objets blob
Chaque objet blob est au format de journal W3C étendu. Il commence par les deux lignes suivantes :

**#Software: RMS**

**#Version: 1.1**

La première ligne indique qu’il s’agit de journaux du service Gestion des droits Azure. La deuxième indique que le reste de l’objet blob suit les spécifications de la version 1.1. À titre de recommandation, les applications qui analysent ces journaux doivent vérifier ces deux lignes avant de continuer l’analyse du reste de l’objet blob.

La troisième ligne énumère une liste de noms de champs séparés par des tabulations :

**#Fields: date            time            row-id        request-type           user-id       result          correlation-id          content-id                owner-email           issuer                     template-id             file-name                  date-published      c-info         c-ip**

Chacune des lignes suivantes est un enregistrement de journal. Les valeurs des champs sont dans le même ordre que celui de la ligne précédente et sont séparées par des tabulations. Utilisez le tableau suivant pour interpréter les champs.

|Nom du champ|Type de données W3C|Description|Exemple de valeur|
|----------------|-----------------------|---------------|---------------------|
|date|Date|Date UTC du traitement de la demande.<br /><br />La source est l’horloge locale du serveur qui a traité la demande.|25-06-2013|
|heure|Heure|Heure UTC (au format 24 h) du traitement de la demande.<br /><br />La source est l’horloge locale du serveur qui a traité la demande.|21:59:28|
|row-id|Text|GUID unique de cet enregistrement de journal.<br /><br />Cette valeur est utile lorsque vous agrégez des journaux ou lorsque vous copiez des journaux dans un autre format.|1c3fe7a9-d9e0-4654-97b7-14fafa72ea63|
|request-type|Nom|Nom de l’API RMS demandée.|AcquireLicense|
|user-id|Chaîne|Utilisateur ayant adressé la demande.<br /><br />La valeur est placée entre guillemets simples. Certains types de demande sont anonymes, auquel cas la valeur est :|« joe@contoso.com »|
|result|Chaîne|« Success » si la demande a été traitée correctement.<br /><br />Type d’erreur (entre guillemets simples) si la demande échoue.|« Success »|
|correlation-id|Text|GUID commun au journal du client RMS et au journal du serveur pour une demande donnée.<br /><br />Cette valeur peut être utile pour résoudre les problèmes liés au client.|cab52088-8925-4371-be34-4b71a3112356|
|content-id|Text|GUID (entre accolades) qui identifie le contenu protégé (par exemple, un document).<br /><br />Ce champ contient une valeur uniquement si le champ request-type est égal à AcquireLicense. Sinon, il reste vierge pour les autres types de demande.|{bb4af47b-cfed-4719-831d-71b98191a4f2}|
|owner-email|Chaîne|Adresse de messagerie du propriétaire du document.|alice@contoso.com|
|issuer|Chaîne|Adresse de messagerie de l’émetteur du document.|alice@contoso.com (ou) FederatedEmail.4c1f4d-93bf-00a95fa1e042@contoso.onmicrosoft.com’|
|Template-id|Chaîne|ID du modèle utilisé pour protéger le document.|{6d9371a6-4e2d-4e97-9a38-202233fed26e}|
|File-name|Chaîne|Nom de fichier du document qui a été protégé.|TopSecretDocument.docx|
|Date-published|Date|Date à laquelle le document a été protégé.|2015-10-15T21:37:00|
|c-info|Chaîne|Informations concernant la plateforme du client d’où émane la demande.<br /><br />La chaîne spécifique varie selon l’application (par exemple, le système d’exploitation ou le navigateur).|’MSIPC;version=1.0.623.47;AppName=WINWORD.EXE;AppVersion=15.0.4753.1000;AppArch=x86;OSName=Windows;OSVersion=6.1.7601;OSArch=amd64’|
|c-ip|Adresse|Adresse IP du client d’où émane la demande.|64.51.202.144|

#### Exceptions pour le champ user-id.
Bien que le champ user-id indique généralement l’utilisateur qui effectue la demande, il existe deux exceptions pour lesquelles la valeur ne mappe pas à un utilisateur réel :

-   Valeur **'microsoftrmsonline@&lt;YourTenantID&gt;.rms.&lt;region&gt;.aadrm.com'**.

    Cette valeur indique qu’un service Office 365, tel qu’Exchange Online ou SharePoint Online, est à l’origine de la demande. Dans la chaîne, *&lt;YourTenantID&gt;* représente le GUID de votre client et *&lt;region&gt;* correspond à la région dans laquelle votre client est inscrit. Par exemple,**AN** représente l’Amérique du Nord, **UE** correspond à l’Europe et **AP** correspond à l’Asie.

-   Si vous utilisez le connecteur RMS :

    Les demandes émises par ce connecteur sont journalisées avec le nom de principal du service que le service RMS génère automatiquement lors de l’installation du connecteur RMS.

#### Types de demande standard
Il existe de nombreux types de demande dans le service Gestion des droits Azure. Le tableau suivant répertorie quelques-uns des types de demandes les plus utilisés.

|Type de demande|Description|
|-------------------|---------------|
|AcquireLicense|Un client sur une machine Windows demande une licence pour du contenu protégé par RMS.|
|AcquirePreLicense|Un client demande, au nom de l’utilisateur, une licence pour du contenu protégé par RMS.|
|AcquireTemplates|Un appel a été fait pour acquérir des modèles basés sur des ID de modèle.|
|AcquireTemplateInformation|Un appel a été fait pour obtenir les ID du modèle à partir du service.|
|AddTemplate|Un appel est fait à partir du portail Azure Classic pour ajouter un modèle.|
|BECreateEndUserLicenseV1|Un appel est fait à partir d’un appareil mobile pour créer une licence utilisateur final.|
|BEGetAllTemplatesV1|Un appel est fait à partir d’un appareil mobile (principal) pour obtenir tous les modèles.|
|Certify|Le client certifie le contenu pour la protection.|
|Decrypt|Le client tente de déchiffrer le contenu protégé par RMS.|
|DeleteTemplateById|Un appel est fait à partir du portail Azure Classic pour supprimer un modèle sur la base de son ID.|
|ExportTemplateById|Un appel est fait à partir du portail Azure Classic pour exporter un modèle sur la base de son ID.|
|FECreateEndUserLicenseV1|Similaire à la demande AcquireLicense, mais à partir d’un appareil mobile.|
|FECreatePublishingLicenseV1|Identique à Certify et GetClientLicensorCert combinés, mais à partir de clients mobiles.|
|FEGetAllTemplates|Un appel est fait à partir d’un appareil mobile (frontal) pour obtenir les modèles.|
|GetAllTemplates|Un appel est fait à partir du portail Azure Classic pour obtenir tous les modèles.|
|GetClientLicensorCert|Le client demande un certificat de publication (qui sera ensuite utilisé pour protéger du contenu) à partir d’un ordinateur Windows.|
|GetConfiguration|Une applet de commande Azure PowerShell est appelée pour obtenir la configuration du client Azure RMS.|
|GetConnectorAuthorizations|Un appel est fait via les connecteurs RMS pour obtenir leur configuration à partir du cloud.|
|GetTenantFunctionalState|Le portail Azure Classic vérifie si Azure RMS est activé.|
|GetTemplateById|Un appel est fait à partir du portail Azure Classic pour obtenir un modèle sur la base de son ID.|
|ExportTemplateById|Un appel est fait à partir du portail Azure Classic pour exporter un modèle sur la base de son ID.|
|FindServiceLocationsForUser|Un appel est fait pour rechercher des URL utilisées pour appeler Certify ou AcquireLicense.|
|ImportTemplate|Un appel est fait à partir du portail Azure Classic pour importer un modèle.|
|ServerCertify|Un appel est fait à partir d’un client RMS (par exemple, SharePoint) pour certifier le serveur.|
|SetUsageLogFeatureState|Un appel est fait pour activer la journalisation de l’utilisation.|
|SetUsageLogStorageAccount|Un appel est fait pour spécifier l’emplacement des journaux Azure RMS.|
|SignDigest|Un appel est fait quand une clé est utilisée à des fins de signature. Cet appel est généralement fait une fois par demande AcquireLicense (ou FECreateEndUserLicenseV1), Certify et GetClientLicensorCert (ou FECreatePublishingLicenseV1).|
|UpdateTemplate|Un appel est fait à partir du portail Azure Classic pour mettre à jour un modèle existant.|

## <a name="BKMK_PowerShell"></a>Référence Windows PowerShell
Les applets de commande Windows PowerShell suivantes permettent de configurer et d’utiliser la journalisation de l’utilisation du service Gestion des droits Azure :

-   [Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx)

-   [Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

-   [Get-AadrmUsageLogLastCounterValue](https://msdn.microsoft.com/library/azure/dn629423.aspx)

-   [Get-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629419.aspx)

-   [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx)

Pour plus d’informations sur l’utilisation de Windows PowerShell pour le service Gestion des droits Azure, voir [Administration de la Gestion des droits Azure à l'aide de Windows PowerShell](../Topic/Administering_Azure_Rights_Management_by_Using_Windows_PowerShell.md).

## Voir aussi
[Utilisation d'Azure Rights Management](../Topic/Using_Azure_Rights_Management.md)

