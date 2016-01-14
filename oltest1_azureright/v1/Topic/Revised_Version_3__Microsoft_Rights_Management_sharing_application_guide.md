---
description: na
keywords: na
title: Revised Version 3: Microsoft Rights Management sharing application guide
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.assetid: 846f1895-1daf-4164-8cf6-e4a691384c41
robots: noindex,nofollow
---
# Version r&#233;vis&#233;e&#160;3&#160;: Guide de l&#39;application de partage Microsoft Rights Management
Utilisez ce guide pour l'application de partage Microsoft Rights Management (RMS) pour Windows afin de vous aider à empêcher que des images et documents importants ne soient accessibles à des personnes non autorisées à les voir, même si vous les envoyez par courrier électronique ou les enregistrez sur un autre appareil. De même, cette application vous permet d'ouvrir et d'utiliser des fichiers protégés par d'autres personnes à l'aide de la même technologie Rights Management.

Cette application de partage fournit cette protection pour vos fichiers de plusieurs manières :

-   Elle ajoute des fonctionnalités à l'Explorateur de fichiers (également connu sous le nom d'Explorateur Windows dans Windows 7 et versions antérieures) afin que, quand vous gérez des fichiers dans un dossier, vous puissiez facilement protéger un seul fichier, plusieurs fichiers en bloc ou tous les fichiers dans un dossier.

-   Elle fournit une protection pour tous les types de fichiers et comprend une visionneuse intégrée pour les types de fichiers texte et image couramment utilisés.

-   Elle ajoute le bouton **Partager un fichier protégé** à la barre d'outils Microsoft Office pour Word, PowerPoint et Excel.

Vous avez uniquement besoin d'un ordinateur qui exécute Windows 7 ou Windows 8 et d'un compte d'administrateur local pour installer l'application de partage RMS. Ensuite, téléchargez et installez cette application gratuite de Microsoft.

