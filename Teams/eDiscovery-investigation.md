---
title: Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams
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
description: Saiba o que fazer quando precisar executar uma Descoberta Eletrônica, como quando precisar enviar todas as informações armazenadas eletronicamente para procedimentos judiciais.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43105db9a4e12d658bf5cf2e9c2c8897fdc918e3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989786"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="5ee24-103">Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5ee24-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>
============================

<span data-ttu-id="5ee24-104">Grandes empresas muitas vezes são expostas a grandes procedimentos legais de penalidade que exigem o envio de todas as ESI (informações armazenadas eletronicamente).</span><span class="sxs-lookup"><span data-stu-id="5ee24-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="5ee24-105">Todas as equipes 1:1 ou chats em grupo são registradas nas caixas de correio dos respectivos usuários e todas as mensagens de canal padrão são registradas na caixa de correio do grupo que representa a equipe.</span><span class="sxs-lookup"><span data-stu-id="5ee24-105">All Teams 1:1 or group chats are journaled through to the respective users’ mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="5ee24-106">Os arquivos carregados em canais padrão são cobertos pela funcionalidade de descoberta eletrônica do SharePoint Online e do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="5ee24-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="5ee24-107">a descoberta eletrônica de mensagens e arquivos em [canais privados](private-channels.md) funciona de maneira diferente em canais padrão.</span><span class="sxs-lookup"><span data-stu-id="5ee24-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="5ee24-108">Para saber mais, consulte [descoberta eletrônica de canais privados](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="5ee24-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

1.  <span data-ttu-id="5ee24-109">Para conduzir uma investigação de descoberta eletrônica com o conteúdo do Microsoft Teams, examine [a](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) etapa 1 neste link.</span><span class="sxs-lookup"><span data-stu-id="5ee24-109">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2.  <span data-ttu-id="5ee24-110">Os dados do Microsoft Teams serão exibidos como mensagens instantâneas ou conversas na saída de exportação do Excel para descoberta eletrônica, e você poderá montar o. PST no Outlook para exibir essas mensagens postar na exportação.</span><span class="sxs-lookup"><span data-stu-id="5ee24-110">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can mount the .PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="5ee24-111">Ao montar o .PST para a equipe, observe que todas as conversas serão mantidas na pasta Bate-papo em Equipe no Histórico de Conversas.</span><span class="sxs-lookup"><span data-stu-id="5ee24-111">When mounting the .PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="5ee24-112">O título da mensagem corresponde à Equipe a ao Canal.</span><span class="sxs-lookup"><span data-stu-id="5ee24-112">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="5ee24-113">Para revisar a imagem abaixo, você pode ver esta mensagem em Bob que encontrava o canal padrão do Project 7 da equipe de especificações de fabricação.</span><span class="sxs-lookup"><span data-stu-id="5ee24-113">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Captura de tela de uma pasta de chat de equipe na caixa de correio de um usuário no Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  <span data-ttu-id="5ee24-115">Para ver chats privados na caixa de correio de um usuário, eles também estão localizados dentro da pasta de chat da equipe em histórico de conversas.</span><span class="sxs-lookup"><span data-stu-id="5ee24-115">To see private chats in a user’s mailbox, they are also located inside the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-guest-to-guest-chats"></a><span data-ttu-id="5ee24-116">Descoberta eletrônica de chats convidados para convidados</span><span class="sxs-lookup"><span data-stu-id="5ee24-116">eDiscovery of guest-to-guest chats</span></span>

<span data-ttu-id="5ee24-117">Atualmente, para um cenário em que apenas convidados participam do 1:1 ou 1: N chat, não oferecemos suporte para a eDiscovery dessas mensagens de chat.</span><span class="sxs-lookup"><span data-stu-id="5ee24-117">Presently, for a scenario where only guests are participating in 1:1 or 1:N chat, we don't support eDiscovery of those chat messages.</span></span> 

