---
description: na
keywords: na
title: Quick Start Tutorial for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1db923bf-7d19-4fdd-a413-bfeb58af5e03
---
# Didacticiel de d&#233;marrage rapide pour la Gestion des droits Azure
Ce didacticiel permet de tester rapidement Microsoft Azure Rights Management (également appelé Azure RMS) pour votre organisation en cinq étapes qui doivent prendre moins de 15 minutes. Vous allez activer le service, envoyer en toute sécurité un document confidentiel par courrier électronique à une personne d’une autre organisation, puis vous serez en mesure d’assurer le suivi de l’ouverture du document. Lorsque le document confidentiel est envoyé par courrier électronique, il est chiffré lors de son transfert et peut être lu uniquement par son destinataire à l’aide des autorisations définies par l’expéditeur.

![](../Image/AzRMS_QuickStartStepsAll.PNG)

Ce didacticiel est destiné aux administrateurs et consultants en informatique, afin de les aider à évaluer Azure Rights Management comme une solution de protection des informations pour une organisation. Dans un environnement de production, les instructions pour activer le service seraient effectuées par un administrateur, et les instructions utilisées pour envoyer le document seraient réalisées par les utilisateurs finaux. Les deux ensembles d’instructions sont inclus dans ce didacticiel pour illustrer le scénario de bout en bout consistant à envoyer en toute sécurité un document confidentiel à une personne d’une autre organisation. Si vous rencontrez des problèmes en suivant ce didacticiel, envoyez un courrier électronique à [AskIPTeam](mailto:askipteam@microsoft.com?subject=Having%20problems%20with%20the%20Quick%20Start%20tutorial) et nous vous aiderons.

Pour suivre ce didacticiel, vous avez besoin des éléments suivants :

