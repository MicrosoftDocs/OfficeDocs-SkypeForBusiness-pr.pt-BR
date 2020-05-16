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
description: O administrador pode aprender quais dados e permissões os aplicativos do Microsoft Teams estão solicitando na organização.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f19cbbba6df7c43c69af35893466344e8df1d17d
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256476"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="c9807-103">Permissões e considerações dos aplicativos Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9807-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="c9807-104">Os aplicativos Microsoft Teams são uma forma de agregar um ou mais recursos em um _pacote de aplicativo_ que pode ser instalado, atualizado e desinstalado.</span><span class="sxs-lookup"><span data-stu-id="c9807-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="c9807-105">Os recursos incluem:</span><span class="sxs-lookup"><span data-stu-id="c9807-105">The capabilities include:</span></span>

- <span data-ttu-id="c9807-106">Bots</span><span class="sxs-lookup"><span data-stu-id="c9807-106">Bots</span></span>
- <span data-ttu-id="c9807-107">Extensões de mensagens</span><span class="sxs-lookup"><span data-stu-id="c9807-107">Messaging extensions</span></span>
- <span data-ttu-id="c9807-108">Guias</span><span class="sxs-lookup"><span data-stu-id="c9807-108">Tabs</span></span>
- <span data-ttu-id="c9807-109">Conectores</span><span class="sxs-lookup"><span data-stu-id="c9807-109">Connectors</span></span>

<span data-ttu-id="c9807-110">Os aplicativos são aceitos pelos usuários e gerenciados pela TI a partir de uma perspectiva política.</span><span class="sxs-lookup"><span data-stu-id="c9807-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="c9807-111">No entanto, para a maioria das partes, as permissões e o perfil de risco de um aplicativo são definidos pelas permissões e pelos perfis de risco das funcionalidades que o aplicativo contém.</span><span class="sxs-lookup"><span data-stu-id="c9807-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="c9807-112">Assim, este artigo foca em permissões e considerações no nível de recurso.</span><span class="sxs-lookup"><span data-stu-id="c9807-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="c9807-113">As permissões listadas abaixo em maiúsculas, por exemplo, RECEIVE_MESSAGE e REPLYTO_MESSAGE, não aparece em nenhum lugar da [documentação do desenvolvedor do Microsoft Teams](https://aka.ms/teamsdevdocs) nem no [Gráfico de permissões da Microsoft](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="c9807-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="c9807-114">São somente uma abreviação descritiva para o propósito deste artigo.</span><span class="sxs-lookup"><span data-stu-id="c9807-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c9807-116">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="c9807-116">Decision point</span></span>|<ul><li><span data-ttu-id="c9807-117">Use as tabelas a seguir como um guia para entender quais permissões os aplicativos que você está investigando estão solicitando.</span><span class="sxs-lookup"><span data-stu-id="c9807-117">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![Um ícone representando o passo seguinte](media/audio_conferencing_image9.png)<br/><span data-ttu-id="c9807-119">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c9807-119">Next step</span></span>|<ul><li><span data-ttu-id="c9807-120">Pesquise o aplicativo ou o próprio serviço para decidir se deseja permitir o acesso a ele dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c9807-120">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="c9807-121">Por exemplo, os bots enviam e recebem mensagens de usuários e, exceto para os bots personalizados da empresa, eles estão localizados fora do limite de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c9807-121">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="c9807-122">Portanto, qualquer aplicativo que inclua um bot requer essas permissões e tem esse perfil de risco, no mínimo.</span><span class="sxs-lookup"><span data-stu-id="c9807-122">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="c9807-123">Permissões e considerações globais do aplicativo</span><span class="sxs-lookup"><span data-stu-id="c9807-123">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="c9807-124">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c9807-124">Required permissions</span></span>

<span data-ttu-id="c9807-125">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c9807-125">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="c9807-126">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="c9807-126">Optional permissions</span></span>

<span data-ttu-id="c9807-127">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c9807-127">None</span></span>

### <a name="considerations"></a><span data-ttu-id="c9807-128">Considerações</span><span class="sxs-lookup"><span data-stu-id="c9807-128">Considerations</span></span>

