---
title: Habilitar usuários para o Enterprise Voice online e o sistema de telefonia no Office 365 caixa postal
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
description: Saiba como habilitar o sistema de telefonia nos serviços de voz do Office 365 para seus usuários do Skype for Business.
ms.openlocfilehash: ae1443fa0f0725b6cbbe722703f24af02139c12d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050193"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="4ee1f-103">Habilitar usuários para o Enterprise Voice online e o sistema de telefonia no Office 365 caixa postal</span><span class="sxs-lookup"><span data-stu-id="4ee1f-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="4ee1f-104">Saiba como habilitar o sistema de telefonia nos serviços de voz do Office 365 para seus usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="4ee1f-105">A etapa final na implantação do sistema de telefonia no Office 365 com conectividade PSTN local é habilitar os usuários para o sistema de telefonia no Office 365 e no correio de voz.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="4ee1f-106">Para habilitar esses recursos, você deve ser um usuário com a função de administrador global do Office 365 e poder executar o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="4ee1f-107">Você precisa seguir as etapas deste tópico para todas as contas de usuário que ainda não têm o Enterprise Voice habilitado para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="4ee1f-108">Habilitar o sistema de telefonia nos serviços de voz do Office 365</span><span class="sxs-lookup"><span data-stu-id="4ee1f-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="4ee1f-109">Para habilitar um usuário para o sistema de telefonia do Office 365 voz e correio de voz, você precisará executar algumas etapas iniciais, como verificar se o conector do Skype for Business online está implantado nos seus servidores e habilitar os usuários para caixa postal hospedada.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="4ee1f-110">Para habilitar os usuários para o sistema de telefonia no Office 365 voz e caixa postal</span><span class="sxs-lookup"><span data-stu-id="4ee1f-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="4ee1f-111">Antes de começar, verifique se o conector do Skype for Business online (módulo do Windows PowerShell) está implantado em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="4ee1f-112">Caso contrário, você pode baixá-lo do [centro de download](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="4ee1f-112">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="4ee1f-113">Você pode encontrar mais informações sobre como usar esse módulo em [Configurando o computador para o gerenciamento do Skype for Business online](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4ee1f-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="4ee1f-114">Inicie o Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="4ee1f-115">Digite o seguinte e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-115">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="4ee1f-116">Digite o seguinte e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-116">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="4ee1f-117">Após pressionar Enter, você deverá ver a caixa de diálogo de credenciais do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="4ee1f-118">Digite o nome de usuário e a senha do administrador do locatário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="4ee1f-119">Na janela do PowerShell, digite o seguinte e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="4ee1f-120">Importe a sessão digitando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-120">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="4ee1f-121">Ao executar o PowerShell em um Skype for Business Server, os cmdlets locais do Skype for Business já estão carregados quando você abre o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="4ee1f-122">Você deve especificar o parâmetro-AllowClobber para permitir que os cmdlets online substituam os cmdlets locais com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="4ee1f-123">Use o cmdlet Set-CsUser para atribuir as propriedades $EnterpriseVoiceEnabled e $HostedVoiceMail ao seu usuário da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="4ee1f-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-124">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="4ee1f-125">Você também pode especificar um usuário pelo endereço SIP, nome UPN, nome de domínio e nome de usuário (domínio \ nomedeusuário) e nome de exibição no Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="4ee1f-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="4ee1f-126">Atualizar o URI da linha e o plano de discagem para usuários habilitados para o sistema de telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="4ee1f-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="4ee1f-127">Esta seção descreve como atualizar o URI da linha e o plano de discagem para usuários habilitados para o sistema de telefonia no Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="4ee1f-128">Para atualizar o URI da linha</span><span class="sxs-lookup"><span data-stu-id="4ee1f-128">To update the Line URI</span></span>

1. <span data-ttu-id="4ee1f-129">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4ee1f-130">Use o menu iniciar ou o atalho da área de trabalho para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ee1f-131">Você também pode abrir uma janela do navegador e, em seguida, inserir a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="4ee1f-132">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="4ee1f-133">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="4ee1f-134">Na tabela, clique na conta de usuário do Skype for Business que você deseja alterar o URI da linha.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="4ee1f-135">Clique em **URI de linha**e digite um número de telefone normalizado exclusivo (por exemplo, Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="4ee1f-135">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="4ee1f-136">Em seguida, clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-136">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="4ee1f-137">Atualizar o plano de discagem usando cmdlets do Windows PowerShell no local</span><span class="sxs-lookup"><span data-stu-id="4ee1f-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4ee1f-138">Você pode atribuir planos de discagem por usuário com o Windows PowerShell e o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="4ee1f-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="4ee1f-139">Você pode executar esse cmdlet do Skype for Business Server 2015 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="4ee1f-140">Para atribuir um plano de discagem por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="4ee1f-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="4ee1f-141">Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para atribuir o plano de discagem por usuário RedmondDialPlan ao usuário Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="4ee1f-142">Para atribuir um plano de discagem por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="4ee1f-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="4ee1f-143">O comando a seguir atribui o plano de discagem por usuário RedmondDialPlan a todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="4ee1f-144">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="4ee1f-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="4ee1f-145">Você pode usar planos de discagem globais ou de usuário para usuários online.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-145">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="4ee1f-146">Os planos de discagem de site não podem ser usados, pois eles se aplicam a usuários que estão hospedados no local e são atribuídos a um site local.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-146">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="4ee1f-147">Para cancelar a atribuição de um plano de discagem por usuário</span><span class="sxs-lookup"><span data-stu-id="4ee1f-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="4ee1f-148">Use o cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para cancelar a atribuição de qualquer plano de discagem por usuário anteriormente atribuído a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="4ee1f-149">Após o plano de discagem por usuário não ser atribuído, Ken Myer será automaticamente gerenciado usando o plano de discagem global ou o plano de discagem de escopo de serviço atribuído ao seu registrador ou gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="4ee1f-150">Um plano de discagem de escopo de serviço tem precedência sobre o plano de discagem global:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="4ee1f-151">Atualizar as políticas de roteamento de voz usando cmdlets do Windows PowerShell no local</span><span class="sxs-lookup"><span data-stu-id="4ee1f-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4ee1f-152">Esta seção descreve como atualizar as políticas de roteamento de voz para usuários habilitados para o sistema de telefonia no Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="4ee1f-153">O sistema de telefonia nos usuários do Office 365 deve ter uma política de roteamento de voz atribuída a eles para chamadas de roteamento com êxito.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="4ee1f-154">Isso difere dos usuários do Business Voice no local que exigem que uma política de voz seja atribuída a eles para permitir que as chamadas sejam roteadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="4ee1f-155">A política de roteamento de voz deve conter usos de PSTN que definem chamadas e rotas autorizadas para o sistema de telefonia nos usuários do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="4ee1f-156">Você pode copiar esses usos de PSTN de políticas de voz existentes para novas políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="4ee1f-157">Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4ee1f-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ee1f-158">Todo o sistema de telefonia nos usuários do Office 365 recebe a mesma política de voz online denominada Businessvoice, que define os recursos de chamada permitidos; por exemplo, permita o toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="4ee1f-159">Para atribuir uma política de roteamento de voz por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="4ee1f-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="4ee1f-160">Use o cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para atribuir a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy ao usuário Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="4ee1f-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="4ee1f-161">Para atribuir uma política de roteamento de voz por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="4ee1f-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="4ee1f-162">O próximo comando atribui a política de roteamento de voz por usuário RedmondVoiceRoutingPolicy a todos os usuários que trabalham na cidade de Redmond.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="4ee1f-163">Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4ee1f-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="4ee1f-164">Você pode usar políticas globais ou de roteamento de voz do usuário para usuários online.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-164">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="4ee1f-165">As políticas de roteamento de voz do site não podem ser usadas, pois elas só se aplicam a usuários hospedados no local e são atribuídas a um site local.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-165">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="4ee1f-166">Para cancelar a atribuição de uma política de roteamento de voz por usuário</span><span class="sxs-lookup"><span data-stu-id="4ee1f-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="4ee1f-167">Use o Grant-CsVoiceRoutingPolicy para cancelar a atribuição de qualquer política de roteamento de voz por usuário anteriormente atribuída a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="4ee1f-168">Depois que a política de roteamento de voz por usuário é desatribuída, Ken Myer será automaticamente gerenciado usando a política de roteamento de voz global.</span><span class="sxs-lookup"><span data-stu-id="4ee1f-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="4ee1f-169">Para obter mais informações, consulte [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4ee1f-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

