---
title: 'Lync Server 2013: Implantando o aplicativo Lync da Windows Store'
description: 'Lync Server 2013: Implantando o aplicativo Lync da Windows Store.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9260d656079fb694a14aadf5049ca36241830c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571707"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="3ed30-103">Implantando o aplicativo Lync da Windows Store no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ed30-103">Deploying Lync Windows Store app in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ed30-104">_**Última modificação do tópico:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="3ed30-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="3ed30-105">Antes de tornar o aplicativo Lync da Windows Store disponível para os usuários, certifique-se de que sua implantação atenda aos [requisitos de aplicativo do Lync Windows Store para Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ed30-105">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="3ed30-106">Para obter detalhes sobre como configurar o Lync Server 2013 para oferecer suporte ao aplicativo Lync da Windows Store, consulte o artigo de blog NextHop, "descoberta automática do Lync Server e o aplicativo Lync da Windows Store" em [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) .</span><span class="sxs-lookup"><span data-stu-id="3ed30-106">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="3ed30-107">Após a configuração correta do ambiente de servidor, você pode direcionar os usuários para baixar o aplicativo Lync da Windows Store pesquisando por "Lync".</span><span class="sxs-lookup"><span data-stu-id="3ed30-107">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="3ed30-108">Habilitando a autenticação multifator para o aplicativo Lync da Windows Store</span><span class="sxs-lookup"><span data-stu-id="3ed30-108">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="3ed30-109">Atualizações cumulativas do Lync Server 2013: junho de 2013 adiciona suporte para a autenticação multifator para clientes de aplicativos Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="3ed30-109">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="3ed30-110">Além de nome de usuário e senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários externos quando eles entrarem em reuniões do Lync.</span><span class="sxs-lookup"><span data-stu-id="3ed30-110">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="3ed30-111">Para habilitar a autenticação multifator, implante o servidor de Federação do AD FS (serviço de Federação do Active Directory) e habilite a autenticação passiva no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ed30-111">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="3ed30-112">Após a configuração do AD FS, os usuários externos que tentarem ingressar em reuniões do Lync serão apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e o desafio de senha juntamente com quaisquer métodos de autenticação adicionais que você tenha configurado.</span><span class="sxs-lookup"><span data-stu-id="3ed30-112">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="3ed30-113">As considerações a seguir são importantes se você planeja configurar o AD FS para a autenticação multifator para o aplicativo Lync da Windows Store:</span><span class="sxs-lookup"><span data-stu-id="3ed30-113">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="3ed30-114">Lync Server 2013 com atualizações cumulativas para Lync Server 2013: o 2013 de junho é necessário no mínimo.</span><span class="sxs-lookup"><span data-stu-id="3ed30-114">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="3ed30-115">Os clientes do Lync 2013 desktop não exigem atualizações cumulativas do Lync Server 2013:2013 de junho, portanto, pode parecer que a autenticação passiva está funcionando porque os clientes do Lync 2013 podem autenticar.</span><span class="sxs-lookup"><span data-stu-id="3ed30-115">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="3ed30-116">No entanto, o processo de autenticação para os clientes do aplicativo Lync da Windows Store não será concluído e nenhuma notificação ou mensagem de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="3ed30-116">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="3ed30-117">O servidor deve ser configurado para que a autenticação passiva seja o único tipo de autenticação oferecido.</span><span class="sxs-lookup"><span data-stu-id="3ed30-117">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="3ed30-118">Se você usar balanceadores de carga de hardware, habilite a persistência de cookie nos balanceadores de carga para que todas as solicitações do cliente de aplicativo do Lync Windows Store sejam tratadas pelo mesmo servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="3ed30-118">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="3ed30-119">Ao estabelecer uma confiança de terceira parte confiável entre os servidores do Lync Server e do AD FS, atribua uma vida útil de token que seja longa o suficiente para abranger o tamanho máximo de suas reuniões do Lync.</span><span class="sxs-lookup"><span data-stu-id="3ed30-119">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="3ed30-120">Normalmente, uma vida de token de 240 minutos é suficiente.</span><span class="sxs-lookup"><span data-stu-id="3ed30-120">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3ed30-121">**Configurar a autenticação multifator**</span><span class="sxs-lookup"><span data-stu-id="3ed30-121">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="3ed30-122">Instale uma função de servidor de federação do AD FS.</span><span class="sxs-lookup"><span data-stu-id="3ed30-122">Install an AD FS federation server role.</span></span> <span data-ttu-id="3ed30-123">Para obter detalhes, consulte o guia de implantação do serviços de Federação do Active Directory 2,0 em <https://go.microsoft.com/fwlink/p/?linkid=267511> .</span><span class="sxs-lookup"><span data-stu-id="3ed30-123">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="3ed30-124">Criar certificados para o AD FS.</span><span class="sxs-lookup"><span data-stu-id="3ed30-124">Create certificates for AD FS.</span></span> <span data-ttu-id="3ed30-125">Para obter mais informações, consulte a seção "certificados do servidor de Federação" do tópico planejar e implantar o AD FS para uso com o logon único em [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="3ed30-125">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="3ed30-126">Na interface de linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3ed30-126">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="3ed30-127">Estabeleça uma parceria executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3ed30-127">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="3ed30-128">Defina as seguintes regras de confiabilidade de parte:</span><span class="sxs-lookup"><span data-stu-id="3ed30-128">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="3ed30-129">Problemas conhecidos que podem impedir a entrada</span><span class="sxs-lookup"><span data-stu-id="3ed30-129">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="3ed30-130">A hora e a data não estão definidas com precisão no dispositivo que está executando o aplicativo Lync da Windows Store</span><span class="sxs-lookup"><span data-stu-id="3ed30-130">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="3ed30-131">A configuração de hora do dispositivo deve ser sincronizada com a configuração de hora no servidor.</span><span class="sxs-lookup"><span data-stu-id="3ed30-131">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="3ed30-132">Isso é particularmente importante para dispositivos como Microsoft Surface e outros dispositivos que executam o Windows RT que não fazem parte de um domínio.</span><span class="sxs-lookup"><span data-stu-id="3ed30-132">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="3ed30-133">Para definir a hora desses dispositivos automaticamente a partir de um servidor de horário, execute o seguinte comando em um prompt de comando com privilégios elevados no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3ed30-133">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="3ed30-134">Aplicativo Lync da Windows Store não pode acessar o Lync Server ou serviços</span><span class="sxs-lookup"><span data-stu-id="3ed30-134">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="3ed30-135">O aplicativo Lync da Windows Store pode não conseguir acessar o Lync Server ou os serviços por meio de adaptadores de rede, como modems USB 4G LTE, que não são registrados com o Windows 8 como dispositivos físicos.</span><span class="sxs-lookup"><span data-stu-id="3ed30-135">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="3ed30-136">O aplicativo Lync da Windows Store pode ter esse problema, mesmo quando os aplicativos e navegadores de desktop podem acessar outros servidores e sites.</span><span class="sxs-lookup"><span data-stu-id="3ed30-136">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="3ed30-137">Aplicativo Lync da Windows Store não é possível entrar com o Lync Server 2010 e o servidor de borda do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="3ed30-137">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="3ed30-138">Se sua topologia consistir no Lync Server 2010 com o servidor de borda do Office Communications Server 2007 R2, será necessário executar a versão atualizada do construtor de topologias disponível na atualização cumulativa do Lync Server 2010: julho de 2013.</span><span class="sxs-lookup"><span data-stu-id="3ed30-138">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="3ed30-139">Versões anteriores do construtor de topologias não criam o mapeamento necessário para o servidor de borda do Office Communications Server 2007, portanto, os clientes do aplicativo do Lync Windows Store não conseguem entrar.</span><span class="sxs-lookup"><span data-stu-id="3ed30-139">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="3ed30-140">As etapas a seguir são necessárias:</span><span class="sxs-lookup"><span data-stu-id="3ed30-140">The following steps are required:</span></span>

