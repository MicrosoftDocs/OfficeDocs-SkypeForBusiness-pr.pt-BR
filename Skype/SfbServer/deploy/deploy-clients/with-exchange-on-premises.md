---
title: Implantar o Skype Room Systems versão 2 com o Exchange no local (Híbrida)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: Leia este tópico para obter informações sobre como implantar o  em um ambiente híbrido com o  no local.
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a><span data-ttu-id="80575-103">Implantar o Skype Room Systems versão 2 com o Exchange no local (Híbrida)</span><span class="sxs-lookup"><span data-stu-id="80575-103">Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)</span></span>
 
<span data-ttu-id="80575-104">Leia este tópico para obter informações sobre como implantar o  em um ambiente híbrido com o  no local.</span><span class="sxs-lookup"><span data-stu-id="80575-104">Read this topic for information on how to deploy  in a hybrid environment with  on premises.</span></span>
  
<span data-ttu-id="80575-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="80575-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="80575-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span><span class="sxs-lookup"><span data-stu-id="80575-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="80575-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="80575-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="80575-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="80575-108">The following process will work for many configurations.</span></span> <span data-ttu-id="80575-109">Se ele não for adequado a sua configuração, recomendamos usar o  para obter o mesmo resultado final e para outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="80575-109">If the process isn't right for your setup, we recommend that you use  to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="80575-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span><span class="sxs-lookup"><span data-stu-id="80575-110">You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup.</span></span> <span data-ttu-id="80575-111">(Veja Script de verificação de conta.)</span><span class="sxs-lookup"><span data-stu-id="80575-111">(See Account Verification Script.)</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="80575-112">Implantar o Skype Room Systems versão 2 com o Exchange no local</span><span class="sxs-lookup"><span data-stu-id="80575-112">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="80575-113">Antes de implantar o  com o  no local, verifique se os requisitos foram atendidos.</span><span class="sxs-lookup"><span data-stu-id="80575-113">Before you deploy  with  on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="80575-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80575-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="80575-115">Se você estiver implantando o  com o  no local, usará as ferramentas administrativas do Active Directory para adicionar um endereço de email à conta de domínio local.</span><span class="sxs-lookup"><span data-stu-id="80575-115">If you are deploying  with  on premises,  you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="80575-116">Essa conta será sincronizada com o .</span><span class="sxs-lookup"><span data-stu-id="80575-116">This account will be synced to .</span></span> <span data-ttu-id="80575-117">Você deverá:</span><span class="sxs-lookup"><span data-stu-id="80575-117">You will need to:</span></span>
  
- <span data-ttu-id="80575-118">Criar uma conta e sincronizá-la com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="80575-118">Create an account and synchronize the account with Active Directory.</span></span>
    
- <span data-ttu-id="80575-119">Habilitar a caixa de correio remota e as propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="80575-119">Enable the remote mailbox and set properties.</span></span>
    
- <span data-ttu-id="80575-120">Atribuir uma licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="80575-120">Assign an Office 365 license</span></span>
    
- <span data-ttu-id="80575-121">Habilitar a conta de dispositivo com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80575-121">Enable the device account with Skype for Business</span></span> <span data-ttu-id="80575-122">Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="80575-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>
    
  - <span data-ttu-id="80575-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span><span class="sxs-lookup"><span data-stu-id="80575-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="80575-124">O plano precisa dar suporte à funcionalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="80575-124">The plan needs to support conferencing capability.</span></span>
    
  - <span data-ttu-id="80575-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="80575-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
    
  - <span data-ttu-id="80575-126">Os usuários de locatário devem ter caixas de correio do .</span><span class="sxs-lookup"><span data-stu-id="80575-126">Your tenant users must have  mailboxes.</span></span>
    
  - <span data-ttu-id="80575-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span><span class="sxs-lookup"><span data-stu-id="80575-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>
    
- <span data-ttu-id="80575-128">Atribuir uma licença do Skype for Business Server 2015 a sua conta do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="80575-128">Assign a Skype for Business Server 2015 license to your Skype Room Systems v2 account</span></span>
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="80575-129">Criar uma conta e sincronizá-la com o Active Directory</span><span class="sxs-lookup"><span data-stu-id="80575-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="80575-130">Na ferramenta Usuários e Computadores do Active Directory, clique com o botão direito do mouse na pasta ou na Unidade Organizacional em que as contas do  serão criadas, clique em Novo e em Usuário.</span><span class="sxs-lookup"><span data-stu-id="80575-130">In the Active Directory Users and Computers AD tool, right-click on the folder or Organizational Unit that your  accounts will be created in, click New, and then click User.</span></span>
    
2. <span data-ttu-id="80575-p106">Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="80575-p106">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>
    
3. <span data-ttu-id="80575-p107">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="80575-p107">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="80575-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="80575-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="80575-137">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="80575-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="80575-138">Nesse caso, você deverá criar uma exceção para cada conta de dispositivo do .</span><span class="sxs-lookup"><span data-stu-id="80575-138">If so, you'll need to create an exception for each  device account.</span></span>
  
