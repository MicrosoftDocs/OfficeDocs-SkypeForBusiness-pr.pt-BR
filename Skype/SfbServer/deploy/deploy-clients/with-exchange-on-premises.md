---
title: Implantar o Skype Room Systems versão 2 com o Exchange no local
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 em um ambiente híbrido com o Exchange no local.
ms.openlocfilehash: 930cc8916459562af89c15aefb60a2bf2c33c7e4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965447"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="188a0-103">Implantar o Skype Room Systems versão 2 com o Exchange no local</span><span class="sxs-lookup"><span data-stu-id="188a0-103">Deploy Skype Room Systems v2 with Exchange on premises</span></span>
 
<span data-ttu-id="188a0-104">Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 em um ambiente híbrido com o Exchange no local e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="188a0-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises and Skype for Business Online.</span></span>
  
<span data-ttu-id="188a0-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="188a0-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="188a0-106">Este tópico aborda as implantações híbridas para sistemas de sala Skype v2 com o Exchange hospedado no local.</span><span class="sxs-lookup"><span data-stu-id="188a0-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="188a0-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="188a0-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="188a0-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="188a0-108">The following process will work for many configurations.</span></span> <span data-ttu-id="188a0-109">Se o processo não é ideal para sua instalação, é recomendável usar o Windows PowerShell para obter o mesmo resultado final conforme documentadas aqui e para obter outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="188a0-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span> 