<span data-ttu-id="5ee24-118">Sem uma caixa de correio, chats convidados para convidados (chats 1xN em que não há usuários locatários domésticos) não seriam indexados e, consequentemente, não seriam incluídos na descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="5ee24-118">Without a mailbox, guest-to-guest chats (1xN chats in which there are no home tenant users) would not be indexed, and as a result, would not be included in eDiscovery.</span></span> <span data-ttu-id="5ee24-119">Para facilitar a descoberta eletrônica para chats convidados a convidados, uma caixa de correio baseada em nuvem (ou uma caixa de correio fantasma) é criada para armazenar os dados do 1xN.</span><span class="sxs-lookup"><span data-stu-id="5ee24-119">To facilitate eDiscovery for guest-to-guest chats, a cloud-based mailbox (or phantom mailbox) is created to store the 1xN data.</span></span> <span data-ttu-id="5ee24-120">Depois que os dados de chat de equipe são armazenados na caixa de correio baseada em nuvem, eles são indexados para pesquisa de conteúdo de descoberta eletrônica e conformidade.</span><span class="sxs-lookup"><span data-stu-id="5ee24-120">After the Teams chat data is stored in the cloud-based mailbox, it is indexed for eDiscovery and compliance content search.</span></span>

<span data-ttu-id="5ee24-121">A ilustração a seguir mostra como a descoberta eletrônica funciona para chats convidados a convidados em que não há uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="5ee24-121">The following illustration shows how eDiscovery works for guest-to-guest chats in which there isn’t a mailbox.</span></span>

![convidado para convidado-chats com e sem caixa de correio](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="5ee24-123">Descoberta eletrônica de canais privados</span><span class="sxs-lookup"><span data-stu-id="5ee24-123">eDiscovery of private channels</span></span>

<span data-ttu-id="5ee24-124">Os registros de mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo.</span><span class="sxs-lookup"><span data-stu-id="5ee24-124">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="5ee24-125">Os títulos dos registros são formatados para indicar o canal privado do qual foram enviados.</span><span class="sxs-lookup"><span data-stu-id="5ee24-125">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="5ee24-126">Como cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.</span><span class="sxs-lookup"><span data-stu-id="5ee24-126">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="5ee24-127">O Microsoft Teams não é compatível com a descoberta eletrônica de um único canal, portanto, a equipe inteira deve ser pesquisada.</span><span class="sxs-lookup"><span data-stu-id="5ee24-127">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="5ee24-128">Para executar uma pesquisa de descoberta eletrônica do conteúdo em um canal privado, pesquise na equipe, no conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).</span><span class="sxs-lookup"><span data-stu-id="5ee24-128">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="5ee24-129">Use as etapas a seguir para identificar arquivos e mensagens em um canal privado para incluir em sua pesquisa de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="5ee24-129">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="5ee24-130">Incluir arquivos de canal privado em uma pesquisa de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="5ee24-130">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="5ee24-131">Antes de executar essas etapas, instale o [Shell de gerenciamento do SharePoint Online e conecte-se ao SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="5ee24-131">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="5ee24-132">Execute o seguinte para obter uma lista de todos os conjuntos de sites do SharePoint associados a canais privados na equipe.</span><span class="sxs-lookup"><span data-stu-id="5ee24-132">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="5ee24-133">Execute o seguinte script do PowerShell para obter uma lista de todas as URLs de conjuntos de sites do SharePoint associadas a canais privados na equipe e a ID do grupo pai da equipe.</span><span class="sxs-lookup"><span data-stu-id="5ee24-133">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="5ee24-134">Para cada ID de equipe ou grupo, execute o seguinte script do PowerShell para identificar todos os sites de canais particulares relevantes, em que $groupID é a ID de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="5ee24-134">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “e8195240-4a70-4830-9106-80193cf717cb“
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="5ee24-135">Incluir mensagens de canal privado em uma pesquisa de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="5ee24-135">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="5ee24-136">Antes de executar essas etapas, verifique se você tem a [versão mais recente do módulo Teams PowerShell](teams-powershell-overview.md) instalada.</span><span class="sxs-lookup"><span data-stu-id="5ee24-136">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="5ee24-137">Execute o seguinte para obter uma lista de canais privados na equipe.</span><span class="sxs-lookup"><span data-stu-id="5ee24-137">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="5ee24-138">Execute o seguinte para obter uma lista de membros do canal privado.</span><span class="sxs-lookup"><span data-stu-id="5ee24-138">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="5ee24-139">Inclua as caixas de correio de todos os membros de cada canal privado da equipe como parte da sua consulta de pesquisa de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="5ee24-139">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ee24-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5ee24-140">Related topics</span></span>

- [<span data-ttu-id="5ee24-141">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="5ee24-141">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
