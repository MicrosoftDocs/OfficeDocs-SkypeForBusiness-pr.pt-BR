---
title: Integração entre o Skype for Business Online e o servidor Exchange
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: A configuração da autenticação OAuth entre o Exchange local e o Skype for Business Online habilita os recursos de integração do Skype for Business e do Exchange descritos no Suporte a Recursos.
ms.openlocfilehash: ac8bfe2f30e813e47a0256a68e4e81852d5bae68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833971"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="2844e-103">Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2844e-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="2844e-104">Configurar a integração entre o servidor Do Exchange e o Skype for Business Online habilita os recursos de integração do Skype for Business e do Exchange descritos no [suporte a recursos.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="2844e-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="2844e-105">Este tópico se aplica à integração com o Exchange Server 2013 a 2019.</span><span class="sxs-lookup"><span data-stu-id="2844e-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2844e-106">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="2844e-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2844e-107">Tempo estimado para a conclusão da tarefa: 15 minutos</span><span class="sxs-lookup"><span data-stu-id="2844e-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="2844e-108">Para executar este procedimento ou estes procedimentos, você precisa receber permissões.</span><span class="sxs-lookup"><span data-stu-id="2844e-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="2844e-109">Para ver de que permissões você precisa, consulte o tópico de permissões de infraestrutura do [Exchange e do Shell.](https://go.microsoft.com/fwlink/p/?LinkId=746511)</span><span class="sxs-lookup"><span data-stu-id="2844e-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="2844e-110">Para informações sobre atalhos de teclado que possam se aplicar aos procedimentos neste tópico, consulte [Atalhos de teclado no Centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="2844e-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="2844e-111">Para saber mais sobre compatibilidade, confira [a compatibilidade do Skype for Business com aplicativos do Office.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)</span><span class="sxs-lookup"><span data-stu-id="2844e-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="2844e-112">Configurar a integração entre o Exchange Server e o O365</span><span class="sxs-lookup"><span data-stu-id="2844e-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="2844e-113">Etapa 1: Configurar a autenticação OAuth entre o Exchange Server e o O365</span><span class="sxs-lookup"><span data-stu-id="2844e-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="2844e-114">Execute as etapas no seguinte artigo:</span><span class="sxs-lookup"><span data-stu-id="2844e-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="2844e-115">Configurar a autenticação OAuth entre organizações do Exchange e do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2844e-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="2844e-116">Etapa 2: Criar uma nova conta de usuário de email para o Aplicativo de Parceiro do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2844e-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="2844e-117">Esta etapa é realizada no servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2844e-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="2844e-118">Ele criará um usuário de email e atribuirá a ele os direitos de função de gerenciamento apropriados.</span><span class="sxs-lookup"><span data-stu-id="2844e-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="2844e-119">Essa conta será usada na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="2844e-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="2844e-120">Especifique um domínio verificado para sua organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="2844e-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="2844e-121">Esse domínio deve ser o mesmo usado como o domínio SMTP principal usado para as contas locais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="2844e-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="2844e-122">Esse domínio é conhecido \<your Verified Domain\> como no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="2844e-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="2844e-123">Além disso, \<DomainControllerFQDN\> ele deve ser o FQDN de um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="2844e-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="2844e-124">Este comando ocultará o novo usuário de email das listas de endereços.</span><span class="sxs-lookup"><span data-stu-id="2844e-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="2844e-125">Esses próximos dois comandos atribuirão a função de gerenciamento UserApplication e ArchiveApplication a essa nova conta.</span><span class="sxs-lookup"><span data-stu-id="2844e-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="2844e-126">Etapa 3: Criar e habilitar um aplicativo parceiro para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2844e-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="2844e-127">Crie um novo aplicativo parceiro e usará a conta que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="2844e-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="2844e-128">Execute o seguinte comando no Exchange PowerShell em sua organização local do Exchange.</span><span class="sxs-lookup"><span data-stu-id="2844e-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="2844e-129">Etapa 4: Exportar o certificado de autorização local</span><span class="sxs-lookup"><span data-stu-id="2844e-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="2844e-130">Execute um script do PowerShell para exportar o certificado de autorização local, que você importa para sua organização do Skype for Business Online na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="2844e-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="2844e-131">Salve o seguinte texto em um script do PowerShell chamado, por exemplo, de ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="2844e-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

<span data-ttu-id="2844e-132">No Exchange PowerShell em sua organização local do Exchange, execute o script do PowerShell que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="2844e-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="2844e-133">Por exemplo: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="2844e-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="2844e-134">Etapa 5: Carregar o certificado de autorização local para o Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="2844e-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="2844e-135">Em seguida, use o Windows PowerShell para carregar o certificado de autorização local que você exportou na etapa anterior para os Serviços de Controle de Acesso (ACS) do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2844e-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="2844e-136">Para fazer isso, o Módulo Azure Active Directory para cmdlets do Windows PowerShell já deve estar instalado.</span><span class="sxs-lookup"><span data-stu-id="2844e-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="2844e-137">Se ele não estiver instalado, vá para instalar o [https://aka.ms/aadposh](https://aka.ms/aadposh) Módulo Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2844e-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="2844e-138">Conclua as etapas a seguir após a instalação do Módulo Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2844e-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="2844e-139">Clique no **módulo Azure Active Directory** para o atalho do Windows PowerShell para abrir um espaço de trabalho do Windows PowerShell que tenha os cmdlets do Azure AD instalados.</span><span class="sxs-lookup"><span data-stu-id="2844e-139">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed.</span></span> <span data-ttu-id="2844e-140">Todos os comandos nesta etapa serão executados usando o Windows PowerShell para console do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2844e-140">All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="2844e-141">Salve o texto a seguir em um arquivo de script do PowerShell chamado, por exemplo,  `UploadAuthCert.ps1` .</span><span class="sxs-lookup"><span data-stu-id="2844e-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="2844e-142">Execute o script do PowerShell criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="2844e-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="2844e-143">Por exemplo:  `.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="2844e-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="2844e-144">Depois de iniciar o script, uma caixa de diálogo de credenciais é exibida.</span><span class="sxs-lookup"><span data-stu-id="2844e-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="2844e-145">Insira as credenciais para a conta de administrador de locatários da sua organização do Microsoft Online Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2844e-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="2844e-146">Depois de executar o script, deixe a sessão do Windows PowerShell para Azure AD aberta.</span><span class="sxs-lookup"><span data-stu-id="2844e-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="2844e-147">Você usará isso para executar um script do PowerShell na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="2844e-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="2844e-148">Etapa 6: Verificar se o certificado foi carregado para a entidade de serviço do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2844e-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="2844e-149">No PowerShell aberto e autenticado no Azure Active Directory, execute o seguinte</span><span class="sxs-lookup"><span data-stu-id="2844e-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="2844e-150">Pressione Enter quando solicitado para ReturnKeyValues</span><span class="sxs-lookup"><span data-stu-id="2844e-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="2844e-151">Confirme se você vê uma chave listada com dados de data de início e término que corresponde às datas de início e término do certificado Oauth do Exchange</span><span class="sxs-lookup"><span data-stu-id="2844e-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="2844e-152">Verificar seu sucesso</span><span class="sxs-lookup"><span data-stu-id="2844e-152">Verify your success</span></span>

<span data-ttu-id="2844e-153">Verifique se a configuração está correta verificando se alguns dos recursos estão funcionando com êxito.</span><span class="sxs-lookup"><span data-stu-id="2844e-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="2844e-154">Confirme se os usuários do Skype for Business com o serviço de Caixa Postal na Nuvem, em uma organização com uma configuração híbrida do Exchange Server, podem alterar com êxito suas saudações da caixa postal.</span><span class="sxs-lookup"><span data-stu-id="2844e-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="2844e-155">Confirme se o histórico da conversa para clientes móveis está visível na pasta Histórico da Conversa do Outlook.</span><span class="sxs-lookup"><span data-stu-id="2844e-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="2844e-156">Confirme se as mensagens de chat arquivadas são depositadas na caixa de correio local do usuário na pasta Limpezas usando [eWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span><span class="sxs-lookup"><span data-stu-id="2844e-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="2844e-157">Como alternativa, veja seu tráfego.</span><span class="sxs-lookup"><span data-stu-id="2844e-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="2844e-158">O tráfego em um handshake do OAuth é realmente distinto (e não se parece com a autenticação básica), especialmente ao redor de realms, onde você começará a ver o tráfego do emissor com esta aparência: 00000004-0000-0ff1-ce00-000000000000@ (às vezes com um /antes do sinal @), nos tokens que estão sendo passados.</span><span class="sxs-lookup"><span data-stu-id="2844e-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="2844e-159">Você não verá um nome de usuário ou senha, que é o ponto do OAuth.</span><span class="sxs-lookup"><span data-stu-id="2844e-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="2844e-160">Mas você verá o emissor do "Office" – neste caso "4" é o Skype for Business – e o realm da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="2844e-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="2844e-161">Se você quiser ter certeza de que está usando o OAuth com êxito, certifique-se de que sabe o que esperar e sabe qual deve ser a aparência do tráfego.</span><span class="sxs-lookup"><span data-stu-id="2844e-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="2844e-162">Portanto, aqui está o que [esperar,](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)aqui está um exemplo bastante padrão do tráfego [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  em um aplicativo da Microsoft (muito útil para ler, embora ele não use tokens de atualização) e há extensões Fiddler que permitirão que você procure em seu JWT OAuth (Token Web JSON).</span><span class="sxs-lookup"><span data-stu-id="2844e-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="2844e-163">Aqui está um [exemplo de configuração,](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)mas você pode usar qualquer ferramenta de rastreamento de rede que você gosta para realizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="2844e-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2844e-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2844e-164">Related topics</span></span>

[<span data-ttu-id="2844e-165">Configurar a autenticação OAuth entre organizações do Exchange e do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2844e-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
