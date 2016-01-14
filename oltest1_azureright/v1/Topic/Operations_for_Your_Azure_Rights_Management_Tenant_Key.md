---
description: na
keywords: na
title: Operations for Your Azure Rights Management Tenant Key
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1284d0ee-0a72-45ba-a64c-3dcb25846c3d
---
# Op&#233;rations pour votre cl&#233; de client Azure Rights Management
Selon la typologie de votre clé de locataire (gérée par Microsoft ou par le client), différents niveaux de contrôle et de responsabilité sont disponibles pour votre clé de locataire Microsoft Azure Rights Management (Azure RMS) après l'implémentation de celle-ci.

La gestion de votre propre clé de locataire est souvent appelée BYOK (Bring Your Own Key). Pour plus d'informations sur ce scénario et découvrir comment choisir entre les deux typologies de clé de locataire, consultez [Planification et implémentation de la clé de locataire Azure Rights Management](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md).

Le tableau suivant présente les opérations que vous pouvez faire, selon la typologie que vous avez choisie pour votre clé de locataire Azure.

|Opération de cycle de vie|Gérée par Microsoft (par défaut)|Gérée par le client (BYOK)|
|-----------------------------|------------------------------------|------------------------------|
|Révocation de votre clé de locataire|Non (automatique)|Non (automatique)|
|Renouvellement de votre clé de locataire|Oui|Oui|
|Sauvegarde et récupération de votre clé de locataire|Non|Oui|
|Exportation de votre clé de locataire|Oui|Non|
|Réponse à une violation|Oui|Oui|
Après avoir identifié la typologie implémentée, utilisez l'une des sections suivantes pour obtenir plus d'informations sur ces opérations pour votre clé de locataire Azure RMS.

## <a name="BKMK_MSManagedOperations"></a>Géré par Microsoft : opérations de cycle de vie de la clé de locataire
Si Microsoft gère votre clé de locataire pour Azure Rights Management (par défaut), utilisez les sections suivantes pour obtenir plus d'informations sur les opérations de cycle de vie qui s'appliquent à cette topologie :

-   [Révocation de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRevoke)

-   [Renouvellement de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRekey)

-   [Sauvegarde et récupération de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSBackup)

-   [Exportation de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSExport)

-   [Réponse à une violation](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSBreach)

### <a name="BKMK_MSRevoke"></a>Révocation de votre clé de locataire
Lorsque vous annulez votre abonnement aux services Azure RMS, ces derniers arrêtent d'utiliser votre clé de locataire et aucune autre action n'est requise de votre part.

### <a name="BKMK_MSRekey"></a>Renouvellement de votre clé de locataire
Le renouvellement de la clé est également appelé déploiement de la clé. Ne renouvelez pas votre clé de locataire à moins que ce soit vraiment nécessaire. Les clients plus anciens, tels qu'Office 2010, n'ont pas été conçu pour gérer naturellement les changements de clés. Dans ce scénario, vous devez effacer l'état RMS des ordinateurs à l'aide d'une stratégie de groupe ou d'un mécanisme similaire. Toutefois, certains événements légitimes peuvent vous obliger à renouveler votre clé de locataire. Par exemple :

-   Votre entreprise s'est divisée en deux sociétés distinctes ou plus. Lorsque vous renouvelez votre clé de locataire, la nouvelle société n'aura pas accès au nouveau contenu publié par vos employés. Elle pourra toujours accéder à l'ancien contenu si elle dispose d'une copie de l'ancienne clé de locataire.

-   Vous pensez que la copie principale de votre clé de locataire (celle en votre possession) a été compromise.

Vous pouvez renouveler votre clé de locataire en appelant les services de support technique Microsoft (CSS), et en prouvant que vous êtes bien l'administrateur client.

Lorsque vous renouvelez votre clé de locataire, le nouveau contenu est protégé à l'aide de la nouvelle clé de locataire. Vous obtenez ce résultat en plusieurs étapes. Ainsi, pendant un certain temps, certains nouveaux contenus continueront d'être protégés par l'ancienne clé de locataire. Le contenu précédemment protégé reste protégé par l'ancienne clé de locataire. Pour prendre en charge ce scénario, les services Azure RMS conservent votre ancienne clé de locataire afin qu'ils puissent émettre des licences pour l'ancien contenu.

