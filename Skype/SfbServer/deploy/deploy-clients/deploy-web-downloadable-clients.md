---
title: Implantar clientes para download da Web no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumo: Implante o Skype para negócios Web App e Skype App de reuniões usado com Skype para negócios.'
ms.openlocfilehash: 216d1a3bc82c3845a8302847c3488dd9f495fa74
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20995838"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="318f6-103">Implantar clientes para download da Web no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="318f6-103">Deploy Web downloadable clients in Skype for Business Server</span></span>
 
<span data-ttu-id="318f6-104">**Resumo:** Implante o Skype para negócios 2015 Web App e Skype reuniões App usado com Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="318f6-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="318f6-105">Skype para negócios Web App é um cliente de web do Internet Information Services (IIS) que está instalado no servidor que executa o Skype para Business Server 2015 e por padrão, ele é implantado por demanda aos usuários de reunião que ainda não tiver o Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="318f6-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server 2015 and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="318f6-106">Esses usuários de reunião são mais frequência que não se conectando de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="318f6-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="318f6-107">Sempre que um usuário clica em uma URL de reunião, mas não tem o Skype para o cliente de negócios instalado, o usuário é apresentado com a opção para ingressar na reunião usando a versão mais recente do Skype para negócios Web App ou aplicativo de reuniões do Skype.</span><span class="sxs-lookup"><span data-stu-id="318f6-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App or Skype Meetings App.</span></span>
  
<span data-ttu-id="318f6-108">Recursos de voz, vídeo e compartilhamento em Skype para negócios Web App requerem um controle Microsoft ActiveX que é usado como um plug-in pelo navegador do usuário.</span><span class="sxs-lookup"><span data-stu-id="318f6-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="318f6-109">Você pode instalar o controle ActiveX antecipadamente ou permitir que os usuários instalem-quando solicitado, o que acontece na primeira vez que eles usam Skype para negócios Web App ou na primeira vez que eles acessem um recurso que requer que o controle ActiveX.</span><span class="sxs-lookup"><span data-stu-id="318f6-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>
  
