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
description: Este artigo explica como configurar e solucionar problemas de delegação do Skype for Business Online. Este artigo fornece orientações sobre recomendações de configuração, práticas recomendadas e etapas de solução de problemas.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010794"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="bedce-104">Configurar e solucionar problemas de delegação do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bedce-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="bedce-105">Este artigo explica como configurar e solucionar problemas de delegação do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="bedce-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="bedce-106">Este artigo fornece orientações sobre recomendações de configuração, práticas recomendadas e etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="bedce-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="bedce-107">Diretrizes e requisitos</span><span class="sxs-lookup"><span data-stu-id="bedce-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="bedce-108">Diretrizes para delegação</span><span class="sxs-lookup"><span data-stu-id="bedce-108">Guidelines for delegation</span></span>

<span data-ttu-id="bedce-109">Configurar e fazer com que a delegação funcione corretamente depende de você seguir estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="bedce-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="bedce-110">Você deve usar o cliente completo do Skype for Business 2015 com as atualizações mais recentes ou o cliente completo do Skype for Business 2016.</span><span class="sxs-lookup"><span data-stu-id="bedce-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="bedce-111">Você deve estar usando o cliente outlook 2013 com as atualizações mais recentes ou o cliente do Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="bedce-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="bedce-112">Certifique-se de que o delegador e os computadores delegados tenham um perfil de email do Outlook que seja o perfil principal ou padrão.</span><span class="sxs-lookup"><span data-stu-id="bedce-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="bedce-113">Esse perfil de email deve conter apenas uma conta.</span><span class="sxs-lookup"><span data-stu-id="bedce-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="bedce-114">O Skype for Business para o delegador e o representante devem ser usuários online.</span><span class="sxs-lookup"><span data-stu-id="bedce-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="bedce-115">Além disso, as caixas de correio do Exchange Server para cada conta devem estar online ou ambas no local.</span><span class="sxs-lookup"><span data-stu-id="bedce-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="bedce-116">O delegador e o representante devem estar usando a mesma versão principal do Outlook.</span><span class="sxs-lookup"><span data-stu-id="bedce-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="bedce-117">O **valor do atributo EnableExchangeDelegateSync** deve ser definido como **true** na política do cliente.</span><span class="sxs-lookup"><span data-stu-id="bedce-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="bedce-118">Você pode verificar essa configuração executando o cmdlet **Get-CSClientPolicy** no módulo PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="bedce-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="bedce-119">O delegador e o representante devem estar no Skype for Business e no Outlook ao mesmo tempo em diferentes estações de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bedce-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="bedce-120">Não há suporte para caixas de correio compartilhadas para a delegação do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="bedce-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="bedce-121">Isso porque a caixa de correio compartilhada não tem a lista de controles de acesso (ACL) de **sernbehalf.**</span><span class="sxs-lookup"><span data-stu-id="bedce-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="bedce-122">Suporte à versão do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bedce-122">Skype for Business client version support</span></span>

||<span data-ttu-id="bedce-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="bedce-123">**Outlook 2013**</span></span>|<span data-ttu-id="bedce-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="bedce-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bedce-125">**Cliente Lync/Skype for Business Basic**</span><span class="sxs-lookup"><span data-stu-id="bedce-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="bedce-126">Incompatível</span><span class="sxs-lookup"><span data-stu-id="bedce-126">Not supported</span></span> |<span data-ttu-id="bedce-127">Incompatível</span><span class="sxs-lookup"><span data-stu-id="bedce-127">Not supported</span></span>
|<span data-ttu-id="bedce-128">**Skype for Business 2015**</span><span class="sxs-lookup"><span data-stu-id="bedce-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="bedce-129">Compatível </span><span class="sxs-lookup"><span data-stu-id="bedce-129">Supported</span></span>| <span data-ttu-id="bedce-130">Compatível</span><span class="sxs-lookup"><span data-stu-id="bedce-130">Supported</span></span>|
|<span data-ttu-id="bedce-131">**Skype for Business 2016**</span><span class="sxs-lookup"><span data-stu-id="bedce-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="bedce-132">Compatível </span><span class="sxs-lookup"><span data-stu-id="bedce-132">Supported</span></span>| <span data-ttu-id="bedce-133">Compatível</span><span class="sxs-lookup"><span data-stu-id="bedce-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="bedce-134">Requisitos de licenciamento</span><span class="sxs-lookup"><span data-stu-id="bedce-134">Licensing requirements</span></span>

