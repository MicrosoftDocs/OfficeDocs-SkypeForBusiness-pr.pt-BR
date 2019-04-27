---
title: Implantar salas de equipes da Microsoft com o Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar as salas de equipes da Microsoft com o Exchange Online.
ms.openlocfilehash: 1dc4e73fea7376033d8914cd1814e1edeb68e7d5
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362583"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="7ca66-103">Implantar salas de equipes da Microsoft com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7ca66-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="7ca66-104">Leia este tópico para obter informações sobre como implantar o Microsoft salas de equipes com o Exchange Online e Skype para Business Server local.</span><span class="sxs-lookup"><span data-stu-id="7ca66-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="7ca66-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="7ca66-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="7ca66-106">Este tópico aborda as implantações híbridas para salas de equipes da Microsoft com o Exchange hospedado online.</span><span class="sxs-lookup"><span data-stu-id="7ca66-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="7ca66-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="7ca66-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="7ca66-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="7ca66-108">The following process will work for many configurations.</span></span> <span data-ttu-id="7ca66-109">Se o processo não é ideal para sua instalação, é recomendável usar o Windows PowerShell para obter o mesmo resultado final conforme documentadas aqui e para obter outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="7ca66-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="7ca66-110">A maneira mais fácil de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="7ca66-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="7ca66-111">A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de salas de equipes da Microsoft compatíveis.</span><span class="sxs-lookup"><span data-stu-id="7ca66-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="7ca66-112">Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo de salas de equipes da Microsoft usará.</span><span class="sxs-lookup"><span data-stu-id="7ca66-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ca66-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ca66-113">Requirements</span></span>

<span data-ttu-id="7ca66-114">Antes de implantar salas de equipes da Microsoft com o Exchange Online, certifique-se de que você cumpre os requisitos.</span><span class="sxs-lookup"><span data-stu-id="7ca66-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="7ca66-115">Para obter mais informações, consulte [requisitos de salas de equipes da Microsoft](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ca66-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="7ca66-116">Para implantar as salas de equipes da Microsoft com o Exchange Online, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="7ca66-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="7ca66-117">Verifique se você tem as permissões apropriadas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="7ca66-117">Be sure you have the right permissions to run the associated cmdlets.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="7ca66-118">Criar uma conta e definir as propriedades do Exchange</span><span class="sxs-lookup"><span data-stu-id="7ca66-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="7ca66-119">Iniciar uma sessão remota do Windows PowerShell em um PC e conecte-se ao Exchange Online da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7ca66-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="7ca66-120">Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="7ca66-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="7ca66-121">Isso permitirá a conta autenticar em salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ca66-121">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="7ca66-122">Se você alterar uma caixa de correio do recurso:</span><span class="sxs-lookup"><span data-stu-id="7ca66-122">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="7ca66-123">Se você estiver criando uma nova caixa de correio de recursos:</span><span class="sxs-lookup"><span data-stu-id="7ca66-123">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="7ca66-124">Para melhorar a experiência de reunião, você precisará definir as propriedades do Exchange na conta de usuário da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7ca66-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="7ca66-125">Adicionar um endereço de e-mail à conta de domínio local</span><span class="sxs-lookup"><span data-stu-id="7ca66-125">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="7ca66-126">Na ferramenta de **usuários do Active Directory e computadores AD** , clique com botão direito no contêiner ou unidade organizacional que suas salas de equipes da Microsoft contas serão criadas, clique em **novo**e, em seguida, clique em **usuário**.</span><span class="sxs-lookup"><span data-stu-id="7ca66-126">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="7ca66-127">Digite o nome de exibição (-Identity) do cmdlet anterior (Set-Mailbox ou New-Mailbox) na caixa **nome completo** e o alias na caixa **nome de logon do usuário** .</span><span class="sxs-lookup"><span data-stu-id="7ca66-127">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="7ca66-128">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7ca66-128">Click **Next**.</span></span>
3. <span data-ttu-id="7ca66-p107">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="7ca66-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7ca66-132">Selecionando a **senha nunca expira** é um requisito para Skype para Business Server em salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ca66-132">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="7ca66-133">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="7ca66-133">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="7ca66-134">Nesse caso, você precisará criar uma exceção para cada conta de usuário de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ca66-134">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="7ca66-135">Clique em **Concluir** para criar a conta.</span><span class="sxs-lookup"><span data-stu-id="7ca66-135">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="7ca66-p109">Depois de criar a conta, execute a sincronização do diretório. Depois de concluir, vá para a página de usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.</span><span class="sxs-lookup"><span data-stu-id="7ca66-p109">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="7ca66-138">Atribuir uma licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="7ca66-138">Assign an Office 365 license</span></span>

