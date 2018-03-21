---
title: "Configurar e solucionar problemas Skype para delegação Business Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Este artigo explica como configurar e solucionar problemas Skype para delegação Business Online. Este artigo fornece orientações para as etapas de solução de problemas, práticas recomendadas e recomendações de instalação."
ms.openlocfilehash: b69f6712f78906bc955d3ce014fe8ccd6ab252c1
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="3896b-104">Configurar e solucionar problemas Skype para delegação Business Online</span><span class="sxs-lookup"><span data-stu-id="3896b-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="3896b-105">Este artigo explica como configurar e solucionar problemas Skype para delegação Business Online.</span><span class="sxs-lookup"><span data-stu-id="3896b-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="3896b-106">Este artigo fornece orientações para as etapas de solução de problemas, práticas recomendadas e recomendações de instalação.</span><span class="sxs-lookup"><span data-stu-id="3896b-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="3896b-107">Requisitos e diretrizes</span><span class="sxs-lookup"><span data-stu-id="3896b-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="3896b-108">Diretrizes para delegação</span><span class="sxs-lookup"><span data-stu-id="3896b-108">Guidelines for delegation</span></span>

<span data-ttu-id="3896b-109">Configurando e instalando a delegação funcione corretamente dependem seguir estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="3896b-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="3896b-110">Você deve estar usando o Skype para negócios 2015 completa do cliente com as atualizações mais recentes ou o Skype para negócios 2016 completa do cliente.</span><span class="sxs-lookup"><span data-stu-id="3896b-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="3896b-111">Você deve estar usando o cliente do Outlook 2013 com as atualizações mais recentes ou o cliente Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="3896b-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="3896b-112">Certifique-se de que o delegator e o representante computadores têm um perfil de email do Outlook que é o principal ou o perfil padrão.</span><span class="sxs-lookup"><span data-stu-id="3896b-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="3896b-113">Se o perfil de email deve conter apenas uma conta.</span><span class="sxs-lookup"><span data-stu-id="3896b-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="3896b-114">Skype para negócios para o delegator e o delegado deve ser usuários Online.</span><span class="sxs-lookup"><span data-stu-id="3896b-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="3896b-115">Além disso, as Exchange Server caixas de correio para cada conta deverá estar Online ou ambos ser no local.</span><span class="sxs-lookup"><span data-stu-id="3896b-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="3896b-116">Delegator tanto o delegado devem estar usando a mesma versão principal do Outlook.</span><span class="sxs-lookup"><span data-stu-id="3896b-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="3896b-117">O valor do atributo **EnableExchangeDelegateSync** deve ser definido como **true** na diretiva do cliente.</span><span class="sxs-lookup"><span data-stu-id="3896b-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="3896b-118">Você pode verificar esta configuração, executando o cmdlet **Get-CSClientPolicy** no Skype para o módulo de PowerShell Online de negócios.</span><span class="sxs-lookup"><span data-stu-id="3896b-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="3896b-119">O delegator e o delegado devem estar conectados ao Skype para negócios e do Outlook ao mesmo tempo em diferentes estações de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3896b-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="3896b-120">Caixas de correio compartilhadas não são suportadas para Skype para delegação Business Online.</span><span class="sxs-lookup"><span data-stu-id="3896b-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="3896b-121">Isso ocorre porque a caixa de correio compartilhada não tem a lista de controle de acesso (ACL) **sendonbehalf** .</span><span class="sxs-lookup"><span data-stu-id="3896b-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="3896b-122">Skype para suporte de versão do cliente de negócios</span><span class="sxs-lookup"><span data-stu-id="3896b-122">Skype for Business client version support</span></span>