1.  <span data-ttu-id="3ed30-141">Instalar a atualização cumulativa do Lync Server 2010:2013 de julho no Lync Server 2010 pools e nos diretores do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3ed30-141">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="3ed30-142">Atualize a configuração de descoberta automática do Lync para indicar que o ponto de entrada SIP externo é o endereço do servidor de borda, fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3ed30-142">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="3ed30-143">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ed30-143">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="3ed30-144">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3ed30-144">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="3ed30-145">Aplicativo Lync da Windows Store não é possível entrar devido a uma falha de validação de nome de certificado</span><span class="sxs-lookup"><span data-stu-id="3ed30-145">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="3ed30-146">Pode ocorrer um problema de entrada para os usuários do Microsoft 365 ou do Office 365 que não estejam executando a versão mais recente do aplicativo Lync da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="3ed30-146">A sign-in issue can occur for Microsoft 365 or Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="3ed30-147">Esse problema geralmente ocorre ao usar vários domínios (por exemplo, quando o URI do SIP é **UserA@domainZ.com** , mas o servidor de borda é **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="3ed30-147">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="3ed30-148">Para corrigir o problema, os usuários devem instalar a versão mais recente do aplicativo Lync da Windows Store, que também requer o Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="3ed30-148">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="3ed30-149">Usar logs de aplicativos do Lync Windows Store para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="3ed30-149">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="3ed30-150">Você pode usar os logs gerados no dispositivo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="3ed30-150">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="3ed30-151">Os logs são armazenados na seguinte pasta:</span><span class="sxs-lookup"><span data-stu-id="3ed30-151">The logs are stored in the following folder:</span></span>

<span data-ttu-id="3ed30-152">% LocalAppData% \\ pacotes \\ Microsoft. LyncMX \_ 8wekyb3d8bbwe \\ localstate de \\ rastreamento</span><span class="sxs-lookup"><span data-stu-id="3ed30-152">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="3ed30-153">Antes de obter os logs de um usuário, verifique se o registro em log está ativado e peça ao usuário para salvar os logs de modo que todas as informações armazenadas na memória também sejam salvas em arquivos no disco rígido.</span><span class="sxs-lookup"><span data-stu-id="3ed30-153">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="3ed30-154">**Para ativar o registro em log**</span><span class="sxs-lookup"><span data-stu-id="3ed30-154">**To turn on logging**</span></span>

1.  <span data-ttu-id="3ed30-155">Abra o aplicativo Lync da Windows Store no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ed30-155">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="3ed30-156">Passe o dedo a partir do lado direito da tela.</span><span class="sxs-lookup"><span data-stu-id="3ed30-156">Swipe from the right side of the screen.</span></span> <span data-ttu-id="3ed30-157">Se você estiver usando um mouse, aponte para o canto superior direito da tela e, em seguida, mova o ponteiro do mouse para baixo na tela.</span><span class="sxs-lookup"><span data-stu-id="3ed30-157">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="3ed30-158">Selecione **configurações**, selecione **Opções**e, em seguida, defina **logs de diagnóstico** como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="3ed30-158">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="3ed30-159">Se **os logs de diagnóstico** estiverem desativados anteriormente, você deverá reiniciar o Lync.</span><span class="sxs-lookup"><span data-stu-id="3ed30-159">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="3ed30-160">Para reiniciar o Lync, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="3ed30-160">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="3ed30-161">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ed30-161">Restart the device.</span></span>
    
      - <span data-ttu-id="3ed30-162">Finalize a tarefa do Lync e inicie o aplicativo novamente.</span><span class="sxs-lookup"><span data-stu-id="3ed30-162">End the Lync task and launch the app again.</span></span> <span data-ttu-id="3ed30-163">Para finalizar a tarefa, abra o Gerenciador de tarefas do Windows, selecione **Lync**e, em seguida, toque em **Finalizar tarefa**.</span><span class="sxs-lookup"><span data-stu-id="3ed30-163">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="3ed30-164">Se o Lync não estiver listado, toque em **mais detalhes** e procure Lync em **processos em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="3ed30-164">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="3ed30-165">**Para salvar os logs**</span><span class="sxs-lookup"><span data-stu-id="3ed30-165">**To save the logs**</span></span>

1.  <span data-ttu-id="3ed30-166">Abra o aplicativo Lync da Windows Store no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3ed30-166">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="3ed30-167">Tente entrar.</span><span class="sxs-lookup"><span data-stu-id="3ed30-167">Try signing in.</span></span>

3.  <span data-ttu-id="3ed30-168">Passe o dedo a partir do lado direito da tela.</span><span class="sxs-lookup"><span data-stu-id="3ed30-168">Swipe from the right side of the screen.</span></span> <span data-ttu-id="3ed30-169">Se você estiver usando um mouse, aponte para o canto superior direito da tela e, em seguida, mova o ponteiro do mouse para baixo na tela.</span><span class="sxs-lookup"><span data-stu-id="3ed30-169">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="3ed30-170">Selecione **configurações**, selecione **sobre**e, em seguida, selecione **salvar logs**.</span><span class="sxs-lookup"><span data-stu-id="3ed30-170">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