### <a name="BKMK_MSBackup"></a>Sauvegarde et récupération de votre clé de locataire
Microsoft se charge de sauvegarder votre clé de locataire. Aucune action n'est requise de votre part.

### <a name="BKMK_MSExport"></a>Exportation de votre clé de locataire
Vous pouvez exporter votre clé de locataire et votre configuration Azure RMS en suivant les instructions contenues dans ces trois étapes :

##### Étape 1 : initiation d'une exportation

-   Pour ce faire, contactez le support technique Microsoft. Vous devez prouver que vous êtes un administrateur de votre client Azure RMS.

##### Étape 2 : attente de la vérification

-   Microsoft vérifie la légitimité de votre demande d'émission de votre clé de locataire RMS. Cela peut prendre jusqu'à 3 semaines.

##### Étape 3 : réception d'instructions concernant la clé de la part du support technique

-   Le support technique de Microsoft vous enverra votre clé de locataire et votre configuration Azure RMS sous forme chiffrée dans un fichier .tpd protégé par mot de passe. Pour ce faire, le support technique vous envoie (vous, la personne ayant demandé un export) tout d'abord un outil par message électronique. Vous devez exécuter cet outil à partir d'une invite de commande, comme suit :

    ```
    AadrmTpd.exe -createkey
    ```
    Cette opération génère une paire de clés RSA et enregistre les moitiés publique et privée sous forme de fichiers dans le dossier actuel. Par exemple, **PublicKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt** et **PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt**.

    Répondez au message électronique que vous a reçu du support technique en y joignant le fichier dont le nom commence par **PublicKey**. Le support technique vous enverra ensuite un fichier de domaine de publication approuvé (TPD) au format .xml, chiffré à l'aide de votre clé RSA. Copiez ce fichier dans le dossier dans lequel vous avez initialement exécuté l'outil AadrmTpd, puis réexécutez l'outil à l'aide de votre fichier dont le nom commence par **PrivateKey** et du fichier reçu du support technique. Par exemple :

    ```
    AadrmTpd.exe -key PrivateKey-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt -target TPD-77172C7B-8E21-48B7-9854-7A4CEAC474D0.xml
    ```
    Cette commande doit générer deux fichiers : l'un contient le mot de passe en clair pour le TPD protégé par mot de passe, tandis que l'autre contient le TPD protégé par mot de passe en question. À des fins de références croisées, les deux fichiers doivent avoir le même GUID que les fichiers de clés publique et privée utilisés lors de l'exécution de la commande AadrmTpd.exe -createkey :

    -   Password-FA29D0FE-5049-4C8E-931B-96C6152B0441.txt

    -   ExportedTPD-FA29D0FE-5049-4C8E-931B-96C6152B0441.xml

    Sauvegardez ces fichiers et stockez-les dans un emplacement sécurisé de façon à pouvoir continuer à déchiffrer le contenu protégé par cette clé de locataire. De plus, si vous migrez vers AD RMS, vous pouvez importer ce fichier de TPD (dont le nom commence par **ExportedTDP**) dans votre serveur AD RMS.

##### Étape 4 : En cours : Protection de votre clé de locataire

-   Après avoir reçu votre clé de locataire, conservez-la en lieu sûr, car toute personne y ayant accès peut déchiffrer tous les documents qu'elle protège.

    Si vous exportez votre clé de locataire parce que vous ne voulez plus utiliser Azure RMS, nous vous conseillons de désactiver votre locataire RMS. Ne reportez pas cela à plus tard après avoir reçu votre clé de locataire, car cette précaution vous aidera à minimiser les conséquences éventuelles d'un accès à votre clé de locataire par une personne non autorisée. Pour obtenir des instructions, consultez [Désaffectation et désactivation de Gestion des droits Azure](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md).

### <a name="BKMK_MSBreach"></a>Réponse à une violation
Un système de sécurité est incomplet sans un processus de réponse aux violations. Votre clé de locataire peut être compromise ou volée. Même si elle est bien protégée, des vulnérabilités peuvent être détectées dans la technologie actuelle du module de sécurité matériel (HSM), ou dans les longueurs et les algorithmes des clés.

Microsoft dispose d'une équipe chargée de répondre aux incidents de sécurité survenant dans ses produits et services. Dès la réception d'un rapport d'incident avéré, cette équipe met tout en œuvre pour analyser la portée, la cause première et les actions de correction à mettre en place. Si ces incidents affectent vos ressources, Microsoft enverra une notification par courrier électronique (à l'adresse fournie lors de la création de l'abonnement) aux administrateurs de votre client Azure RMS.

