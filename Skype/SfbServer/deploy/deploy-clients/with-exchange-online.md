---
title: Implantar o Skype Room Systems versão 2 com o Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 com o Exchange Online.
ms.openlocfilehash: 51a1f4089dfb3453802e8d3241869c3c325c904c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883241"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="dad9c-103">Implantar o Skype Room Systems versão 2 com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dad9c-103">Deploy Skype Room Systems v2 with Exchange Online</span></span> 
 
<span data-ttu-id="dad9c-104">Leia este tópico para obter informações sobre como implantar v2 de sistemas de sala Skype com o Exchange Online e Skype para Business Server local.</span><span class="sxs-lookup"><span data-stu-id="dad9c-104">Read this topic for information on how to deploy Skype Room Systems v2 with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="dad9c-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="dad9c-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="dad9c-106">Este tópico aborda as implantações híbridas para sistemas de sala Skype v2 com o Exchange hospedado online.</span><span class="sxs-lookup"><span data-stu-id="dad9c-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted online.</span></span> <span data-ttu-id="dad9c-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="dad9c-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="dad9c-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="dad9c-108">The following process will work for many configurations.</span></span> <span data-ttu-id="dad9c-109">Se o processo não é ideal para sua instalação, é recomendável usar o Windows PowerShell para obter o mesmo resultado final conforme documentadas aqui e para obter outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="dad9c-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> 

<span data-ttu-id="dad9c-110">A maneira mais fácil de configurar as contas de usuário é configurá-los usando o Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="dad9c-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="dad9c-111">A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de v2 Skype sala sistemas compatíveis.</span><span class="sxs-lookup"><span data-stu-id="dad9c-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="dad9c-112">Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo v2 de sistemas de sala Skype usará.</span><span class="sxs-lookup"><span data-stu-id="dad9c-112">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a><span data-ttu-id="dad9c-113">Implantar o Skype Room Systems versão 2 com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dad9c-113">Deploy Skype Room Systems v2 with Exchange Online</span></span>

