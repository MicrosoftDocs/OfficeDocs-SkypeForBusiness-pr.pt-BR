---
title: Gerenciar o acesso externo (federação) no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Seu administrador de ti pode configurar o acesso externo para outros domínios (Federação) para permitir que os usuários desses domínios participem da equipe.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702716"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="16562-103">Gerenciar o acesso externo (federação) no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16562-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="16562-104">Com o acesso externo ao Microsoft Teams, os usuários de outros domínios podem participar de chats e chamadas.</span><span class="sxs-lookup"><span data-stu-id="16562-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="16562-105">Você também pode permitir que usuários externos que ainda estejam usando o Skype for Business online ou o Skype for Business no local para participar.</span><span class="sxs-lookup"><span data-stu-id="16562-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="16562-106">O acesso externo (Federação) e o acesso de convidado são diferentes:</span><span class="sxs-lookup"><span data-stu-id="16562-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="16562-107">O acesso de convidado concede permissão de acesso a um indivíduo.</span><span class="sxs-lookup"><span data-stu-id="16562-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="16562-108">O acesso externo oferece permissão de acesso a um domínio inteiro.</span><span class="sxs-lookup"><span data-stu-id="16562-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="16562-109">O acesso de convidado, uma vez concedido por um proprietário de equipe, permite que um convidado [acesse recursos](guest-experience.md), como discussões e arquivos de canal, para uma equipe específica e converse com outros usuários na equipe em que foram convidados.</span><span class="sxs-lookup"><span data-stu-id="16562-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="16562-110">Com o acesso externo (chat federado), os participantes do chat externo não têm acesso às equipes ou aos recursos da equipe que convida a organização.</span><span class="sxs-lookup"><span data-stu-id="16562-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="16562-111">Eles podem participar apenas de um chat federado único.</span><span class="sxs-lookup"><span data-stu-id="16562-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="16562-112">Os administradores de locatários podem escolher entre as duas opções de comunicação, dependendo do nível de colaboração que é desejável na parte externa.</span><span class="sxs-lookup"><span data-stu-id="16562-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="16562-113">Os administradores podem escolher abordagens ou ambos, dependendo de suas necessidades organizacionais, mas recomendamos habilitar o acesso de convidado para obter uma experiência de equipes mais abrangente e colaborativa.</span><span class="sxs-lookup"><span data-stu-id="16562-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="16562-114">Consulte a tabela a seguir para obter uma comparação de recursos de acesso externo e de convidado.</span><span class="sxs-lookup"><span data-stu-id="16562-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="16562-115">Recurso</span><span class="sxs-lookup"><span data-stu-id="16562-115">Feature</span></span> | <span data-ttu-id="16562-116">Usuários de acesso externo</span><span class="sxs-lookup"><span data-stu-id="16562-116">External access users</span></span> | <span data-ttu-id="16562-117">Usuários de acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="16562-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="16562-118">O usuário pode conversar com alguém em outra empresa</span><span class="sxs-lookup"><span data-stu-id="16562-118">User can chat with someone in another company</span></span> | <span data-ttu-id="16562-119">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-119">Yes</span></span> |<span data-ttu-id="16562-120">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-120">Yes</span></span> |
| <span data-ttu-id="16562-121">O usuário pode fazer uma chamada para alguém em outra empresa</span><span class="sxs-lookup"><span data-stu-id="16562-121">User can call someone in another company</span></span> | <span data-ttu-id="16562-122">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-122">Yes</span></span> | <span data-ttu-id="16562-123">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-123">Yes</span></span> |
| <span data-ttu-id="16562-124">O usuário pode ver se alguém de outra empresa está disponível para chamada ou chat</span><span class="sxs-lookup"><span data-stu-id="16562-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="16562-125">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-125">Yes</span></span> | <span data-ttu-id="16562-126">Sim<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="16562-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="16562-127">O usuário pode pesquisar usuários em locatários externos</span><span class="sxs-lookup"><span data-stu-id="16562-127">User can search for users across external tenants</span></span> | <span data-ttu-id="16562-128">Sim<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="16562-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="16562-129">Não</span><span class="sxs-lookup"><span data-stu-id="16562-129">No</span></span> |
| <span data-ttu-id="16562-130">O usuário pode compartilhar arquivos</span><span class="sxs-lookup"><span data-stu-id="16562-130">User can share files</span></span> | <span data-ttu-id="16562-131">Não</span><span class="sxs-lookup"><span data-stu-id="16562-131">No</span></span> | <span data-ttu-id="16562-132">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-132">Yes</span></span> |
| <span data-ttu-id="16562-133">O usuário pode acessar os recursos da equipe</span><span class="sxs-lookup"><span data-stu-id="16562-133">User can access Teams resources</span></span> | <span data-ttu-id="16562-134">Não</span><span class="sxs-lookup"><span data-stu-id="16562-134">No</span></span> | <span data-ttu-id="16562-135">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-135">Yes</span></span> |
| <span data-ttu-id="16562-136">O usuário pode ser adicionado a um chat em grupo</span><span class="sxs-lookup"><span data-stu-id="16562-136">User can be added to a group chat</span></span> | <span data-ttu-id="16562-137">Não</span><span class="sxs-lookup"><span data-stu-id="16562-137">No</span></span> | <span data-ttu-id="16562-138">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-138">Yes</span></span> |
| <span data-ttu-id="16562-139">O usuário pode ser adicionado a uma reunião</span><span class="sxs-lookup"><span data-stu-id="16562-139">User can be added to a meeting</span></span> | <span data-ttu-id="16562-140">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-140">Yes</span></span> | <span data-ttu-id="16562-141">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-141">Yes</span></span> |
| <span data-ttu-id="16562-142">Outros usuários podem ser adicionados a um chat com um usuário externo</span><span class="sxs-lookup"><span data-stu-id="16562-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="16562-143">Não<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="16562-143">No<sup>3</sup></span></span> | <span data-ttu-id="16562-144">N/D</span><span class="sxs-lookup"><span data-stu-id="16562-144">N/A</span></span> |
| <span data-ttu-id="16562-145">O usuário é identificado como uma festa externa</span><span class="sxs-lookup"><span data-stu-id="16562-145">User is identified as an external party</span></span> | <span data-ttu-id="16562-146">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-146">Yes</span></span> | <span data-ttu-id="16562-147">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-147">Yes</span></span> |
| <span data-ttu-id="16562-148">A presença será exibida</span><span class="sxs-lookup"><span data-stu-id="16562-148">Presence is displayed</span></span> | <span data-ttu-id="16562-149">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-149">Yes</span></span> | <span data-ttu-id="16562-150">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-150">Yes</span></span> |
| <span data-ttu-id="16562-151">Mensagem de ausência temporária é mostrada</span><span class="sxs-lookup"><span data-stu-id="16562-151">Out of office message is shown</span></span> | <span data-ttu-id="16562-152">Não</span><span class="sxs-lookup"><span data-stu-id="16562-152">No</span></span> | <span data-ttu-id="16562-153">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-153">Yes</span></span> |
| <span data-ttu-id="16562-154">O usuário individual pode ser bloqueado</span><span class="sxs-lookup"><span data-stu-id="16562-154">Individual user can be blocked</span></span> | <span data-ttu-id="16562-155">Não</span><span class="sxs-lookup"><span data-stu-id="16562-155">No</span></span> | <span data-ttu-id="16562-156">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-156">Yes</span></span> |
| <span data-ttu-id="16562-157">@mentions têm suporte</span><span class="sxs-lookup"><span data-stu-id="16562-157">@mentions are supported</span></span> | <span data-ttu-id="16562-158">Não</span><span class="sxs-lookup"><span data-stu-id="16562-158">No</span></span> | <span data-ttu-id="16562-159">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-159">Yes</span></span> |
| <span data-ttu-id="16562-160">Fazer chamadas privadas</span><span class="sxs-lookup"><span data-stu-id="16562-160">Make Private Calls</span></span> | <span data-ttu-id="16562-161">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-161">Yes</span></span> | <span data-ttu-id="16562-162">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-162">Yes</span></span> |
| <span data-ttu-id="16562-163">Permitir vídeo IP</span><span class="sxs-lookup"><span data-stu-id="16562-163">Allow IP Video</span></span> | <span data-ttu-id="16562-164">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-164">Yes</span></span> | <span data-ttu-id="16562-165">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-165">Yes</span></span> |
| <span data-ttu-id="16562-166">Modo de compartilhamento de tela</span><span class="sxs-lookup"><span data-stu-id="16562-166">Screen Sharing Mode</span></span> | <span data-ttu-id="16562-167">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-167">Yes</span></span> | <span data-ttu-id="16562-168">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-168">Yes</span></span> |
| <span data-ttu-id="16562-169">Permitir reunião agora</span><span class="sxs-lookup"><span data-stu-id="16562-169">Allow Meet Now</span></span> | <span data-ttu-id="16562-170">Não</span><span class="sxs-lookup"><span data-stu-id="16562-170">No</span></span> | <span data-ttu-id="16562-171">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-171">Yes</span></span> |
| <span data-ttu-id="16562-172">Editar mensagens enviadas</span><span class="sxs-lookup"><span data-stu-id="16562-172">Edit Sent Messages</span></span> | <span data-ttu-id="16562-173">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-173">Yes</span></span> | <span data-ttu-id="16562-174">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-174">Yes</span></span> |
| <span data-ttu-id="16562-175">Pode excluir mensagens enviadas</span><span class="sxs-lookup"><span data-stu-id="16562-175">Can Delete Sent Messages</span></span> | <span data-ttu-id="16562-176">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-176">Yes</span></span> | <span data-ttu-id="16562-177">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-177">Yes</span></span> |
| <span data-ttu-id="16562-178">Usar o Giphy em conversa</span><span class="sxs-lookup"><span data-stu-id="16562-178">Use Giphy In Conversation</span></span> | <span data-ttu-id="16562-179">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-179">Yes</span></span> | <span data-ttu-id="16562-180">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-180">Yes</span></span> |
| <span data-ttu-id="16562-181">Usar o memes em conversa</span><span class="sxs-lookup"><span data-stu-id="16562-181">Use Memes In Conversation</span></span> | <span data-ttu-id="16562-182">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-182">Yes</span></span> | <span data-ttu-id="16562-183">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-183">Yes</span></span> |
| <span data-ttu-id="16562-184">Usar adesivos em conversa</span><span class="sxs-lookup"><span data-stu-id="16562-184">Use Stickers In Conversation</span></span> | <span data-ttu-id="16562-185">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-185">Yes</span></span> | <span data-ttu-id="16562-186">Sim</span><span class="sxs-lookup"><span data-stu-id="16562-186">Yes</span></span> |
||||

