---
title: 'Lync Server 2013: Implantando o Lync Web App'
description: 'Lync Server 2013: Implantando o Lync Web App.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce6fef02781afbd5bc5f315ce24bfb3bdb16df1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560417"
---
# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="319f6-103">Implantando o Lync Web App no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="319f6-103">Deploying Lync Web App in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="319f6-104">_**Última modificação do tópico:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="319f6-104">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="319f6-105">O Lync Web App é um cliente da Web do IIS (serviços de informações da Internet) que é instalado com o Lync Server 2013 e é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="319f6-105">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="319f6-106">Nenhuma etapa adicional é necessária para habilitar o Lync Web App no servidor ou implantar o cliente Web para os usuários.</span><span class="sxs-lookup"><span data-stu-id="319f6-106">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="319f6-107">Sempre que um usuário clica em uma URL de reunião, mas não tem o cliente Lync 2013 instalado, o usuário recebe a opção de participar da reunião usando a versão mais recente do Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="319f6-107">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="319f6-108">Os recursos de voz, vídeo e compartilhamento no Lync Web App requerem um controle ActiveX da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="319f6-108">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="319f6-109">Você pode instalar o controle ActiveX com antecedência ou permitir que os usuários o instalem quando solicitado, que ocorre na primeira vez em que usam o Lync Web App ou na primeira vez que acessam um recurso que requer o controle ActiveX.</span><span class="sxs-lookup"><span data-stu-id="319f6-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="319f6-110">Nas implantações do servidor de borda do Lync Server 2013, um proxy reverso HTTPS na rede de perímetro é necessário para o acesso do cliente do Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="319f6-110">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="319f6-111">Também é necessário publicar URLs simples.</span><span class="sxs-lookup"><span data-stu-id="319f6-111">You must also publish simple URLs.</span></span> <span data-ttu-id="319f6-112">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores de proxy reverso para o Lync Server 2013</A> e <A href="lync-server-2013-planning-for-simple-urls.md">planejando URLs simples no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="319f6-112">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="319f6-113">Habilitando a autenticação multifator para o Lync Web App</span><span class="sxs-lookup"><span data-stu-id="319f6-113">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="319f6-114">A versão do Lync Server 2013 do Lync Web App oferece suporte à autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="319f6-114">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="319f6-115">Além de nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários que estão participando de redes externas quando eles entram nas reuniões do Lync.</span><span class="sxs-lookup"><span data-stu-id="319f6-115">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="319f6-116">Você pode habilitar a autenticação multifator implantando o servidor de Federação do serviço de Federação do Active Directory (AD FS) e habilitando a autenticação passiva no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="319f6-116">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="319f6-117">Após a configuração do AD FS, os usuários externos que tentarem ingressar em reuniões do Lync serão apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e o desafio de senha juntamente com quaisquer métodos de autenticação adicionais que você tenha configurado.</span><span class="sxs-lookup"><span data-stu-id="319f6-117">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="319f6-118">As considerações a seguir são importantes se você deseja planejar a configuração do AD FS para a autenticação multifator:</span><span class="sxs-lookup"><span data-stu-id="319f6-118">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="319f6-119">A autenticação do ADFS multifator funcionará se o participante da reunião e o organizador estiverem na mesma organização ou ambos de uma organização federada do AD FS.</span><span class="sxs-lookup"><span data-stu-id="319f6-119">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="319f6-120">A autenticação ADFS multifator não funciona para usuários federados do Lync porque a infraestrutura da Web do Lync Server atualmente não oferece suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="319f6-120">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="319f6-121">Se você usar balanceadores de carga de hardware, habilite a persistência de cookie nos balanceadores de carga para que todas as solicitações do cliente do Lync Web App sejam tratadas pelo mesmo servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="319f6-121">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="319f6-122">Ao estabelecer uma confiança de terceira parte confiável entre os servidores do Lync Server e do AD FS, atribua uma vida útil de token que seja longa o suficiente para abranger o tamanho máximo de suas reuniões do Lync.</span><span class="sxs-lookup"><span data-stu-id="319f6-122">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="319f6-123">Normalmente, uma vida de token de 240 minutos é suficiente.</span><span class="sxs-lookup"><span data-stu-id="319f6-123">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="319f6-124">Essa configuração não se aplica aos clientes móveis do Lync.</span><span class="sxs-lookup"><span data-stu-id="319f6-124">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="319f6-125">**Configurar a autenticação multifator**</span><span class="sxs-lookup"><span data-stu-id="319f6-125">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="319f6-126">Instale uma função de servidor de federação do AD FS.</span><span class="sxs-lookup"><span data-stu-id="319f6-126">Install an AD FS federation server role.</span></span> <span data-ttu-id="319f6-127">Para obter detalhes, consulte o guia de implantação do serviços de Federação do Active Directory 2,0 em <https://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="319f6-127">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="319f6-128">Criar certificados para o AD FS.</span><span class="sxs-lookup"><span data-stu-id="319f6-128">Create certificates for AD FS.</span></span> <span data-ttu-id="319f6-129">Para obter mais informações, consulte a seção "certificados do servidor de Federação" do tópico planejar e implantar o AD FS para uso com o logon único em [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="319f6-129">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="319f6-130">Na interface de linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="319f6-130">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="319f6-131">Estabeleça uma parceria executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="319f6-131">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="319f6-132">Defina as seguintes regras de confiabilidade de parte:</span><span class="sxs-lookup"><span data-stu-id="319f6-132">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="319f6-133">Configuração de BranchCache</span><span class="sxs-lookup"><span data-stu-id="319f6-133">BranchCache Configuration</span></span>

