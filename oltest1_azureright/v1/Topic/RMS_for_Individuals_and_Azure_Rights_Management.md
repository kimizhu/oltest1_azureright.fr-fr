---
description: na
keywords: na
title: RMS for Individuals and Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2efcb440-fefd-45e9-872b-f471573aadf2
---
# RMS for Individuals et Azure Rights Management
RMS for Individuals est un abonnement gratuit en libre-service destiné aux utilisateurs au sein d'une organisation, qui reçoivent des fichiers sensibles protégés par Gestion des droits Microsoft Azure (Azure RMS), mais qui ne peuvent pas s'authentifier parce que le département informatique ne gère pas de compte pour eux dans Azure. Par exemple, le département informatique ne dispose pas d'Office 365 ou n'utilise par les services Azure.

Ces utilisateurs peuvent créer un compte professionnel ou scolaire gratuit à utiliser avec Azure RMS, puis télécharger et installer l'application de partage Rights Management. Par conséquent, ces utilisateurs peuvent désormais s'authentifier pour prouver qu'ils sont bien la personne à qui les fichiers protégés ont été envoyés, puis lire ceux-ci sur des ordinateurs ou des appareils mobiles.

À l'aide de l'application de partage Rights Management sur un ordinateur Windows, ces utilisateurs peuvent également protéger des fichiers sur place ou envoyer des fichiers protégés par courrier électronique à des personnes faisant ou non partie de leur organisation. Si les destinataires du courrier électronique appartiennent à une organisation qui ne gère pas non plus de comptes utilisateurs dans Azure, ils peuvent également créer un compte RMS for Individuals pour lire les pièces jointes protégées.