4. <span data-ttu-id="80575-139">Depois de criar a conta, execute a sincronização do diretório.</span><span class="sxs-lookup"><span data-stu-id="80575-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="80575-140">Após a conclusão, vá para a página de usuários no Centro de administração do  e verifique se a conta criada nas etapas anteriores foi mesclada com a conta online.</span><span class="sxs-lookup"><span data-stu-id="80575-140">When it's complete, go to the users page in your  admin center and verify that the account created in the previous steps has merged to online.</span></span>
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="80575-141">Habilitar a caixa de correio remota e as propriedades definidas</span><span class="sxs-lookup"><span data-stu-id="80575-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="80575-142">Habilite a caixa de correio remota abrindo o shell de gerenciamento do  no local com permissões de administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="80575-142">Enable the remote mailbox by opening your on-premises  management shell with administrator permissions and run the following command:</span></span>
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. <span data-ttu-id="80575-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="80575-143">Start a remote Windows PowerShell session and connect to Microsoft Exchange.</span></span> <span data-ttu-id="80575-144">No locatário do , execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="80575-144">From your  tenant, run the following commands:</span></span>
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. <span data-ttu-id="80575-145">Para aprimorar a experiência de reunião, será necessário definir as propriedades do  na conta de dispositivo, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="80575-145">To improve the meeting experience, you'll need to set the  properties on the device account as follows:</span></span>
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    <span data-ttu-id="80575-146">Para obter mais informações sobre propriedades que precisam ser definidas, consulte as propriedades do .</span><span class="sxs-lookup"><span data-stu-id="80575-146">For more information about which properties you need to set, see  properties.</span></span>
    
4. <span data-ttu-id="80575-147">Você deverá conectar-se ao Azure AD para aplicar algumas configurações à conta.</span><span class="sxs-lookup"><span data-stu-id="80575-147">You will need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="80575-148">Você pode executar este comando para se conectar:</span><span class="sxs-lookup"><span data-stu-id="80575-148">You can run this command to connect:</span></span>
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a><span data-ttu-id="80575-149">Atribuir uma licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="80575-149">Assign an Office 365 license</span></span>

1. <span data-ttu-id="80575-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span><span class="sxs-lookup"><span data-stu-id="80575-150">The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="80575-151">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="80575-151">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>
    
2. <span data-ttu-id="80575-152">Em seguida, use Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do .</span><span class="sxs-lookup"><span data-stu-id="80575-152">Next, use Get-MsolAccountSku to retrieve a list of available SKUs for your  tenant.</span></span>
    
3. <span data-ttu-id="80575-p113">Depois de listar as SKUs, você poderá adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="80575-p113">Once you list out the SKUs, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="80575-155">Habilitar a conta de dispositivo com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80575-155">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="80575-156">Crie uma sessão remota do  em um computador, como a seguir:</span><span class="sxs-lookup"><span data-stu-id="80575-156">Create a remote  session from a PC as follows:</span></span>
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="80575-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span><span class="sxs-lookup"><span data-stu-id="80575-157">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="80575-158">Se você não tem certeza sobre o valor que deve usar no parâmetro RegistrarPool em seu ambiente, pode obter o valor de um usuário do  existente usando este comando:</span><span class="sxs-lookup"><span data-stu-id="80575-158">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing  user using this command</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="80575-159">Atribuir uma licença do Skype for Business a sua conta do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="80575-159">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="80575-160">Faça logon como administrador do locatário, abra o portal de administração do  e clique no aplicativo Administrador.</span><span class="sxs-lookup"><span data-stu-id="80575-160">Log in as a tenant administrator, open the  Administrative Portal, and click on the Admin app.</span></span>
    
2. <span data-ttu-id="80575-161">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="80575-161">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
    
3. <span data-ttu-id="80575-162">Clique na conta do  e clique no ícone de caneta para editar as informações da conta.</span><span class="sxs-lookup"><span data-stu-id="80575-162">Click the  account, and then click the pen icon to edit the account information.</span></span>
    
4. <span data-ttu-id="80575-163">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="80575-163">Click **Licenses**.</span></span>
    
5. <span data-ttu-id="80575-164">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="80575-164">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="80575-165">Se quiser usar o Enterprise Voice no , será necessário usar uma licença com o Plano 3.</span><span class="sxs-lookup"><span data-stu-id="80575-165">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your .</span></span>
    
6. <span data-ttu-id="80575-166">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="80575-166">Click **Save**.</span></span>
    
<span data-ttu-id="80575-167">Para validação, você deverá ser capaz de usar qualquer cliente do  para fazer logon nessa conta.</span><span class="sxs-lookup"><span data-stu-id="80575-167">For validation, you should be able to use any  client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80575-168">Consulte também</span><span class="sxs-lookup"><span data-stu-id="80575-168">See also</span></span>

#### 

[<span data-ttu-id="80575-169">Planejar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="80575-169">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="80575-170">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="80575-170">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="80575-171">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="80575-171">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="80575-172">Gerenciar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="80575-172">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