<span data-ttu-id="319f6-134">O recurso BranchCache no Windows 7 e no Windows Server 2008 R2 pode interferir nos componentes Web do Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="319f6-134">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="319f6-135">Para evitar problemas para usuários do Lync Web App, verifique se o BranchCache não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="319f6-135">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="319f6-136">Para obter detalhes sobre como desabilitar o BranchCache, consulte o guia de implantação do BranchCache, que está disponível no formato Word no centro de download da Microsoft em [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) e no formato HTML na biblioteca técnica do Windows Server 2008 R2 em [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) .</span><span class="sxs-lookup"><span data-stu-id="319f6-136">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="319f6-137">Verificando a implantação do Lync Web App</span><span class="sxs-lookup"><span data-stu-id="319f6-137">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="319f6-138">Você pode usar o cmdlet Test-CsUcwaConference para verificar se um par de usuários de teste pode participar de uma conferência usando a UCWA (Unified Communications Web API).</span><span class="sxs-lookup"><span data-stu-id="319f6-138">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="319f6-139">Para obter detalhes sobre esse cmdlet, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="319f6-139">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="319f6-140">Solucionando problemas de instalação de plug-in no Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="319f6-140">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="319f6-141">Se a instalação do plug-in falhar em um computador executando o Windows Server 2008 R2, talvez seja necessário modificar a configuração de segurança do Internet Explorer ou a configuração da chave do registro DisableMSI.</span><span class="sxs-lookup"><span data-stu-id="319f6-141">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="319f6-142">**Modificar a configuração de segurança no Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="319f6-142">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="319f6-143">Abra o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="319f6-143">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="319f6-144">Clique em **Ferramentas**, **Opções da Internet** e em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="319f6-144">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="319f6-145">Role até a seção **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="319f6-145">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="319f6-146">Desmarque **Não salvar páginas criptografadas no disco** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="319f6-146">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="319f6-147">Se for selecionada, esta configuração também causará um erro ao tentar baixar um anexo do Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="319f6-147">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="319f6-148">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="319f6-148">Rejoin the meeting.</span></span> <span data-ttu-id="319f6-149">O download do plug-in deve ocorrer sem erros.</span><span class="sxs-lookup"><span data-stu-id="319f6-149">The plug-in should download without errors.</span></span>

<span data-ttu-id="319f6-150">**Modificar a configuração do Registro DisableMSI**</span><span class="sxs-lookup"><span data-stu-id="319f6-150">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="319f6-151">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="319f6-151">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="319f6-152">Para acessar o Editor de registro, digite **regedit**.</span><span class="sxs-lookup"><span data-stu-id="319f6-152">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="319f6-153">Navegue até HKEY \_ local \_ Machine \\ software \\ Policies \\ Microsoft \\ Windows \\ Installer.</span><span class="sxs-lookup"><span data-stu-id="319f6-153">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="319f6-154">Edite ou adicione a chave do registro DisableMSI do tipo REG \_ DWORD e defina-a como 0.</span><span class="sxs-lookup"><span data-stu-id="319f6-154">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="319f6-155">Reingresse na reunião.</span><span class="sxs-lookup"><span data-stu-id="319f6-155">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="319f6-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="319f6-156">See Also</span></span>


[<span data-ttu-id="319f6-157">Configurando a página de ingresso na reunião no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="319f6-157">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="319f6-158">Plataformas com suporte do Lync Web App para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="319f6-158">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