- <span data-ttu-id="c9807-129">Um aplicativo deve divulgar quais dados ele usa e o que os dados são usados nos termos de uso e nos links da política de privacidade.</span><span class="sxs-lookup"><span data-stu-id="c9807-129">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="c9807-130">O [consentimento específico do recurso](resource-specific-consent.md) fornece um conjunto de permissões que os aplicativos podem solicitar, que aparecem na tela de instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c9807-130">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="c9807-131">Para saber mais sobre permissões de consentimento específicas do recurso, consulte [referência de permissões de gráfico](https://docs.microsoft.com/graph/permissions-reference).</span><span class="sxs-lookup"><span data-stu-id="c9807-131">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference).</span></span>

- <span data-ttu-id="c9807-132">Os aplicativos também podem precisar de permissões diferentes de permissões de consentimento específicas do recurso.</span><span class="sxs-lookup"><span data-stu-id="c9807-132">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="c9807-133">Após a instalação de um aplicativo, o aplicativo pode solicitar permissões de gráfico por meio de um prompt de consentimento.</span><span class="sxs-lookup"><span data-stu-id="c9807-133">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="c9807-134">Para saber mais, consulte [noções básicas sobre experiências de consentimento de aplicativos do Azure ad](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span><span class="sxs-lookup"><span data-stu-id="c9807-134">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="c9807-135">Você pode configurar permissões de API e consentimento no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c9807-135">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="c9807-136">Para saber mais, consulte [estrutura de consentimento do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span><span class="sxs-lookup"><span data-stu-id="c9807-136">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="c9807-137">Bots e extensões de mensagens</span><span class="sxs-lookup"><span data-stu-id="c9807-137">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="c9807-138">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c9807-138">Required permissions</span></span>

- <span data-ttu-id="c9807-139">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="c9807-139">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="c9807-140">O bot pode receber mensagens de usuários e respondê-las. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c9807-140">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="c9807-141">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="c9807-141">POST_MESSAGE_USER.</span></span> <span data-ttu-id="c9807-142">Depois que um usuário envia uma mensagem para um bot, o bot pode enviar mensagens diretas ao usuário (também chamadas de *mensagens proativas* a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="c9807-142">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="c9807-143">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="c9807-143">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="c9807-144">Os bots adicionados às equipes podem obter uma lista de nomes e IDs dos canais de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="c9807-144">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="c9807-145">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="c9807-145">Optional permissions</span></span>

- <span data-ttu-id="c9807-146">Entidade.</span><span class="sxs-lookup"><span data-stu-id="c9807-146">IDENTITY.</span></span> <span data-ttu-id="c9807-147">Quando ele é usado em um canal, os bots do aplicativo podem acessar informações de identidade básicas dos membros da equipe (nome, sobrenome, nome UPN, endereço de email); Quando ele é usado em um chat pessoal ou em grupo, o bot pode acessar as mesmas informações para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="c9807-147">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="c9807-148">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="c9807-148">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="c9807-149">Permite que os bots de um aplicativo enviem mensagens diretas (pró-ativas) para qualquer membro da equipe a qualquer momento, mesmo que o usuário nunca tenha se falado ao bot antes.</span><span class="sxs-lookup"><span data-stu-id="c9807-149">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="c9807-150">As seguintes permissões não são explícitas, mas são implícitas por RECEIVE_MESSAGE e REPLYTO_MESSAGE e os escopos nos quais os bots podem ser usados, declarados no manifesto:</span><span class="sxs-lookup"><span data-stu-id="c9807-150">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="c9807-151">RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="c9807-151">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="c9807-152">RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="c9807-152">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="c9807-153">RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="c9807-153">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="c9807-154">SEND_FILES RECEIVE_FILES. <sup>2</sup> controla se um bot pode enviar e receber arquivos em um chat pessoal (ainda não compatível com o chat em grupo ou canais).</span><span class="sxs-lookup"><span data-stu-id="c9807-154">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="c9807-155">Considerações</span><span class="sxs-lookup"><span data-stu-id="c9807-155">Considerations</span></span>

- <span data-ttu-id="c9807-156">Os bots só têm acesso às equipes às quais foram adicionados ou aos usuários que os instalaram.</span><span class="sxs-lookup"><span data-stu-id="c9807-156">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="c9807-157">Os bots recebem apenas mensagens que são explicitamente mencionadas pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="c9807-157">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="c9807-158">Esses dados saem da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="c9807-158">This data leaves the corporate network.</span></span>

- <span data-ttu-id="c9807-159">Os bots só podem responder a conversas nas quais são mencionados.</span><span class="sxs-lookup"><span data-stu-id="c9807-159">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="c9807-160">Depois que um usuário tiver disparado com um bot, se o bot armazenar a ID do usuário, ele poderá enviar mensagens diretas ao usuário a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="c9807-160">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="c9807-161">Teoricamente, é possível que as mensagens de bot contenham links para sites de phishing ou de malware, mas os bots podem ser bloqueados pelo usuário, pelo administrador de locatários ou globalmente pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9807-161">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="c9807-162">Um bot pode recuperar (e pode armazenar) informações de identidade muito básicas para os membros da equipe para os quais o aplicativo foi adicionado ou para usuários individuais em chats pessoais ou em grupo.</span><span class="sxs-lookup"><span data-stu-id="c9807-162">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="c9807-163">Para obter mais informações sobre esses usuários, o bot deve exigir que eles entrem no Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c9807-163">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="c9807-164">Os bots podem recuperar (e podem armazenar) a lista de canais em uma equipe; esses dados saem da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="c9807-164">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="c9807-165">Quando um arquivo é enviado a um bot, o arquivo sai da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="c9807-165">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="c9807-166">O envio e recebimento de arquivos requer a aprovação do usuário para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="c9807-166">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="c9807-167">Por padrão, os bots não têm a capacidade de agir em nome do usuário, mas os bots podem solicitar que os usuários entrem; assim que o usuário entrar, o bot terá um token de acesso com o qual poderá fazer outras coisas.</span><span class="sxs-lookup"><span data-stu-id="c9807-167">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="c9807-168">Exatamente o que essas coisas adicionais dependem do bot e do local em que o usuário entra: um bot é um aplicativo do Azure AD registrado em https://apps.dev.microsoft.com/ e pode ter seu próprio conjunto de permissões.</span><span class="sxs-lookup"><span data-stu-id="c9807-168">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="c9807-169">Os bots são informados sempre que os usuários são adicionados ou excluídos de uma equipe.</span><span class="sxs-lookup"><span data-stu-id="c9807-169">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="c9807-170">Os bots não visualizam os endereços IP dos usuários nem outras informações referenciais.</span><span class="sxs-lookup"><span data-stu-id="c9807-170">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="c9807-171">Todas as informações vêm da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9807-171">All information comes from Microsoft.</span></span> <span data-ttu-id="c9807-172">(Há uma exceção: se um bot implementar sua própria experiência de entrada, a interface do usuário de entrada exibirá os endereços IP e as informações de referenciador dos usuários.)</span><span class="sxs-lookup"><span data-stu-id="c9807-172">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="c9807-173">As extensões de mensagens, por outro lado, podem ver os endereços IP e as informações referenciais dos usuários.</span><span class="sxs-lookup"><span data-stu-id="c9807-173">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="c9807-174">As diretrizes do aplicativo (e o processo de revisão do AppSource) exigem critério de postagem de mensagens de chat pessoais para usuários (por meio da permissão POST_MESSAGE_TEAM) para fins válidos.</span><span class="sxs-lookup"><span data-stu-id="c9807-174">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="c9807-175">Em caso de abuso, os usuários podem bloquear o bot, os administradores de locatários podem bloquear o aplicativo e a Microsoft pode bloquear os bots de forma centralizada, se necessário.</span><span class="sxs-lookup"><span data-stu-id="c9807-175">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="c9807-176"><sup>1</sup> alguns bots apenas enviam mensagens (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="c9807-176"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="c9807-177">Eles são chamados de bots de "somente notificação", mas o termo não se refere ao que um bot é permitido ou não pode fazer, isso significa que o bot não quer expor uma experiência de conversa.</span><span class="sxs-lookup"><span data-stu-id="c9807-177">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="c9807-178">O Microsoft Teams usa esse campo para desativar a funcionalidade na interface do usuário que normalmente seria habilitada; o bot não está restrito sobre o que pode ser feito em comparação com os bots que expõem uma experiência de conversa.</span><span class="sxs-lookup"><span data-stu-id="c9807-178">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="c9807-179"><sup>2</sup> governada pela propriedade booleana supportsFiles no objeto bot no arquivo manifest. JSON do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c9807-179"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="c9807-180">Se um bot tem sua própria entrada, há um segundo: experiência de consentimento diferente na primeira vez que o usuário entra.</span><span class="sxs-lookup"><span data-stu-id="c9807-180">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="c9807-181">Atualmente, as permissões do Azure AD associadas a qualquer um dos recursos dentro de um aplicativo do Teams (bot, guia, conector ou extensão de mensagens) são completamente separadas das permissões do teams listadas aqui.</span><span class="sxs-lookup"><span data-stu-id="c9807-181">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="c9807-182">Guias</span><span class="sxs-lookup"><span data-stu-id="c9807-182">Tabs</span></span>

<span data-ttu-id="c9807-183">Uma guia é um site em execução dentro do teams.</span><span class="sxs-lookup"><span data-stu-id="c9807-183">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="c9807-184">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c9807-184">Required permissions</span></span>

<span data-ttu-id="c9807-185">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="c9807-185">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="c9807-186">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="c9807-186">Optional permissions</span></span>

<span data-ttu-id="c9807-187">Nenhum (atualmente)</span><span class="sxs-lookup"><span data-stu-id="c9807-187">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="c9807-188">Considerações</span><span class="sxs-lookup"><span data-stu-id="c9807-188">Considerations</span></span>

- <span data-ttu-id="c9807-189">O perfil de risco para uma guia é quase idêntico ao mesmo site em execução em uma guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="c9807-189">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="c9807-190">Uma guia também obtém o contexto no qual ele está em execução, incluindo o nome de entrada e o UPN do usuário atual, a ID de objeto do Azure AD para o usuário atual, a ID do grupo do Office 365 em que ele reside (se for uma equipe), a ID do locatário e a localidade atual do usuário.</span><span class="sxs-lookup"><span data-stu-id="c9807-190">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Office 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="c9807-191">No entanto, para mapear essas IDs para as informações de um usuário, a guia teria que fazer com que o usuário entre no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c9807-191">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="c9807-192">Conectores</span><span class="sxs-lookup"><span data-stu-id="c9807-192">Connectors</span></span>

<span data-ttu-id="c9807-193">Um conector publica mensagens em um canal quando ocorrem eventos em um sistema externo.</span><span class="sxs-lookup"><span data-stu-id="c9807-193">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="c9807-194">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c9807-194">Required permissions</span></span>

<span data-ttu-id="c9807-195">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="c9807-195">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="c9807-196">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="c9807-196">Optional permissions</span></span>

<span data-ttu-id="c9807-197">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="c9807-197">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="c9807-198">Certos conectores oferecem suporte a mensagens acionáveis, que permitem que os usuários publiquem respostas direcionadas para a mensagem do conector, por exemplo, adicionando uma resposta a um problema do GitHub ou adicionando uma data a um cartão Trello.</span><span class="sxs-lookup"><span data-stu-id="c9807-198">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="c9807-199">Considerações</span><span class="sxs-lookup"><span data-stu-id="c9807-199">Considerations</span></span>

- <span data-ttu-id="c9807-200">O sistema que lança mensagens do conector não sabe para quem está postando ou quem recebe as mensagens: nenhuma informação sobre o destinatário é divulgada.</span><span class="sxs-lookup"><span data-stu-id="c9807-200">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="c9807-201">(A Microsoft é o destinatário real, e não o locatário; A Microsoft faz a postagem real para o canal.)</span><span class="sxs-lookup"><span data-stu-id="c9807-201">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="c9807-202">Nenhum dado sai da rede corporativa quando as mensagens do conector são postadas em um canal.</span><span class="sxs-lookup"><span data-stu-id="c9807-202">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="c9807-203">Os conectores que dão suporte a mensagens acionáveis (permissão REPLYTO_CONNECTOR_MESSAGE) também não vêem o endereço IP e informações de referenciais; essas informações são enviadas à Microsoft e roteadas para pontos de extremidade HTTP que foram registrados anteriormente na Microsoft no portal de conectores.</span><span class="sxs-lookup"><span data-stu-id="c9807-203">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="c9807-204">Cada vez que um conector é configurado para um canal, uma URL exclusiva para essa instância do conector é criada.</span><span class="sxs-lookup"><span data-stu-id="c9807-204">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="c9807-205">Se essa instância do conector for excluída, a URL não poderá mais ser usada.</span><span class="sxs-lookup"><span data-stu-id="c9807-205">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="c9807-206">As mensagens de conector não podem conter anexos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c9807-206">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="c9807-207">A URL da instância do conector deve ser tratada como segredo/confidencial: qualquer pessoa que tenha essa URL pode postá-la, como um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="c9807-207">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="c9807-208">Portanto, há algum risco de spam ou links para sites de phishing ou malware.</span><span class="sxs-lookup"><span data-stu-id="c9807-208">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="c9807-209">Se isso fosse acontecer, os proprietários da equipe podem excluir a instância do conector.</span><span class="sxs-lookup"><span data-stu-id="c9807-209">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="c9807-210">Se o serviço que envia mensagens de conector fosse comprometido e começar a enviar spam/phishing/malware links, um administrador de locatário pode impedir que novas instâncias de conector sejam criadas e a Microsoft possa bloqueá-las de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="c9807-210">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="c9807-211">No momento, não é possível saber quais conectores suportam mensagens acionáveis (REPLYTO_CONNECTOR_MESSAGE permissão).</span><span class="sxs-lookup"><span data-stu-id="c9807-211">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="c9807-212">WebHooks de saída</span><span class="sxs-lookup"><span data-stu-id="c9807-212">Outgoing webhooks</span></span>

<span data-ttu-id="c9807-213">Os *WebHooks de saída* são criados instantaneamente por parte dos proprietários da equipe ou dos membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="c9807-213">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="c9807-214">Eles não são recursos de aplicativos Teams; essas informações estão incluídas para fins de integridade.</span><span class="sxs-lookup"><span data-stu-id="c9807-214">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="c9807-215">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c9807-215">Required permissions</span></span>

<span data-ttu-id="c9807-216">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="c9807-216">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="c9807-217">Pode receber mensagens de usuários e respondê-las.</span><span class="sxs-lookup"><span data-stu-id="c9807-217">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="c9807-218">Permissões opcionais</span><span class="sxs-lookup"><span data-stu-id="c9807-218">Optional permissions</span></span>

<span data-ttu-id="c9807-219">Nenhum</span><span class="sxs-lookup"><span data-stu-id="c9807-219">None</span></span>

### <a name="considerations"></a><span data-ttu-id="c9807-220">Considerações</span><span class="sxs-lookup"><span data-stu-id="c9807-220">Considerations</span></span>

- <span data-ttu-id="c9807-221">Os WebHooks de saída são semelhantes aos bots, mas têm menos privilégios.</span><span class="sxs-lookup"><span data-stu-id="c9807-221">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="c9807-222">Eles devem ser explicitamente mencionados, exatamente como os bots.</span><span class="sxs-lookup"><span data-stu-id="c9807-222">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="c9807-223">Quando um webhook de saída é registrado, um segredo é gerado, o que permite que o webhook de saída Verifique se o remetente é o Microsoft Teams em oposição a um invasor mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="c9807-223">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="c9807-224">Esse segredo deve permanecer como um segredo; qualquer pessoa que tenha acesso a ela pode representar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c9807-224">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="c9807-225">Se o segredo estiver comprometido, o webhook de saída pode ser excluído e recriado, e um novo segredo será gerado.</span><span class="sxs-lookup"><span data-stu-id="c9807-225">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="c9807-226">Embora seja possível criar um webhook de saída que não valide o segredo, recomendamos nele.</span><span class="sxs-lookup"><span data-stu-id="c9807-226">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="c9807-227">Além de receber e responder a mensagens, os WebHooks de saída não podem fazer muito: eles não podem enviar mensagens de forma proativa, eles não podem enviar ou receber arquivos, eles não podem fazer nada que os bots possam fazer, exceto receber e responder a mensagens.</span><span class="sxs-lookup"><span data-stu-id="c9807-227">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
