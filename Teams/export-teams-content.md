---
title: Exportar conteúdo com as APIs de exportação do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Neste artigo, você aprenderá a exportar conteúdo de equipes usando as APIs de exportação do Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944596"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar conteúdo com as APIs de exportação do Microsoft Teams

As APIs de exportação do teams permitem que você exporte o 1:1, o chat em grupo e mensagens de canal do Microsoft Teams. Se a sua organização precisar exportar mensagens do Microsoft Teams, você poderá extraí-las usando as APIs de exportação do teams. *Mensagem de chat* representa uma mensagem de chat individual em um [canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) ou [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta). A mensagem de chat pode ser uma mensagem de chat raiz ou parte de um thread de resposta que é definido pela propriedade **replyToId** na mensagem de chat.

Veja a seguir alguns exemplos de como você pode usar essas APIs de exportação:

- **Exemplo 1**: se você tiver habilitado o Microsoft Teams em sua organização e quiser exportar todas as mensagens do Microsoft Teams para a data de forma programática passando o intervalo de datas para um determinado usuário ou equipe.
- **Exemplo 2**: se você quiser exportar de forma programática todas as mensagens de usuário ou de equipe diariamente fornecendo um intervalo de datas. APIs de exportação podem recuperar todas as mensagens criadas ou atualizadas durante um determinado intervalo de datas.

## <a name="what-is-supported-by-the-teams-export-apis"></a>O que é compatível com as APIs de exportação do teams?

- **Mensagem de exportação em massa da mensagem do teams:** As APIs de exportação do Team dão suporte a até 200 RPS por aplicativo por locatário e 600 RPS para um aplicativo, com esses limites, você deve ser capaz de exportar mensagens de equipe em massa.
- **Contexto do aplicativo**: para chamar o Microsoft Graph, seu aplicativo deve adquirir um token de acesso da plataforma de identidade da Microsoft. O token de acesso contém informações sobre seu aplicativo e as permissões que ele tem para os recursos e APIs disponíveis por meio do Microsoft Graph. Para obter um token de acesso, seu aplicativo deve ser registrado com a plataforma de identidade da Microsoft e ser autorizado por um usuário ou administrador para ter acesso aos recursos do Microsoft Graph necessários.

    Se você já estiver familiarizado com a integração de um aplicativo com a plataforma de identidade da Microsoft para obter tokens, consulte a seção [próximas etapas](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) para obter informações e exemplos específicos do Microsoft Graph.
- **Ambiente híbrido:** As APIs de exportação dão suporte a mensagens enviadas por usuários provisionados em um ambiente híbrido (Exchange e Teams locais). Todas as mensagens enviadas por usuários configurados para ambiente híbrido poderão ser acessadas usando APIs de exportação.
- **Mensagens excluídas pelo usuário:** As mensagens que são excluídas pelo usuário do teams Client podem ser acessadas usando APIs de exportação de até 30 dias a partir do momento da exclusão.
- **Anexos da mensagem:** As APIs de exportação incluem os links para os anexos que são enviados como parte das mensagens. Usando as APIs de exportação, você pode recuperar os arquivos anexados nas mensagens.
- **Propriedades da mensagem de chat:** Consulte a lista completa de propriedades com suporte para APIs de exportação de equipes [aqui](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).

## <a name="how-to-access-teams-export-apis"></a>Como acessar as APIs de exportação do teams

- O **exemplo 1** é uma consulta simples para recuperar todas as mensagens de um usuário ou equipe sem filtros:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- O **exemplo 2** é uma consulta de exemplo para recuperar todas as mensagens de um usuário ou equipe especificando filtros de data/hora e as principais mensagens de 50:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Para obter mais detalhes sobre o recurso chatMessage, consulte o artigo [tipo de recurso chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .
