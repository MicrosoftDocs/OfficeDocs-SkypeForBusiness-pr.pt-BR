---
title: Implantar as Salas do Microsoft Teams com o Exchange Online
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Exchange Online e Skype for Business Server local.
ms.openlocfilehash: 2f92f85ddf39c5e1a813492b3092eeeef9b77e4c
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796675"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="bea3a-103">Implantar as Salas do Microsoft Teams com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bea3a-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="bea3a-104">Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams com Exchange Online e Skype for Business Server local.</span><span class="sxs-lookup"><span data-stu-id="bea3a-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="bea3a-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="bea3a-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="bea3a-106">Este tópico aborda implantações híbridas para Salas do Microsoft Teams com Exchange hospedado online.</span><span class="sxs-lookup"><span data-stu-id="bea3a-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="bea3a-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="bea3a-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="bea3a-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="bea3a-108">The following process will work for many configurations.</span></span> <span data-ttu-id="bea3a-109">Se o processo não estiver correto para sua instalação, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final como documentado aqui e para outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="bea3a-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="bea3a-110">A maneira mais fácil de configurar contas de usuário é configurá-las usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bea3a-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="bea3a-111">A Microsoft [forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis Salas do Microsoft Teams usuário.</span><span class="sxs-lookup"><span data-stu-id="bea3a-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="bea3a-112">Se preferir, siga as etapas abaixo para configurar contas que seu Salas do Microsoft Teams dispositivo usará.</span><span class="sxs-lookup"><span data-stu-id="bea3a-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="bea3a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bea3a-113">Requirements</span></span>

