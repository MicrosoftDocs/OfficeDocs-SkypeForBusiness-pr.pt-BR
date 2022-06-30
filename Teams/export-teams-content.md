---
title: Exportar conteúdo com as APIs de Exportação do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: Neste artigo, você aprenderá a exportar conteúdo do Teams usando as APIs de Exportação do Microsoft Teams.
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
ms.openlocfilehash: ffbea482ac15d1362eabc720fe2c05a8b5954954
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562640"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Exportar conteúdo com as APIs de Exportação do Microsoft Teams

As APIs de Exportação do Teams permitem que você exporte 1:1, chat em grupo, chats de reunião e mensagens de canal do Microsoft Teams. Se sua organização precisar exportar mensagens do Microsoft Teams, você poderá extraí-las usando APIs de Exportação do Teams. *A Mensagem de Chat* representa uma mensagem de chat individual dentro [de um canal ou](/graph/api/resources/channel) [chat](/graph/api/resources/chat). A mensagem de chat pode ser uma mensagem de chat raiz ou parte de um thread de resposta definido pela propriedade **replyToId** na mensagem de chat.

Aqui estão alguns exemplos de como você pode usar essas APIs de exportação:

- **Exemplo 1**: se você habilitou o Microsoft Teams em sua organização e deseja exportar todas as mensagens do Microsoft Teams para data de forma programática passando o intervalo de datas para um determinado usuário ou equipe.
- **Exemplo 2**: se você quiser exportar programaticamente todas as mensagens do usuário ou da equipe diariamente, fornecendo um intervalo de datas. As APIs de exportação podem recuperar todas as mensagens criadas ou atualizadas durante o intervalo de datas determinado.

## <a name="what-is-supported-by-the-teams-export-apis"></a>O que é compatível com as APIs de Exportação do Teams?

- **Exportação em massa da mensagem do Teams:** As APIs de Exportação do Teams dão suporte a até 200 RPS por aplicativo por locatário e 600 RPS para um aplicativo, com esses limites, você deve ser capaz de exportar em massa mensagens do Teams.
- **Contexto do** aplicativo: para chamar o Microsoft Graph, seu aplicativo deve adquirir um token de acesso do plataforma de identidade da Microsoft. O token de acesso contém informações sobre seu aplicativo e as permissões que ele tem para os recursos e APIs disponíveis por meio do Microsoft Graph. Para obter um token de acesso, seu aplicativo deve ser registrado no plataforma de identidade da Microsoft e ser autorizado por um usuário ou um administrador para acessar os recursos do Microsoft Graph de que precisa.

    Se você já estiver familiarizado com a integração de um aplicativo com o plataforma de identidade da Microsoft para obter tokens, consulte a seção [](/graph/auth/auth-concepts#next-steps) Próximas Etapas para obter informações e exemplos específicos do Microsoft Graph.
- **Ambiente Híbrido:** As APIs de exportação dão suporte a mensagens enviadas por usuários provisionados no Ambiente Híbrido (Exchange e Teams locais). Todas as mensagens enviadas por usuários configurados para o ambiente híbrido estarão acessíveis usando APIs de Exportação.
- **Mensagens excluídas pelo usuário:** As mensagens excluídas pelos usuários do cliente do Teams podem ser acessadas usando APIs de exportação até 21 dias a partir do momento da exclusão.
- **Anexos de mensagem:** As APIs de exportação incluem os links para os anexos que são enviados como parte das mensagens. Usando APIs de Exportação, você pode recuperar os arquivos anexados nas mensagens.
- **Propriedades da mensagem de chat:** Consulte a lista completa de propriedades compatíveis com apIs de exportação do Teams [aqui](/graph/api/resources/chatmessage#properties).

> [!NOTE]
> As APIs de exportação não dão suporte a *reações*.

## <a name="how-to-access-teams-export-apis"></a>Como acessar as APIs de Exportação do Teams

- **O exemplo 1** é uma consulta simples para recuperar todas as mensagens de um usuário ou equipe sem filtros:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **O exemplo 2** é uma consulta de exemplo para recuperar todas as mensagens de um usuário ou equipe especificando filtros de data e hora e as 50 principais mensagens:

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> A API retorna a resposta com o link da próxima página no caso de vários resultados. Para obter o próximo conjunto de resultados, basta chamar GET na URL de @odata.nextlink. Se @odata.nextlink não estiver presente ou nulo, todas as mensagens serão recuperadas.

## <a name="prerequisites-to-access-teams-export-apis"></a>Pré-requisitos para acessar as APIs de Exportação do Teams

- As APIs do Microsoft Teams no Microsoft Graph que acessam dados confidenciais são consideradas APIs protegidas. As APIs de exportação exigem que você tenha validação adicional, além de permissões e consentimento, antes de poder usá-las. Para solicitar acesso a essas APIs protegidas, preencha o formulário [de solicitação](https://aka.ms/teamsgraph/requestaccess).
- As permissões de aplicativo são usadas por aplicativos que são executados sem um usuário conectado presente; permissões de aplicativo só podem ser consentida por um administrador. As seguintes permissões são necessárias:
  - *Chat.Read.All*: habilita o acesso a todas as mensagens 1:1, chat em grupo e chat de reunião
  - *ChannelMessage.Read.All*: habilita o acesso a todas as mensagens de canal
  - *User.Read.All*: habilita o acesso à lista de usuários para um locatário

## <a name="license-requirements-for-teams-export-apis"></a>Requisitos de licença para APIs de Exportação do Teams

A API de Exportação dá suporte a cenários de segurança e conformidade (S+C) e uso geral por meio de um parâmetro de consulta de modelo. Os cenários de S+C (Modelo A) incluem capacidade de propagação e exigem uma assinatura E5 e cenários de uso geral (Modelo B) estão disponíveis para todas as assinaturas e são somente consumo. Para obter mais informações sobre taxas de consumo e capacidade de propagação, consulte Requisitos de licenciamento e [pagamento para APIs do Microsoft Graph Teams](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>Cenários de S+C/Modelo A

Restritos a aplicativos que executam funções de segurança e/ou conformidade, os usuários devem ter licenças específicas do E5 para usar essa funcionalidade e receber a capacidade de propagação. A capacidade de propagação é por usuário e é calculada por mês e é agregada no nível do locatário. Para uso além da capacidade de propagação, os proprietários de aplicativos são cobrados pelo consumo de API. O modelo A só pode acessar mensagens de usuários com uma licença E5 atribuída.

### <a name="general-usagemodel-b-scenarios"></a>Cenários de uso geral/Modelo B

Disponível para todos os cenários não relacionados a S+C, não há requisitos de licença ou capacidade de propagação. Quando os medidores de consumo forem disponibilizados, os proprietários do aplicativo serão cobrados por todas as chamadas mensais à API.

### <a name="evaluation-mode-default"></a>Modo de Avaliação (padrão)

Nenhuma declaração de modelo permite o acesso a APIs com uso limitado por cada aplicativo solicitante para fins de avaliação.

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

> [!NOTE]
> Para obter mais detalhes sobre o recurso chatMessage, consulte o artigo de tipo de recurso [chatMessage](/graph/api/resources/chatmessage) .
