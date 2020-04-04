---
title: Usar a pesquisa de conteúdo no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Saiba como usar a pesquisa de conteúdo no Microsoft Teams para consultar informações do Microsoft Teams do Exchange, do SharePoint Online, do OneDrive for Business e do OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: af81b857d6cf60f7de1a1b1e199d08ede089de5f
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137741"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="4aee6-103">Usar a pesquisa de conteúdo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4aee6-103">Use Content Search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="4aee6-104">A pesquisa de conteúdo de mensagens e arquivos em [canais privados](private-channels.md) funciona de forma diferente do que em canais padrão.</span><span class="sxs-lookup"><span data-stu-id="4aee6-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="4aee6-105">Para saber mais, consulte [pesquisa de conteúdo em canais privados](#content-search-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="4aee6-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="4aee6-106">A pesquisa de conteúdo fornece uma maneira de consultar as informações do Microsoft Teams estendido o Exchange, o SharePoint Online e o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="4aee6-106">Content Search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="4aee6-107">Para saber mais, leia [Pesquisar conteúdo no Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span><span class="sxs-lookup"><span data-stu-id="4aee6-107">To learn more, read [Content Search in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span></span>

<span data-ttu-id="4aee6-108">Por exemplo, ao usar a **pesquisa de conteúdo** em sua caixa de correio de especificações de fabricação e especificações de fabricação do site do SharePoint, você pode pesquisar as conversas de canal padrão do teams do Exchange, uploads e alterações de arquivos do SharePoint Online e alterações do OneNote.</span><span class="sxs-lookup"><span data-stu-id="4aee6-108">For example, using **Content Search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="4aee6-109">Você também pode adicionar critérios de consulta à **pesquisa de conteúdo** para restringir os resultados retornados.</span><span class="sxs-lookup"><span data-stu-id="4aee6-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="4aee6-110">No exemplo acima, você pode procurar por conteúdo em que as palavras-chave "**novas especificações de fábrica"** foram usadas.</span><span class="sxs-lookup"><span data-stu-id="4aee6-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="4aee6-111">Depois de adicionar critérios de pesquisa, você pode exportar um relatório ou os dados para o seu computador para análise.</span><span class="sxs-lookup"><span data-stu-id="4aee6-111">After adding search conditions, you can export a report or the data to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="4aee6-112">Pesquisa de conteúdo em canais privados</span><span class="sxs-lookup"><span data-stu-id="4aee6-112">Content search of private channels</span></span>

<span data-ttu-id="4aee6-113">Os registros das mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo.</span><span class="sxs-lookup"><span data-stu-id="4aee6-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="4aee6-114">Os títulos dos registros são formatados para indicar de qual canal privado eles foram enviados.</span><span class="sxs-lookup"><span data-stu-id="4aee6-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="4aee6-115">Como cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.</span><span class="sxs-lookup"><span data-stu-id="4aee6-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="4aee6-116">O Teams não oferece suporte à pesquisa de conteúdo de um único canal, portanto, a equipe inteira deve ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="4aee6-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="4aee6-117">Para executar uma pesquisa de conteúdo de um canal privado, pesquise na equipe, no conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).</span><span class="sxs-lookup"><span data-stu-id="4aee6-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="4aee6-118">Use as etapas a seguir para identificar arquivos e mensagens em um canal privado para incluir em sua pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4aee6-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="4aee6-119">Incluir arquivos de canal privado em uma pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="4aee6-119">Include private channel files in a content search</span></span>

<span data-ttu-id="4aee6-120">Antes de executar essas etapas, instale o [Shell de gerenciamento do SharePoint Online e conecte-se ao SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="4aee6-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="4aee6-121">Execute o seguinte para obter uma lista de todos os conjuntos de sites do SharePoint associados a canais privados na equipe.</span><span class="sxs-lookup"><span data-stu-id="4aee6-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="4aee6-122">Execute o seguinte script do PowerShell para obter uma lista de todas as URLs de conjuntos de sites do SharePoint associadas a canais privados na equipe e a ID do grupo pai da equipe.</span><span class="sxs-lookup"><span data-stu-id="4aee6-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="4aee6-123">Para cada ID de equipe ou grupo, execute o seguinte script do PowerShell para identificar todos os sites de canais particulares relevantes.</span><span class="sxs-lookup"><span data-stu-id="4aee6-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="4aee6-124">Incluir mensagens de canal privado em uma pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="4aee6-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="4aee6-125">Antes de executar essas etapas, verifique se você tem a [versão mais recente do módulo Teams PowerShell](teams-powershell-overview.md) instalada.</span><span class="sxs-lookup"><span data-stu-id="4aee6-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="4aee6-126">Execute o seguinte para obter uma lista de canais privados na equipe.</span><span class="sxs-lookup"><span data-stu-id="4aee6-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="4aee6-127">Execute o seguinte para obter uma lista de membros do canal privado.</span><span class="sxs-lookup"><span data-stu-id="4aee6-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="4aee6-128">Inclua as caixas de correio de todos os membros de cada canal privado da equipe como parte da consulta de pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4aee6-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4aee6-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4aee6-129">Related topics</span></span>

- [<span data-ttu-id="4aee6-130">casos de descoberta eletrônica no centro de conformidade & segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="4aee6-130">eDiscovery cases in the Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 