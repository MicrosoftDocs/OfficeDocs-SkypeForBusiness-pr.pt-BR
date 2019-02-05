---
title: Configurar OAuth entre o Skype for Business Online e o Exchange no local
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configurando o OAuth a autenticação entre o Exchange no local e Skype para Business Online permite que o Skype para recursos de integração do Exchange e de negócios descritos no suporte ao recurso.
ms.openlocfilehash: f6108842f827cbb9cfb6761495c4787ed2b7868b
ms.sourcegitcommit: fddb1d6798e7a716ad87b0613f45a76deff6a043
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2019
ms.locfileid: "29735171"
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a><span data-ttu-id="991ea-103">Configurar OAuth entre o Skype for Business Online e o Exchange no local</span><span class="sxs-lookup"><span data-stu-id="991ea-103">Configure OAuth between Skype for Business Online and Exchange on premises</span></span>

<span data-ttu-id="991ea-104">Configurando o OAuth a autenticação entre o Exchange no local e Skype para Business Online permite que o Skype para recursos de integração do Exchange e de negócios descritos em [suporte de recurso](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="991ea-104">Configuring OAuth authentication between Exchange on premises and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="991ea-105">Este tópico se aplica ao Exchange Server 2016 e Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="991ea-105">This topic applies to Exchange Server 2016 and Exchange Server 2013.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="991ea-106">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="991ea-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="991ea-107">Tempo estimado para concluir esta tarefa: 15 minutos</span><span class="sxs-lookup"><span data-stu-id="991ea-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="991ea-108">Você precisa receber permissões antes de realizar esse procedimento ou procedimentos.</span><span class="sxs-lookup"><span data-stu-id="991ea-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="991ea-109">Para ver quais permissões você precisa, consulte o tópico [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="991ea-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="991ea-110">Para obter informações sobre os atalhos do teclado que podem ser aplicados aos procedimentos deste tópico, consulte [Atalhos de teclado no centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="991ea-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a><span data-ttu-id="991ea-111">Configure a autenticação de OAuth entre seu Exchange local e as empresas com Skype for Business</span><span class="sxs-lookup"><span data-stu-id="991ea-111">Configure OAuth authentication between your on-premises Exchange and Skype for Business organizations</span></span>

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a><span data-ttu-id="991ea-112">Etapa 1: crie um objeto do servidor de autorização para sua organização do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="991ea-112">Step 1: Create an authorization server object for your Skype for Business Online organization</span></span>

<span data-ttu-id="991ea-113">Especifique um domínio verificado para seu Skype para a organização Business Online.</span><span class="sxs-lookup"><span data-stu-id="991ea-113">Specify a verified domain for your Skype for Business Online organization.</span></span> <span data-ttu-id="991ea-114">Esse domínio deve ser o mesmo que o domínio SIP primário utilizado para o modelo de contas baseadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="991ea-114">This domain should be the same domain used as the primary SIP domain used for the cloud-based accounts.</span></span> <span data-ttu-id="991ea-115">Este domínio é conhecido como \<seu domínio verificado\> no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="991ea-115">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>

<span data-ttu-id="991ea-116">Execute o seguinte comando no Shell de gerenciamento do Exchange (o Exchange PowerShell) no seu local de organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="991ea-116">Run the following command in the Exchange Management Shell (the Exchange PowerShell) in your on-premises Exchange organization.</span></span>

```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1"
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a><span data-ttu-id="991ea-117">Etapa 2: habilite o aplicativo parceiro para sua organização do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="991ea-117">Step 2: Enable the partner application for your Skype for Business Online organization</span></span>

<span data-ttu-id="991ea-118">Execute o seguinte comando no Exchange PowerShell em seu local de organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="991ea-118">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="991ea-119">Etapa 3: crie uma nova conta de Usuário de Email para o aplicativo parceiro do Skype for Business Online </span><span class="sxs-lookup"><span data-stu-id="991ea-119">Step 3: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="991ea-p103">Esta etapa é realizada no local. Ela criará um usuário de caixa de correio e atribuirá os direitos apropriados da função de gerenciamento. Essa conta será então usada na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="991ea-p103">This step is done on-premises. It will create a mail user and assign it the appropriate management role rights. This account will then be used in the next step.</span></span>

<span data-ttu-id="991ea-123">Especifique um domínio verificado para sua organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="991ea-123">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="991ea-124">Esse domínio deve ser o mesmo usado como o domínio SMTP primário usado para as contas do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="991ea-124">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="991ea-125">Este domínio é conhecido como \<seu domínio verificado\> no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="991ea-125">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="991ea-126">Além disso, o \<DomainControllerFQDN\> deve ser o FQDN de um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="991ea-126">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="991ea-127">Esse comando ocultará o novo usuário da caixa de correio das listas de endereços.</span><span class="sxs-lookup"><span data-stu-id="991ea-127">This command will hide the new mail user from address lists.</span></span>

```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="991ea-128">Esses dois próximos comandos atribuirão a função de gerenciamento de UserApplication e ArchiveApplication a esta nova conta.</span><span class="sxs-lookup"><span data-stu-id="991ea-128">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="991ea-129">Etapa 4: crie e habilite um aplicativo parceiro para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="991ea-129">Step 4: Create and enable a Partner Application for Skype for Business Online</span></span>

<span data-ttu-id="991ea-130">Crie um novo aplicativo parceiro e use a conta que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="991ea-130">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="991ea-131">Execute o seguinte comando no Exchange PowerShell em seu local de organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="991ea-131">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="991ea-132">Etapa 5: Exportar o certificado de autorização local</span><span class="sxs-lookup"><span data-stu-id="991ea-132">Step 5: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="991ea-133">Execute um script do PowerShell para exportar o certificado de autorização local, que você importará para seu Skype para a organização Business Online na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="991ea-133">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="991ea-134">Salve o seguinte texto em um arquivo de script do PowerShell denominado, por exemplo, ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="991ea-134">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```
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

<span data-ttu-id="991ea-135">No Exchange PowerShell em sua organização do Exchange local, execute o script do PowerShell que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="991ea-135">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="991ea-136">Por exemplo:.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="991ea-136">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="991ea-137">Etapa 6: carregar o certificado de autorização local para o Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="991ea-137">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="991ea-138">Em seguida, utilize o Windows PowerShell para carregar o certificado de autorização local que você exportou na etapa anterior no Serviço de Controle de Acesso do Azure Active Directory (ACS).</span><span class="sxs-lookup"><span data-stu-id="991ea-138">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="991ea-139">Para fazer isso, o Módulo Azure Active Directory para cmdlets do Windows PowerShell já deve estar instalado.</span><span class="sxs-lookup"><span data-stu-id="991ea-139">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="991ea-140">Se não estiver instalado, vá para [https://aka.ms/aadposh](https://aka.ms/aadposh) para instalar o Windows Azure Active Directory módulo para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="991ea-140">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="991ea-141">Conclua as etapas a seguir após a instalação do módulo Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="991ea-141">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="991ea-p108">Clique no atalho do **Módulo Azure Active Directory para Windows PowerShell** para abrir um espaço de trabalho do Windows PowerShell que possui os cmdlets do Azure AD instalado. Todos os comandos nesta etapa serão executados utilizando-se o Windows PowerShell para console do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="991ea-p108">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="991ea-144">Salve o seguinte texto em um arquivo de script do PowerShell chamado, por exemplo, `UploadAuthCert.ps1`.</span><span class="sxs-lookup"><span data-stu-id="991ea-144">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```
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

3. <span data-ttu-id="991ea-145">Execute o script do PowerShell criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="991ea-145">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="991ea-146">Por exemplo:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="991ea-146">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="991ea-p110">Depois de iniciar o script, uma caixa de diálogo de credenciais será exibida. Insira as credenciais para a conta do administrador do locatário de sua empresa Microsoft Online Azure AD. Depois de executar o script, deixe a sessão Windows PowerShell para Azure AD aberta. Você a utilizará para executar um script do PowerShell na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="991ea-p110">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a><span data-ttu-id="991ea-151">Passo 7: registrar as autoridades do nome do host para o domínio SMTP</span><span class="sxs-lookup"><span data-stu-id="991ea-151">Step 7: Register the hostname authorities for the SMTP domain</span></span>

<span data-ttu-id="991ea-152">Especifique um domínio verificado para sua organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="991ea-152">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="991ea-153">Esse domínio deve ser o mesmo usado como o domínio SMTP primário usado para as contas do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="991ea-153">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="991ea-154">Este domínio é conhecido como \<seu domínio verificado\> no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="991ea-154">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="991ea-155">A execução bem sucedida do script a seguir requer que o Windows PowerShell para Azure Active Directory esteja conectado ao seu locatário do Microsoft Online Azure AD, conforme explicado na etapa 4 na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="991ea-155">Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.</span></span>

1. <span data-ttu-id="991ea-156">Salve o texto a seguir em um arquivo de script do PowerShell denominado, por exemplo, RegisterEndpoints.ps1.</span><span class="sxs-lookup"><span data-stu-id="991ea-156">Save the following text to a PowerShell script file named, for example, RegisterEndpoints.ps1.</span></span> <span data-ttu-id="991ea-157">Este exemplo usa um curinga para registrar todos os pontos de extremidade para contoso.com.</span><span class="sxs-lookup"><span data-stu-id="991ea-157">This example uses a wildcard to register all endpoints for contoso.com.</span></span> <span data-ttu-id="991ea-158">Substitua contoso.com por uma autoridade de nome de host para a sua organização do Exchange local</span><span class="sxs-lookup"><span data-stu-id="991ea-158">Replace contoso.com with a hostname authority for your on-premises Exchange organization</span></span>

   ```
   $externalAuthority="*.<your Verified Domain>"
   $ServiceName = "00000002-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName;
   $spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority);
   $p.ServicePrincipalNames.Add($spn);
   Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames;
   ```

2. <span data-ttu-id="991ea-159">No Windows PowerShell para Azure Active Directory, execute o script do Windows PowerShell que você criou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="991ea-159">In Windows PowerShell for Azure Active Directory, run the Windows PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="991ea-160">Por exemplo: `.\RegisterEndpoints.ps1`</span><span class="sxs-lookup"><span data-stu-id="991ea-160">For example: `.\RegisterEndpoints.ps1`</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="991ea-161">Verifique se a operação foi realizada com sucesso</span><span class="sxs-lookup"><span data-stu-id="991ea-161">Verify your success</span></span>

<span data-ttu-id="991ea-162">Verifique se a configuração do OAuth está correta verificando se alguns recursos estão funcionando com êxito, como obtenção do histórico de conversa para clientes móveis visíveis na pasta Histórico de Conversas do Outlook.</span><span class="sxs-lookup"><span data-stu-id="991ea-162">Verify that the OAuth configuration is correct by verifying some of the features are working successfully, such as having conversation history for mobile clients visible in the Outlook Conversation History folder.</span></span>

1. <span data-ttu-id="991ea-163">Inicie o Skype para aplicativos móveis de negócios no seu Windows Phone ou dispositivo iOS e entrar como um Skype para usuário Business Online com um Exchange 2016 ou caixa de correio do Exchange 2013 local.</span><span class="sxs-lookup"><span data-stu-id="991ea-163">Start the Skype for Business mobile app on your Windows Phone or iOS device and sign in as a Skype for Business Online user with an Exchange 2016 or Exchange 2013 on-premises mailbox.</span></span>

2. <span data-ttu-id="991ea-164">Ter uma conversa de mensagem instantânea com outro Skype para usuário Business Online.</span><span class="sxs-lookup"><span data-stu-id="991ea-164">Have an instant messaging conversation with another Skype for Business Online user.</span></span>

3. <span data-ttu-id="991ea-165">Fechar a janela de Conversa IM.</span><span class="sxs-lookup"><span data-stu-id="991ea-165">Close the IM conversation window.</span></span>

4. <span data-ttu-id="991ea-166">Inicie o Outlook para este usuário e verifique se a conversa está visível na pasta Histórico de Conversas do Outlook.</span><span class="sxs-lookup"><span data-stu-id="991ea-166">Start Outlook for this user and verify that the conversation is visible in the Outlook Conversation history folder.</span></span>

<span data-ttu-id="991ea-167">Como alternativa, examine o tráfego.</span><span class="sxs-lookup"><span data-stu-id="991ea-167">Alternately, look at your traffic.</span></span> <span data-ttu-id="991ea-168">O tráfego em um handshake OAuth é realmente característica (e não se parece com a autenticação básica), especialmente ao redor territórios, onde você vai começar a ver o tráfego de emissor parecida com esta: 00000004-0000-0ff1-ce00-000000000000 @ (às vezes com uma / antes o sinal @), em que estão sendo passados tokens.</span><span class="sxs-lookup"><span data-stu-id="991ea-168">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="991ea-169">Você não verá um nome de usuário ou senha, que é o ponto do OAuth.</span><span class="sxs-lookup"><span data-stu-id="991ea-169">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="991ea-170">Mas você verá o emissor 'Temporária' – nesse caso, '4' é Skype para negócios – e o território de sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="991ea-170">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="991ea-171">Se você quiser ter certeza de que você estiver usando o OAuth com êxito, certifique-se de que você sabe o que esperar e quando já souber o que o tráfego deve se parecer com.</span><span class="sxs-lookup"><span data-stu-id="991ea-171">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="991ea-172">Caso [aqui está o que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aqui está um bem standard [exemplo de tráfego de OAuth em um aplicativo da Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (realmente úteis para mensagens lidas, embora não use Refresh tokens) e existem extensões Fiddler que permitirá que você procure em seu OAuth JWT (JSON Token de Web).</span><span class="sxs-lookup"><span data-stu-id="991ea-172">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="991ea-173">Aqui está um [exemplo de configuração de um](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mas você pode usar qualquer ferramenta de rastreamento de rede que você deseja realizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="991ea-173">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>
