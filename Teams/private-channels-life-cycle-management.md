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
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gerenciar o ciclo de vida de canais privados no Microsoft Teams

Aqui você encontrará a orientação que precisa para gerenciar o ciclo de vida dos [canais privados](private-channels.md) na sua organização.

> [!IMPORTANT]
> Se você estiver usando as etapas do Windows PowerShell nesse artigo para gerenciar os canais privados, deve instalar e usar o módulo de visualização pública do PowerShell do Teams a partir da [Galeria do PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). Para etapas sobre como instalar o módulo, confira [Instalar o PowerShell do Microsoft Teams](teams-powershell-install.md). O módulo mais recente do Windows PowerShell do Teams para Disponibilidade Geral não tem suporte para gerenciamento de canais privados.

## <a name="set-whether-team-members-can-create-private-channels"></a>Defina se os proprietários e membros podem criar canais privados

Os proprietários de equipe podem desativar ou ativar a capacidade dos membros de criar canais privados nas configurações da equipe. Para fazer isso na guia **Configurações** de uma equipe, desative ou ative em **Permitir aos membros criar canais privados**.

Como administrador você pode usar a API do Graph para controlar se os membros podem criar canais privados em equipes específicas. Veja um exemplo.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="set-whether-users-in-your-organization-can-create-private-channels"></a>Defina se os usuários em sua organização podem criar canais privados

Como administrador, você pode definir políticas usando o centro de Administração do Microsoft Teams ou do Windows PowerShell para controlar quais usuários em sua organização podem criar canais privados.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Use as políticas para controlar quais usuários em sua organização podem criar canais privados. Para saber mais, confira o artigo [Gerenciar políticas de equipes no Teams](teams-policies.md).

### <a name="using-powershell"></a>Usando o Windows PowerShell

Use **CsTeamsChannelsPolicy** para definir quais usuários em sua organização podem criar canais privados. Confira o parâmetro **AllowPrivateChannelCreation** para **verdadeiro** para permitir aos usuários atribuídos com a política a criar canais privados. Definir o parâmetro para **falso** desativa a capacidade de criar canais privados para usuários atribuídos com a política.

Para saber mais, confira [New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps).

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Criar um canal privado em nome do proprietário de equipe

Como administrador você pode usar o Windows PowerShell ou a API do Graph para criar um canal privado em nome do proprietário de equipe. Por exemplo, você pode querer fazer isso se sua organização quiser centralizar a criação de canais privados.

### <a name="using-powershell"></a>Usando o Windows PowerShell

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

## <a name="get-a-list-of-all-private-channel-messages"></a>Obter uma lista de todas as mensagens do canal privado

Você pode obter uma lista de todas as mensagens e respostas postadas em um canal privado para propósitos de arquivo ou auditoria.  Veja aqui como usar a API do Graph para fazer isso.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Encontrar URLs do Microsoft Office SharePoint Online para todos os canais privados em uma equipe

Se estiver procurando executar o eDiscovery, reter legalmente arquivos em um canal privado ou construir um aplicativo personalizado que coloca os arquivos em canais privados específicos, precisará de uma maneira de consultar os conjuntos exclusivos de sites do Microsoft Office SharePoint Online criados para cada canal privado.

Como administrador, você pode usar os comandos do Windows PowerShell ou das APIs do Graph para consultar essas URLs.

### <a name="using-powershell"></a>Usando o Windows PowerShell

1. Instalar e conectar com sua conta de administrador do [Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).
2. Executar o seguinte, onde &lt;group_id&gt; é a ID de grupo da equipe. (Você pode encontrar facilmente a ID de grupo no link para a equipe.)

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "<group_id>"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity
    $site.url -Detail; if ($x.RelatedGroupId -eq $groupID)
    {$x.RelatedGroupId;$x.url}}
    ```

### <a name="using-graph-api"></a>Usando a API do Graph

Você pode tentar esses comandos através do [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Use o seguinte para obter a lista de IDs de canal privado para uma determinada equipe, onde <group_id> é a ID de grupo da equipe. Você precisará disso nas chamadas subsequentes. (Você pode encontrar facilmente a ID de grupo no link para a equipe.)

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

2. Para cada canal privado que você quiser obter a URL do Microsoft Office SharePoint Online, faça a seguinte solicitação, onde &lt;channel_id&gt; é a ID do canal.

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

## <a name="list-and-update-roles-of-owners-and-members-in-a-private-channel"></a>Listar e atualizar os papeis de proprietários e membros em um canal privado

Se desejar listar os proprietários e membros de um canal privado para decidir se precisa promover certos membros do canal privado para um proprietário. Isso pode acontecer quando você tem proprietários de canais privados que deixaram a organização e o canal privado requer que os administradores ajudem a reivindicar a propriedade do canal.

Como administrador, você pode usar o centro de Administração do Microsoft Teams, do Windows PowerShell ou da API do Graph para realizar essas ações.

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

Para saber como gerenciar os membros da equipe usando o centro de Administração do Microsoft Teams, confira [Gerenciar equipes no centro de Administração do Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="using-powershell"></a>Usando o Windows PowerShell

1. Executar o seguinte, onde &lt;group_id&gt; é a ID de grupo da equipe e &lt;channel_name&gt; é o nome do canal.

    ```PowerShell
    Get-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" 
    ```

2. Promover um membro a proprietário.

    ```PowerShell
    Add-TeamChannelUser -GroupId <group_id> -DisplayName "<channel_name>" -User <UPN> -Role Owner
    ```

### <a name="using-graph-api"></a>Usando a API do Graph

Você pode tentar esses comandos através do [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Executar o seguinte, onde &lt;group_id&gt; é a ID de grupo da equipe e &lt;channel_id&gt; é a ID do canal.

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
2. Use o seguinte para promover o membro a um proprietário, onde &lt;group_id&gt;, &lt;channel_id&gt; e &lt;id&gt; são retornadas da chamada anterior. Observe que &lt;id&gt; e &lt;userId&gt; retornadas das chamadas anteriores não são as mesmas e não são intercambiáveis. Certifique-se de usar &lt;id&gt;.

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
    - [Listar canais](https://docs.microsoft.com/graph/api/channel-list)
    - [Criar um canal](https://docs.microsoft.com/graph/api/channel-post)
    - [Adicionar membro ao canal](https://docs.microsoft.com/graph/api/conversationmember-add)
    - [Atualizar membro no canal](https://docs.microsoft.com/graph/api/conversationmember-update)
    - [Remover membro do canal](https://docs.microsoft.com/graph/api/conversationmember-delete)
