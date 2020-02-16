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
description: Este artigo explica como configurar e solucionar problemas de delegação do Skype for Business online. Este artigo fornece orientações sobre recomendações de configuração, práticas recomendadas e etapas de solução de problemas.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010794"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="4d95c-104">Configurar e solucionar problemas de delegação do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4d95c-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="4d95c-105">Este artigo explica como configurar e solucionar problemas de delegação do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4d95c-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="4d95c-106">Este artigo fornece orientações sobre recomendações de configuração, práticas recomendadas e etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="4d95c-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="4d95c-107">Diretrizes e requisitos</span><span class="sxs-lookup"><span data-stu-id="4d95c-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="4d95c-108">Diretrizes de delegação</span><span class="sxs-lookup"><span data-stu-id="4d95c-108">Guidelines for delegation</span></span>

<span data-ttu-id="4d95c-109">Configurar e obter a delegação para funcionar corretamente depende das seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="4d95c-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="4d95c-110">Você deve estar usando o cliente completo do Skype for Business 2015 com as atualizações mais recentes ou o Skype for Business 2016 Full Client.</span><span class="sxs-lookup"><span data-stu-id="4d95c-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="4d95c-111">Você deve usar o cliente Outlook 2013 com as atualizações mais recentes ou o cliente do Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="4d95c-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="4d95c-112">Verifique se o delegador e os computadores delegados têm um perfil de email do Outlook que é o perfil principal ou padrão.</span><span class="sxs-lookup"><span data-stu-id="4d95c-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="4d95c-113">Esse perfil de email deve conter apenas uma conta.</span><span class="sxs-lookup"><span data-stu-id="4d95c-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="4d95c-114">O Skype for Business para o delegante e o representante devem ser usuários online.</span><span class="sxs-lookup"><span data-stu-id="4d95c-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="4d95c-115">Além disso, as caixas de correio do Exchange Server para cada conta devem estar online ou ambas estar locais.</span><span class="sxs-lookup"><span data-stu-id="4d95c-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="4d95c-116">O delegante e o representante devem usar a mesma versão principal do Outlook.</span><span class="sxs-lookup"><span data-stu-id="4d95c-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="4d95c-117">O valor do atributo **EnableExchangeDelegateSync** deve ser definido como **true** na política do cliente.</span><span class="sxs-lookup"><span data-stu-id="4d95c-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="4d95c-118">Você pode verificar essa configuração executando o cmdlet **Get-CSClientPolicy** no módulo do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4d95c-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="4d95c-119">Tanto o delegante quanto o representante devem estar conectados ao Skype for Business e ao Outlook ao mesmo tempo em diferentes estações de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4d95c-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="4d95c-120">Caixas de correio compartilhadas não são compatíveis com a delegação do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4d95c-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="4d95c-121">Isso ocorre porque a caixa de correio compartilhada não tem a ACL (lista de controle de acesso) do **SendOnBehalf** .</span><span class="sxs-lookup"><span data-stu-id="4d95c-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="4d95c-122">Suporte de versão do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4d95c-122">Skype for Business client version support</span></span>

||<span data-ttu-id="4d95c-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="4d95c-123">**Outlook 2013**</span></span>|<span data-ttu-id="4d95c-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="4d95c-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d95c-125">**Cliente Lync/Skype for Business Basic**</span><span class="sxs-lookup"><span data-stu-id="4d95c-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="4d95c-126">Incompatível</span><span class="sxs-lookup"><span data-stu-id="4d95c-126">Not supported</span></span> |<span data-ttu-id="4d95c-127">Incompatível</span><span class="sxs-lookup"><span data-stu-id="4d95c-127">Not supported</span></span>
|<span data-ttu-id="4d95c-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="4d95c-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="4d95c-129">Compatível </span><span class="sxs-lookup"><span data-stu-id="4d95c-129">Supported</span></span>| <span data-ttu-id="4d95c-130">Compatível</span><span class="sxs-lookup"><span data-stu-id="4d95c-130">Supported</span></span>|
|<span data-ttu-id="4d95c-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="4d95c-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="4d95c-132">Compatível </span><span class="sxs-lookup"><span data-stu-id="4d95c-132">Supported</span></span>| <span data-ttu-id="4d95c-133">Compatível</span><span class="sxs-lookup"><span data-stu-id="4d95c-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="4d95c-134">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="4d95c-134">Licensing requirements</span></span>

