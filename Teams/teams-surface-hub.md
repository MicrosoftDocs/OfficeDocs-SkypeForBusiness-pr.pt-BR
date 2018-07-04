---
title: Implantar as equipes da Microsoft para o Hub de superfície
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Defina configurações de administração for Microsoft Teams para o Hub de superfície.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192176"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="14b87-103">Implantar as equipes da Microsoft para o Hub de superfície</span><span class="sxs-lookup"><span data-stu-id="14b87-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="14b87-104">Antes de implantar Teams da Microsoft para Microsoft Surface Hub, certifique-se de que você cumpre o hardware, sistema operacional e outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="14b87-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="14b87-105">Para obter mais informações, consulte o [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="14b87-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="14b87-106">Configurar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="14b87-106">Set up user accounts</span></span>
 
<span data-ttu-id="14b87-107">Para configurar contas de usuário que podem ser usadas com equipes para o Hub de superfície, crie a conta de dispositivo como faria para suporte com Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="14b87-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="14b87-108">A conta do dispositivo precisa ter a autenticação multifator desabilitada (para permitir o logon automático) para os seguintes serviços dependentes de equipes no Office 365:</span><span class="sxs-lookup"><span data-stu-id="14b87-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="14b87-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="14b87-109">Exchange</span></span> 
- <span data-ttu-id="14b87-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="14b87-110">SharePoint</span></span> 
- <span data-ttu-id="14b87-111">Aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="14b87-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="14b87-112">Adicionar uma conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="14b87-112">Add a device account</span></span> 

<span data-ttu-id="14b87-113">1 \.</span><span class="sxs-lookup"><span data-stu-id="14b87-113">1\.</span></span> <span data-ttu-id="14b87-114">Inicie uma sessão remota do Windows PowerShell em um PC e se conectar ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="14b87-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="14b87-115">Certifique-se de que você tem as permissões corretas definidas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="14b87-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="14b87-116">Veja a seguir alguns exemplos de cmdlets que podem ser usados e modificados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="14b87-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="14b87-117">2 \.</span><span class="sxs-lookup"><span data-stu-id="14b87-117">2\.</span></span> <span data-ttu-id="14b87-118">Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="14b87-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="14b87-119">Isso permitirá a conta autenticar a equipes.</span><span class="sxs-lookup"><span data-stu-id="14b87-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="14b87-120">Se você estiver alterando uma caixa de correio do recurso existente:</span><span class="sxs-lookup"><span data-stu-id="14b87-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="14b87-121">Se você criar uma nova caixa de correio para o recurso:</span><span class="sxs-lookup"><span data-stu-id="14b87-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="14b87-122">3\.</span><span class="sxs-lookup"><span data-stu-id="14b87-122">3\.</span></span> <span data-ttu-id="14b87-123">Várias propriedades do Exchange deverão ser definidas na conta de dispositivo para aprimorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="14b87-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="14b87-124">Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="14b87-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="14b87-125">4\.</span><span class="sxs-lookup"><span data-stu-id="14b87-125">4\.</span></span> <span data-ttu-id="14b87-126">Você deverá conectar-se ao Azure Active Directory para aplicar algumas configurações à conta.</span><span class="sxs-lookup"><span data-stu-id="14b87-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="14b87-127">Para se conectar ao Azure AD, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="14b87-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="14b87-128">5\.</span><span class="sxs-lookup"><span data-stu-id="14b87-128">5\.</span></span> <span data-ttu-id="14b87-129">	Para a senha não expirar, execute o cmdlet Set-MsolUser com a opção PasswordNeverExpires, como a seguir:  </span><span class="sxs-lookup"><span data-stu-id="14b87-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="14b87-130">Você também pode definir um número de telefone para a sala da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="14b87-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="14b87-131">6\.</span><span class="sxs-lookup"><span data-stu-id="14b87-131">6\.</span></span> <span data-ttu-id="14b87-132">A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Skype para negócios não funcionará.</span><span class="sxs-lookup"><span data-stu-id="14b87-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="14b87-133">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="14b87-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="14b87-134">Você pode usar o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="14b87-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="14b87-p109">Em seguida, você pode adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="14b87-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="14b87-137">7\.</span><span class="sxs-lookup"><span data-stu-id="14b87-137">7\.</span></span> <span data-ttu-id="14b87-138">Em seguida, você precisará habilitar a conta de dispositivo com equipes para o Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="14b87-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="14b87-139">Certifique-se de que seu ambiente atende aos requisitos definidos no [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="14b87-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="14b87-140">Iniciar uma sessão do Windows PowerShell remota da seguinte maneira (certifique-se de instalar o Skype para componentes de negócios Online PowerShell):</span><span class="sxs-lookup"><span data-stu-id="14b87-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="14b87-141">Em seguida, habilite suas equipes de conta do Hub de superfície executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="14b87-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="14b87-142">Obtenha as informações de RegistrarPool da nova conta de usuário sendo instalação, como mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="14b87-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="14b87-143">Novas contas de usuário não podem ser criadas no mesmo pool do registrador contas de usuário existentes no inquilino.</span><span class="sxs-lookup"><span data-stu-id="14b87-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="14b87-144">O comando acima evitará erros na configuração de conta devido a essa situação.</span><span class="sxs-lookup"><span data-stu-id="14b87-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="14b87-145">Depois de concluir as etapas anteriores para permitir que as equipes de conta do Hub de superfície, você precisa atribuir uma licença para o dispositivo do Hub de superfície v2.</span><span class="sxs-lookup"><span data-stu-id="14b87-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="14b87-146">Usando o portal administrativo do Office 365, atribua a equipes de licença do Hub de superfície para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14b87-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="14b87-147">Atribuir uma licença para a conta</span><span class="sxs-lookup"><span data-stu-id="14b87-147">Assign a license to the account</span></span>

1. <span data-ttu-id="14b87-148">Faça logon como um administrador de locatários, abra o Centro de administração do Office 365 e clique no aplicativo Administração.</span><span class="sxs-lookup"><span data-stu-id="14b87-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="14b87-149">Clique em **usuários e grupos**e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="14b87-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="14b87-150">Selecione as equipes de conta do Hub de superfície e, em seguida, clique ou toque no ícone de caneta, o que significa editar.</span><span class="sxs-lookup"><span data-stu-id="14b87-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="14b87-151">Clique na opção de **licenças** .</span><span class="sxs-lookup"><span data-stu-id="14b87-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="14b87-152">Na seção **Atribuir licenças** , você precisa selecionar o plano, dependendo do seu licenciamento.</span><span class="sxs-lookup"><span data-stu-id="14b87-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="14b87-153">Clique em **Salvar** para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="14b87-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="14b87-154">Instalar equipes para o Hub de superfície do repositório de Microsoft</span><span class="sxs-lookup"><span data-stu-id="14b87-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="14b87-155">Essas instruções incluem as soluções alternativas de atuais para a instalação de equipes para o Hub de superfície do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="14b87-155">These instructions include the current workarounds for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="14b87-156">Inicie o repositório do Windows:</span><span class="sxs-lookup"><span data-stu-id="14b87-156">Start the Windows Store:</span></span><br>
   <span data-ttu-id="14b87-157">a.</span><span class="sxs-lookup"><span data-stu-id="14b87-157">a.</span></span> <span data-ttu-id="14b87-158">Toque em **Iniciar** > **todos os aplicativos** > **configurações**.</span><span class="sxs-lookup"><span data-stu-id="14b87-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="14b87-159">b.</span><span class="sxs-lookup"><span data-stu-id="14b87-159">b.</span></span> <span data-ttu-id="14b87-160">Toque em **conta de dispositivo do Hub de superfície, gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="14b87-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="14b87-161">c.</span><span class="sxs-lookup"><span data-stu-id="14b87-161">c.</span></span> <span data-ttu-id="14b87-162">À esquerda, toque em da guia **aplicativos e recursos** .</span><span class="sxs-lookup"><span data-stu-id="14b87-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="14b87-163">d.</span><span class="sxs-lookup"><span data-stu-id="14b87-163">d.</span></span> <span data-ttu-id="14b87-164">À direita, toque no botão **Abrir armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="14b87-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="14b87-165">Do Microsoft Store, procure *As equipes da Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="14b87-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="14b87-166">As **Equipes da Microsoft para o Hub de superfície (Preview)** será exibida.</span><span class="sxs-lookup"><span data-stu-id="14b87-166">The **Microsoft Teams for Surface Hub (Preview)** will be displayed.</span></span> <span data-ttu-id="14b87-167">Toque no botão **obter o aplicativo** para instalar.</span><span class="sxs-lookup"><span data-stu-id="14b87-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="14b87-168">Quando a instalação estiver concluída, reinicie o Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="14b87-168">When the installation is complete, restart the Surface Hub.</span></span> 
4. <span data-ttu-id="14b87-169">Depois que o Hub de superfície for reiniciado, você poderá iniciar o aplicativo de equipes do menu **Iniciar** e ingressar em uma reunião do calendário.</span><span class="sxs-lookup"><span data-stu-id="14b87-169">After the Surface Hub restarts, you should be able to start the Teams app from the **Start** menu and join a meeting from the calendar.</span></span> 

## <a name="make-teams-the-default-vtc-application"></a><span data-ttu-id="14b87-170">Tornar as equipes aplicativo VTC padrão</span><span class="sxs-lookup"><span data-stu-id="14b87-170">Make Teams the default VTC application</span></span>

<span data-ttu-id="14b87-171">As equipes podem ser definidas até ser o aplicativo de VTC padrão, em vez de Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="14b87-171">Teams can be set up to be the default VTC application instead of Skype for Business.</span></span> <span data-ttu-id="14b87-172">Uma política de gerenciamento de dispositivo móvel (MDM) deve ser aplicada ao dispositivo Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="14b87-172">A Mobile Device Management (MDM) policy needs to be applied to the Surface Hub device.</span></span> 
 
<span data-ttu-id="14b87-173">Há duas opções para configurar políticas MDM:</span><span class="sxs-lookup"><span data-stu-id="14b87-173">There are two options for configuring MDM policies:</span></span> 

- <span data-ttu-id="14b87-174">Se você tiver uma diretiva configurada, você deve adicioná-lo por meio do aplicativo de gerenciamento do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14b87-174">If you have a policy configured, add it via the Device management app.</span></span> 
- <span data-ttu-id="14b87-175">Se você não tiver uma diretiva remoto configurada, temos um arquivo de pacote provisionados que pode ser carregado em uma chave USB.</span><span class="sxs-lookup"><span data-stu-id="14b87-175">If you do not have a remote policy configured, we have a provisioned package file that you can load onto an USB key.</span></span>

### <a name="device-management-configuration"></a><span data-ttu-id="14b87-176">Configuração de gerenciamento de dispositivo</span><span class="sxs-lookup"><span data-stu-id="14b87-176">Device management configuration</span></span>

<span data-ttu-id="14b87-177">O exemplo a seguir é um exemplo da adição de uma política MDM configurada em uma autoridade de MDM central.</span><span class="sxs-lookup"><span data-stu-id="14b87-177">The following is an example of adding an MDM policy configured from a central MDM authority.</span></span> <span data-ttu-id="14b87-178">Se você estiver na rede corporativa, você pode usar as seguintes instruções textual, incluindo a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="14b87-178">If you are on the corporate network, you can use the following instructions verbatim, including user account.</span></span> 
 
1. <span data-ttu-id="14b87-179">Na seção **Gerenciamento de dispositivo** , toque em **+**.</span><span class="sxs-lookup"><span data-stu-id="14b87-179">Under the **Device Management** section, tap **+**.</span></span><br>
   <span data-ttu-id="14b87-180">A caixa de diálogo **conectar ao trabalhar ou escola** será aberto.</span><span class="sxs-lookup"><span data-stu-id="14b87-180">The **Connect to work or school** dialog box will open.</span></span> 
2. <span data-ttu-id="14b87-181">Insira o endereço de email de diretiva e a senha, quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="14b87-181">Enter the policy e-mail address and password when prompted.</span></span><br>
   <span data-ttu-id="14b87-182">**Observação:**  Não há um bug do sistema operacional que não atualizar automaticamente a interface do usuário depois que você inseriu sua conta de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14b87-182">**NOTE:**  There's a bug in the OS that doesn't automatically refresh the UI after you've entered your device management account.</span></span> <span data-ttu-id="14b87-183">Você precisará feche e abra novamente as configurações para ver a conta listada.</span><span class="sxs-lookup"><span data-stu-id="14b87-183">You'll need to close and re-open settings in order to see the account listed.</span></span> 
3. <span data-ttu-id="14b87-184">Ele vai levar alguns minutos para as configurações de diretiva MDM sincronizar. Se desejar forçar uma sincronização, toque no botão de **conta MDM** e, em seguida, toque no botão **Info** .</span><span class="sxs-lookup"><span data-stu-id="14b87-184">It'll take a few minutes for the MDM policy settings to sync. If you want to force a sync, tap the **MDM account** button, and then tap the **Info** button.</span></span> <span data-ttu-id="14b87-185">Isso exibirá a janela de informações onde você pode toque em **sincronização**.</span><span class="sxs-lookup"><span data-stu-id="14b87-185">This will bring up the Info window where you can then tap **Sync**.</span></span> 
4. <span data-ttu-id="14b87-186">Para verificar se você tem o que você precisa, é possível verificar o registro.</span><span class="sxs-lookup"><span data-stu-id="14b87-186">To verify that you have what you need, you can check the registry.</span></span> <span data-ttu-id="14b87-187">Você deverá ver duas chaves em **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span><span class="sxs-lookup"><span data-stu-id="14b87-187">You should see two keys under **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**.</span></span> <br><br>
   <span data-ttu-id="14b87-188">O valor DWORD **VtcAppMeetingHandlingMode** indica que as equipes é o aplicativo padrão.</span><span class="sxs-lookup"><span data-stu-id="14b87-188">The **VtcAppMeetingHandlingMode** DWORD value indicates that Teams is the default app.</span></span> <span data-ttu-id="14b87-189">Os valores a seguir são reconhecidos.</span><span class="sxs-lookup"><span data-stu-id="14b87-189">The following values are recognized.</span></span> <br><br>
    |<span data-ttu-id="14b87-190">Número</span><span class="sxs-lookup"><span data-stu-id="14b87-190">Number</span></span> | <span data-ttu-id="14b87-191">Valor</span><span class="sxs-lookup"><span data-stu-id="14b87-191">Value</span></span>   |
    |-------|---------|
    |<span data-ttu-id="14b87-192">0</span><span class="sxs-lookup"><span data-stu-id="14b87-192">0</span></span>      | <span data-ttu-id="14b87-193">SkypePreferred</span><span class="sxs-lookup"><span data-stu-id="14b87-193">SkypePreferred</span></span>            |
    |<span data-ttu-id="14b87-194">1</span><span class="sxs-lookup"><span data-stu-id="14b87-194">1</span></span>      | <span data-ttu-id="14b87-195">VtcPreferred (equipes)</span><span class="sxs-lookup"><span data-stu-id="14b87-195">VtcPreferred (Teams)</span></span>      |
    |<span data-ttu-id="14b87-196">2</span><span class="sxs-lookup"><span data-stu-id="14b87-196">2</span></span>      | <span data-ttu-id="14b87-197">VtcExclusive (somente para equipes)</span><span class="sxs-lookup"><span data-stu-id="14b87-197">VtcExclusive (Teams only)</span></span> |

    <span data-ttu-id="14b87-198">O **VtcCallAppPackageId** é o nome do pacote equipes instalado.</span><span class="sxs-lookup"><span data-stu-id="14b87-198">The **VtcCallAppPackageId** is the name of the installed Teams package.</span></span> <span data-ttu-id="14b87-199">Se isso não for exibido, certifique-se de que ter instalado o pacote de equipes e resincronização.</span><span class="sxs-lookup"><span data-stu-id="14b87-199">If this doesn't show up, make sure you've installed the Teams package, and re-sync.</span></span> 
 
### <a name="configure-mdm-via-usb-key"></a><span data-ttu-id="14b87-200">Configurar MDM via chave USB</span><span class="sxs-lookup"><span data-stu-id="14b87-200">Configure MDM via USB key</span></span> 
 
<span data-ttu-id="14b87-201">Os pacotes podem ser encontrados na [página de download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="14b87-201">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="14b87-202">Selecione a adequada para o pacote que você estiver planejando instalar e copiá-lo para uma chave USB.</span><span class="sxs-lookup"><span data-stu-id="14b87-202">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="14b87-203">O arquivo .ppkg correto a ser usado depende do pacote de equipes que tenha sido instalado do repositório e a política que você gostaria de aplicar (Skype exclusivo, Skype preferencial, equipes preferenciais, exclusive equipes).</span><span class="sxs-lookup"><span data-stu-id="14b87-203">The correct .ppkg file to use depends on the Teams package that has been installed from the store, and the policy you'd like to apply (Skype exclusive, Skype preferred, Teams preferred, Teams exclusive).</span></span> 
 
1. <span data-ttu-id="14b87-204">Anexe a chave USB com o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="14b87-204">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="14b87-205">Abra o aplicativo de **configurações** em um dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="14b87-205">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="14b87-206">Abra o **gerenciamento de contas de dispositivo do Hub de superfície**.</span><span class="sxs-lookup"><span data-stu-id="14b87-206">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="14b87-207">Abra o **gerenciamento de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="14b87-207">Open **Device Management**.</span></span> 
5. <span data-ttu-id="14b87-208">Clique em **Adicionar ou remover um pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="14b87-208">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="14b87-209">Clique em **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="14b87-209">Click **Add Package**.</span></span>
7. <span data-ttu-id="14b87-210">Selecione a opção de **Mídia removível** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="14b87-210">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="14b87-211">Adicione o **Allowbuildspreview.ppkg**e, em seguida, selecione o pacote de superfície Hub que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="14b87-211">Add the **Allowbuildspreview.ppkg**, and then select the Surface Hub package you want to add.</span></span> 
9. <span data-ttu-id="14b87-212">Reinicie o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="14b87-212">Restart the Surface Hub device.</span></span> 

> [!NOTE]
> <span data-ttu-id="14b87-213">Se seu dispositivo ou dispositivos de sua organização não atualmente fazem parte do programa Insider Windows e você estiver nos países cobertos pela regulamentação de proteção de dados gerais (GDPR) (ou você tiver alterado manualmente suas configurações de telemetria para básico), em seguida, você deve verificar novamente que você tenha permitido telemetria completa antes de participar do programa Insider.</span><span class="sxs-lookup"><span data-stu-id="14b87-213">If your device or your organization's devices are not currently part of the Windows Insider Program and you are in countries covered by General Data Protection Regulation (GDPR) (or you have manually changed your telemetry settings to Basic), then you must re-check that you have permitted full telemetry before you join the Insider Program.</span></span> <span data-ttu-id="14b87-214">GDPR alterado o comportamento padrão de dispositivos de superfície Hub na UE para definir telemetria como básica.</span><span class="sxs-lookup"><span data-stu-id="14b87-214">GDPR changed the default behavior of Surface Hub devices in the EU to set telemetry to Basic.</span></span>