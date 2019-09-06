---
title: Implantar as Salas do Microsoft Teams com o Exchange Online
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Exchange Online.
ms.openlocfilehash: d2e410eeb04ac65f7fc458bc6c1d8e67579c0f8b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774930"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="90b45-103">Implantar as Salas do Microsoft Teams com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="90b45-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="90b45-104">Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams com o Exchange Online e o Skype for Business Server no local.</span><span class="sxs-lookup"><span data-stu-id="90b45-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="90b45-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="90b45-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="90b45-106">Este tópico aborda implantações híbridas de salas do Microsoft Teams com o Exchange hospedado online.</span><span class="sxs-lookup"><span data-stu-id="90b45-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="90b45-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="90b45-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="90b45-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="90b45-108">The following process will work for many configurations.</span></span> <span data-ttu-id="90b45-109">Se o processo não está correto para a sua configuração, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final conforme documentado aqui e para outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="90b45-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="90b45-110">A maneira mais fácil de configurar contas de usuário é configurá-las usando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="90b45-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="90b45-111">A Microsoft fornece [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar as contas de recursos existentes que você tem para ajudar a transformá-las em contas de usuário compatíveis do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90b45-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="90b45-112">Se preferir, você pode seguir as etapas abaixo para configurar contas que o dispositivo de salas do Microsoft Teams vai usar.</span><span class="sxs-lookup"><span data-stu-id="90b45-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="90b45-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90b45-113">Requirements</span></span>