<span data-ttu-id="4d95c-135">**Cenário de licenciamento Enterprise E3**</span><span class="sxs-lookup"><span data-stu-id="4d95c-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="4d95c-136">**Licença**</span><span class="sxs-lookup"><span data-stu-id="4d95c-136">**License**</span></span>|<span data-ttu-id="4d95c-137">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="4d95c-137">**Clients**</span></span>|<span data-ttu-id="4d95c-138">**Observações**</span><span class="sxs-lookup"><span data-stu-id="4d95c-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d95c-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="4d95c-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="4d95c-140">Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d95c-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4d95c-141">Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d95c-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="4d95c-142">O cliente Skype for Business Basic não oferece suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="4d95c-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4d95c-143">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="4d95c-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="4d95c-144">Enterprise E3 com o sistema telefônico do Office 365 + plano do xCalling do Office 365</span><span class="sxs-lookup"><span data-stu-id="4d95c-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="4d95c-145">Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d95c-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4d95c-146">Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d95c-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4d95c-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="4d95c-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="4d95c-148">O cliente Skype for Business Basic não oferece suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="4d95c-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4d95c-149">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="4d95c-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="4d95c-150">**Cenário de licenciamento Enterprise e5**</span><span class="sxs-lookup"><span data-stu-id="4d95c-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="4d95c-151">**Licença**</span><span class="sxs-lookup"><span data-stu-id="4d95c-151">**License**</span></span>|<span data-ttu-id="4d95c-152">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="4d95c-152">**Clients**</span></span>|<span data-ttu-id="4d95c-153">**Observações**</span><span class="sxs-lookup"><span data-stu-id="4d95c-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d95c-154">Enterprise e5</span><span class="sxs-lookup"><span data-stu-id="4d95c-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="4d95c-155">Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="4d95c-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="4d95c-156">Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d95c-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="4d95c-157">O cliente Skype for Business Basic não oferece suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="4d95c-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4d95c-158">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="4d95c-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="4d95c-159">Enterprise E5 mais o plano de chamadas do Office 365</span><span class="sxs-lookup"><span data-stu-id="4d95c-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="4d95c-160">Skype for Business para Mac 2016</span><span class="sxs-lookup"><span data-stu-id="4d95c-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="4d95c-161">Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d95c-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4d95c-162">Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d95c-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="4d95c-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="4d95c-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="4d95c-164">O cliente Skype for Business Basic não oferece suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="4d95c-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="4d95c-165">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="4d95c-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="4d95c-166">Configurar e verificar a delegação</span><span class="sxs-lookup"><span data-stu-id="4d95c-166">Set up and verify delegation</span></span>

<span data-ttu-id="4d95c-167">Para configurar a delegação do Skype for Business Online, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="4d95c-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="4d95c-168">Para clientes Windows</span><span class="sxs-lookup"><span data-stu-id="4d95c-168">For Windows clients</span></span>

 <span data-ttu-id="4d95c-169">**Guia encaminhamento de chamadas**</span><span class="sxs-lookup"><span data-stu-id="4d95c-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="4d95c-170">Selecione **ferramentas** > **Opções** > **configurações de encaminhamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="4d95c-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="4d95c-171">Selecione **Editar membros de meus representantes**.</span><span class="sxs-lookup"><span data-stu-id="4d95c-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="4d95c-172">Selecione **Adicionar**, selecione o representante que você deseja adicionar e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d95c-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="4d95c-173">**Sem guia encaminhamento de chamadas**</span><span class="sxs-lookup"><span data-stu-id="4d95c-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="4d95c-174">No Outlook, selecione \*\*\*\* > **configurações** > de conta de arquivo**Adicionar\*\*\*\*acesso** > ao representante.</span><span class="sxs-lookup"><span data-stu-id="4d95c-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="4d95c-175">Localize e adicione o nome da pessoa que vai ser o representante.</span><span class="sxs-lookup"><span data-stu-id="4d95c-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="4d95c-176">Selecione o menu **calendário** e, em seguida, selecione **Editor (pode ler, criar e modificar itens)**.</span><span class="sxs-lookup"><span data-stu-id="4d95c-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="4d95c-177">Para clientes Mac-Lync</span><span class="sxs-lookup"><span data-stu-id="4d95c-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="4d95c-178">**Guia encaminhamento de chamadas**</span><span class="sxs-lookup"><span data-stu-id="4d95c-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="4d95c-179">Se o cliente não tiver uma guia de **encaminhamento de chamadas** com o link **Editar meus membros do representante** e a delegar estiver localizada em um computador Mac, a delegação precisará se conectar a um computador baseado no Windows para configurar a delegação.</span><span class="sxs-lookup"><span data-stu-id="4d95c-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="4d95c-180">Isso ocorre porque os clientes Mac não podem fazer conexões MAPI, e isso é um requisito para estabelecer a delegação do Skype for Business a partir do Outlook.</span><span class="sxs-lookup"><span data-stu-id="4d95c-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="4d95c-181">Verificar o sucesso</span><span class="sxs-lookup"><span data-stu-id="4d95c-181">Verify success</span></span>

