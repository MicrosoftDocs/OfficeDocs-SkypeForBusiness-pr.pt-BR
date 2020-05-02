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
ms.openlocfilehash: 10746605895732af19a43ffb85df06a81ae34316
ms.sourcegitcommit: 3325fd9de57367e9dd60685d1fef096921441a76
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "43997242"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a><span data-ttu-id="5fbcb-103">Gerenciar o ciclo de vida de canais privados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5fbcb-103">Manage the life cycle of private channels in Microsoft Teams</span></span>

<span data-ttu-id="5fbcb-104">Aqui você encontrará as diretrizes necessárias para gerenciar o ciclo de vida de [canais privados](private-channels.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-104">Here you'll find the guidance you need to manage the life cycle of [private channels](private-channels.md) in your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fbcb-105">Se estiver usando as etapas do PowerShell neste artigo para gerenciar canais privados, você deve instalar e usar a versão mais recente do módulo do PowerShell do teams a partir da Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-105">If you're using the PowerShell steps in this article to manage private channels, you must install and use the latest version of the Teams PowerShell module from the PowerShell Test Gallery.</span></span> <span data-ttu-id="5fbcb-106">Para ver as etapas sobre como fazer isso, confira [instalar o módulo PowerShell do teams mais recente na Galeria de teste do PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-106">For steps on how to do this, see [Install the latest Teams PowerShell module from the PowerShell Test Gallery](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).</span></span> <span data-ttu-id="5fbcb-107">A versão mais recente disponível publicamente do módulo Teams PowerShell (atualmente [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) não oferece suporte ao gerenciamento de canais privados.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-107">The latest publicly available version of the Teams PowerShell module (currently [1.0.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.3)) doesn't support managing private channels.</span></span>

## <a name="set-whether-team-members-can-create-private-channels"></a><span data-ttu-id="5fbcb-108">Definir se os membros da equipe podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="5fbcb-108">Set whether team members can create private channels</span></span>

<span data-ttu-id="5fbcb-109">Os proprietários da equipe podem desativar ou ativar a capacidade de os Membros criarem canais privados nas configurações da equipe.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-109">Team owners can turn off or turn on the ability for members to create private channels in team settings.</span></span> <span data-ttu-id="5fbcb-110">Para fazer isso, na guia **configurações** da equipe, desative ou ative **permitir que os membros criem canais privados**.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-110">To do this, on the **Settings** tab for the team, turn off or turn on **Allow members to create private channels**.</span></span>

<span data-ttu-id="5fbcb-111">Como administrador, você pode usar a API de gráficos para controlar se os membros podem criar canais privados em equipes específicas.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-111">As an admin, you can use Graph API to control whether members can create private channels in specific teams.</span></span> <span data-ttu-id="5fbcb-112">Aqui está um exemplo.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-112">Here's an example.</span></span>

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a><span data-ttu-id="5fbcb-113">Definir se os usuários em sua organização podem criar canais privados</span><span class="sxs-lookup"><span data-stu-id="5fbcb-113">Set whether users in your organization can create private channels</span></span>

<span data-ttu-id="5fbcb-114">Como administrador, você pode definir políticas usando o centro de administração do Microsoft Teams ou o PowerShell para controlar quais usuários na sua organização têm permissão para criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-114">As an admin, you can set policies by using the Microsoft Teams admin center or PowerShell to control which users in your organization are allowed to create private channels.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="5fbcb-115">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5fbcb-115">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="5fbcb-116">Use as políticas do teams para definir quais usuários na sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-116">Use teams policies to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="5fbcb-117">Para saber mais, consulte [gerenciar políticas de equipes no Microsoft Teams](teams-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-117">To learn more, see [Manage teams policies in Teams](teams-policies.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5fbcb-118">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fbcb-118">Using PowerShell</span></span>

<span data-ttu-id="5fbcb-119">Use o **CsTeamsChannelsPolicy** para definir quais usuários da sua organização podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-119">Use **CsTeamsChannelsPolicy** to set which users in your organization are allowed to create private channels.</span></span> <span data-ttu-id="5fbcb-120">Defina o parâmetro **AllowPrivateChannelCreation** como **true** para permitir que os usuários atribuídos à política criem canais privados.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-120">Set the **AllowPrivateChannelCreation** parameter to **true** to allow users who are assigned the policy to create private channels.</span></span> <span data-ttu-id="5fbcb-121">Definir o parâmetro como **false** desativa a capacidade de criar canais privados para os usuários atribuídos à política.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-121">Setting the parameter to **false** turns off the ability to create private channels for users who are assigned the policy.</span></span>

<span data-ttu-id="5fbcb-122">Para saber mais, confira [novo – CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-122">To learn more, see [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).</span></span>

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a><span data-ttu-id="5fbcb-123">Criar um canal privado em nome de um proprietário de equipe</span><span class="sxs-lookup"><span data-stu-id="5fbcb-123">Create a private channel on behalf of a team owner</span></span>

<span data-ttu-id="5fbcb-124">Como administrador, você pode usar a API do PowerShell ou do Graph para criar um canal privado em nome de um proprietário de equipe.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-124">As an admin, you can use PowerShell or Graph API to create a private channel on behalf of a team owner.</span></span> <span data-ttu-id="5fbcb-125">Por exemplo, você pode querer fazer isso se a sua organização quer centralizar a criação de canais privados.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-125">For example, you may want to do this if your organization wants to centralize creation of private channels.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5fbcb-126">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fbcb-126">Using PowerShell</span></span>

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a><span data-ttu-id="5fbcb-127">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="5fbcb-127">Using Graph API</span></span>

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

## <a name="get-a-list-of-all-private-channel-messages"></a><span data-ttu-id="5fbcb-128">Obter uma lista de todas as mensagens particulares do canal privado</span><span class="sxs-lookup"><span data-stu-id="5fbcb-128">Get a list of all private channel messages</span></span>

<span data-ttu-id="5fbcb-129">Você pode querer obter uma lista de todas as mensagens e respostas postadas em um canal privado para fins de arquivamento e auditoria.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-129">You may want to get a list of all messages and replies posted in a private channel for archiving and auditing purposes.</span></span>  <span data-ttu-id="5fbcb-130">Veja como usar a API de gráfico para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-130">Here's how to use Graph API to do this.</span></span>

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a><span data-ttu-id="5fbcb-131">Localizar URLs do SharePoint para todos os canais particulares em uma equipe</span><span class="sxs-lookup"><span data-stu-id="5fbcb-131">Find SharePoint URLs for all private channels in a team</span></span>

<span data-ttu-id="5fbcb-132">Se você estiver procurando executar o descoberta eletrônica ou o controle legal em arquivos em um canal privado ou procurando criar um aplicativo personalizado que coloca arquivos em canais particulares específicos, você precisará de uma maneira de consultar os conjuntos de sites exclusivos do SharePoint criados para cada canal privado.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-132">Whether you're looking to perform eDiscovery or legal hold on files in a private channel or looking to build a custom app that places files in specific private channels, you'll want a way to query the unique SharePoint site collections that are created for each private channel.</span></span>

<span data-ttu-id="5fbcb-133">Como administrador, você pode usar os comandos do PowerShell ou de APIs de gráfico para consultar essas URLs.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-133">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5fbcb-134">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fbcb-134">Using PowerShell</span></span>

1. <span data-ttu-id="5fbcb-135">Instale e conecte-se ao [Shell de gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) com sua conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-135">Install and connect to the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) with your admin account.</span></span>
2. <span data-ttu-id="5fbcb-136">Execute o seguinte, onde &lt;group_id&gt; é a ID do grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-136">Run the following, where &lt;group_id&gt; is the Group ID of the team.</span></span> <span data-ttu-id="5fbcb-137">(Você pode localizar facilmente a identificação do grupo no link para a equipe.)</span><span class="sxs-lookup"><span data-stu-id="5fbcb-137">(You can easily find the Group ID in the link to the team.)</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a><span data-ttu-id="5fbcb-138">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="5fbcb-138">Using Graph API</span></span>

<span data-ttu-id="5fbcb-139">Você pode experimentar esses comandos por meio do [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-139">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="5fbcb-140">Use o seguinte para obter a lista de IDs de canais particulares para uma determinada equipe, onde <group_id> é a ID de grupo da equipe.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-140">Use the following to get the list of private channel IDs for a given team, where <group_id> is the group ID of the team.</span></span> <span data-ttu-id="5fbcb-141">Você precisará disso nas chamadas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-141">You'll need this in subsequent calls.</span></span> <span data-ttu-id="5fbcb-142">(Você pode localizar facilmente a identificação do grupo no link para a equipe).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-142">(You can easily find the group ID in the link to the team).</span></span>

    <span data-ttu-id="5fbcb-143">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5fbcb-143">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    <span data-ttu-id="5fbcb-144">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="5fbcb-144">**Response**</span></span>

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

2. <span data-ttu-id="5fbcb-145">Para cada canal privado do qual você deseja obter a URL do SharePoint, faça a seguinte solicitação, &lt;em&gt; que channel_id é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-145">For each private channel which you want to get the SharePoint URL, make the following request, where &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="5fbcb-146">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5fbcb-146">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    <span data-ttu-id="5fbcb-147">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="5fbcb-147">**Response**</span></span>

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a><span data-ttu-id="5fbcb-148">Listar e atualizar funções de proprietários e membros em um canal privado</span><span class="sxs-lookup"><span data-stu-id="5fbcb-148">List and update roles of owners and members in a private channel</span></span>

<span data-ttu-id="5fbcb-149">Talvez você queira listar os proprietários e os membros de um canal privado para decidir se precisa promover certos membros do canal privado para um proprietário.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-149">You may want to list out the owners and members of a private channel to decide whether you need to promote certain members of the private channel to an owner.</span></span> <span data-ttu-id="5fbcb-150">Isso pode acontecer quando você tem proprietários de canais privados que saíram da organização e o canal privado exige que a ajuda do administrador solicite a posse do canal.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-150">This can happen when you have owners of private channels who have left the organization and the private channel requires admin help to claim ownership of the channel.</span></span>

<span data-ttu-id="5fbcb-151">Como administrador, você pode usar os comandos do PowerShell ou de APIs de gráfico para consultar essas URLs.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-151">As an admin, you can use PowerShell or Graph APIs commands to query these URLs.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="5fbcb-152">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fbcb-152">Using PowerShell</span></span>

1. <span data-ttu-id="5fbcb-153">Execute o seguinte, onde &lt;group_id&gt; é a ID do grupo da equipe e &lt;channel_name&gt; é o nome do canal.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-153">Run the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_name&gt; is the channel name.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. <span data-ttu-id="5fbcb-154">Promover um membro a um proprietário.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-154">Promote a member to an owner.</span></span>

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a><span data-ttu-id="5fbcb-155">Usando a API do Graph</span><span class="sxs-lookup"><span data-stu-id="5fbcb-155">Using Graph API</span></span>

<span data-ttu-id="5fbcb-156">Você pode experimentar esses comandos por meio do [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-156">You can try these commands through [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

1. <span data-ttu-id="5fbcb-157">Use o seguinte, em &lt;que&gt; group_id é a ID do grupo da equipe &lt;e&gt; channel_id é a ID do canal.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-157">Use the following, where &lt;group_id&gt; is the group ID of the team and &lt;channel_id&gt; is the channel ID.</span></span>

    <span data-ttu-id="5fbcb-158">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5fbcb-158">**Request**</span></span>

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    <span data-ttu-id="5fbcb-159">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="5fbcb-159">**Response**</span></span>

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
2.     <span data-ttu-id="5fbcb-160">Use o seguinte para promover o membro a um proprietário, onde &lt;group_id&gt;, &lt;channel_id&gt;e &lt;ID&gt; serão retornados da chamada anterior.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-160">Use the following to promote the member to an owner, where &lt;group_id&gt;, &lt;channel_id&gt;, and &lt;id&gt; are returned from the previous call.</span></span> <span data-ttu-id="5fbcb-161">Observe que &lt;ID&gt; e &lt;userid&gt; retornados da chamada anterior não são iguais e não são intercambiáveis.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-161">Note that &lt;id&gt; and &lt;userId&gt; returned from the previous call aren't the same and aren't interchangeable.</span></span> <span data-ttu-id="5fbcb-162">Certifique-se de &lt;usar&gt;ID.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-162">Make sure you use &lt;id&gt;.</span></span>

    <span data-ttu-id="5fbcb-163">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5fbcb-163">**Request**</span></span>

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    <span data-ttu-id="5fbcb-164">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="5fbcb-164">**Response**</span></span>

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

## <a name="teams-powershell-module"></a><span data-ttu-id="5fbcb-165">Módulo do teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fbcb-165">Teams Powershell module</span></span>

### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="5fbcb-166">Instalar o módulo do PowerShell do teams mais recente na Galeria de teste do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fbcb-166">Install the latest Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="5fbcb-167">A versão mais recente disponível publicamente do módulo Teams PowerShell (atualmente [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) não oferece suporte ao gerenciamento de canais privados.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-167">The latest publicly available version of the Teams PowerShell module (currently [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) doesn't support managing private channels.</span></span> <span data-ttu-id="5fbcb-168">Use estas etapas para instalar a versão mais recente do módulo do teams PowerShell com suporte a canal privado (atualmente 1.0.21) na Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-168">Use these steps to install the latest version of the Teams PowerShell module with private channel support (currently 1.0.21) from the PowerShell Test Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="5fbcb-169">Não instale o módulo Teams PowerShell da Galeria de teste do PowerShell lado a lado com uma versão do módulo da Galeria pública do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-169">Don't install the Teams PowerShell module from the PowerShell Test Gallery side-by-side with a version of the module from the public PowerShell Gallery.</span></span> <span data-ttu-id="5fbcb-170">Siga estas etapas para desinstalar primeiro o módulo do teams PowerShell da galeria do PowerShell público e instalar a versão mais recente do módulo da Galeria de teste do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-170">Follow these steps to first uninstall the Teams PowerShell module from the public PowerShell Gallery, and then install the latest version of the module from the PowerShell Test Gallery.</span></span>

1. <span data-ttu-id="5fbcb-171">Feche todas as sessões existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-171">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="5fbcb-172">Inicie uma nova instância do módulo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-172">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="5fbcb-173">Execute o seguinte para desinstalar o módulo do teams PowerShell da galeria do PowerShell público:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-173">Run the following to uninstall the Teams PowerShell module from the public PowerShell Gallery:</span></span>

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. <span data-ttu-id="5fbcb-174">Feche todas as sessões existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-174">Close all existing PowerShell sessions.</span></span>
5. <span data-ttu-id="5fbcb-175">Inicie o módulo do Windows PowerShell novamente e, em seguida, execute o seguinte para registrar a Galeria de teste do PowerShell como uma fonte confiável:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-175">Start the Windows PowerShell module again, and then run the following to register the PowerShell Test Gallery as a trusted source:</span></span>

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. <span data-ttu-id="5fbcb-176">Execute o seguinte para instalar o módulo do PowerShell mais recente do teams a partir da Galeria de teste do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-176">Run the following to install the latest Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. <span data-ttu-id="5fbcb-177">Execute o seguinte para verificar se a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell foi instalada com êxito:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-177">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a><span data-ttu-id="5fbcb-178">Atualize para a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell</span><span class="sxs-lookup"><span data-stu-id="5fbcb-178">Update to the latest version of the Teams PowerShell module from the PowerShell Test Gallery</span></span>

<span data-ttu-id="5fbcb-179">Se você já tiver instalado o módulo do teams PowerShell da Galeria de teste do PowerShell, use as etapas a seguir para atualizar para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-179">If you already installed the Teams PowerShell module from the PowerShell Test Gallery, use the following steps to update to the latest version.</span></span>

1. <span data-ttu-id="5fbcb-180">Feche todas as sessões existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-180">Close all existing PowerShell sessions.</span></span>
2. <span data-ttu-id="5fbcb-181">Inicie uma nova instância do módulo do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-181">Start a new instance of the Windows PowerShell module.</span></span>
3. <span data-ttu-id="5fbcb-182">Execute o seguinte para atualizar a versão atualmente instalada do módulo do teams PowerShell a partir da Galeria de teste do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-182">Run the following to update the currently installed version of the Teams PowerShell module from the PowerShell Test Gallery:</span></span>

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. <span data-ttu-id="5fbcb-183">Execute o seguinte para verificar se a versão mais recente do módulo do teams PowerShell da Galeria de teste do PowerShell foi instalada com êxito:</span><span class="sxs-lookup"><span data-stu-id="5fbcb-183">Run the following to verify that the latest version of the Teams PowerShell module from the PowerShell Test Gallery is successfully installed:</span></span>

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a><span data-ttu-id="5fbcb-184">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5fbcb-184">Related topics</span></span>

- [<span data-ttu-id="5fbcb-185">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="5fbcb-185">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="5fbcb-186">Usar a API do Microsoft Graph para trabalhar com o Teams</span><span class="sxs-lookup"><span data-stu-id="5fbcb-186">Use the Microsoft Graph API to work with Teams</span></span>](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [<span data-ttu-id="5fbcb-187">Canais de lista</span><span class="sxs-lookup"><span data-stu-id="5fbcb-187">List channels</span></span>](https://docs.microsoft.com/graph/api/channel-list)
    - [<span data-ttu-id="5fbcb-188">Criar canal</span><span class="sxs-lookup"><span data-stu-id="5fbcb-188">Create channel</span></span>](https://docs.microsoft.com/graph/api/channel-post)
    - [<span data-ttu-id="5fbcb-189">Adicionar membro ao canal</span><span class="sxs-lookup"><span data-stu-id="5fbcb-189">Add member to channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [<span data-ttu-id="5fbcb-190">Atualizar membro no canal</span><span class="sxs-lookup"><span data-stu-id="5fbcb-190">Update member in channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [<span data-ttu-id="5fbcb-191">Remover membro do canal</span><span class="sxs-lookup"><span data-stu-id="5fbcb-191">Remove member from channel</span></span>](https://docs.microsoft.com/graph/api/conversationmember-delete)
