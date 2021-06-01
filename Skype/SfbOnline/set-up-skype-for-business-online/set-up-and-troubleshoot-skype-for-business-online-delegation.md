---
title: Configurar e solucionar problemas de delegação do Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Este artigo explica como configurar e solucionar problemas Skype for Business delegação Online. Este artigo fornece orientações sobre recomendações de instalação, práticas recomendadas e etapas de solução de problemas.
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239820"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="88f20-104">Configurar e solucionar problemas de delegação do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="88f20-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="88f20-105">Este artigo explica como configurar e solucionar problemas Skype for Business delegação Online.</span><span class="sxs-lookup"><span data-stu-id="88f20-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="88f20-106">Este artigo fornece orientações sobre recomendações de instalação, práticas recomendadas e etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="88f20-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="88f20-107">Diretrizes e requisitos</span><span class="sxs-lookup"><span data-stu-id="88f20-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="88f20-108">Diretrizes para delegação</span><span class="sxs-lookup"><span data-stu-id="88f20-108">Guidelines for delegation</span></span>

<span data-ttu-id="88f20-109">Configurar e fazer com que a delegação funcione corretamente depende de você seguir estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="88f20-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="88f20-110">Você deve estar usando o cliente Skype for Business 2015 completo com as atualizações mais recentes ou o cliente Skype for Business 2016 completo.</span><span class="sxs-lookup"><span data-stu-id="88f20-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="88f20-111">Você deve estar usando o cliente Outlook 2013 com as atualizações mais recentes ou o Outlook 2016 cliente.</span><span class="sxs-lookup"><span data-stu-id="88f20-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="88f20-112">Certifique-se de que o delegador e os computadores delegados tenham um Outlook de email que seja o principal ou o perfil padrão.</span><span class="sxs-lookup"><span data-stu-id="88f20-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="88f20-113">Esse perfil de email deve conter apenas uma conta.</span><span class="sxs-lookup"><span data-stu-id="88f20-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="88f20-114">Skype for Business o representante e o representante devem ser usuários online.</span><span class="sxs-lookup"><span data-stu-id="88f20-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="88f20-115">Além disso, Exchange Server caixas de correio de cada conta devem estar online ou ambas no local.</span><span class="sxs-lookup"><span data-stu-id="88f20-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="88f20-116">Tanto o representante quanto o representante devem estar usando a mesma versão principal do Outlook.</span><span class="sxs-lookup"><span data-stu-id="88f20-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="88f20-117">O **valor do atributo EnableExchangeDelegateSync** deve ser definido como **true** na política do cliente.</span><span class="sxs-lookup"><span data-stu-id="88f20-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="88f20-118">Você pode verificar essa configuração executando o cmdlet **Get-CSClientPolicy** no módulo Skype for Business PowerShell Online.</span><span class="sxs-lookup"><span data-stu-id="88f20-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="88f20-119">O representante e o representante devem estar Skype for Business e Outlook ao mesmo tempo em estações de trabalho diferentes.</span><span class="sxs-lookup"><span data-stu-id="88f20-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="88f20-120">Não há suporte para caixas de correio compartilhadas para a delegação Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="88f20-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="88f20-121">Isso porque a caixa de correio compartilhada não tem a lista de controle de acesso (ACL) **de sendonbehalf.**</span><span class="sxs-lookup"><span data-stu-id="88f20-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="88f20-122">Skype for Business versão do cliente</span><span class="sxs-lookup"><span data-stu-id="88f20-122">Skype for Business client version support</span></span>

||<span data-ttu-id="88f20-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="88f20-123">**Outlook 2013**</span></span>|<span data-ttu-id="88f20-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="88f20-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88f20-125">**Lync/Skype for Business Cliente Básico**</span><span class="sxs-lookup"><span data-stu-id="88f20-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="88f20-126">Incompatível</span><span class="sxs-lookup"><span data-stu-id="88f20-126">Not supported</span></span> |<span data-ttu-id="88f20-127">Incompatível</span><span class="sxs-lookup"><span data-stu-id="88f20-127">Not supported</span></span>
|<span data-ttu-id="88f20-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="88f20-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="88f20-129">Compatível </span><span class="sxs-lookup"><span data-stu-id="88f20-129">Supported</span></span>| <span data-ttu-id="88f20-130">Compatível</span><span class="sxs-lookup"><span data-stu-id="88f20-130">Supported</span></span>|
|<span data-ttu-id="88f20-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="88f20-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="88f20-132">Compatível </span><span class="sxs-lookup"><span data-stu-id="88f20-132">Supported</span></span>| <span data-ttu-id="88f20-133">Compatível</span><span class="sxs-lookup"><span data-stu-id="88f20-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="88f20-134">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="88f20-134">Licensing requirements</span></span>