||<span data-ttu-id="3896b-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="3896b-123">**Outlook 2013**</span></span>|<span data-ttu-id="3896b-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="3896b-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3896b-125">**Lync/Skype para negócios básicos do cliente**</span><span class="sxs-lookup"><span data-stu-id="3896b-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="3896b-126">Não suportado</span><span class="sxs-lookup"><span data-stu-id="3896b-126">Not supported</span></span> |<span data-ttu-id="3896b-127">Não suportado</span><span class="sxs-lookup"><span data-stu-id="3896b-127">Not supported</span></span>
|<span data-ttu-id="3896b-128">**Skype para negócios 2015**</span><span class="sxs-lookup"><span data-stu-id="3896b-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="3896b-129">Compatível </span><span class="sxs-lookup"><span data-stu-id="3896b-129">Supported</span></span>| <span data-ttu-id="3896b-130">Compatível </span><span class="sxs-lookup"><span data-stu-id="3896b-130">Supported</span></span>|
|<span data-ttu-id="3896b-131">**Skype para 2016 de negócios**</span><span class="sxs-lookup"><span data-stu-id="3896b-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="3896b-132">Compatível </span><span class="sxs-lookup"><span data-stu-id="3896b-132">Supported</span></span>| <span data-ttu-id="3896b-133">Compatível </span><span class="sxs-lookup"><span data-stu-id="3896b-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="3896b-134">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="3896b-134">Licensing requirements</span></span>

<span data-ttu-id="3896b-135">**Cenário de licenciamento corporativo E3**</span><span class="sxs-lookup"><span data-stu-id="3896b-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="3896b-136">**Licença**</span><span class="sxs-lookup"><span data-stu-id="3896b-136">**License**</span></span>|<span data-ttu-id="3896b-137">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="3896b-137">**Clients**</span></span>|<span data-ttu-id="3896b-138">**Observações**</span><span class="sxs-lookup"><span data-stu-id="3896b-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3896b-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="3896b-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="3896b-140">Lync 2013 (Skype para negócios 2015) usados com o Outlook 2013 ou 2016 do Outlook</span><span class="sxs-lookup"><span data-stu-id="3896b-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3896b-141">Skype para 2016 corporativos usados com o Outlook 2013 ou 2016 do Outlook</span><span class="sxs-lookup"><span data-stu-id="3896b-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="3896b-142">Skype para básicos de negócios do cliente não oferece suporte a delegação.</span><span class="sxs-lookup"><span data-stu-id="3896b-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="3896b-143">Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.</span><span class="sxs-lookup"><span data-stu-id="3896b-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="3896b-144">Enterprise E3 com o sistema de telefone do Office 365 + Office 365 xCalling plano</span><span class="sxs-lookup"><span data-stu-id="3896b-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="3896b-145">Lync 2013 (Skype para negócios 2015) usados com o Outlook 2013 ou 2016 do Outlook</span><span class="sxs-lookup"><span data-stu-id="3896b-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3896b-146">Skype para 2016 corporativos usados com o Outlook 2013 ou 2016 do Outlook</span><span class="sxs-lookup"><span data-stu-id="3896b-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3896b-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="3896b-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="3896b-148">Skype para básicos de negócios do cliente não oferece suporte a delegação.</span><span class="sxs-lookup"><span data-stu-id="3896b-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="3896b-149">Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.</span><span class="sxs-lookup"><span data-stu-id="3896b-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="3896b-150">**Cenário de licenciamento E5 da empresa**</span><span class="sxs-lookup"><span data-stu-id="3896b-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="3896b-151">**Licença**</span><span class="sxs-lookup"><span data-stu-id="3896b-151">**License**</span></span>|<span data-ttu-id="3896b-152">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="3896b-152">**Clients**</span></span>|<span data-ttu-id="3896b-153">**Observações**</span><span class="sxs-lookup"><span data-stu-id="3896b-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3896b-154">E5 da empresa</span><span class="sxs-lookup"><span data-stu-id="3896b-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="3896b-155">Lync 2013 (Skype para negócios 2015) usados com o Outlook 2013 ou 2016 do Outlook.</span><span class="sxs-lookup"><span data-stu-id="3896b-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="3896b-156">Skype para 2016 corporativos usados com o Outlook 2013 ou 2016 do Outlook</span><span class="sxs-lookup"><span data-stu-id="3896b-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="3896b-157">Skype para básicos de negócios do cliente não oferece suporte a delegação.</span><span class="sxs-lookup"><span data-stu-id="3896b-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="3896b-158">Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.</span><span class="sxs-lookup"><span data-stu-id="3896b-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="3896b-159">Enterprise E5 plus plano de chamada do Office 365</span><span class="sxs-lookup"><span data-stu-id="3896b-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="3896b-160">Skype para negócios para Mac 2016</span><span class="sxs-lookup"><span data-stu-id="3896b-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="3896b-161">Lync 2013 (Skype para negócios 2015) usados com o Outlook 2013 ou 2016 do Outlook</span><span class="sxs-lookup"><span data-stu-id="3896b-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3896b-162">Skype para 2016 corporativos usados com o Outlook 2013 ou 2016 do Outlook</span><span class="sxs-lookup"><span data-stu-id="3896b-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="3896b-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="3896b-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="3896b-164">Skype para básicos de negócios do cliente não oferece suporte a delegação.</span><span class="sxs-lookup"><span data-stu-id="3896b-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="3896b-165">Para clientes do Mac, você pode delegar chamadas, mas não em reuniões.</span><span class="sxs-lookup"><span data-stu-id="3896b-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="3896b-166">Configurar e verificar a delegação</span><span class="sxs-lookup"><span data-stu-id="3896b-166">Set up and verify delegation</span></span>

