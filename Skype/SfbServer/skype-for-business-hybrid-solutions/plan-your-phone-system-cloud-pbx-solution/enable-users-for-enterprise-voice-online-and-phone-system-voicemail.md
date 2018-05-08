---
title: Habilitar usuários para Enterprise Voice online e o sistema telefônico no correio de voz do Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Aprenda a habilitar o sistema telefônico nos serviços de voz do Office 365 para sua Skype para usuários comerciais.
ms.openlocfilehash: 1810be3f891e1f66e724133732ed16e94a1d8015
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="d41fc-103">Habilitar usuários para Enterprise Voice online e o sistema telefônico no correio de voz do Office 365</span><span class="sxs-lookup"><span data-stu-id="d41fc-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="d41fc-104">Aprenda a habilitar o sistema telefônico nos serviços de voz do Office 365 para sua Skype para usuários comerciais.</span><span class="sxs-lookup"><span data-stu-id="d41fc-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="d41fc-105">Implantar o sistema telefônico no Office 365 com conectividade PSTN de local a etapa final é habilitar os usuários para o sistema telefônico no Office 365 e caixa postal.</span><span class="sxs-lookup"><span data-stu-id="d41fc-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="d41fc-106">Para isso, você precisa ter a função Administrador Global do Office 365 e estar habilitado para a execução remota do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d41fc-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="d41fc-107">Siga as etapas neste tópico para todas as contas de usuário que ainda não têm o Enterprise Voice habilitado para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="d41fc-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="d41fc-108">Habilitar o sistema telefônico nos serviços de voz do Office 365</span><span class="sxs-lookup"><span data-stu-id="d41fc-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="d41fc-109">Para habilitar um usuário para o sistema telefônico no Office 365 Voice e caixa postal, você precisará executar algumas etapas iniciais, como verificação vejam do Skype para Business Connector Online é implantado em seus servidores e permitir que os usuários para caixa postal hospedada.</span><span class="sxs-lookup"><span data-stu-id="d41fc-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see of the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="d41fc-110">Para habilitar os usuários para o sistema telefônico no correio de voz e voz do Office 365</span><span class="sxs-lookup"><span data-stu-id="d41fc-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="d41fc-111">Antes de começar, verifique se o Skype para Business Online Connector (módulo do Windows PowerShell) é implantado em seus servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="d41fc-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="d41fc-112">Se não for, você pode baixá-lo no [Centro de download](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="d41fc-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="d41fc-113">Você pode encontrar mais informações sobre como usar este módulo em [Configurando o seu computador e Skype para gerenciamento de negócios Online](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d41fc-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="d41fc-114">Inicie o Windows PowerShell como um administrador.</span><span class="sxs-lookup"><span data-stu-id="d41fc-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="d41fc-115">Digite o seguinte e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="d41fc-115">Type the following and press Enter:</span></span>
    
  ```
  Import-Module skypeonlineconnector
  ```

4. <span data-ttu-id="d41fc-116">Digite o seguinte e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="d41fc-116">Type the following and press Enter:</span></span>
    
  ```
  $cred = Get-Credential
  ```

    <span data-ttu-id="d41fc-117">Após pressionar Enter, a caixa de diálogo Credenciais do Windows PowerShell será exibida.</span><span class="sxs-lookup"><span data-stu-id="d41fc-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="d41fc-118">Digite seu nome de usuário e sua senha de administrador de locatário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d41fc-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="d41fc-119">Na janela do PowerShell, digite o seguinte e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="d41fc-119">In the PowerShell window, type the following and press Enter:</span></span>
    
  ```
  $Session = New-CsOnlineSession -Credential $cred -Verbose
  ```

7. <span data-ttu-id="d41fc-120">Importe a sessão digitando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d41fc-120">Import the session by typing the following cmdlet:</span></span>
    
  ```
  Import-PSSession $Session -AllowClobber
  ```

    <span data-ttu-id="d41fc-121">Ao executar o PowerShell em um Skype para Business Server, o local Skype para negócios cmdlets já estão carregados quando você abre o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d41fc-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="d41fc-122">Você deve especificar o parâmetro - AllowClobber para permitir que os cmdlets on-line substituir os cmdlets no local com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="d41fc-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="d41fc-123">Use o cmdlet Set-CsUser para atribuir as propriedades $EnterpriseVoiceEnabled e $HostedVoiceMail ao usuário, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="d41fc-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    <span data-ttu-id="d41fc-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d41fc-124">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    > [!NOTE]
    > <span data-ttu-id="d41fc-125">Você também pode especificar um usuário pelo endereço SIP, nome de Usuário Principal (UPN), nome de domínio e nome e usuário (domínio\nome de usuário) e nome de exibição no Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="d41fc-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="d41fc-126">Atualizar o URI de linha e discagem plano para usuários habilitados para o sistema telefônico no Office 365</span><span class="sxs-lookup"><span data-stu-id="d41fc-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="d41fc-127">Esta seção descreve como atualizar o URI de linha e plano para usuários habilitados para o sistema telefônico no Office 365 de discagem.</span><span class="sxs-lookup"><span data-stu-id="d41fc-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="d41fc-128">Atualizar o URI da Linha</span><span class="sxs-lookup"><span data-stu-id="d41fc-128">To update the Line URI</span></span>

1. <span data-ttu-id="d41fc-129">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d41fc-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d41fc-130">Utilize o menu Iniciar ou o atalho na área de trabalho para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d41fc-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d41fc-131">Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d41fc-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="d41fc-132">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="d41fc-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d41fc-133">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="d41fc-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="d41fc-134">Na tabela, clique na conta de usuário do Skype for Business da qual deseja alterar o URI da linha.</span><span class="sxs-lookup"><span data-stu-id="d41fc-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="d41fc-p104">Clique em **URI da Linha**, digite um número de telefone único e normalizado (por exemplo, tel:+14255550200) e, em seguida, clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d41fc-p104">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="d41fc-137">Atualizar o plano de discagem usando cmdlets do Windows PowerShell local</span><span class="sxs-lookup"><span data-stu-id="d41fc-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d41fc-138">Você pode atribuir os planos de discagem com o Windows PowerShell e o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para por usuário.</span><span class="sxs-lookup"><span data-stu-id="d41fc-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d41fc-139">Você pode executar esse cmdlet do Skype para Business Server 2015 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d41fc-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="d41fc-140">Atribuir um plano de discagem por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="d41fc-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="d41fc-141">Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para atribuir o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="d41fc-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="d41fc-142">Atribuir um plano de discagem por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="d41fc-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="d41fc-143">Esse comando atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="d41fc-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="d41fc-144">Para obter mais informações sobre o parâmetro LdapFilter usada nesse comando, consulte a documentação para o cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="d41fc-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

  ```

> [!NOTE]
> <span data-ttu-id="d41fc-p107">Você pode usar planos de discagem globais ou do usuário para usuários online. Planos de discagem locais não podem ser usados, pois se aplicam somente a usuários hospedados no local e são atribuídos a um site local.</span><span class="sxs-lookup"><span data-stu-id="d41fc-p107">You may use either Global or User dial plans for online users. Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="d41fc-147">Retirar a atribuição de uma plano de discagem por usuário</span><span class="sxs-lookup"><span data-stu-id="d41fc-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="d41fc-148">Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para retirar a atribuição de qualquer plano de discagem por usuário previamente atribuído a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d41fc-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="d41fc-149">Depois que a atribuição do plano de discagem por usuário for cancelada, Ken Myer será automaticamente gerenciado com o uso do plano de discagem global ou do plano de discagem de escopo de serviço atribuído ao seu Registrador ou gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d41fc-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="d41fc-150">Um plano de discagem de escopo de serviço tem precedência sobre o plano de discagem global:</span><span class="sxs-lookup"><span data-stu-id="d41fc-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="d41fc-151">Atualizar as políticas de roteamento de voz usando cmdlets do Windows PowerShell no local</span><span class="sxs-lookup"><span data-stu-id="d41fc-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d41fc-152">Esta seção descreve como atualizar as políticas de roteamento de voz para usuários habilitados para o sistema telefônico no Office 365.</span><span class="sxs-lookup"><span data-stu-id="d41fc-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="d41fc-153">O sistema telefônico em usuários do Office 365 deve ter uma política de roteamento de voz atribuída a eles para chamadas rotear com êxito.</span><span class="sxs-lookup"><span data-stu-id="d41fc-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="d41fc-154">É diferente dos usuários de voz de negócios locais, que exigem que uma política de voz seja atribuída a eles para permitir o roteamento bem-sucedido das chamadas.</span><span class="sxs-lookup"><span data-stu-id="d41fc-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="d41fc-155">A política de roteamento de voz deve conter os usos de PSTN que definem chamadas autorizadas e rotas para o sistema telefônico no usuários do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d41fc-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="d41fc-156">Você pode copiar esses usos de PSTN de Políticas de voz existentes para as novas Políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="d41fc-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="d41fc-157">Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d41fc-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d41fc-158">Todos os sistema telefônico no Office 365 usuários recebem a mesma política de voz online chamado BusinessVoice que define os recursos de chamada permitidos; Por exemplo, permitir que o toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="d41fc-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="d41fc-159">Para atribuir uma política de roteamento de voz por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="d41fc-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="d41fc-160">Use o cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para atribuir a política de roteamento de voz RedmondVoiceRoutingPolicy por usuário ao usuário Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="d41fc-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="d41fc-161">Para atribuir uma política de roteamento de voz por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="d41fc-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="d41fc-162">O comando a seguir atribui a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy a todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="d41fc-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="d41fc-163">Para obter mais informações sobre o parâmetro LdapFilter usada nesse comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d41fc-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="d41fc-p111">Você pode usar políticas de roteamento de voz globais ou do usuário para usuários online. Políticas de roteamento de voz locais não podem ser usadas, pois se aplicam somente a usuários hospedados no local e são atribuídas a um site local.</span><span class="sxs-lookup"><span data-stu-id="d41fc-p111">You may use either Global or User voice routing policies for online users. Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="d41fc-166">Para retirar a atribuição de uma política de roteamento de voz por usuário</span><span class="sxs-lookup"><span data-stu-id="d41fc-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="d41fc-167">Use o Grant-CsVoiceRoutingPolicy para retirar a atribuição de qualquer política roteamento de voz por usuário previamente atribuída a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d41fc-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="d41fc-168">Depois que a atribuição da política de roteamento de voz por usuário for cancelada, Ken Myer será automaticamente gerenciado com o uso da política de roteamento de voz global.</span><span class="sxs-lookup"><span data-stu-id="d41fc-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="d41fc-169">Para obter mais informações, consulte [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d41fc-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