<span data-ttu-id="88f20-135">**Enterprise Cenário de licenciamento do E3**</span><span class="sxs-lookup"><span data-stu-id="88f20-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="88f20-136">**Licença**</span><span class="sxs-lookup"><span data-stu-id="88f20-136">**License**</span></span>|<span data-ttu-id="88f20-137">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="88f20-137">**Clients**</span></span>|<span data-ttu-id="88f20-138">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="88f20-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88f20-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="88f20-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="88f20-140">Lync 2013 (Skype for Business 2015) usado com Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f20-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="88f20-141">Skype for Business 2016 usado com Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f20-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="88f20-142">Skype for Business O cliente básico não dá suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="88f20-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="88f20-143">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="88f20-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="88f20-144">Enterprise E3 com Sistema de Telefonia Office 365 + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="88f20-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="88f20-145">Lync 2013 (Skype for Business 2015) usado com Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f20-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="88f20-146">Skype for Business 2016 usado com Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f20-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="88f20-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="88f20-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="88f20-148">Skype for Business O cliente básico não dá suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="88f20-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="88f20-149">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="88f20-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="88f20-150">**Enterprise Cenário de licenciamento do E5**</span><span class="sxs-lookup"><span data-stu-id="88f20-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="88f20-151">**Licença**</span><span class="sxs-lookup"><span data-stu-id="88f20-151">**License**</span></span>|<span data-ttu-id="88f20-152">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="88f20-152">**Clients**</span></span>|<span data-ttu-id="88f20-153">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="88f20-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88f20-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="88f20-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="88f20-155">Lync 2013 (Skype for Business 2015) usado com Outlook 2013 ou Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="88f20-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="88f20-156">Skype for Business 2016 usado com Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f20-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="88f20-157">Skype for Business O cliente básico não dá suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="88f20-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="88f20-158">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="88f20-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="88f20-159">Enterprise E5 mais Office 365 plano de chamada</span><span class="sxs-lookup"><span data-stu-id="88f20-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="88f20-160">Skype for Business para Mac 2016</span><span class="sxs-lookup"><span data-stu-id="88f20-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="88f20-161">Lync 2013 (Skype for Business 2015) usado com Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f20-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="88f20-162">Skype for Business 2016 usado com Outlook 2013 ou Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88f20-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="88f20-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="88f20-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="88f20-164">Skype for Business O cliente básico não dá suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="88f20-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="88f20-165">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="88f20-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="88f20-166">Configurar e verificar a delegação</span><span class="sxs-lookup"><span data-stu-id="88f20-166">Set up and verify delegation</span></span>

<span data-ttu-id="88f20-167">Para configurar a delegação Skype for Business Online, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="88f20-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="88f20-168">Para Windows clientes</span><span class="sxs-lookup"><span data-stu-id="88f20-168">For Windows clients</span></span>

 <span data-ttu-id="88f20-169">**Guia Encaminhamento de Chamada**</span><span class="sxs-lookup"><span data-stu-id="88f20-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="88f20-170">Selecione **Opções de**  >  **Ferramentas** De Encaminhamento de Chamada  >  **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="88f20-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="88f20-171">Selecione **Editar membros do meu representante**.</span><span class="sxs-lookup"><span data-stu-id="88f20-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="88f20-172">Selecione **Adicionar**, selecione o representante que você deseja adicionar e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="88f20-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="88f20-173">**Sem guia Encaminhamento de Chamada**</span><span class="sxs-lookup"><span data-stu-id="88f20-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="88f20-174">Em Outlook, selecione **File**  >  **Account Configurações** Delegate  >  **Access**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="88f20-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="88f20-175">Localize e adicione o nome da pessoa que será o representante.</span><span class="sxs-lookup"><span data-stu-id="88f20-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="88f20-176">Selecione o menu **Calendário** e selecione **Editor (pode ler, criar e modificar itens)**.</span><span class="sxs-lookup"><span data-stu-id="88f20-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="88f20-177">Para clientes Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="88f20-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="88f20-178">**Guia Encaminhamento de Chamada**</span><span class="sxs-lookup"><span data-stu-id="88f20-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="88f20-179">Se o cliente não  tiver uma guia Encaminhamento de Chamada que tenha o link **Editar** meus Membros delegados e o delegador estiver localizado em um computador Mac, o delegador deverá entrar em um computador baseado em Windows para configurar a delegação.</span><span class="sxs-lookup"><span data-stu-id="88f20-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="88f20-180">Isso porque os clientes Mac não podem fazer conexões MAPI, e isso é um requisito para estabelecer uma delegação Skype for Business de Outlook.</span><span class="sxs-lookup"><span data-stu-id="88f20-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="88f20-181">Verificar o sucesso</span><span class="sxs-lookup"><span data-stu-id="88f20-181">Verify success</span></span>