<span data-ttu-id="bedce-135">**Cenário de licenciamento enterprise E3**</span><span class="sxs-lookup"><span data-stu-id="bedce-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="bedce-136">**Licença**</span><span class="sxs-lookup"><span data-stu-id="bedce-136">**License**</span></span>|<span data-ttu-id="bedce-137">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="bedce-137">**Clients**</span></span>|<span data-ttu-id="bedce-138">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="bedce-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bedce-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="bedce-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="bedce-140">Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bedce-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bedce-141">Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bedce-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="bedce-142">O cliente Skype for Business Basic não dá suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="bedce-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bedce-143">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="bedce-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="bedce-144">Enterprise E3 com o Office 365 Phone System + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="bedce-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="bedce-145">Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bedce-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bedce-146">Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bedce-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bedce-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="bedce-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="bedce-148">O cliente Skype for Business Basic não dá suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="bedce-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bedce-149">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="bedce-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="bedce-150">**Cenário de licenciamento enterprise E5**</span><span class="sxs-lookup"><span data-stu-id="bedce-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="bedce-151">**Licença**</span><span class="sxs-lookup"><span data-stu-id="bedce-151">**License**</span></span>|<span data-ttu-id="bedce-152">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="bedce-152">**Clients**</span></span>|<span data-ttu-id="bedce-153">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="bedce-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bedce-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="bedce-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="bedce-155">O Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="bedce-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="bedce-156">Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bedce-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="bedce-157">O cliente Skype for Business Basic não dá suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="bedce-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bedce-158">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="bedce-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="bedce-159">Enterprise E5 mais Plano de Chamada do Office 365</span><span class="sxs-lookup"><span data-stu-id="bedce-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="bedce-160">Skype for Business para Mac 2016</span><span class="sxs-lookup"><span data-stu-id="bedce-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="bedce-161">Lync 2013 (Skype for Business 2015) usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bedce-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bedce-162">Skype for Business 2016 usado com o Outlook 2013 ou o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bedce-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="bedce-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="bedce-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="bedce-164">O cliente Skype for Business Basic não dá suporte à delegação.</span><span class="sxs-lookup"><span data-stu-id="bedce-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="bedce-165">Para clientes Mac, você pode delegar chamadas, mas não reuniões.</span><span class="sxs-lookup"><span data-stu-id="bedce-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="bedce-166">Configurar e verificar delegação</span><span class="sxs-lookup"><span data-stu-id="bedce-166">Set up and verify delegation</span></span>

<span data-ttu-id="bedce-167">Para configurar a delegação do Skype for Business Online, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="bedce-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="bedce-168">Para clientes windows</span><span class="sxs-lookup"><span data-stu-id="bedce-168">For Windows clients</span></span>

 <span data-ttu-id="bedce-169">**Guia Encaminhamento de Chamada**</span><span class="sxs-lookup"><span data-stu-id="bedce-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="bedce-170">Selecione **Configurações** de Encaminhamento de Chamada de Opções  >    >  **de Ferramentas.**</span><span class="sxs-lookup"><span data-stu-id="bedce-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="bedce-171">Selecione **Editar membros de meu representante.**</span><span class="sxs-lookup"><span data-stu-id="bedce-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="bedce-172">Selecione **Adicionar,** selecione o representante que você deseja adicionar e, em seguida, selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="bedce-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="bedce-173">**Sem guia Encaminhamento de Chamada**</span><span class="sxs-lookup"><span data-stu-id="bedce-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="bedce-174">No Outlook, selecione **Acesso de** Representante  >  **de Configurações de Conta** de  >    >  **Arquivo.**</span><span class="sxs-lookup"><span data-stu-id="bedce-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="bedce-175">Localize e adicione o nome da pessoa que será o representante.</span><span class="sxs-lookup"><span data-stu-id="bedce-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="bedce-176">Selecione o menu **Calendário** e, em seguida, selecione **Editor (pode ler, criar e modificar itens).**</span><span class="sxs-lookup"><span data-stu-id="bedce-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="bedce-177">Para clientes Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="bedce-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="bedce-178">**Guia Encaminhamento de Chamada**</span><span class="sxs-lookup"><span data-stu-id="bedce-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="bedce-179">Se o cliente não  tiver uma guia Encaminhamento de Chamada que tenha o **link** Editar meus Membros Delegados e o delegador estiver localizado em um computador Mac, o delegador deverá entrar em um computador baseado no Windows para configurar a delegação.</span><span class="sxs-lookup"><span data-stu-id="bedce-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="bedce-180">Isso porque os clientes mac não podem fazer conexões MAPI, e esse é um requisito para estabelecer a delegação do Skype for Business do Outlook.</span><span class="sxs-lookup"><span data-stu-id="bedce-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="bedce-181">Verificar o sucesso</span><span class="sxs-lookup"><span data-stu-id="bedce-181">Verify success</span></span>

