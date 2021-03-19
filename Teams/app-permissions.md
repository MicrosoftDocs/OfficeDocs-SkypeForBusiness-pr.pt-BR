---
title: Permissões e considerações dos aplicativos Microsoft Teams
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: O administrador pode saber quais dados e permissões os aplicativos do Microsoft Teams estão solicitando de sua organização.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1e6628467d4300130c39a3bade87919fb064a14f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874701"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="dbc71-103">Permissões e considerações dos aplicativos Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbc71-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="dbc71-104">Os aplicativos do Microsoft Teams são uma  maneira de agregar um ou mais recursos em um pacote de aplicativos que podem ser instalados, atualizados e desinstalados.</span><span class="sxs-lookup"><span data-stu-id="dbc71-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="dbc71-105">Os recursos incluem:</span><span class="sxs-lookup"><span data-stu-id="dbc71-105">The capabilities include:</span></span>

- <span data-ttu-id="dbc71-106">Bots</span><span class="sxs-lookup"><span data-stu-id="dbc71-106">Bots</span></span>
- <span data-ttu-id="dbc71-107">Extensões de mensagens</span><span class="sxs-lookup"><span data-stu-id="dbc71-107">Messaging extensions</span></span>
- <span data-ttu-id="dbc71-108">Guias</span><span class="sxs-lookup"><span data-stu-id="dbc71-108">Tabs</span></span>
- <span data-ttu-id="dbc71-109">Conectores</span><span class="sxs-lookup"><span data-stu-id="dbc71-109">Connectors</span></span>

<span data-ttu-id="dbc71-110">Os aplicativos são consentidos pelos usuários e gerenciados por IT de uma perspectiva de política.</span><span class="sxs-lookup"><span data-stu-id="dbc71-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="dbc71-111">No entanto, na maioria das partes, as permissões e o perfil de risco de um aplicativo são definidos pelas permissões e perfis de risco dos recursos que o aplicativo contém.</span><span class="sxs-lookup"><span data-stu-id="dbc71-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="dbc71-112">Portanto, este artigo se concentra em permissões e considerações no nível de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="dbc71-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="dbc71-113">As permissões listadas abaixo em letras [maiúsculas,](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)por exemplo, RECEIVE_MESSAGE e REPLYTO_MESSAGE, não aparecem em qualquer lugar na documentação de desenvolvedor do [Microsoft Teams](https://aka.ms/teamsdevdocs) ou nas permissões do Microsoft Graph .</span><span class="sxs-lookup"><span data-stu-id="dbc71-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="dbc71-114">Eles são simplesmente uma taquigrafia descritiva para a finalidade deste artigo.</span><span class="sxs-lookup"><span data-stu-id="dbc71-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="dbc71-115">Título</span><span class="sxs-lookup"><span data-stu-id="dbc71-115">Title</span></span>   | <span data-ttu-id="dbc71-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="dbc71-116">Description</span></span>    |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="dbc71-118">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="dbc71-118">Decision point</span></span>|<ul><li><span data-ttu-id="dbc71-119">Use as tabelas abaixo como um guia para entender quais permissões os aplicativos que você está investigando estão solicitando.</span><span class="sxs-lookup"><span data-stu-id="dbc71-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Um ícone representando o passo seguinte](media/audio_conferencing_image9.png)<br/><span data-ttu-id="dbc71-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="dbc71-121">Next step</span></span>|<ul><li><span data-ttu-id="dbc71-122">Pesquise o aplicativo ou o próprio serviço para decidir se você deseja permitir o acesso a ele em sua organização.</span><span class="sxs-lookup"><span data-stu-id="dbc71-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="dbc71-123">Por exemplo, os bots enviam e recebem mensagens de usuários e, exceto para bots personalizados da empresa, eles estão localizados fora do limite de conformidade.</span><span class="sxs-lookup"><span data-stu-id="dbc71-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="dbc71-124">Portanto, qualquer aplicativo que inclua um bot exige essas permissões e tem esse perfil de risco, no mínimo.</span><span class="sxs-lookup"><span data-stu-id="dbc71-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="dbc71-125">Consulte também [Solicitar permissões de dispositivo para sua guia do Microsoft Teams.](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)</span><span class="sxs-lookup"><span data-stu-id="dbc71-125">See also [Request device permissions for your Microsoft Teams tab](https://docs.microsoft.com/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="dbc71-126">Considerações e permissões globais do aplicativo</span><span class="sxs-lookup"><span data-stu-id="dbc71-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="dbc71-127">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="dbc71-127">Required permissions</span></span>

