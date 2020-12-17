---
title: Gerenciar o ciclo de vida de canais privados no Microsoft Teams
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
description: Confira como gerenciar o ciclo de vida dos canais privados na sua organização.
ms.openlocfilehash: 336d97071c30bca145d26f4c853d5bb30265721f
ms.sourcegitcommit: 68dffc3aca46992448bc2be0689bfd352e016316
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49601656"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="9f89a-103">Gerenciar o ciclo de vida de canais privados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f89a-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="9f89a-104">Aqui você encontrará a orientação que precisa para gerenciar o ciclo de vida dos [canais privados](private-channels.md) na sua organização.</span><span class="sxs-lookup"><span data-stu-id="9f89a-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f89a-105">Se você estiver usando as etapas do Windows PowerShell nesse artigo para gerenciar os canais privados, deve instalar e usar o módulo de visualização pública do PowerShell do Teams a partir da [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span><span class="sxs-lookup"><span data-stu-id="9f89a-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the Teams PowerShell public preview module from the [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> <span data-ttu-id="9f89a-106">Para etapas sobre como instalar o módulo, confira [Instalar o PowerShell do Microsoft Teams](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="9f89a-106">For steps on how to install the module, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span> <span data-ttu-id="9f89a-107">O módulo mais recente do Windows PowerShell do Teams para Disponibilidade Geral não tem suporte para gerenciamento de canais privados.</span><span class="sxs-lookup"><span data-stu-id="9f89a-107">The latest General Availability Teams PowerShell module doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="9f89a-108">Defina se os proprietários e membros podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="9f89a-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="9f89a-109">Os proprietários de equipe podem desativar ou ativar a capacidade dos membros de criar canais privados nas configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="9f89a-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="9f89a-110">Para fazer isso na guia **Configurações** de uma equipe, desative ou ative em **Permitir aos membros criar canais privados**.</span><span class="sxs-lookup"><span data-stu-id="9f89a-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="9f89a-111">Como administrador você pode usar a API do Graph para controlar se os membros podem criar canais privados em equipes específicas.</span><span class="sxs-lookup"><span data-stu-id="9f89a-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="9f89a-112">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="9f89a-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="9f89a-113">Defina se os usuários em sua organização podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="9f89a-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="9f89a-114">Como administrador, você pode definir políticas usando o centro de Administração do Microsoft Teams ou do Windows PowerShell para controlar quais usuários em sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="9f89a-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9f89a-115">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f89a-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="9f89a-116">Use as políticas para controlar quais usuários em sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="9f89a-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="9f89a-117">Para saber mais, confira o artigo [Gerenciar políticas de equipes no Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9f89a-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9f89a-118">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f89a-118">Using PowerShell</span></span>

<span data-ttu-id="9f89a-119">Use **CsTeamsChannelsPolicy** para definir quais usuários em sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="9f89a-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="9f89a-120">Confira o parâmetro **AllowPrivateChannelCreation** para **verdadeiro** para permitir aos usuários atribuídos com a política a criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="9f89a-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="9f89a-121">Definir o parâmetro para **falso** desativa a capacidade de criar canais privados para usuários atribuídos com a política.</span><span class="sxs-lookup"><span data-stu-id="9f89a-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="9f89a-122">Para saber mais, confira [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9f89a-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="9f89a-123">Criar um canal privado em nome do proprietário de equipe</span><span class="sxs-lookup"><span data-stu-id="9f89a-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="9f89a-124">Como administrador você pode usar o Windows PowerShell ou a API do Graph para criar um canal privado em nome do proprietário de equipe.</span><span class="sxs-lookup"><span data-stu-id="9f89a-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="9f89a-125">Por exemplo, você pode querer fazer isso se sua organização quiser centralizar a criação de canais privados.</span><span class="sxs-lookup"><span data-stu-id="9f89a-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9f89a-126">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f89a-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="9f89a-127">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="9f89a-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="9f89a-128">Obter uma lista de todas as mensagens do canal privado</span><span class="sxs-lookup"><span data-stu-id="9f89a-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="9f89a-129">Você pode obter uma lista de todas as mensagens e respostas postadas em um canal privado para propósitos de arquivo ou auditoria.</span><span class="sxs-lookup"><span data-stu-id="9f89a-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="9f89a-130">Veja aqui como usar a API do Graph para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="9f89a-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="9f89a-131">Encontrar URLs do Microsoft Office SharePoint Online para todos os canais privados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="9f89a-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="9f89a-132">Se estiver procurando executar o eDiscovery, reter legalmente arquivos em um canal privado ou construir um aplicativo personalizado que coloca os arquivos em canais privados específicos, precisará de uma maneira de consultar os conjuntos exclusivos de sites do Microsoft Office SharePoint Online criados para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="9f89a-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="9f89a-133">Como administrador, você pode usar os comandos do Windows PowerShell ou das APIs do Graph para consultar essas URLs.</span><span class="sxs-lookup"><span data-stu-id="9f89a-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9f89a-134">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f89a-134">Using PowerShell</span></span>

1. <span data-ttu-id="9f89a-135">Instalar e conectar com sua conta de administrador do [Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="9f89a-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="9f89a-136">Executar o seguinte, onde &lt;group_id&gt; é a ID de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="9f89a-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="9f89a-137">(Você pode encontrar facilmente a ID de grupo no link para a equipe.)</span><span class="sxs-lookup"><span data-stu-id="9f89a-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="9f89a-138">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="9f89a-138">Using Graph API</span></span>

<span data-ttu-id="9f89a-139">Você pode tentar esses comandos através do [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="9f89a-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="9f89a-140">Use o seguinte para obter a lista de IDs de canal privado para uma determinada equipe, onde <group_id> é a ID de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="9f89a-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="9f89a-141">Você precisará disso nas chamadas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="9f89a-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="9f89a-142">(Você pode encontrar facilmente a ID de grupo no link para a equipe.)</span><span class="sxs-lookup"><span data-stu-id="9f89a-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="9f89a-143">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9f89a-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="9f89a-144">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="9f89a-144">**Response**</span></span>

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

2. <span data-ttu-id="9f89a-145">Para cada canal privado que você quiser obter a URL do Microsoft Office SharePoint Online, faça a seguinte solicitação, onde &lt;channel_id&gt; é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="9f89a-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="9f89a-146">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9f89a-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="9f89a-147">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="9f89a-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="9f89a-148">Listar e atualizar os papeis de proprietários e membros em um canal privado</span><span class="sxs-lookup"><span data-stu-id="9f89a-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="9f89a-149">Se desejar listar os proprietários e membros de um canal privado para decidir se precisa promover certos membros do canal privado para um proprietário.</span><span class="sxs-lookup"><span data-stu-id="9f89a-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="9f89a-150">Isso pode acontecer quando você tem proprietários de canais privados que deixaram a organização e o canal privado requer que os administradores ajudem a reivindicar a propriedade do canal.</span><span class="sxs-lookup"><span data-stu-id="9f89a-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="9f89a-151">Como administrador, você pode usar o centro de Administração do Microsoft Teams, do Windows PowerShell ou da API do Graph para realizar essas ações.</span><span class="sxs-lookup"><span data-stu-id="9f89a-151">As an admin, you can use the Microsoft Teams admin center, PowerShell, or Graph API to perform these actions.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="9f89a-152">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9f89a-152">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="9f89a-153">Para saber como gerenciar os membros da equipe usando o centro de Administração do Microsoft Teams, confira [Gerenciar equipes no centro de Administração do Microsoft Teams](manage-teams-in-modern-portal.md).</span><span class="sxs-lookup"><span data-stu-id="9f89a-153">To learn how to manage team members using the Microsoft Teams admin center, see [Manage teams in the Microsoft Teams admin center](manage-teams-in-modern-portal.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="9f89a-154">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f89a-154">Using PowerShell</span></span>

1. <span data-ttu-id="9f89a-155">Executar o seguinte, onde &lt;group_id&gt; é a ID de grupo da equipe e &lt;channel_name&gt; é o nome do canal.</span><span class="sxs-lookup"><span data-stu-id="9f89a-155">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="9f89a-156">Promover um membro a proprietário.</span><span class="sxs-lookup"><span data-stu-id="9f89a-156">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="9f89a-157">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="9f89a-157">Using Graph API</span></span>

<span data-ttu-id="9f89a-158">Você pode tentar esses comandos através do [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="9f89a-158">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="9f89a-159">Executar o seguinte, onde &lt;group_id&gt; é a ID de grupo da equipe e &lt;channel_id&gt; é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="9f89a-159">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="9f89a-160">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9f89a-160">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="9f89a-161">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="9f89a-161">**Response**</span></span>

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
2. <span data-ttu-id="9f89a-162">Use o seguinte para promover o membro a um proprietário, onde &lt;group_id&gt;, &lt;channel_id&gt; e &lt;id&gt; são retornadas da chamada anterior.</span><span class="sxs-lookup"><span data-stu-id="9f89a-162">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="9f89a-163">Observe que &lt;id&gt; e &lt;userId&gt; retornadas das chamadas anteriores não são as mesmas e não são intercambiáveis.</span><span class="sxs-lookup"><span data-stu-id="9f89a-163">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="9f89a-164">Certifique-se de usar &lt;id&gt;.</span><span class="sxs-lookup"><span data-stu-id="9f89a-164">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="9f89a-165">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9f89a-165">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="9f89a-166">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="9f89a-166">**Response**</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="9f89a-167">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9f89a-167">Related topics</span></span>

- [<span data-ttu-id="9f89a-168">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="9f89a-168">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="9f89a-169">Usar a API do Microsoft Graph para trabalhar com o Teams</span><span class="sxs-lookup"><span data-stu-id="9f89a-169">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="9f89a-170">Listar canais</span><span class="sxs-lookup"><span data-stu-id="9f89a-170">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="9f89a-171">Criar um canal</span><span class="sxs-lookup"><span data-stu-id="9f89a-171">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="9f89a-172">Adicionar membro ao canal</span><span class="sxs-lookup"><span data-stu-id="9f89a-172">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="9f89a-173">Atualizar membro no canal</span><span class="sxs-lookup"><span data-stu-id="9f89a-173">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="9f89a-174">Remover membro do canal</span><span class="sxs-lookup"><span data-stu-id="9f89a-174">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
