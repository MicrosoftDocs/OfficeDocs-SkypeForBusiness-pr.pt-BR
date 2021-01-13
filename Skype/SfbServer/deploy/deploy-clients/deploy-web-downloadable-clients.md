---
title: Implantar clientes para download da Web no Skype for Business Server
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
description: 'Resumo: implante o Skype for Business Web App e o aplicativo Reuniões do Skype usados com o Skype for Business.'
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805921"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="a799b-103">Implantar clientes para download da Web no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a799b-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="a799b-104">**Resumo:** Implante o Skype for Business 2015 Web App e o aplicativo Reuniões do Skype usados com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a799b-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="a799b-105">O Skype for Business Web App é um cliente Web do IIS (Serviços de Informações da Internet) instalado no servidor que executa o Skype for Business Server e, por padrão, é implantado sob demanda para usuários que ainda não têm o cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a799b-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="a799b-106">Esses usuários da reunião geralmente não se conectam de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="a799b-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="a799b-107">Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente Skype for Business instalado, o usuário tem a opção de ingressar na reunião usando a versão mais recente do Skype for Business Web App, do Aplicativo de Reuniões do Skype ou do Skype for Business para Mac.</span><span class="sxs-lookup"><span data-stu-id="a799b-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="a799b-108">Os recursos de voz, vídeo e compartilhamento no Skype for Business Web App exigem um controle Microsoft ActiveX usado como plug-in pelo navegador do usuário.</span><span class="sxs-lookup"><span data-stu-id="a799b-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="a799b-109">Você pode instalar o controle ActiveX com antecedência ou permitir que os usuários o instalem quando solicitado, o que acontece na primeira vez que eles usam o Skype for Business Web App ou na primeira vez que acessam um recurso que requer o controle ActiveX.</span><span class="sxs-lookup"><span data-stu-id="a799b-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="a799b-110">Nas implantações do Servidor de Borda do Skype for Business Server, um proxy reverso HTTPS na rede de perímetro é necessário para o acesso do cliente do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="a799b-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="a799b-111">Também é necessário publicar URLs simples.</span><span class="sxs-lookup"><span data-stu-id="a799b-111">You must also publish simple URLs.</span></span> <span data-ttu-id="a799b-112">Para obter detalhes, [consulte Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and DNS requirements for simple [URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="a799b-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="a799b-113">Habilitar a autenticação multifa factor para o Skype for Business Web App</span><span class="sxs-lookup"><span data-stu-id="a799b-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="a799b-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="a799b-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="a799b-115">O Skype for Business Web App, o Aplicativo de Reuniões do Skype e o Skype for Business para Mac suportam a autenticação multifa factor.</span><span class="sxs-lookup"><span data-stu-id="a799b-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="a799b-116">Além do nome de usuário e da senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários que estão inscritas em redes externas ao entrar em reuniões do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a799b-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="a799b-117">Você pode habilitar a autenticação multifaionária implantando o servidor de federação do AD FS (Serviço de Federação do Active Directory) e habilitando a autenticação passiva no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a799b-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="a799b-118">Depois que o AD FS é configurado, os usuários externos que tentam ingressar em reuniões do Skype for Business são apresentados com uma página da Web de autenticação multifato do AD FS que contém o nome de usuário e o desafio de senha, juntamente com quaisquer métodos de autenticação adicionais que você tenha configurado.</span><span class="sxs-lookup"><span data-stu-id="a799b-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a799b-119">As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:</span><span class="sxs-lookup"><span data-stu-id="a799b-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="a799b-120">A autenticação multifafa do ADFS funciona se o participante da reunião e o organizador estão na mesma organização ou são de uma organização federada do AD FS.</span><span class="sxs-lookup"><span data-stu-id="a799b-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="a799b-121">A autenticação multifato do ADFS não funciona para usuários federados do Lync porque a infraestrutura da Web do servidor do Lync não dá suporte a ela no momento.</span><span class="sxs-lookup"><span data-stu-id="a799b-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="a799b-122">Se você usar balanceadores de carga de hardware, habilita a persistência de cookie nos balanceadores de carga para que todas as solicitações dos clientes do Aplicativo Web do Skype for Business ou do Aplicativo de Reuniões sejam manipuladas pelo mesmo Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="a799b-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="a799b-123">Ao estabelecer uma relação de confiança de terceiros confiável entre o Skype for Business Server e os servidores do AD FS, atribua uma vida de token longa o suficiente para abranger a duração máxima de suas reuniões do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a799b-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="a799b-124">Normalmente, uma vida de token de 240 minutos é suficiente.</span><span class="sxs-lookup"><span data-stu-id="a799b-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="a799b-125">Essa configuração não se aplica aos clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="a799b-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="a799b-126">Configurar a autenticação multifa factor</span><span class="sxs-lookup"><span data-stu-id="a799b-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="a799b-127">Instale uma função de servidor de federação do AD FS.</span><span class="sxs-lookup"><span data-stu-id="a799b-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="a799b-128">Para obter detalhes, consulte o Guia de Implantação dos Serviços de Federação do [Active Directory 2.0](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="a799b-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="a799b-129">Criar certificados para o AD FS.</span><span class="sxs-lookup"><span data-stu-id="a799b-129">Create certificates for AD FS.</span></span> <span data-ttu-id="a799b-130">Para obter mais informações, consulte a seção ["Certificados](https://go.microsoft.com/fwlink/p/?LinkId=285376) do servidor de federação" do tópico Planejar e implantar o AD FS para uso com o tópico de login único.</span><span class="sxs-lookup"><span data-stu-id="a799b-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="a799b-131">Na interface de linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a799b-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="a799b-132">Estabeleça uma parceria executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a799b-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="a799b-133">Defina as seguintes regras de confiabilidade de parte:</span><span class="sxs-lookup"><span data-stu-id="a799b-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="a799b-134">Desabilitar BranchCache</span><span class="sxs-lookup"><span data-stu-id="a799b-134">Disable BranchCache</span></span>
<span data-ttu-id="a799b-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="a799b-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="a799b-136">O recurso BranchCache no Windows 7 e no Windows Server 2008 R2 pode interferir nos componentes Web do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="a799b-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="a799b-137">Para evitar problemas para usuários do Skype for Business Web App, certifique-se de que o BranchCache não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a799b-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="a799b-138">Para obter detalhes sobre como desabilitar o BranchCache, consulte o [Guia de Implantação do BranchCache.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="a799b-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="a799b-139">Verificando a implantação do Skype for Business Web App</span><span class="sxs-lookup"><span data-stu-id="a799b-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="a799b-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="a799b-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="a799b-141">Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="a799b-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="a799b-142">Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) na documentação do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a799b-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="a799b-143">Solução de problemas de instalação de plug-in no Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a799b-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="a799b-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="a799b-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="a799b-145">Se a instalação do plug-in falhar em um computador que executa o Windows Server 2008 R2, talvez seja necessário modificar a configuração de segurança do Internet Explorer ou a configuração da chave do Registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="a799b-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="a799b-146">Modificar a configuração de segurança no Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="a799b-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="a799b-147">Abra o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a799b-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="a799b-148">Clique em **Ferramentas**, **Opções da Internet** e em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="a799b-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="a799b-149">Role até a seção **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="a799b-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="a799b-150">Desmarque **Não salvar páginas criptografadas no disco** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a799b-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a799b-151">Se selecionada, essa configuração também causará um erro ao tentar baixar um anexo do Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="a799b-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="a799b-152">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="a799b-152">Rejoin the meeting.</span></span> <span data-ttu-id="a799b-153">O download do plug-in deve ocorrer sem erros.</span><span class="sxs-lookup"><span data-stu-id="a799b-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="a799b-154">Modificar a configuração do Registro DisableMSI</span><span class="sxs-lookup"><span data-stu-id="a799b-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="a799b-155">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a799b-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="a799b-156">Para acessar o Editor de registro, digite **regedit**.</span><span class="sxs-lookup"><span data-stu-id="a799b-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="a799b-157">Navegue até HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="a799b-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="a799b-158">Editar ou adicionar a chave do registro DisableMSI do tipo REG_DWORD e configure como 0.</span><span class="sxs-lookup"><span data-stu-id="a799b-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="a799b-159">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="a799b-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="a799b-160">Habilitar o Aplicativo Reuniões do Skype para substituir o Skype for Business Web App (opcional, somente Skype for Business Server 2015)</span><span class="sxs-lookup"><span data-stu-id="a799b-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="a799b-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="a799b-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="a799b-162">Este procedimento é opcional e se aplica à cu5 do Skype for Business Server 2015 e posterior.</span><span class="sxs-lookup"><span data-stu-id="a799b-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="a799b-163">Se você não usá-lo, os usuários externos continuarão a ingressar em reuniões usando o Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="a799b-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="a799b-164">Habilitar o acesso simplificado à reunião e ao aplicativo Reuniões do Skype</span><span class="sxs-lookup"><span data-stu-id="a799b-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="a799b-165">Quando você habilita o acesso à REDE de Distribuição de Conteúdo (CDN), os usuários terão a capacidade de se conectar à CDN online e obter o Aplicativo reuniões do Skype (no Windows) e o Skype for Business para Mac (no Mac) e usarão a experiência de ingressar em reunião simplificada.</span><span class="sxs-lookup"><span data-stu-id="a799b-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="a799b-166">Permitir que a telemetria de registro em log do lado do cliente na página da Web de ingressar na reunião ou no aplicativo Reuniões do Skype seja enviada aos servidores da Microsoft (o comando assume como false).</span><span class="sxs-lookup"><span data-stu-id="a799b-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="a799b-167">As informações enviadas à Microsoft estão em conformidade estrita com as práticas de coleta de dados [do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)</span><span class="sxs-lookup"><span data-stu-id="a799b-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="a799b-168">De definida o tempo final antes de voltar para a experiência do Skype for Business Web App hospedada localmente se a CDN não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="a799b-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="a799b-169">O valor padrão é 6 segundos.</span><span class="sxs-lookup"><span data-stu-id="a799b-169">The default value is 6 seconds.</span></span> <span data-ttu-id="a799b-170">Se esse valor for definido como 0, não haverá tempo final.</span><span class="sxs-lookup"><span data-stu-id="a799b-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="a799b-171">Com MeetingUxUseCdn no Skype for Business Server 2015 Atualização Cumulativa 5, o valor padrão é definido como False.</span><span class="sxs-lookup"><span data-stu-id="a799b-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="a799b-172">Isso causa um problema em que o cliente do Skype for Business para Mac não consegue participar de reuniões de parceiros não federados como convidado, mesmo que o administrador do Skype for Business tenha definido MeetingUxUseCdn como True.</span><span class="sxs-lookup"><span data-stu-id="a799b-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="a799b-173">Para que isso funcione, o Skype for Business Server 2015 deve ter a Atualização Cumulativa 7, 6.0.9319.534 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="a799b-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="a799b-174">Consulte [Habilitar o Aplicativo Reuniões do Skype para substituir o Skype for Business Web App no Skype for Business Server 2015.](https://support.microsoft.com/kb/4132312)</span><span class="sxs-lookup"><span data-stu-id="a799b-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="a799b-175">Confira também</span><span class="sxs-lookup"><span data-stu-id="a799b-175">See also</span></span>
<span data-ttu-id="a799b-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="a799b-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="a799b-177">Planejar-se para clientes de reuniões (aplicativo Web App e Reuniões)</span><span class="sxs-lookup"><span data-stu-id="a799b-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="a799b-178">Configurar a página de junção de reunião no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a799b-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="a799b-179">Declaração de Privacidade dos Serviços Online da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a799b-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="a799b-180">Termos e Documentação de Licenciamento</span><span class="sxs-lookup"><span data-stu-id="a799b-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
