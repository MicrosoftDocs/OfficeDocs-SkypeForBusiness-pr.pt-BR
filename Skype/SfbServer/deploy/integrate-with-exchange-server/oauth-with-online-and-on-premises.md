---
title: Integração entre o Skype for Business Online e o Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: A configuração da autenticação OAuth entre o Exchange local e o Skype for Business Online permite que os recursos de integração do Skype for Business e do Exchange descritos em suporte a recursos.
ms.openlocfilehash: fe6d7bbe1be9418b7e960de02e91cecf1c808d2b
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715803"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="ea5ac-103">Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ea5ac-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="ea5ac-104">A configuração da integração entre o Exchange Server e o Skype for Business Online permite que os recursos de integração do Skype for Business e do Exchange descritos em [suporte a recursos](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="ea5ac-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="ea5ac-105">Este tópico se aplica à integração com o Exchange Server 2013 a 2019.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ea5ac-106">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="ea5ac-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ea5ac-107">Tempo estimado para concluir esta tarefa: 15 minutos</span><span class="sxs-lookup"><span data-stu-id="ea5ac-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="ea5ac-108">Você precisa receber permissões antes de realizar esse procedimento ou procedimentos.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="ea5ac-109">Para ver quais permissões você precisa, consulte o tópico [permissões de infraestrutura do Shell e do Exchange](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="ea5ac-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="ea5ac-110">Para obter informações sobre os atalhos de teclado que podem ser aplicáveis aos procedimentos deste tópico, consulte [atalhos de teclado no centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="ea5ac-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="ea5ac-111">Para obter informações sobre compatibilidade, confira [compatibilidade do Skype for Business com os aplicativos do Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span><span class="sxs-lookup"><span data-stu-id="ea5ac-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="ea5ac-112">Configurar a integração entre o Exchange Server e o O365</span><span class="sxs-lookup"><span data-stu-id="ea5ac-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="ea5ac-113">Etapa 1: configurar a autenticação OAuth entre o Exchange Server e o O365</span><span class="sxs-lookup"><span data-stu-id="ea5ac-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="ea5ac-114">Execute as etapas do seguinte artigo:</span><span class="sxs-lookup"><span data-stu-id="ea5ac-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="ea5ac-115">Configurar a autenticação OAuth entre organizações Exchange e Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea5ac-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="ea5ac-116">Etapa 2: criar uma nova conta de usuário de email para o aplicativo para parceiros do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ea5ac-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="ea5ac-117">Esta etapa é feita no Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="ea5ac-118">Ela criará um usuário de caixa de correio e atribuirá os direitos apropriados da função de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="ea5ac-119">Essa conta será então usada na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="ea5ac-120">Especifique um domínio verificado para sua organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="ea5ac-121">Esse domínio deve ser o mesmo usado como o domínio SMTP principal usado para as contas do Exchange no local.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="ea5ac-122">Esse domínio é chamado \<de domínio\> verificado no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="ea5ac-123">Além disso, \<o\> DOMAINCONTROLLERFQDN deve ser o FQDN de um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="ea5ac-124">Esse comando ocultará o novo usuário da caixa de correio das listas de endereços.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-124">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="ea5ac-125">Esses dois próximos comandos atribuirão a função de gerenciamento de UserApplication e ArchiveApplication a esta nova conta.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="ea5ac-126">Etapa 3: criar e habilitar um aplicativo parceiro para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ea5ac-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="ea5ac-127">Crie um novo aplicativo parceiro e use a conta que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="ea5ac-128">Execute o seguinte comando no PowerShell do Exchange em sua organização do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="ea5ac-129">Etapa 4: exportar o certificado de autorização local</span><span class="sxs-lookup"><span data-stu-id="ea5ac-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="ea5ac-130">Execute um script do PowerShell para exportar o certificado de autorização local, que você vai importar para sua organização do Skype for Business online na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="ea5ac-131">Salve o seguinte texto em um arquivo de script do PowerShell denominado, por exemplo, ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

``` Powershell
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

<span data-ttu-id="ea5ac-132">No Exchange PowerShell em sua organização do Exchange local, execute o script do PowerShell que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="ea5ac-133">Por exemplo: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="ea5ac-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="ea5ac-134">Etapa 6: carregar o certificado de autorização local para o Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="ea5ac-134">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="ea5ac-135">Em seguida, utilize o Windows PowerShell para carregar o certificado de autorização local que você exportou na etapa anterior no Serviço de Controle de Acesso do Azure Active Directory (ACS).</span><span class="sxs-lookup"><span data-stu-id="ea5ac-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="ea5ac-136">Para fazer isso, o Módulo Azure Active Directory para cmdlets do Windows PowerShell já deve estar instalado.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="ea5ac-137">Se não estiver instalado, vá para [https://aka.ms/aadposh](https://aka.ms/aadposh) instalar o módulo Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="ea5ac-138">Conclua as etapas a seguir após a instalação do módulo Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="ea5ac-p107">Clique no atalho do **Módulo Azure Active Directory para Windows PowerShell** para abrir um espaço de trabalho do Windows PowerShell que possui os cmdlets do Azure AD instalado. Todos os comandos nesta etapa serão executados utilizando-se o Windows PowerShell para console do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="ea5ac-141">Salve o seguinte texto em um arquivo de script do PowerShell chamado, por `UploadAuthCert.ps1`exemplo,.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ``` Powershell
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

3. <span data-ttu-id="ea5ac-142">Execute o script do PowerShell criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="ea5ac-143">Por exemplo:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="ea5ac-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="ea5ac-p109">Depois de iniciar o script, uma caixa de diálogo de credenciais será exibida. Insira as credenciais para a conta do administrador do locatário de sua empresa Microsoft Online Azure AD. Depois de executar o script, deixe a sessão Windows PowerShell para Azure AD aberta. Você a utilizará para executar um script do PowerShell na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-p109">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-7-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="ea5ac-148">Etapa 7: Verifique se o certificado foi carregado na entidade de serviço do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea5ac-148">Step 7: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="ea5ac-149">No PowerShell aberto e autenticado para o Azure Active Directory, execute o seguinte</span><span class="sxs-lookup"><span data-stu-id="ea5ac-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="ea5ac-150">Pressione Enter quando solicitado para ReturnKeyValues</span><span class="sxs-lookup"><span data-stu-id="ea5ac-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="ea5ac-151">Confirme que você vê uma chave listada com data de início e dados finais que correspondem às datas de início e término do certificado OAuth do Exchange</span><span class="sxs-lookup"><span data-stu-id="ea5ac-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="ea5ac-152">Verifique se a operação foi realizada com sucesso</span><span class="sxs-lookup"><span data-stu-id="ea5ac-152">Verify your success</span></span>

<span data-ttu-id="ea5ac-153">Verifique se a configuração está correta verificando se alguns dos recursos estão funcionando com êxito.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="ea5ac-154">Confirme se os usuários do Skype for Business com serviço de correio de voz na nuvem, em uma organização com uma configuração híbrida do Exchange Server, podem alterar suas saudações de correio de voz com êxito.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="ea5ac-155">Confirme se o histórico de conversas para clientes móveis está visível na pasta Histórico de conversas do Outlook.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="ea5ac-156">Confirme se as mensagens de chat arquivadas são depositadas na caixa de correio local do usuário na pasta Purges usando o [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span><span class="sxs-lookup"><span data-stu-id="ea5ac-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="ea5ac-157">Como alternativa, examine seu tráfego.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="ea5ac-158">O tráfego em um handshake OAuth é realmente distintivo (e não se parece com autenticação básica), especialmente em relação a territórios, onde você começará a ver o tráfego do emissor que tem a seguinte aparência: 00000004-0000-0ff1-ce00-000000000000 @ (às vezes com/antes o símbolo @), nos tokens que estão sendo passados.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="ea5ac-159">Você não verá um nome de usuário ou senha, que é o ponto de OAuth.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="ea5ac-160">Mas você verá o emissor "Office" – neste caso, ' 4 ' é o Skype for Business – e o território da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="ea5ac-161">Se você quiser ter certeza de que está usando o OAuth com êxito, verifique se sabe o que esperar e saiba para que tal tráfego deve ser exibido.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="ea5ac-162">Portanto, [Veja o que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aqui está um exemplo bem padrão [de tráfego OAuth em um aplicativo da Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (muito útil para ler, embora não use tokens de atualização), e existem extensões Fiddler que permitem que você examine seu JWT OAuth (JSON Token da Web).</span><span class="sxs-lookup"><span data-stu-id="ea5ac-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="ea5ac-163">Veja um [exemplo de](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)como configurar um, mas você pode usar qualquer ferramenta de rastreamento de rede que você queira para empreender esse processo.</span><span class="sxs-lookup"><span data-stu-id="ea5ac-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ea5ac-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ea5ac-164">Related topics</span></span>

[<span data-ttu-id="ea5ac-165">Configurar a autenticação OAuth entre organizações Exchange e Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea5ac-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