<span data-ttu-id="16562-187"><sup>1</sup> desde que o usuário tenha sido adicionado como um convidado e esteja conectado como convidado ao locatário de convidado.</span><span class="sxs-lookup"><span data-stu-id="16562-187"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="16562-188"><sup>2</sup> somente por endereço de email ou protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="16562-188"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="16562-189"><sup>3</sup> o chat externo (federado) só é o 1:1.</span><span class="sxs-lookup"><span data-stu-id="16562-189"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

> [!NOTE]
> <span data-ttu-id="16562-190">Para obter mais informações sobre os recursos convidados e sobre a experiência de convidado, consulte [Ativar ou desativar o acesso de convidado ao Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) e o [que a experiência de convidado é curtir](https://docs.microsoft.com/microsoftteams/guest-experience).</span><span class="sxs-lookup"><span data-stu-id="16562-190">For more information on guest features and the guest experience, see [Turn on or off guest access to Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) and [What the guest experience is like](https://docs.microsoft.com/microsoftteams/guest-experience).</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="16562-191">Ativar ou desativar o acesso externo (os usuários podem se comunicar com os usuários do Skype for Business e do Teams)</span><span class="sxs-lookup"><span data-stu-id="16562-191">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="16562-192">Você pode usar o centro de administração do Microsoft Teams & o Skype for Business para gerenciar o acesso externo.</span><span class="sxs-lookup"><span data-stu-id="16562-192">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="16562-193">No centro de administração do Microsoft Teams & o centro de administração do Skype for Business, selecione >  **configurações de toda a organização\*\*\*\*acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="16562-193">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Captura de tela de acesso externo às configurações de toda a organização](media/manage-external-access-1.png)<span data-ttu-id="16562-195">.</span><span class="sxs-lookup"><span data-stu-id="16562-195"></span></span>

2. <span data-ttu-id="16562-196">Alternar os **usuários podem se comunicar com o Skype for Business e os usuários** do teams alternar para **ativado** ou **desativado**.</span><span class="sxs-lookup"><span data-stu-id="16562-196">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![Captura de tela da opção de acesso externo ativada](media/manage-external-access-2.png)<span data-ttu-id="16562-198">.</span><span class="sxs-lookup"><span data-stu-id="16562-198"></span></span>

3. <span data-ttu-id="16562-199">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="16562-199">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="16562-200">Adicionar ou bloquear um domínio</span><span class="sxs-lookup"><span data-stu-id="16562-200">Add or block a domain</span></span>

<span data-ttu-id="16562-201">Siga estas etapas para adicionar um domínio ou desativar o acesso externo para um domínio.</span><span class="sxs-lookup"><span data-stu-id="16562-201">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="16562-202">No centro de administração do Microsoft Teams & o centro de administração do Skype for Business, selecione >  **configurações de toda a organização\*\*\*\*acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="16562-202">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="16562-203">Selecione **Adicionar um domínio**.</span><span class="sxs-lookup"><span data-stu-id="16562-203">Select **Add a domain**.</span></span> 
 
    ![Captura de tela da página de acesso externo com o link adicionar um domínio](media/manage-external-access-3.png)<span data-ttu-id="16562-205">.</span><span class="sxs-lookup"><span data-stu-id="16562-205"></span></span>

   <span data-ttu-id="16562-206">O painel **Adicionar um domínio** é exibido.</span><span class="sxs-lookup"><span data-stu-id="16562-206">The **Add a domain** pane appears.</span></span>

    ![Captura de tela do painel Adicionar um domínio](media/manage-external-access-4.png)<span data-ttu-id="16562-208">.</span><span class="sxs-lookup"><span data-stu-id="16562-208"></span></span>


3. <span data-ttu-id="16562-209">Em **Adicionar um domínio**, digite o nome do domínio; por exemplo, digite Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="16562-209">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="16562-210">Selecione **Permitido** ou **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="16562-210">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="16562-211">Você pode alterar essa configuração a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="16562-211">You can change this setting at any time.</span></span>

2. <span data-ttu-id="16562-212">Selecione **concluído**.</span><span class="sxs-lookup"><span data-stu-id="16562-212">Select **Done**.</span></span>

<span data-ttu-id="16562-213">Depois de adicionar um domínio, você verá o nome de domínio e o status adicionados à lista de domínios na página de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="16562-213">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="16562-214">Mais informações</span><span class="sxs-lookup"><span data-stu-id="16562-214">More information</span></span>

<span data-ttu-id="16562-215">Para obter informações sobre o acesso de convidado no Microsoft Teams, consulte [gerenciar o acesso de convidados no Microsoft Teams](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="16562-215">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
