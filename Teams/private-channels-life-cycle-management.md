---
title: Gerenciar os canais privados no Microsoft Teams com Graph API
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar canais privados em sua organização usando Graph API.
ms.openlocfilehash: b0b915529d9d4bc780215afceead61ebf31e5259
ms.sourcegitcommit: eddc03f777ce78bd5273708da9b1ab609ee20099
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2022
ms.locfileid: "62064867"
---
# <a name="manage-the-life-cycle-of-private-channels-in-microsoft-teams"></a>Gerenciar o ciclo de vida de canais privados no Microsoft Teams

Aqui você encontrará as diretrizes que você precisa para usar a API Graph para gerenciar Teams [canais](./private-channels.md) privados em sua organização.

## <a name="set-whether-team-members-can-create-private-channels"></a>Defina se os proprietários e membros podem criar canais privados

Como administrador você pode usar a API do Graph para controlar se os membros podem criar canais privados em equipes específicas. Veja um exemplo.

```Graph API
PATCH /teams/<team_id>
{"memberSettings": 
  {
    "allowCreatePrivateChannels": false
  }
}
```

## <a name="create-a-private-channel-on-behalf-of-a-team-owner"></a>Criar um canal privado em nome do proprietário de equipe

Como administrador, você pode usar a API Graph para criar um canal privado em nome de um proprietário da equipe. Por exemplo, você pode querer fazer isso se sua organização quiser centralizar a criação de canais privados.

```Graph API
POST /teams/{id}/channels
{
    "membershipType": "Private",
    "displayName": "<Channel_Name>",
    "members": [
        {
            "@odata.type": "#microsoft.graph.aadUserConversationMember",
            "user@odata.bind": "https://graph.microsoft.com/v1.0/users('<user_id>')",
            "roles": [
                "owner"
            ]
        }
    ]
}
            
```

## <a name="get-a-list-of-all-private-channel-messages"></a>Obter uma lista de todas as mensagens do canal privado

Você pode obter uma lista de todas as mensagens e respostas postadas em um canal privado para propósitos de arquivo ou auditoria.  Veja aqui como usar a API do Graph para fazer isso.

```Graph API
GET /teams/{id}/channels/{id}/messages
GET /teams/{id}/channels/{id}/messages/{id}/replies/{id}
```

## <a name="find-sharepoint-urls-for-all-private-channels-in-a-team"></a>Encontrar URLs do Microsoft Office SharePoint Online para todos os canais privados em uma equipe

Se estiver procurando executar o eDiscovery, reter legalmente arquivos em um canal privado ou construir um aplicativo personalizado que coloca os arquivos em canais privados específicos, precisará de uma maneira de consultar os conjuntos exclusivos de sites do Microsoft Office SharePoint Online criados para cada canal privado.

Como administrador, você pode usar Graph APIs para consultar essas URLs.

Você pode tentar esses comandos através do [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Use o seguinte para obter a lista de IDs de canal privado para uma determinada equipe, onde <group_id> é a ID de grupo da equipe. Você precisará disso nas chamadas subsequentes. (Você pode encontrar facilmente a ID de grupo no link para a equipe.)

    **Solicitação**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels?$filter=membershipType eq 'private'
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
    GET https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/filesFolder
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

Como administrador, você pode usar a API Graph para executar essas ações.

Você pode tentar esses comandos através do [Explorador do Graph](https://developer.microsoft.com/graph/graph-explorer).

1. Executar o seguinte, onde &lt;group_id&gt; é a ID de grupo da equipe e &lt;channel_id&gt; é a ID do canal.

    **Solicitação**

    ```Graph API
    GET https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/members
    ```

    **Resposta**

    ```Graph API
    HTTP/1.1 200 OK Content-type: application/json
    Content-length: 
    {
          "@odata.context": "https://graph.microsoft.com/$metadata#teams({group_id}')/channels('{channel_id}')/members",
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
    https://graph.microsoft.com/teams/<group_id>/channels/<channel_id>/members/<id>
      
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
      "@odata.context": "https://graph.microsoft.com/$metadata#teams('{group_id}')/channels('{channel_id}')/members/$entity",
      "@odata.type": "#microsoft.graph.aadUserConversationMember",
      "id": "id-value",
      "roles": ["owner"],
      "displayName": "display-name-value",
      "userId": "userId-value",
      "email": "email-value"
     }
    ```

## <a name="related-topics"></a>Tópicos relacionados

[Usar a API do Microsoft Graph para trabalhar com o Teams](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)

[Listar canais](/graph/api/channel-list)

[Criar um canal](/graph/api/channel-post)

[Adicionar membro ao canal](/graph/api/conversationmember-add)

[Atualizar membro no canal](/graph/api/conversationmember-update)

[Remover membro do canal](/graph/api/conversationmember-delete)
