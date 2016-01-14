---
description: na
keywords: na
title: Configuring Usage Rights for Azure Rights Management
search: na
ms.date: na
ms.service: rights-management
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 97ddde38-b91b-42a5-8eb4-3ce6ce15393d
---
# Configuration des droits d&#39;utilisation pour Azure Rights Management
Lorsque vous définissez la protection de fichiers ou de messages électroniques à l’aide d’Azure Rights Management (Azure RMS) et n’utilisez pas de modèle, vous devez configurer les droits d’utilisation vous-même. En outre, lorsque vous configurez des modèles personnalisés pour Azure RMS, vous sélectionnez les droits d’utilisation qui seront ensuite appliqués automatiquement lorsque le modèle sera sélectionné par des utilisateurs, administrateurs ou services configurés. Par exemple, dans le portail Azure Classic, vous pouvez sélectionner des rôles qui configurent un regroupement logique de droits d’utilisation, ou configurer les droits individuels.

Utilisez cette rubrique pour vous aider à configurer les droits d’utilisation de l’application que vous utilisez et pour comprendre comment ces droits sont interprétés par les applications.

## Descriptions et droits d’utilisation
Le tableau suivant répertorie et décrit les droits d’utilisation pris en charge par Rights Management, et la manière dont ils sont utilisés et interprétés. Dans ce tableau, le **Nom commun** correspond à la manière dont le droit d’utilisation est généralement affiché ou référencé sous une forme plus conviviale que la valeur de mot unique utilisée dans le code (valeur d’**Encodage dans la stratégie**). La **Constante ou valeur d’API** est le nom d’un appel d’API MSIPC, selon le Kit de développement logiciel (SDK), utilisé lorsque vous écrivez une application compatible avec RMS qui vérifie un droit d’utilisation, ou en ajoute un à une stratégie.

|Nom commun|Encodage dans la stratégie|Description|Implémentation dans les droits personnalisés Office|Connectez-vous au portail Azure Classic.|Nom dans les modèles AD RMS|Constante ou valeur d’API|Informations supplémentaires|
|--------------|------------------------------|---------------|-------------------------------------------------------|--------------------------------------------|-------------------------------|-----------------------------|--------------------------------|
|Modifier le contenu, Modifier|DOCEDIT|Permet à l’utilisateur de modifier, réorganiser, mettre en forme ou filtrer le contenu de l’application. N’accorde pas le droit d’enregistrer la copie modifiée.|En relation avec les options **Modifier** et **Contrôle total**.|**Modifier le contenu**|**Éditer**|Non applicable|Dans les applications Office, ce droit permet également à l’utilisateur d’enregistrer le document.|
|Enregistrer|MODIFIER|Permet à l’utilisateur d’enregistrer le document à son emplacement actuel.|En relation avec les options **Modifier** et **Contrôle total**.|**Enregistrer le fichier**|**Enregistrer**|IPC_GENERIC_WRITEL"EDIT"|Dans les applications Office, ce droit permet également à l’utilisateur de modifier le document.|
|Commentaire|COMMENTAIRE|Active l’option d’ajout d’annotations ou de commentaires au contenu.|Non implémenté|Non implémenté|Non implémenté|IPC_GENERIC_COMMENTL"COMMENT"|Ce droit disponible dans le Kit de développement logiciel (SDK), est disponible en tant que stratégie ad hoc dans le module de protection RMS pour Windows PowerShell. Il a été implémenté dans certaines applications de fournisseur de logiciel. Toutefois, il n’est pas largement utilisé et n’est pas actuellement pris en charge par les applications Office.|
|Enregistrer sous, Exporter|EXPORTER|Active l’option d’enregistrement du contenu sous un autre nom de fichier (Enregistrer sous). Selon l’application, le fichier peut être enregistré sans protection.|En relation avec les options **Modifier** et **Contrôle total**.|**Exporter le contenu (Enregistrer sous)**|**Exporter (Enregistrer sous)**|IPC_GENERIC_EXPORTL"EXPORT"|Ce droit permet également à l’utilisateur d’utiliser d’autres options d’exportation dans les applications, telles que **Envoyer à OneNote**.|
|Prédictif|TRANSFÉRER|Active l’option de transfert de message électronique et d’ajout de destinataires aux lignes **À** et **CC**.|Refusée en cas d’utilisation de la stratégie standard **Ne pas transférer**.|**Prédictif**|**Prédictif**|IPC_EMAIL_FORWARDL"FORWARD"|N’autorise pas le redirecteur à accorder des droits à d’autres utilisateurs dans le cadre de l’action de transfert.|
|Contrôle total|OWNER|Accorde tous les droits sur le document. Toutes les actions disponibles peuvent être effectuées.|Comme l’option personnalisée **Contrôle total**.|**Contrôle total**|**Contrôle total**|IPC_GENERIC_ALLL"OWNER"|Inclut la possibilité de supprimer la protection.|
|Imprimer|PRINT|Active les options d’impression du contenu.|Comme l’option **imprimer le contenu**  dans les autorisations personnalisées. N’est pas un paramètre par destinataire.|**Imprimer**|**Imprimer**|IPC_GENERIC_PRINTL"PRINT|Aucune information supplémentaire|
|Répondre|RÉPONDRE|Active l’option Répondre dans un client de messagerie sans autoriser de modification des lignes **À** ou **CC**.|Non applicable|**Répondre**|**Répondre**|IPC_EMAIL_REPLY|Aucune information supplémentaire|
|Répondre à tous|REPLYALL|Active l’option **Répondre à tous** dans un client de messagerie, mais ne permet pas à l’utilisateur d’ajouter des destinataires aux lignes **À** ou **CC**.|Non applicable|**Répondre à tous**|**Répondre à tous**|IPC_EMAIL_REPLYALLL"REPLYALL"|Aucune information supplémentaire|
|Afficher, Ouvrir, Lire|AFFICHAGE|Permet à l’utilisateur d’ouvrir le document et d’en voir le contenu.|Comme l’option **Afficher** de la stratégie personnalisée **Lecture**.|**Afficher le contenu**|**View**|IPC_GENERIC_READL"VIEW"|Aucune information supplémentaire|
|Copier|EXTRACT|Active les options permettant de copier des données à l’intérieur du document ou du document vers un autre.|Comme l’option de stratégie personnalisée **Autoriser les utilisateurs bénéficiant d’accès en lecture à copier le contenu**.|**Copier et Extraire le contenu**|**Extraction**|IPC_GENERIC_EXTRACTL"EXTRACT"|Dans certaines applications, permet également d’enregistrer l’ensemble du document sous forme non protégée.|
|Afficher les droits|VIEWRIGHTSDATA|Permet à l’utilisateur d’afficher la stratégie appliquée au document.|Non implémenté|**Afficher les droits affectés**|**Afficher les droits**|IPC_READ_RIGHTSL"VIEWRIGHTSDATA"|Ignoré par certaines applications.|
|Modifier les droits|EDITRIGHTSDATA|Permet à l’utilisateur de modifier la stratégie appliquée au document. Inclut notamment la suppression de la protection.|Non implémenté|**Modifier les droits**|**Modifier les droits**|IPC_WRITE_RIGHTSL"EDITRIGHTSDATA"|Aucune information supplémentaire|
|Autoriser les macros|OBJMODEL|Active l’option permettant d’exécuter des macros ou d’effectuer d’autres opérations d’accès à distance ou par programme au contenu d’un document.|Comme l’option de stratégie personnalisée **Autoriser l’accès par programme**. N’est pas un paramètre par destinataire.|**Autoriser les macros**|**Autoriser les macros**|Non applicable|Aucune information supplémentaire|

