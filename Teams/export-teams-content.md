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
ms.openlocfilehash: 026b7f238b059b4e310fa2216b482c68f2528780
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650974"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar conteúdo com as APIs de exportação do Microsoft Teams

As APIs de exportação do teams permitem que você exporte o 1:1 e mensagens de chat em grupo do Microsoft Teams. Se a sua organização precisar exportar mensagens do Microsoft Teams, você poderá extraí-las usando as APIs de exportação do teams. *Mensagem de chat* representa uma mensagem de chat individual em um [canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) ou [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta). A mensagem de chat pode ser uma mensagem de chat raiz ou parte de um thread de resposta que é definido pela propriedade **replyToId** na mensagem de chat.

Veja a seguir alguns exemplos de como você pode usar essas APIs de exportação:

- **Exemplo 1**: se você tiver habilitado o Microsoft Teams em sua organização e quiser exportar todas as mensagens do Microsoft Teams para a data de forma programática passando o intervalo de datas para um determinado usuário.
- **Exemplo 2**: se você quiser exportar programaticamente todas as mensagens de usuário diariamente fornecendo um intervalo de datas. APIs de exportação podem recuperar todas as mensagens criadas ou atualizadas durante um determinado intervalo de datas.

## <a name="what-is-supported-by-the-teams-export-apis"></a>O que é compatível com as APIs de exportação do teams?

- **Mensagem de exportação em massa da mensagem do teams:** As APIs de exportação do Team dão suporte a até 200 RPS por aplicativo por locatário e 600 RPS para um aplicativo, com esses limites, você deve ser capaz de exportar mensagens de equipe em massa.
- **Contexto do aplicativo**: para chamar o Microsoft Graph, seu aplicativo deve adquirir um token de acesso da plataforma de identidade da Microsoft. O token de acesso contém informações sobre seu aplicativo e as permissões que ele tem para os recursos e APIs disponíveis por meio do Microsoft Graph. Para obter um token de acesso, seu aplicativo deve ser registrado com a plataforma de identidade da Microsoft e ser autorizado por um usuário ou administrador para ter acesso aos recursos do Microsoft Graph necessários.

    Se você já estiver familiarizado com a integração de um aplicativo com a plataforma de identidade da Microsoft para obter tokens, consulte a seção [próximas etapas](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) para obter informações e exemplos específicos do Microsoft Graph.
- **Ambiente híbrido:** As APIs de exportação dão suporte a mensagens enviadas por usuários provisionados em um ambiente híbrido (Exchange e Teams locais). Todas as mensagens enviadas por usuários configurados para ambiente híbrido poderão ser acessadas usando APIs de exportação.
- **Mensagens excluídas pelo usuário:** As mensagens que são excluídas pelo usuário do teams Client podem ser acessadas usando APIs de exportação de até 30 dias a partir do momento da exclusão.
- **Anexos da mensagem:** As APIs de exportação incluem os links para os anexos que são enviados como parte das mensagens. Usando as APIs de exportação, você pode recuperar os arquivos anexados nas mensagens.
- **Propriedades da mensagem de chat:** Consulte a lista completa de propriedades com suporte para APIs de exportação de equipes [aqui](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).

## <a name="how-to-access-teams-export-apis"></a>Como acessar as APIs de exportação do teams

- O **exemplo 1** é uma consulta simples para recuperar todas as mensagens de um usuário sem filtros:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- O **exemplo 2** é uma consulta de exemplo para recuperar todas as mensagens de um usuário especificando filtros de data e hora e as principais mensagens de 50:

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>A API retorna a resposta com o link próxima página em caso de vários resultados. Para obter o próximo conjunto de resultados, basta chamar obter a URL de @odata. Nextlink. Se @odata. Nextlink não estiver presente ou for NULL, todas as mensagens serão recuperadas.

## <a name="prerequisites-to-access-teams-export-apis"></a>Pré-requisitos para acessar as APIs de exportação do teams 

- As APIs de exportação do teams estão atualmente em visualização. Ele só estará disponível para usuários e locatários que tenham as [licenças necessárias](https://aka.ms/teams-changenotification-licenses) para APIs. No futuro, a Microsoft pode exigir que você ou seus clientes paguem taxas adicionais com base na quantidade de dados acessados por meio da API.
- As APIs do Microsoft Teams no Microsoft Graph que acessam dados confidenciais são consideradas APIs protegidas. As APIs de exportação exigem validação adicional, além de permissões e consentimento, para que você possa usá-las. Para solicitar acesso a essas APIs protegidas, preencha o [formulário de solicitação](https://aka.ms/teamsgraph/requestaccess).
- As permissões de aplicativo são usadas por aplicativos que são executados sem um usuário conectado presente; as permissões do aplicativo só podem ser consentidas por um administrador. As seguintes permissões são necessárias:

    - *Chat. Read. All*: permite o acesso a todas as 1:1 e mensagens de chat em grupo 
    - *User. Read. All*: permite o acesso à lista de usuários para um locatário 

## <a name="json-representation"></a>Representação JSON

O exemplo a seguir é uma representação JSON do recurso:

Namespace: Microsoft. Graph

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
                    "id": "0de69e5e-2da8-4cf2-821f-5e6585b2c65b",
                    "displayName": "User Name",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "19:0de69e5e-2da8-4cf2-821f-5e6585b2c65b_5c64e248-3269-4268-a36e-0f80314e9c39@unq.gbl.spaces"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>Para obter mais detalhes sobre o recurso chatMessage, consulte o artigo [tipo de recurso chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .
