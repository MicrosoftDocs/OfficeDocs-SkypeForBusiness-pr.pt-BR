---
title: Implantar Salas do Microsoft Teams com Exchange local
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams em um ambiente híbrido com Exchange local.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117349"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="553c9-103">Implantar as Salas do Microsoft Teams com o Exchange no local</span><span class="sxs-lookup"><span data-stu-id="553c9-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="553c9-104">Leia este tópico para obter informações sobre como implantar Salas do Microsoft Teams em um ambiente híbrido com Exchange local e Microsoft Teams ou Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="553c9-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="553c9-105">Se a sua organização tem uma combinação de serviços hospedados no local e online, a configuração depende de onde cada serviço está hospedado.</span><span class="sxs-lookup"><span data-stu-id="553c9-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="553c9-106">Este tópico aborda implantações híbridas para Salas do Microsoft Teams com Exchange hospedados no local.</span><span class="sxs-lookup"><span data-stu-id="553c9-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="553c9-107">Como existem muitas variações nesse tipo de implantação, não é possível fornecer instruções detalhadas para todas elas.</span><span class="sxs-lookup"><span data-stu-id="553c9-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="553c9-108">O processo a seguir funcionará para várias configurações.</span><span class="sxs-lookup"><span data-stu-id="553c9-108">The following process will work for many configurations.</span></span> <span data-ttu-id="553c9-109">Se o processo não estiver correto para sua instalação, recomendamos que você use o Windows PowerShell para obter o mesmo resultado final como documentado aqui e para outras opções de implantação.</span><span class="sxs-lookup"><span data-stu-id="553c9-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="553c9-110">A Microsoft [forneceSkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), um script que ajudará a criar novas contas de usuário ou validar contas de recursos existentes que você tem para ajudá-lo a transformá-las em contas de usuário compatíveis Salas do Microsoft Teams usuário.</span><span class="sxs-lookup"><span data-stu-id="553c9-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="553c9-111">Se preferir, siga as etapas abaixo para configurar contas que seu Salas do Microsoft Teams dispositivo usará.</span><span class="sxs-lookup"><span data-stu-id="553c9-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="553c9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="553c9-112">Requirements</span></span>

<span data-ttu-id="553c9-113">Antes de implantar Salas do Microsoft Teams com Exchange local, certifique-se de ter atendido aos requisitos.</span><span class="sxs-lookup"><span data-stu-id="553c9-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="553c9-114">Para obter mais informações, [consulte Salas do Microsoft Teams requisitos](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="553c9-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="553c9-115">Se você estiver implantando Salas do Microsoft Teams com Exchange local, você estará usando ferramentas administrativas do Active Directory para adicionar um endereço de email para sua conta de domínio local.</span><span class="sxs-lookup"><span data-stu-id="553c9-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="553c9-116">Essa conta será sincronizada com Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="553c9-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="553c9-117">Você deverá:</span><span class="sxs-lookup"><span data-stu-id="553c9-117">You will need to:</span></span>
  