<span data-ttu-id="dbc71-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dbc71-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="dbc71-129">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="dbc71-129">Optional permissions</span></span>

<span data-ttu-id="dbc71-130">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dbc71-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="dbc71-131">Considerações</span><span class="sxs-lookup"><span data-stu-id="dbc71-131">Considerations</span></span>

- <span data-ttu-id="dbc71-132">Um aplicativo deve divulgar quais dados ele usa e para que os dados são usados em seus termos de uso e links de política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="dbc71-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="dbc71-133">[O consentimento específico do recurso](resource-specific-consent.md) fornece um conjunto de permissões que os aplicativos podem solicitar, que aparece na tela de instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dbc71-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="dbc71-134">Para saber mais sobre permissões de consentimento específicas do recurso, consulte [Referência de permissões do Graph.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="dbc71-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="dbc71-135">Os aplicativos também podem precisar de permissões diferentes de permissões de consentimento específicas do recurso.</span><span class="sxs-lookup"><span data-stu-id="dbc71-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="dbc71-136">Depois que um aplicativo é instalado, o aplicativo pode solicitar permissões do Graph por meio de um prompt de consentimento.</span><span class="sxs-lookup"><span data-stu-id="dbc71-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="dbc71-137">Para saber mais, consulte [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span><span class="sxs-lookup"><span data-stu-id="dbc71-137">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="dbc71-138">Você pode configurar permissões de API e consentimento no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dbc71-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="dbc71-139">Para saber mais, confira [a estrutura de consentimento do Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="dbc71-139">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="dbc71-140">Bots e extensões de mensagens</span><span class="sxs-lookup"><span data-stu-id="dbc71-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="dbc71-141">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="dbc71-141">Required permissions</span></span>

- <span data-ttu-id="dbc71-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="dbc71-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="dbc71-143">O bot pode receber mensagens dos usuários e responder a eles. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dbc71-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="dbc71-144">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="dbc71-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="dbc71-145">Depois que um usuário envia uma mensagem para um bot, o bot pode enviar mensagens diretas do usuário (também chamadas de mensagens *proativas* a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="dbc71-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="dbc71-146">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="dbc71-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="dbc71-147">Bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais em uma equipe.</span><span class="sxs-lookup"><span data-stu-id="dbc71-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="dbc71-148">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="dbc71-148">Optional permissions</span></span>

- <span data-ttu-id="dbc71-149">IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="dbc71-149">IDENTITY.</span></span> <span data-ttu-id="dbc71-150">Quando ele é usado em um canal, os bots do aplicativo podem acessar informações básicas de identidade dos membros da equipe (nome, sobrenome, nome principal do usuário [UPN], endereço de email); quando é usado em um chat pessoal ou em grupo, o bot pode acessar as mesmas informações para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="dbc71-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="dbc71-151">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="dbc71-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="dbc71-152">Permite que os bots de um aplicativo enviem mensagens diretas (proativas) a qualquer membro da equipe a qualquer momento, mesmo que o usuário nunca tenha falado com o bot antes.</span><span class="sxs-lookup"><span data-stu-id="dbc71-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="dbc71-153">Os seguintes não são permissões explícitas, mas estão implícitos por RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots podem ser usados, declarados no manifesto:</span><span class="sxs-lookup"><span data-stu-id="dbc71-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="dbc71-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="dbc71-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="dbc71-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="dbc71-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="dbc71-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="dbc71-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="dbc71-157">SEND_FILES, RECEIVE_FILES. <sup>2</sup> Controla se um bot pode enviar e receber arquivos no chat pessoal (ainda não há suporte para chat em grupo ou canais).</span><span class="sxs-lookup"><span data-stu-id="dbc71-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="dbc71-158">Considerações</span><span class="sxs-lookup"><span data-stu-id="dbc71-158">Considerations</span></span>

- <span data-ttu-id="dbc71-159">Os bots têm acesso apenas às equipes às quais foram adicionadas ou aos usuários que as instalaram.</span><span class="sxs-lookup"><span data-stu-id="dbc71-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="dbc71-160">Os bots só recebem mensagens nas quais são explicitamente mencionados pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="dbc71-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="dbc71-161">Esses dados deixam a rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="dbc71-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="dbc71-162">Os bots só podem responder às conversas nas quais são mencionados.</span><span class="sxs-lookup"><span data-stu-id="dbc71-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="dbc71-163">Depois que um usuário conversar com um bot, se o bot armazenar a ID desse usuário, ele poderá enviar mensagens diretas desse usuário a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="dbc71-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="dbc71-164">Teoricamente, é possível que as mensagens bot contenham links para sites de phishing ou malware, mas os bots podem ser bloqueados pelo usuário, pelo administrador do locatário ou globalmente pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dbc71-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="dbc71-165">Um bot pode recuperar (e pode armazenar) informações de identidade muito básicas para os membros da equipe aos que o aplicativo foi adicionado ou para usuários individuais em chats pessoais ou de grupo.</span><span class="sxs-lookup"><span data-stu-id="dbc71-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="dbc71-166">Para obter mais informações sobre esses usuários, o bot deve exigir que eles entre no Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="dbc71-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="dbc71-167">Os bots podem recuperar (e podem armazenar) a lista de canais em uma equipe; esses dados deixam a rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="dbc71-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="dbc71-168">Quando um arquivo é enviado para um bot, o arquivo deixa a rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="dbc71-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="dbc71-169">O envio e recebimento de arquivos requer aprovação do usuário para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbc71-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="dbc71-170">Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem pedir aos usuários para entrar; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer coisas adicionais.</span><span class="sxs-lookup"><span data-stu-id="dbc71-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="dbc71-171">Exatamente o que essas coisas adicionais são depende do bot e de onde o usuário faz o acesso: um bot é um aplicativo do Azure AD registrado e pode ter seu próprio conjunto https://apps.dev.microsoft.com/ de permissões.</span><span class="sxs-lookup"><span data-stu-id="dbc71-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="dbc71-172">Os bots são informados sempre que os usuários são adicionados ou excluídos de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="dbc71-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="dbc71-173">Os bots não veem os endereços IP dos usuários ou outras informações de referência.</span><span class="sxs-lookup"><span data-stu-id="dbc71-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="dbc71-174">Todas as informações vêm da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dbc71-174">All information comes from Microsoft.</span></span> <span data-ttu-id="dbc71-175">(Há uma exceção: se um bot implementar sua própria experiência de login, a interface do usuário de login verá os endereços IP dos usuários e informações de referência.)</span><span class="sxs-lookup"><span data-stu-id="dbc71-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="dbc71-176">As extensões de mensagens, por outro lado, veem os endereços IP dos usuários e informações de referência.</span><span class="sxs-lookup"><span data-stu-id="dbc71-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="dbc71-177">As diretrizes do aplicativo (e nosso processo de revisão do AppSource) exigem discrição na postagem de mensagens de chat pessoais aos usuários (por meio da permissão POST_MESSAGE_TEAM) para fins válidos.</span><span class="sxs-lookup"><span data-stu-id="dbc71-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="dbc71-178">Em caso de abuso, os usuários podem bloquear o bot, os administradores de locatários podem bloquear o aplicativo e a Microsoft pode bloquear os bots centralmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="dbc71-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="dbc71-179"><sup>1</sup> Alguns bots só enviam mensagens (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="dbc71-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="dbc71-180">Eles são chamados de bots "somente notificação", mas o termo não se refere ao que um bot é permitido ou não pode fazer, isso significa que o bot não quer expor uma experiência de conversa.</span><span class="sxs-lookup"><span data-stu-id="dbc71-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="dbc71-181">O Teams usa esse campo para desabilitar a funcionalidade na interface do usuário que normalmente seria habilitada; o bot não é restrito no que é permitido fazer em comparação com bots que expõem uma experiência de conversa.</span><span class="sxs-lookup"><span data-stu-id="dbc71-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="dbc71-182"><sup>2</sup> Governada pela propriedade supportsFiles Boolean no objeto bot no arquivo manifest.json para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dbc71-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="dbc71-183">Se um bot tiver sua própria assinatura, haverá uma segunda experiência de consentimento diferente na primeira vez em que o usuário entrar.</span><span class="sxs-lookup"><span data-stu-id="dbc71-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="dbc71-184">Atualmente, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo do Teams (bot, guia, conector ou extensão de mensagens) estão completamente separadas das permissões do Teams listadas aqui.</span><span class="sxs-lookup"><span data-stu-id="dbc71-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="dbc71-185">Guias</span><span class="sxs-lookup"><span data-stu-id="dbc71-185">Tabs</span></span>

<span data-ttu-id="dbc71-186">Uma guia é um site em execução no Teams.</span><span class="sxs-lookup"><span data-stu-id="dbc71-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="dbc71-187">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="dbc71-187">Required permissions</span></span>

<span data-ttu-id="dbc71-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="dbc71-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="dbc71-189">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="dbc71-189">Optional permissions</span></span>

<span data-ttu-id="dbc71-190">Nenhum (no momento)</span><span class="sxs-lookup"><span data-stu-id="dbc71-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="dbc71-191">Considerações</span><span class="sxs-lookup"><span data-stu-id="dbc71-191">Considerations</span></span>

- <span data-ttu-id="dbc71-192">O perfil de risco de uma guia é quase idêntico ao mesmo site em execução em uma guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="dbc71-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="dbc71-193">Uma guia também obtém o contexto em que está sendo executado, incluindo o nome de login e o UPN do usuário atual, a ID do Objeto do Azure AD para o usuário atual, a ID do Grupo do Microsoft 365 no qual ele reside (se for uma equipe), a ID do locatário e a localidade atual do usuário.</span><span class="sxs-lookup"><span data-stu-id="dbc71-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="dbc71-194">No entanto, para mapear essas IDs para as informações de um usuário, a guia teria que fazer o usuário entrar no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dbc71-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="dbc71-195">Conectores</span><span class="sxs-lookup"><span data-stu-id="dbc71-195">Connectors</span></span>

<span data-ttu-id="dbc71-196">Um conector posta mensagens em um canal quando ocorrem eventos em um sistema externo.</span><span class="sxs-lookup"><span data-stu-id="dbc71-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="dbc71-197">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="dbc71-197">Required permissions</span></span>

<span data-ttu-id="dbc71-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="dbc71-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="dbc71-199">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="dbc71-199">Optional permissions</span></span>

<span data-ttu-id="dbc71-200">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="dbc71-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="dbc71-201">Certos conectores suportam mensagens ativas, que permitem que os usuários postem respostas direcionadas à mensagem do conector, por exemplo, adicionando uma resposta a um problema do GitHub ou adicionando uma data a um cartão Trello.</span><span class="sxs-lookup"><span data-stu-id="dbc71-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="dbc71-202">Considerações</span><span class="sxs-lookup"><span data-stu-id="dbc71-202">Considerations</span></span>

- <span data-ttu-id="dbc71-203">O sistema que posta mensagens do conector não sabe para quem está postando ou quem recebe as mensagens: nenhuma informação sobre o destinatário é divulgada.</span><span class="sxs-lookup"><span data-stu-id="dbc71-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="dbc71-204">(A Microsoft é o destinatário real, não o locatário; A Microsoft faz a postagem real no canal.)</span><span class="sxs-lookup"><span data-stu-id="dbc71-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="dbc71-205">Nenhum dado deixa a rede corporativa quando as mensagens do conector são postadas em um canal.</span><span class="sxs-lookup"><span data-stu-id="dbc71-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="dbc71-206">Conectores que suportam mensagens ativas (REPLYTO_CONNECTOR_MESSAGE permissão) também não veem endereço IP e informações de referência; essas informações são enviadas para a Microsoft e roteadas para pontos de extremidade HTTP que foram registrados anteriormente com a Microsoft no portal conectores.</span><span class="sxs-lookup"><span data-stu-id="dbc71-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="dbc71-207">Sempre que um conector é configurado para um canal, uma URL exclusiva para essa instância do conector é criada.</span><span class="sxs-lookup"><span data-stu-id="dbc71-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="dbc71-208">Se essa instância do conector for excluída, a URL não poderá mais ser usada.</span><span class="sxs-lookup"><span data-stu-id="dbc71-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="dbc71-209">As mensagens do conector não podem conter anexos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="dbc71-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="dbc71-210">A URL da instância do conector deve ser tratada como secreta/confidencial: qualquer pessoa que tenha essa URL pode postá-la, como um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="dbc71-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="dbc71-211">Portanto, há algum risco de spam ou links para phishing ou sites de malware.</span><span class="sxs-lookup"><span data-stu-id="dbc71-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="dbc71-212">Se isso acontecer, os proprietários da equipe poderão excluir a instância do conector.</span><span class="sxs-lookup"><span data-stu-id="dbc71-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="dbc71-213">Se o serviço que envia mensagens do conector se tornar comprometido e começar a enviar links de spam/phishing/malware, um administrador de locatários poderá impedir a criação de novas instâncias do conector e a Microsoft poderá bloqueá-las centralmente.</span><span class="sxs-lookup"><span data-stu-id="dbc71-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="dbc71-214">No momento, não é possível saber quais conectores suportam mensagens ativas (REPLYTO_CONNECTOR_MESSAGE permissão).</span><span class="sxs-lookup"><span data-stu-id="dbc71-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="dbc71-215">Webhooks de saída</span><span class="sxs-lookup"><span data-stu-id="dbc71-215">Outgoing webhooks</span></span>

<span data-ttu-id="dbc71-216">*Webhooks de saída* são criados em tempo real por proprietários de equipe ou membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="dbc71-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="dbc71-217">Eles não são recursos de aplicativos do Teams; essas informações são incluídas para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="dbc71-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="dbc71-218">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="dbc71-218">Required permissions</span></span>

<span data-ttu-id="dbc71-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="dbc71-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="dbc71-220">Pode receber mensagens dos usuários e responder a eles.</span><span class="sxs-lookup"><span data-stu-id="dbc71-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="dbc71-221">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="dbc71-221">Optional permissions</span></span>

<span data-ttu-id="dbc71-222">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dbc71-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="dbc71-223">Considerações</span><span class="sxs-lookup"><span data-stu-id="dbc71-223">Considerations</span></span>

- <span data-ttu-id="dbc71-224">Os webhooks de saída são semelhantes aos bots, mas têm menos privilégios.</span><span class="sxs-lookup"><span data-stu-id="dbc71-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="dbc71-225">Eles devem ser explicitamente mencionados, assim como os bots.</span><span class="sxs-lookup"><span data-stu-id="dbc71-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="dbc71-226">Quando um webhook de saída é registrado, um segredo é gerado, o que permite que o webhook de saída verifique se o remetente é o Microsoft Teams em vez de um invasor mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="dbc71-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="dbc71-227">Esse segredo deve permanecer em segredo; qualquer pessoa que tenha acesso a ela pode representar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dbc71-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="dbc71-228">Se o segredo for comprometido, o webhook de saída poderá ser excluído e re-criado, e um novo segredo será gerado.</span><span class="sxs-lookup"><span data-stu-id="dbc71-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="dbc71-229">Embora seja possível criar um webhook de saída que não valide o segredo, recomendamos isso.</span><span class="sxs-lookup"><span data-stu-id="dbc71-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="dbc71-230">Além de receber e responder mensagens, os webhooks de saída não podem fazer muito: eles não podem enviar mensagens de forma proativa, não podem enviar ou receber arquivos, não podem fazer mais nada que os bots possam fazer, exceto receber e responder a mensagens.</span><span class="sxs-lookup"><span data-stu-id="dbc71-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
