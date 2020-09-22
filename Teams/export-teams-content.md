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
ms.openlocfilehash: 7849892870f54f43f0fda16564ad472426d46cd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171429"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="2f7e8-103">Exportar conteúdo com as APIs de exportação do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f7e8-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="2f7e8-104">As APIs de exportação do teams permitem que você exporte o 1:1 e mensagens de chat em grupo do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="2f7e8-105">Se a sua organização precisa exportar mensagens do Microsoft Teams, você pode poder extraí-las usando as APIs de exportação do teams.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-105">If your organization needs to export Microsoft Teams messages, you can be able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="2f7e8-106">*Mensagem de chat* representa uma mensagem de chat individual em um [canal](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) ou [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="2f7e8-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="2f7e8-107">A mensagem de chat pode ser uma mensagem de chat raiz ou parte de um thread de resposta que é definido pela propriedade **replyToId** na mensagem de chat.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="2f7e8-108">Veja a seguir alguns exemplos de como você pode usar essas APIs de exportação:</span><span class="sxs-lookup"><span data-stu-id="2f7e8-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="2f7e8-109">**Exemplo 1**: se você tiver habilitado o Microsoft Teams em sua organização e quiser exportar todas as mensagens do Microsoft Teams para a data de forma programática passando o intervalo de dados para um determinado usuário.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the data range for a given user.</span></span>
- <span data-ttu-id="2f7e8-110">**Exemplo 2**: se você quiser exportar programaticamente todas as mensagens de usuário diariamente fornecendo um intervalo de dados.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-110">**Example 2**: If you want to programmatically export all user messages daily by providing a data range.</span></span> <span data-ttu-id="2f7e8-111">APIs de exportação podem recuperar todas as mensagens criadas ou atualizadas durante um determinado intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="2f7e8-112">O que é compatível com as APIs de exportação do teams?</span><span class="sxs-lookup"><span data-stu-id="2f7e8-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="2f7e8-113">**Mensagem de exportação em massa da mensagem do teams:** As APIs de exportação do Team dão suporte a até 200 RPS por aplicativo por locatário e 600 RPS para um aplicativo, com esses limites, você deve ser capaz de exportar mensagens de equipe em massa.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="2f7e8-114">**Contexto do aplicativo**: para chamar o Microsoft Graph, seu aplicativo deve adquirir um token de acesso da plataforma de identidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="2f7e8-115">O token de acesso contém informações sobre seu aplicativo e as permissões que ele tem para os recursos e APIs disponíveis por meio do Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="2f7e8-116">Para obter um token de acesso, seu aplicativo deve ser registrado com a plataforma de identidade da Microsoft e ser autorizado por um usuário ou administrador para ter acesso aos recursos do Microsoft Graph necessários.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="2f7e8-117">Se você já estiver familiarizado com a integração de um aplicativo com a plataforma de identidade da Microsoft para obter tokens, consulte a seção [próximas etapas](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) para obter informações e exemplos específicos do Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="2f7e8-118">**Ambiente híbrido:** As APIs de exportação dão suporte a mensagens enviadas por usuários provisionados em um ambiente híbrido (Exchange e Teams locais).</span><span class="sxs-lookup"><span data-stu-id="2f7e8-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="2f7e8-119">Todas as mensagens enviadas por usuários configurados para ambiente híbrido poderão ser acessadas usando APIs de exportação.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="2f7e8-120">**Mensagens excluídas pelo usuário:** As mensagens que são excluídas pelo usuário do teams Client podem ser acessadas usando APIs de exportação de até 30 dias a partir do momento da exclusão.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="2f7e8-121">**Anexos da mensagem:** As APIs de exportação incluem os links para os anexos que são enviados como parte das mensagens.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="2f7e8-122">Usando as APIs de exportação, você pode recuperar os arquivos anexados nas mensagens.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="2f7e8-123">**Propriedades da mensagem de chat:** Consulte a lista completa de propriedades com suporte para APIs de exportação de equipes [aqui](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span><span class="sxs-lookup"><span data-stu-id="2f7e8-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="2f7e8-124">Como acessar as APIs de exportação do teams</span><span class="sxs-lookup"><span data-stu-id="2f7e8-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="2f7e8-125">O **exemplo 1** é uma consulta simples para recuperar todas as mensagens de um usuário sem filtros:</span><span class="sxs-lookup"><span data-stu-id="2f7e8-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET [https://graph.microsoft.com/beta/users/{id}/chats/allMessages](https://graph.microsoft.com/beta/users/%7bid%7d/chats/allMessages)
    ```

- <span data-ttu-id="2f7e8-126">O **exemplo 2** é uma consulta de exemplo para recuperar todas as mensagens de um usuário especificando filtros de data e hora e as principais mensagens de 50:</span><span class="sxs-lookup"><span data-stu-id="2f7e8-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="2f7e8-127">A API retorna a resposta com o link próxima página em caso de vários resultados.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="2f7e8-128">Para obter o próximo conjunto de resultados, basta chamar obter a URL de @odata. Nextlink.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="2f7e8-129">Se @odata. Nextlink não estiver presente ou for NULL, todas as mensagens serão recuperadas.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="2f7e8-130">Pré-requisitos para acessar as APIs de exportação do teams</span><span class="sxs-lookup"><span data-stu-id="2f7e8-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="2f7e8-131">As APIs de exportação do teams estão atualmente em visualização, sujeitas aos termos de uso da Microsoft APIs.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-131">Teams Export APIs are currently in preview, subject to the Microsoft APIs Terms of Use.</span></span>  <span data-ttu-id="2f7e8-132">Ele só estará disponível para usuários e locatários que tenham as licenças necessárias.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-132">It will only be available to users and tenants that have the required licenses.</span></span> <span data-ttu-id="2f7e8-133">As tentativas de acessar APIs sem as licenças adequadas resultarão em um erro 403.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-133">Attempts to access APIs without the proper licenses will result in a 403 error.</span></span>
- <span data-ttu-id="2f7e8-134">As APIs do Microsoft Teams no Microsoft Graph que acessam dados confidenciais são consideradas APIs protegidas.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="2f7e8-135">As APIs de exportação exigem validação adicional, além de permissões e consentimento, para que você possa usá-las.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="2f7e8-136">Para solicitar acesso a essas APIs protegidas, preencha o [formulário de solicitação](https://aka.ms/teamsgraph/requestaccess).</span><span class="sxs-lookup"><span data-stu-id="2f7e8-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="2f7e8-137">As permissões de aplicativo são usadas por aplicativos que são executados sem um usuário conectado presente; as permissões do aplicativo só podem ser consentidas por um administrador.</span><span class="sxs-lookup"><span data-stu-id="2f7e8-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="2f7e8-138">As seguintes permissões são necessárias:</span><span class="sxs-lookup"><span data-stu-id="2f7e8-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="2f7e8-139">*Chat. Read. All*: permite o acesso a todas as 1:1 e mensagens de chat em grupo</span><span class="sxs-lookup"><span data-stu-id="2f7e8-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="2f7e8-140">*User. Read. All*: permite o acesso à lista de usuários para um locatário</span><span class="sxs-lookup"><span data-stu-id="2f7e8-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="2f7e8-141">Representação JSON</span><span class="sxs-lookup"><span data-stu-id="2f7e8-141">JSON representation</span></span>

<span data-ttu-id="2f7e8-142">O exemplo a seguir é uma representação JSON do recurso:</span><span class="sxs-lookup"><span data-stu-id="2f7e8-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="2f7e8-143">Namespace: Microsoft. Graph</span><span class="sxs-lookup"><span data-stu-id="2f7e8-143">Namespace: microsoft.graph</span></span>

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
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="2f7e8-144">Para obter mais detalhes sobre o recurso chatMessage, consulte o artigo [tipo de recurso chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) .</span><span class="sxs-lookup"><span data-stu-id="2f7e8-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>