<span data-ttu-id="4d95c-182">Se a configuração for bem-sucedida, o representante deve ver a mensagem **você foi adicionado como um representante para < nome>** mensagem e também que as **pessoas para as quais eu gerencio as chamadas para** o grupo são criadas.</span><span class="sxs-lookup"><span data-stu-id="4d95c-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="4d95c-183">A delegação deve ver que o grupo de **representantes** é criado.</span><span class="sxs-lookup"><span data-stu-id="4d95c-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d95c-184">As permissões de delegação geralmente aparecem dentro de 30 minutos do processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="4d95c-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="4d95c-185">No entanto, esse processo pode levar até 24 horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4d95c-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="4d95c-186">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="4d95c-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="4d95c-187">Problemas comuns</span><span class="sxs-lookup"><span data-stu-id="4d95c-187">Common issues</span></span>

- > <span data-ttu-id="4d95c-188">**Edição 1** A entrada do representante continua sendo exibida nas **pessoas que eu gerencio as chamadas para** o grupo depois que o delegador removeu o representante do cliente do Outlook.</span><span class="sxs-lookup"><span data-stu-id="4d95c-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="4d95c-189">**Resolução 1** No cliente Skype for Business, clique com o botão direito do mouse no representante no grupo **representantes** e selecione **remover do grupo**.</span><span class="sxs-lookup"><span data-stu-id="4d95c-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="4d95c-190">**Problema 2** Após o acesso de representante ser concedido por meio do cliente Outlook, nem a mensagem de confirmação nem as **pessoas que eu gerencio chamadas para** o grupo aparecem para o representante.</span><span class="sxs-lookup"><span data-stu-id="4d95c-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="4d95c-191">**Resolução 2** Remova a delegação do cliente do Outlook, aguarde cerca de 15 minutos de replicação e, em seguida, adicione o representante novamente.</span><span class="sxs-lookup"><span data-stu-id="4d95c-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="4d95c-192">Outros problemas comuns</span><span class="sxs-lookup"><span data-stu-id="4d95c-192">Other common issues</span></span>

- <span data-ttu-id="4d95c-193">A delegação não funciona se o limite de 25 delegadores e 25 representantes for excedido.</span><span class="sxs-lookup"><span data-stu-id="4d95c-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="4d95c-194">Não há suporte para o cliente Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="4d95c-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4d95c-195">Se você instalar o cliente Skype for Business Basic, ele removerá e interromperá a delegação.</span><span class="sxs-lookup"><span data-stu-id="4d95c-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="4d95c-196">Se o valor de **status MAPI** não estiver **OK**, certifique-se de que os valores **SIP** e **SMTP** sejam correspondentes.</span><span class="sxs-lookup"><span data-stu-id="4d95c-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4d95c-197">Pode levar alguns minutos para que o status MAPI seja exibido como **OK** após iniciar pela primeira vez o Skype for Business e o Outlook.</span><span class="sxs-lookup"><span data-stu-id="4d95c-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="4d95c-198">Não há suporte para a criação de um grupo de segurança e a adição de permissões de delegação para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="4d95c-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="4d95c-199">O MAPI não está disponível.</span><span class="sxs-lookup"><span data-stu-id="4d95c-199">MAPI is unavailable.</span></span> <span data-ttu-id="4d95c-200">Consulte o [erro "MAPI não disponível" no cliente Skype for Business 2016](https://support.microsoft.com/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="4d95c-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="4d95c-201">A caixa de correio do Exchange Online não está acessível por meio do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4d95c-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="4d95c-202">Se isso ocorrer, execute o [teste de conectividade do Outlook](https://testconnectivity.microsoft.com/) para ter certeza de que ele passou.</span><span class="sxs-lookup"><span data-stu-id="4d95c-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="4d95c-203">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4d95c-203">Related topics</span></span>
[<span data-ttu-id="4d95c-204">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4d95c-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="4d95c-205">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="4d95c-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
