---
title: Personalizar propriedades da conta de usuário para Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Você pode usar os procedimentos nesta seção para modificar as propriedades de conta de usuário individual.
ms.openlocfilehash: fc15dac499fe5d812d5d084a919db10096e6dc56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="customize-user-account-properties-for-skype-for-business-server-2015"></a><span data-ttu-id="ba6bc-103">Personalizar propriedades da conta de usuário para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ba6bc-103">Customize user account properties for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ba6bc-104">Você pode usar os procedimentos nesta seção para modificar as propriedades de conta de usuário individual.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="ba6bc-105">Há duas operações básicas que podem ser feitas no nível do usuário individual:</span><span class="sxs-lookup"><span data-stu-id="ba6bc-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="ba6bc-106">Configurar opções de telefonia para uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="ba6bc-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="ba6bc-107">Mover usuários para outro pool</span><span class="sxs-lookup"><span data-stu-id="ba6bc-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="ba6bc-108">Configurar opções de telefonia para uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="ba6bc-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="ba6bc-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="ba6bc-109"></span></span>

<span data-ttu-id="ba6bc-110">Você pode personalizar as configurações de telefonia para um usuário específico (desde que o usuário individual tiver sido habilitado para Skype para Business Server 2015 e a organização dá suporte à telefonia).</span><span class="sxs-lookup"><span data-stu-id="ba6bc-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server 2015 and the organization supports telephony).</span></span>
  