<span data-ttu-id="88f20-182">Se a configuração for bem-sucedida, o representante deverá ver a mensagem You were added as a delegate **for < Name>** message e também que o grupo Pessoas que Eu **Gerencie** Chamadas Para é criado.</span><span class="sxs-lookup"><span data-stu-id="88f20-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="88f20-183">O delegator deve ver que o grupo **Delegates** foi criado.</span><span class="sxs-lookup"><span data-stu-id="88f20-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88f20-184">As permissões de delegação geralmente aparecem dentro de 30 minutos do processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="88f20-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="88f20-185">No entanto, esse processo pode levar até 24 horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="88f20-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="88f20-186">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="88f20-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="88f20-187">Problemas comuns</span><span class="sxs-lookup"><span data-stu-id="88f20-187">Common issues</span></span>

- > <span data-ttu-id="88f20-188">**Problema 1** A entrada do representante continua a aparecer no grupo **Pessoas que Gerencio** Chamadas para Depois que o representante tiver removido o representante do cliente Outlook.</span><span class="sxs-lookup"><span data-stu-id="88f20-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="88f20-189">**Resolução 1** No cliente Skype for Business, clique com o botão direito do mouse no representante no grupo **Representantes** e selecione **Remover do Grupo**.</span><span class="sxs-lookup"><span data-stu-id="88f20-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="88f20-190">**Problema 2** Depois que o acesso de representante é concedido por meio do cliente Outlook, nem a mensagem de confirmação nem o grupo **People I Manage Calls For** são exibidos para o representante.</span><span class="sxs-lookup"><span data-stu-id="88f20-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="88f20-191">**Resolução 2** Remova a delegação do cliente Outlook, aguarde cerca de 15 minutos para replicação e adicione o representante novamente.</span><span class="sxs-lookup"><span data-stu-id="88f20-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="88f20-192">Outros problemas comuns</span><span class="sxs-lookup"><span data-stu-id="88f20-192">Other common issues</span></span>

- <span data-ttu-id="88f20-193">A delegação não funcionará se o limite de 25 delegadores e 25 representantes for excedido.</span><span class="sxs-lookup"><span data-stu-id="88f20-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="88f20-194">O Skype for Business cliente Basic não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="88f20-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="88f20-195">Se você instalar o cliente Skype for Business Basic, ele removerá e quebrará a delegação.</span><span class="sxs-lookup"><span data-stu-id="88f20-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="88f20-196">Se o **valor Status de MAPI** não estiver **OK,** certifique-se de que os valores **SIP** e **SMTP** corresponderão.</span><span class="sxs-lookup"><span data-stu-id="88f20-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="88f20-197">Pode levar vários minutos para que o status MAPI seja exibido como **OK** depois que você começar a Skype for Business e Outlook.</span><span class="sxs-lookup"><span data-stu-id="88f20-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="88f20-198">Não há suporte para a criação de um grupo de segurança e a adição de permissões de delegação para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="88f20-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="88f20-199">MAPI não está disponível.</span><span class="sxs-lookup"><span data-stu-id="88f20-199">MAPI is unavailable.</span></span> <span data-ttu-id="88f20-200">Consulte ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="88f20-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="88f20-201">A Exchange Online caixa de correio não está acessível por meio do cliente Skype for Business cliente.</span><span class="sxs-lookup"><span data-stu-id="88f20-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="88f20-202">Se isso ocorrer, execute o teste [de Outlook conectividade](https://testconnectivity.microsoft.com/) para garantir que ele passe.</span><span class="sxs-lookup"><span data-stu-id="88f20-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="88f20-203">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="88f20-203">Related topics</span></span>
[<span data-ttu-id="88f20-204">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="88f20-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="88f20-205">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="88f20-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
