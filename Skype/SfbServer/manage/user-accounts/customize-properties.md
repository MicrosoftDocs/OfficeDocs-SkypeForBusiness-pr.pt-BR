---
title: Personalizar propriedades de conta de usuário para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Você pode usar os procedimentos neste seção para modificar as propriedades de conta de usuários individuais.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826261"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="a96c0-103">Personalizar propriedades de conta de usuário para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a96c0-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="a96c0-104">Você pode usar os procedimentos neste seção para modificar as propriedades de conta de usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="a96c0-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="a96c0-105">Há duas operações básicas que podem ser feitas no nível do usuário individual:</span><span class="sxs-lookup"><span data-stu-id="a96c0-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="a96c0-106">Configurar opções de telefonia para uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="a96c0-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="a96c0-107">Mover usuários para outro pool</span><span class="sxs-lookup"><span data-stu-id="a96c0-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="a96c0-108">Configurar opções de telefonia para uma conta de usuário específica</span><span class="sxs-lookup"><span data-stu-id="a96c0-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="a96c0-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="a96c0-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="a96c0-110">Você pode personalizar as configurações de telefonia para um usuário específico (desde que o usuário individual tenha sido habilitado para o Skype for Business Server e a organização suporte telefonia).</span><span class="sxs-lookup"><span data-stu-id="a96c0-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="a96c0-111">As opções de telefonia do usuário do Skype for Business Server incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a96c0-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="a96c0-112">**Áudio/vídeo desabilitado** O usuário não pode fazer chamadas com áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="a96c0-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="a96c0-113">**Somente pc-pc** O usuário só pode fazer chamadas de áudio ou vídeo pc-PC.</span><span class="sxs-lookup"><span data-stu-id="a96c0-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="a96c0-114">**Enterprise Voice** O usuário pode usar a infraestrutura do Skype for Business Server para rotear todas as chamadas de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="a96c0-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="a96c0-115">O usuário também pode fazer chamadas PC-PC.</span><span class="sxs-lookup"><span data-stu-id="a96c0-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="a96c0-116">**Controle de chamada remota** O usuário pode usar o Skype for Business Server para controlar o telefone de mesa e também pode fazer chamadas PC-PC.</span><span class="sxs-lookup"><span data-stu-id="a96c0-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="a96c0-117">Para obter detalhes sobre como configurar a telefonia para uma organização, consulte [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and Deploy Enterprise Voice in Skype for Business [Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="a96c0-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="a96c0-118">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a96c0-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a96c0-119">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a96c0-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a96c0-120">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a96c0-121">Na caixa **Pesquisar usuários**, digite toda ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta que deseja e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="a96c0-122">Na tabela, clique na conta de usuário que deseja modificar.</span><span class="sxs-lookup"><span data-stu-id="a96c0-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="a96c0-123">No menu **Editar**, clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="a96c0-124">Em **Telefonia**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a96c0-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="a96c0-125">Para desabilitar as chamadas de áudio e vídeo do usuário, clique em   **Áudio/vídeo desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="a96c0-p102">Para habilitar a comunicação de áudio PC-PC do usuário, mas não o controle de chamada remota ou o Enterprise Voice, clique em **Somente PC-PC**. Especifique um valor para **URI da Linha** para o telefone que o usuário usa para comunicações de áudio PC-PC.</span><span class="sxs-lookup"><span data-stu-id="a96c0-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="a96c0-128">Para rotear as chamadas telefônicas do usuário usando a infraestrutura do Skype for Business de acordo com a classe de política de serviço, incluindo a comunicação de áudio PC-PC, clique em **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="a96c0-129">Em   **URI da Linha**, especifique o número de telefone para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a96c0-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="a96c0-130">Em **Política de plano de discagem** e **Política de Voz**, especifique as políticas apropriadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="a96c0-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="a96c0-131">Para especificar as regras de normalização para conversão de números de telefone discados pelo usuário no formato E.164, selecione o perfil de local apropriado no em **Política de local**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="a96c0-132">Para habilitar o controle de chamada remota, que permite que os usuários controlem sua linha de telefone de mesa do Skype for Business Server para fazer chamadas pc-to-PC e chamadas pc-para-telefone, clique em Controle de chamada **remota.**</span><span class="sxs-lookup"><span data-stu-id="a96c0-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="a96c0-133">Em **URI da Linha**, especifique o número de telefone para o controle de chamada remota.</span><span class="sxs-lookup"><span data-stu-id="a96c0-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="a96c0-134">O usuário deve ter um telefone de mesa e a conexão PBX (central privada de comutação telefônica) para roteamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="a96c0-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="a96c0-135">Mover usuários para outro pool</span><span class="sxs-lookup"><span data-stu-id="a96c0-135">Move users to another pool</span></span>
<span data-ttu-id="a96c0-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="a96c0-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="a96c0-137">Você pode usar o Painel de Controle do Skype for Business Server para atribuir usuários a um servidor ou pool específico.</span><span class="sxs-lookup"><span data-stu-id="a96c0-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="a96c0-138">Mover todos os usuários existentes de um pool de origem que está executando o Lync Server 2010 ou anterior para um pool de destino do Skype for Business Server em um ambiente complexo do Active Directory pode resultar em replicação mais lenta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a96c0-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="a96c0-139">Para evitar isso, você pode usar filtros de pesquisa para mover usuários de pools que executam o Lync Server 2010 ou anterior separadamente, ou pode usar o Shell de Gerenciamento do Skype for Business Server para mover usuários com cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a96c0-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="a96c0-140">Além disso, a funcionalidade de filtro funciona com usuários do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a96c0-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="a96c0-141">Para mover os usuários selecionados para um outro servidor ou pool</span><span class="sxs-lookup"><span data-stu-id="a96c0-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="a96c0-142">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a96c0-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a96c0-143">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a96c0-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a96c0-144">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a96c0-145">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome de conta do SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) da linha da conta de usuário que você deseja e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="a96c0-146">Na tabela, selecione um usuário específico ou usuários na lista.</span><span class="sxs-lookup"><span data-stu-id="a96c0-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="a96c0-147">No menu **Ação**, clique em **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="a96c0-148">Em **Mover Usuários**, selecione o pool para o qual você deseja mover os usuários em **Pool de registradores de destino**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="a96c0-149">(Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a96c0-p106">Se você selecionar **Forçar**, a conta de usuário será movida, mas nenhum dado de usuário associado será excluído (por exemplo, conferências agendadas pelo usuário). Se essa opção não for selecionada, a conta e os dados associados serão movidos.</span><span class="sxs-lookup"><span data-stu-id="a96c0-p106">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="a96c0-152">Para mover todos os usuários de um servidor ou pool para outro servidor ou pool</span><span class="sxs-lookup"><span data-stu-id="a96c0-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="a96c0-153">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a96c0-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a96c0-154">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a96c0-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a96c0-155">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a96c0-156">No menu **Ação**, clique em **Mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="a96c0-157">Em **Mover Usuários**, selecione o pool que contenha as contas de usuário que você deseja mover no **Pool de registradores de origem**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="a96c0-158">Em **Pool de registradores de destino**, selecione o pool para o qual você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="a96c0-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="a96c0-159">(Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a96c0-p107">Se você selecionar **Forçar**, a conta de usuário será movida, mas nenhum dado de usuário associado será excluído (por exemplo, conferências agendadas pelo usuário). Se essa opção não for selecionada, a conta e os dados associados serão movidos.</span><span class="sxs-lookup"><span data-stu-id="a96c0-p107">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="a96c0-162">Para mover usuários de um pool para um pool diferente usando um filtro</span><span class="sxs-lookup"><span data-stu-id="a96c0-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="a96c0-163">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a96c0-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a96c0-164">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a96c0-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a96c0-165">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a96c0-166">Na **Pesquisa de Usuário,** clique **em Pesquisar** e em **Adicionar Filtro.**</span><span class="sxs-lookup"><span data-stu-id="a96c0-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="a96c0-167">Nos Critérios de pesquisa, selecione **Pool de Registradores**, selecione **Igual a**, selecione **FQDN Atual do Pool** e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="a96c0-168">No menu **Ação**, clique em **Mover todos os usuários para o pool**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a96c0-169">Quando um filtro é aplicado a um conjunto de usuário existente, a opção **Mover todos os usuários para o pool** está no contexto do subconjunto de usuários filtrados, não em **todos** os usuários possíveis.</span><span class="sxs-lookup"><span data-stu-id="a96c0-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="a96c0-170">Em **Mover Usuários**, selecione o pool que contenha as contas de usuário que você deseja mover no **Pool de registradores de origem**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="a96c0-171">Em **Pool de registradores de destino**, selecione o pool para o qual você deseja mover os usuários.</span><span class="sxs-lookup"><span data-stu-id="a96c0-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="a96c0-172">(Opcional) Se o pool ou o servidor de destino não estiver disponível, marque a caixa de seleção **Forçar**.</span><span class="sxs-lookup"><span data-stu-id="a96c0-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a96c0-p108">Se você selecionar **Forçar**, a conta de usuário será movida, mas nenhum dado de usuário associado será excluído (por exemplo, conferências agendadas pelo usuário e os contatos). Se essa opção não for selecionada, a conta e os dados associados serão movidos.</span><span class="sxs-lookup"><span data-stu-id="a96c0-p108">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="a96c0-175">Para mover usuários de um pool para outro usando cmdlets do Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="a96c0-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="a96c0-176">Dependendo de como você executar comandos do Windows PowerShell (ou seja, local ou remotamente), será necessário fazer logoff como membro das funções administrativas corretas do Skype for Business Server da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a96c0-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="a96c0-177">a.</span><span class="sxs-lookup"><span data-stu-id="a96c0-177">a.</span></span> <span data-ttu-id="a96c0-178">Se você estiver executando os comandos na máquina local (por exemplo, faça logon diretamente em um Servidor Front-End): faça logon no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .</span><span class="sxs-lookup"><span data-stu-id="a96c0-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="a96c0-179">b.</span><span class="sxs-lookup"><span data-stu-id="a96c0-179">b.</span></span> <span data-ttu-id="a96c0-180">Se você estiver executando os comandos remotamente em outro computador (por exemplo, faça logon em seu computador e execute os comandos remotamente em um Servidor Front End Standard Edition): de uma conta de usuário atribuída à função CsUserAdministrator ou à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a96c0-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a96c0-181">Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business** e no Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="a96c0-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a96c0-182">Para mover usuários único, use o cmdlet Move-CsUser da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a96c0-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="a96c0-183">Quando o usuário a ser movido for Pilar Ackerman, e for movido de seu pool doméstico atribuído atualmente para o pool pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a96c0-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="a96c0-184">Para mover muitos usuários, use os filtros com o cmdlet **Get-CsUser** e passe o conjunto resultante de usuários para **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="a96c0-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="a96c0-185">Os comandos combinados do **Get-CsUser** e do **Move-CsUser** devem resultar nisso:</span><span class="sxs-lookup"><span data-stu-id="a96c0-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


