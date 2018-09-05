---
title: Implantar as equipes da Microsoft para o Hub de superfície
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
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
ms.openlocfilehash: aed0cc2b26fa55dcf47b2d90bbd974720c371663
ms.sourcegitcommit: 53c10589c284c6e4bbba574a7ba2df2d29519d1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2018
ms.locfileid: "23829262"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="1b2d2-103">Implantar as equipes da Microsoft para o Hub de superfície</span><span class="sxs-lookup"><span data-stu-id="1b2d2-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="1b2d2-104">Antes de implantar Teams da Microsoft para Microsoft Surface Hub, certifique-se de que você cumpre o hardware, sistema operacional e outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="1b2d2-105">Para obter mais informações, consulte o [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="1b2d2-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

## <a name="set-up-user-accounts"></a><span data-ttu-id="1b2d2-106">Configurar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="1b2d2-106">Set up user accounts</span></span>
 
<span data-ttu-id="1b2d2-107">Para configurar contas de usuário que podem ser usadas com equipes para o Hub de superfície, crie a conta de dispositivo como faria para suporte com Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-107">To set up user accounts that can be used with Teams for Surface Hub, create the device account as you would for support with Skype for Business.</span></span> <span data-ttu-id="1b2d2-108">A conta do dispositivo precisa ter a autenticação multifator desabilitada (para permitir o logon automático) para os seguintes serviços dependentes de equipes no Office 365:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-108">The device account needs to have multi-factor authentication disabled (to allow automatic logon) for the following dependent services of Teams in Office 365:</span></span>  
- <span data-ttu-id="1b2d2-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="1b2d2-109">Exchange</span></span> 
- <span data-ttu-id="1b2d2-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="1b2d2-110">SharePoint</span></span> 
- <span data-ttu-id="1b2d2-111">Aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="1b2d2-111">Office Apps</span></span> 

## <a name="add-a-device-account"></a><span data-ttu-id="1b2d2-112">Adicionar uma conta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="1b2d2-112">Add a device account</span></span> 

<span data-ttu-id="1b2d2-113">1 \.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-113">1\.</span></span> <span data-ttu-id="1b2d2-114">Inicie uma sessão remota do Windows PowerShell em um PC e se conectar ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-114">Start a remote Windows PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="1b2d2-115">Certifique-se de que você tem as permissões corretas definidas para executar os cmdlets associados.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-115">Be sure you have the correct permissions set to run the associated cmdlets.</span></span> <span data-ttu-id="1b2d2-116">Veja a seguir alguns exemplos de cmdlets que podem ser usados e modificados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-116">The following are some examples of cmdlets that can be used and modified in your environment.</span></span>

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

<span data-ttu-id="1b2d2-117">2 \.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-117">2\.</span></span> <span data-ttu-id="1b2d2-118">Depois de estabelecer uma sessão, você vai criar uma nova caixa de correio e habilitá-lo como um RoomMailboxAccount ou alterar as configurações de uma caixa de correio de sala existente.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-118">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="1b2d2-119">Isso permitirá a conta autenticar a equipes.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-119">This will allow the account to authenticate to Teams.</span></span>

<span data-ttu-id="1b2d2-120">Se você estiver alterando uma caixa de correio do recurso existente:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-120">If you are changing an existing resource mailbox:</span></span>

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="1b2d2-121">Se você criar uma nova caixa de correio para o recurso:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-121">If you’re creating a new resource mailbox:</span></span>

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="1b2d2-122">3\.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-122">3\.</span></span> <span data-ttu-id="1b2d2-123">Várias propriedades do Exchange deverão ser definidas na conta de dispositivo para aprimorar a experiência de reunião.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-123">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="1b2d2-124">Para saber quais propriedades precisam ser definidas, confira a seção Propriedades do Exchange.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-124">You can see which properties need to be set in the Exchange properties section.</span></span>

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

<span data-ttu-id="1b2d2-125">4\.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-125">4\.</span></span> <span data-ttu-id="1b2d2-126">Você deverá conectar-se ao Azure Active Directory para aplicar algumas configurações à conta.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-126">You will need to connect to Azure Active Directory to apply some account settings.</span></span> <span data-ttu-id="1b2d2-127">Para se conectar ao Azure AD, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-127">To connect to Azure AD, run the following cmdlet:</span></span>

```
Connect-MsolService -Credential $cred
```

