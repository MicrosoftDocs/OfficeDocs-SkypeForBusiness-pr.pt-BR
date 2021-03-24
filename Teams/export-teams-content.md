---
title: Exportar conteúdo com as APIs de Exportação do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Neste artigo, você aprenderá sobre como exportar conteúdo do Teams usando as APIs de Exportação do Microsoft Teams.
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
ms.openlocfilehash: 013cd992619264f875841b1b6bb13aca3943d14e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092437"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar conteúdo com as APIs de Exportação do Microsoft Teams

As APIs de Exportação do Teams permitem que você exporte 1:1, chat em grupo, chats de reunião e mensagens de canal do Microsoft Teams. Se sua organização precisar exportar mensagens do Microsoft Teams, você poderá extraí-las usando APIs de Exportação do Teams. *Mensagem de chat* representa uma mensagem de chat individual dentro de [um canal](/graph/api/resources/channel?view=graph-rest-beta) ou [chat](/graph/api/resources/chat?view=graph-rest-beta). A mensagem de chat pode ser uma mensagem de chat raiz ou parte de um thread de resposta definido pela **propriedade replyToId** na mensagem de chat.

Aqui estão alguns exemplos sobre como você pode usar essas APIs de exportação:

- **Exemplo 1**: Se você habilitar o Microsoft Teams em sua organização e quiser exportar todas as mensagens do Microsoft Teams para datar programaticamente passando o intervalo de datas para um determinado usuário ou equipe.
- **Exemplo 2**: Se você quiser exportar programaticamente todas as mensagens de usuário ou equipe diariamente, fornecendo um intervalo de datas. As APIs de exportação podem recuperar todas as mensagens criadas ou atualizadas durante o intervalo de datas determinado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>O que é suportado pelas APIs de Exportação do Teams?

- **Exportação em massa da mensagem do Teams:** As APIs de Exportação do Teams suportam até 200 RPS por locatário por aplicativo e 600 RPS para um Aplicativo, com esses limites, você deve ser capaz de exportar em massa mensagens do Teams.
- **Contexto do aplicativo**: Para chamar o Microsoft Graph, seu aplicativo deve adquirir um token de acesso da plataforma de identidade da Microsoft. O token de acesso contém informações sobre seu aplicativo e as permissões que ele tem para os recursos e APIs disponíveis por meio do Microsoft Graph. Para obter um token de acesso, seu aplicativo deve ser registrado na plataforma de identidade da Microsoft e ser autorizado por um usuário ou um administrador para acessar os recursos do Microsoft Graph necessários.

    Se você já estiver familiarizado com a integração de um aplicativo [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) com a plataforma de identidade da Microsoft para obter tokens, consulte a seção Próximas Etapas para obter informações e exemplos específicos do Microsoft Graph.
- **Ambiente Híbrido:** Exportar APIs suportam mensagens enviadas por usuários provisionados em Ambiente Híbrido (Exchange e Teams locais). Todas as mensagens enviadas por usuários configurados para ambiente híbrido estarão acessíveis usando APIs de Exportação.
- **Mensagens excluídas pelo usuário:** As mensagens excluídas pelos usuários do cliente teams podem ser acessadas usando APIs de exportação até 21 dias a partir do momento da exclusão.
- **Anexos de mensagem:** As APIs de exportação incluem os links para os anexos enviados como parte das mensagens. Usando as APIs de Exportação, você pode recuperar os arquivos anexados nas mensagens.
- **Propriedades da mensagem de chat:** Consulte a lista completa de propriedades que as APIs de Exportação do Teams suportam [aqui](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).

## <a name="how-to-access-teams-export-apis"></a>Como acessar APIs de Exportação do Teams

- **O Exemplo 1** é uma consulta simples para recuperar todas as mensagens de um usuário ou equipe sem filtros:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- **O Exemplo 2** é uma consulta de exemplo para recuperar todas as mensagens de um usuário ou equipe especificando os filtros de data e as 50 principais mensagens:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>A API retorna a resposta com o link da próxima página em caso de vários resultados. Para obter o próximo conjunto de resultados, basta chamar GET na url de @odata.nextlink. Se @odata.nextlink não estiver presente ou nulo, todas as mensagens serão recuperadas.

## <a name="prerequisites-to-access-teams-export-apis"></a>Pré-requisitos para acessar APIs de Exportação do Teams 

- As APIs de Exportação do Teams estão atualmente em visualização. Ele só estará disponível para usuários e locatários que tenham as [licenças necessárias](/graph/teams-licenses) para APIs. No futuro, a Microsoft pode exigir que você ou seus clientes paguem taxas adicionais com base na quantidade de dados acessados por meio da API.
- As APIs do Microsoft Teams no Microsoft Graph que acessam dados confidenciais são consideradas APIs protegidas. As APIs de exportação exigem que você tenha validação adicional, além de permissões e consentimento, antes de poder usá-las. Para solicitar acesso a essas APIs protegidas, preencha o formulário [de solicitação](https://aka.ms/teamsgraph/requestaccess).
- As permissões de aplicativo são usadas por aplicativos que são executados sem um usuário in-locar presente; permissões de aplicativo só podem ser consentida por um administrador. As seguintes permissões são necessárias:

    - *Chat.Read.All*: habilita o acesso a todas as mensagens de chat de grupo e 1:1 
    - *User.Read.All*: habilita o acesso à lista de usuários para um locatário 

## <a name="json-representation"></a>Representação JSON

O exemplo a seguir é uma representação JSON do recurso:

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

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Para obter mais detalhes sobre o recurso chatMessage, consulte o artigo tipo de recurso [chatMessage.](/graph/api/resources/chatmessage)