<span data-ttu-id="3896b-167">Para configurar o Skype para delegação Business Online, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3896b-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="3896b-168">Para clientes Windows</span><span class="sxs-lookup"><span data-stu-id="3896b-168">For Windows clients</span></span>

 <span data-ttu-id="3896b-169">**Guia de encaminhamento de chamadas**</span><span class="sxs-lookup"><span data-stu-id="3896b-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="3896b-170">Selecione **Ferramentas** > **Opções** > **configurações de encaminhamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="3896b-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="3896b-171">Selecione **Editar Meus membros representantes**.</span><span class="sxs-lookup"><span data-stu-id="3896b-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="3896b-172">Selecione **Adicionar**, selecione o representante que você deseja adicionar e selecione **Okey**.</span><span class="sxs-lookup"><span data-stu-id="3896b-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="3896b-173">**Nenhuma guia encaminhamento de chamadas**</span><span class="sxs-lookup"><span data-stu-id="3896b-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="3896b-174">No Outlook, selecione o **arquivo** > **Configurações de conta** > **Acesso delegado** > **Add**.</span><span class="sxs-lookup"><span data-stu-id="3896b-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="3896b-175">Localize e, em seguida, adicione o nome da pessoa que vai ser delegado.</span><span class="sxs-lookup"><span data-stu-id="3896b-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="3896b-176">Selecione o menu **calendário** e selecione **Editor (pode ler, criar e modificar itens)**.</span><span class="sxs-lookup"><span data-stu-id="3896b-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="3896b-177">Clientes Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="3896b-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="3896b-178">**Guia de encaminhamento de chamadas**</span><span class="sxs-lookup"><span data-stu-id="3896b-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="3896b-179">Se o cliente não tem uma guia **Encaminhamento de chamadas** que tenha o link **Editar Meus membros representantes** e representante está localizado em um computador Mac, representante deve entrar em um computador baseado no Windows para configurar a delegação.</span><span class="sxs-lookup"><span data-stu-id="3896b-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="3896b-180">Isso ocorre porque os clientes Mac não podem fazer conexões MAPI e isso é um requisito para estabelecer Skype para delegação de negócios do Outlook.</span><span class="sxs-lookup"><span data-stu-id="3896b-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="3896b-181">Verificar o sucesso</span><span class="sxs-lookup"><span data-stu-id="3896b-181">Verify success</span></span>

