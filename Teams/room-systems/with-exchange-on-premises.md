---
title: Implantar as Salas do Microsoft Teams com o Exchange no local
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams em um ambiente híbrido com o Exchange no local.
ms.openlocfilehash: 62840e0a28ee1eba2a9b5a94f976f169eab628da
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952714"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="fef9d-103">Implantar as Salas do Microsoft Teams com o Exchange no local</span><span class="sxs-lookup"><span data-stu-id="fef9d-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="fef9d-104">Leia este tópico para obter informações sobre como implantar salas do Microsoft Teams em um ambiente híbrido com o Exchange no local e o Microsoft Teams ou o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="fef9d-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="fef9d-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="fef9d-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="fef9d-106">Este tópico aborda implantações híbridas de salas do Microsoft Teams com o Exchange hospedado no local.</span><span class="sxs-lookup"><span data-stu-id="fef9d-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="fef9d-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="fef9d-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="fef9d-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="fef9d-108">The following process will work for many configurations.</span></span> <span data-ttu-id="fef9d-109">Se o processo não está correto para a sua configuração, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final conforme documentado aqui e para outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="fef9d-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="fef9d-110">A Microsoft fornece [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar as contas de recursos existentes que você tem para ajudar a transformá-las em contas de usuário compatíveis do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fef9d-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="fef9d-111">Se preferir, você pode seguir as etapas abaixo para configurar contas que o dispositivo de salas do Microsoft Teams vai usar.</span><span class="sxs-lookup"><span data-stu-id="fef9d-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="fef9d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fef9d-112">Requirements</span></span>

<span data-ttu-id="fef9d-113">Antes de implantar salas do Microsoft Teams com o Exchange no local, certifique-se de que atenda aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="fef9d-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="fef9d-114">Para obter mais informações, consulte [requisitos de salas do Microsoft Teams](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fef9d-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="fef9d-115">Se você estiver implantando salas do Microsoft Teams com o Exchange no local, usará as ferramentas administrativas do Active Directory para adicionar um endereço de email para a sua conta de domínio local.</span><span class="sxs-lookup"><span data-stu-id="fef9d-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="fef9d-116">Esta conta será sincronizada com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="fef9d-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="fef9d-117">Você deverá:</span><span class="sxs-lookup"><span data-stu-id="fef9d-117">You will need to:</span></span>
  
- <span data-ttu-id="fef9d-118">Criar uma conta e sincronizá-la com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fef9d-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="fef9d-119">Habilitar a caixa de correio remota e as propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="fef9d-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="fef9d-120">Atribua uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="fef9d-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="fef9d-121">Habilite a conta do dispositivo com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fef9d-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="fef9d-122">Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="fef9d-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="fef9d-123">Você precisará ter o Skype for Business online (plano 2) ou versão mais recente no seu plano do Office 365.</span><span class="sxs-lookup"><span data-stu-id="fef9d-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="fef9d-124">O plano precisa dar suporte à funcionalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="fef9d-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="fef9d-125">Se você precisa do Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para salas do Microsoft Teams, você precisa do Skype for Business online (plano 3).</span><span class="sxs-lookup"><span data-stu-id="fef9d-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="fef9d-126">Os usuários do locatário devem ter caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="fef9d-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="fef9d-127">Sua conta de salas do Microsoft Teams exige uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3), mas não requer uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fef9d-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="fef9d-128">Atribua uma licença do Skype for Business Server à sua conta de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fef9d-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="fef9d-129">Criar uma conta e sincronizá-la com o Active Directory</span><span class="sxs-lookup"><span data-stu-id="fef9d-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="fef9d-130">Na ferramenta **usuários e computadores do Active Directory** , clique com o botão direito do mouse na pasta ou unidade organizacional na qual as contas de salas do Microsoft Teams serão criadas, clique em **novo**e, em seguida, clique em **usuário**.</span><span class="sxs-lookup"><span data-stu-id="fef9d-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="fef9d-p107">Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fef9d-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="fef9d-p108">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="fef9d-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fef9d-136">Selecionar a **senha nunca expira** é um requisito para as salas do Skype for Business Server em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fef9d-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="fef9d-137">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="fef9d-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="fef9d-138">Em caso afirmativo, você precisará criar uma exceção para cada conta de dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fef9d-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="fef9d-139">Depois de criar a conta, execute a sincronização do diretório.</span><span class="sxs-lookup"><span data-stu-id="fef9d-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="fef9d-140">Quando ele estiver concluído, vá para a página usuários no centro de administração do Microsoft 365 e verifique se a conta criada nas etapas anteriores foi mesclada para online.</span><span class="sxs-lookup"><span data-stu-id="fef9d-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="fef9d-141">Habilitar a caixa de correio remota e as propriedades definidas</span><span class="sxs-lookup"><span data-stu-id="fef9d-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="fef9d-142">[Abra o Shell de gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [Conecte-se ao seu servidor Exchange usando o PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="fef9d-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="fef9d-143">No PowerShell do Exchange, encaixar uma caixa de correio para a conta (habilitar a caixa de correio na conta) executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="fef9d-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="fef9d-144">Para obter informações detalhadas sobre a sintaxe e o parâmetro, consulte [habilitar-caixa de correio](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="fef9d-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="fef9d-145">No PowerShell do Exchange, defina as seguintes configurações na caixa de correio da sala para melhorar a experiência da reunião:</span><span class="sxs-lookup"><span data-stu-id="fef9d-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="fef9d-146">AutomateProcessing: a aceitação autoaceitar (os organizadores de reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: grátis = aceitar; Busy = recusar.)</span><span class="sxs-lookup"><span data-stu-id="fef9d-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="fef9d-147">AddOrganizerToSubject: $false (o organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="fef9d-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="fef9d-148">DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="fef9d-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="fef9d-149">DeleteSubject: $false (Mantenha o assunto das solicitações de reunião recebidas.)</span><span class="sxs-lookup"><span data-stu-id="fef9d-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="fef9d-150">RemovePrivateProperty: $false (garante que o sinalizador particular enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)</span><span class="sxs-lookup"><span data-stu-id="fef9d-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="fef9d-151">AddAdditionalResponse: $true (o texto especificado pelo parâmetro AdditionalResponse é adicionado a solicitações de reunião.)</span><span class="sxs-lookup"><span data-stu-id="fef9d-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="fef9d-152">AdditionalResponse: "esta é uma sala de reunião do Skype!"</span><span class="sxs-lookup"><span data-stu-id="fef9d-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="fef9d-153">(O texto adicional a ser adicionado à solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="fef9d-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="fef9d-154">Este exemplo configura essas configurações na caixa de correio da sala chamada Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="fef9d-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="fef9d-155">Para obter informações detalhadas de sintaxe e parâmetro, consulte [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="fef9d-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="fef9d-156">Atribuir uma licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="fef9d-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="fef9d-157">Conecte-se ao Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fef9d-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="fef9d-158">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="fef9d-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="fef9d-159">Não há suporte para o [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="fef9d-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="fef9d-160">A conta do dispositivo precisa ter uma licença válida do Office 365 ou o Exchange e o Microsoft Teams não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="fef9d-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="fef9d-161">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="fef9d-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="fef9d-162">Você pode usar`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="fef9d-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="fef9d-163">para recuperar uma lista de SKUs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fef9d-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="fef9d-164">Em seguida, você pode adicionar uma licença usando o`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="fef9d-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="fef9d-165">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fef9d-165">cmdlet.</span></span> <span data-ttu-id="fef9d-166">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="fef9d-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="fef9d-167">Para obter instruções detalhadas, consulte [atribuir licenças a contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fef9d-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="fef9d-168">Habilitar a conta do dispositivo</span><span class="sxs-lookup"><span data-stu-id="fef9d-168">Enable the device account</span></span>

<span data-ttu-id="fef9d-169">O PowerShell do Skype for Business Online é usado para gerenciar serviços para o Microsoft Teams e o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="fef9d-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="fef9d-170">Crie uma sessão remota do Windows PowerShell a partir de um PC da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fef9d-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="fef9d-171">Obter o endereço SIP da conta:</span><span class="sxs-lookup"><span data-stu-id="fef9d-171">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="fef9d-172">Para habilitar a sua conta de salas do Microsoft Teams, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="fef9d-172">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="fef9d-173">Se não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, você pode obter o valor de um usuário existente usando este comando:</span><span class="sxs-lookup"><span data-stu-id="fef9d-173">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="fef9d-174">Atribuir uma licença à sua conta de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fef9d-174">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="fef9d-175">Faça logon como administrador de locatários, abra o portal administrativo do Office 365 e clique no aplicativo de administração.</span><span class="sxs-lookup"><span data-stu-id="fef9d-175">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="fef9d-176">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="fef9d-176">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="fef9d-177">Clique na conta de salas do Microsoft Teams e, em seguida, clique no ícone de caneta para editar as informações da conta.</span><span class="sxs-lookup"><span data-stu-id="fef9d-177">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="fef9d-178">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="fef9d-178">Click **Licenses**.</span></span>
5. <span data-ttu-id="fef9d-179">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fef9d-179">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="fef9d-180">Você precisará usar uma licença do plano 3 se quiser usar o Enterprise Voice em suas salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fef9d-180">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="fef9d-181">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fef9d-181">Click **Save**.</span></span>

<span data-ttu-id="fef9d-182">Para a validação, você deve ser capaz de usar qualquer cliente para se conectar a esta conta.</span><span class="sxs-lookup"><span data-stu-id="fef9d-182">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fef9d-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="fef9d-183">See also</span></span>

[<span data-ttu-id="fef9d-184">Configurar contas para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fef9d-184">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="fef9d-185">Plano para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fef9d-185">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="fef9d-186">Implantar salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fef9d-186">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="fef9d-187">Configurar um console de salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fef9d-187">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="fef9d-188">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fef9d-188">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