<span data-ttu-id="ba6bc-111">Skype para opções de telefonia do usuário Business Server incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ba6bc-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="ba6bc-112">**Áudio/vídeo desabilitado** O usuário não pode fazer chamadas com áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="ba6bc-113">**PC-PC somente** O usuário pode fazer somente PC-PC áudio ou vídeos chamadas.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="ba6bc-114">**Enterprise Voice** O usuário pode usar o Skype para Business Server 2015 infra-estrutura para rotear todas as chamadas de entrada e saídas.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-114">**Enterprise Voice** The user can use the Skype for Business Server 2015 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="ba6bc-115">O usuário também pode fazer chamadas de PC para PC.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="ba6bc-116">**Controle de chamada remota** O usuário pode usar o Skype para Business Server 2015 para controlar um telefone de mesa e também pode fazer chamadas de PC para PC.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-116">**Remote call control** The user can use Skype for Business Server 2015 to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="ba6bc-117">Para obter detalhes sobre como configurar telefonia para uma organização, consulte [habilitar usuários para Enterprise Voice no Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e [Implantar o Enterprise Voice no Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="ba6bc-118">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba6bc-119">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ba6bc-120">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ba6bc-121">Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou linha identificador URI (Uniform Resource) da conta de usuário que você deseja e clique em **Find **.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="ba6bc-122">Na tabela, clique na conta de usuário que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="ba6bc-123">No menu **Editar** , clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="ba6bc-124">Em **telefonia**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ba6bc-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="ba6bc-125">Para desabilitar as chamadas de áudio e vídeos para o usuário, clique em **áudio/vídeo desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="ba6bc-126">Para habilitar as comunicações de áudio PC-PC do usuário, mas o controle de chamada remota não ou o Enterprise Voice, clique em **PC-PC apenas**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="ba6bc-127">Especifica um valor para **URI de linha** de telefone que o usuário usa para comunicações de áudio PC-PC.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="ba6bc-128">Para rotear chamadas de telefone do usuário usando o Skype para a infra-estrutura de negócios de acordo com a classe de política de serviço, incluindo a comunicação de áudio PC-PC, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="ba6bc-129">Em **URI da linha**, especifique o número de telefone para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="ba6bc-130">Na **política do plano de discagem** e **diretiva de voz**, especifique as políticas apropriadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="ba6bc-131">Para especificar as regras de normalização para traduzir números de telefone discados pelo usuário para o formato e. 164, selecione o perfil de local apropriado na **política local**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="ba6bc-132">Para habilitar a chamada remota o controle, que permite aos usuários controlar sua linha de telefone de mesa do Skype para negócios 2015 de Server fazer chamadas de PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server 2015 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="ba6bc-133">Em **URI da linha**, especifique o número de telefone para controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="ba6bc-134">O usuário deve ter um telefone de mesa e a conexão do privada de comutação telefônica (PBX) para roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="ba6bc-135">Mover usuários para outro pool</span><span class="sxs-lookup"><span data-stu-id="ba6bc-135">Move users to another pool</span></span>
<span data-ttu-id="ba6bc-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="ba6bc-136"></span></span>

<span data-ttu-id="ba6bc-137">Você pode usar o Skype para painel de controle do Business Server para atribuir usuários a um servidor ou pool específico.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="ba6bc-138">Mover todos os usuários existentes de um pool de origem que está executando o Lync Server 2010 ou versão anterior para um Skype para Business Server 2015 pool de destino em um ambiente do Active Directory complexo pode resultar em mais lenta replicação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server 2015 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="ba6bc-139">Para evitar isso, você pode usar filtros de pesquisa para mover usuários de pools que estejam executando o Lync Server 2010 ou anteriormente separadamente, ou você pode usar o Skype para Business Server Management Shell para mover usuários com cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="ba6bc-140">Além disso, a funcionalidade do filtro funciona com o Skype para usuários corporativos Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-140">Also, the filter functionality works with Skype for Business Server 2015 users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="ba6bc-141">Para mover usuários selecionados para um outro servidor ou pool</span><span class="sxs-lookup"><span data-stu-id="ba6bc-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="ba6bc-142">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba6bc-143">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ba6bc-144">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ba6bc-145">Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou linha identificador URI (Uniform Resource) da conta de usuário que você deseja e clique em **Find **.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="ba6bc-146">Na tabela, selecione um usuário específico ou usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="ba6bc-147">No menu **ação** , clique em **mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="ba6bc-148">Em **Mover usuários**, selecione o pool que você deseja mover os usuários no **pool de registradores de destino**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="ba6bc-149">(Opcional) Se o servidor de destino ou o pool não estiver disponível, marque a caixa de seleção **Forçar** .</span><span class="sxs-lookup"><span data-stu-id="ba6bc-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ba6bc-150">Se você selecionar **Force**, a conta de usuário é movida, mas quaisquer dados de usuário associada são excluídos (por exemplo, conferências que o usuário tiver programado).</span><span class="sxs-lookup"><span data-stu-id="ba6bc-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="ba6bc-151">Se você não selecionar a ele, a conta e os dados associados são movidos.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="ba6bc-152">Para mover todos os usuários de um servidor ou pool para outro servidor ou pool</span><span class="sxs-lookup"><span data-stu-id="ba6bc-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="ba6bc-153">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba6bc-154">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ba6bc-155">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ba6bc-156">No menu **ação** , clique em **mover todos os usuários ao pool**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="ba6bc-157">Em **Mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool de registradores de origem**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="ba6bc-158">Em **pool de registradores de destino**, selecione o pool que você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="ba6bc-159">(Opcional) Se o servidor de destino ou o pool não estiver disponível, marque a caixa de seleção **Forçar** .</span><span class="sxs-lookup"><span data-stu-id="ba6bc-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ba6bc-160">Se você selecionar **Force**, a conta de usuário é movida, mas quaisquer dados de usuário associada são excluídos (por exemplo, conferências que o usuário tiver programado).</span><span class="sxs-lookup"><span data-stu-id="ba6bc-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="ba6bc-161">Se você não selecionar a ele, a conta e os dados associados são movidos.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="ba6bc-162">Para mover usuários de um pool para um pool diferente usando um filtro</span><span class="sxs-lookup"><span data-stu-id="ba6bc-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="ba6bc-163">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba6bc-164">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ba6bc-165">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ba6bc-166">Em **Pesquisa de usuário**, clique em **Pesquisar**e, em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="ba6bc-167">Nos critérios de pesquisa, selecione **Pool de registradores**, selecione é **igual a**, selecione **FQDN atual do Pool**e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="ba6bc-168">No menu **ação** , clique em **mover todos os usuários ao pool**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ba6bc-169">Quando um filtro é aplicado a um conjunto existente de usuários, a opção **mover todos os usuários para o pool** está no contexto do subconjunto de filtrada de usuários, não em **todos os** usuários possíveis.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="ba6bc-170">Em **Mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool de registradores de origem**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="ba6bc-171">Em **pool de registradores de destino**, selecione o pool de onde você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="ba6bc-172">(Opcional) Se o servidor de destino ou o pool não estiver disponível, marque a caixa de seleção **Forçar** .</span><span class="sxs-lookup"><span data-stu-id="ba6bc-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ba6bc-173">Se você selecionar **Force**, a conta de usuário é movida, mas quaisquer dados de usuário associada são excluídos (por exemplo, conferências que o usuário tiver programado e contatos).</span><span class="sxs-lookup"><span data-stu-id="ba6bc-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="ba6bc-174">Se você não selecionar a ele, a conta e os dados associados são movidos.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="ba6bc-175">Para mover usuários de um pool para outro usando cmdlets do Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="ba6bc-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="ba6bc-176">Dependendo de como você executa comandos do Windows PowerShell (ou seja, local ou remotamente), você precisa fazer logon como membro do Skype correto para funções administrativas do Business Server 2015 da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ba6bc-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server 2015 administrative roles as follows:</span></span>
    
   <span data-ttu-id="ba6bc-177">a.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-177">a.</span></span> <span data-ttu-id="ba6bc-178">Se você estiver executando os comandos na máquina local (por exemplo, você faça logon diretamente em um servidor Front-End): faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com o necessário direitos de usuário, conforme descrito em **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="ba6bc-179">b.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-179">b.</span></span> <span data-ttu-id="ba6bc-180">Se você estiver executando os comandos remotamente em outro computador (por exemplo, você faz logon seu computador e executa os comandos remotamente em um Standard Edition servidor Front-End): a partir de uma conta de usuário atribuída à função CsUserAdministrator ou a CsAdministrator função, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba6bc-181">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ba6bc-182">Para mover usuários únicos, use o cmdlet Move-CsUser conforme segue:</span><span class="sxs-lookup"><span data-stu-id="ba6bc-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="ba6bc-183">Onde o usuário mover é o usuário Pilar Ackerman e o usuário será movido de seu pool doméstico atribuído atualmente para o pool pool01. contoso.NET</span><span class="sxs-lookup"><span data-stu-id="ba6bc-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="ba6bc-184">Para mover um grande número de usuários, use os filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="ba6bc-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="ba6bc-185">Os comandos combinados do **Get-CsUser** e **Move-CsUser** podem resultar nisto:</span><span class="sxs-lookup"><span data-stu-id="ba6bc-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


