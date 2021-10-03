---
title: Exportar conteúdo com as APIs Microsoft Teams Export
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Neste artigo, você aprenderá sobre como exportar Teams conteúdo usando as APIs Microsoft Teams Export.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082861"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar conteúdo com as APIs Microsoft Teams Export

Teams As APIs de exportação permitem que você exporte 1:1, chat em grupo, chats de reunião e mensagens de canal Microsoft Teams. Se a sua organização precisar exportar Microsoft Teams mensagens, você poderá extraí-las usando Teams Exportar APIs. *Mensagem de chat* representa uma mensagem de chat individual dentro de [um canal](/graph/api/resources/channel?view=graph-rest-beta) ou [chat](/graph/api/resources/chat?view=graph-rest-beta). A mensagem de chat pode ser uma mensagem de chat raiz ou parte de um thread de resposta definido pela **propriedade replyToId** na mensagem de chat.

Aqui estão alguns exemplos sobre como você pode usar essas APIs de exportação:

- **Exemplo 1**: Se você habilitar Microsoft Teams em sua organização e quiser exportar todas as mensagens Microsoft Teams para datar programaticamente passando o intervalo de datas para um determinado usuário ou equipe.
- **Exemplo 2**: Se você quiser exportar programaticamente todas as mensagens de usuário ou equipe diariamente, fornecendo um intervalo de datas. As APIs de exportação podem recuperar todas as mensagens criadas ou atualizadas durante o intervalo de datas determinado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>O que é suportado pelas APIs Teams Export?

- Exportação em massa de **Teams Mensagem:** as APIs de exportação de Teams suportam até 200 RPS por locatário por aplicativo e 600 RPS para um Aplicativo, com esses limites, você deve ser capaz de exportar em massa mensagens Teams.
- **Contexto do** aplicativo : para chamar o Microsoft Graph, seu aplicativo deve adquirir um token de acesso do plataforma de identidade da Microsoft. O token de acesso contém informações sobre seu aplicativo e as permissões que ele tem para os recursos e APIs disponíveis por meio do Microsoft Graph. Para obter um token de acesso, seu aplicativo deve ser registrado no plataforma de identidade da Microsoft e ser autorizado por um usuário ou um administrador para acessar os recursos do Microsoft Graph que precisa.

    Se você já estiver familiarizado com a integração de um aplicativo [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) com o plataforma de identidade da Microsoft para obter tokens, consulte a seção Próximas Etapas para obter informações e exemplos específicos do Microsoft Graph.
- **Ambiente Híbrido:** Exportar APIs suportam mensagens enviadas por usuários provisionados em Ambiente Híbrido (local Exchange e Teams). Todas as mensagens enviadas por usuários configurados para ambiente híbrido estarão acessíveis usando APIs de Exportação.
- **Mensagens excluídas pelo usuário:** As mensagens excluídas pelos usuários do cliente Teams podem ser acessadas usando APIs de exportação até 21 dias a partir do momento da exclusão.
- **Anexos de mensagem:** As APIs de exportação incluem os links para os anexos enviados como parte das mensagens. Usando as APIs de Exportação, você pode recuperar os arquivos anexados nas mensagens.
- **Propriedades da mensagem de chat:** Consulte a lista completa de propriedades que Teams as APIs de Exportação [suportam aqui](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).

>[!NOTE]
>As APIs de exportação não suportam *reações.*

## <a name="how-to-access-teams-export-apis"></a>Como acessar as APIs Teams Exportação

- **O Exemplo 1** é uma consulta simples para recuperar todas as mensagens de um usuário ou equipe sem filtros:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
    ```

- **O Exemplo 2** é uma consulta de exemplo para recuperar todas as mensagens de um usuário ou equipe especificando os filtros de data e as 50 principais mensagens:

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>A API retorna a resposta com o link da próxima página em caso de vários resultados. Para obter o próximo conjunto de resultados, basta chamar GET na url de @odata.nextlink. Se @odata.nextlink não estiver presente ou nulo, todas as mensagens serão recuperadas.

## <a name="prerequisites-to-access-teams-export-apis"></a>Pré-requisitos para acessar Teams Exportar APIs 

- Microsoft Teams APIs na Microsoft Graph que acessar dados confidenciais são consideradas APIs protegidas. As APIs de exportação exigem que você tenha validação adicional, além de permissões e consentimento, antes de poder usá-las. Para solicitar acesso a essas APIs protegidas, preencha o formulário [de solicitação](https://aka.ms/teamsgraph/requestaccess).
- As permissões de aplicativo são usadas por aplicativos que são executados sem um usuário in-locar presente; permissões de aplicativo só podem ser consentida por um administrador. As seguintes permissões são necessárias:

    - *Chat.Read.All*: habilita o acesso a todas as mensagens de chat de grupo e de reunião 1:1 
    - *ChannelMessage.Read.All*: habilita o acesso a todas as mensagens de canal  
    - *User.Read.All*: habilita o acesso à lista de usuários para um locatário

## <a name="license-requirements-for-teams-export-apis"></a>Requisitos de licença para Teams DE Exportação

A API de exportação dá suporte a cenários de segurança e conformidade (S+C) e uso geral por meio de um parâmetro de consulta de modelo. Os cenários S+C (Modelo A) incluem capacidade de semente e exigem uma assinatura do E5 e cenários de uso geral (Modelo B) estão disponíveis para todas as assinaturas e é somente consumo. Para obter mais informações sobre taxas de capacidade e consumo de sementes, consulte [Licensing and payment requirements for Microsoft Graph Teams APIs](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>Cenários S+C/Model A

Restritos a aplicativos que executam funções de segurança e/ou conformidade, os usuários devem ter licenças E5 específicas para usar essa funcionalidade e receber a capacidade de semente. A capacidade de semente é por usuário e calculada por mês e é agregada no nível do locatário. Para uso além da capacidade de semente, os proprietários de aplicativos são cobrados pelo consumo de API. O Modelo A só pode acessar mensagens de usuários com uma licença E5 atribuída.

### <a name="general-usagemodel-b-scenarios"></a>Cenários gerais de uso/modelo B

Disponível para todos os cenários não relacionados a S+C, não há requisitos de licença ou capacidade de sementes. Quando os medidores de consumo ficam disponíveis, os proprietários de aplicativos serão cobrados por todas as chamadas de API mensais. 

### <a name="evaluation-mode-default"></a>Modo de Avaliação (padrão)

Nenhuma declaração de modelo permite o acesso a APIs com uso limitado por cada aplicativo solicitando para fins de avaliação. 

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