<span data-ttu-id="3896b-182">Se a instalação for bem-sucedida, o delegado deve ver o que **você foi adicionado como um representante para < nome >** mensagem e também que o grupo de **pessoas para as quais gerenciar chamadas** é criado.</span><span class="sxs-lookup"><span data-stu-id="3896b-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="3896b-183">Representante verá que o grupo de **delegados** é criado.</span><span class="sxs-lookup"><span data-stu-id="3896b-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3896b-184">Permissões de delegação normalmente aparecem em até 30 minutos do processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="3896b-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="3896b-185">No entanto, esse processo pode levar até 24 horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="3896b-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="3896b-186">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="3896b-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="3896b-187">Problemas comuns</span><span class="sxs-lookup"><span data-stu-id="3896b-187">Common issues</span></span>

- > <span data-ttu-id="3896b-188">**Problema 1** A entrada de representante continua aparecem no grupo de **pessoas para as quais gerenciar chamadas** após a delegator tiver removido o representante do cliente do Outlook.</span><span class="sxs-lookup"><span data-stu-id="3896b-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="3896b-189">**Solução 1** Na Skype para o cliente de negócios, o representante do grupo de **representantes** do mouse em e selecione **Remover do grupo**.</span><span class="sxs-lookup"><span data-stu-id="3896b-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="3896b-190">**Problema 2** Depois que o acesso de representante for concedido por meio do cliente do Outlook, nem a mensagem de confirmação nem o grupo de **pessoas para as quais gerenciar chamadas** aparecem para o representante.</span><span class="sxs-lookup"><span data-stu-id="3896b-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="3896b-191">**Resolução 2** Remover a delegação de cliente do Outlook, aguarde cerca de 15 minutos para replicação e adicione novamente o delegado.</span><span class="sxs-lookup"><span data-stu-id="3896b-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="3896b-192">Outros problemas comuns</span><span class="sxs-lookup"><span data-stu-id="3896b-192">Other common issues</span></span>

- <span data-ttu-id="3896b-193">Delegação não funciona se o limite dos 25 delegantes e 25 representantes é excedido.</span><span class="sxs-lookup"><span data-stu-id="3896b-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="3896b-194">Não há suporte para o Skype para básicos de negócios do cliente.</span><span class="sxs-lookup"><span data-stu-id="3896b-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3896b-195">Se você instalar o Skype para básicos de negócios do cliente, ele removerá e interromper a delegação.</span><span class="sxs-lookup"><span data-stu-id="3896b-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="3896b-196">Se o valor de **Status de MAPI** não for **Okey**, certifique-se de que coincidem com os valores de **SIP** e **SMTP** .</span><span class="sxs-lookup"><span data-stu-id="3896b-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3896b-197">Pode levar alguns minutos para que o status MAPI exibir como **Okey** após iniciar primeiro Skype para negócios e Outlook.</span><span class="sxs-lookup"><span data-stu-id="3896b-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="3896b-198">Criando um grupo de segurança e adicionar permissões de delegação para esse grupo de segurança não não suportado.</span><span class="sxs-lookup"><span data-stu-id="3896b-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="3896b-199">MAPI não está disponível.</span><span class="sxs-lookup"><span data-stu-id="3896b-199">MAPI is unavailable.</span></span> <span data-ttu-id="3896b-200">Consulte a [mensagem de erro "MAPI indisponível" no Skype para 2016 de negócios do cliente](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="3896b-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="3896b-201">A caixa de correio do Exchange Online não está acessível através do Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="3896b-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="3896b-202">Se isso ocorrer, execute o [teste de conectividade do Outlook](https://testconnectivity.microsoft.com/) para certificar-se de que ele passa.</span><span class="sxs-lookup"><span data-stu-id="3896b-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="3896b-203">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3896b-203">Related topics</span></span>
[<span data-ttu-id="3896b-204">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3896b-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="3896b-205">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="3896b-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
