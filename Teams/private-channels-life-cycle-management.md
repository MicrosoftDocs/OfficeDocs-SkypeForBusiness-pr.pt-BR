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
ms.openlocfilehash: 45d9591eed2bd3a880d3ca3e2ceb2252bf6f8898
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326688"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gerenciar o ciclo de vida de canais privados no Microsoft Teams

Aqui você encontrará as diretrizes necessárias para gerenciar o ciclo de vida de [canais privados](private-channels.md) em sua organização.

> [!IMPORTANT]
> Se você estiver usando as etapas do PowerShell neste artigo para gerenciar canais privados, deve instalar e usar a versão de pré-lançamento mais recente do módulo do teams PowerShell da [Galeria de teste do PowerShell](https://www.poshtestgallery.com/packages/MicrosoftTeams/). Para ver as etapas sobre como instalar o módulo, consulte [instalar a versão de pré-lançamento do módulo do teams PowerShell](install-prerelease-teams-powershell-module.md). A versão mais recente disponível publicamente do módulo Teams PowerShell não oferece suporte ao gerenciamento de canais privados.

## <a name="set-whether-team-members-can-create-private-channels"></a>Definir se os membros da equipe podem criar canais privados

Os proprietários da equipe podem desativar ou ativar a capacidade de os Membros criarem canais privados nas configurações da equipe. Para fazer isso, na guia **configurações** da equipe, desative ou ative **permitir que os membros criem canais privados**.

Como administrador, você pode usar a API de gráficos para controlar se os membros podem criar canais privados em equipes específicas. Aqui está um exemplo.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Definir se os usuários em sua organização podem criar canais privados

Como administrador, você pode definir políticas usando o centro de administração do Microsoft Teams ou o PowerShell para controlar quais usuários na sua organização têm permissão para criar canais privados.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Use as políticas do teams para definir quais usuários na sua organização podem criar canais privados. Para saber mais, consulte [gerenciar políticas de equipes no Microsoft Teams](teams-policies.md).

### <a name="using-powershell"></a>Usando o PowerShell

Use o **CsTeamsChannelsPolicy** para definir quais usuários da sua organização podem criar canais privados. Defina o parâmetro **AllowPrivateChannelCreation** como **true** para permitir que os usuários atribuídos à política criem canais privados. Definir o parâmetro como **false** desativa a capacidade de criar canais privados para os usuários atribuídos à política.

Para saber mais, confira [novo – CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Criar um canal privado em nome de um proprietário de equipe

Como administrador, você pode usar a API do PowerShell ou do Graph para criar um canal privado em nome de um proprietário de equipe. Por exemplo, você pode querer fazer isso se a sua organização quer centralizar a criação de canais privados.

### <a name="using-powershell"></a>Usando o PowerShell

```PowerShell
New-TeamChannel –GroupId <Group_Id> –MembershipType Private –DisplayName "<Channel_Name>" –Owner <Owner_UPN>
```

### <a name="using-graph-api"></a>Usando a API do Graph

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Obter uma lista de todas as mensagens particulares do canal privado

Você pode querer obter uma lista de todas as mensagens e respostas postadas em um canal privado para fins de arquivamento e auditoria.  Veja como usar a API de gráfico para fazer isso.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Localizar URLs do SharePoint para todos os canais particulares em uma equipe

Se você estiver procurando executar o descoberta eletrônica ou o controle legal em arquivos em um canal privado ou procurando criar um aplicativo personalizado que coloca arquivos em canais particulares específicos, você precisará de uma maneira de consultar os conjuntos de sites exclusivos do SharePoint criados para cada canal privado.

Como administrador, você pode usar os comandos do PowerShell ou de APIs de gráfico para consultar essas URLs.

### <a name="using-powershell"></a>Usando o PowerShell

1. Instale e conecte-se ao [Shell de gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps) com sua conta de administrador.
2. Execute o seguinte, onde &lt; group_id &gt; é a ID do grupo da equipe. (Você pode localizar facilmente a identificação do grupo no link para a equipe.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Usando a API do Graph

Você pode experimentar esses comandos por meio do [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).

1. Use o seguinte para obter a lista de IDs de canais particulares para uma determinada equipe, onde <group_id> é a ID de grupo da equipe. Você precisará disso nas chamadas subsequentes. (Você pode localizar facilmente a identificação do grupo no link para a equipe).

    **Solicitação**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels?$filter=membershipType eq 'private'
    ```

    **Resposta**

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

2. Para cada canal privado do qual você deseja obter a URL do SharePoint, faça a seguinte solicitação, em que &lt; channel_id &gt; é a ID do canal.

    **Solicitação**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/filesFolder
    ```

    **Resposta**

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Listar e atualizar funções de proprietários e membros em um canal privado

Talvez você queira listar os proprietários e os membros de um canal privado para decidir se precisa promover certos membros do canal privado para um proprietário. Isso pode acontecer quando você tem proprietários de canais privados que saíram da organização e o canal privado exige que a ajuda do administrador solicite a posse do canal.

Como administrador, você pode usar o centro de administração do Microsoft Teams, o PowerShell ou a API de gráfico para executar essas ações.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Para saber como gerenciar os membros da equipe usando o centro de administração do Microsoft Teams, consulte [gerenciar equipes no centro de administração do Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="using-powershell"></a>Usando o PowerShell

1. Execute o seguinte, onde &lt; group_id &gt; é a ID do grupo da equipe e &lt; channel_name &gt; é o nome do canal.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Promover um membro a um proprietário.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Usando a API do Graph

Você pode experimentar esses comandos por meio do [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).

1. Use o seguinte, em que &lt; group_id &gt; é a ID do grupo da equipe e &lt; CHANNEL_ID &gt; é a ID do canal.

    **Solicitação**

    ```Graph API
    GET https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members
    ```
    
    **Resposta**

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
2. Use o seguinte para promover o membro a um proprietário, onde &lt; group_id &gt; , &lt; channel_id &gt; e &lt; ID &gt; serão retornados da chamada anterior. Observe que &lt; ID &gt; e &lt; userid &gt; retornados da chamada anterior não são iguais e não são intercambiáveis. Certifique-se de usar &lt; ID &gt; .

    **Solicitação**

    ```Graph API
    PATCH 
    https://graph.microsoft.com/beta/teams/<group_id>/channels/<channel_id>/members/<id>
      
    {
    "@odata.type": "#microsoft.graph.aadUserConversationMember",
    "roles": ["owner"]
    }
    ```

    **Resposta**

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

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
- [Usar a API do Microsoft Graph para trabalhar com o Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
    - [Canais de lista](https://docs.microsoft.com/graph/api/channel-list)
    - [Criar canal](https://docs.microsoft.com/graph/api/channel-post)
    - [Adicionar membro ao canal](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Atualizar membro no canal](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Remover membro do canal](https://docs.microsoft.com/graph/api/conversationmember-delete)