<span data-ttu-id="bea3a-114">Antes de implantar Salas do Microsoft Teams com Exchange Online, certifique-se de ter atendido aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="bea3a-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="bea3a-115">Para obter mais informações, [consulte Salas do Microsoft Teams requisitos](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bea3a-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="bea3a-116">Para implantar Salas do Microsoft Teams com Exchange Online, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="bea3a-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="bea3a-117">Verifique se você tem as permissões apropriadas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="bea3a-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="bea3a-118">O módulo Azure Active Directory para [cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) Windows PowerShell nesta seção (por exemplo, Set-MsolUser) foi testado na configuração de contas para Salas do Microsoft Teams dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bea3a-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="bea3a-119">É possível que outros cmdlets funcionem, no entanto, eles não foram testados neste cenário específico.</span><span class="sxs-lookup"><span data-stu-id="bea3a-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="bea3a-120">Se você implantou os Serviços de Federação do Active Directory (AD FS), talvez seja necessário converter a conta de usuário em um usuário gerenciado antes de seguir essas etapas e converter o usuário de volta em um usuário federado depois de concluir essas etapas.</span><span class="sxs-lookup"><span data-stu-id="bea3a-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="bea3a-121">Criar uma conta e definir as propriedades do Exchange</span><span class="sxs-lookup"><span data-stu-id="bea3a-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="bea3a-122">Inicie uma sessão Windows PowerShell remota em um computador e conecte-se Exchange Online seguinte:</span><span class="sxs-lookup"><span data-stu-id="bea3a-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="bea3a-123">Depois de estabelecer uma sessão, você criará uma nova caixa de correio e a habilitará como RoomMailboxAccount ou alterará as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="bea3a-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="bea3a-124">Isso permitirá que a conta se autenture em Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bea3a-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="bea3a-125">Se você alterar uma caixa de correio do recurso:</span><span class="sxs-lookup"><span data-stu-id="bea3a-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="bea3a-126">Se você estiver criando uma nova caixa de correio de recurso:</span><span class="sxs-lookup"><span data-stu-id="bea3a-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="bea3a-127">Para melhorar a experiência de reunião, você precisará definir as propriedades Exchange na conta do usuário da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="bea3a-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="bea3a-128">Adicionar um endereço de e-mail à conta de domínio local</span><span class="sxs-lookup"><span data-stu-id="bea3a-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="bea3a-129">Na ferramenta AD Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse no contêiner ou unidade organizacional em que suas contas Salas do Microsoft Teams serão criadas, clique em Novo e em **Usuário**. </span><span class="sxs-lookup"><span data-stu-id="bea3a-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="bea3a-130">Digite o nome de exibição (- Identity ) do cmdlet anterior (Set-Mailbox ou New-Mailbox) na caixa **Nome** completo e o alias na caixa Nome de **logon do** usuário.</span><span class="sxs-lookup"><span data-stu-id="bea3a-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="bea3a-131">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bea3a-131">Click **Next**.</span></span>
3. <span data-ttu-id="bea3a-p108">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="bea3a-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bea3a-135">Selecionar **Senha nunca expira é** um requisito para Skype for Business Server no Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bea3a-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="bea3a-136">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="bea3a-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="bea3a-137">Em caso afirmado, você precisará criar uma exceção para cada Salas do Microsoft Teams de usuário.</span><span class="sxs-lookup"><span data-stu-id="bea3a-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="bea3a-138">Clique em **Concluir** para criar a conta.</span><span class="sxs-lookup"><span data-stu-id="bea3a-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="bea3a-139">Depois de criar a conta, execute uma sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="bea3a-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="bea3a-140">Isso pode ser feito usando [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bea3a-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="bea3a-141">Quando isso for concluído, vá para a página usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.</span><span class="sxs-lookup"><span data-stu-id="bea3a-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="bea3a-142">Atribuir uma Microsoft 365 ou Office 365 licença</span><span class="sxs-lookup"><span data-stu-id="bea3a-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="bea3a-143">Primeiro, conecte-se ao Azure AD para aplicar algumas configurações de conta.</span><span class="sxs-lookup"><span data-stu-id="bea3a-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="bea3a-144">Você poderá executar este cmdlet para se conectar.</span><span class="sxs-lookup"><span data-stu-id="bea3a-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="bea3a-145">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="bea3a-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="bea3a-146">Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="bea3a-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="bea3a-147">A conta de usuário precisa ter uma licença Microsoft 365 ou Office 365 para garantir que Exchange e Skype for Business Server funcionem.</span><span class="sxs-lookup"><span data-stu-id="bea3a-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="bea3a-148">Se você tiver a licença, precisará atribuir um local de uso à sua conta de usuário— isso determina quais SKUs de licença estão disponíveis para sua conta.</span><span class="sxs-lookup"><span data-stu-id="bea3a-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="bea3a-149">Você fará a atribuição em uma etapa a seguir.</span><span class="sxs-lookup"><span data-stu-id="bea3a-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="bea3a-150">Em seguida, use `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="bea3a-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="bea3a-151">para recuperar uma lista de SKUs disponíveis para sua Microsoft 365 ou Office 365 organização.</span><span class="sxs-lookup"><span data-stu-id="bea3a-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="bea3a-152">Depois de listar as SKUs, você pode adicionar uma licença usando o `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="bea3a-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="bea3a-153">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bea3a-153">cmdlet.</span></span> <span data-ttu-id="bea3a-154">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="bea3a-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="bea3a-155">Habilitar a conta de usuário com Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bea3a-155">Enable the user account with Skype for Business Server</span></span>

> [!NOTE]
> <span data-ttu-id="bea3a-156">Se você estiver configurando uma Salas do Teams apenas para participar Microsoft Teams reuniões, não será necessário fazer as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="bea3a-156">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="bea3a-157">As etapas a seguir só serão necessárias se você quiser habilitar o suporte para Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bea3a-157">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="bea3a-158">Crie uma sessão Windows PowerShell remota de um computador da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="bea3a-158">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="bea3a-159">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="bea3a-159">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="bea3a-160">Se você estiver usando a versão pública mais [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o conector Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="bea3a-160">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="bea3a-161">Para habilitar sua Salas do Microsoft Teams para Skype for Business Server, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="bea3a-161">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="bea3a-162">Se você não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, poderá obter o valor de um usuário Skype for Business Server existente usando este comando</span><span class="sxs-lookup"><span data-stu-id="bea3a-162">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="bea3a-163">Atribuir uma Skype for Business Server de usuário à sua conta Salas do Microsoft Teams de usuário</span><span class="sxs-lookup"><span data-stu-id="bea3a-163">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

> [!NOTE]
> <span data-ttu-id="bea3a-164">Se você estiver configurando uma Salas do Teams apenas para participar Microsoft Teams reuniões, não será necessário fazer as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="bea3a-164">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="bea3a-165">As etapas a seguir só serão necessárias se você quiser habilitar o suporte para Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bea3a-165">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="bea3a-166">Faça logoff como administrador de locatário, abra o Microsoft 365 de administração e clique no aplicativo Administrador.</span><span class="sxs-lookup"><span data-stu-id="bea3a-166">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="bea3a-167">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="bea3a-167">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="bea3a-168">Clique na Salas do Microsoft Teams e clique no ícone de caneta para editar as informações da conta.</span><span class="sxs-lookup"><span data-stu-id="bea3a-168">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="bea3a-169">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="bea3a-169">Click **Licenses**.</span></span>
5. <span data-ttu-id="bea3a-170">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bea3a-170">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="bea3a-171">Você terá que usar uma licença de Plano 3 se quiser usar Enterprise Voice em Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bea3a-171">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="bea3a-172">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bea3a-172">Click **Save**.</span></span>

<span data-ttu-id="bea3a-173">Para validação, você deve ser capaz de usar qualquer Skype for Business cliente para fazer logoff nessa conta.</span><span class="sxs-lookup"><span data-stu-id="bea3a-173">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="bea3a-174">Se você estiver usando atualmente SKUs E1, E3, E4 ou E5 com Skype for Business Plano 2 com Audioconferência ou com Sistema de Telefonia e um Plano de Chamada, eles continuarão a funcionar.</span><span class="sxs-lookup"><span data-stu-id="bea3a-174">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="bea3a-175">No entanto, você deve considerar a mudança para um modelo de licenciamento mais simples, conforme descrito [na atualização de](rooms-licensing.md)licenciamento Teams Sala de Reunião , após a expiração das licenças atuais.</span><span class="sxs-lookup"><span data-stu-id="bea3a-175">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bea3a-176">Se você estiver usando o Skype for Business Plano 2, só poderá usar o Salas do Microsoft Teams no modo Somente Skype for Business, o que significa que todas as reuniões serão Skype for Business reuniões.</span><span class="sxs-lookup"><span data-stu-id="bea3a-176">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="bea3a-177">Para habilitar sua sala de reunião para Microsoft Teams reuniões, recomendamos que você compre a Sala de Reunião de reunião.</span><span class="sxs-lookup"><span data-stu-id="bea3a-177">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bea3a-178">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bea3a-178">Related topics</span></span>

[<span data-ttu-id="bea3a-179">Configurar contas para Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bea3a-179">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="bea3a-180">Planejar as Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bea3a-180">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="bea3a-181">Implantar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bea3a-181">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="bea3a-182">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bea3a-182">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="bea3a-183">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bea3a-183">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