- <span data-ttu-id="553c9-118">Criar uma conta e sincronizá-la com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="553c9-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="553c9-119">Habilitar a caixa de correio remota e as propriedades definidas.</span><span class="sxs-lookup"><span data-stu-id="553c9-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="553c9-120">Atribua uma Microsoft 365 ou Office 365 licença.</span><span class="sxs-lookup"><span data-stu-id="553c9-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="553c9-121">Habilita a conta do dispositivo com Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="553c9-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="553c9-122">Para habilitar a conta de dispositivo, seu ambiente deverá atender aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="553c9-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="553c9-123">Você precisará ter um Skype for Business Online (Plano 2) ou superior em seu Microsoft 365 ou Office 365 plano.</span><span class="sxs-lookup"><span data-stu-id="553c9-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="553c9-124">O plano precisa dar suporte à funcionalidade de conferência.</span><span class="sxs-lookup"><span data-stu-id="553c9-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="553c9-125">Se você precisar Enterprise Voice (telefonia PSTN) usando provedores de serviços de telefonia para Salas do Microsoft Teams você precisa Skype for Business Online (Plano 3).</span><span class="sxs-lookup"><span data-stu-id="553c9-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="553c9-126">Ao configurar uma conta de sala com Microsoft Teams ou Skype for Business Online, o número de telefone deve ser atribuído antes da conta ser habilitada como uma conta de sala.</span><span class="sxs-lookup"><span data-stu-id="553c9-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="553c9-127">Os usuários do locatário devem ter Exchange caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="553c9-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="553c9-128">Sua Salas do Microsoft Teams de Skype for Business requer uma licença Skype for Business Online (Plano 2) ou Skype for Business Online (Plano 3), mas não exige uma licença de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="553c9-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="553c9-129">Atribua uma Skype for Business Server de usuário à sua Salas do Microsoft Teams de usuário.</span><span class="sxs-lookup"><span data-stu-id="553c9-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="553c9-130">Criar uma conta e sincronizá-la com o Active Directory</span><span class="sxs-lookup"><span data-stu-id="553c9-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="553c9-131">Na ferramenta Usuários e Computadores do **Active Directory,** clique com o botão direito do mouse na pasta ou Unidade Organizacional na qual suas contas Salas do Microsoft Teams serão criadas, clique em Novo **e** em **Usuário**.</span><span class="sxs-lookup"><span data-stu-id="553c9-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="553c9-p107">Digite o nome de exibição do cmdlet anterior na caixa **Nome completo** e o alias na caixa **Nome de logon do usuário**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="553c9-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="553c9-p108">Digite a senha da conta. Você deverá redigitá-la para verificação. Verifique se a caixa de seleção **A senha nunca expira** é a única opção selecionada.</span><span class="sxs-lookup"><span data-stu-id="553c9-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553c9-137">Selecionar **Senha nunca expira é** um requisito para Skype for Business Server no Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="553c9-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="553c9-138">As regras do domínio podem proibir senhas que não expiram.</span><span class="sxs-lookup"><span data-stu-id="553c9-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="553c9-139">Em caso afirmado, você precisará criar uma exceção para cada Salas do Microsoft Teams de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="553c9-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="553c9-140">Depois de criar a conta, execute a sincronização do diretório.</span><span class="sxs-lookup"><span data-stu-id="553c9-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="553c9-141">Quando estiver concluída, vá até a página usuários no centro de administração do Microsoft 365 e verifique se a conta criada nas etapas anteriores foi mesclada para online.</span><span class="sxs-lookup"><span data-stu-id="553c9-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="553c9-142">Habilitar a caixa de correio remota e as propriedades definidas</span><span class="sxs-lookup"><span data-stu-id="553c9-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="553c9-143">[Abra o Shell de Gerenciamento Exchange ou](/powershell/exchange/exchange-server/open-the-exchange-management-shell) conecte-se ao seu servidor Exchange usando o [PowerShell remoto.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="553c9-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="553c9-144">No Exchange PowerShell, crie uma caixa de correio para a conta (caixa de correio habilitada para a conta) executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="553c9-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="553c9-145">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="553c9-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="553c9-146">No Exchange PowerShell, configure as seguintes configurações na caixa de correio da sala para melhorar a experiência de reunião:</span><span class="sxs-lookup"><span data-stu-id="553c9-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="553c9-147">AutomateProcessing: AutoAccept (Os organizadores da reunião recebem a decisão de reserva de sala diretamente sem intervenção humana: free = accept; busy = decline.)</span><span class="sxs-lookup"><span data-stu-id="553c9-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="553c9-148">AddOrganizerToSubject: $false (O organizador da reunião não é adicionado ao assunto da solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="553c9-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="553c9-149">DeleteComments: $false (Mantenha qualquer texto no corpo da mensagem de solicitações de reunião de entrada.)</span><span class="sxs-lookup"><span data-stu-id="553c9-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="553c9-150">DeleteSubject: $false (Mantenha o assunto das solicitações de reunião de entrada.)</span><span class="sxs-lookup"><span data-stu-id="553c9-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="553c9-151">RemovePrivateProperty: $false (Garante que o sinalizador privado enviado pelo organizador da reunião na solicitação de reunião original permaneça conforme especificado.)</span><span class="sxs-lookup"><span data-stu-id="553c9-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="553c9-152">AddAdditionalResponse: $true (O texto especificado pelo parâmetro AdditionalResponse é adicionado às solicitações de reunião.)</span><span class="sxs-lookup"><span data-stu-id="553c9-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="553c9-153">AdditionalResponse: "Esta é uma sala Reunião do Skype de Reunião do Skype!"</span><span class="sxs-lookup"><span data-stu-id="553c9-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="553c9-154">(O texto adicional a ser acrescentado à solicitação de reunião.)</span><span class="sxs-lookup"><span data-stu-id="553c9-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="553c9-155">Este exemplo configura essas configurações na caixa de correio de sala chamada Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="553c9-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="553c9-156">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="553c9-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="553c9-157">Atribuir uma Microsoft 365 ou Office 365 licença</span><span class="sxs-lookup"><span data-stu-id="553c9-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="553c9-158">Conexão para Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="553c9-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="553c9-159">Para obter detalhes sobre o Active Directory, consulte [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="553c9-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="553c9-160">Azure Active Directory não há suporte para o [PowerShell 2.0.](/powershell/azure/active-directory/overview?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="553c9-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="553c9-161">A conta de dispositivo precisa ter uma licença Microsoft 365 ou Office 365, ou Exchange e Microsoft Teams não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="553c9-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="553c9-162">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="553c9-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="553c9-163">Você pode usar `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="553c9-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="553c9-164">para recuperar uma lista de SKUs disponíveis.</span><span class="sxs-lookup"><span data-stu-id="553c9-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="553c9-165">Em seguida, você pode adicionar uma licença usando o `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="553c9-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="553c9-166">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="553c9-166">cmdlet.</span></span> <span data-ttu-id="553c9-167">Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="553c9-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="553c9-168">Para obter instruções [detalhadas, consulte Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="553c9-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="553c9-169">Habilitar a conta do dispositivo</span><span class="sxs-lookup"><span data-stu-id="553c9-169">Enable the device account</span></span>

<span data-ttu-id="553c9-170">Skype for Business O PowerShell online é usado para gerenciar serviços para Microsoft Teams e Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="553c9-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="553c9-171">Crie uma sessão Windows PowerShell remota de um computador da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="553c9-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="553c9-172">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="553c9-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="553c9-173">Se você estiver usando a versão pública mais [recente Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o conector Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="553c9-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="553c9-174">Obtenha o endereço SIP da conta:</span><span class="sxs-lookup"><span data-stu-id="553c9-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="553c9-175">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="553c9-175">**Optional.**</span></span> <span data-ttu-id="553c9-176">Se você quiser atribuir um número de telefone à conta, a operação deve ser executada neste ponto.</span><span class="sxs-lookup"><span data-stu-id="553c9-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="553c9-177">Se você quiser atribuir um número de telefone de Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="553c9-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="553c9-178">Se você estiver atribuindo um número de telefone fornecido pela Microsoft, use o cmdlet abaixo depois de ter provisionado o usuário com uma licença de Plano de Chamadas:</span><span class="sxs-lookup"><span data-stu-id="553c9-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="553c9-179">Para habilitar sua Salas do Microsoft Teams, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="553c9-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="553c9-180">Se você não tiver certeza de qual valor usar para o parâmetro RegistrarPool em seu ambiente, poderá obter o valor de um usuário existente usando este comando:</span><span class="sxs-lookup"><span data-stu-id="553c9-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="553c9-181">Atribuir uma licença à sua Salas do Microsoft Teams de usuário</span><span class="sxs-lookup"><span data-stu-id="553c9-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="553c9-182">Faça logoff como administrador de locatário, abra o Microsoft 365 de administração e clique no aplicativo Administrador.</span><span class="sxs-lookup"><span data-stu-id="553c9-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="553c9-183">Clique em **Usuários e Grupos** e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="553c9-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="553c9-184">Clique na Salas do Microsoft Teams e clique no ícone de caneta para editar as informações da conta.</span><span class="sxs-lookup"><span data-stu-id="553c9-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="553c9-185">Clique em **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="553c9-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="553c9-186">Em **Atribuir licenças**, selecione  Skype for Business (Plano 2) ou Skype for Business (Plano 3), de acordo com o seu licenciamento e os requisitos do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="553c9-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="553c9-187">Você terá que usar uma licença de Plano 3 se quiser usar Enterprise Voice em seu Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="553c9-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="553c9-188">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="553c9-188">Click **Save**.</span></span>

<span data-ttu-id="553c9-189">Para validação, você deve ser capaz de usar qualquer cliente para fazer logoff nessa conta.</span><span class="sxs-lookup"><span data-stu-id="553c9-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="553c9-190">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="553c9-190">Related topics</span></span>

[<span data-ttu-id="553c9-191">Configurar contas para Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="553c9-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="553c9-192">Planejar as Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="553c9-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="553c9-193">Implantar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="553c9-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="553c9-194">Configurar um console de Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="553c9-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="553c9-195">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="553c9-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)