Si vous avez des questions qui ne sont pas traitées dans ce guide, voir [Forum aux questions sur l'application de partage Microsoft Rights Management pour Windows](http://go.microsoft.com/fwlink/?LinkId=303971).

## Exemples d'utilisation de l'application de partage RMS
Voici quelques exemples de la façon dont vous pouvez utiliser l'application de partage RMS pour protéger vos fichiers.

|Scénario|Solution utilisant l'application de partage RMS|
|------------|---------------------------------------------------|
|**Je souhaite copier en toute sécurité un document confidentiel de l'entreprise sur un autre appareil**<br /><br />Vous utilisez votre PC pour travailler sur un document stratégique confidentiel de l'entreprise et vous souhaitez le copier sur une clé USB afin de pouvoir continuer à travailler dessus quand vous quittez le bureau et n'avez pas accès au réseau d'entreprise.|L'application de partage RMS est installée à la fois sur votre PC et sur votre ordinateur portable. L'Explorateur de fichiers sur votre PC vous permet de protéger le fichier à l'aide d'un modèle pour qu'il ne soit pas accessible à des personnes extérieures à votre entreprise. Vous copiez ensuite le fichier sur votre clé USB, branchez la clé à votre ordinateur portable et continuez à travailler sur le document. Si vous perdez la clé USB ou que votre portable est volé, aucune personne extérieure à votre entreprise ne peut accéder au document.|
|**Je souhaite partager en toute sécurité des informations financières avec quelqu'un de confiance qui est externe à mon organisation**<br /><br />Vous travaillez avec une entreprise partenaire et vous voulez envoyer par courrier électronique une feuille de calcul Excel qui contient les chiffres des prévisions de ventes. Vous voulez que ce partenaire puisse afficher les chiffres, mais pas les modifier.|Vous utilisez le bouton **Partager un fichier protégé** sur le ruban dans Excel, tapez les adresses de messagerie des deux personnes avec lesquelles vous travaillez dans l'entreprise partenaire, sélectionnez **Observateur** sur le curseur, puis cliquez sur **Envoyer**.<br /><br />Quand le courrier électronique arrive à l'entreprise partenaire, seuls les destinataires du courrier électronique peuvent afficher la feuille de calcul, mais ils ne peuvent pas l'enregistrer, la modifier, l'imprimer ni la transférer.|
|**Je souhaite envoyer en toute sécurité un schéma technique par courrier électronique à une personne qui utilise un appareil iOS**<br /><br />Votre entreprise utilise une application d'ingénierie personnalisée et vous voulez envoyer par courrier électronique un schéma hautement confidentiel à un collègue qui consulte régulièrement ses messages électroniques sur son appareil iOS.|Vous utilisez l'Explorateur de fichiers pour cliquer avec le bouton droit sur le fichier et pour sélectionner **Partager un fichier protégé**. L'application de partage RMS reconnaissant que l'extension de fichier ne provient pas d'une application qui prend en charge RMS en mode natif, quand elle joint le fichier à un message électronique, elle le convertit automatiquement en fichier protégé de façon générique et sélectionne automatiquement l'option **Autoriser la consommation avec les périphériques**.<br /><br />Le destinataire reçoit le message électronique sur son appareil iOS, clique sur le lien dans le message électronique qui lui indique comment télécharger l'application de partage RMS, installe la version pour les appareils iOS et affiche ensuite le schéma.|
|**Mon entreprise n'utilise pas Rights Management, mais j'ai reçu un message électronique avec une pièce jointe qui est protégée par RMS**<br /><br />L'expéditeur du courrier électronique est quelqu'un à qui vous faites confiance, car vous avez traité avec lui par le passé et vous pensez qu'il vous envoie des informations sur une nouvelle opportunité commerciale potentielle.|Vous cliquez sur le lien dans le message électronique qui vous indique comment télécharger l'application de partage RMS pour votre ordinateur, l'installer et vous abonner à RMS pour les particuliers. Microsoft confirme que votre organisation ne dispose pas d'un abonnement à Office 365, vous envoie un courrier électronique pour effectuer le processus d'abonnement gratuit. Vous vous connectez ensuite avec votre nouveau compte. Vous pouvez ensuite ouvrir la pièce jointe pour en savoir plus sur la nouvelle opportunité professionnelle.|

## <a name="BKMK_Install"></a>Comment télécharger et installer l'application de partage RMS
> [!IMPORTANT]
> Vous devez disposer d'un compte d'administrateur local pour installer l'application de partage RMS. Si vous ne vous connectez pas en tant qu'administrateur local, vous pouvez utiliser l'option **Exécuter en tant qu'administrateur** quand vous exécutez Setup.exe à l'étape 3.

Pour installer l'application de partage RMS, procédez comme suit :

1.  Accédez à la page [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) sur le site web Microsoft.

2.  Dans la section **Ordinateurs**, cliquez sur l'icône **Application RMS pour Windows** et enregistrez le package d'installation de l'application de partage Microsoft Rights Management sur votre ordinateur.

3.  Double-cliquez sur le fichier compressé qui a été téléchargé, puis sur **setup.exe**. Si vous êtes invité à continuer, cliquez sur **Oui**.

4.  Dans la page **Installation de Microsoft RMS**, cliquez sur **Suivant** et attendez que l'installation se termine.

5.  Une fois l'installation terminée, cliquez sur **Redémarrer** pour redémarrer votre ordinateur et terminer l'installation. Vous pouvez également cliquer sur **Fermer** et redémarrer votre ordinateur plus tard pour terminer l'installation.

Vous êtes maintenant prêt à protéger vos fichiers ou à lire des fichiers protégés par d'autres utilisateurs.

## <a name="BKMK_UsingMSRMSApp"></a>Que voulez-vous faire ?
Utilisez les instructions suivantes pour vous aider à utiliser des fichiers protégés.

### <a name="BKMK_CreatePTXT"></a>Créer un fichier texte protégé
Vous pouvez convertir un fichier texte standard (.txt) en un fichier protégé avec l'extension de fichier .ptxt.

##### Pour créer un fichier texte protégé (.ptxt)

1.  Dans l'Explorateur de fichiers, cliquez avec le bouton droit dans un dossier, cliquez sur **Nouveau**, puis sur **Document texte**.

2.  Renommez le fichier (par exemple Exemple.txt).

3.  Double-cliquez sur le fichier pour l'ouvrir dans le Bloc-notes.

4.  Dans le Bloc-notes, ajoutez quelques lignes de texte au fichier, puis enregistrez-le. Vous pouvez utiliser le texte suivant comme exemple de texte.

    ```
    This is a sample text file.
    This is a sample text file.
    This is a sample text file.
    This is a sample text file. 
    This is a sample text file.
    This is a sample text file.
    ```

5.  Cliquez avec le bouton droit sur le fichier, cliquez sur **Protéger sur place** et sélectionnez un modèle dans la liste. S'il s'agit de la première fois que vous avez utilisé l'application de partage RMS, vous devez d'abord sélectionner **Protection de la société**, qui télécharge les modèles pour votre organisation.

6.  Dans l'écran **Application de partage Microsoft Rights Management**, confirmez la stratégie que vous souhaitez appliquer, cliquez sur **Appliquer** et, une fois que le fichier est protégé, cliquez sur **Fermer**.

### <a name="BKMK_ViewPTXT"></a>Afficher un fichier texte protégé (.ptxt) ou un fichier image protégé
Pour afficher un fichier texte protégé (.ptxt), dans l'Explorateur de fichiers, double-cliquez sur le fichier (par exemple Exemple.ptxt). Des informations d'identification peuvent vous être demandées. Quand le fichier s'ouvre, la stratégie de protection du fichier s'affiche en haut du fichier.

Vous affichez et ouvrez des images protégées de la même façon.

### <a name="BKMK_CreatePFILE"></a>Créer un fichier protégé générique
Utilisez le format de fichier de protection générique (.pfile) pour offrir un niveau de protection générique pour les types de fichiers qui ne sont pas directement pris en charge par l'application de partage RMS ni d'autres applications qui fournissent une protection de type RMS intégrée. Vous pouvez utiliser la page [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970) sur le site web Microsoft pour vérifier rapidement les applications qui prennent en charge une protection intégrée RMS.

Par exemple, comme Microsoft Visio ne prend actuellement pas en charge une protection intégrée pour les services RMS, vous pouvez utiliser une protection générique pour les fichiers .vsd que vous créez avec Microsoft Visio.

> [!TIP]
> Quelle est la différence entre une protection intégrée (native) et une protection générique ?
> 
> -   Quand vous protégez un fichier de façon générique, les personnes non autorisées ne peuvent pas ouvrir le fichier. Toutefois, une fois que les personnes autorisées ont ouvert le fichier, elles peuvent ensuite le transférer sans qu'il ne soit protégé à d'autres personnes ou l'enregistrer à un emplacement accessible à d'autres utilisateurs. Un message s'affiche en haut du fichier qui leur indique les autorisations dont elles disposent sur le fichier et elles sont invitées à les respecter, mais cette protection ne peut pas être appliquée. En outre, quand vous protégez un fichier de façon générique, vous ne pouvez pas ajouter plus de restrictions que les autorisations n'en ont déjà. Par exemple, si vous utilisez des autorisations personnalisées, le curseur dans l'application de partage RMS sélectionne automatiquement **COPROPRIÉTAIRE** et vous ne pouvez pas remplacer cette valeur par des autorisations plus restrictives comme **OBSERVATEUR** ou **COAUTEUR**.
> -   En comparaison, quand vous utilisez la protection intégrée de RMS avec des applications qui la prennent en charge (par exemple, les fichiers Office), la protection s'applique au fichier même si le fichier est ensuite envoyé à quelqu'un d'autre ou enregistré à un autre emplacement. En outre, quand vous protégez ces fichiers, vous pouvez utiliser des autorisations restrictives, par exemple lecture seule, ou l'autorisation de modifier, mais pas d'imprimer ni de copier. Par exemple, si vous utilisez des autorisations personnalisées, le curseur dans l'application de partage RMS sélectionne automatiquement **RÉVISEUR** pour les autorisations, que vous pouvez ensuite modifier pour être plus ou moins restrictives.

##### Exemple : Pour créer un fichier protégé générique (.pfile) à partir d'un fichier de dessin Visio (.vsd)

1.  Dans l'Explorateur de fichiers, cliquez avec le bouton droit dans un dossier, cliquez sur **Nouveau**, puis sur **Nouveau document Visio**.

2.  Renommez le fichier (par exemple Exemple.vsd).

3.  Double-cliquez sur le fichier pour l'ouvrir dans Visio.

4.  Dans Visio, ajoutez des éléments au dessin, puis enregistrez et fermez le fichier.

5.  Cliquez avec le bouton droit sur le fichier, cliquez sur **Protéger sur place** et sélectionnez un modèle de stratégie dans la liste. S'il s'agit de la première fois que vous avez utilisé l'application de partage RMS, vous devez d'abord sélectionner **Protection de la société**, qui télécharge les modèles pour votre organisation.

6.  Dans l'écran **Application de partage Microsoft Rights Management**, sélectionnez la stratégie que vous souhaitez appliquer, puis cliquez sur **Appliquer**.

7.  Un message indique que votre fichier protégé a été enregistré comme fichier .pfile (par exemple, Sample.vsd.pfile). Le fichier d'origine est supprimé.

### <a name="BKMK_ViewPFILE"></a>Afficher un fichier protégé générique (.pfile)
Pour afficher un fichier protégé générique (.pfile), dans l'Explorateur de fichiers, double-cliquez sur le fichier protégé générique (.pfile), par exemple Sample.vsd.pfile, puis cliquez sur **Ouvrir**.

### <a name="BKMK_Unprotect"></a>Supprimer la protection d'un fichier
Pour supprimer la protection d'un fichier protégé (autrement dit, pour le déprotéger), utilisez l'option **Supprimer la protection** :

1.  Cliquez avec le bouton droit sur le fichier (par exemple, Sample.ptxt), cliquez sur **Protéger sur place**, puis sur **Supprimer la protection**. Des informations d'identification peuvent vous être demandées.

2.  Le fichier protégé d'origine est supprimé (par exemple, Sample.ptxt) et remplacé par un fichier portant le même nom, mais avec l'extension de nom de fichier non protégé (par exemple, Sample.txt).

### <a name="BKMK_ProtectCustom"></a>Protéger un fichier avec vos propres autorisations personnalisées
La façon la plus simple de protéger un fichier consiste à utiliser des modèles, mais vous pouvez également spécifier vos propres autorisations. Ces autorisations portent le nom de protection créée par l'utilisateur, qui est utile dans les situations suivantes :

-   Vous souhaitez limiter l'accès au fichier à une liste spécifique d'utilisateurs individuels uniquement qui sont identifiés par leurs adresses de messagerie.

-   Vous souhaitez limiter l'utilisation du fichier avec des droits spécifiques uniquement, tels que les droits en lecture seule à un document.

Pour protéger un fichier avec des autorisations créées par l'utilisateur, cliquez avec le bouton droit sur le fichier, cliquez sur **Protéger sur place**, puis sur **Autorisations personnalisées**. L'écran suivant s'affiche :

![](../Image/ADRMS_MSRMSApp_ProtectCustom.gif)

Tapez les adresses de messagerie des utilisateurs, utilisez le curseur pour sélectionner les autorisations pour le fichier, puis cliquez sur **Appliquer**.

### <a name="BKMK_UserDefined"></a>Utiliser des fichiers avec une protection personnalisée
La plupart des fichiers protégés que vous ouvrez auront été protégés en appliquant des modèles. Toutefois, les utilisateurs peuvent également protéger les fichiers à l'aide de leurs propres autorisations personnalisées, également désignées sous le nom de protection créée par l'utilisateur.

Pour les formats de fichiers texte et image, ce niveau de protection nécessite que toutes les applications qui vous permettent de modifier, d'enregistrer ou de limiter ces fichiers aient été conçues pour prendre en charge la protection RMS et qu'elles implémentent les API de protection fournies dans le Kit de développement logiciel (SDK) AD RMS.

Quand vous affichez un fichier texte protégé avec une protection créée par l'utilisateur, vous remarquez une légère différence dans les autorisations affichées pour le fichier, comme illustré dans l'exemple suivant.

Pour les fichiers qui sont protégés à l'aide du format de fichier de protection générique (.pfile), les droits spécifiques ou les autorisations spécifiées par l'utilisateur s'affichent dans l'écran de confirmation au lieu du nom du modèle qui a été utilisé pour protéger le fichier, comme illustré dans l'image suivante.

![](../Image/ADRMS_MSRMSApp_SP_ConsumePfile.gif)

### <a name="BKMK_ShareProtected"></a>Protéger le contenu à partager par courrier électronique
Pour protéger le contenu que vous souhaitez partager à l'aide d'un message électronique, cliquez avec le bouton droit sur le fichier, puis cliquez sur **Partager un fichier protégé**. L'écran suivant s'affiche :

![](../Image/ADRMS_MSRMSAPP_SP_ShareProtected.gif)

Tapez les adresses de messagerie de la liste des utilisateurs, utilisez le curseur pour sélectionner les autorisations pour le fichier, puis cliquez sur **Envoyer**. Outlook crée ensuite un message électronique pour les destinataires avec un court message que vous pouvez modifier, puis joint le fichier protégé. Le fichier d'origine n'est pas protégé.

Pour permettre aux personnes d'afficher des fichiers protégés sur des appareils autres que Windows, cliquez sur **Autoriser la consommation avec les périphériques**. Il est possible que les utilisateurs doivent télécharger l'application de partage RMS pour leur appareil, et il existe un lien pour effectuer cette opération dans le courrier électronique.

### <a name="BKMK_Multiple"></a>Appliquer la protection à plusieurs fichiers et dossiers
Vous n'êtes pas obligé d'appliquer une protection aux fichiers un par un quand vous utilisez l'Explorateur de fichiers. Au lieu de cela, vous pouvez sélectionner plusieurs fichiers ou tous les fichiers dans un dossier si ces fichiers ne sont pas déjà protégés.

##### Pour protéger plusieurs fichiers ou tous les fichiers d'un dossier sélectionné

1.  Dans l'Explorateur de fichiers, sélectionnez plusieurs fichiers ou un dossier qui contient les fichiers à protéger.

2.  Cliquez avec le bouton droit sur le dossier ou les fichiers sélectionnés, cliquez sur **Protéger sur place** et sélectionnez un modèle dans la liste. S'il s'agit de la première fois que vous avez utilisé l'application de partage RMS, vous devez d'abord sélectionner **Protection de la société**, qui télécharge les modèles pour votre organisation.

3.  Dans l'écran **Application de partage Microsoft Rights Management**, vérifiez que les fichiers ont été protégés.

> [!TIP]
> Si vous constatez des erreurs, reportez-vous à [Forum Aux Questions pour l'application de partage Microsoft Rights Management pour Windows](http://go.microsoft.com/fwlink/?LinkId=303971).

### <a name="BKMK_OfficeToolbar"></a>Utiliser le complément de barre d'outils Office
Vous pouvez protéger et partager des fichiers dans Word, PowerPoint et Excel directement à partir de Microsoft Office à l'aide du complément du ruban Office pour l'application de partage Microsoft Rights Management.

Dans le groupe **Protection**, cliquez sur **Partager un fichier protégé** pour démarrer l'application de partage Microsoft Rights Management.

![](../Image/ADRMS_MSRMSApp_SP_OfficeToolbar.png)

### <a name="BKMK_AccessKeys"></a>Utiliser des raccourcis clavier
Appuyez sur la touche **Alt** pour voir les touches d'accès disponibles, puis sur **Alt** + la touche d'accès pour sélectionner une option.

Par exemple, dans la boîte de dialogue **Partager un fichier protégé**, appuyez sur la touche **Alt** pour voir les touches d'accès, puis sur **Alt + u** pour cocher la case **Les utilisateurs doivent se connecter chaque fois qu'ils ouvrent ce fichier**.

![](../Image/ADRMS_MSRMSApp_AccessKeys.png)

## Voir aussi
[Téléchargement de l'application de partage Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970)
 [Forum Aux Questions sur l'application de partage Microsoft Rights Management pour Windows](http://go.microsoft.com/fwlink/?LinkId=303971)

