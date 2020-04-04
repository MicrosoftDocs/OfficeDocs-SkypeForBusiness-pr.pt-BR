---
title: Conduzir uma investigação de conteúdo de descoberta eletrônica do conteúdo
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba o que fazer quando você precisar executar uma descoberta eletrônica, como quando precisa enviar todas as informações armazenadas eletronicamente para procedimentos legais.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136681"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="6c332-103">Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6c332-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="6c332-104">Grandes empresas muitas vezes são expostas a grandes procedimentos legais de penalidade que exigem o envio de todas as ESI (informações armazenadas eletronicamente).</span><span class="sxs-lookup"><span data-stu-id="6c332-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="6c332-105">Todas as equipes 1:1 ou chats em grupo são registradas nas caixas de correio dos respectivos usuários e todas as mensagens de canal padrão são registradas na caixa de correio do grupo que representa a equipe.</span><span class="sxs-lookup"><span data-stu-id="6c332-105">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="6c332-106">Os arquivos carregados em canais padrão são cobertos pela funcionalidade de descoberta eletrônica do SharePoint Online e do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="6c332-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="6c332-107">a descoberta eletrônica de mensagens e arquivos em [canais privados](private-channels.md) funciona de maneira diferente em canais padrão.</span><span class="sxs-lookup"><span data-stu-id="6c332-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="6c332-108">Para saber mais, consulte [descoberta eletrônica de canais privados](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="6c332-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="6c332-109">No momento, não há suporte para eDiscovery de mensagens de chat em cenários em que os usuários convidados são os únicos participantes de um chat 1:1 ou 1: N.</span><span class="sxs-lookup"><span data-stu-id="6c332-109">At this time, we don't support eDiscovery of chat messages in scenarios where guest users are the only participants in a 1:1 or 1:N chat.</span></span> <span data-ttu-id="6c332-110">Esses tipos de chats também são chamados de chats *convidados para convidados* porque não incluem usuários locatários domésticos.</span><span class="sxs-lookup"><span data-stu-id="6c332-110">These types of chats are also called *guest-to-guest* chats because they don't include home tenant users.</span></span>

1. <span data-ttu-id="6c332-111">Para conduzir uma investigação de descoberta eletrônica com o conteúdo do Microsoft Teams, examine [a](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) etapa 1 neste link.</span><span class="sxs-lookup"><span data-stu-id="6c332-111">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2. <span data-ttu-id="6c332-112">Os dados do Microsoft Teams serão exibidos como mensagens instantâneas ou conversas na saída de exportação do Excel para descoberta eletrônica, e você poderá abrir o arquivo PST no Outlook para exibir essas mensagens postar na exportação.</span><span class="sxs-lookup"><span data-stu-id="6c332-112">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can open the PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="6c332-113">Ao exibir o PST da equipe, observe que todas as conversas são mantidas na pasta de chat da equipe em histórico de conversas.</span><span class="sxs-lookup"><span data-stu-id="6c332-113">When viewing the PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="6c332-114">O título da mensagem corresponde à Equipe a ao Canal.</span><span class="sxs-lookup"><span data-stu-id="6c332-114">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="6c332-115">Para revisar a imagem abaixo, você pode ver esta mensagem em Bob que encontrava o canal padrão do Project 7 da equipe de especificações de fabricação.</span><span class="sxs-lookup"><span data-stu-id="6c332-115">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Captura de tela de uma pasta de chat de equipe na caixa de correio de um usuário no Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. <span data-ttu-id="6c332-117">Para ver chats privados na caixa de correio de um usuário, eles também estão localizados na pasta de chat da equipe em histórico de conversas.</span><span class="sxs-lookup"><span data-stu-id="6c332-117">To see private chats in a user's mailbox, they are also located in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="6c332-118">Descoberta eletrônica de canais privados</span><span class="sxs-lookup"><span data-stu-id="6c332-118">eDiscovery of private channels</span></span>

<span data-ttu-id="6c332-119">Os registros das mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo.</span><span class="sxs-lookup"><span data-stu-id="6c332-119">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="6c332-120">Os títulos dos registros são formatados para indicar de qual canal privado eles foram enviados.</span><span class="sxs-lookup"><span data-stu-id="6c332-120">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="6c332-121">Como cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.</span><span class="sxs-lookup"><span data-stu-id="6c332-121">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="6c332-122">O Microsoft Teams não é compatível com a descoberta eletrônica de um único canal, portanto, a equipe inteira deve ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="6c332-122">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="6c332-123">Para executar uma pesquisa de descoberta eletrônica do conteúdo em um canal privado, pesquise na equipe, no conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).</span><span class="sxs-lookup"><span data-stu-id="6c332-123">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="6c332-124">Use as etapas a seguir para identificar arquivos e mensagens em um canal privado para incluir em sua pesquisa de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="6c332-124">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="6c332-125">Incluir arquivos de canal privado em uma pesquisa de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="6c332-125">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="6c332-126">Antes de executar essas etapas, instale o [Shell de gerenciamento do SharePoint Online e conecte-se ao SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="6c332-126">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="6c332-127">Execute o seguinte para obter uma lista de todos os conjuntos de sites do SharePoint associados a canais privados na equipe.</span><span class="sxs-lookup"><span data-stu-id="6c332-127">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="6c332-128">Execute o seguinte script do PowerShell para obter uma lista de todas as URLs de conjuntos de sites do SharePoint associadas a canais privados na equipe e a ID do grupo pai da equipe.</span><span class="sxs-lookup"><span data-stu-id="6c332-128">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="6c332-129">Para cada ID de equipe ou grupo, execute o seguinte script do PowerShell para identificar todos os sites de canais particulares relevantes, em que $groupID é a ID de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="6c332-129">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="6c332-130">Incluir mensagens de canal privado em uma pesquisa de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="6c332-130">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="6c332-131">Antes de executar essas etapas, verifique se você tem a [versão mais recente do módulo Teams PowerShell](teams-powershell-overview.md) instalada.</span><span class="sxs-lookup"><span data-stu-id="6c332-131">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="6c332-132">Execute o seguinte para obter uma lista de canais privados na equipe.</span><span class="sxs-lookup"><span data-stu-id="6c332-132">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="6c332-133">Execute o seguinte para obter uma lista de membros do canal privado.</span><span class="sxs-lookup"><span data-stu-id="6c332-133">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="6c332-134">Inclua as caixas de correio de todos os membros de cada canal privado da equipe como parte da sua consulta de pesquisa de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="6c332-134">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6c332-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6c332-135">Related topics</span></span>

- [<span data-ttu-id="6c332-136">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="6c332-136">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
