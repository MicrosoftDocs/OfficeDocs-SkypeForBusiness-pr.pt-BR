---
title: Gerenciar os canais privados no Microsoft Teams com a API do Graph
author: MikePlumleyMSFT
ms.author: mikeplum
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
description: Saiba como gerenciar canais privados em sua organização usando a API do Graph.
ms.openlocfilehash: e97d808bd9f544ef611b0b5e4b0456d302b4013d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117739"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="a4b52-103">Gerenciar o ciclo de vida de canais privados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a4b52-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="a4b52-104">Aqui você encontrará as diretrizes que você precisa gerenciar para usar a API graph para gerenciar canais privados do [Teams](./private-channels.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a4b52-104">Here you'll find the guidance you need to manage use the Graph API to manage [Teams private channels](./private-channels.md) in your organization.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="a4b52-105">Defina se os proprietários e membros podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="a4b52-105">Set whether team members can create private channels</span></span>

<span data-ttu-id="a4b52-106">Como administrador você pode usar a API do Graph para controlar se os membros podem criar canais privados em equipes específicas.</span><span class="sxs-lookup"><span data-stu-id="a4b52-106">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="a4b52-107">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a4b52-107">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="a4b52-108">Criar um canal privado em nome do proprietário de equipe</span><span class="sxs-lookup"><span data-stu-id="a4b52-108">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="a4b52-109">Como administrador, você pode usar a API do Graph para criar um canal privado em nome de um proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="a4b52-109">As an admin, you can use the Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="a4b52-110">Por exemplo, você pode querer fazer isso se sua organização quiser centralizar a criação de canais privados.</span><span class="sxs-lookup"><span data-stu-id="a4b52-110">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="a4b52-111">Obter uma lista de todas as mensagens do canal privado</span><span class="sxs-lookup"><span data-stu-id="a4b52-111">Get a list of all private channel messages</span></span>

<span data-ttu-id="a4b52-112">Você pode obter uma lista de todas as mensagens e respostas postadas em um canal privado para propósitos de arquivo ou auditoria.</span><span class="sxs-lookup"><span data-stu-id="a4b52-112">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="a4b52-113">Veja aqui como usar a API do Graph para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="a4b52-113">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="a4b52-114">Encontrar URLs do Microsoft Office SharePoint Online para todos os canais privados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="a4b52-114">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="a4b52-115">Se estiver procurando executar o eDiscovery, reter legalmente arquivos em um canal privado ou construir um aplicativo personalizado que coloca os arquivos em canais privados específicos, precisará de uma maneira de consultar os conjuntos exclusivos de sites do Microsoft Office SharePoint Online criados para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="a4b52-115">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="a4b52-116">Como administrador, você pode usar comandos de APIs do Graph para consultar essas URLs.</span><span class="sxs-lookup"><span data-stu-id="a4b52-116">As an admin, you can use Graph APIs commands to query these URLs.</span></span>

<span data-ttu-id="a4b52-117">Você pode tentar esses comandos através do [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="a4b52-117">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="a4b52-118">Use o seguinte para obter a lista de IDs de canal privado para uma determinada equipe, onde <group_id> é a ID de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="a4b52-118">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="a4b52-119">Você precisará disso nas chamadas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="a4b52-119">You'll need this in subsequent calls.</span></span> <span data-ttu-id="a4b52-120">(Você pode encontrar facilmente a ID de grupo no link para a equipe.)</span><span class="sxs-lookup"><span data-stu-id="a4b52-120">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="a4b52-121">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="a4b52-121">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="a4b52-122">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="a4b52-122">**Response**</span></span>

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

2. <span data-ttu-id="a4b52-123">Para cada canal privado que você quiser obter a URL do Microsoft Office SharePoint Online, faça a seguinte solicitação, onde &lt;channel_id&gt; é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="a4b52-123">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="a4b52-124">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="a4b52-124">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="a4b52-125">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="a4b52-125">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="a4b52-126">Listar e atualizar os papeis de proprietários e membros em um canal privado</span><span class="sxs-lookup"><span data-stu-id="a4b52-126">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="a4b52-127">Se desejar listar os proprietários e membros de um canal privado para decidir se precisa promover certos membros do canal privado para um proprietário.</span><span class="sxs-lookup"><span data-stu-id="a4b52-127">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="a4b52-128">Isso pode acontecer quando você tem proprietários de canais privados que deixaram a organização e o canal privado requer que os administradores ajudem a reivindicar a propriedade do canal.</span><span class="sxs-lookup"><span data-stu-id="a4b52-128">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="a4b52-129">Como administrador, você pode usar a API do Graph para executar essas ações.</span><span class="sxs-lookup"><span data-stu-id="a4b52-129">As an admin, you can use the Graph API to perform these actions.</span></span>

<span data-ttu-id="a4b52-130">Você pode tentar esses comandos através do [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="a4b52-130">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="a4b52-131">Executar o seguinte, onde &lt;group_id&gt; é a ID de grupo da equipe e &lt;channel_id&gt; é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="a4b52-131">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="a4b52-132">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="a4b52-132">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="a4b52-133">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="a4b52-133">**Response**</span></span>

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
2. <span data-ttu-id="a4b52-134">Use o seguinte para promover o membro a um proprietário, onde &lt;group_id&gt;, &lt;channel_id&gt; e &lt;id&gt; são retornadas da chamada anterior.</span><span class="sxs-lookup"><span data-stu-id="a4b52-134">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="a4b52-135">Observe que &lt;id&gt; e &lt;userId&gt; retornadas das chamadas anteriores não são as mesmas e não são intercambiáveis.</span><span class="sxs-lookup"><span data-stu-id="a4b52-135">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="a4b52-136">Certifique-se de usar &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="a4b52-136">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="a4b52-137">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="a4b52-137">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="a4b52-138">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="a4b52-138">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="a4b52-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a4b52-139">Related topics</span></span>

[<span data-ttu-id="a4b52-140">Usar a API do Microsoft Graph para trabalhar com o Teams</span><span class="sxs-lookup"><span data-stu-id="a4b52-140">Use the Microsoft Graph API to work with Teams</span></span>](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[<span data-ttu-id="a4b52-141">Listar canais</span><span class="sxs-lookup"><span data-stu-id="a4b52-141">List channels</span></span>](/graph/api/channel-list)

[<span data-ttu-id="a4b52-142">Criar um canal</span><span class="sxs-lookup"><span data-stu-id="a4b52-142">Create channel</span></span>](/graph/api/channel-post)

[<span data-ttu-id="a4b52-143">Adicionar membro ao canal</span><span class="sxs-lookup"><span data-stu-id="a4b52-143">Add member to channel</span></span>](/graph/api/conversationmember-add)

[<span data-ttu-id="a4b52-144">Atualizar membro no canal</span><span class="sxs-lookup"><span data-stu-id="a4b52-144">Update member in channel</span></span>](/graph/api/conversationmember-update)

[<span data-ttu-id="a4b52-145">Remover membro do canal</span><span class="sxs-lookup"><span data-stu-id="a4b52-145">Remove member from channel</span></span>](/graph/api/conversationmember-delete)