---
title: Implantar o Skype Room Systems versão 2 com o Exchange no local
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 em um ambiente híbrido com o Exchange no local.
ms.openlocfilehash: a804ba6b1210efae8ed36630180f14ad367cb955
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645413"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="bc5fa-103">Implantar o Skype Room Systems versão 2 com o Exchange no local</span><span class="sxs-lookup"><span data-stu-id="bc5fa-103">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="bc5fa-104">Leia este tópico para obter informações sobre como implantar sistemas de sala Skype v2 em um ambiente híbrido com o Exchange no local e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises and Skype for Business Online.</span></span>
  
<span data-ttu-id="bc5fa-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="bc5fa-106">Este tópico aborda as implantações híbridas para sistemas de sala Skype v2 com o Exchange hospedado no local.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="bc5fa-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="bc5fa-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-108">The following process will work for many configurations.</span></span> <span data-ttu-id="bc5fa-109">Se o processo não é ideal para sua instalação, é recomendável usar o Windows PowerShell para obter o mesmo resultado final conforme documentadas aqui e para obter outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="bc5fa-110">A Microsoft fornece [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudarão a criar novas contas de usuário ou validar contas existentes de recurso, que você ter para ajudá-lo a transformá-los em contas de usuário de v2 Skype sala sistemas compatíveis.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="bc5fa-111">Se você preferir, você pode seguir as etapas abaixo para configurar contas para que seu dispositivo v2 de sistemas de sala Skype usará.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-111">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="bc5fa-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc5fa-112">Requirements</span></span>

<span data-ttu-id="bc5fa-113">Antes de implantar sistemas de sala Skype v2 com o Exchange no local, certifique-se de que você cumpre os requisitos.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="bc5fa-114">Para obter mais informações, veja [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="bc5fa-115">Se você estiver implantando v2 Skype sistemas de sala com o Exchange no local, você usará ferramentas administrativas do Active Directory para adicionar um endereço de email para sua conta de domínio local.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="bc5fa-116">Essa conta será sincronizada com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="bc5fa-117">Você deverá:</span><span class="sxs-lookup"><span data-stu-id="bc5fa-117">You will need to:</span></span>
  
- <span data-ttu-id="bc5fa-118">Criar uma conta e sincronizá-la com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="bc5fa-119">Habilitar a caixa de correio remota e as propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="bc5fa-120">Atribua uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="bc5fa-121">Habilite a conta de dispositivo com Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="bc5fa-122">Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="bc5fa-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="bc5fa-123">Você precisará ter Skype para negócios Online (plano 2) ou superior no seu plano do Office 365.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="bc5fa-124">O plano precisa dar suporte à funcionalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="bc5fa-125">Se precisar de Enterprise Voice (telefonia PSTN) usando os provedores de serviços de telefonia para sistemas de sala Skype v2 será necessário Skype para Business Online (plano 3).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="bc5fa-126">Os usuários de Inquilino devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="bc5fa-127">Sua conta de v2 de sistemas de sala Skype exigir um Skype para negócios Online (plano 2) ou Skype licença Business Online (plano 3), mas ele não requer uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="bc5fa-128">Atribua um Skype licença Business Server à sua conta de v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="bc5fa-129">Criar uma conta e sincronizá-la com o Active Directory</span><span class="sxs-lookup"><span data-stu-id="bc5fa-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="bc5fa-130">Na ferramenta de **usuários do Active Directory e computadores AD** , clique com botão direito na pasta ou unidade organizacional que seus sistemas de sala Skype v2 contas serão criadas, clique em **novo**e, em seguida, clique em **usuário**.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="bc5fa-p107">Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="bc5fa-p108">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc5fa-136">Selecionando a **senha nunca expira** é um requisito para Skype para Business Server em sistemas de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="bc5fa-137">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="bc5fa-138">Nesse caso, você precisará criar uma exceção para cada conta de dispositivo v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="bc5fa-139">Depois de criar a conta, execute a sincronização do diretório.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="bc5fa-140">Quando ele estiver concluído, vá para a página de usuários no seu centro de administração do Office 365 e verifique se a conta criada nas etapas anteriores mesclada para online.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="bc5fa-141">Habilitar a caixa de correio remota e as propriedades definidas</span><span class="sxs-lookup"><span data-stu-id="bc5fa-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="bc5fa-142">[Abra o Shell de gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [Conecte-se ao servidor do Exchange usando o PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="bc5fa-143">No PowerShell do Exchange, criar uma caixa de correio para a conta (caixa de correio-habilitar a conta) executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="bc5fa-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="bc5fa-144">Para detalhadas sobre sintaxe e informações de parâmetro, consulte [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="bc5fa-145">No PowerShell do Exchange, defina as seguintes configurações na caixa de correio de sala para melhorar a experiência de reunião:</span><span class="sxs-lookup"><span data-stu-id="bc5fa-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="bc5fa-146">AutomateProcessing: AutoAccept (organizadores de reunião recebem a decisão de reserva de sala diretamente, sem intervenção humana: livre = aceitar; ocupado = recusar.)</span><span class="sxs-lookup"><span data-stu-id="bc5fa-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="bc5fa-147">AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="bc5fa-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="bc5fa-148">DeleteComments: $false (mantenha qualquer texto no corpo da mensagem de entrada solicitações de reunião).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="bc5fa-149">DeleteSubject: $false (manter o assunto de solicitações de reunião recebidas).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="bc5fa-150">RemovePrivateProperty: $false (assegura o sinalizador particular que foi enviado pelo organizador da reunião na reunião original permanece conforme especificado de solicitação).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="bc5fa-151">AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="bc5fa-152">AdditionalResponse: "Esta é uma sala de reunião Skype!"</span><span class="sxs-lookup"><span data-stu-id="bc5fa-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="bc5fa-153">(O texto adicional para adicionar à solicitação de reunião).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="bc5fa-154">Este exemplo configura essas configurações na caixa de correio de sala chamada Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="bc5fa-155">Para detalhadas sobre sintaxe e informações de parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="bc5fa-156">Atribuir uma licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="bc5fa-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="bc5fa-157">Conecte-se ao PowerShell do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-157">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="bc5fa-158">Para obter instruções, consulte [conectar-se com o Azure Active Directory PowerShell para o módulo de gráfico](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="bc5fa-158">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

2. <span data-ttu-id="bc5fa-159">A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Skype para negócios não funcionará.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-159">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="bc5fa-160">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-160">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="bc5fa-161">Você pode usar o Get-AzureADSubscribedSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="bc5fa-161">You can use Get-AzureADSubscribedSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```

   <span data-ttu-id="bc5fa-162">Em seguida, você pode adicionar uma licença usando o cmdlet Set-AzureADUserLicense.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-162">Next, you can add a license using the Set-AzureADUserLicense cmdlet.</span></span> <span data-ttu-id="bc5fa-163">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-163">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

   <span data-ttu-id="bc5fa-164">Para obter instruções detalhadas, consulte [Atribuir licenças às contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc5fa-164">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="bc5fa-165">Habilitar a conta de dispositivo com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc5fa-165">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="bc5fa-166">Crie uma sessão remota do Windows PowerShell de um PC, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="bc5fa-166">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="bc5fa-167">Para habilitar sua conta do Skype sala sistemas v2 para Skype para Business Server, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="bc5fa-167">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="bc5fa-168">Se você não tiver certeza sobre qual valor usar para o parâmetro RegistrarPool no seu ambiente, você pode obter o valor de um existente Skype para usuário Business Server usando este comando</span><span class="sxs-lookup"><span data-stu-id="bc5fa-168">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="bc5fa-169">Atribuir uma licença do Skype for Business a sua conta do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="bc5fa-169">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="bc5fa-170">Logon como um administrador de locatário, abra o Portal do Office 365 administrativas e clique no aplicativo Administração.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-170">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="bc5fa-171">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-171">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="bc5fa-172">Clique na conta de sistemas de sala Skype v2 e, em seguida, clique no ícone de caneta para editar as informações de conta.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-172">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="bc5fa-173">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-173">Click **Licenses**.</span></span>
5. <span data-ttu-id="bc5fa-174">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-174">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="bc5fa-175">Você terá que usar uma licença de plano 3 se você quiser usar o Enterprise Voice em sua v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-175">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
6. <span data-ttu-id="bc5fa-176">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-176">Click **Save**.</span></span>

<span data-ttu-id="bc5fa-177">Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para fazer logon conta.</span><span class="sxs-lookup"><span data-stu-id="bc5fa-177">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bc5fa-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bc5fa-178">See also</span></span>

[<span data-ttu-id="bc5fa-179">Configurar contas para sistemas de sala Skype v2</span><span class="sxs-lookup"><span data-stu-id="bc5fa-179">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="bc5fa-180">Plan for Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="bc5fa-180">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="bc5fa-181">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="bc5fa-181">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="bc5fa-182">Configurar o console do Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="bc5fa-182">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="bc5fa-183">Gerenciar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="bc5fa-183">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)