-   Un abonnement prenant en charge Azure Rights Management. Il peut s’agit d’un abonnement payant ou d’évaluation. Si vous souhaitez utiliser le suivi des documents, qui est nécessaire pour l’étape 5 de ce didacticiel, votre abonnement doit prendre le suivi des documents en charge. Pour plus d’informations sur les options d’abonnement et pour obtenir des liens vers des versions d’essai gratuites, voir la section [Abonnements au cloud prenant en charge Azure RMS](../Topic/Requirements_for_Azure_Rights_Management.md#BKMK_SupportedSubscriptions) de la rubrique [Conditions requises pour Azure Rights Management](../Topic/Requirements_for_Azure_Rights_Management.md).

    Conseil : si vous avez besoin obtenir un abonnement, essayez de vous y prendre à l’avance, car ce processus peut parfois nécessiter un certain temps.

-   Un compte d’administrateur pour vous connecter au Centre d’administration Office 365 ou au portail Azure Classic, afin de pouvoir activer le service Rights Management. Ce compte doit également disposer d’une adresse de messagerie et d’un service de messagerie professionnel (par exemple, Exchange Online ou Exchange Server).

-   Un ordinateur exécutant Windows (au minimum Windows 7 SP1) et sur lequel Office 2016, Office 2013 ou Office 2010 est installé.

C’est parti !

## Étape 1 : activation du service Rights Management
![](../Image/AzRMS_QuickStartSteps1.PNG)

Même si vous avez un abonnement prenant en charge Azure Rights Management, le service est désactivé par défaut. Pour l’activer, vous pouvez utiliser le Centre d’administration Office 365 ou le portail Azure Classic :

-   Si vous avez un abonnement Office 365 qui inclut le service Gestion des droits Azure, ou bien un abonnement Office 365 qui l’exclut, mais que vous disposez d’un abonnement pour Azure RMS Premium, **utilisez le Centre d’administration Office 365**.

-   Si vous n’avez pas d’abonnement Office 365, **utilisez le portail Azure Classic**.

![](../Image/AzRMS_Tutorial_1_Screenshots.png)

#### Pour activer Rights Management à partir du centre d’administration Office 365

1.  Accédez au [portail Office 365](https://portal.office.com/) et connectez-vous avec votre compte professionnel ou scolaire.

2.  Si le Centre d’administration Office 365 ne s’affiche pas automatiquement, sélectionnez l’icône de lancement d’application dans l’angle supérieur gauche, puis choisissez **Admin**. La vignette **Admin** s’affiche uniquement pour les administrateurs Office 365.

    > [!TIP]
    > Pour obtenir l’aide du centre d’administration, voir [À propos du Centre d’administration Office 365 - Aide de l’administrateur](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547).

3.  Dans le volet gauche, développez **PARAMÈTRES DE SERVICE**.

4.  Cliquez sur **Rights Management**.

5.  Sur la page **RIGHTS MANAGEMENT**, cliquez sur **Gérer**.

6.  Dans la page **Rights Management**, cliquez sur **Activer**.

7.  Lorsque l’invite **Voulez-vous activer Rights Management ?** apparaît, cliquez sur **activer**.

Vous devriez maintenant voir **Rights management est activé**, ainsi que l’option de désactivation (vous devrez peut-être actualiser la page manuellement).

À ce stade, ne cliquez pas sur **fonctionnalités avancées**. Vous seriez redirigé vers le portail Azure Classic permettant de configurer des modèles qui sont superflus pour ce didacticiel. Choisissez plutôt de fermer le Centre d’administration Office 365.

#### Activation de Rights Management à partir du portail Azure

1.  Accédez au [portail Azure Classic](http://go.microsoft.com/fwlink/p/?LinkID=275081), puis connectez-vous.

2.  Dans le volet gauche, cliquez sur **Active Directory**.

3.  Dans la page **Active Directory**, cliquez sur **RIGHTS MANAGEMENT**.

4.  Sélectionnez le répertoire à gérer pour [!INCLUDE[aad_rightsmanagement_2](../Token/aad_rightsmanagement_2_md.md)], cliquez sur **ACTIVER**, puis confirmez votre action.

**Statut de Rights Management** doit désormais afficher l’état **Actif** et l’option **ACTIVER** est remplacée par **DÉSACTIVER**.

Bien que vous puissiez configurer d’autres options pour Rights Management dans le portail, celles-ci ne sont pas nécessaires pour ce didacticiel. Vous pouvez donc fermer le portail Azure Classic.

C’est tout ce que vous avez à faire pour cette première étape. Le service est activé : tous les utilisateurs de votre organisation peuvent maintenant commencer à protéger des documents importants et sensibles. Dans un environnement de production, vous souhaiterez peut-être limiter les personnes pouvant le faire au début, afin d’assurer un déploiement échelonné. Toutefois, ce n’est pas nécessaire pour ce didacticiel.

Bien que ce ne soit pas inclus dans cette rubrique, pour un déploiement de production, vous souhaiterez probablement configurer des modèles personnalisés. Les modèles facilitent l’application rapide des paramètres corrects lorsque les utilisateurs doivent protéger des fichiers. Lorsque vous activez Rights Management, vous obtenez automatiquement deux modèles par défaut que vous souhaiterez probablement compléter avec vos modèles personnalisés dans un environnement de production. Cependant, les modèles ne sont pas nécessaires pour ce didacticiel, vous pouvez donc passer à l’étape suivante.

|Pour en savoir plus|Informations supplémentaires|
|-----------------------|--------------------------------|
|Activation de Rights Management et contrôle des personnes pouvant protéger des fichiers et des messages électroniques lorsque le service est activé   →|[Activation d'Azure Rights Management](../Topic/Activating_Azure_Rights_Management.md)|
|Modèles par défaut et création de modèles personnalisés   →|[Configuration de modèles personnalisés pour Azure Rights Management](../Topic/Configuring_Custom_Templates_for_Azure_Rights_Management.md)|

## Étape 2 : installation de l’application de partage Rights Management
![](../Image/AzRMS_QuickStartSteps2.PNG)

L’application de partage Rights Management (également appelée « application de partage RMS ») n’est pas obligatoire pour Azure Rights Management, mais nous la recommandons pour tous les ordinateurs et appareils mobiles prenant en charge Azure Rights Management. L’application de partage RMS s’intègre aux applications Office via l’installation d’un complément Office, afin de permettre aux utilisateurs de protéger facilement des fichiers directement depuis le ruban. Elle permet également de protéger tout type de fichier en appliquant une protection générique pour les fichiers qui ne sont pas pris en charge en mode natif par Azure Rights Management, et propose un site de suivi de document pour suivre et révoquer les fichiers sous protection. Nous utiliserons le site de suivi de document plus loin dans ce didacticiel.

Cette application peut être téléchargée gratuitement et propose une installation par script pour les environnements de production. Dans le cadre de ce didacticiel, nous allons l’installer localement.

![](../Image/AzRMS_Tutorial_2_Screenshots.png)

#### Pour télécharger et installer l’application de partage Rights Management

1.  Accédez à la page [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) sur le site web Microsoft.

2.  Dans la section **Ordinateurs**, cliquez sur l’icône de l’**application RMS pour Windows** et enregistrez le fichier **Setup.exe** pour installer l’application de partage Microsoft Rights Management.

3.  Pour une installation locale, vous devez utiliser un compte d’administrateur pour exécuter le fichier Setup.exe qui a été téléchargé. Si vous êtes invité à continuer, cliquez sur **Oui**.

4.  Dans la page **Installer Microsoft RMS**, cliquez sur **Suivant**, puis attendez que l’installation se termine.

5.  Une fois l’installation terminée, cliquez sur **Redémarrer** si vous êtes invité à redémarrer votre ordinateur, ou sur **Fermer** pour terminer l’installation.

Vous êtes maintenant prêt à protéger les fichiers contenant des informations que vous souhaitez partager, mais uniquement avec les personnes que vous indiquez.

|Pour en savoir plus|Informations supplémentaires|
|-----------------------|--------------------------------|
|Installation locale de l’application de partage Rights Management pour Windows et instructions utilisateur   →|[Guide d’utilisation de l’application de partage Rights Management](http://technet.microsoft.com/library/dn339006.aspx)|
|Installation par script de l’application de partage Rights Management pour Windows et informations techniques   →|[guide de l’administrateur de l’application de partage Rights Management](http://technet.microsoft.com/library/dn339003.aspx)|
|Pour comprendre la différence entre la protection native et la protection générique   →|[Quelle est la différence entre la protection générique et la protection intégrée (native) ?](https://technet.microsoft.com/library/dn574738.aspx)|

## Étape 3 : envoi par courrier électronique du document que vous souhaitez protéger
![](../Image/AzRMS_QuickStartSteps3.PNG)

Pour cette étape, commencez par créer et enregistrer un document Word qui représente le document que vous souhaitez protéger, puis nommez-le **Confidential.docx**. Dans le cadre de ce didacticiel, faites en sorte que le document contienne du texte, quel qu’il soit, afin de pouvoir confirmer plus facilement que le destinataire autorisé a pu le lire. Par exemple, vous pouvez saisir le texte suivant : **Si vous pouvez lire ce texte à partir de la pièce jointe de votre courrier électronique, l’expéditeur a réussi à partager un fichier protégé par Azure RMS.**

Ensuite, vous pouvez partager en toute sécurité ce document par courrier électronique.

![](../Image/AzRMS_Tutorial_3_Screenshots.png)

#### Partage en toute sécurité d’un document par courrier électronique

1.  Dans Outlook, créez un message et joignez le fichier que vous venez de créer.

2.  Dans la zone **À**, saisissez au moins une adresse de messagerie professionnelle. Veillez à spécifier une adresse de messagerie professionnelle telle que **janetm@contoso.com** ou **p.dover@fabrikam.com**, car le service Gestion des droits Azure ne prend actuellement pas en charge les adresses électroniques personnelles proposées par votre fournisseur Internet, que vous pourriez utiliser à titre privé. Le fait de savoir si le destinataire possède également Azure Rights Management n’est pas important.

3.  Indiquez un objet, tel que **Document confidentiel**, puis saisissez un bref message, tel que **Merci de lire ce document et de ne pas le partager.**

4.  Puis, dans l’onglet **Message** du groupe **RMS**, cliquez sur **Partage protégé**, puis sur**Partage protégé** à nouveau :

5.  Dans la boîte de dialogue **Partage protégé** :

    1.  Sélectionnez **Visionneuse – Affichage uniquement**.

        Cela signifie que les destinataires seront en mesure d’afficher le document, mais pas de le modifier ou de l’imprimer.

    2.  Sélectionnez **M’avertir par message électronique lorsque quelqu’un essaie d’ouvrir ces documents**.

        Vous recevrez une notification par courrier électronique chaque fois que les destinataires ou d’autres personnes tenteront d’ouvrir la pièce jointe, par exemple, si votre destinataire transfère le courrier à un collègue. Dans ce dernier scénario, vous verrez que l’accès a été refusé, et dans les détails de l’utilisateur, vous pouvez décider d’envoyer à cette personne une copie du document qu’elle peut ouvrir.

    3.  Sélectionnez **M’autoriser à révoquer de suite l’accès à ces documents**.

        Cette option nécessite que les destinataires disposent d’une connexion Internet chaque fois qu’ils ouvrent la pièce jointe, mais le point positif réside dans le fait que si vous révoquez ultérieurement le document, ils ne seront pas en mesure de l’ouvrir lors de leur prochaine tentative d’ouverture. Si vous ne sélectionnez pas cette option, il est possible que les destinataires puissent ouvrir le document, même sans connexion Internet. Toutefois, si vous révoquez ultérieurement le document, sa prise d’effet peut survenir après un certain délai.

    4.  Cliquez sur **Envoyer maintenant**.

        Le courrier électronique avec une pièce jointe est envoyé aux adresses de messagerie que vous avez indiquées. En plus de votre message électronique, les destinataires reçoivent des instructions sur la façon de lire le document joint protégé par Azure Rights Management.

Maintenant que vous avez envoyé votre document protégé, vous pouvez demander à vos destinataires de l’ouvrir dès qu’ils le reçoivent. Ne fermez pas Outlook, car nous allons l’utiliser à nouveau lors de la dernière étape pour suivre la pièce jointe.

|Pour en savoir plus|Informations supplémentaires|
|-----------------------|--------------------------------|
|Instructions détaillées et méthodes alternatives pour protéger des fichiers que vous partagez par courrier électronique   →|[Protection d’un fichier que vous partagez par courrier électronique à l’aide de l’application de partage Rights Management](https://technet.microsoft.com/library/dn574735.aspx)|
|Options de la boîte de dialogue **partage protégé** →|[Options de boîte de dialogue pour l’application de partage Rights Management](https://technet.microsoft.com/library/dn574738.aspx)|

## Étape 4 : demande au destinataires d’ouvrir le document envoyé par courrier électronique
![](../Image/AzRMS_QuickStartSteps4.PNG)

Vos destinataires peuvent utiliser de nombreux appareils pour lire le document protégé que vous avez envoyé en pièce jointe d’un courrier électronique. Les appareils incluent les iPad, les iPhone, les tablettes et les téléphones Android, les ordinateurs Mac, ainsi que les ordinateurs Windows.

Demandez-leur de lire le message électronique que vous leur avez envoyé. Avant de voir votre message électronique, ils verront le message suivant :

**L’expéditeur a protégé les pièces jointes avec Microsoft RMS. Vous devez** [vous enregistrer](http://aka.ms/rms) **pour les ouvrir.**

Lorsqu’ils cliquent sur le lien, ils sont redirigés vers les instructions pour installer l’application de partage RMS et pour se connecter à un compte gratuit, si nécessaire. Le compte gratuit leur accorde un abonnement à RMS for individuals, et garantit que les utilisateurs autorisés pourront toujours lire un document protégé, même si leur organisation ne dispose pas d’Azure RMS. Ils peuvent ensuite lire les pièces jointes protégées à l’aide des instructions suivantes.

![](../Image/AzRMS_Tutorial_4_Screenshots.png)

#### Affichage de la pièce jointe du document protégé

1.  Étant donné qu’Azure Rights Management a protégé un document Word, il existe deux pièces jointes au courrier électronique. Il s’agit en fait de deux versions du même fichier, mais avec différentes extensions. Ouvrez la version avec l’extension de nom de fichier **.ppdf** (**Confidential.ppdf**).

    Si vous disposez sur votre appareil d’une version d’[Office prenant en charge Rights Management](https://technet.microsoft.com/library/dn655136.aspx), vous pouvez ouvrir l’autre version du fichier (**Confidential.docx**) afin qu’il s’ouvre dans Word.

2.  Si vous êtes invité à saisir votre nom d’utilisateur et votre mot de passe, indiquez votre nom d’utilisateur dans le même format que l’adresse de messagerie utilisée pour vous envoyer le courrier électronique et la pièce jointe. Par exemple, **janetm@contoso.com** ou **p.dover@fabrikam.com**. En ce qui concerne votre mot de passe, saisissez celui que vous avez fourni lors de votre inscription à RMS for individuals. Si votre organisation a Azure RMS, entrez votre mot de passe professionnel habituel.

Le document s’ouvre et vous pouvez maintenant lire le contenu. Par exemple, il peut contenir le message **Si vous pouvez lire ce texte à partir de la pièce jointe de votre courrier électronique, l’expéditeur a réussi à partager un fichier protégé par Azure RMS.** Étant donné que le document est en lecture seule, vous ne pouvez pas modifier son contenu.

Vous pouvez éventuellement demander à votre destinataire de transférer le courrier électronique à d’autres personnes que vous n’avez pas incluses dans votre courrier d’origine. Même si ces personnes travaillent pour une organisation qui dispose d’Azure Rights Management ou s’il demandent un abonnement à RMS for individuals, ils ne seront pas en mesure d’ouvrir la pièce jointe. Lorsqu’elles sont invitées à saisir leur nom d’utilisateur, l’accès au document leur est refusé.

Maintenant que le destinataire a ouvert la pièce jointe et l’a éventuellement transférée à une autre personne, attendez-vous à recevoir une notification par courrier électronique qui vous informe de cette activité. Toutefois, les courriers électroniques se perdent facilement au fil du temps. Afin d’assurer un meilleur suivi des personnes ayant accédé à votre document, utilisez le site de suivi de document (sujet traité dans la dernière étape de ce didacticiel).

|Pour en savoir plus|Informations supplémentaires|
|-----------------------|--------------------------------|
|Instructions détaillées pour afficher les fichiers protégés par Azure Rights Management   →|[Affichage et utilisation des fichiers qui ont été protégés par Rights Management](https://technet.microsoft.com/library/dn574741.aspx)|
|Abonnement gratuit RMS for individuals   →|[RMS for Individuals et Azure Rights Management](../Topic/RMS_for_Individuals_and_Azure_Rights_Management.md)|
|Deux versions du fichier joint au courrier électronique   →|[Quel est le fichier .ppdf créé automatiquement ?](https://technet.microsoft.com/library/dn574738.aspx)|

## Étape 5 : suivi de votre document protégé
![](../Image/AzRMS_QuickStartSteps5.PNG)

> [!NOTE]
> Pour cette étape, vous devez disposer d’un abonnement qui prend en charge le suivi de document. Pour vérifier si votre abonnement inclut le suivi de document, voir la [comparaison des différentes offres de services Rights Management (RMS)](https://technet.microsoft.com/dn858608.aspx).

Cette étape est facultative, mais la plupart des utilisateurs souhaitent savoir si la pièce jointe qu’ils ont envoyée a été ouverte, à quel moment et aussi à quel endroit. Par exemple :

-   Vous attendez une réponse de la part d’une personne à une heure donnée, et vous pouvez voir sur le site de suivi de document qu’elle n’a pas ouvert le document, bien que l’échéance approche. Vous lui envoyez un courrier électronique de suivi ou l’appelez en guise de rappel.

-   Après avoir vu que le document a été ouvert, vous assurez le suivi et demandez à la personne si elle a des questions ou besoin d’informations supplémentaires.

![](../Image/AzRMS_Tutorial_5_Screenshots.png)

#### Suivi du document protégé

1.  Dans Outlook, dans l’onglet **Accueil** du groupe **RMS**, cliquez sur **Suivre l’utilisation**.

2.  Si la page de **protection et partage de vos conditions d’utilisation** apparaît, cliquez sur **Se connecter** et indiquez à nouveau votre nom d’utilisateur et votre mot de passe.

3.  Sur la page **Vos documents partagés**, vous verrez le document que vous avez joint au courrier électronique, **Confidential.docx**. À ce stade, il s’agit du seul fichier affiché, mais la liste s’allongera à mesure que vous partagerez des fichiers.

    Sur cette page, vous pouvez voir le moment où vous avez partagé le document (moment de l’envoi du courrier électronique contenant la pièce jointe protégée), la date de la dernière activité et le nom du destinataire auquel vous avez envoyé le courrier. Cliquez sur le nom du document pour plus de détails.

4.  Sur la nouvelle page qui porte le nom du fichier sur lequel vous avez cliqué, vous pouvez voir les détails du résumé de ce document, ainsi qu’une liste d’autres options disponibles pour le document (**Liste**, **Chronologie**, **Carte**, **Paramètres**).

    Cliquez sur chaque option pour explorer les différentes façons de suivre votre document protégé. Sinon, sur la page **Résumé**, cliquez sur **Ouvrir dans Excel** pour exporter les informations dans une feuille de calcul, ou cliquez sur **Révoquer l’accès** pour cesser de partager le document.

Vous pouvez revenir sur ce site pour suivre les autres activités de votre document protégé ou révoquer son accès si nécessaire. Vous pouvez même accéder au site à partir de votre appareil mobile ou de votre tablette, à l’aide d’un navigateur et du lien suivant : [suivi de document](http://go.microsoft.com/fwlink/?LinkId=529562)

|Pour en savoir plus|Informations supplémentaires|
|-----------------------|--------------------------------|
|Instructions détaillées pour le suivi de vos documents   →|[Suivi et révocation de vos documents lorsque vous utilisez l’application de partage RMS](https://technet.microsoft.com/library/dn986611.aspx)|
|Vidéo de deux minutes qui explique et présente le suivi de document   →|[Révocation et suivi de document Azure RMS](http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation)|
|Dépannage et questions des clients   →|[FAQ pour le suivi de document](https://technet.microsoft.com/dn947488)|

## Étapes suivantes
Ce didacticiel vous a présenté seulement un scénario dans lequel Azure RMS peut vous aider à protéger vos données. Pour découvrir d’autres cas d’utilisation courants, voir la section [Azure RMS en action](https://technet.microsoft.com/library/jj585026.aspx) de l’article [Qu'est-ce qu'Azure Rights Management ?](../Topic/What_is_Azure_Rights_Management_.md). Dans cet article, il existe d’autres sections qui peuvent vous être utiles, telles que le fonctionnement d’Azure RMS et les problèmes professionnels qu’il peut résoudre.

Si vous êtes prêt à déployer Azure RMS, voir [feuille de route pour le déploiement d'Azure Rights Management](../Topic/Azure_Rights_Management_Deployment_Roadmap.md) pour connaître les étapes de déploiement et accéder aux liens pointant vers des instructions.

## Voir aussi
[Prise en main d'Azure Rights Management](../Topic/Getting_Started_with_Azure_Rights_Management.md)

