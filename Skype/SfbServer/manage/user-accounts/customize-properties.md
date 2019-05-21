---
title: Personalizar as propriedades da conta de usuário para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Você pode usar os procedimentos desta seção para modificar propriedades de conta de usuário individuais.
ms.openlocfilehash: d0e1a3ac02f5696e91e07c0f08cf0cf10e09f98e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275070"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="d485d-103">Personalizar as propriedades da conta de usuário para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d485d-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="d485d-104">Você pode usar os procedimentos desta seção para modificar propriedades de conta de usuário individuais.</span><span class="sxs-lookup"><span data-stu-id="d485d-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="d485d-105">Há duas operações básicas que podem ser realizadas no nível do usuário individual:</span><span class="sxs-lookup"><span data-stu-id="d485d-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="d485d-106">Configurar opções de telefonia para uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="d485d-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="d485d-107">Mover usuários para outro pool</span><span class="sxs-lookup"><span data-stu-id="d485d-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="d485d-108">Configurar opções de telefonia para uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="d485d-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="d485d-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="d485d-109"></span></span>

<span data-ttu-id="d485d-110">Você pode personalizar as configurações de telefonia para um usuário específico (desde que o usuário individual tenha sido habilitado para o Skype for Business Server e a organização seja compatível com a telefonia).</span><span class="sxs-lookup"><span data-stu-id="d485d-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="d485d-111">As opções de telefonia do usuário do Skype for Business Server incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d485d-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="d485d-112">**Áudio/vídeo desabilitado** O usuário não pode fazer chamadas com áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="d485d-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="d485d-113">**PC para PC somente** O usuário pode fazer apenas chamadas de áudio e com vídeo para PC para PC.</span><span class="sxs-lookup"><span data-stu-id="d485d-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="d485d-114">**Enterprise Voice** O usuário pode usar a infraestrutura do Skype for Business Server para direcionar todas as chamadas de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="d485d-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="d485d-115">O usuário também pode fazer chamadas de PC para PC.</span><span class="sxs-lookup"><span data-stu-id="d485d-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="d485d-116">**Controle de chamada remota** O usuário pode usar o Skype for Business Server para controlar o telefone de mesa e também pode fazer chamadas de PC para PC.</span><span class="sxs-lookup"><span data-stu-id="d485d-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="d485d-117">Para obter detalhes sobre como configurar a telefonia de uma organização, consulte [habilitar usuários do Enterprise Voice no Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e [implantar o Enterprise Voice no Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="d485d-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="d485d-118">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d485d-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d485d-119">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d485d-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d485d-120">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="d485d-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d485d-121">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e clique em \*\*Localizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d485d-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="d485d-122">Na tabela, clique na conta de usuário que você deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="d485d-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="d485d-123">No menu **Editar** , clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="d485d-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="d485d-124">Em **telefonia**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d485d-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="d485d-125">Para desativar as chamadas de áudio e vídeo para o usuário, clique em **áudio/vídeo desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="d485d-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="d485d-126">Para habilitar as comunicações de áudio PC para PC para o usuário, mas não o controle de chamada remota ou o Enterprise Voice, clique em **PC para PC somente**.</span><span class="sxs-lookup"><span data-stu-id="d485d-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="d485d-127">Especifique um valor para o **URI da linha** para o telefone que o usuário usa para comunicações de áudio PC para PC.</span><span class="sxs-lookup"><span data-stu-id="d485d-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="d485d-128">Para encaminhar as chamadas telefônicas do usuário usando a infraestrutura do Skype for Business, de acordo com a classe de política de serviço, incluindo comunicação de áudio PC para PC, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="d485d-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="d485d-129">Em **URI da linha**, especifique o número de telefone do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d485d-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="d485d-130">Em **política de plano** de discagem e **política de voz**, especifique as políticas adequadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="d485d-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="d485d-131">Para especificar as regras de normalização para a tradução de números de telefone discados pelo usuário para o formato E. 164, selecione o perfil de localização apropriado na **política de localização**.</span><span class="sxs-lookup"><span data-stu-id="d485d-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="d485d-132">Para habilitar o controle de chamada remota, que permite que os usuários controlem a linha de telefone da área de trabalho do Skype for Business Server para fazer chamadas de PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**.</span><span class="sxs-lookup"><span data-stu-id="d485d-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="d485d-133">Em **URI de linha**, especifique o número de telefone para o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="d485d-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="d485d-134">O usuário deve ter uma conexão de telefone de mesa e PBX (Private Branch Exchange) para roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="d485d-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="d485d-135">Mover usuários para outro pool</span><span class="sxs-lookup"><span data-stu-id="d485d-135">Move users to another pool</span></span>
<span data-ttu-id="d485d-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="d485d-136"></span></span>

<span data-ttu-id="d485d-137">Você pode usar o painel de controle do Skype for Business Server para atribuir usuários a um servidor ou pool específico.</span><span class="sxs-lookup"><span data-stu-id="d485d-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="d485d-138">Mover todos os usuários existentes de um pool de origem que esteja executando o Lync Server 2010 ou anterior para um pool de destino do Skype for Business Server em um ambiente do Active Directory complexo pode resultar em uma replicação mais lenta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d485d-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="d485d-139">Para evitar isso, você pode usar filtros de pesquisa para mover os usuários de pools que executam o Lync Server 2010 ou anterior separadamente, ou pode usar o Shell de gerenciamento do Skype for Business Server para mover usuários com cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d485d-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="d485d-140">Além disso, a funcionalidade de filtro funciona com usuários do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d485d-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="d485d-141">Para mover os usuários selecionados para um servidor ou pool diferente</span><span class="sxs-lookup"><span data-stu-id="d485d-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="d485d-142">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d485d-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d485d-143">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d485d-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d485d-144">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="d485d-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d485d-145">Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e clique em \*\*Localizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d485d-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="d485d-146">Na tabela, selecione um usuário ou usuários específicos na lista.</span><span class="sxs-lookup"><span data-stu-id="d485d-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="d485d-147">No menu **ação** , clique em **mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="d485d-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="d485d-148">Em **mover usuários**, selecione o pool para o qual você deseja mover os usuários no **pool**de registradores de destino.</span><span class="sxs-lookup"><span data-stu-id="d485d-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="d485d-149">Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .</span><span class="sxs-lookup"><span data-stu-id="d485d-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="d485d-150">Se você selecionar **forçar**, a conta do usuário será movida, mas todos os dados do usuário associados serão excluídos (por exemplo, conferências que o usuário agendou).</span><span class="sxs-lookup"><span data-stu-id="d485d-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="d485d-151">Se você não selecioná-lo, a conta e os dados associados serão movidos.</span><span class="sxs-lookup"><span data-stu-id="d485d-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="d485d-152">Para mover todos os usuários de um servidor ou pool para um servidor ou pool diferente</span><span class="sxs-lookup"><span data-stu-id="d485d-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="d485d-153">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d485d-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d485d-154">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d485d-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d485d-155">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="d485d-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d485d-156">No menu **ação** , clique em **mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="d485d-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="d485d-157">Em **mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool**de registradores de origem.</span><span class="sxs-lookup"><span data-stu-id="d485d-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="d485d-158">No **pool**de registradores de destino, selecione o pool para o qual você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="d485d-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="d485d-159">Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .</span><span class="sxs-lookup"><span data-stu-id="d485d-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="d485d-160">Se você selecionar **forçar**, a conta do usuário será movida, mas todos os dados do usuário associados serão excluídos (por exemplo, conferências que o usuário agendou).</span><span class="sxs-lookup"><span data-stu-id="d485d-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="d485d-161">Se você não selecioná-lo, a conta e os dados associados serão movidos.</span><span class="sxs-lookup"><span data-stu-id="d485d-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="d485d-162">Para mover os usuários de um pool para um pool diferente usando um filtro</span><span class="sxs-lookup"><span data-stu-id="d485d-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="d485d-163">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d485d-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d485d-164">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d485d-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d485d-165">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="d485d-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d485d-166">Em **pesquisa de usuário**, clique em **Pesquisar**e, em seguida, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="d485d-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="d485d-167">Nos critérios de pesquisa, selecione **pool**de registradores, selecione **igual a**, selecione o **FQDN do pool atual**e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="d485d-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="d485d-168">No menu **ação** , clique em **mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="d485d-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d485d-169">Quando um filtro é aplicado a um conjunto de usuários existente, a opção **mover todos os usuários para o pool** está no contexto do subconjunto filtrado de usuários, e não **todos** os usuários possíveis.</span><span class="sxs-lookup"><span data-stu-id="d485d-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="d485d-170">Em **mover usuários**, selecione o pool que contém as contas de usuário que você deseja mover no **pool**de registradores de origem.</span><span class="sxs-lookup"><span data-stu-id="d485d-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="d485d-171">No **pool**de registradores de destino, selecione o pool para o qual você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="d485d-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="d485d-172">Adicionais Se o servidor ou o pool de destino não estiver disponível, marque a caixa de seleção **forçar** .</span><span class="sxs-lookup"><span data-stu-id="d485d-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="d485d-173">Se você selecionar **forçar**, a conta do usuário será movida, mas todos os dados do usuário associados serão excluídos (por exemplo, conferências que o usuário agendou e os contatos).</span><span class="sxs-lookup"><span data-stu-id="d485d-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="d485d-174">Se você não selecioná-lo, a conta e os dados associados serão movidos.</span><span class="sxs-lookup"><span data-stu-id="d485d-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="d485d-175">Para mover os usuários de um pool para outro usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d485d-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="d485d-176">Dependendo de como você executa comandos do Windows PowerShell (ou seja, local ou remotamente), você precisa fazer logon como membro das funções administrativas corretas do Skype for Business Server da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="d485d-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="d485d-177">a.</span><span class="sxs-lookup"><span data-stu-id="d485d-177">a.</span></span> <span data-ttu-id="d485d-178">Se você estiver executando os comandos no computador local (por exemplo, você fizer logon diretamente em um servidor front-end): faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com o necessário direitos de usuário, conforme descrito em **permissões de configuração de representante**.</span><span class="sxs-lookup"><span data-stu-id="d485d-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="d485d-179">b.</span><span class="sxs-lookup"><span data-stu-id="d485d-179">b.</span></span> <span data-ttu-id="d485d-180">Se você estiver executando os comandos remotamente em outro computador (por exemplo, se conectar ao seu computador e executar os comandos remotamente em um servidor front-end Standard Edition): de uma conta de usuário atribuída à função CsUserAdministrator ou ao CsAdministrator , faça logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d485d-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d485d-181">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="d485d-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="d485d-182">Para mover usuários únicos, use o cmdlet Move-CsUser da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d485d-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="d485d-183">Onde o usuário mover é o usuário pilar Alverca, e o usuário será movido do pool inicial atribuído no momento para o pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d485d-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="d485d-184">Para mover um grande número de usuários, use filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **mover-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="d485d-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="d485d-185">Os comandos combinados do **Get-CsUser** e do **move-CsUser** podem fazer isso:</span><span class="sxs-lookup"><span data-stu-id="d485d-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