<span data-ttu-id="90b45-114">Antes de implantar salas do Microsoft Teams com o Exchange Online, verifique se você atendeu aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="90b45-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="90b45-115">Para obter mais informações, consulte [requisitos de salas do Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90b45-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="90b45-116">Para implantar salas do Microsoft Teams com o Exchange Online, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="90b45-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="90b45-117">Verifique se você tem as permissões apropriadas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="90b45-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="90b45-118">O [módulo do Azure Active Directory para cmdlets do Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) nesta seção (por exemplo, Set-MsolUser) foram testados na configuração de contas para dispositivos de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90b45-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="90b45-119">No entanto, é possível que outros cmdlets funcionem, mas não foram testados nesse cenário específico.</span><span class="sxs-lookup"><span data-stu-id="90b45-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="90b45-120">Criar uma conta e definir as propriedades do Exchange</span><span class="sxs-lookup"><span data-stu-id="90b45-120">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="90b45-121">Inicie uma sessão remota do Windows PowerShell em um computador e conecte-se ao Exchange Online da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="90b45-121">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. <span data-ttu-id="90b45-122">Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como uma RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="90b45-122">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="90b45-123">Isso permitirá que a conta seja autenticada em salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90b45-123">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="90b45-124">Se você alterar uma caixa de correio do recurso:</span><span class="sxs-lookup"><span data-stu-id="90b45-124">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="90b45-125">Se você estiver criando uma nova caixa de correio de recurso:</span><span class="sxs-lookup"><span data-stu-id="90b45-125">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="90b45-126">Para melhorar a experiência da reunião, você precisará definir as propriedades do Exchange na conta de usuário da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="90b45-126">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="90b45-127">Adicionar um endereço de e-mail à conta de domínio local</span><span class="sxs-lookup"><span data-stu-id="90b45-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="90b45-128">Na ferramenta **ad usuários e computadores do Active Directory** , clique com o botão direito do mouse no contêiner ou na unidade organizacional em que suas contas de sala do Microsoft Teams serão criadas, clique em **novo**e clique em **usuário**.</span><span class="sxs-lookup"><span data-stu-id="90b45-128">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="90b45-129">Digite o nome para exibição (-identidade) do cmdlet anterior (Set-Mailbox ou New-Mailbox) na caixa **nome completo** e o alias para a caixa **nome de logon do usuário** .</span><span class="sxs-lookup"><span data-stu-id="90b45-129">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="90b45-130">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="90b45-130">Click **Next**.</span></span>
3. <span data-ttu-id="90b45-p108">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="90b45-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90b45-134">Selecionar a **senha nunca expira** é um requisito para as salas do Skype for Business Server em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90b45-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="90b45-135">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="90b45-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="90b45-136">Em caso afirmativo, você precisará criar uma exceção para cada conta de usuário das salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90b45-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="90b45-137">Clique em **Concluir** para criar a conta.</span><span class="sxs-lookup"><span data-stu-id="90b45-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="90b45-138">Depois de criar a conta, execute uma sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="90b45-138">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="90b45-139">Isso pode ser feito usando [set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90b45-139">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="90b45-140">Quando concluir, vá para a página usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.</span><span class="sxs-lookup"><span data-stu-id="90b45-140">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="90b45-141">Atribuir uma licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="90b45-141">Assign an Office 365 license</span></span>

1. <span data-ttu-id="90b45-142">Primeiro, conecte-se ao Azure AD para aplicar algumas configurações de conta.</span><span class="sxs-lookup"><span data-stu-id="90b45-142">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="90b45-143">Você poderá executar este cmdlet para se conectar.</span><span class="sxs-lookup"><span data-stu-id="90b45-143">You can run this cmdlet to connect.</span></span> <span data-ttu-id="90b45-144">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="90b45-144">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="90b45-145">Não há suporte para o [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="90b45-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="90b45-146">A conta de usuário precisa ter uma licença válida do Office 365 para garantir que o Exchange e o Skype for Business Server funcionem.</span><span class="sxs-lookup"><span data-stu-id="90b45-146">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="90b45-147">Se você tiver a licença, será necessário atribuir um local de uso à sua conta de usuário — isso determina quais SKUs de licença estão disponíveis para a sua conta.</span><span class="sxs-lookup"><span data-stu-id="90b45-147">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="90b45-148">Você fará a atribuição em uma etapa seguinte.</span><span class="sxs-lookup"><span data-stu-id="90b45-148">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="90b45-149">Em seguida, use`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="90b45-149">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="90b45-150">para recuperar uma lista de SKUs disponíveis para o seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="90b45-150">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="90b45-151">Depois de listar os SKUs, você pode adicionar uma licença usando o botão`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="90b45-151">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="90b45-152">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="90b45-152">cmdlet.</span></span> <span data-ttu-id="90b45-153">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="90b45-153">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="90b45-154">Habilitar a conta de usuário com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="90b45-154">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="90b45-155">Crie uma sessão remota do Windows PowerShell a partir de um PC da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="90b45-155">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="90b45-156">Para habilitar a sua conta de salas do Microsoft Teams para o Skype for Business Server, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="90b45-156">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="90b45-157">Se não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, você pode obter o valor de um usuário existente do Skype for Business Server usando este comando</span><span class="sxs-lookup"><span data-stu-id="90b45-157">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="90b45-158">Atribuir uma licença do Skype for Business Server à sua conta de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90b45-158">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="90b45-159">Faça logon como administrador de locatários, abra o portal administrativo do Office 365 e clique no aplicativo de administração.</span><span class="sxs-lookup"><span data-stu-id="90b45-159">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="90b45-160">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="90b45-160">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="90b45-161">Clique na conta de salas do Microsoft Teams e, em seguida, clique no ícone de caneta para editar as informações da conta.</span><span class="sxs-lookup"><span data-stu-id="90b45-161">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="90b45-162">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="90b45-162">Click **Licenses**.</span></span>
5. <span data-ttu-id="90b45-163">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="90b45-163">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="90b45-164">Você precisará usar uma licença do plano 3 se quiser usar as salas do Enterprise Voice em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90b45-164">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="90b45-165">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="90b45-165">Click **Save**.</span></span>

<span data-ttu-id="90b45-166">Para a validação, você deve ser capaz de usar qualquer cliente Skype for Business para se conectar a esta conta.</span><span class="sxs-lookup"><span data-stu-id="90b45-166">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="90b45-167">Confira também</span><span class="sxs-lookup"><span data-stu-id="90b45-167">See also</span></span>

[<span data-ttu-id="90b45-168">Configurar contas para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90b45-168">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="90b45-169">Plano para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90b45-169">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="90b45-170">Implantar salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90b45-170">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="90b45-171">Configurar um console de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90b45-171">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="90b45-172">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90b45-172">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