> [!IMPORTANT]
> Cet abonnement gratuit garantit que des personnes autorisées puissent toujours lire des fichiers protégés. Actuellement, vous pouvez également utiliser cet abonnement gratuit pour protéger des documents et créer de nouveaux messages électroniques. Toutefois, la capacité de création de contenu protégé est destinée uniquement à des fins d'évaluation et risque d'être supprimée dans le futur. Pour plus d'informations et suivre les éventuelles modifications apportées à l'utilisation de RMS for Individuals pour protéger du contenu, voir les [Conditions d'utilisation de Microsoft Rights Management](https://portal.aadrm.com/Legal/Service).

Pour plus d'informations sur la façon dont vous pouvez protéger des fichiers à l'aide de l'application de partage Rights Management gratuite, consultez le [Guide de l'utilisateur de l'application de partage Rights Management](http://technet.microsoft.com/library/dn339006.aspx).

RMS for Individuals est un exemple d'inscription en libre-service prise en charge par Azure Active Directory. Pour plus d'informations sur son fonctionnement, voir [Qu'est-ce qu'une inscription libre-service à Azure ?](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/) dans la documentation de Microsoft Azure. Pour plus d'informations spécifiques de RMS for Individuals, voir les sections suivantes :

-   [Inscription à RMS for individuals](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_SignUp)

    -   [Présentation technique](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TechnicalOverview)

-   [Contrôle administrateur des comptes créés pour RMS for individuals](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TakeControlofAccounts)

-   [Détermination des utilisateurs inscrits à RMS for Individuals](#BKMK_Detect)

## <a name="BKMK_SignUp"></a>Inscription à RMS for individuals
Pour obtenir un compte gratuit, demandez-le via la [page Microsoft Rights Management](https://portal.aadrm.com/) et indiquez votre adresse de messagerie professionnelle ou scolaire. Le plus souvent, vous êtes redirigé vers cette page d'inscription si vous recevez un message électronique avec pièce jointe protégée, qui contient des instructions sur la manière de s'inscrire. Vous recevez alors un message électronique en réponse de Microsoft, et pouvez ensuite effectuer la procédure d'inscription en fournissant les détails nécessaires pour la création de votre compte. Lorsque vous recevez un message de confirmation de Microsoft, cet ultime courrier électronique vous renvoie à une page à partir de laquelle vous pouvez télécharger l'application de partage pour différents appareils, et qui contient un lien vers le guide de l'utilisateur.

#### Inscription à RMS for individuals

1.  À l'aide d'un ordinateur Windows ou Mac, accédez à la page [Microsoft Rights Management](https://portal.aadrm.com).

2.  Entrez l'adresse de messagerie que vous utilisez au sein de votre organisation, par exemple,**janetm@contoso.com** ou **p.dover@fabrikam.com**.

    > [!IMPORTANT]
    > Les adresses e-mail personnelles ne sont pas prises en charge. Par conséquent, n'indiquez pas de compte Microsoft (anciennement compte Microsoft Live ID) ou tout autre compte personnel que vous pouvez utiliser à votre domicile avec votre fournisseur d'accès à Internet.

3.  Cliquez sur **Mise en route**.

    Microsoft utilise votre adresse de messagerie pour vérifier si votre organisation possède déjà un [abonnement payant incluant Azure RMS](https://technet.microsoft.com/library/dn655136.aspx). Si tel est le cas, vous n'avez pas besoin de RMS for Individuals. Vous êtes connecté immédiatement et l'inscription en libre-service à RMS for Individuals est annulée. Si aucun abonnement payant pour Azure RMS n'est trouvé, vous passez à l'étape suivante.

4.  Attendez qu'un e-mail de confirmation soit envoyé à l'adresse que vous avez indiquée. Il doit provenir de Microsoft (DoNotReply@microsoft.com) et sont objet est **Microsoft RMS**.

5.  Cliquez ensuite sur le lien figurant dans les instructions pour terminer l'inscription.

6.  Ce lien vous permet d'accéder à une nouvelle page **Microsoft Rights Management** dans laquelle vous pouvez entrer les informations relatives à votre compte. Tapez vos nom et prénom, entrez et confirmez le mot de passe de votre choix, sélectionnez votre pays dans la liste déroulante (ou le pays le plus proche si le vôtre n'y figure pas), puis cliquez sur **Créer**.

7.  Vous devez alors recevoir un autre e-mail de Microsoft, vous confirmant que votre compte est prêt à l'emploi.

8.  Lorsque vous recevez le message électronique, cliquez sur le lien de connexion pour lire les instructions de téléchargement et d'installation de l'application de partage, ou cliquez sur le lien Aide pour lire le guide de l'utilisateur de celle-ci.

Votre compte étant créé, vous pouvez à présent protéger des fichiers et lire des fichiers protégés par d'autres personnes. Lorsque vous êtes invité à vous connecter pour protéger des fichiers ou lire des fichiers protégés, entrez l'adresse e-mail et le mot de passe utilisés lors de la création du compte RMS for Individuals.

### <a name="BKMK_TechnicalOverview"></a>Présentation technique
RMS for Individuals utilise un processus d'inscription en libre-service dont se servent également d'autres services recourant à la technologie cloud de Microsoft pour l'authentification des utilisateurs.

Voici ce qui se passe en arrière-plan quand un utilisateur s'inscrit à RMS for individuals alors que son organisation n'a pas d'abonnement Office 365 ou Azure, et donc pas d'annuaire dans Azure pour authentifier les utilisateurs :

1.  Lorsque le premier utilisateur d'une organisation demande un abonnement RMS for Individuals, le nom de domaine figurant dans son adresse de messagerie est vérifié afin de déterminer s'il est déjà associé à un client Azure. À défaut de client existant, un client est automatiquement créé pour l'organisation, ainsi qu'un répertoire Azure contenant un compte pour ce premier utilisateur. Contrairement à un abonnement payant à Azure, le premier compte n'est pas un compte d'administrateur général, mais d'utilisateur standard. Le nouveau compte utilise l'adresse de messagerie et le mot de passe fournis par l'utilisateur.

    > [!NOTE]
    > Certains noms de domaine ne peuvent pas être utilisés pour créer l'annuaire. Ils ne peuvent donc pas non plus être utilisés pour RMS for individuals. La liste des noms de domaines bloqués figure dans le fichier JSON (JavaScript Objet Notation) [http://portal.aadrm.com/content/blocked_domains.json](http://portal.aadrm.com/content/blocked_domains.json)

    Si un client est trouvé, son compte est vérifié pour voir s'il dispose déjà un abonnement Azure RMS. À défaut, l'abonnement gratuit à RMS for Individuals peut être ajouté.

2.  L'organisation reçoit un abonnement RMS for Individuals. Désormais, Azure peut authentifier cet utilisateur qui peut ensuite protéger des fichiers et lire des fichiers protégés par d'autres à l'aide de la solution Gestion des droits Azure. Pour protéger des fichiers et lire des fichiers protégés, l'utilisateur doit disposer d'une application compatible RMS, telle que l'[application de partage Rights Management](https://technet.microsoft.com/library/dn919648.aspx) disponible gratuitement.

3.  Lorsque le deuxième utilisateur de la même organisation demande un abonnement RMS for individuals, un nouveau compte utilisateur est ajouté à l'annuaire Azure créé précédemment en utilisant l'abonnement RMS for individuals de l'organisation. Ce deuxième utilisateur a les mêmes droits que le premier (protéger des fichiers et lire des fichiers protégés), mais, en plus de cela, les deux utilisateurs peuvent désormais collaborer plus aisément en toute sécurité, car ils peuvent rapidement appliquer des modèles par défaut à des fichiers, qui restreignent l'accès aux comptes figurant dans l'annuaire Azure de leur organisation.

4.  Les utilisateurs suivants de la même organisation procèdent de même, en ajoutant des comptes d'utilisateur (lors de l'inscription) à l'annuaire Azure de l'organisation. Plus il y a de comptes associés à l'annuaire, plus le nombre d'utilisateurs pouvant collaborer en toute sécurité est important. Cela permet d'empêcher simplement que des personnes non autorisées lisent des fichiers auxquels elles ne devraient pas avoir accès.

Grâce à ce processus, aucun frais n'est imputé à l'organisation et aucune intervention du service informatique n'est requise. Cependant, le département informatique peut choisir d'effectuer l'une des actions suivantes :

-   **Gérer les comptes et le processus d'inscription** : les administrateurs informatiques peuvent prendre possession de l'annuaire créé automatiquement et des comptes dans Azure. Ils peuvent ensuite gérer les comptes en implémentant des solutions d'intégration d'annuaire, telles que la synchronisation des mots de passe et l'authentification unique. Ils peuvent également empêcher des utilisateurs de créer des comptes ou de s'inscrire à RMS for Individuals.

    Pour plus d'informations, consultez la section suivante [Contrôle administrateur des comptes créés pour RMS for individuals](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md#BKMK_TakeControlofAccounts).

-   **Gérer Rights Management** : Les administrateurs informatiques peuvent convertir l'abonnement RMS for individuals de l'organisation en abonnement payant incluant Azure Rights Management. Dans ce cas, l'annuaire et les comptes Azure existants sont préservés afin d'assurer une transition transparente pour les utilisateurs de RMS for individuals. Les fichiers que les utilisateurs ont protégés le restent, avec les mêmes stratégies, et les personnes autorisées peuvent continuer à y accéder de la même manière.

    Cette conversion permet à l'organisation d'intégrer Rights Management dans ses flux de travaux, ses services et ses magasins de données. Vous pouvez en outre gérer Rights Management, puisque vous contrôlez la clé de locataire de l'organisation pour Azure Rights Management. Vous pouvez à présent exécuter les actions suivantes :

    -   Configurez Exchange et SharePoint pour la prise en charge d'Azure Rights Management, même si ces éléments s'exécutent en local. Exchange et SharePoint sont pris en charge en mode natif pour les services en ligne et sont pris en charge par un connecteur pour les serveurs locaux. Pour plus d'informations, consultez les rubriques suivantes :

        -   Les sections Exchange Online et SharePoint Online de [Office 365 : configuration pour les clients et services en ligne](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_O365) dans la rubrique [Configuration d'applications pour Azure Rights Management](../Topic/Configuring_Applications_for_Azure_Rights_Management.md)

        -   [Déploiement du connecteur Azure Rights Management](../Topic/Deploying_the_Azure_Rights_Management_Connector.md)

    -   Exécutez le processus eDiscovery sur les données de votre organisation, afin de pouvoir déchiffrer, si nécessaire, les fichiers qui ont été protégés à l'aide de Rights Management. Pour plus d'informations, consultez [Configuration de super utilisateurs pour Azure Rights Management et les services de découverte ou la récupération de données](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md).

    -   Consignez l'ensemble de l'activité liée à Rights Management de votre organisation. Il s'agit d'informations précieuses puisque vous pouvez non seulement savoir quels fichiers sont protégés et qui y accède, mais également identifier le comportement potentiellement suspect de personnes non autorisées. Pour plus d'informations, consultez [Journalisation et analyse de l'utilisation d'Azure Rights Management](../Topic/Logging_and_Analyzing_Azure_Rights_Management_Usage.md).

    -   Offrir aux utilisateurs la possibilité de suivre et révoquer leurs documents protégés, si ces fonctionnalités sont prises en charge par votre [abonnement Azure RMS](https://technet.microsoft.com/dn858608). Pour plus d'informations, voir  [Suivre et révoquer vos documents quand vous utilisez l'application de partage RMS](https://technet.microsoft.com/library/dn986611.aspx) dans le [Guide d'utilisation de l'application de partage Rights Management](https://technet.microsoft.com/library/dn339006.aspx).

    -   Implémentez une solution Bring you own key (BYOK) afin que votre clé de locataire pour Azure Rights Management soit générée en local selon vos stratégies informatiques, puis transférée en toute sécurité à Microsoft grâce à un module de sécurité matériel (HSM). Pour plus d'informations, consultez [Planification et implémentation de la clé de locataire Azure Rights Management](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md).

## <a name="BKMK_TakeControlofAccounts"></a>Contrôle administrateur des comptes créés pour RMS for individuals
Même si vous ne souhaitez pas convertir l'abonnement RMS for individuals de votre organisation en un abonnement payant, vous pouvez tout de même contrôler les comptes d'utilisateur associés à l'annuaire Azure de votre organisation de l'une des manières suivantes :

-   Implémentez des solutions d'intégration d'annuaire pour Azure Active Directory et votre infrastructure de services de domaine Active Directory. Vous pouvez synchroniser les comptes et les mots de passe, afin que les utilisateurs n'aient pas à créer de nouveaux comptes pour utiliser Rights Management. Vos stratégies de mot de passe locales s'appliqueront ainsi aux nouveaux comptes utilisateur Azure. Vous pouvez également synchroniser les mots de passe, afin que les utilisateurs n'aient pas à mémoriser un autre mot de passe pour utiliser Rights Management.

-   Vous pouvez empêcher des utilisateurs de s'inscrire pour utiliser la solution Gestion des droits Azure avec l'abonnement RMS for Individuals. Le plus souvent, cette option est peu avantageuse, car les utilisateurs partagent des fichiers sans protection (ce qui constitue un danger pour l'organisation) ou utilisent un autre mécanisme de protection de fichiers qui empêche le service informatique d'accéder aux données. Toutefois, si vous souhaitez vraiment empêcher des utilisateurs de s'inscrire à RMS for Individuals, procédez de l'une des manières suivantes après avoir acquis la propriété de l'annuaire de votre organisation dans Azure :

    -   Empêchez tout utilisateur de souscrire un abonnement en libre-service, RMS for Individuals inclus.  (Actuellement, ce paramètre s'applique à tous les abonnements Azure qui utilisent le processus en libre-service, et vous ne pouvez pas sélectionner le service concerné). Pour ce faire, définissez le paramètre **AllowAdHocSubscriptions** sur false avec l'applet de commande [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx) du module Windows PowerShell pour Azure Active Directory. Par exemple : **Set-MsolCompanySettings -AllowAdHocSubscriptions $false**

    -   Empêchez les utilisateurs de créer un compte dans Azure, ce qui signifie que seuls les utilisateurs ayant déjà un compte peuvent souscrire des abonnements en libre-service, dont l'abonnement RMS for Individuals.  Pour ce faire, définissez le paramètre **AllowEmailVerifiedUsers** sur false avec l'applet de commande [Set-MsolCompanySettings](http://technet.microsoft.com/library/dn194127.aspx) du module Windows PowerShell pour Azure Active Directory. Par exemple : **Set-MsolCompanySettings -AllowEmailVerifiedUsers $false -AllowAdHocSubscriptions $true**

    -   Synchronisez votre infrastructure de services de domaine Active Directory avec Azure Active Directory. Cela empêche la création de comptes lorsque des utilisateurs souscrivent des abonnements en libre-service tel l'abonnement RMS for Individuals. Vous pouvez par ailleurs supprimer ou désactiver des comptes précédemment créés dans l'annuaire Azure.

Pour contrôler les comptes d'utilisateur dans l'annuaire Azure, ou empêcher des utilisateurs de s'inscrire à RMS for individuals, vous devez disposer d'un abonnement Azure et être propriétaire de l'annuaire. Si vous n'avez pas encore d'abonnement Azure, vous pouvez en obtenir un gratuitement. Si un annuaire a été créé automatiquement pour vous lors du processus d'abonnement en libre-service, acquérez la propriété du domaine utilisé pour le créer. Si vous possédez déjà un annuaire dans Azure, et que les utilisateurs ont spécifié un nouveau domaine que vous utilisez dans votre organisation, fusionnez ce domaine dans votre annuaire existant. Pour plus d'informations, voir les instructions de la rubrique [Qu’est-ce qu'une inscription libre-service à Azure ?](https://azure.microsoft.com/documentation/articles/active-directory-self-service-signup/)

## <a name="BKMK_Detect"></a>Détermination des utilisateurs inscrits à RMS for Individuals
En tant qu'administrateur, vous souhaitez sûrement savoir si vos utilisateurs se sont inscrits à RMS for individuals. Pour ce faire, utilisez une ou plusieurs des méthodes suivantes :

-   Demandez aux utilisateurs comment ils protègent les fichiers hautement confidentiels, en particulier lorsqu'ils collaborent avec des personnes extérieures à l'organisation.

-   Si vous avez un abonnement Azure pour votre organisation, utilisez l'applet de commande [Get-MsolAccountSku](https://msdn.microsoft.com/library/azure/dn194118.aspx) pour voir si **RIGHTSMANAGEMENT_ADHOC** est renvoyé comme l'un des abonnements. Si c'est le cas, il s'agit de l'abonnement RMS for individuals qui a été accordé à l'organisation, avec un pool d'unités actives disponibles dont les utilisateurs peuvent se servir pour le processus d'inscription libre-service.

-   Utilisez une solution de gestion de système, telle que System Center Configuration Manager, pour dresser l'inventaire des logiciels installés et utilisés. L'application de partage Rights Management s'exécute à l'aide du programme **ipviewer.exe** et vous pouvez [télécharger et installer l'application](http://go.microsoft.com/fwlink/?LinkId=303970) gratuitement pour identifier d'autres caractéristiques de cette application que vous utilisez ensuite pour l'inventaire logiciel.

-   Recherchez les extensions de nom de fichier créées par l'application de partage Rights Management. Les extensions de nom de fichier .pfile et .ppdf sont des exemples évidents, mais d'autres fichiers changent d'extension de nom quand ils font l'objet d'une protection native de Rights Management. Pour plus d'informations, consultez la section [Types de fichiers pris en charge et extensions de nom de fichier](http://technet.microsoft.com/library/dn339003.aspx) du [Guide de l'administrateur sur l'application de partage Rights Management](http://technet.microsoft.com/library/dn339003.aspx).

## Voir aussi
[Prise en main d'Azure Rights Management](../Topic/Getting_Started_with_Azure_Rights_Management.md)