<span data-ttu-id="1b2d2-128">5\.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-128">5\.</span></span> <span data-ttu-id="1b2d2-129">	Para a senha não expirar, execute o cmdlet Set-MsolUser com a opção PasswordNeverExpires, como a seguir:  </span><span class="sxs-lookup"><span data-stu-id="1b2d2-129">If you do not want the password to expire, run the Set-MsolUser cmdlet with the PasswordNeverExpires option as follows:</span></span> 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

<span data-ttu-id="1b2d2-130">Você também pode definir um número de telefone para a sala da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-130">You can also set a phone number for the room as follows:</span></span>

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

<span data-ttu-id="1b2d2-131">6\.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-131">6\.</span></span> <span data-ttu-id="1b2d2-132">A conta do dispositivo precisa ter uma licença válida do Office 365 ou Exchange e Skype para negócios não funcionará.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-132">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="1b2d2-133">Se você tem a licença, deve atribuir um local de uso à conta de dispositivo (isso determina quais SKUs de licença estão disponíveis para sua conta).</span><span class="sxs-lookup"><span data-stu-id="1b2d2-133">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="1b2d2-134">Você pode usar o Get-MsolAccountSku para recuperar uma lista de SKUs disponíveis para seu locatário do Office 365, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-134">You can use Get-MsolAccountSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>
 
```
Get-MsolAccountSku
```

