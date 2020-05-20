---
title: Gerenciar o ciclo de vida de canais privados no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr, phlouie
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar o ciclo de vida de canais privados em sua organização.
ms.openlocfilehash: 154cde6ad8371b2d9f902bf3803f48e72ade0a77
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321690"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="3079c-103">Gerenciar o ciclo de vida de canais privados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3079c-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="3079c-104">Aqui você encontrará as diretrizes necessárias para gerenciar o ciclo de vida de [canais privados](private-channels.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3079c-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3079c-105">Se você estiver usando as etapas do PowerShell neste artigo para gerenciar canais privados, deve instalar e usar a versão de pré-lançamento mais recente do módulo do teams PowerShell da [Galeria de teste do PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="3079c-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest pre-release version of the Teams PowerShell module from the [PowerShell Test Gallery](https://www.poshtestgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="3079c-106">Para ver as etapas sobre como instalar o módulo, consulte [instalar a versão de pré-lançamento do módulo do teams PowerShell](install-prerelease-teams-powershell-module.md).</span><span class="sxs-lookup"><span data-stu-id="3079c-106">For steps on how to install the module, see [Install the pre-release version of the Teams PowerShell module](install-prerelease-teams-powershell-module.md).</span></span> <span data-ttu-id="3079c-107">A versão mais recente disponível publicamente do módulo Teams PowerShell não oferece suporte ao gerenciamento de canais privados.</span><span class="sxs-lookup"><span data-stu-id="3079c-107">The latest publicly available version of the Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="3079c-108">Definir se os membros da equipe podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="3079c-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="3079c-109">Os proprietários da equipe podem desativar ou ativar a capacidade de os Membros criarem canais privados nas configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="3079c-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="3079c-110">Para fazer isso, na guia **configurações** da equipe, desative ou ative **permitir que os membros criem canais privados**.</span><span class="sxs-lookup"><span data-stu-id="3079c-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="3079c-111">Como administrador, você pode usar a API de gráficos para controlar se os membros podem criar canais privados em equipes específicas.</span><span class="sxs-lookup"><span data-stu-id="3079c-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="3079c-112">Aqui está um exemplo.</span><span class="sxs-lookup"><span data-stu-id="3079c-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="3079c-113">Definir se os usuários em sua organização podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="3079c-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="3079c-114">Como administrador, você pode definir políticas usando o centro de administração do Microsoft Teams ou o PowerShell para controlar quais usuários na sua organização têm permissão para criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="3079c-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3079c-115">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3079c-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3079c-116">Use as políticas do teams para definir quais usuários na sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="3079c-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="3079c-117">Para saber mais, consulte [gerenciar políticas de equipes no Microsoft Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3079c-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3079c-118">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3079c-118">Using PowerShell</span></span>

<span data-ttu-id="3079c-119">Use o **CsTeamsChannelsPolicy** para definir quais usuários da sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="3079c-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="3079c-120">Defina o parâmetro **AllowPrivateChannelCreation** como **true** para permitir que os usuários atribuídos à política criem canais privados.</span><span class="sxs-lookup"><span data-stu-id="3079c-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="3079c-121">Definir o parâmetro como **false** desativa a capacidade de criar canais privados para os usuários atribuídos à política.</span><span class="sxs-lookup"><span data-stu-id="3079c-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="3079c-122">Para saber mais, confira [novo – CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3079c-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="3079c-123">Criar um canal privado em nome de um proprietário de equipe</span><span class="sxs-lookup"><span data-stu-id="3079c-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="3079c-124">Como administrador, você pode usar a API do PowerShell ou do Graph para criar um canal privado em nome de um proprietário de equipe.</span><span class="sxs-lookup"><span data-stu-id="3079c-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="3079c-125">Por exemplo, você pode querer fazer isso se a sua organização quer centralizar a criação de canais privados.</span><span class="sxs-lookup"><span data-stu-id="3079c-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3079c-126">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3079c-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="3079c-127">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="3079c-127">Using Graph API</span></span>

```Graph API
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="3079c-128">Obter uma lista de todas as mensagens particulares do canal privado</span><span class="sxs-lookup"><span data-stu-id="3079c-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="3079c-129">Você pode querer obter uma lista de todas as mensagens e respostas postadas em um canal privado para fins de arquivamento e auditoria.</span><span class="sxs-lookup"><span data-stu-id="3079c-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="3079c-130">Veja como usar a API de gráfico para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="3079c-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="3079c-131">Localizar URLs do SharePoint para todos os canais particulares em uma equipe</span><span class="sxs-lookup"><span data-stu-id="3079c-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="3079c-132">Se você estiver procurando executar o descoberta eletrônica ou o controle legal em arquivos em um canal privado ou procurando criar um aplicativo personalizado que coloca arquivos em canais particulares específicos, você precisará de uma maneira de consultar os conjuntos de sites exclusivos do SharePoint criados para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="3079c-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="3079c-133">Como administrador, você pode usar os comandos do PowerShell ou de APIs de gráfico para consultar essas URLs.</span><span class="sxs-lookup"><span data-stu-id="3079c-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3079c-134">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3079c-134">Using PowerShell</span></span>

1. <span data-ttu-id="3079c-135">Instale e conecte-se ao [Shell de gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) com sua conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="3079c-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="3079c-136">Execute o seguinte, onde &lt; group_id &gt; é a ID do grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="3079c-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="3079c-137">(Você pode localizar facilmente a identificação do grupo no link para a equipe.)</span><span class="sxs-lookup"><span data-stu-id="3079c-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="3079c-138">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="3079c-138">Using Graph API</span></span>

<span data-ttu-id="3079c-139">Você pode experimentar esses comandos por meio do [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="3079c-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="3079c-140">Use o seguinte para obter a lista de IDs de canais particulares para uma determinada equipe, onde <group_id> é a ID de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="3079c-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="3079c-141">Você precisará disso nas chamadas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="3079c-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="3079c-142">(Você pode localizar facilmente a identificação do grupo no link para a equipe).</span><span class="sxs-lookup"><span data-stu-id="3079c-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="3079c-143">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="3079c-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="3079c-144">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="3079c-144">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
    
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

2. <span data-ttu-id="3079c-145">Para cada canal privado do qual você deseja obter a URL do SharePoint, faça a seguinte solicitação, em que &lt; channel_id &gt; é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="3079c-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="3079c-146">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="3079c-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="3079c-147">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="3079c-147">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json
    Content-length:
      
    {
      "value": [
        {
          "description": "description-value",
          "displayName": "display-name-value",
          "id": "channel_id",
          "membershipType": "membership-type-value",
          "isFavoriteByDefault": false,
          "webUrl": "webUrl-value",
          "email": "email-value"
        }
      ]
    }
    ```

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="3079c-148">Listar e atualizar funções de proprietários e membros em um canal privado</span><span class="sxs-lookup"><span data-stu-id="3079c-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="3079c-149">Talvez você queira listar os proprietários e os membros de um canal privado para decidir se precisa promover certos membros do canal privado para um proprietário.</span><span class="sxs-lookup"><span data-stu-id="3079c-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="3079c-150">Isso pode acontecer quando você tem proprietários de canais privados que saíram da organização e o canal privado exige que a ajuda do administrador solicite a posse do canal.</span><span class="sxs-lookup"><span data-stu-id="3079c-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="3079c-151">Como administrador, você pode usar os comandos do PowerShell ou de APIs de gráfico para consultar essas URLs.</span><span class="sxs-lookup"><span data-stu-id="3079c-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="3079c-152">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3079c-152">Using PowerShell</span></span>

1. <span data-ttu-id="3079c-153">Execute o seguinte, onde &lt; group_id &gt; é a ID do grupo da equipe e &lt; channel_name &gt; é o nome do canal.</span><span class="sxs-lookup"><span data-stu-id="3079c-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="3079c-154">Promover um membro a um proprietário.</span><span class="sxs-lookup"><span data-stu-id="3079c-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="3079c-155">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="3079c-155">Using Graph API</span></span>

<span data-ttu-id="3079c-156">Você pode experimentar esses comandos por meio do [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="3079c-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="3079c-157">Use o seguinte, em que &lt; group_id &gt; é a ID do grupo da equipe e &lt; CHANNEL_ID &gt; é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="3079c-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="3079c-158">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="3079c-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="3079c-159">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="3079c-159">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams({group_id}')/channels('{channel_id}')/members",
          "@odata.count": 2,
          "value": [
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
                  "id": "id-value",
                  "roles": [],
                  "displayName": "display-name-value",
                  "userId": "userId-value",
                  "email": "email-value"
              },
              {
                  "@odata.type": "#microsoft.graph.aadUserConversationMember",
              "id": "id-value",
              "roles": ["owner"],
              "displayName": "display-name-value",
              "userId": "userId-value",
              "email": "email-value"
              }
          ]
    }
    ```    
2. <span data-ttu-id="3079c-160">Use o seguinte para promover o membro a um proprietário, onde &lt; group_id &gt; , &lt; channel_id &gt; e &lt; ID &gt; serão retornados da chamada anterior.</span><span class="sxs-lookup"><span data-stu-id="3079c-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="3079c-161">Observe que &lt; ID &gt; e &lt; userid &gt; retornados da chamada anterior não são iguais e não são intercambiáveis.</span><span class="sxs-lookup"><span data-stu-id="3079c-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="3079c-162">Certifique-se de usar &lt; ID &gt; .</span><span class="sxs-lookup"><span data-stu-id="3079c-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="3079c-163">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="3079c-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="3079c-164">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="3079c-164">**Response**</span></span>

    ```Graph API
    HTTP/1.1 200 OK
    Content-type: application/json

    {
      "@odata.context": "https://graph.microsoft.com/beta/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a><span data-ttu-id="3079c-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3079c-165">Related topics</span></span>

- [<span data-ttu-id="3079c-166">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="3079c-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="3079c-167">Usar a API do Microsoft Graph para trabalhar com o Teams</span><span class="sxs-lookup"><span data-stu-id="3079c-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="3079c-168">Canais de lista</span><span class="sxs-lookup"><span data-stu-id="3079c-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="3079c-169">Criar canal</span><span class="sxs-lookup"><span data-stu-id="3079c-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="3079c-170">Adicionar membro ao canal</span><span class="sxs-lookup"><span data-stu-id="3079c-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="3079c-171">Atualizar membro no canal</span><span class="sxs-lookup"><span data-stu-id="3079c-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="3079c-172">Remover membro do canal</span><span class="sxs-lookup"><span data-stu-id="3079c-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
