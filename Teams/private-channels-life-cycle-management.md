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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar o ciclo de vida de canais privados em sua organização.
ms.openlocfilehash: 5fe3f29559e62b6b6b11833304aa7bb13206fe6a
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37969409"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="d7761-103">Gerenciar o ciclo de vida de canais privados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7761-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="d7761-104">Aqui você encontrará as diretrizes necessárias para gerenciar o ciclo de vida de [canais privados](private-channels.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d7761-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="d7761-105">Definir se os membros da equipe podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="d7761-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="d7761-106">Os proprietários da equipe podem desativar ou ativar a capacidade de os Membros criarem canais privados nas configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="d7761-106">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="d7761-107">Para fazer isso, na guia **configurações** da equipe, desative ou ative **permitir que os membros criem canais privados**.</span><span class="sxs-lookup"><span data-stu-id="d7761-107">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="d7761-108">Como administrador, você pode usar a API de gráficos para controlar se os membros podem criar canais privados em equipes específicas.</span><span class="sxs-lookup"><span data-stu-id="d7761-108">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="d7761-109">Aqui está um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d7761-109">Here's an example.</span></span>

```
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="d7761-110">Definir se os usuários em sua organização podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="d7761-110">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="d7761-111">Como administrador, você pode definir políticas usando o centro de administração do Microsoft Teams ou o PowerShell para controlar quais usuários na sua organização têm permissão para criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="d7761-111">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="d7761-112">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7761-112">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="d7761-113">Use as políticas do teams para definir quais usuários na sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="d7761-113">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="d7761-114">Para saber mais, consulte [gerenciar políticas de equipes no Microsoft Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d7761-114">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d7761-115">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7761-115">Using PowerShell</span></span>

<span data-ttu-id="d7761-116">Use o **CsTeamsChannelsPolicy** para definir quais usuários da sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="d7761-116">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="d7761-117">Defina o parâmetro **AllowPrivateChannelCreation** como **true** para permitir que os usuários atribuídos à política criem canais privados.</span><span class="sxs-lookup"><span data-stu-id="d7761-117">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="d7761-118">Definir o parâmetro como **false** desativa a capacidade de criar canais privados para os usuários atribuídos à política.</span><span class="sxs-lookup"><span data-stu-id="d7761-118">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="d7761-119">Para saber mais, confira [novo – CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d7761-119">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="d7761-120">Criar um canal privado em nome de um proprietário de equipe</span><span class="sxs-lookup"><span data-stu-id="d7761-120">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="d7761-121">Como administrador, você pode usar a API do PowerShell ou do Graph para criar um canal privado em nome de um proprietário de equipe.</span><span class="sxs-lookup"><span data-stu-id="d7761-121">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="d7761-122">Por exemplo, você pode querer fazer isso se a sua organização quer centralizar a criação de canais privados.</span><span class="sxs-lookup"><span data-stu-id="d7761-122">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d7761-123">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7761-123">Using PowerShell</span></span>

```
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName “<Channel_Name>” –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="d7761-124">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="d7761-124">Using Graph API</span></span>

```
POST /teams/{id}/channels
{ "membershipType": "Private",
  "displayName": "<Channel_Name>",
  "members":[{    
           "@odata.type":"#microsoft.graph.aadUserConversationMember",
           "user@odata.bind":"https://graph.microsoft.com/beta/users('<user_id>')",
           "roles":["owner"]
            }]
```

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="d7761-125">Obter uma lista de todas as mensagens particulares do canal privado</span><span class="sxs-lookup"><span data-stu-id="d7761-125">Get a list of all private channel messages</span></span>

<span data-ttu-id="d7761-126">Você pode querer obter uma lista de todas as mensagens e respostas postadas em um canal privado para fins de arquivamento e auditoria.</span><span class="sxs-lookup"><span data-stu-id="d7761-126">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="d7761-127">Veja como usar a API de gráfico para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="d7761-127">Here's how to use Graph API to do this.</span></span>

```
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="d7761-128">Localizar URLs do SharePoint para todos os canais particulares em uma equipe</span><span class="sxs-lookup"><span data-stu-id="d7761-128">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="d7761-129">Se você estiver procurando executar o descoberta eletrônica ou o controle legal em arquivos em um canal privado ou procurando criar um aplicativo de linha de negócios que coloca arquivos em canais particulares específicos, você desejará uma maneira de consultar os conjuntos de sites exclusivos do SharePoint criados para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="d7761-129">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a line-of-business app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="d7761-130">Como administrador, você pode usar os comandos do PowerShell ou de APIs de gráfico para consultar essas URLs.</span><span class="sxs-lookup"><span data-stu-id="d7761-130">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d7761-131">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7761-131">Using PowerShell</span></span>

1. <span data-ttu-id="d7761-132">Instale e conecte-se ao [Shell de gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) com sua conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="d7761-132">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="d7761-133">Execute o seguinte, onde &lt;group_id&gt; é a ID do grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="d7761-133">Run the following, where &lt;group_id&gt; is the group Id of the team.</span></span> <span data-ttu-id="d7761-134">(Você pode localizar facilmente a identificação do grupo no link para a equipe.)</span><span class="sxs-lookup"><span data-stu-id="d7761-134">(You can easily find the group Id in the link to the team.)</span></span>

    ```
    $sites = get-sposite -template "teamchannel#0"
    $groupID = “<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="d7761-135">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="d7761-135">Using Graph API</span></span>

