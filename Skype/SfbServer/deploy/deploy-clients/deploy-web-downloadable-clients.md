---
title: Implantar clientes baixáveis da Web no Skype for Business Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumo: Implante o Aplicativo Web do Skype for Business e o Aplicativo de Reuniões do Skype usado com o Skype for Business.'
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122125"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="85f93-103">Implantar clientes baixáveis da Web no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="85f93-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="85f93-104">**Resumo:** Implante o Aplicativo Web do Skype for Business 2015 e o Aplicativo de Reuniões do Skype usado com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85f93-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="85f93-105">O Skype for Business Web App é um cliente Web do Serviços de Informações da Internet (IIS) instalado no servidor que executa o Skype for Business Server e, por padrão, é implantado sob demanda para atender usuários que ainda não têm o cliente skype for Business.</span><span class="sxs-lookup"><span data-stu-id="85f93-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="85f93-106">Esses usuários de reunião estão mais frequentemente do que não se conectando de fora da sua rede.</span><span class="sxs-lookup"><span data-stu-id="85f93-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="85f93-107">Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente skype for Business instalado, o usuário é apresentado com a opção de ingressar na reunião usando a versão mais recente do Skype for Business Web App, Skype Meetings App ou Skype for Business para Mac.</span><span class="sxs-lookup"><span data-stu-id="85f93-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="85f93-108">Os recursos de voz, vídeo e compartilhamento no Skype for Business Web App exigem um controle microsoft ActiveX que é usado como um plug-in pelo navegador do usuário.</span><span class="sxs-lookup"><span data-stu-id="85f93-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="85f93-109">Você pode instalar o controle ActiveX com antecedência ou permitir que os usuários o instalem quando solicitado, o que acontece na primeira vez que eles usam o Skype for Business Web App ou a primeira vez que acessam um recurso que exige o controle ActiveX.</span><span class="sxs-lookup"><span data-stu-id="85f93-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="85f93-110">Nas implantações do Servidor de Borda do Skype for Business Server, um proxy reverso HTTPS na rede de perímetro é necessário para o acesso do cliente do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="85f93-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="85f93-111">Também é necessário publicar URLs simples.</span><span class="sxs-lookup"><span data-stu-id="85f93-111">You must also publish simple URLs.</span></span> <span data-ttu-id="85f93-112">Para obter detalhes, consulte [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and DNS requirements for simple [URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="85f93-112">For details, see [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="85f93-113">Habilitar a autenticação multifabilitar para o Skype for Business Web App</span><span class="sxs-lookup"><span data-stu-id="85f93-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="85f93-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="85f93-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="85f93-115">O Skype for Business Web App, o Aplicativo de Reuniões do Skype e o Skype for Business para Mac suportam a autenticação multifa factor.</span><span class="sxs-lookup"><span data-stu-id="85f93-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="85f93-116">Além do nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários que estão inscritas em redes externas ao entrar em reuniões do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="85f93-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="85f93-117">Você pode habilitar a autenticação multifabilitar implantando o servidor de federação do Serviço de Federação do Active Directory (AD FS) e habilitando a autenticação passiva no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85f93-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="85f93-118">Após a configuração do AD FS, os usuários externos que tentam ingressar em reuniões do Skype for Business são apresentados com uma página da Web de autenticação multifato do AD FS que contém o nome de usuário e o desafio de senha, juntamente com quaisquer métodos de autenticação adicionais que você configurou.</span><span class="sxs-lookup"><span data-stu-id="85f93-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85f93-119">As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:</span><span class="sxs-lookup"><span data-stu-id="85f93-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="85f93-120">A autenticação ADFS multifato funciona se o participante e o organizador da reunião estão na mesma organização ou são ambos de uma organização federada do AD FS.</span><span class="sxs-lookup"><span data-stu-id="85f93-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="85f93-121">A autenticação ADFS de vários fatores não funciona para usuários federados do Lync porque a infraestrutura web do servidor Lync atualmente não dá suporte a ela.</span><span class="sxs-lookup"><span data-stu-id="85f93-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="85f93-122">Se você usar balanceadores de carga de hardware, habilita a persistência de cookie nos balanceadores de carga para que todas as solicitações dos clientes do Skype for Business Web App ou do Aplicativo de Reuniões sejam manipuladas pelo mesmo Servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="85f93-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="85f93-123">Ao estabelecer uma confiança de parte confiável entre o Skype for Business Server e os servidores do AD FS, atribua uma vida de token que seja longa o suficiente para abranger o comprimento máximo de suas reuniões do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="85f93-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="85f93-124">Normalmente, uma vida de token de 240 minutos é suficiente.</span><span class="sxs-lookup"><span data-stu-id="85f93-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="85f93-125">Essa configuração não se aplica aos clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="85f93-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="85f93-126">Configurar a autenticação multifa factor</span><span class="sxs-lookup"><span data-stu-id="85f93-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="85f93-127">Instale uma função de servidor de federação do AD FS.</span><span class="sxs-lookup"><span data-stu-id="85f93-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="85f93-128">Para obter detalhes, consulte o Guia de Implantação dos [Serviços de Federação do Active Directory 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="85f93-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))</span></span>

2. <span data-ttu-id="85f93-129">Criar certificados para o AD FS.</span><span class="sxs-lookup"><span data-stu-id="85f93-129">Create certificates for AD FS.</span></span> <span data-ttu-id="85f93-130">Para obter mais informações, consulte a seção ["Certificados](/previous-versions/azure/azure-services/jj205462(v=azure.100)) do servidor de federação" do tópico Plan for and deploy AD FS for use with single sign-on topic.</span><span class="sxs-lookup"><span data-stu-id="85f93-130">For more information, see ["Federation server certificates"](/previous-versions/azure/azure-services/jj205462(v=azure.100)) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="85f93-131">Na interface Windows PowerShell linha de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="85f93-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="85f93-132">Estabeleça uma parceria executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="85f93-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="85f93-133">Defina as seguintes regras de confiabilidade de parte:</span><span class="sxs-lookup"><span data-stu-id="85f93-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="85f93-134">Desabilitar BranchCache</span><span class="sxs-lookup"><span data-stu-id="85f93-134">Disable BranchCache</span></span>
<span data-ttu-id="85f93-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="85f93-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="85f93-136">O recurso BranchCache no Windows 7 e no Windows Server 2008 R2 pode interferir nos componentes web do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="85f93-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="85f93-137">Para evitar problemas para usuários do Skype for Business Web App, certifique-se de que BranchCache não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="85f93-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="85f93-138">Para obter detalhes sobre como desabilitar BranchCache, consulte o [Guia de Implantação branchCache.](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="85f93-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="85f93-139">Verificando a implantação do Skype for Business Web App</span><span class="sxs-lookup"><span data-stu-id="85f93-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="85f93-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="85f93-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="85f93-141">Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="85f93-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="85f93-142">Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) na documentação do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="85f93-142">For details about this cmdlet, see [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="85f93-143">Solução de problemas de instalação de plug-in no Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="85f93-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="85f93-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="85f93-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="85f93-145">Se a instalação do plug-in falhar em um computador que executa o Windows Server 2008 R2, talvez seja necessário modificar a configuração de segurança do Internet Explorer ou a configuração da chave do Registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="85f93-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="85f93-146">Modificar a configuração de segurança no Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="85f93-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="85f93-147">Abra o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="85f93-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="85f93-148">Clique em **Ferramentas**, **Opções da Internet** e em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="85f93-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="85f93-149">Role até a seção **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="85f93-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="85f93-150">Desmarque **Não salvar páginas criptografadas no disco** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="85f93-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="85f93-151">Se selecionada, essa configuração também causará um erro ao tentar baixar um anexo do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="85f93-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="85f93-152">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="85f93-152">Rejoin the meeting.</span></span> <span data-ttu-id="85f93-153">O download do plug-in deve ocorrer sem erros.</span><span class="sxs-lookup"><span data-stu-id="85f93-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="85f93-154">Modificar a configuração DisableMSI Registry</span><span class="sxs-lookup"><span data-stu-id="85f93-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="85f93-155">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="85f93-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="85f93-156">Para acessar o Editor de registro, digite **regedit**.</span><span class="sxs-lookup"><span data-stu-id="85f93-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="85f93-157">Navegue até HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="85f93-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="85f93-158">Editar ou adicionar a chave do registro DisableMSI do tipo REG_DWORD e configure como 0.</span><span class="sxs-lookup"><span data-stu-id="85f93-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="85f93-159">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="85f93-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="85f93-160">Habilitar o Aplicativo de Reuniões do Skype para substituir o Skype for Business Web App (Opcional, Somente Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="85f93-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="85f93-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="85f93-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="85f93-162">Este procedimento é opcional e se aplica ao Skype for Business Server 2015 CU5 e posterior.</span><span class="sxs-lookup"><span data-stu-id="85f93-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="85f93-163">Se você não usá-lo, os usuários externos continuarão a participar de reuniões usando o Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="85f93-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="85f93-164">Habilitar a junção de reuniões simplificadas e o Aplicativo de Reuniões do Skype</span><span class="sxs-lookup"><span data-stu-id="85f93-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="85f93-165">Quando você habilita o acesso à Rede de Entrega de Conteúdo (CDN), os usuários terão a capacidade de se conectar à CDN online e obter o Skype Meetings App (no Windows) e o Skype for Business para Mac (no Mac) e usarão a experiência de junção de reunião simplificada.</span><span class="sxs-lookup"><span data-stu-id="85f93-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="85f93-166">Permitir que a telemetria de registro em log do lado do cliente da página da Web de junção de reunião ou o Aplicativo de Reuniões do Skype seja enviada aos servidores microsoft (o comando padrão é false).</span><span class="sxs-lookup"><span data-stu-id="85f93-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="85f93-167">As informações enviadas à Microsoft estão em estrita conformidade com as práticas de coleta de dados [do Skype for Business.](/skypeforbusiness/legal-and-regulatory/data-collection-practices)</span><span class="sxs-lookup"><span data-stu-id="85f93-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="85f93-168">Desembolse o tempo de tempo antes de voltar para a experiência do Skype for Business Web App hospedada localmente se a CDN não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="85f93-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="85f93-169">O valor padrão é 6 segundos.</span><span class="sxs-lookup"><span data-stu-id="85f93-169">The default value is 6 seconds.</span></span> <span data-ttu-id="85f93-170">Se esse valor for definido como 0, não haverá tempo de vida.</span><span class="sxs-lookup"><span data-stu-id="85f93-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="85f93-171">Com MeetingUxUseCdn no Skype for Business Server 2015 Cumulative Update 5, o valor padrão é definido como False.</span><span class="sxs-lookup"><span data-stu-id="85f93-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="85f93-172">Isso causa um problema em que o cliente skype for Business para Mac não pode participar de reuniões de parceiros não federados como convidado, mesmo que o Administrador do Skype for Business tenha definido MeetingUxUseCdn como True.</span><span class="sxs-lookup"><span data-stu-id="85f93-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="85f93-173">Para que isso funcione, o Skype for Business Server 2015 deve ter a Atualização Cumulativa 7, 6.0.9319.534 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="85f93-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="85f93-174">Consulte [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span><span class="sxs-lookup"><span data-stu-id="85f93-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="85f93-175">Confira também</span><span class="sxs-lookup"><span data-stu-id="85f93-175">See also</span></span>
<span data-ttu-id="85f93-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="85f93-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="85f93-177">Planejar os clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)</span><span class="sxs-lookup"><span data-stu-id="85f93-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="85f93-178">Configurar a página de junção de reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="85f93-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="85f93-179">Declaração de Privacidade dos Serviços Online da Microsoft</span><span class="sxs-lookup"><span data-stu-id="85f93-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="85f93-180">Termos de licenciamento e documentação</span><span class="sxs-lookup"><span data-stu-id="85f93-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)