1. <span data-ttu-id="7ca66-139">Primeiro, conecte-se para o Windows Azure AD para aplicar algumas configurações de conta.</span><span class="sxs-lookup"><span data-stu-id="7ca66-139">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="7ca66-140">Você poderá executar este cmdlet para se conectar.</span><span class="sxs-lookup"><span data-stu-id="7ca66-140">You can run this cmdlet to connect.</span></span>

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="7ca66-141">A conta de usuário precisa ter uma licença válida do Office 365 para garantir que Exchange e Skype para Business Server funcionará.</span><span class="sxs-lookup"><span data-stu-id="7ca66-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="7ca66-142">Se você tiver a licença, você precisa atribuir um local de uso para sua conta de usuário — Isso determina quais SKUs de licença estão disponíveis para sua conta.</span><span class="sxs-lookup"><span data-stu-id="7ca66-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="7ca66-143">Você vai fazer a atribuição em uma etapa a seguir.</span><span class="sxs-lookup"><span data-stu-id="7ca66-143">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="7ca66-144">Em seguida, usar`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="7ca66-144">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="7ca66-145">para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ca66-145">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="7ca66-146">Depois que você lista check-out SKUs do, você pode adicionar uma licença usando o`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="7ca66-146">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="7ca66-147">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7ca66-147">cmdlet.</span></span> <span data-ttu-id="7ca66-148">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="7ca66-148">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="7ca66-149">Habilitar a conta de usuário com Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7ca66-149">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="7ca66-150">Crie uma sessão remota do Windows PowerShell de um PC, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7ca66-150">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="7ca66-151">Para habilitar sua conta de salas de equipes da Microsoft para Skype para Business Server, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="7ca66-151">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="7ca66-152">Se você não tiver certeza sobre qual valor usar para o parâmetro RegistrarPool no seu ambiente, você pode obter o valor de um existente Skype para usuário Business Server usando este comando</span><span class="sxs-lookup"><span data-stu-id="7ca66-152">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="7ca66-153">Atribuir um Skype licença Business Server à sua conta de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ca66-153">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="7ca66-154">Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.</span><span class="sxs-lookup"><span data-stu-id="7ca66-154">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="7ca66-155">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="7ca66-155">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="7ca66-156">Clique na conta de salas de equipes da Microsoft e clique no ícone de caneta para editar as informações de conta.</span><span class="sxs-lookup"><span data-stu-id="7ca66-156">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="7ca66-157">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="7ca66-157">Click **Licenses**.</span></span>
5. <span data-ttu-id="7ca66-158">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7ca66-158">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="7ca66-159">Você terá que usar uma licença de plano 3 se você quiser usar o Enterprise Voice em salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ca66-159">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="7ca66-160">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7ca66-160">Click **Save**.</span></span>

<span data-ttu-id="7ca66-161">Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para fazer logon conta.</span><span class="sxs-lookup"><span data-stu-id="7ca66-161">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ca66-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="7ca66-162">See also</span></span>

[<span data-ttu-id="7ca66-163">Configurar contas para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ca66-163">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="7ca66-164">Planejar para salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ca66-164">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="7ca66-165">Implantar salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ca66-165">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="7ca66-166">Configurar um console de salas de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ca66-166">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="7ca66-167">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7ca66-167">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
