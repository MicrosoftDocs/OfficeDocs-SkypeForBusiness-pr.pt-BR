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
description: O administrador de TI pode configurar acesso externo para outros domínios (federação) permitir que os usuários desses domínios participar de equipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98dc47ec66861d2f0c77c0eff45851c09e8bc353
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33356184"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="49e95-103">Gerenciar o acesso externo (federação) no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49e95-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="49e95-104">Com o acesso externo de Teams da Microsoft, os usuários de outros domínios podem participar de sua bate-papos e chamadas.</span><span class="sxs-lookup"><span data-stu-id="49e95-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="49e95-105">Você também pode permitir que usuários externos que ainda estejam usando Skype para Business Online ou Skype para negócios prem participar.</span><span class="sxs-lookup"><span data-stu-id="49e95-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="49e95-106">Acesso externo (federação) e o acesso de convidado são diferentes:</span><span class="sxs-lookup"><span data-stu-id="49e95-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="49e95-107">Acesso de convidado concede permissão de acesso a um indivíduo.</span><span class="sxs-lookup"><span data-stu-id="49e95-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="49e95-108">Acesso externo concede permissão de acesso a um domínio inteiro.</span><span class="sxs-lookup"><span data-stu-id="49e95-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="49e95-109">Acesso de convidado, uma vez concedido por um proprietário de equipe, permite que um convidado para [acessar recursos](guest-experience.md), como discussões de canal e de arquivos, para uma equipe específico e bate-papo com outros usuários na equipe de que foram convidados para.</span><span class="sxs-lookup"><span data-stu-id="49e95-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="49e95-110">Com o acesso externo (federado bate-papo), os participantes externos chat não têm acesso para equipes ou os recursos da equipe da organização convidando.</span><span class="sxs-lookup"><span data-stu-id="49e95-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="49e95-111">Eles só podem participar de bate-papo federado individuais.</span><span class="sxs-lookup"><span data-stu-id="49e95-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="49e95-112">Administradores de Inquilino podem escolher entre as opções de dois comunicação, dependendo de qual nível de colaboração é desejável com o participante externo.</span><span class="sxs-lookup"><span data-stu-id="49e95-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="49e95-113">Os administradores podem escolher abordagens ou ambos, dependendo de suas necessidades organizacionais, mas recomendamos que permitindo o acesso de convidado para uma experiência mais completa de equipes colaborativo.</span><span class="sxs-lookup"><span data-stu-id="49e95-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="49e95-114">Consulte a tabela para obter uma comparação de externos e convidado para acessar os recursos a seguir.</span><span class="sxs-lookup"><span data-stu-id="49e95-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="49e95-115">Recurso</span><span class="sxs-lookup"><span data-stu-id="49e95-115">Feature</span></span> | <span data-ttu-id="49e95-116">Usuários de acesso externo</span><span class="sxs-lookup"><span data-stu-id="49e95-116">External access users</span></span> | <span data-ttu-id="49e95-117">Usuários de acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="49e95-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="49e95-118">Usuário puder conversar com alguém em outra empresa</span><span class="sxs-lookup"><span data-stu-id="49e95-118">User can chat with someone in another company</span></span> | <span data-ttu-id="49e95-119">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-119">Yes</span></span> |<span data-ttu-id="49e95-120">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-120">Yes</span></span> |
| <span data-ttu-id="49e95-121">Usuário pode chamar alguém em outra empresa</span><span class="sxs-lookup"><span data-stu-id="49e95-121">User can call someone in another company</span></span> | <span data-ttu-id="49e95-122">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-122">Yes</span></span> | <span data-ttu-id="49e95-123">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-123">Yes</span></span> |
| <span data-ttu-id="49e95-124">Usuário poderá ver se alguém de outra empresa está disponível para o bate-papo ou chamada</span><span class="sxs-lookup"><span data-stu-id="49e95-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="49e95-125">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-125">Yes</span></span> | <span data-ttu-id="49e95-126">Sim<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="49e95-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="49e95-127">Usuários podem pesquisar para usuários por meio de inquilinos externos</span><span class="sxs-lookup"><span data-stu-id="49e95-127">User can search for users across external tenants</span></span> | <span data-ttu-id="49e95-128">Sim<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="49e95-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="49e95-129">Não</span><span class="sxs-lookup"><span data-stu-id="49e95-129">No</span></span> |
| <span data-ttu-id="49e95-130">Usuário pode compartilhar arquivos</span><span class="sxs-lookup"><span data-stu-id="49e95-130">User can share files</span></span> | <span data-ttu-id="49e95-131">Não</span><span class="sxs-lookup"><span data-stu-id="49e95-131">No</span></span> | <span data-ttu-id="49e95-132">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-132">Yes</span></span> |
| <span data-ttu-id="49e95-133">Usuário pode acessar os recursos de equipes</span><span class="sxs-lookup"><span data-stu-id="49e95-133">User can access Teams resources</span></span> | <span data-ttu-id="49e95-134">Não</span><span class="sxs-lookup"><span data-stu-id="49e95-134">No</span></span> | <span data-ttu-id="49e95-135">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-135">Yes</span></span> |
| <span data-ttu-id="49e95-136">Usuário pode ser adicionado a um chat de grupo</span><span class="sxs-lookup"><span data-stu-id="49e95-136">User can be added to a group chat</span></span> | <span data-ttu-id="49e95-137">Não</span><span class="sxs-lookup"><span data-stu-id="49e95-137">No</span></span> | <span data-ttu-id="49e95-138">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-138">Yes</span></span> |
| <span data-ttu-id="49e95-139">Usuário pode ser adicionado a uma reunião</span><span class="sxs-lookup"><span data-stu-id="49e95-139">User can be added to a meeting</span></span> | <span data-ttu-id="49e95-140">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-140">Yes</span></span> | <span data-ttu-id="49e95-141">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-141">Yes</span></span> |
| <span data-ttu-id="49e95-142">Usuários adicionais podem ser adicionados a uma conversa com um usuário externo</span><span class="sxs-lookup"><span data-stu-id="49e95-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="49e95-143">Nenhum<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="49e95-143">No<sup>3</sup></span></span> | <span data-ttu-id="49e95-144">N/D</span><span class="sxs-lookup"><span data-stu-id="49e95-144">N/A</span></span> |
| <span data-ttu-id="49e95-145">Usuário é identificado como um participante externo</span><span class="sxs-lookup"><span data-stu-id="49e95-145">User is identified as an external party</span></span> | <span data-ttu-id="49e95-146">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-146">Yes</span></span> | <span data-ttu-id="49e95-147">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-147">Yes</span></span> |
| <span data-ttu-id="49e95-148">A presença é exibida</span><span class="sxs-lookup"><span data-stu-id="49e95-148">Presence is displayed</span></span> | <span data-ttu-id="49e95-149">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-149">Yes</span></span> | <span data-ttu-id="49e95-150">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-150">Yes</span></span> |
| <span data-ttu-id="49e95-151">Ausência temporária mensagem é mostrada</span><span class="sxs-lookup"><span data-stu-id="49e95-151">Out of office message is shown</span></span> | <span data-ttu-id="49e95-152">Não</span><span class="sxs-lookup"><span data-stu-id="49e95-152">No</span></span> | <span data-ttu-id="49e95-153">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-153">Yes</span></span> |
| <span data-ttu-id="49e95-154">Usuário individual poderão ser bloqueado.</span><span class="sxs-lookup"><span data-stu-id="49e95-154">Individual user can be blocked</span></span> | <span data-ttu-id="49e95-155">Não</span><span class="sxs-lookup"><span data-stu-id="49e95-155">No</span></span> | <span data-ttu-id="49e95-156">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-156">Yes</span></span> |
| <span data-ttu-id="49e95-157">@mentions são suportados</span><span class="sxs-lookup"><span data-stu-id="49e95-157">@mentions are supported</span></span> | <span data-ttu-id="49e95-158">Não</span><span class="sxs-lookup"><span data-stu-id="49e95-158">No</span></span> | <span data-ttu-id="49e95-159">Sim</span><span class="sxs-lookup"><span data-stu-id="49e95-159">Yes</span></span> |
||||