<span data-ttu-id="1b2d2-p109">Em seguida, você pode adicionar uma licença usando o cmdlet Set-MsolUserLicense. Nesse caso, $strLicense é o código de SKU que você vê (por exemplo, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="1b2d2-p109">Next, you can add a license using the Set-MsolUserLicense cmdlet. In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

<span data-ttu-id="1b2d2-137">7\.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-137">7\.</span></span> <span data-ttu-id="1b2d2-138">Em seguida, você precisará habilitar a conta de dispositivo com equipes para o Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-138">Next, you need to enable the device account with Teams for Surface Hub.</span></span> <span data-ttu-id="1b2d2-139">Certifique-se de que seu ambiente atende aos requisitos definidos no [guia de administração do Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).</span><span class="sxs-lookup"><span data-stu-id="1b2d2-139">Be sure your environment meets the requirements defined in [Microsoft Surface Hub admin guide](https://docs.microsoft.com/en-us/surface-hub/).</span></span>

<span data-ttu-id="1b2d2-140">Iniciar uma sessão do Windows PowerShell remota da seguinte maneira (certifique-se de instalar o Skype para componentes de negócios Online PowerShell):</span><span class="sxs-lookup"><span data-stu-id="1b2d2-140">Start a remote Windows PowerShell session as follows (be sure to install Skype for Business Online PowerShell components):</span></span>

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

<span data-ttu-id="1b2d2-141">Em seguida, habilite suas equipes de conta do Hub de superfície executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-141">Next, enable your Teams for Surface Hub account by running the following cmdlet:</span></span>

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

<span data-ttu-id="1b2d2-142">Obtenha as informações de RegistrarPool da nova conta de usuário sendo instalação, como mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-142">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> <span data-ttu-id="1b2d2-143">Novas contas de usuário não podem ser criadas no mesmo pool do registrador contas de usuário existentes no inquilino.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-143">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="1b2d2-144">O comando acima evitará erros na configuração de conta devido a essa situação.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-144">The command above will prevent errors in account setup due to this situation.</span></span> 

<span data-ttu-id="1b2d2-145">Depois de concluir as etapas anteriores para permitir que as equipes de conta do Hub de superfície, você precisa atribuir uma licença para o dispositivo do Hub de superfície v2.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-145">After you've completed the preceding steps to enable your Teams for Surface Hub account, you need to assign a license to the Surface Hub v2 device.</span></span> <span data-ttu-id="1b2d2-146">Usando o portal administrativo do Office 365, atribua a equipes de licença do Hub de superfície para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-146">Using the Office 365 administrative portal, assign a Teams for Surface Hub license to the device.</span></span>

### <a name="assign-a-license-to-the-account"></a><span data-ttu-id="1b2d2-147">Atribuir uma licença para a conta</span><span class="sxs-lookup"><span data-stu-id="1b2d2-147">Assign a license to the account</span></span>

1. <span data-ttu-id="1b2d2-148">Faça logon como um administrador de locatários, abra o Centro de administração do Office 365 e clique no aplicativo Administração.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-148">Log on as a tenant administrator, open the Office 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="1b2d2-149">Clique em **usuários e grupos**e clique em **Adicionar usuários, redefinir senhas e muito mais**.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-149">Click **Users and Groups**, and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="1b2d2-150">Selecione as equipes de conta do Hub de superfície e, em seguida, clique ou toque no ícone de caneta, o que significa editar.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-150">Select the Teams for Surface Hub account, and then click or tap the pen icon, which means edit.</span></span>
4. <span data-ttu-id="1b2d2-151">Clique na opção de **licenças** .</span><span class="sxs-lookup"><span data-stu-id="1b2d2-151">Click the **Licenses** option.</span></span>
5. <span data-ttu-id="1b2d2-152">Na seção **Atribuir licenças** , você precisa selecionar o plano, dependendo do seu licenciamento.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-152">In the **Assign licenses** section, you need to select the plan, depending on your licensing.</span></span>
6. <span data-ttu-id="1b2d2-153">Clique em **Salvar** para concluir a tarefa.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-153">Click **Save** to complete the task.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="1b2d2-154">Instalar equipes para o Hub de superfície do repositório de Microsoft</span><span class="sxs-lookup"><span data-stu-id="1b2d2-154">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="1b2d2-155">Essas instruções são para a instalação de equipes para o Hub de superfície do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-155">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="1b2d2-156">Inicie o repositório da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-156">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="1b2d2-157">a.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-157">a.</span></span> <span data-ttu-id="1b2d2-158">Toque em **Iniciar** > **todos os aplicativos** > **configurações**.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-158">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="1b2d2-159">b.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-159">b.</span></span> <span data-ttu-id="1b2d2-160">Toque em **conta de dispositivo do Hub de superfície, gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-160">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="1b2d2-161">c.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-161">c.</span></span> <span data-ttu-id="1b2d2-162">À esquerda, toque em da guia **aplicativos e recursos** .</span><span class="sxs-lookup"><span data-stu-id="1b2d2-162">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="1b2d2-163">d.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-163">d.</span></span> <span data-ttu-id="1b2d2-164">À direita, toque no botão **Abrir armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="1b2d2-164">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="1b2d2-165">Do Microsoft Store, procure *As equipes da Microsoft*.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-165">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="1b2d2-166">As **Equipes da Microsoft para o Hub de superfície** será exibida.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-166">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="1b2d2-167">Toque no botão **obter o aplicativo** para instalar.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-167">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="1b2d2-168">Quando a instalação estiver concluída, reinicie o Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-168">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="1b2d2-169">Não toque no **início** do repositório de página de listagem.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-169">Do not tap on **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="1b2d2-170">Tornar as equipes a chamada padrão e a aplicação de reuniões</span><span class="sxs-lookup"><span data-stu-id="1b2d2-170">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="1b2d2-171">Há duas opções para configurar a política padrão de aplicativo de chamada e reuniões:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-171">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="1b2d2-172">**Opção 1**: configurar via chave USB.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-172">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="1b2d2-173">**Opção 2**: configurar via MDM como Intune.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-173">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="1b2d2-174">Opção 1: Configurar via chave USB</span><span class="sxs-lookup"><span data-stu-id="1b2d2-174">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="1b2d2-175">Os pacotes podem ser encontrados na [página de download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span><span class="sxs-lookup"><span data-stu-id="1b2d2-175">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="1b2d2-176">Selecione a adequada para o pacote que você estiver planejando instalar e copiá-lo para uma chave USB.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-176">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="1b2d2-177">O arquivo .ppkg correto a ser usado depende a diretiva de aplicação de padrão que você gostaria de aplicar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1b2d2-177">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="1b2d2-178">Número</span><span class="sxs-lookup"><span data-stu-id="1b2d2-178">Number</span></span>  |<span data-ttu-id="1b2d2-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b2d2-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1b2d2-180">0</span><span class="sxs-lookup"><span data-stu-id="1b2d2-180">0</span></span>     | <span data-ttu-id="1b2d2-181">App preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="1b2d2-181">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="1b2d2-182">1</span><span class="sxs-lookup"><span data-stu-id="1b2d2-182">1</span></span>     | <span data-ttu-id="1b2d2-183">As equipes de app preferencial na tela Iniciar, Skype reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="1b2d2-183">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="1b2d2-184">2</span><span class="sxs-lookup"><span data-stu-id="1b2d2-184">2</span></span>     | <span data-ttu-id="1b2d2-185">Equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível)</span><span class="sxs-lookup"><span data-stu-id="1b2d2-185">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="1b2d2-186">Anexe a chave USB com o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-186">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="1b2d2-187">Abra o aplicativo de **configurações** em um dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-187">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="1b2d2-188">Abra o **gerenciamento de contas de dispositivo do Hub de superfície**.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-188">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="1b2d2-189">Abra o **gerenciamento de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-189">Open **Device Management**.</span></span> 
5. <span data-ttu-id="1b2d2-190">Clique em **Adicionar ou remover um pacote de provisionamento**.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-190">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="1b2d2-191">Clique em **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-191">Click **Add Package**.</span></span>
7. <span data-ttu-id="1b2d2-192">Selecione a opção de **Mídia removível** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-192">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="1b2d2-193">Adicione o pacote adequado **TeamsRTMMode\*.ppkg** que anteriormente foi copiado para a chave USB.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-193">Add the appropriate **TeamsRTMMode\*.ppkg** package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="1b2d2-194">Reinicie o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-194">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="1b2d2-195">Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-195">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="1b2d2-196">Opção 2: Configurar via MDM como Intune</span><span class="sxs-lookup"><span data-stu-id="1b2d2-196">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="1b2d2-197">Use o seguinte para configurar a chamada e reuniões aplicativo política padrão via Intune.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-197">Use the following to configure the default calling and meetings application policy via Intune.</span></span>

<span data-ttu-id="1b2d2-198">.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-198"></span></span>

|<span data-ttu-id="1b2d2-199">Configuração</span><span class="sxs-lookup"><span data-stu-id="1b2d2-199">Setting</span></span>   |<span data-ttu-id="1b2d2-200">Valor</span><span class="sxs-lookup"><span data-stu-id="1b2d2-200">Value</span></span>    |<span data-ttu-id="1b2d2-201">Descrição</span><span class="sxs-lookup"><span data-stu-id="1b2d2-201">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="1b2d2-202">Path</span><span class="sxs-lookup"><span data-stu-id="1b2d2-202">Path</span></span>      | <span data-ttu-id="1b2d2-203">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="1b2d2-203">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="1b2d2-204">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1b2d2-204">Data Type</span></span> | <span data-ttu-id="1b2d2-205">inteiro (0-2)</span><span class="sxs-lookup"><span data-stu-id="1b2d2-205">integer (0-2)</span></span>   |<span data-ttu-id="1b2d2-206">0 - app preferencial do Skype na tela Iniciar, equipes de reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="1b2d2-206">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="1b2d2-207">1 - equipes preferencial app na tela Iniciar, Skype reuniões disponíveis</span><span class="sxs-lookup"><span data-stu-id="1b2d2-207">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="1b2d2-208">2 - equipes de aplicativo exclusivo na tela Iniciar (Skype app não disponível)</span><span class="sxs-lookup"><span data-stu-id="1b2d2-208">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="1b2d2-209">Operações</span><span class="sxs-lookup"><span data-stu-id="1b2d2-209">Operations</span></span>| <span data-ttu-id="1b2d2-210">Obter, definir</span><span class="sxs-lookup"><span data-stu-id="1b2d2-210">Get, Set</span></span>        |

|<span data-ttu-id="1b2d2-211">Configuração</span><span class="sxs-lookup"><span data-stu-id="1b2d2-211">Setting</span></span>   |<span data-ttu-id="1b2d2-212">Valor</span><span class="sxs-lookup"><span data-stu-id="1b2d2-212">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="1b2d2-213">Path</span><span class="sxs-lookup"><span data-stu-id="1b2d2-213">Path</span></span>      | <span data-ttu-id="1b2d2-214">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="1b2d2-214">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="1b2d2-215">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1b2d2-215">Data Type</span></span> | <span data-ttu-id="1b2d2-216">cadeia de caracteres - conjunto de cadeia de caracteres para a ID do pacote de aplicativo de equipes como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! As equipes**</span><span class="sxs-lookup"><span data-stu-id="1b2d2-216">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="1b2d2-217">Operações</span><span class="sxs-lookup"><span data-stu-id="1b2d2-217">Operations</span></span>| <span data-ttu-id="1b2d2-218">Obter, definir</span><span class="sxs-lookup"><span data-stu-id="1b2d2-218">Get, Set</span></span>        |

<span data-ttu-id="1b2d2-219">Reinicie o dispositivo do Hub de superfície.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-219">Restart the Surface Hub device.</span></span> <span data-ttu-id="1b2d2-220">Depois que o dispositivo for reiniciado, você poderá iniciar o aplicativo de equipes na tela de início e ingressar em uma reunião do calendário.</span><span class="sxs-lookup"><span data-stu-id="1b2d2-220">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

