---
title: Exportar conteúdo com as APIs de exportação do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Neste artigo, você aprenderá sobre como exportar conteúdo do Teams usando as APIs de exportação do Microsoft Teams.
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
ms.openlocfilehash: 9c99bed1ef9a1862b469dd5214b8d829bde8479b
ms.sourcegitcommit: 15c45befbee35e69f9ec82493151cb82e61da4fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50096924"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar conteúdo com as APIs de exportação do Microsoft Teams

As APIs de exportação do Teams permitem exportar mensagens 1:1, chat em grupo e canal do Microsoft Teams. Se sua organização precisar exportar mensagens do Microsoft Teams, você poderá extraí-las usando APIs de exportação do Teams. *A Mensagem de* Chat representa uma mensagem de chat individual dentro [de um canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) ou [chat.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) A mensagem de chat pode ser uma mensagem de chat raiz ou parte de um thread de resposta definido pela propriedade **replyToId** na mensagem de chat.

Aqui estão alguns exemplos sobre como você pode usar essas APIs de exportação:

- **Exemplo 1:** se você tiver habilitado o Microsoft Teams em sua organização e quiser exportar todas as mensagens do Microsoft Teams para datar programaticamente passando o intervalo de datas para um determinado usuário ou equipe.
- **Exemplo 2:** se você quiser exportar programaticamente todas as mensagens de usuário ou equipe diariamente fornecendo um intervalo de datas. Exportar APIs pode recuperar todas as mensagens criadas ou atualizadas durante o intervalo de datas determinado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>O que é suportado pelas APIs de exportação do Teams?

- **Exportação em massa da mensagem do Teams:** O Teams Export APIs oferece suporte a até 200 HACKS por locatário por aplicativo e 600 HACKS para um Aplicativo, com esses limites, você deve ser capaz de exportar mensagens do Teams em massa.
- **Contexto do** aplicativo: para ligar para o Microsoft Graph, seu aplicativo deve adquirir um token de acesso da plataforma de identidade da Microsoft. O token de acesso contém informações sobre seu aplicativo e as permissões que ele tem para os recursos e APIs disponíveis por meio do Microsoft Graph. Para obter um token de acesso, seu aplicativo deve ser registrado na plataforma de identidade da Microsoft e ser autorizado por um usuário ou um administrador para ter acesso aos recursos necessários do Microsoft Graph.

    Se você já estiver familiarizado com a integração de um aplicativo [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) com a plataforma de identidade da Microsoft para obter tokens, confira a seção Próximas Etapas para obter informações e exemplos específicos do Microsoft Graph.
- **Ambiente híbrido:** Exportar apIs suportam mensagens enviadas por usuários provisionados em Ambiente Híbrido (Exchange e Teams locais). Todas as mensagens que são enviadas por usuários configurados para ambiente híbrido estarão acessíveis usando as APIs de exportação.
- **Mensagens excluídas pelo usuário:** As mensagens excluídas pelo usuário do cliente teams podem ser acessadas usando APIs de exportação até 30 dias a partir do momento da exclusão.
- **Anexos de Mensagens:** As APIs de exportação incluem os links para os anexos que são enviados como parte das mensagens. Usando Exportar APIs, você pode recuperar os arquivos anexados nas mensagens.
- **Propriedades da mensagem de chat:** Confira a lista completa de propriedades que as APIs de exportação do Teams têm [suporte aqui.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Como acessar APIs de exportação do Teams

- **Exemplo 1** é uma consulta simples para recuperar todas as mensagens de um usuário ou equipe sem filtros:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **Exemplo 2** é uma consulta de exemplo para recuperar todas as mensagens de um usuário ou equipe, especificando filtros de data e 50 mensagens principais:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>A API retorna a resposta com o próximo link de página em caso de vários resultados. Para obter o próximo conjunto de resultados, basta ligar para OBTER na URL @odata.nextlink. Se @odata.nextlink não estiver presente ou nulo, todas as mensagens serão recuperadas.

## <a name="prerequisites-to-access-teams-export-apis"></a>Pré-requisitos para acessar APIs de exportação do Teams 

- As APIs de exportação do Teams estão atualmente em visualização. Ele estará disponível somente para usuários e locatários que tenham as [licenças necessárias](https://aka.ms/teams-changenotification-licenses) para APIs. No futuro, a Microsoft pode exigir que você ou seus clientes paguem taxas adicionais com base na quantidade de dados acessados por meio da API.
- APIs do Microsoft Teams no Microsoft Graph que acessam dados confidenciais são consideradas APIs protegidas. Exportar APIs exigem que você tenha validação adicional, além de permissões e consentimento, antes de poder usá-las. Para solicitar acesso a essas APIs protegidas, preencha o formulário [de solicitação.](https://aka.ms/teamsgraph/requestaccess)
- As permissões de aplicativo são usadas por aplicativos que são executados sem a presença de um usuário de acesso; permissões de aplicativo só podem ser consentida por um administrador. As seguintes permissões são necessárias:

    - *Chat.Read.All:* habilita o acesso a todas as mensagens de chat em grupo e 1:1 
    - *User.Read.All:* habilita o acesso à lista de usuários de um locatário 

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
>Para obter mais detalhes sobre o recurso chatMessage, consulte o artigo do tipo de recurso [chatMessage.](https://docs.microsoft.com/graph/api/resources/chatmessage)
