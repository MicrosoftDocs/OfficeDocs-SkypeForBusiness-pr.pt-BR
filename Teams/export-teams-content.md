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
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="57e6d-103">Exportar conteúdo com as APIs de Exportação do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57e6d-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="57e6d-104">As APIs de Exportação do Teams permitem que você exporte 1:1, chat em grupo, chats de reunião e mensagens de canal do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="57e6d-104">Teams Export APIs allow you to export 1:1, group chat, meeting chats, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="57e6d-105">Se sua organização precisar exportar mensagens do Microsoft Teams, você poderá extraí-las usando APIs de Exportação do Teams.</span><span class="sxs-lookup"><span data-stu-id="57e6d-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="57e6d-106">*Mensagem de chat* representa uma mensagem de chat individual dentro de [um canal](/graph/api/resources/channel?view=graph-rest-beta) ou [chat](/graph/api/resources/chat?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="57e6d-106">*Chat Message* represents an individual chat message within a [channel](/graph/api/resources/channel?view=graph-rest-beta) or [chat](/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="57e6d-107">A mensagem de chat pode ser uma mensagem de chat raiz ou parte de um thread de resposta definido pela **propriedade replyToId** na mensagem de chat.</span><span class="sxs-lookup"><span data-stu-id="57e6d-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="57e6d-108">Aqui estão alguns exemplos sobre como você pode usar essas APIs de exportação:</span><span class="sxs-lookup"><span data-stu-id="57e6d-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="57e6d-109">**Exemplo 1**: Se você habilitar o Microsoft Teams em sua organização e quiser exportar todas as mensagens do Microsoft Teams para datar programaticamente passando o intervalo de datas para um determinado usuário ou equipe.</span><span class="sxs-lookup"><span data-stu-id="57e6d-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="57e6d-110">**Exemplo 2**: Se você quiser exportar programaticamente todas as mensagens de usuário ou equipe diariamente, fornecendo um intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="57e6d-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="57e6d-111">As APIs de exportação podem recuperar todas as mensagens criadas ou atualizadas durante o intervalo de datas determinado.</span><span class="sxs-lookup"><span data-stu-id="57e6d-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="57e6d-112">O que é suportado pelas APIs de Exportação do Teams?</span><span class="sxs-lookup"><span data-stu-id="57e6d-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="57e6d-113">**Exportação em massa da mensagem do Teams:** As APIs de Exportação do Teams suportam até 200 RPS por locatário por aplicativo e 600 RPS para um Aplicativo, com esses limites, você deve ser capaz de exportar em massa mensagens do Teams.</span><span class="sxs-lookup"><span data-stu-id="57e6d-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="57e6d-114">**Contexto do aplicativo**: Para chamar o Microsoft Graph, seu aplicativo deve adquirir um token de acesso da plataforma de identidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="57e6d-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="57e6d-115">O token de acesso contém informações sobre seu aplicativo e as permissões que ele tem para os recursos e APIs disponíveis por meio do Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="57e6d-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="57e6d-116">Para obter um token de acesso, seu aplicativo deve ser registrado na plataforma de identidade da Microsoft e ser autorizado por um usuário ou um administrador para acessar os recursos do Microsoft Graph necessários.</span><span class="sxs-lookup"><span data-stu-id="57e6d-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="57e6d-117">Se você já estiver familiarizado com a integração de um aplicativo [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) com a plataforma de identidade da Microsoft para obter tokens, consulte a seção Próximas Etapas para obter informações e exemplos específicos do Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="57e6d-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="57e6d-118">**Ambiente Híbrido:** Exportar APIs suportam mensagens enviadas por usuários provisionados em Ambiente Híbrido (Exchange e Teams locais).</span><span class="sxs-lookup"><span data-stu-id="57e6d-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="57e6d-119">Todas as mensagens enviadas por usuários configurados para ambiente híbrido estarão acessíveis usando APIs de Exportação.</span><span class="sxs-lookup"><span data-stu-id="57e6d-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="57e6d-120">**Mensagens excluídas pelo usuário:** As mensagens excluídas pelos usuários do cliente teams podem ser acessadas usando APIs de exportação até 21 dias a partir do momento da exclusão.</span><span class="sxs-lookup"><span data-stu-id="57e6d-120">**User Deleted Messages:** Messages that are deleted by users from the Teams client can be accessed using export APIs up to 21 days from the time of deletion.</span></span>
- <span data-ttu-id="57e6d-121">**Anexos de mensagem:** As APIs de exportação incluem os links para os anexos enviados como parte das mensagens.</span><span class="sxs-lookup"><span data-stu-id="57e6d-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="57e6d-122">Usando as APIs de Exportação, você pode recuperar os arquivos anexados nas mensagens.</span><span class="sxs-lookup"><span data-stu-id="57e6d-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="57e6d-123">**Propriedades da mensagem de chat:** Consulte a lista completa de propriedades que as APIs de Exportação do Teams suportam [aqui](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span><span class="sxs-lookup"><span data-stu-id="57e6d-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="57e6d-124">Como acessar APIs de Exportação do Teams</span><span class="sxs-lookup"><span data-stu-id="57e6d-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="57e6d-125">**O Exemplo 1** é uma consulta simples para recuperar todas as mensagens de um usuário ou equipe sem filtros:</span><span class="sxs-lookup"><span data-stu-id="57e6d-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages
    ```

- <span data-ttu-id="57e6d-126">**O Exemplo 2** é uma consulta de exemplo para recuperar todas as mensagens de um usuário ou equipe especificando os filtros de data e as 50 principais mensagens:</span><span class="sxs-lookup"><span data-stu-id="57e6d-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
><span data-ttu-id="57e6d-127">A API retorna a resposta com o link da próxima página em caso de vários resultados.</span><span class="sxs-lookup"><span data-stu-id="57e6d-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="57e6d-128">Para obter o próximo conjunto de resultados, basta chamar GET na url de @odata.nextlink.</span><span class="sxs-lookup"><span data-stu-id="57e6d-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="57e6d-129">Se @odata.nextlink não estiver presente ou nulo, todas as mensagens serão recuperadas.</span><span class="sxs-lookup"><span data-stu-id="57e6d-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="57e6d-130">Pré-requisitos para acessar APIs de Exportação do Teams</span><span class="sxs-lookup"><span data-stu-id="57e6d-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="57e6d-131">As APIs de Exportação do Teams estão atualmente em visualização.</span><span class="sxs-lookup"><span data-stu-id="57e6d-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="57e6d-132">Ele só estará disponível para usuários e locatários que tenham as [licenças necessárias](/graph/teams-licenses) para APIs.</span><span class="sxs-lookup"><span data-stu-id="57e6d-132">It will only be available to users and tenants that have the [required licenses](/graph/teams-licenses) for APIs.</span></span> <span data-ttu-id="57e6d-133">No futuro, a Microsoft pode exigir que você ou seus clientes paguem taxas adicionais com base na quantidade de dados acessados por meio da API.</span><span class="sxs-lookup"><span data-stu-id="57e6d-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="57e6d-134">As APIs do Microsoft Teams no Microsoft Graph que acessam dados confidenciais são consideradas APIs protegidas.</span><span class="sxs-lookup"><span data-stu-id="57e6d-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="57e6d-135">As APIs de exportação exigem que você tenha validação adicional, além de permissões e consentimento, antes de poder usá-las.</span><span class="sxs-lookup"><span data-stu-id="57e6d-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="57e6d-136">Para solicitar acesso a essas APIs protegidas, preencha o formulário [de solicitação](https://aka.ms/teamsgraph/requestaccess).</span><span class="sxs-lookup"><span data-stu-id="57e6d-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="57e6d-137">As permissões de aplicativo são usadas por aplicativos que são executados sem um usuário in-locar presente; permissões de aplicativo só podem ser consentida por um administrador.</span><span class="sxs-lookup"><span data-stu-id="57e6d-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="57e6d-138">As seguintes permissões são necessárias:</span><span class="sxs-lookup"><span data-stu-id="57e6d-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="57e6d-139">*Chat.Read.All*: habilita o acesso a todas as mensagens de chat de grupo e 1:1</span><span class="sxs-lookup"><span data-stu-id="57e6d-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="57e6d-140">*User.Read.All*: habilita o acesso à lista de usuários para um locatário</span><span class="sxs-lookup"><span data-stu-id="57e6d-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="57e6d-141">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="57e6d-141">JSON representation</span></span>

<span data-ttu-id="57e6d-142">O exemplo a seguir é uma representação JSON do recurso:</span><span class="sxs-lookup"><span data-stu-id="57e6d-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="57e6d-143">Namespace: microsoft.graph</span><span class="sxs-lookup"><span data-stu-id="57e6d-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="57e6d-144">Para obter mais detalhes sobre o recurso chatMessage, consulte o artigo tipo de recurso [chatMessage.](/graph/api/resources/chatmessage)</span><span class="sxs-lookup"><span data-stu-id="57e6d-144">For more details on chatMessage resource, see the [chatMessage resource type](/graph/api/resources/chatmessage) article.</span></span>