---
description: na
keywords: na
title: Frequently Asked Questions for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 71ce491f-41c1-4d15-9646-455a6eaa157d
---
# Forum aux questions d&#39;Azure Rights Management
Forum Aux Questions concernant Microsoft [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)], également appelé Azure RMS :

## Quelles sont les conditions requises pour déployer Azure RMS et comment procéder ?
Tout d’abord, pour plus d’informations sur les options d’abonnement au cloud, l’utilisation des serveurs locaux avec Azure RMS, les scénarios de déploiement non pris en charge, les appareils et applications prenant en charge Azure RMS et pour obtenir un lien vers une liste d’adresses IP et de noms de domaine pour les pare-feu ou les serveurs proxy, voir [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md). Vous pouvez également consulter les autres rubriques de la section [Prise en main d'Azure Rights Management](../Topic/Getting_Started_with_Azure_Rights_Management.md) pour comprendre comment [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)] peut vous aider à protéger les données de votre organisation, son fonctionnement avec les applications ainsi que ses différences avec la version locale d’Active Directory Rights Management, et pour connaître les termes et abréviations spécifiques à [!INCLUDE[aad_rightsmanagement_1](../Token/aad_rightsmanagement_1_md.md)].

Lorsque vous êtes prêt à tester Azure RMS ou à le déployer pour votre organisation, voir [feuille de route pour le déploiement d'Azure Rights Management](../Topic/Azure_Rights_Management_Deployment_Roadmap.md) pour connaître la procédure à suivre et obtenir des liens vers davantage d’informations et d’instructions.

Pour encore plus d’informations, de ressources et d’options de prise en charge, voir [Informations et support technique pour Azure Rights Management](../Topic/Information_and_Support_for_Azure_Rights_Management.md).

## Puis-je intégrer Azure RMS avec mes serveurs sur site ?
Oui. Vous pouvez intégrer Azure RMS avec vos serveurs locaux, tels que les serveurs de fichiers Windows, Exchange Server et SharePoint. Pour ce faire, utilisez le [connecteur Rights Management](https://technet.microsoft.com/library/dn375964.aspx). Ou bien, si vous êtes simplement intéressé par l’utilisation de l’Infrastructure de classification des fichiers avec Windows Server, vous pouvez utiliser les [applets de commande de protection RMS](https://technet.microsoft.com/library/mt601315%28v=ws.10%29.aspx). Vous pouvez également synchroniser et fédérer vos contrôleurs de domaine Active Directory avec Azure AD pour une expérience d’authentification plus agréable pour les utilisateurs, par exemple, en utilisant [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/).

Azure RMS génère et gère automatiquement les certificats XrML de façon appropriée. Il n’utilise donc pas d’infrastructure à clé publique locale. Pour plus d’informations sur la façon dont Azure RMS utilise les certificats, voir la section [Procédure pas à pas décrivant le fonctionnement d'Azure RMS : première utilisation, protection du contenu, consommation du contenu](../Topic/What_is_Azure_Rights_Management_.md#BKMK_Walthrough) de la rubrique [Qu'est-ce qu'Azure Rights Management ?](../Topic/What_is_Azure_Rights_Management_.md).

## J’ai un déploiement hybride d’Exchange avec certains utilisateurs sur Exchange Online et d’autres utilisateurs sur Exchange Server. Est-ce compatible avec Azure RMS ?
Absolument, et l’avantage est que les utilisateurs peuvent protéger et consommer sans problème des messages électroniques et pièces jointes entre les deux déploiements Exchange. Pour cette configuration, activez [Azure RMS](https://technet.microsoft.com/library/jj658941.aspx) et [Gestion des droits relatifs à l’information (IRM) pour Exchange Online](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx), puis [déployez et configurez le connecteur RMS](https://technet.microsoft.com/library/dn375964.aspx) pour Exchange Server.

## Si je déploie Azure RMS en production, ma société est-elle enfermée dans la solution ou risque-t-elle de perdre l’accès au contenu protégé par Azure RMS ?
Non, vous gardez toujours le contrôle de vos données et pouvez continuer à y accéder, même si vous décidez de ne plus utiliser Azure RMS. Pour plus d’informations, voir [Désaffectation et désactivation de Gestion des droits Azure](../Topic/Decommissioning_and_Deactivating_Azure_Rights_Management.md).

Toutefois, avant que vous désaffectiez votre déploiement Azure RMS, nous aimerions que vous nous aidiez à comprendre pourquoi vous avez pris cette décision. Si Azure RMS ne répond pas à vos besoins, demandez-nous si de nouvelles fonctionnalités sont prévues dans un futur proche ou s’il existe des alternatives. Envoyez un message électronique à [AskIPTeam@Microsoft.com](mailto:askipteam@microsoft.com?subject=Planning%20to%20decommission%20Azure%20RMS). Nous serons heureux de discuter de vos exigences techniques et professionnelles.

## Puis-je contrôler les utilisateurs pouvant utiliser Azure RMS pour protéger du contenu ?
Oui, Azure RMS dispose de contrôles d’intégration d’utilisateur pour ce scénario. Pour plus d’informations, voir la section [Configuration de contrôles d'intégration pour un déploiement échelonné](../Topic/Activating_Azure_Rights_Management.md#BKMK_OnboardingControls) dans la rubrique [Activation d'Azure Rights Management](../Topic/Activating_Azure_Rights_Management.md).

## Puis-je empêcher des utilisateurs de partager des documents protégés avec des organisations spécifiques ?
L’un des avantages majeurs d’Azure RMS est qu’il prend en charge la collaboration interentreprises sans que vous deviez configurer des approbations explicites pour chaque organisation partenaire, car Azure AD se charge de l’authentification à votre place.

Il n’existe aucune option d’administration permettant d’empêcher des utilisateurs de partager en toute sécurité des documents avec des organisations spécifiques. Par exemple, imaginons que vous souhaitiez bloquer une organisation en laquelle vous n’avez pas confiance ou qui exerce une activité concurrente. Empêcher Azure RMS d’envoyer des documents protégés à des utilisateurs travaillant au sein de cette organisation n’aurait aucun sens, car ceux-ci partageraient leurs documents non protégés, ce qui est probablement la dernière chose que vous souhaitez dans le cadre de ce scénario. Par exemple, vous ne seriez pas en mesure d’identifier qui partage des documents confidentiels avec quels utilisateurs au sein de ces organisations, contrairement à ce que vous pouvez faire quand le document (ou le message électronique) est protégé par Azure RMS.

## Lors du partage d’un document protégé avec une personne extérieure à mon organisation, comment cet utilisateur s’authentifie-t-il ?
Azure RMS utilise toujours un compte Azure Active Directory et une adresse de messagerie associée pour l’authentification de l’utilisateur, ce qui rend la collaboration interentreprises transparente pour les administrateurs. Si l’autre organisation utilise des services Azure, les utilisateurs disposent déjà de comptes dans Azure Active Directory, même si ceux-ci sont créés et gérés localement, puis synchronisés avec Azure.  Si l’organisation dispose d’Office 365, en arrière-plan, ce service utilise également Azure Active Directory pour les comptes d’utilisateur.  Si l’organisation de l’utilisateur ne dispose pas de compte géré dans Azure, les utilisateurs peuvent s’inscrire à [RMS for Individuals](https://technet.microsoft.com/library/dn592127.aspx), ce qui a pour effet de créer un locataire Azure non managé et un annuaire pour l’organisation avec un compte pour l’utilisateur, afin que celui-ci puisse s’authentifier après d’Azure RMS.

La méthode d’authentification pour ces comptes peut varier en fonction de la manière dont l’administrateur de l’autre organisation a configuré les comptes Azure Active Directory. Par exemple, ils peuvent utiliser des mots de passe créés pour ces comptes, Multi-Factor Authentication (MFA), une fédération ou des mots de passe créés dans les services de domaine Active Directory, puis synchronisés avec Azure Active Directory.

## Puis-je ajouter des utilisateurs ne faisant pas partie de mon organisation à des modèles personnalisés ?
Oui.  La création de modèles personnalisés que les utilisateurs finaux (et administrateurs) peuvent sélectionner à partir d’applications accélère et facilite l’application de la protection des informations à l’aide de stratégies prédéfinies que vous spécifiez. L’un des paramètres du modèle définit qui peut accéder au contenu, et vous pouvez spécifier des utilisateurs et des groupes au sein de votre organisation, ainsi que des utilisateurs extérieurs à celle-ci.

Pour spécifier des utilisateurs extérieurs à votre organisation, utilisez le [module Windows PowerShell pour Azure Rights Management](https://technet.microsoft.com/library/jj585012.aspx).

-   **Utilisez un objet de définition de droits pour créer ou mettre à jour un modèle**.    Spécifiez les adresses de messagerie externes et leurs droits dans un objet de définition de droits, que vous pouvez ensuite utiliser pour créer ou mettre à jour un modèle. Spécifiez l’objet de définition de droits à l’aide de l’applet de commande [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx) pour créer une variable et spécifier ensuite cette variable dans le paramètre -RightsDefinition avec l’applet de commande [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx) (pour un nouveau modèle) ou l’applet de commande [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx) (si vous modifiez un modèle existant). Cependant, si vous ajoutez ces utilisateurs à un modèle existant, vous devez définir des objets de définition de droits pour les groupes existants des modèles et pas seulement les utilisateurs externes.

Pour plus d’informations sur les modèles personnalisés, voir [Configuration de modèles personnalisés pour Azure Rights Management](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md).

## Quels appareils et types de fichier Azure RMS prend-il en charge ?
Pour obtenir la liste des appareils pris en charge, voir la section [Périphériques client prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedDevices) de la rubrique [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md). Les fonctionnalités RMS n’étant pas actuellement disponibles sur tous les appareils pris en charge, pensez à consulter la table [Fonctionnalités d’un appareil client](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_ClientCapabilities) dans la même rubrique.

Azure RMS peut prendre en charge tous les types de fichier. Dans le cas de texte, d’images, de fichiers Microsoft Office (Word, Excel, PowerPoint), de fichiers .pdf et d’autres types de fichier d’application, Azure RMS offre une protection native qui comprend le chiffrement et la mise en application de droits (autorisations). Pour tous les autres types de fichier et d’application, la protection générique offre l’encapsulation et l’authentification des fichiers afin de vérifier si un utilisateur est autorisé à ouvrir le fichier.

Pour obtenir la liste des extensions prises en charge en mode natif par Azure RMS, voir la section [Types et extensions de noms de fichiers pris en charge](http://technet.microsoft.com/library/dn339003.aspx) dans le [Guide administrateur de l’application de partage Rights Management](http://technet.microsoft.com/library/dn339003.aspx). Les extensions de nom de fichier qui ne figurent pas dans la liste sont prises en charge via l’utilisation de l’application de partage RMS qui applique automatiquement une protection générique à ces fichiers.

## Quand la migration à partir d’AD RMS sera-t-elle prise en charge ?
Initialement, Azure RMS ne prenait pas en charge la migration à partir d’un déploiement local de Rights Management, tel que AD RMS. Cette migration est désormais prise en charge.

Pour plus d’informations, voir [Migration d'AD RMS vers Azure Rights Management](../Topic/Migrating_from_AD_RMS_to_Azure_Rights_Management.md).

## Nous voulons utiliser BYOK avec Azure RMS mais avons appris que cette solution n’est pas compatible avec Exchange Online. Que conseillez-vous ?
Ne laissez pas cette limitation retarder votre déploiement d’Azure RMS. Si vous disposez d’Exchange Online et souhaitez utiliser la solution BYOK, nous vous recommandons de déployer maintenant Azure RMS en mode de gestion de clés par défaut dans lequel Microsoft génère et gère votre clé. De cette façon, vous bénéficiez de tous les avantages de la protection de vos fichiers et courriers électroniques importants, avec la possibilité de passer à BYOK ultérieurement (par exemple, si Exchange Online ne prend pas en charge BYOK).

Toutefois, si vos stratégies d’entreprise vous obligent à utiliser un module de sécurité matériel (HSM) sans lequel votre déploiement d’Azure RMS serait bloqué, vous pouvez déployer Azure RMS avec l’option BYOK, et des fonctionnalités RMS réduites pour Exchange. Pour plus d’informations, voir la section [Tarifs et restrictions BYOK](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md#BKMK_Pricing) dans la rubrique [Planification et implémentation de la clé de locataire Azure Rights Management](../Topic/Planning_and_Implementing_Your_Azure_Rights_Management_Tenant_Key.md).

## Il semble qu’une fonctionnalité que je recherche ne fonctionne pas avec les bibliothèques protégées SharePoint. Une prise en charge de ma fonctionnalité est-elle prévue ?
Actuellement, SharePoint prend en charge les documents protégés par les des bibliothèques protégées des services RMS, qui ne prennent pas en charge les modèles personnalisés, le suivi de document et d’autres fonctionnalités.  Pour plus d’informations, voir la section [SharePoint Online et OneDrive Entreprise : configuration de la gestion des droits relatifs à l'information](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharePointOnline) de la rubrique [Mode de prise en charge d'Azure Rights Management par les applications](../Topic/How_Applications_Support_Azure_Rights_Management.md).

Si vous êtes intéressé par une fonctionnalité spécifique qui n’est pas encore prise en charge, surveillez les annonces publiées sur le [blog de l’équipe RMS](http://blogs.technet.com/b/rms/).

## Comment configurer OneDrive Entreprise dans SharePoint Online, afin que les utilisateurs puissent partager en toute sécurité des fichiers avec des personnes à l’intérieur et à l’extérieur de l’organisation ?
Par défaut, en votre qualité d’administrateur Office 365, ce n’est pas vous qui configurez cela, mais les utilisateurs.

De la même manière qu’un administrateur de site SharePoint active et configure IRM pour une bibliothèque SharePoint dont il est propriétaire, OneDrive Entreprise a été conçu pour permettre aux utilisateurs d’activer et de configurer IRM pour leur propre bibliothèque OneDrive Entreprise.  Cependant, en utilisant PowerShell, vous pouvez le faire à leur place. Pour obtenir des instructions, développez la section [SharePoint Online et OneDrive Entreprise : configuration de la gestion des droits relatifs à l'information](../Topic/Configuring_Applications_for_Azure_Rights_Management.md#BKMK_SharePointOnline) de l’article [Configuration d'applications pour Azure Rights Management](../Topic/Configuring_Applications_for_Azure_Rights_Management.md).

## Avez-vous des conseils ou des astuces pour réussir le déploiement de RMS ?
Après avoir supervisé de nombreux déploiements et écouté nos clients, partenaires, consultants et ingénieurs du support technique, voici l’un des conseils les plus importants que nous pouvons vous donner : **Concevoir et déployer des stratégies de droits simples**.

Puisqu’Azure RMS permet de partager des fichiers en toute sécurité, vous pouvez faire preuve d’ambition concernant la portée de la protection de vos informations. Mais faites bien attention aux stratégies relatives aux droits. Pour de nombreuses organisations, la meilleure chose à faire est de prévenir la fuite des données en appliquant le modèle de stratégie de droits par défaut, qui restreint l’accès aux seuls membres de votre organisation. Bien sûr, vous pouvez être bien plus précis si vous devez empêcher des personnes d’imprimer, d’éditer, etc. Évitez néanmoins d’être trop précis pour des documents nécessitant un niveau de sécurité élevé. Au lieu d’implémenter ces stratégies restrictives le premier jour, adoptez une approche plus progressive.

## Quelles fonctionnalités peuvent ou ne peuvent pas être utilisées avec les différents abonnements Azure RMS ?
Pour les abonnements payants qui prennent en charge Azure RMS (Office 365, Azure RMS Premium et Enterprise Mobility Suite), il existe quelques différences pour ce qui est des fonctionnalités RMS prises en charge. Pour obtenir la liste de ces fonctionnalités, voir [Comparaison des offres Rights Management Services (RMS)](http://technet.microsoft.com/dn858608).

L’abonnement gratuit qui prend en charge Azure RMS (RMS for Individuals) prend en charge la consommation de contenu protégé par Azure RMS. Pour plus d’informations, voir [RMS for Individuals et Azure Rights Management](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md).

## Où trouver des informations techniques sur l’abonnement gratuit Azure RMS (RMS for Individuals), par exemple, son fonctionnement, la façon de prendre le contrôle des comptes et les domaines non utilisables ?
Les réponses à ces questions se trouvent dans la rubrique [RMS for Individuals et Azure Rights Management](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md).

## Comment récupérer l’accès à des fichiers protégés par un employé qui a quitté l’organisation ?
Utilisez la fonctionnalité de super utilisateur d’Azure RMS, qui permet à des utilisateurs autorisés d’exercer des droits de propriétaire sur toutes les licences d’utilisation accordées par le client RMS de votre organisation. Cette même fonctionnalité permet à des services autorisés d’indexer et d’inspecter des fichiers si nécessaire.

Pour plus d’informations, voir [Configuration de super utilisateurs pour Azure Rights Management et les services de découverte ou la récupération de données](../Topic/Configuring_Super_Users_for_Azure_Rights_Management_and_Discovery_Services_or_Data_Recovery.md).

## Est-ce que Rights Management peut empêcher les captures d’écran ?
Rights Management bloque les captures d’écran créées à partir de la plupart des outils de capture d’écran courants, ce qui permet d’éviter toute divulgation accidentelle ou imprudente d’informations confidentielles ou sensibles. Cependant, il existe plusieurs façons de partager des données affichées sur un écran, et la capture d’écran n’est qu’une méthode parmi tant d’autres. Par exemple, un utilisateur désireux de partager des informations affichées peut parfaitement les photographier avec son téléphone, recopier les données ou simplement les communiquer verbalement à un tiers.

Ces exemples montrent bien que la technologie à elle seule ne peut pas toujours empêcher les utilisateurs de partager les données qui ne devraient pas l’être. Même si Rights Management peut contribuer à protéger vos données importantes au moyen de stratégies d’autorisation et d’utilisation, cette solution de gestion des droits d’entreprise doit être assortie d’autres moyens de contrôle. Par exemple, vous pouvez mettre en place une sécurité physique, surveiller et soumettre à un contrôle strict les personnes autorisées à accéder aux données de votre organisation et investir dans la formation pour sensibiliser les utilisateurs à la question du partage de données.

## Où puis-je trouver des informations annexes sur Azure RMS (considérations juridiques, conformité, contrats de niveau de service, etc.) ?
Azure RMS prend en charge d’autres services et s’appuie également sur d’autres services. Si vous recherchez des informations relatives au service Azure RMS qui n’ont pas trait à son utilisation, consultez les ressources suivantes :

**Juridique et confidentialité :**

-   Pour plus d’informations sur le contrat Microsoft Azure : [Contrat Microsoft Azure](http://azure.microsoft.com/support/legal/subscription-agreement/)

-   Pour plus d’informations sur la confidentialité dans Microsoft Azure : [Déclaration de confidentialité de Microsoft Azure](http://azure.microsoft.com/support/legal/privacy-statement/)

**Sécurité, conformité et audit :**

Voir la section [Respect des obligations réglementaires, de conformité et de sécurité](../Topic/What_is_Azure_Rights_Management_.md#BKMK_RMScompliance) de la rubrique [Qu'est-ce qu'Azure Rights Management ?](../Topic/What_is_Azure_Rights_Management_.md). De plus :

-   Pour connaître les certifications externes pour Azure RMS : [Centre de gestion de la confidentialité Microsoft Azure](http://azure.microsoft.com/support/trust-center/)

-   Pour plus d’informations sur FIPS 140 : [Validation FIPS 140](https://technet.microsoft.com/library/security/cc750357.aspx)

**Contrats de niveau de service :**

-   Contrat de niveau de service pour Azure RMS, par pays : [Contrat de niveau de service](http://microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)

-   Contrat de niveau de service pour Azure Active Directory : [Contrats de niveau de service](http://azure.microsoft.com/support/legal/sla/)

**Documentation :**

-   Site de documentation sur Azure Active Directory : [Azure Active Directory](http://azure.microsoft.com/documentation/services/active-directory/)

-   Bibliothèque Azure Active Directory : [Azure Active Directory](http://msdn.microsoft.com/library/azure/jj673460.aspx)

-   Bibliothèque Office 365 : [Office 365](http://technet.microsoft.com/library/dn127064%28v=office.14%29.aspx)

## Que puis-je faire si ma question ne figure pas dans cette rubrique ?
Utilisez les liens et ressources répertoriés dans [Informations et support technique pour Azure Rights Management](../Topic/Information_and_Support_for_Azure_Rights_Management.md).

En outre, il existe des FAQ conçus pour les utilisateurs finaux :

-   [FAQ concernant l’application de partage Rights Management pour Windows](https://technet.microsoft.com/dn467883)

-   [FAQ relatif à l’application de partage Rights Management pour plateformes mobiles et Mac](https://technet.microsoft.com/dn451248)

-   [FAQ pour le suivi de document](http://go.microsoft.com/fwlink/?LinkId=523977)

Cette page de FAQ sera régulièrement actualisée. Les nouveautés seront répertoriées dans les avis de mise à jour mensuels de la documentation, sur le blog de l’[équipe Rights Management (RMS) de Microsoft](http://blogs.technet.com/b/rms/).

> [!TIP]
> Vous pouvez utiliser la [balise docs](http://blogs.technet.com/b/rms/archive/tags/docs/) sur le blog, pour repérer plus facilement ces avis de documentation.

## Voir aussi
[Prise en main d'Azure Rights Management](../Topic/Getting_Started_with_Azure_Rights_Management.md)