<span data-ttu-id="dad9c-114">Antes de implantar sistemas de sala Skype v2 com o Exchange Online, certifique-se de que você cumpre os requisitos.</span><span class="sxs-lookup"><span data-stu-id="dad9c-114">Before you deploy Skype Room Systems v2 with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="dad9c-115">Para obter mais informações, consulte [requisitos de v2 de sistemas de sala Skype](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dad9c-115">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="dad9c-116">Para implantar sistemas de sala Skype v2 com o Exchange Online, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="dad9c-116">To deploy Skype Room Systems v2 with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="dad9c-117">Verifique se você tem as permissões apropriadas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="dad9c-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="dad9c-118">Criar uma conta e definir as propriedades do Exchange</span><span class="sxs-lookup"><span data-stu-id="dad9c-118">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="dad9c-119">Iniciar uma sessão remota do Windows PowerShell em um PC e conecte-se ao Exchange Online da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dad9c-119">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. <span data-ttu-id="dad9c-120">Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="dad9c-120">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="dad9c-121">Isso permitirá a conta para se autenticar no v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="dad9c-121">This will allow the account to authenticate into Skype Room Systems v2.</span></span>
    
   <span data-ttu-id="dad9c-122">Se você alterar uma caixa de correio do recurso:</span><span class="sxs-lookup"><span data-stu-id="dad9c-122">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="dad9c-123">Se você estiver criando uma nova caixa de correio de recursos:</span><span class="sxs-lookup"><span data-stu-id="dad9c-123">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="dad9c-124">Para melhorar a experiência de reunião, você precisará definir as propriedades do Exchange na conta de usuário da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dad9c-124">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. <span data-ttu-id="dad9c-p106">Você deverá conectar-se ao Azure AD para aplicar algumas configurações à conta. Você poderá executar este cmdlet para se conectar.</span><span class="sxs-lookup"><span data-stu-id="dad9c-p106">You need to connect to Azure AD to apply some account settings. You can run this cmdlet to connect.</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="dad9c-127">Adicionar um endereço de e-mail à conta de domínio local</span><span class="sxs-lookup"><span data-stu-id="dad9c-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="dad9c-128">Na ferramenta de **usuários do Active Directory e computadores AD** , clique com botão direito na pasta ou unidade organizacional que seus sistemas de sala Skype v2 contas serão criadas, clique em **novo**e clique em **usuário**.</span><span class="sxs-lookup"><span data-stu-id="dad9c-128">In **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and the click **User**.</span></span>
    
2. <span data-ttu-id="dad9c-p107">Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dad9c-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>


3. <span data-ttu-id="dad9c-p108">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="dad9c-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dad9c-134">Selecionando a **senha nunca expira** é um requisito para Skype para Business Server em sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="dad9c-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="dad9c-135">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="dad9c-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="dad9c-136">Nesse caso, você precisará criar uma exceção para cada conta de usuário do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="dad9c-136">If so, you'll need to create an exception for each Skype Room Systems v2 user account.</span></span>
  
4. <span data-ttu-id="dad9c-137">Clique em **Concluir** para criar a conta.</span><span class="sxs-lookup"><span data-stu-id="dad9c-137">Click **Finish** to create the account.</span></span>
    
5. <span data-ttu-id="dad9c-p110">Depois de criar a conta, execute a sincronização do diretório. Depois de concluir, vá para a página de usuários e verifique se as duas contas criadas nas etapas anteriores foram mescladas.</span><span class="sxs-lookup"><span data-stu-id="dad9c-p110">After you've created the account, run a directory synchronization. When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>
    
### <a name="assign-an-office-365-license"></a><span data-ttu-id="dad9c-140">Atribuir uma licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="dad9c-140">Assign an Office 365 license</span></span>

1. <span data-ttu-id="dad9c-141">A conta de usuário precisa ter uma licença válida do Office 365 para garantir que Exchange e Skype para Business Server funcionará.</span><span class="sxs-lookup"><span data-stu-id="dad9c-141">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="dad9c-142">Se você tiver a licença, você precisa atribuir um local de uso para sua conta de usuário — Isso determina quais SKUs de licença estão disponíveis para sua conta.</span><span class="sxs-lookup"><span data-stu-id="dad9c-142">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="dad9c-143">Em seguida, use o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="dad9c-143">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="dad9c-p112">Depois de listar as SKUs, você poderá adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="dad9c-p112">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="dad9c-146">Habilitar a conta de usuário com Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="dad9c-146">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="dad9c-147">Crie uma sessão remota do Windows PowerShell de um PC, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="dad9c-147">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="dad9c-148">Para habilitar sua conta do Skype sala sistemas v2 para Skype para Business Server, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="dad9c-148">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="dad9c-149">Se você não tiver certeza sobre qual valor usar para o parâmetro RegistrarPool no seu ambiente, você pode obter o valor de um existente Skype para usuário Business Server usando este comando</span><span class="sxs-lookup"><span data-stu-id="dad9c-149">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="dad9c-150">Atribuir um Skype licença Business Server à sua conta de v2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="dad9c-150">Assign a Skype for Business Server license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="dad9c-151">Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.</span><span class="sxs-lookup"><span data-stu-id="dad9c-151">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="dad9c-152">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="dad9c-152">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="dad9c-153">Clique na conta de sistemas de sala Skype v2 e, em seguida, clique no ícone de caneta para editar as informações de conta.</span><span class="sxs-lookup"><span data-stu-id="dad9c-153">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="dad9c-154">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="dad9c-154">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="dad9c-155">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dad9c-155">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="dad9c-156">Você terá que usar uma licença de plano 3 se você quiser usar o Enterprise Voice em sua v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="dad9c-156">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="dad9c-157">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dad9c-157">Click **Save**.</span></span>
    
<span data-ttu-id="dad9c-158">Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para fazer logon conta.</span><span class="sxs-lookup"><span data-stu-id="dad9c-158">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dad9c-159">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dad9c-159">See also</span></span>

[<span data-ttu-id="dad9c-160">Configurar contas para sistemas de sala Skype v2</span><span class="sxs-lookup"><span data-stu-id="dad9c-160">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="dad9c-161">Planejar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="dad9c-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="dad9c-162">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="dad9c-162">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="dad9c-163">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="dad9c-163">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="dad9c-164">Gerenciar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="dad9c-164">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

