---
description: na
keywords: na
title: Dialog box options for the Rights Management sharing application
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 7b91ab30-6363-4929-bcbd-4dfbd05f644a
---
# Options de bo&#238;te de dialogue pour l&#39;application de partage Rights&#160;Management
Ces informations vous aident à spécifier les options des boîtes de dialogue **Ajouter une protection** ou **Partage protégé** de l'application de partage RMS. Ces boîtes de dialogue s'affichent quand vous voulez [protéger un fichier à partager](http://technet.microsoft.com/library/dn574735.aspx) ou [protéger un fichier en place](http://technet.microsoft.com/library/dn574733.aspx) et choisissez des autorisations personnalisées.

> [!IMPORTANT]
> Si les options diffèrent de celles présentées ici, vous ne disposez probablement pas de la dernière version de l'application de partage installée. Vous pouvez télécharger la version la plus récente à partir de la page [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970).
> 
> Comment savoir si vous disposez de la dernière version ? Recherchez l'**application de partage Microsoft Rights Management** répertoriée dans Programmes et fonctionnalités, puis vérifiez le numéro de version correspondant. Pour pouvoir afficher et utiliser les options du tableau, la version doit être au moins **1.0.1770.0**. Vous pouvez vérifier le numéro de la dernière version dans la page de téléchargement.

Outre les options que vous pouvez choisir, vous pourriez également vous interroger sur les points suivants :

-   [Qu'est-ce que le fichier .ppdf créé automatiquement ?](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md#BKMK_PPDF)

-   [Quelle est la différence entre la protection générique et la protection intégrée (native) ?](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md#BKMK_GenericNative)

|Option|Description|
|----------|---------------|
|**UTILISATEURS**|Si vous n'avez pas encore spécifié d'adresse de messagerie à partir d'Outlook, tapez les adresses de personnes qui doivent pouvoir ouvrir le fichier.<br /><br />Si votre organisation utilise la version locale de Rights Management (AD RMS), les adresses de messagerie que vous pouvez spécifier sont limitées aux personnes de votre organisation. Dans ce cas, si vous tentez de spécifier des adresses de messagerie externes, un message s'affiche, indiquant que la configuration de votre organisation n'autorise le partage de contenu protégé qu'à l'intérieur de celle-ci. En revanche, si votre organisation utilise Azure RMS, ces adresses de messagerie peuvent également être celles de personnes d'une autre organisation.<br /><br />Par exemple, janetm@contoso.com ou p.dover@fabrikam.com.|
|**Protection générique**|Si cette option est sélectionnée, cela signifie que le fichier que vous avez sélectionné ne peut pas être protégé en mode natif. Pour plus d'informations, voir [Quelle est la différence entre la protection générique et la protection intégrée (native) ?](../Topic/Dialog_box_options_for_the_Rights_Management_sharing_application.md#BKMK_GenericNative) dans cette rubrique.|
|**Visionneuse – Affichage uniquement**<br /><br />**Réviseur – Affichage et modification**<br /><br />**Co-auteur – Affichage, modification, copie et impression**<br /><br />**Copropriétaire – Toutes les autorisations** **Note:** Toutes ces options sont associées à une icône circulaire placée devant leur nom, qui représente un globe terrestre. Cette icône est utilisée parce que, généralement, vous sélectionnez l'une de ces options lorsque vous envoyez votre pièce jointe à une personne d'une autre organisation.|Sélectionnez l'une des options suivantes si vous souhaitez définir les droits de votre document protégé. Cliquez sur chaque option pour en afficher la description.<br /><br />Lorsque vous choisissez l'une de ces options, seules les personnes que vous spécifiez dans **UTILISATEURS** disposent des droits que vous définissez pour ouvrir et utiliser le document. Par exemple, si elles transfèrent celui-ci à quelqu'un d'autre, le document ne s'ouvre pas.|
|Modèles de stratégie que votre administrateur configure.<br /><br />Par exemple, si le nom de votre entreprise est Contoso, Ltd : **Contoso, Ltd - Affichage confidentiel uniquement** **Note:** Toutes ces options sont associées à une icône carrée placée devant leur nom, qui représente un immeuble de bureaux. Cette icône est utilisée parce que, généralement, vous sélectionnez l'une de ces options lorsque vous envoyez votre pièce jointe à une personne de votre organisation.|Lorsque vous partagez un document avec des personnes travaillant pour votre organisation, vous voyez les modèles de stratégie disponibles que votre administrateur configure. Choisissez l'un de ceux-ci quand le document ne doit pas être partagé à l'extérieur de votre organisation.<br /><br />Lorsque vous choisissez l'une de ces options, votre administrateur définit les droits relatifs au document et qui peut l'ouvrir.|
|**Ces documents expirent le**|Sélectionnez cette option uniquement pour des fichiers soumis à une contrainte de temps que les utilisateurs que vous avez sélectionnés doivent pouvoir ouvrir après une date que vous spécifiez. Vous pouvez toujours ouvrir le fichier d'origine mais, après minuit (dans votre fuseau horaire), le jour spécifié, d'autres utilisateurs ne peuvent plus l'ouvrir.<br /><br />Cette option n'est pas disponible si vous sélectionnez un modèle de stratégie que votre administrateur configure.|
|**M'avertir lorsqu'une personne tente d'ouvrir ces documents**|**Note:** Cette option est actuellement en version préliminaire.<br />Sélectionnez-la si vous souhaitez recevoir des notifications par courrier électronique chaque fois que quelqu'un tente d'ouvrir le document que vous protégez. Le message électronique indique qui a tenté d'ouvrir le document, à quel moment et si la tentative a réussi.<br /><br />Cette option est disponible uniquement si votre organisation utilise Azure RMS. Si votre organisation utilise la version locale de Rights Management (AD RMS), cette option ne s'affiche pas.|
|**M'autoriser à révoquer de suite l'accès à ces documents.**|Choisissez cette option si vous pensez que vous pourriez être amené ultérieurement à devoir révoquer l'accès aux documents via le site de suivi de document, avec effet immédiat de la révocation. Toutefois, le choix de cette option signifie que, même si le document n'est pas révoqué, les utilisateurs ont toujours besoin d'une connexion Internet pour le lire chaque fois qu'ils y accèdent. Il peut y avoir des situations où les utilisateurs ne peuvent pas connecter leur appareil à Internet et ne peuvent donc pas lire votre document comme prévu.<br /><br />Si vous ne choisissez pas cette option, vous pouvez toujours révoquer un document ultérieurement via le site de suivi de document. Toutefois, les utilisateurs n'ayant pas toujours besoin d'une connexion Internet pour lire le document, ils ne sont pas immédiatement informés de la révocation de celui-ci et peuvent continuer à le lire jusqu'à leur prochaine authentification auprès d'Azure RMS. Par défaut, la durée maximale pendant laquelle un utilisateur peut continuer à lire un document protégé que vous avez révoqué est de 30 jours, mais un administrateur peut allonger ou raccourcir cette période.<br /><br />Cette option est disponible uniquement si votre organisation utilise Azure RMS. Si votre organisation utilise la version locale de Rights Management (AD RMS), cette option ne s'affiche pas.|

## <a name="BKMK_GenericNative"></a>Quelle est la différence entre la protection générique et la protection intégrée (native) ?

-   Lorsque vous **appliquez à un fichier une protection générique**, les personnes non autorisées ne peut pas l'ouvrir. En revanche, des personnes autorisées ayant ouvert le fichier peuvent ensuite le transférer, non protégé, à d'autres personnes, ou l'enregistrer dans un emplacement accessible à d'autres. Bien qu'elles voient s'afficher un message leur indiquant les autorisations dont elles disposent sur le fichier et les invitant à respecter les restrictions qui y sont associées, cette protection n'est nullement contraignante. En outre, lorsque vous appliquez une protection générique à un fichier, vous ne pouvez pas moduler l'autorisation d'accès à celui-ci. Par exemple, vous ne pouvez pas restreindre l'utilisation du contenu au seul affichage ou empêcher son impression.

    > [!NOTE]
    > Un fichier faisant l'objet d'une protection générique a toujours l'extension de nom de fichier **.pfile**.

-   Par contre, lorsque vous utilisez la **protection intégrée (native)** de Rights Management avec des applications qui la prennent en charge (par exemple, des fichiers Office), la protection s'applique au fichier, même si celui-ci est transféré à quelqu'un d'autre ou enregistré dans un autre emplacement. Et lorsque vous protégez un fichier de cette manière, vous pouvez utiliser des autorisations restrictives, telles que la lecture seule, ou l'édition mais non l'impression ou la copie. Par exemple, vous pouvez sélectionner **Visionneuse – Affichage uniquement** pour empêcher toute modification, impression ou copie du fichier.

Pour plus d'informations techniques, voir la section [Niveaux de protection : natif et générique](../Topic/Rights_Management_sharing_application_administrator_guide.md#BKMK_LevelsofProtection) de [guide de l'administrateur de l'application de partage Rights Management](../Topic/Rights_Management_sharing_application_administrator_guide.md).

## <a name="BKMK_PPDF"></a>Qu'est-ce que le fichier .ppdf créé automatiquement ?

-   Lorsque vous partagez un fichier protégé par courrier électronique (partage protégé), l'application de partage RMS crée automatiquement une version **.ppdf** du fichier pour Word, Excel, PowerPoint ou PDF. Il s'agit d'une version protégée en lecture seule du fichier que seules les personnes autorisées peuvent ouvrir. Cela garantit que les destinataires peuvent toujours lire la pièce jointe, même s'ils utilisent un appareil mobile dépourvu d'une application prenant en charge Rights Management en mode natif. Pour autant que ces personnes disposent de l'application de partage RMS, elles peuvent lire la pièce jointe.

    Dans ce scénario, contrairement à la protection générique, la restriction d'utilisation est appliquée. Le destinataire ne peut pas enregistrer cette version du fichier et, s'il transfère la pièce jointe à quelqu'un d'autre, les restrictions d'origine continuent à s'appliquer au document. Seules les personnes autorisées à accéder au document protégé peuvent ouvrir celui-ci.

    > [!NOTE]
    > Un fichier .ppdf est créé automatiquement lorsque vous effectuez un partage protégé (partage par courrier électronique), mais ne l'est pas lorsque vous protégez sur place.

## Exemples et autres instructions
Pour obtenir des exemples et des instructions concernant l'utilisation de l'application de partage Rights Management, voir les sections suivantes dans le Guide d'utilisation de l'application de partage Rights Management :

-   [Exemples d’utilisation de l’application de partage RMS](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingExamples)

-   [Que souhaitez-vous faire ?](../Topic/Rights_Management_sharing_application_user_guide.md#BKMK_SharingInstructions)

## Voir aussi
[Guide d’utilisation de l’application de partage Rights Management](../Topic/Rights_Management_sharing_application_user_guide.md)