<span data-ttu-id="bedce-182">Se a configuração for bem-sucedida, o representante verá que Você foi adicionado como representante  da mensagem **< Nome>** e também que o grupo Pessoas para quem Eu Gerencie Chamadas foi criado.</span><span class="sxs-lookup"><span data-stu-id="bedce-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="bedce-183">O delegador deve ver que o grupo **Representantes** é criado.</span><span class="sxs-lookup"><span data-stu-id="bedce-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bedce-184">As permissões de delegação geralmente aparecem dentro de 30 minutos após o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="bedce-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="bedce-185">No entanto, esse processo pode levar até 24 horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="bedce-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="bedce-186">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bedce-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="bedce-187">Problemas comuns</span><span class="sxs-lookup"><span data-stu-id="bedce-187">Common issues</span></span>

- > <span data-ttu-id="bedce-188">**Problema 1** A entrada de representante continua a aparecer no grupo **Pessoas para** as que Eu Gerencio Chamadas depois que o delegado remover o representante do cliente do Outlook.</span><span class="sxs-lookup"><span data-stu-id="bedce-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="bedce-189">**Resolução 1** No cliente Skype for Business, clique com  o botão direito do mouse no representante no grupo Representantes e selecione **Remover do Grupo.**</span><span class="sxs-lookup"><span data-stu-id="bedce-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="bedce-190">**Problema 2** Depois que o acesso de representante é concedido por  meio do cliente do Outlook, nem a mensagem de confirmação nem o grupo Pessoas para quem Eu Gerencio Chamadas são exibidos para o representante.</span><span class="sxs-lookup"><span data-stu-id="bedce-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="bedce-191">**Resolução 2** Remova a delegação do cliente outlook, aguarde cerca de 15 minutos para replicação e adicione o representante novamente.</span><span class="sxs-lookup"><span data-stu-id="bedce-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="bedce-192">Outros problemas comuns</span><span class="sxs-lookup"><span data-stu-id="bedce-192">Other common issues</span></span>

- <span data-ttu-id="bedce-193">A delegação não funcionará se o limite de 25 delegadores e 25 representantes for excedido.</span><span class="sxs-lookup"><span data-stu-id="bedce-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="bedce-194">Não há suporte para o cliente Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="bedce-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bedce-195">Se você instalar o cliente Skype for Business Basic, ele removerá e quebrará a delegação.</span><span class="sxs-lookup"><span data-stu-id="bedce-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="bedce-196">Se o **valor status MAPI** não estiver **OK,** certifique-se de que os valores **SIP** e **SMTP** corresponderem.</span><span class="sxs-lookup"><span data-stu-id="bedce-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bedce-197">Pode levar vários minutos para que o status MAPI seja exibido como **OK** depois de iniciar o Skype for Business e o Outlook pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="bedce-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="bedce-198">Não há suporte para a criação de um grupo de segurança e a adição de permissões de delegação para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="bedce-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="bedce-199">MAPI não está disponível.</span><span class="sxs-lookup"><span data-stu-id="bedce-199">MAPI is unavailable.</span></span> <span data-ttu-id="bedce-200">Veja [o erro "MAPI indisponível" no cliente Skype for Business 2016.](https://support.microsoft.com/help/3147130)</span><span class="sxs-lookup"><span data-stu-id="bedce-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="bedce-201">A caixa de correio do Exchange Online não é acessível por meio do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bedce-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="bedce-202">Se isso ocorrer, execute o [teste de conectividade do Outlook](https://testconnectivity.microsoft.com/) para garantir que ele passe.</span><span class="sxs-lookup"><span data-stu-id="bedce-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="bedce-203">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bedce-203">Related topics</span></span>
[<span data-ttu-id="bedce-204">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bedce-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="bedce-205">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="bedce-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
