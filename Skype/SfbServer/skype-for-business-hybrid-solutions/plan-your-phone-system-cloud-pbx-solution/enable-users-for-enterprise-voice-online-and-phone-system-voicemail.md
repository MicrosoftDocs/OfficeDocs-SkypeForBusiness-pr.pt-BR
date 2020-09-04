---
title: Habilitar os usuários do Enterprise Voice online e da Caixa Postal do Sistema de Telefone
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Saiba como habilitar os serviços de voz do sistema de telefonia para seus usuários do Skype for Business.
ms.openlocfilehash: ed5e571976a032facc70b2e602d4b0ea7fd01afc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359177"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="d5370-103">Habilitar os usuários do Enterprise Voice online e da Caixa Postal do Sistema de Telefone</span><span class="sxs-lookup"><span data-stu-id="d5370-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="d5370-104">O Skype for Business online será desativado no dia 31 de julho de 2021 depois do qual o serviço não estará mais acessível.</span><span class="sxs-lookup"><span data-stu-id="d5370-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="d5370-105">Além disso, a conectividade PSTN entre seu ambiente local por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business online não terá mais suporte.</span><span class="sxs-lookup"><span data-stu-id="d5370-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="d5370-106">Saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="d5370-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="d5370-107">Saiba como habilitar os serviços de voz do sistema de telefonia para seus usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d5370-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="d5370-108">A etapa final na implantação do sistema de telefonia com conectividade PSTN local é habilitar os usuários para o sistema de telefonia e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="d5370-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="d5370-109">Para habilitar esses recursos, você deve ser um usuário com a função de administrador global e poder executar o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="d5370-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="d5370-110">Você precisa seguir as etapas deste tópico para todas as contas de usuário que ainda não têm o Enterprise Voice habilitado para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="d5370-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="d5370-111">Habilitar serviços de voz do sistema de telefonia</span><span class="sxs-lookup"><span data-stu-id="d5370-111">Enable Phone System voice services</span></span>

<span data-ttu-id="d5370-112">Para habilitar um usuário para voz e caixa postal do sistema de telefonia, você precisará executar algumas etapas iniciais, como verificar se o conector do Skype for Business online está implantado nos seus servidores e habilitar os usuários para caixa postal hospedada.</span><span class="sxs-lookup"><span data-stu-id="d5370-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="d5370-113">Para habilitar os usuários para voz e caixa postal do sistema de telefonia</span><span class="sxs-lookup"><span data-stu-id="d5370-113">To enable your users for Phone System voice and voicemail</span></span>

1. <span data-ttu-id="d5370-114">Antes de começar, verifique se o conector do Skype for Business online (módulo do Windows PowerShell) está implantado em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d5370-114">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="d5370-115">Caso contrário, você pode baixá-lo do [centro de download](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="d5370-115">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="d5370-116">Você pode encontrar mais informações sobre como usar esse módulo em [Configurando o computador para o gerenciamento do Skype for Business online](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d5370-116">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="d5370-117">Inicie o Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="d5370-117">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="d5370-118">Digite o seguinte e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d5370-118">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="d5370-119">Digite o seguinte e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d5370-119">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="d5370-120">Após pressionar Enter, você deverá ver a caixa de diálogo de credenciais do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5370-120">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="d5370-121">Digite o nome de usuário e a senha do administrador do locatário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5370-121">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="d5370-122">Na janela do PowerShell, digite o seguinte e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="d5370-122">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="d5370-123">Importe a sessão digitando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d5370-123">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="d5370-124">Ao executar o PowerShell em um Skype for Business Server, os cmdlets locais do Skype for Business já estão carregados quando você abre o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5370-124">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="d5370-125">Você deve especificar o parâmetro-AllowClobber para permitir que os cmdlets online substituam os cmdlets locais com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="d5370-125">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="d5370-126">Use o cmdlet Set-CsUser para atribuir as propriedades $EnterpriseVoiceEnabled e $HostedVoiceMail ao seu usuário da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d5370-126">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="d5370-127">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5370-127">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="d5370-128">Você também pode especificar um usuário pelo endereço SIP, nome UPN, nome de domínio e nome de usuário (domínio \ nomedeusuário) e nome de exibição no Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="d5370-128">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="d5370-129">Atualizar o URI da linha e o plano de discagem para usuários habilitados para o sistema de telefonia</span><span class="sxs-lookup"><span data-stu-id="d5370-129">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="d5370-130">Esta seção descreve como atualizar o URI da linha e o plano de discagem para usuários habilitados para o sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="d5370-130">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="d5370-131">Para atualizar o URI da linha</span><span class="sxs-lookup"><span data-stu-id="d5370-131">To update the Line URI</span></span>