## Droits inclus dans les niveaux d’autorisation
Certaines applications regroupent les droits d’utilisation dans des niveaux d’autorisation, ce qui facilite la sélection de droits d’utilisation qui sont généralement utilisés ensemble. Ces niveaux d’autorisation permettent de réduire la complexité, si bien que les utilisateurs peuvent choisir des options basées sur des rôles.  Par exemple, **Réviseur** et **Coauteur**. Bien que ces options montrent souvent aux utilisateurs un récapitulatif des droits, il peut arriver qu’elles n’incluent pas tous les droits répertoriés dans le tableau précédent.

Envisagez le tableau suivant comme une liste de ces niveaux d’autorisation et comme une liste complète des droits qu’ils renferment.

|Niveau d’autorisation|Applications|Droits inclus (nom commun)|
|-------------------------|----------------|------------------------------|
|Observateur|Portail Azure Classic<br /><br />Application de partage Rights Management pour Windows|Afficher, Ouvrir, Lire<br /><br />Répondre<br /><br />Répondre à tous|
|Réviseur|Portail Azure Classic<br /><br />Application de partage Rights Management pour Windows|Afficher, Ouvrir, Lire<br /><br />Enregistrer<br /><br />Modifier le contenu, Modifier<br /><br />Répondre<sup>*</sup><br /><br />Répondre à tous<sup>*</sup><br /><br />Transférer<sup>*</sup>|
|Coauteur|Portail Azure Classic<br /><br />Application de partage Rights Management pour Windows|Afficher, Ouvrir, Lire<br /><br />Enregistrer<br /><br />Modifier le contenu, Modifier<br /><br />Copier<br /><br />Afficher les droits<br /><br />Modifier les droits<br /><br />Autoriser les macros<br /><br />Enregistrer sous, Exporter<br /><br />Imprimer<br /><br />Répondre<sup>*</sup><br /><br />Répondre à tous<sup>*</sup><br /><br />Transférer<sup>*</sup>|
|Copropriétaire|Portail Azure Classic<br /><br />Application de partage Rights Management pour Windows|Afficher, Ouvrir, Lire<br /><br />Enregistrer<br /><br />Modifier le contenu, Modifier<br /><br />Copier<br /><br />Afficher les droits<br /><br />Modifier les droits<br /><br />Autoriser les macros<br /><br />Enregistrer sous, Exporter<br /><br />Imprimer<br /><br />Répondre<sup>*</sup><br /><br />Répondre à tous<sup>*</sup><br /><br />Transférer<sup>*</sup><br /><br />Contrôle total|
<sup>*</sup> Non applicable à l’application de partage Rights Management pour Windows

## Droits inclus dans les modèles par défaut
Les droits inclus avec les modèles par défaut sont les suivants :

|Nom d’affichage|Droits inclus (nom commun)|
|-------------------|------------------------------|
|&lt;nom de l’organisation&gt; - Affichage confidentiel uniquement|Afficher, Ouvrir, Lire|
|&lt;nom de l’organisation&gt; - Confidentiel|Afficher, Ouvrir, Lire<br /><br />Enregistrer<br /><br />Modifier le contenu, Modifier<br /><br />Afficher les droits<br /><br />Autoriser les macros<br /><br />Prédictif<br /><br />Répondre<br /><br />Répondre à tous|

## Voir aussi
[Configuration d'Azure Rights Management](../Topic/Configuring_Azure_Rights_Management.md)

