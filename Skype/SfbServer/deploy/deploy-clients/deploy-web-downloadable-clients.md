---
title: Implantar clientes para download da Web no Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'Resumo: implantar o Skype for Business Web App e o aplicativo de reuniões do Skype usado com o Skype for Business.'
ms.openlocfilehash: 16a2a28bf634524d6f61ba579652a6dddfd06de3
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429417"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="00bad-103">Implantar clientes para download da Web no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00bad-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="00bad-104">**Resumo:** Implante o aplicativo Web do Skype for Business 2015 e o aplicativo de reuniões do Skype usado com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00bad-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="00bad-105">O Skype for Business Web App é um cliente da Web do IIS (serviços de informações da Internet) instalado no servidor que executa o Skype for Business Server e, por padrão, é implantado por demanda para atender aos usuários que ainda não têm o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="00bad-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="00bad-106">Esses usuários da reunião são mais frequentes do que não se conectar de fora da sua rede.</span><span class="sxs-lookup"><span data-stu-id="00bad-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="00bad-107">Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente Skype for Business instalado, o usuário recebe a opção de participar da reunião usando a versão mais recente do Skype for Business Web App, o aplicativo de reuniões do Skype ou o Skype for Business para Mac.</span><span class="sxs-lookup"><span data-stu-id="00bad-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="00bad-108">Os recursos de voz, vídeo e compartilhamento no Skype for Business Web App requerem um controle ActiveX da Microsoft usado como um plug-in do navegador do usuário.</span><span class="sxs-lookup"><span data-stu-id="00bad-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="00bad-109">Você pode instalar o controle ActiveX com antecedência ou permitir que os usuários o instalem quando solicitado, que ocorre na primeira vez em que usam o Skype for Business Web App ou na primeira vez que acessam um recurso que requer o controle ActiveX.</span><span class="sxs-lookup"><span data-stu-id="00bad-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="00bad-110">Nas implantações do servidor de borda do Skype for Business Server, um proxy reverso HTTPS na rede de perímetro é necessário para o acesso do cliente do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="00bad-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="00bad-111">Também é necessário publicar URLs simples.</span><span class="sxs-lookup"><span data-stu-id="00bad-111">You must also publish simple URLs.</span></span> <span data-ttu-id="00bad-112">Para obter detalhes, consulte [setting up Reverse proxy servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS Requirements for Simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="00bad-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="00bad-113">Habilitar a autenticação multifator para o Skype for Business Web App</span><span class="sxs-lookup"><span data-stu-id="00bad-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="00bad-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="00bad-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="00bad-115">O Skype for Business Web App, o aplicativo de reuniões do Skype e o Skype for Business para Mac oferecem suporte à autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="00bad-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="00bad-116">Além de nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar os usuários que estão participando de redes externas ao entrarem em reuniões do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="00bad-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="00bad-117">Você pode habilitar a autenticação multifator implantando o servidor de Federação do serviço de Federação do Active Directory (AD FS) e habilitando a autenticação passiva no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00bad-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="00bad-118">Após a configuração do AD FS, os usuários externos que tentarem participar de reuniões do Skype for Business são apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e a senha desafio, juntamente com quaisquer métodos de autenticação adicionais que você tenha configurado.</span><span class="sxs-lookup"><span data-stu-id="00bad-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00bad-119">As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:</span><span class="sxs-lookup"><span data-stu-id="00bad-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="00bad-120">A autenticação do ADFS multifator funcionará se o participante da reunião e o organizador estiverem na mesma organização ou ambos de uma organização federada do AD FS.</span><span class="sxs-lookup"><span data-stu-id="00bad-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="00bad-121">A autenticação ADFS multifator não funciona para usuários federados do Lync porque a infraestrutura da Web do Lync Server atualmente não oferece suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="00bad-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="00bad-122">Se você usar balanceadores de carga de hardware, habilite a persistência de cookie nos balanceadores de carga para que todas as solicitações do cliente de aplicativos Web App ou de reuniões do Skype for Business sejam tratadas pelo mesmo servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="00bad-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="00bad-123">Ao estabelecer uma confiança de terceira parte confiável entre o Skype for Business Server e os servidores AD FS, atribua uma vida útil de token que seja longa o suficiente para abranger o tamanho máximo de suas reuniões do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="00bad-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="00bad-124">Normalmente, uma vida de token de 240 minutos é suficiente.</span><span class="sxs-lookup"><span data-stu-id="00bad-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="00bad-125">Essa configuração não se aplica aos clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="00bad-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="00bad-126">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="00bad-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="00bad-127">Instale uma função de servidor de federação do AD FS.</span><span class="sxs-lookup"><span data-stu-id="00bad-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="00bad-128">Para obter detalhes, consulte o [Guia de implantação do serviços de Federação do Active Directory 2,0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="00bad-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="00bad-129">Criar certificados para o AD FS.</span><span class="sxs-lookup"><span data-stu-id="00bad-129">Create certificates for AD FS.</span></span> <span data-ttu-id="00bad-130">Para obter mais informações, consulte a seção ["certificados do servidor de Federação"](https://go.microsoft.com/fwlink/p/?LinkId=285376) do tópico planejar e implantar o AD FS para uso com o logon único.</span><span class="sxs-lookup"><span data-stu-id="00bad-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="00bad-131">Na interface de linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="00bad-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="00bad-132">Estabeleça uma parceria executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="00bad-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="00bad-133">Defina as seguintes regras de confiabilidade de parte:</span><span class="sxs-lookup"><span data-stu-id="00bad-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="00bad-134">Desabilitar o BranchCache</span><span class="sxs-lookup"><span data-stu-id="00bad-134">Disable BranchCache</span></span>
<span data-ttu-id="00bad-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="00bad-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="00bad-136">O recurso BranchCache no Windows 7 e no Windows Server 2008 R2 pode interferir nos componentes Web do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="00bad-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="00bad-137">Para evitar problemas para usuários do Skype for Business Web App, verifique se o BranchCache não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="00bad-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="00bad-138">Para obter detalhes sobre como desabilitar o BranchCache, consulte o [Guia de implantação do BranchCache](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span><span class="sxs-lookup"><span data-stu-id="00bad-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="00bad-139">Verificando a implantação do Skype for Business Web App</span><span class="sxs-lookup"><span data-stu-id="00bad-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="00bad-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="00bad-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="00bad-141">Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="00bad-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="00bad-142">Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) na documentação do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00bad-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="00bad-143">Solucionando problemas de instalação de plug-in no Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="00bad-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="00bad-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="00bad-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="00bad-145">Se a instalação do plug-in falhar em um computador executando o Windows Server 2008 R2, talvez seja necessário modificar a configuração de segurança do Internet Explorer ou a configuração da chave do registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="00bad-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="00bad-146">Modificar a configuração de segurança no Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="00bad-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="00bad-147">Abra o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="00bad-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="00bad-148">Clique em **Ferramentas**, **Opções da Internet** e em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="00bad-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="00bad-149">Role até a seção **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="00bad-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="00bad-150">Desmarque **Não salvar páginas criptografadas no disco** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="00bad-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00bad-151">Se for selecionada, essa configuração também causará um erro ao tentar baixar um anexo do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="00bad-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="00bad-152">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="00bad-152">Rejoin the meeting.</span></span> <span data-ttu-id="00bad-153">O download do plug-in deve ocorrer sem erros.</span><span class="sxs-lookup"><span data-stu-id="00bad-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="00bad-154">Modificar a configuração do registro DisableMSI</span><span class="sxs-lookup"><span data-stu-id="00bad-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="00bad-155">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="00bad-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="00bad-156">Para acessar o Editor de registro, digite **regedit**.</span><span class="sxs-lookup"><span data-stu-id="00bad-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="00bad-157">Navegue até HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="00bad-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="00bad-158">Editar ou adicionar a chave do registro DisableMSI do tipo REG_DWORD e configure como 0.</span><span class="sxs-lookup"><span data-stu-id="00bad-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="00bad-159">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="00bad-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="00bad-160">Habilitar o aplicativo de reuniões do Skype para substituir o Skype for Business Web App (opcional, Skype for Business Server 2015 apenas)</span><span class="sxs-lookup"><span data-stu-id="00bad-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="00bad-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="00bad-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="00bad-162">Este procedimento é opcional e se aplica ao Skype for Business Server 2015 CU5 e posterior.</span><span class="sxs-lookup"><span data-stu-id="00bad-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="00bad-163">Se você não usá-lo, os usuários externos continuarão a participar de reuniões usando o Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="00bad-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="00bad-164">Habilitar o ingresso em reunião simplificada e o aplicativo reuniões do Skype</span><span class="sxs-lookup"><span data-stu-id="00bad-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="00bad-165">Quando você habilita o acesso à rede de distribuição de conteúdo (CDN), os usuários terão a capacidade de se conectar à CDN online e obter o aplicativo de reuniões do Skype (no Windows) e o Skype for Business para Mac (no Mac) e usarão a experiência de junção de reunião simplificada.</span><span class="sxs-lookup"><span data-stu-id="00bad-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="00bad-166">Permitir a telemetria de registro no cliente da página de ingresso na reunião ou do aplicativo de reuniões do Skype para ser enviado aos servidores da Microsoft (o comando padrão é false).</span><span class="sxs-lookup"><span data-stu-id="00bad-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="00bad-167">As informações enviadas à Microsoft estão em conformidade estrita com a [privacidade e o Microsoft Teams](../../../../Teams/teams-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="00bad-167">Information sent to Microsoft is in strict compliance with [Privacy and Microsoft Teams](../../../../Teams/teams-privacy.md).</span></span>

3. <span data-ttu-id="00bad-168">Defina o tempo limite antes de voltar para a experiência do aplicativo Web do Skype for Business hospedado localmente, se a CDN não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="00bad-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="00bad-169">O valor padrão é 6 segundos.</span><span class="sxs-lookup"><span data-stu-id="00bad-169">The default value is 6 seconds.</span></span> <span data-ttu-id="00bad-170">Se esse valor for definido como 0, não haverá tempo limite.</span><span class="sxs-lookup"><span data-stu-id="00bad-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="00bad-171">Com o MeetingUxUseCdn na atualização cumulativa 5 do Skype for Business Server 2015, o valor padrão é definido como false.</span><span class="sxs-lookup"><span data-stu-id="00bad-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="00bad-172">Isso causa um problema em que o cliente do Skype for Business para Mac não consegue ingressar em reuniões de parceiros não federados como convidados, mesmo que o administrador do Skype for Business tenha definido MeetingUxUseCdn como true.</span><span class="sxs-lookup"><span data-stu-id="00bad-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="00bad-173">Para que isso funcione, o Skype for Business Server 2015 deve ter a atualização cumulativa 7, 6.0.9319.534 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="00bad-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="00bad-174">Consulte [habilitar o aplicativo de reuniões do Skype para substituir o Skype for Business Web App no Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span><span class="sxs-lookup"><span data-stu-id="00bad-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="00bad-175">Confira também</span><span class="sxs-lookup"><span data-stu-id="00bad-175">See also</span></span>
<span data-ttu-id="00bad-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="00bad-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="00bad-177">Plano para clientes de reuniões (aplicativo Web e aplicativos de reuniões)</span><span class="sxs-lookup"><span data-stu-id="00bad-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="00bad-178">Configurar a página de ingresso na reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00bad-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="00bad-179">Declaração de Privacidade dos Serviços Online da Microsoft</span><span class="sxs-lookup"><span data-stu-id="00bad-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="00bad-180">Termos e documentação de licenciamento</span><span class="sxs-lookup"><span data-stu-id="00bad-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