En cas de violation, la meilleure mesure que vous ou Microsoft puissiez prendre dépend de la portée de la violation. Microsoft vous accompagnera dans ce processus. Le tableau suivant présente des situations type et les réponses que vous pouvez mettre en place. Toutefois, la réponse exacte que vous apporterez dépendra des informations obtenues lors de l'analyse.

|Description de l'incident|Réponse possible|
|-----------------------------|--------------------|
|Votre clé de locataire a fait l'objet d'une fuite.|Renouvelez votre clé de locataire. Consultez la section [Renouvellement de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_MSRekey) dans cet article.|
|Une personne non autorisée ou un programme malveillant a obtenu le droit d'utiliser votre clé de locataire, sans que celle-ci ait fait l'objet d'une fuite.|Dans ce cas, le renouvellement de votre clé de locataire ne sera pas utile et une analyse de la cause première sera obligatoire. Si un bogue au niveau d'un processus ou d'un logiciel est responsable de l'accès de l'individu non autorisé, cette situation doit être résolue.|
|Une vulnérabilité a été découverte dans l'algorithme RSA ou la longueur de la clé, ou des attaques en force brute peuvent être envisagées au niveau informatique.|Microsoft doit mettre à jour les services Azure RMS pour prendre en charge de nouveaux algorithmes et longueurs de clé plus élevées qui sont résilients, mais également informer tous les clients qu'ils doivent renouveler leur clé de locataire.|