<span data-ttu-id="d7761-136">Você pode experimentar esses comandos por meio do [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="d7761-136">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="d7761-137">Use o seguinte para obter a lista de IDs de canais particulares para uma determinada equipe, onde <group_id> é a ID de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="d7761-137">Use the following to get the list of private channel Ids for a given team, where <group_id> is the group Id of the team.</span></span> <span data-ttu-id="d7761-138">Você precisará disso nas chamadas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="d7761-138">You'll need this in subsequent calls.</span></span> <span data-ttu-id="d7761-139">(Você pode localizar facilmente a identificação do grupo no link para a equipe).</span><span class="sxs-lookup"><span data-stu-id="d7761-139">(You can easily find the group Id in the link to the team).</span></span>

    <span data-ttu-id="d7761-140">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="d7761-140">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="d7761-141">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="d7761-141">**Response**</span></span>

    ```
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

2. <span data-ttu-id="d7761-142">Para cada canal privado do qual você deseja obter a URL do SharePoint, faça a seguinte solicitação, &lt;onde&gt; channel_id é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="d7761-142">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="d7761-143">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="d7761-143">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="d7761-144">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="d7761-144">**Response**</span></span>

    ```
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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="d7761-145">Listar e atualizar funções de proprietários e membros em um canal privado</span><span class="sxs-lookup"><span data-stu-id="d7761-145">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="d7761-146">Talvez você queira listar os proprietários e os membros de um canal privado para decidir se precisa promover certos membros do canal privado para um proprietário.</span><span class="sxs-lookup"><span data-stu-id="d7761-146">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="d7761-147">Isso pode acontecer quando você tem proprietários de canais privados que saíram da organização e o canal privado exige que a ajuda do administrador solicite a posse do canal.</span><span class="sxs-lookup"><span data-stu-id="d7761-147">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="d7761-148">Como administrador, você pode usar os comandos do PowerShell ou de APIs de gráfico para consultar essas URLs.</span><span class="sxs-lookup"><span data-stu-id="d7761-148">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="d7761-149">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7761-149">Using PowerShell</span></span>

1. <span data-ttu-id="d7761-150">Instale e conecte-se ao [módulo do Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) com sua conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="d7761-150">Install and connect to the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) with your admin account.</span></span>
2. <span data-ttu-id="d7761-151">Execute o seguinte, onde &lt;group_id&gt; é a ID do grupo da equipe e &lt;channel_id&gt; é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="d7761-151">Run the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="d7761-152">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="d7761-152">**Request**</span></span>

    ```
    Get-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" 
    ```
    
    <span data-ttu-id="d7761-153">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="d7761-153">**Response**</span></span>

    ```
    HTTP/1.1 200 OK Content-type: application/json
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

3. <span data-ttu-id="d7761-154">Promover um membro a um proprietário.</span><span class="sxs-lookup"><span data-stu-id="d7761-154">Promote a member to an owner.</span></span>

    ```
    Add-TeamChannelUser -GroupId <group_id> -MembershipType Private -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="d7761-155">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="d7761-155">Using Graph API</span></span>

<span data-ttu-id="d7761-156">Você pode experimentar esses comandos por meio do [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="d7761-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="d7761-157">Use o seguinte, onde &lt;group_id&gt; é a ID do grupo da equipe e &lt;channel_id&gt; é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="d7761-157">Use the following, where &lt;group_id&gt; is the group Id of the team and &lt;channel_id&gt; is the channel Id.</span></span>

    <span data-ttu-id="d7761-158">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="d7761-158">**Request**</span></span>

    ```
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="d7761-159">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="d7761-159">**Response**</span></span>

    ```
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
2.  <span data-ttu-id="d7761-160">Use o seguinte para promover o membro a um proprietário, onde &lt;group_id&gt;, &lt;channel_id&gt;e &lt;ID&gt; são retornados da chamada anterior.</span><span class="sxs-lookup"><span data-stu-id="d7761-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="d7761-161">Observe que &lt;ID&gt; e &lt;userid&gt; retornados da chamada anterior não são iguais e não são intercambiáveis.</span><span class="sxs-lookup"><span data-stu-id="d7761-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="d7761-162">Certifique-se de &lt;usar&gt;ID.</span><span class="sxs-lookup"><span data-stu-id="d7761-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="d7761-163">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="d7761-163">**Request**</span></span>

    ```
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="d7761-164">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="d7761-164">**Response**</span></span>

    ```
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

## <a name="related-topics"></a><span data-ttu-id="d7761-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d7761-165">Related topics</span></span>

- [<span data-ttu-id="d7761-166">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="d7761-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="d7761-167">Usar a API do Microsoft Graph para trabalhar com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7761-167">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="d7761-168">Canais de lista</span><span class="sxs-lookup"><span data-stu-id="d7761-168">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="d7761-169">Criar canal</span><span class="sxs-lookup"><span data-stu-id="d7761-169">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="d7761-170">Adicionar membro ao canal</span><span class="sxs-lookup"><span data-stu-id="d7761-170">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="d7761-171">Atualizar membro no canal</span><span class="sxs-lookup"><span data-stu-id="d7761-171">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="d7761-172">Remover membro do canal</span><span class="sxs-lookup"><span data-stu-id="d7761-172">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)