> [!NOTE]
> <span data-ttu-id="318f6-110">Skype para implantações de servidor de borda de 2015 Business Server, um proxy reverso de HTTPS na rede de perímetro será necessário para Skype para acesso de cliente de negócios Web App.</span><span class="sxs-lookup"><span data-stu-id="318f6-110">In Skype for Business Server 2015 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="318f6-111">Você também deve publicar URLs simples.</span><span class="sxs-lookup"><span data-stu-id="318f6-111">You must also publish simple URLs.</span></span> <span data-ttu-id="318f6-112">Para obter detalhes, consulte [Configuração Up Reverse Proxy Servers](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) e [requisitos de DNS para URLs simples no Skype para Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="318f6-112">For details, see [Setting Up Reverse Proxy Servers](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span> 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="318f6-113">Habilitar a autenticação multifator para Skype para negócios Web App</span><span class="sxs-lookup"><span data-stu-id="318f6-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="318f6-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="318f6-114"></span></span>

<span data-ttu-id="318f6-115">O Skype para negócios Web App e Skype reuniões App oferecem suporte a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="318f6-115">The Skype for Business Web App and Skype Meetings App support multi-factor authentication.</span></span> <span data-ttu-id="318f6-116">Além do nome de usuário e senha, você pode exigir que os métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar os usuários que estão ingressando a partir de redes externas quando entrarem no Skype para reuniões de negócios.</span><span class="sxs-lookup"><span data-stu-id="318f6-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="318f6-117">Você pode habilitar a autenticação multifator Implantando o servidor de Federação do serviço de Federação do Active Directory (AD FS) e habilitando autenticação passiva no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="318f6-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="318f6-118">Depois que o AD FS estiver configurado, os usuários externos que tentarem ingressar Skype para reuniões de negócios são apresentados com uma AD FS a autenticação multifator página da Web que contém o nome de usuário e senha desafiar junto com quaisquer métodos de autenticação adicional que você configurou.</span><span class="sxs-lookup"><span data-stu-id="318f6-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="318f6-119">As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:</span><span class="sxs-lookup"><span data-stu-id="318f6-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
  
- <span data-ttu-id="318f6-p105">A autenticação multifator do ADFS funciona se o participante e o organizador da reunião estiverem na mesma organização ou forem de uma organização federada do AD FS. A autenticação do ADFS de vários fatores não funciona para usuários federados do Lync porque a infraestrutura da Web do servidor do Lync não dà suporte à ela atualmente.</span><span class="sxs-lookup"><span data-stu-id="318f6-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>
    
- <span data-ttu-id="318f6-122">Se você usar os balanceadores de carga de hardware, habilite a persistência de cookie nos balanceadores de carga para que todas as requisições do Skype para clientes corporativos Web App ou aplicativo de reuniões são manipuladas pelo mesmo servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="318f6-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>
    
- <span data-ttu-id="318f6-123">Quando se estabelece uma terceira parte confiável entre Skype para servidores Business Server e o AD FS, atribua uma token vida que é grande o suficiente para abranger o comprimento máximo do seu Skype para reuniões de negócios.</span><span class="sxs-lookup"><span data-stu-id="318f6-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="318f6-124">Normalmente, uma vida de token de 240 minutos é suficiente.</span><span class="sxs-lookup"><span data-stu-id="318f6-124">Typically, a token life of 240 minutes is sufficient.</span></span>
    
- <span data-ttu-id="318f6-125">Esta configuração não se aplica aos clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="318f6-125">This configuration does not apply to Lync mobile clients.</span></span>
    
### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="318f6-126">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="318f6-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="318f6-127">Instale uma função de servidor de federação AD FS.</span><span class="sxs-lookup"><span data-stu-id="318f6-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="318f6-128">Para obter detalhes, consulte o [Guia de implantação do Active Directory Federation Services 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="318f6-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>
    
2. <span data-ttu-id="318f6-129">Crie certificados para o AD FS.</span><span class="sxs-lookup"><span data-stu-id="318f6-129">Create certificates for AD FS.</span></span> <span data-ttu-id="318f6-130">Para obter mais informações, consulte a seção ["Certificados de servidor de federação"](https://go.microsoft.com/fwlink/p/?LinkId=285376) do plano para e implantar o AD FS para uso com o tópico de logon único.</span><span class="sxs-lookup"><span data-stu-id="318f6-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>
    
3. <span data-ttu-id="318f6-131">Da interface de linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="318f6-131">From the Windows PowerShell command-line interface, run the following command:</span></span>
    
    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="318f6-132">Estabeleça uma parceria executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="318f6-132">Establish a partnership by running the following command:</span></span>
    
    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="318f6-133">Defina as seguintes regras de confiabilidade de parte:</span><span class="sxs-lookup"><span data-stu-id="318f6-133">Set the following relying party rules:</span></span>
    
    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="318f6-134">Desabilitar o BranchCache </span><span class="sxs-lookup"><span data-stu-id="318f6-134">Disable BranchCache</span></span>
<span data-ttu-id="318f6-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="318f6-135"></span></span>

<span data-ttu-id="318f6-136">O recurso BranchCache no Windows 7 e Windows Server 2008 R2 pode interferir Skype de componentes da web de negócios Web App.</span><span class="sxs-lookup"><span data-stu-id="318f6-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="318f6-137">Para evitar problemas de Skype para usuários corporativos Web App, certifique-se de que o BranchCache não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="318f6-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span> 
  
<span data-ttu-id="318f6-138">Para obter detalhes sobre como desabilitar o BranchCache, consulte o [Guia de implantação do BranchCache](https://docs.microsoft.com/en-us/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="318f6-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/en-us/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>
  
## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="318f6-139">Verificando Skype para implantação de aplicativo Web de negócios</span><span class="sxs-lookup"><span data-stu-id="318f6-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="318f6-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="318f6-140"></span></span>

<span data-ttu-id="318f6-141">Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="318f6-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="318f6-142">Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) no Skype para obter a documentação do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="318f6-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="318f6-143">Solucionando problemas de instalação de plug-in no Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="318f6-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="318f6-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="318f6-144"></span></span>

<span data-ttu-id="318f6-145">Se a instalação do plug-in falhar em um computador executando o Windows Server 2008 R2, você pode precisar modificar a configuração de segurança do Internet Explorer ou a configuração da chave do registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="318f6-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>
  
### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="318f6-146">Modificar a configuração de segurança no Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="318f6-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="318f6-147">Abra o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="318f6-147">Open Internet Explorer.</span></span>
    
2. <span data-ttu-id="318f6-148">Clique em **Ferramentas **, em **Opções da Internet ** e em **Avançado **.</span><span class="sxs-lookup"><span data-stu-id="318f6-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>
    
3. <span data-ttu-id="318f6-149">Role para baixo até a seção **Segurança **.</span><span class="sxs-lookup"><span data-stu-id="318f6-149">Scroll down to the **Security** section.</span></span>
    
4. <span data-ttu-id="318f6-150">Desmarque **Não salvar páginas criptografadas no disco ** e clique em **OK **.</span><span class="sxs-lookup"><span data-stu-id="318f6-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="318f6-151">Se selecionado, esta configuração também causará um erro ao tentar baixar um anexo do Skype para negócios Web App.</span><span class="sxs-lookup"><span data-stu-id="318f6-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span> 
  
5. <span data-ttu-id="318f6-p111">Reingresse na reunião. O download do plug-in deve ocorrer sem erros.</span><span class="sxs-lookup"><span data-stu-id="318f6-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>
    
### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="318f6-154">Modificar a configuração do Registro DisableMSI</span><span class="sxs-lookup"><span data-stu-id="318f6-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="318f6-155">Clique em  **Iniciar ** e em  **Executar **.</span><span class="sxs-lookup"><span data-stu-id="318f6-155">Click **Start**, and then click **Run**.</span></span>
    
2. <span data-ttu-id="318f6-156">Para acessar o Editor do Registro, digite **regedit **.</span><span class="sxs-lookup"><span data-stu-id="318f6-156">To access the Registry Editor, type **regedit**.</span></span>
    
3. <span data-ttu-id="318f6-157">Navegue até HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="318f6-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>
    
4. <span data-ttu-id="318f6-158">Editar ou adicionar a chave do registro DisableMSI do tipo REG_DWORD e configure como 0.</span><span class="sxs-lookup"><span data-stu-id="318f6-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>
    
5. <span data-ttu-id="318f6-159">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="318f6-159">Rejoin the meeting.</span></span>
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="318f6-160">Habilitar o aplicativo de reuniões do Skype substituir Skype para negócios Web App (opcional, Skype para negócios 2015 de servidor somente)</span><span class="sxs-lookup"><span data-stu-id="318f6-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="318f6-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="318f6-161"></span></span>

<span data-ttu-id="318f6-162">Esse procedimento é opcional e se aplica a Skype para Business Server 2015 CU5 e posterior.</span><span class="sxs-lookup"><span data-stu-id="318f6-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="318f6-163">Se você não usá-lo, os usuários externos continuarão participar de reuniões usando Skype para negócios Web App.</span><span class="sxs-lookup"><span data-stu-id="318f6-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span> 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="318f6-164">Habilitar ingresso em reunião simplificado e Aplicativo Reuniões do Skype</span><span class="sxs-lookup"><span data-stu-id="318f6-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="318f6-165">Quando você habilita o acesso à rede conteúdo de entrega (CDN), os usuários terão a capacidade de conectar ao CDN online e obtenha Skype reuniões App e usará o simplificado experiência de participação da reunião.</span><span class="sxs-lookup"><span data-stu-id="318f6-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App, and will use the simplified meeting join experience.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="318f6-166">Permitir que o cliente telemetria de registro em log do lado da reunião ingressar em página da web ou o aplicativo de reuniões do Skype sejam enviadas aos servidores da Microsoft (os padrões de comando como false).</span><span class="sxs-lookup"><span data-stu-id="318f6-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="318f6-167">As informações enviadas à Microsoft estão em conformidade com [Skype para práticas de coleta de dados corporativos](https://docs.microsoft.com/en-us/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span><span class="sxs-lookup"><span data-stu-id="318f6-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/en-us/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>
    
3. <span data-ttu-id="318f6-168">Defina o tempo limite antes de queda de volta para o Skype hospedado localmente para a experiência de negócios Web App se CDN não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="318f6-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="318f6-169">O valor padrão é de seis segundos.</span><span class="sxs-lookup"><span data-stu-id="318f6-169">The default value is 6 seconds.</span></span> <span data-ttu-id="318f6-170">Se esse valor estiver definido como 0, não haverá tempo limite.</span><span class="sxs-lookup"><span data-stu-id="318f6-170">If this value is set to 0, there will be no timeout.</span></span>
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="318f6-171">Ver também</span><span class="sxs-lookup"><span data-stu-id="318f6-171">See also</span></span>
<span data-ttu-id="318f6-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="318f6-172"></span></span>

[<span data-ttu-id="318f6-173">Planejar para clientes de reuniões (Web App e reuniões App)</span><span class="sxs-lookup"><span data-stu-id="318f6-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="318f6-174">Configurar a reunião página de ingresso em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="318f6-174">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)
  
[<span data-ttu-id="318f6-175">Declaração de privacidade do Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="318f6-175">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[<span data-ttu-id="318f6-176">Termos de licenciamento e documentação</span><span class="sxs-lookup"><span data-stu-id="318f6-176">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)