<span data-ttu-id="49e95-160"><sup>1</sup> fornecida que o usuário foi adicionado como um convidado e tiver entrado no como convidado para o inquilino de convidado.</span><span class="sxs-lookup"><span data-stu-id="49e95-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="49e95-161"><sup>2</sup> somente por email ou endereço de protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="49e95-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="49e95-162"><sup>3</sup> bate-papo (federado) externo é 1:1 somente.</span><span class="sxs-lookup"><span data-stu-id="49e95-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="49e95-163">Ativar ou desativar o acesso externo (os usuários podem se comunicar com Skype para usuários empresariais e equipes)</span><span class="sxs-lookup"><span data-stu-id="49e95-163">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="49e95-164">Você pode usar o & Teams Microsoft Skype para centro de administração de negócios para gerenciar o acesso externo.</span><span class="sxs-lookup"><span data-stu-id="49e95-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="49e95-165">Na & Teams Microsoft Skype para Business Admin Center, selecione **configurações de toda a organização** > **acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="49e95-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Captura de tela de acesso externo de configurações de toda a organização](media/manage-external-access-1.png)<span data-ttu-id="49e95-167">.</span><span class="sxs-lookup"><span data-stu-id="49e95-167"></span></span>

2. <span data-ttu-id="49e95-168">Alterne a chave **usuários podem se comunicar com Skype para usuários empresariais e equipes** para **ativada** ou **desativada**.</span><span class="sxs-lookup"><span data-stu-id="49e95-168">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![Captura de tela da opção de acesso externo ativada](media/manage-external-access-2.png)<span data-ttu-id="49e95-170">.</span><span class="sxs-lookup"><span data-stu-id="49e95-170"></span></span>

