---
title: Usar a pesquisa de conteúdo no Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Saiba mais sobre como usar a pesquisa de conteúdo no centro de conformidade do Microsoft 365 para pesquisar Microsoft Teams conteúdo armazenado no Exchange Online, SharePoint Online, OneDrive for Business e OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb63f3668ef03cdaf760a24ae1df0a815e7f282d
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855800"
---
# <a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="66b71-103">Usar a pesquisa de conteúdo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66b71-103">Use Content search in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="66b71-104">A pesquisa de conteúdo de mensagens e arquivos em [canais privados](private-channels.md) funciona de forma diferente dos canais padrão.</span><span class="sxs-lookup"><span data-stu-id="66b71-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="66b71-105">Para saber mais, confira [Pesquisa de conteúdo de canais privados](#content-search-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="66b71-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="66b71-106">A pesquisa de conteúdo fornece uma maneira de consultar Microsoft Teams informações que abrangem Exchange, SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="66b71-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="66b71-107">Para saber mais, confira [Pesquisa de conteúdo em Microsoft 365](/microsoft-365/compliance/content-search).</span><span class="sxs-lookup"><span data-stu-id="66b71-107">To learn more, see [Content search in Microsoft 365](/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="66b71-108">Por exemplo,  usando a pesquisa de conteúdo em sua caixa de correio de Especificações de Manufatura e o site de Especificações de Manufatura SharePoint, você pode pesquisar em conversas de canal padrão do Teams do Exchange, carregamentos de arquivos e modificações do SharePoint Online e OneNote alterações.</span><span class="sxs-lookup"><span data-stu-id="66b71-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="66b71-109">Você também pode adicionar critérios de consulta à Pesquisa **de Conteúdo** para restringir os resultados retornados.</span><span class="sxs-lookup"><span data-stu-id="66b71-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="66b71-110">No exemplo acima, você pode procurar conteúdo em que as palavras-chave "**New Factory Specs" foram usadas.**</span><span class="sxs-lookup"><span data-stu-id="66b71-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="66b71-111">Depois de adicionar condições de pesquisa, você pode exportar um relatório ou o conteúdo real para seu computador para análise.</span><span class="sxs-lookup"><span data-stu-id="66b71-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="66b71-112">Pesquisa de conteúdo de canais privados</span><span class="sxs-lookup"><span data-stu-id="66b71-112">Content search of private channels</span></span>

<span data-ttu-id="66b71-113">Os registros das mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo.</span><span class="sxs-lookup"><span data-stu-id="66b71-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="66b71-114">Os títulos dos registros são formatados para indicar de qual canal privado eles foram enviados.</span><span class="sxs-lookup"><span data-stu-id="66b71-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="66b71-115">Como cada canal privado tem seu próprio conjunto de sites SharePoint separado do site da equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.</span><span class="sxs-lookup"><span data-stu-id="66b71-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="66b71-116">Teams não dá suporte à pesquisa de conteúdo de um único canal, portanto, toda a equipe deve ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="66b71-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="66b71-117">Para executar uma pesquisa de conteúdo de um canal privado, pesquise pela equipe, o conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).</span><span class="sxs-lookup"><span data-stu-id="66b71-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="66b71-118">Use as etapas a seguir para identificar arquivos e mensagens em um canal privado para incluir na pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="66b71-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="66b71-119">Incluir arquivos de canal privado em uma pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="66b71-119">Include private channel files in a content search</span></span>

<span data-ttu-id="66b71-120">Antes de executar essas etapas, instale o Shell SharePoint [Gerenciamento Online e conecte-se ao SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="66b71-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="66b71-121">Execute o seguinte para obter uma lista de todos os SharePoint de sites associados a canais privados na equipe.</span><span class="sxs-lookup"><span data-stu-id="66b71-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="66b71-122">Execute o seguinte script do PowerShell para obter uma lista de todas as URLs do conjunto de sites SharePoint associadas a canais privados na equipe e à ID do grupo de equipe pai.</span><span class="sxs-lookup"><span data-stu-id="66b71-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="66b71-123">Para cada ID de equipe ou grupo, execute o seguinte script do PowerShell para identificar todos os sites de canal particular relevantes.</span><span class="sxs-lookup"><span data-stu-id="66b71-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="66b71-124">Incluir mensagens de canal privado em uma pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="66b71-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="66b71-125">Antes de executar essas etapas, certifique-se de ter a versão mais recente [do módulo Teams PowerShell](teams-powershell-overview.md) instalado.</span><span class="sxs-lookup"><span data-stu-id="66b71-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="66b71-126">Execute o seguinte para obter uma lista de canais privados na equipe.</span><span class="sxs-lookup"><span data-stu-id="66b71-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="66b71-127">Execute o seguinte para obter uma lista de membros do canal privado.</span><span class="sxs-lookup"><span data-stu-id="66b71-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="66b71-128">Inclua as caixas de correio de todos os membros de cada canal privado na equipe como parte da consulta de pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="66b71-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="66b71-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="66b71-129">Related topics</span></span>

- [<span data-ttu-id="66b71-130">Casos de Descoberta eDiscovery no Microsoft 365 De conformidade</span><span class="sxs-lookup"><span data-stu-id="66b71-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](/Office365/SecurityCompliance/ediscovery-cases)