<span data-ttu-id="188a0-110">A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de v2 Skype sala sistemas compatíveis.</span><span class="sxs-lookup"><span data-stu-id="188a0-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="188a0-111">Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo v2 de sistemas de sala Skype usará.</span><span class="sxs-lookup"><span data-stu-id="188a0-111">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="188a0-112">Implantar o Skype Room Systems versão 2 com o Exchange no local</span><span class="sxs-lookup"><span data-stu-id="188a0-112">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="188a0-113">Antes de implantar sistemas de sala Skype v2 com o Exchange no local, certifique-se de que você cumpre os requisitos.</span><span class="sxs-lookup"><span data-stu-id="188a0-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="188a0-114">Para obter mais informações, consulte [requisitos de v2 de sistemas de sala Skype](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="188a0-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="188a0-115">Se você estiver implantando v2 Skype sistemas de sala com o Exchange no local, você usará ferramentas administrativas do Active Directory para adicionar um endereço de email para sua conta de domínio local.</span><span class="sxs-lookup"><span data-stu-id="188a0-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="188a0-116">Essa conta será sincronizada com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="188a0-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="188a0-117">Você deverá:</span><span class="sxs-lookup"><span data-stu-id="188a0-117">You will need to:</span></span>
  
- <span data-ttu-id="188a0-118">Criar uma conta e sincronizá-la com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="188a0-118">Create an account and synchronize the account with Active Directory.</span></span>
    
- <span data-ttu-id="188a0-119">Habilitar a caixa de correio remota e as propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="188a0-119">Enable the remote mailbox and set properties.</span></span>
    
- <span data-ttu-id="188a0-120">Atribua uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="188a0-120">Assign an Office 365 license.</span></span>
    
- <span data-ttu-id="188a0-121">Habilite a conta de dispositivo com Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="188a0-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="188a0-122">Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="188a0-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>
    
  - <span data-ttu-id="188a0-123">Você precisará ter Skype para negócios Online (plano 2) ou superior no seu plano do Office 365.</span><span class="sxs-lookup"><span data-stu-id="188a0-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="188a0-124">O plano precisa dar suporte à funcionalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="188a0-124">The plan needs to support conferencing capability.</span></span>
    
  - <span data-ttu-id="188a0-125">Se precisar de Enterprise Voice (telefonia PSTN) usando os provedores de serviços de telefonia para sistemas de sala Skype v2 será necessário Skype para Business Online (plano 3).</span><span class="sxs-lookup"><span data-stu-id="188a0-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
  - <span data-ttu-id="188a0-126">Os usuários de Inquilino devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="188a0-126">Your tenant users must have Exchange mailboxes.</span></span>
    
  - <span data-ttu-id="188a0-127">Sua conta de v2 de sistemas de sala Skype exigir um Skype para negócios Online (plano 2) ou Skype licença Business Online (plano 3), mas ele não requer uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="188a0-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
- <span data-ttu-id="188a0-128">Atribua um Skype licença Business Server à sua conta de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="188a0-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="188a0-129">Criar uma conta e sincronizá-la com o Active Directory</span><span class="sxs-lookup"><span data-stu-id="188a0-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="188a0-130">Na ferramenta de **usuários do Active Directory e computadores AD** , clique com botão direito na pasta ou unidade organizacional que seus sistemas de sala Skype v2 contas serão criadas, clique em **novo**e, em seguida, clique em **usuário**.</span><span class="sxs-lookup"><span data-stu-id="188a0-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>
    
2. <span data-ttu-id="188a0-p107">Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="188a0-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
    
3. <span data-ttu-id="188a0-p108">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="188a0-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="188a0-136">Selecionando a **senha nunca expira** é um requisito para Skype para Business Server em sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="188a0-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="188a0-137">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="188a0-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="188a0-138">Nesse caso, você precisará criar uma exceção para cada conta de dispositivo v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="188a0-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="188a0-139">Depois de criar a conta, execute a sincronização do diretório.</span><span class="sxs-lookup"><span data-stu-id="188a0-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="188a0-140">Quando ele estiver concluído, vá para a página de usuários no seu centro de administração do Office 365 e verifique se a conta criada nas etapas anteriores mesclada para online.</span><span class="sxs-lookup"><span data-stu-id="188a0-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="188a0-141">Habilitar a caixa de correio remota e as propriedades definidas</span><span class="sxs-lookup"><span data-stu-id="188a0-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="188a0-142">Habilitar a caixa de correio remota abrindo o shell de gerenciamento do Exchange no local com permissões de administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="188a0-142">Enable the remote mailbox by opening your on-premises Exchange management shell with administrator permissions and run the following command:</span></span>
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. <span data-ttu-id="188a0-143">Iniciar uma sessão remota do Windows PowerShell e se conectar ao Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="188a0-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span></span> <span data-ttu-id="188a0-144">A partir de seu locatário do Office 365, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="188a0-144">From your Office 365 tenant, run the following commands:</span></span>
    
   ```
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess = New-PSSession -ConfigurationName Microsoft.Exchange -Credential $cred -AllowRedirection -Authentication Basic -ConnectionUri "https://<ExchangeServerFQDN>/PowerShell"
   Import-PSSession $sess
   ```

3. <span data-ttu-id="188a0-145">Para melhorar a experiência de reunião, você precisará definir as propriedades do Exchange na conta do dispositivo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="188a0-145">To improve the meeting experience, you'll need to set the Exchange properties on the device account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    <span data-ttu-id="188a0-146">Para obter mais informações sobre quais propriedades, você precisa definir, consulte as propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="188a0-146">For more information about which properties you need to set, see Exchange properties.</span></span>
    
4. <span data-ttu-id="188a0-147">Você deverá conectar-se ao Azure AD para aplicar algumas configurações à conta.</span><span class="sxs-lookup"><span data-stu-id="188a0-147">You will need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="188a0-148">Você pode executar este comando para se conectar:</span><span class="sxs-lookup"><span data-stu-id="188a0-148">You can run this command to connect:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a><span data-ttu-id="188a0-149">Atribuir uma licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="188a0-149">Assign an Office 365 license</span></span>

1. <span data-ttu-id="188a0-150">A conta do dispositivo precisa ter uma licença válida do Office 365 para garantir que Exchange e Skype para Business Server funcionará.</span><span class="sxs-lookup"><span data-stu-id="188a0-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="188a0-151">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="188a0-151">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="188a0-152">Em seguida, use o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="188a0-152">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
    
3. <span data-ttu-id="188a0-p114">Depois de listar as SKUs, você poderá adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="188a0-p114">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="188a0-155">Habilitar a conta de dispositivo com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="188a0-155">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="188a0-156">Crie uma sessão remota do Windows PowerShell de um PC, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="188a0-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="188a0-157">Para habilitar sua conta do Skype sala sistemas v2 para Skype para Business Server, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="188a0-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="188a0-158">Se você não tiver certeza sobre qual valor usar para o parâmetro RegistrarPool no seu ambiente, você pode obter o valor de um existente Skype para usuário Business Server usando este comando</span><span class="sxs-lookup"><span data-stu-id="188a0-158">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="188a0-159">Atribuir uma licença do Skype for Business a sua conta do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="188a0-159">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="188a0-160">Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.</span><span class="sxs-lookup"><span data-stu-id="188a0-160">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="188a0-161">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="188a0-161">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="188a0-162">Clique na conta de sistemas de sala Skype v2 e, em seguida, clique no ícone de caneta para editar as informações de conta.</span><span class="sxs-lookup"><span data-stu-id="188a0-162">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="188a0-163">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="188a0-163">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="188a0-164">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="188a0-164">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="188a0-165">Você terá que usar uma licença de plano 3 se você quiser usar o Enterprise Voice em sua v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="188a0-165">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
    
6. <span data-ttu-id="188a0-166">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="188a0-166">Click **Save**.</span></span>
    
<span data-ttu-id="188a0-167">Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para fazer logon conta.</span><span class="sxs-lookup"><span data-stu-id="188a0-167">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="188a0-168">Consulte também</span><span class="sxs-lookup"><span data-stu-id="188a0-168">See also</span></span>

[<span data-ttu-id="188a0-169">Configurar contas para sistemas de sala Skype v2</span><span class="sxs-lookup"><span data-stu-id="188a0-169">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="188a0-170">Planejar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="188a0-170">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="188a0-171">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="188a0-171">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="188a0-172">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="188a0-172">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="188a0-173">Gerenciar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="188a0-173">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