1. <span data-ttu-id="d5370-132">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d5370-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d5370-133">Use o menu iniciar ou o atalho da área de trabalho para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5370-133">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5370-134">Você também pode abrir uma janela do navegador e, em seguida, inserir a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5370-134">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="d5370-135">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="d5370-135">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d5370-136">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="d5370-136">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="d5370-137">Na tabela, clique na conta de usuário do Skype for Business que você deseja alterar o URI da linha.</span><span class="sxs-lookup"><span data-stu-id="d5370-137">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="d5370-138">Clique em **URI de linha**e digite um número de telefone normalizado exclusivo (por exemplo, Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="d5370-138">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="d5370-139">Em seguida, clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d5370-139">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="d5370-140">Atualizar o plano de discagem usando cmdlets do Windows PowerShell no local</span><span class="sxs-lookup"><span data-stu-id="d5370-140">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d5370-141">Você pode atribuir planos de discagem por usuário com o Windows PowerShell e o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d5370-141">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d5370-142">Você pode executar esse cmdlet do Skype for Business Server 2015 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5370-142">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="d5370-143">Para atribuir um plano de discagem por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="d5370-143">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="d5370-144">Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para atribuir o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="d5370-144">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="d5370-145">Para atribuir um plano de discagem por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="d5370-145">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="d5370-146">O comando a seguir atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="d5370-146">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="d5370-147">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="d5370-147">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="d5370-148">Você pode usar planos de discagem globais ou de usuário para usuários online.</span><span class="sxs-lookup"><span data-stu-id="d5370-148">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="d5370-149">Os planos de discagem de site não podem ser usados, pois eles se aplicam a usuários que estão hospedados no local e são atribuídos a um site local.</span><span class="sxs-lookup"><span data-stu-id="d5370-149">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="d5370-150">Para cancelar a atribuição de um plano de discagem por usuário</span><span class="sxs-lookup"><span data-stu-id="d5370-150">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="d5370-151">Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para cancelar a atribuição de qualquer plano de discagem por usuário anteriormente atribuído a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d5370-151">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="d5370-152">Após o plano de discagem por usuário não ser atribuído, Ken Myer será automaticamente gerenciado usando o plano de discagem global ou o plano de discagem de escopo de serviço atribuído ao seu registrador ou gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d5370-152">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="d5370-153">Um plano de discagem de escopo de serviço tem precedência sobre o plano de discagem global:</span><span class="sxs-lookup"><span data-stu-id="d5370-153">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="d5370-154">Atualizar as políticas de roteamento de voz usando cmdlets do Windows PowerShell no local</span><span class="sxs-lookup"><span data-stu-id="d5370-154">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d5370-155">Esta seção descreve como atualizar as políticas de roteamento de voz para usuários habilitados para o sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="d5370-155">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="d5370-156">Os usuários do sistema de telefonia precisam ter uma política de roteamento de voz atribuída a eles para que as chamadas sejam roteadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="d5370-156">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="d5370-157">Isso difere dos usuários do Business Voice no local que exigem que uma política de voz seja atribuída a eles para permitir que as chamadas sejam roteadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="d5370-157">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="d5370-158">A política de roteamento de voz deve conter usos de PSTN que definem chamadas e rotas autorizadas para usuários de sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="d5370-158">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="d5370-159">Você pode copiar esses usos de PSTN de políticas de voz existentes para novas políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="d5370-159">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="d5370-160">Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d5370-160">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d5370-161">Todos os usuários do sistema telefônico recebem a mesma política de voz online chamada Businessvoice,, que define os recursos de chamada permitidos; por exemplo, permita o toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="d5370-161">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="d5370-162">Para atribuir uma política de roteamento de voz por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="d5370-162">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="d5370-163">Use o cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para atribuir a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy ao usuário Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="d5370-163">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="d5370-164">Para atribuir uma política de roteamento de voz por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="d5370-164">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="d5370-165">O próximo comando atribui a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy a todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="d5370-165">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="d5370-166">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d5370-166">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="d5370-167">Você pode usar políticas globais ou de roteamento de voz do usuário para usuários online.</span><span class="sxs-lookup"><span data-stu-id="d5370-167">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="d5370-168">As políticas de roteamento de voz do site não podem ser usadas, pois elas só se aplicam a usuários hospedados no local e são atribuídas a um site local.</span><span class="sxs-lookup"><span data-stu-id="d5370-168">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="d5370-169">Para cancelar a atribuição de uma política de roteamento de voz por usuário</span><span class="sxs-lookup"><span data-stu-id="d5370-169">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="d5370-170">Use o Grant-CsVoiceRoutingPolicy para cancelar a atribuição de qualquer política de roteamento de voz por usuário anteriormente atribuída a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d5370-170">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="d5370-171">Depois que a política de roteamento de voz por usuário é desatribuída, Ken Myer será automaticamente gerenciado usando a política de roteamento de voz global.</span><span class="sxs-lookup"><span data-stu-id="d5370-171">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="d5370-172">Para obter mais informações, consulte [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d5370-172">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