3. <span data-ttu-id="49e95-171">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="49e95-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="49e95-172">Adicionar ou bloquear um domínio</span><span class="sxs-lookup"><span data-stu-id="49e95-172">Add or block a domain</span></span>

<span data-ttu-id="49e95-173">Siga estas etapas para adicionar um domínio ou desativar o acesso externo para um domínio.</span><span class="sxs-lookup"><span data-stu-id="49e95-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="49e95-174">Na & Teams Microsoft Skype para Business Admin Center, selecione **configurações de toda a organização** > **acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="49e95-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="49e95-175">Selecione **Adicionar um domínio**.</span><span class="sxs-lookup"><span data-stu-id="49e95-175">Select **Add a domain**.</span></span> 
 
    ![Página de acesso a captura de tela do externo com adicionar um link de domínio](media/manage-external-access-3.png)<span data-ttu-id="49e95-177">.</span><span class="sxs-lookup"><span data-stu-id="49e95-177"></span></span>

   <span data-ttu-id="49e95-178">O painel de **Adicionar um domínio** aparece.</span><span class="sxs-lookup"><span data-stu-id="49e95-178">The **Add a domain** pane appears.</span></span>

    ![Captura de tela de adicionar um painel de domínio](media/manage-external-access-4.png)<span data-ttu-id="49e95-180">.</span><span class="sxs-lookup"><span data-stu-id="49e95-180"></span></span>


3. <span data-ttu-id="49e95-181">Em **Adicionar um domínio**, digite o nome do domínio; Por exemplo, digite Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="49e95-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="49e95-182">Selecione **Permitido** ou **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="49e95-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="49e95-183">Você pode alterar essa configuração a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="49e95-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="49e95-184">Selecione **concluído**.</span><span class="sxs-lookup"><span data-stu-id="49e95-184">Select **Done**.</span></span>

<span data-ttu-id="49e95-185">Depois de adicionar um domínio, você verá o nome de domínio e o status adicionado à lista de domínios na página de acesso externo.</span><span class="sxs-lookup"><span data-stu-id="49e95-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="49e95-186">Mais informações</span><span class="sxs-lookup"><span data-stu-id="49e95-186">More information</span></span>

<span data-ttu-id="49e95-187">Para obter informações sobre o acesso de convidado no Teams da Microsoft, consulte [Gerenciar o acesso de convidado em equipes da Microsoft](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="49e95-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