## <a name="BKMK_BYOKManagedOperations"></a>Géré par le client : opérations de cycle de vie de la clé de locataire
Si vous gérez votre clé de locataire pour Azure Rights Management (dans le cadre d'un scénario BYOK, ou Bring Your Own Key), utilisez les sections suivantes pour obtenir plus d'informations sur les opérations de cycle de vie qui s'appliquent à cette topologie :

-   [Révocation de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRevoke)

-   [Renouvellement de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRekey)

-   [Sauvegarde et récupération de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKBackup)

-   [Exportation de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKExport)

-   [Réponse à une violation](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKBreach)

### <a name="BKMK_BYOKRevoke"></a>Révocation de votre clé de locataire
Lorsque vous annulez votre abonnement aux services Azure RMS, ces derniers arrêtent d'utiliser votre clé de locataire et aucune autre action n'est requise de votre part.

### <a name="BKMK_BYOKRekey"></a>Renouvellement de votre clé de locataire
Le renouvellement de la clé est également appelé déploiement de la clé. Ne renouvelez pas votre clé de locataire à moins que ce soit vraiment nécessaire. Les clients plus anciens, tels qu'Office 2010, n'ont pas été conçu pour gérer naturellement les changements de clés. Dans ce scénario, vous devez effacer l'état RMS des ordinateurs à l'aide d'une stratégie de groupe ou d'un mécanisme similaire. Toutefois, certains événements légitimes peuvent vous obliger à renouveler votre clé de locataire. Par exemple :

-   Votre entreprise s'est divisée en deux sociétés distinctes ou plus. Lorsque vous renouvelez votre clé de locataire, la nouvelle société n'aura pas accès au nouveau contenu publié par vos employés. Elle pourra toujours accéder à l'ancien contenu si elle dispose d'une copie de l'ancienne clé de locataire.

-   Vous pensez que la copie principale de votre clé de locataire (celle en votre possession) a été compromise.

Lorsque vous renouvelez votre clé de locataire, le nouveau contenu est protégé à l'aide de la nouvelle clé de locataire. Vous obtenez ce résultat en plusieurs étapes. Ainsi, pendant un certain temps, certains nouveaux contenus continueront d'être protégés par l'ancienne clé de locataire. Le contenu précédemment protégé reste protégé par l'ancienne clé de locataire. Pour prendre en charge ce scénario, les services Azure RMS conservent votre ancienne clé de locataire afin qu'ils puissent émettre des licences pour l'ancien contenu.

Pour renouveler votre clé de locataire, générez et créez une nouvelle clé sur Internet ou manuellement en suivant les procédures décrites dans la section [Implémentation de la solution Bring Your Own Key (BYOK)](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_ImplementBYOK) de la rubrique [Planification et implémentation de la clé de locataire Azure Rights Management](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md).

### <a name="BKMK_BYOKBackup"></a>Sauvegarde et récupération de votre clé de locataire
Vous êtes responsable de la sauvegarde de votre clé de locataire. Si vous avez généré votre clé de locataire dans un module de sécurité matériel Thales, pour sauvegarder la clé, il vous suffit de sauvegarder le fichier de clé tokénisée, le fichier Word ainsi que les cartes Administrateur.

Si vous avez transféré votre clé en suivant les procédures décrites dans la section [Implémentation de la solution Bring Your Own Key (BYOK)](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_ImplementBYOK) de la rubrique [Planification et implémentation de la clé de locataire Azure Rights Management](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md), les services Azure RMS rendront le fichier de clé tokénisée persistant pour le protéger contre l'échec de nœuds Azure RMS. Cependant, il ne s'agit pas là d'une sauvegarde complète. Par exemple, si vous avez besoin d'une copie en clair de votre clé afin d'utiliser celle-ci en dehors d'un module de sécurité matériel Thales, les services Azure RMS ne pourront pas le récupérer à votre place, car ils ne disposent que d'une copie non récupérable.

### <a name="BKMK_BYOKExport"></a>Exportation de votre clé de locataire
Si vous utilisez une solution BYOK, vous ne pouvez pas exporter votre clé de locataire à partir d'Azure RMS. La copie se trouvant dans Azure RMS est non récupérable. Si vous souhaitez supprimer cette clé afin qu'elle soit inutilisable, contactez le service clientèle Microsoft.

### <a name="BKMK_BYOKBreach"></a>Réponse à une violation
Un système de sécurité est incomplet sans un processus de réponse aux violations. Votre clé de locataire peut être compromise ou volée. Même si elle est bien protégée, des vulnérabilités peuvent être détectées dans la technologie actuelle du module de sécurité matériel (HSM), ou dans les longueurs et les algorithmes des clés.

Microsoft dispose d'une équipe chargée de répondre aux incidents de sécurité survenant dans ses produits et services. Dès la réception d'un rapport d'incident avéré, cette équipe met tout en œuvre pour analyser la portée, la cause première et les actions de correction à mettre en place. Si ces incidents affectent vos ressources, Microsoft enverra une notification par courrier électronique (à l'adresse fournie lors de la création de l'abonnement) aux administrateurs de votre client Azure RMS.

En cas de violation, la meilleure action que vous ou Microsoft pourra mettre en place dépend de la portée de la violation. Microsoft vous accompagnera lors de ce processus. Le tableau suivant présente des situations type et les réponses que vous pouvez mettre en place. Toutefois, la réponse exacte que vous apporterez dépendra des informations obtenues lors de l'analyse.

|Description de l'incident|Réponse possible|
|-----------------------------|--------------------|
|Votre clé de locataire a fait l'objet d'une fuite.|Renouvelez votre clé de locataire. Consultez la section [Renouvellement de votre clé de locataire](../Topic/Operations_for_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_BYOKRekey) dans cet article.|
|Une personne non autorisée ou un programme malveillant a obtenu le droit d'utiliser votre clé de locataire, sans que celle-ci ait fait l'objet d'une fuite.|Dans ce cas, le renouvellement de votre clé de locataire ne sera pas utile et une analyse de la cause première sera obligatoire. Si un bogue au niveau d'un processus ou d'un logiciel est responsable de l'accès de l'individu non autorisé, cette situation doit être résolue.|
|Vulnérabilité détectée dans la technologie HSM actuelle.|Microsoft doit mettre à jour les modules de sécurité matériel. S'il y a des raisons de penser que les clés ont été exposées via cette vulnérabilité, Microsoft demandera à tous les clients de renouveler leur clé de locataire.|
|Une vulnérabilité a été découverte dans l'algorithme RSA ou la longueur de la clé, ou des attaques en force brute peuvent être envisagées au niveau informatique.|Microsoft doit mettre à jour les services Azure RMS pour prendre en charge de nouveaux algorithmes et longueurs de clé plus élevées qui sont résilients, mais également informer tous les clients qu'ils doivent renouveler leur clé de locataire.|

## Voir aussi
[Utilisation d'Azure Rights Management](../Topic/Using_Azure_Rights_Management.md)

