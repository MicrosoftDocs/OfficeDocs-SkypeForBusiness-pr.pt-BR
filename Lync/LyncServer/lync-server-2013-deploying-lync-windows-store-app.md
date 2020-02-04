---
title: 'Lync Server 2013: Implantando o aplicativo Lync da Windows Store'
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
ms.openlocfilehash: 49fcea107a4613ca78661a21d492612f82d9775f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="99613-102">Implantando o aplicativo Lync da Windows Store no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99613-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99613-103">_**Tópico da última modificação:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="99613-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="99613-104">Antes de disponibilizar o aplicativo Lync da Windows Store para os usuários, certifique-se de que sua implantação atenda aos [requisitos do aplicativo Lync da Windows Store para o Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99613-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="99613-105">Para obter detalhes sobre como configurar o Lync Server 2013 para dar suporte ao aplicativo Lync da Windows Store, consulte o artigo "NextHop" do Lync Server e o aplicativo Lync da [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)Windows Store "em.</span><span class="sxs-lookup"><span data-stu-id="99613-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="99613-106">Após a configuração correta do ambiente do servidor, você pode direcionar os usuários para baixar o aplicativo Lync da Windows Store ao procurar por "Lync".</span><span class="sxs-lookup"><span data-stu-id="99613-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="99613-107">Habilitando a autenticação multifator para o aplicativo Lync da Windows Store</span><span class="sxs-lookup"><span data-stu-id="99613-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="99613-108">Atualizações cumulativas do Lync Server 2013:2013 de junho adiciona suporte para a autenticação multifator para os clientes do aplicativo Lync da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="99613-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="99613-109">Além do nome de usuário e da senha, você pode exigir métodos de autenticação adicionais, como cartões inteligentes ou PINs, para autenticar usuários externos quando eles entrarem em reuniões do Lync.</span><span class="sxs-lookup"><span data-stu-id="99613-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="99613-110">Para habilitar a autenticação multifator, implante o serviço de Federação do Active Directory (AD FS) e habilite a autenticação passiva no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99613-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="99613-111">Após a configuração do AD FS, os usuários externos que tentam ingressar em reuniões do Lync são apresentados com uma página da Web de autenticação multifator do AD FS que contém o nome de usuário e o desafio da senha, juntamente com qualquer método de autenticação adicional que você tenha configurado .</span><span class="sxs-lookup"><span data-stu-id="99613-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="99613-112">Veja a seguir considerações importantes se você planeja configurar o AD FS para autenticação multifator para o aplicativo Lync da Windows Store:</span><span class="sxs-lookup"><span data-stu-id="99613-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="99613-113">Lync Server 2013 com atualizações cumulativas do Lync Server 2013:2013 de junho é necessário no mínimo.</span><span class="sxs-lookup"><span data-stu-id="99613-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="99613-114">Os clientes de desktop do Lync 2013 não exigem atualizações cumulativas do Lync Server 2013:2013 de junho, portanto, pode parecer que a autenticação passiva está funcionando porque os clientes do Lync 2013 são capazes de se autenticar.</span><span class="sxs-lookup"><span data-stu-id="99613-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="99613-115">No entanto, o processo de autenticação para os clientes do aplicativo Lync da Windows Store falhará em concluir, e nenhuma mensagem de erro será exibida.</span><span class="sxs-lookup"><span data-stu-id="99613-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="99613-116">O servidor deve ser configurado para que a autenticação passiva seja o único tipo de autenticação oferecido.</span><span class="sxs-lookup"><span data-stu-id="99613-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="99613-117">Se você usar balanceadores de carga de hardware, habilite a persistência de cookies nos balanceadores de carga para que todas as solicitações do cliente do aplicativo Lync da Windows Store sejam manipuladas pelo mesmo servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="99613-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="99613-118">Quando você estabelece uma relação de confiança entre terceira parte confiável entre os servidores do Lync Server e do AD FS, atribua uma vida de token longa o suficiente para abranger o tamanho máximo de suas reuniões do Lync.</span><span class="sxs-lookup"><span data-stu-id="99613-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="99613-119">Normalmente, uma vida de token de 240 minutos é suficiente.</span><span class="sxs-lookup"><span data-stu-id="99613-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="99613-120">**Para configurar a autenticação multifator**</span><span class="sxs-lookup"><span data-stu-id="99613-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="99613-121">Instale uma função de servidor de federação AD FS.</span><span class="sxs-lookup"><span data-stu-id="99613-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="99613-122">Para obter detalhes, consulte o guia de implantação do serviços de Federação <http://go.microsoft.com/fwlink/p/?linkid=267511>do Active Directory 2,0 em.</span><span class="sxs-lookup"><span data-stu-id="99613-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="99613-123">Crie certificados para o AD FS.</span><span class="sxs-lookup"><span data-stu-id="99613-123">Create certificates for AD FS.</span></span> <span data-ttu-id="99613-124">Para obter mais informações, consulte a seção "certificados do servidor de Federação" do tópico planejar e implantar o AD FS para uso com o tópico logon [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)único em.</span><span class="sxs-lookup"><span data-stu-id="99613-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="99613-125">Na interface de linha de comando do Windows PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="99613-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="99613-126">Estabeleça uma parceria executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="99613-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="99613-127">Defina as seguintes regras de confiabilidade de parte:</span><span class="sxs-lookup"><span data-stu-id="99613-127">Set the following relying party rules:</span></span>
    
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

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="99613-128">Problemas conhecidos que podem impedir a entrada</span><span class="sxs-lookup"><span data-stu-id="99613-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="99613-129">A hora e a data não estão definidas com precisão no dispositivo que está executando o aplicativo Lync da Windows Store</span><span class="sxs-lookup"><span data-stu-id="99613-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="99613-130">A configuração de hora no dispositivo deve ser sincronizada com a configuração de hora no servidor.</span><span class="sxs-lookup"><span data-stu-id="99613-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="99613-131">Isso é especialmente importante para dispositivos como Microsoft Surface e outros dispositivos que executam o Windows RT que não fazem parte de um domínio.</span><span class="sxs-lookup"><span data-stu-id="99613-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="99613-132">Para definir o tempo desses dispositivos automaticamente a partir de um servidor de horário, execute o seguinte comando em um prompt de comando elevado no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="99613-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="99613-133">O aplicativo Lync da Windows Store não pode acessar o servidor ou serviços do Lync</span><span class="sxs-lookup"><span data-stu-id="99613-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="99613-134">O aplicativo Lync da Windows Store pode não conseguir acessar o servidor ou serviços do Lync por meio de adaptadores de rede, como modems USB 4G LTE, que não se registram no Windows 8 como dispositivos físicos.</span><span class="sxs-lookup"><span data-stu-id="99613-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="99613-135">O aplicativo Lync da Windows Store pode ter esse problema mesmo quando os aplicativos da área de trabalho e navegadores são capazes de acessar outros servidores e sites.</span><span class="sxs-lookup"><span data-stu-id="99613-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="99613-136">O aplicativo Lync da Windows Store não pode entrar com o Lync Server 2010 e o Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="99613-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="99613-137">Se a sua topologia consistir no Lync Server 2010 com o Office Communications Server 2007 R2 Edge Server, será necessário executar a versão atualizada do construtor de topologias disponível na atualização cumulativa do Lync Server 2010: julho de 2013.</span><span class="sxs-lookup"><span data-stu-id="99613-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="99613-138">As versões anteriores do construtor de topologias não criam o mapeamento obrigatório para o servidor de borda do Office Communications Server 2007, portanto, os clientes do aplicativo Lync da Windows Store não conseguem entrar.</span><span class="sxs-lookup"><span data-stu-id="99613-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="99613-139">As seguintes etapas são necessárias:</span><span class="sxs-lookup"><span data-stu-id="99613-139">The following steps are required:</span></span>

1.  <span data-ttu-id="99613-140">Instale a atualização cumulativa do Lync Server 2010:2013 de julho no Lync Server 2010 pools e nos directors do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="99613-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="99613-141">Atualize a configuração de descoberta automática do Lync para indicar que o ponto de entrada SIP externo é o endereço do servidor de borda fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="99613-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="99613-142">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99613-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="99613-143">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="99613-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="99613-144">O aplicativo Lync da Windows Store não pode entrar devido a uma falha na validação do nome do certificado</span><span class="sxs-lookup"><span data-stu-id="99613-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="99613-145">Pode ocorrer um problema de entrada para os usuários do Office 365 que não estão executando a versão mais recente do aplicativo Lync da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="99613-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="99613-146">Geralmente, esse problema ocorre ao usar vários domínios (por exemplo, quando o URI SIP é **UserA@domainZ.com** , mas o servidor de borda é **SIP.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="99613-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="99613-147">Para corrigir o problema, os usuários devem instalar a versão mais recente do aplicativo Lync da Windows Store, que também requer o Windows 8,1.</span><span class="sxs-lookup"><span data-stu-id="99613-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="99613-148">Usar os logs do aplicativo Lync da Windows Store para solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="99613-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="99613-149">Você pode usar os logs gerados no dispositivo para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="99613-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="99613-150">Os logs são armazenados na seguinte pasta:</span><span class="sxs-lookup"><span data-stu-id="99613-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="99613-151">% LocalAppData%\\pacotes\\Microsoft. LyncMX\_8wekyb3d8bbwe\\o\\rastreamento localstate</span><span class="sxs-lookup"><span data-stu-id="99613-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="99613-152">Antes de obter os logs de um usuário, verifique se o registro em log está ativado e peça para o usuário salvar os logs para que todas as informações armazenadas na memória também sejam salvas em arquivos no disco rígido.</span><span class="sxs-lookup"><span data-stu-id="99613-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="99613-153">**Para ativar o registro em log**</span><span class="sxs-lookup"><span data-stu-id="99613-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="99613-154">Abra o aplicativo Lync da Windows Store no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99613-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="99613-155">Passe o dedo do lado direito da tela.</span><span class="sxs-lookup"><span data-stu-id="99613-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="99613-156">Se você estiver usando um mouse, aponte para o canto superior direito da tela e, em seguida, mova o ponteiro do mouse para baixo na tela.</span><span class="sxs-lookup"><span data-stu-id="99613-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="99613-157">Selecione **configurações**, selecione **Opções**e, em seguida, defina **os logs de diagnóstico** como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="99613-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="99613-158">Se **os logs de diagnóstico** tiverem sido desativados anteriormente, reinicie o Lync.</span><span class="sxs-lookup"><span data-stu-id="99613-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="99613-159">Para reiniciar o Lync, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="99613-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="99613-160">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99613-160">Restart the device.</span></span>
    
      - <span data-ttu-id="99613-161">Encerre a tarefa do Lync e inicie o aplicativo novamente.</span><span class="sxs-lookup"><span data-stu-id="99613-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="99613-162">Para finalizar a tarefa, abra o Gerenciador de tarefas do Windows, selecione **Lync**e, em seguida, toque em **Finalizar tarefa**.</span><span class="sxs-lookup"><span data-stu-id="99613-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="99613-163">Se o Lync não estiver listado, toque em **mais detalhes** e procure o Lync em **processos em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="99613-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="99613-164">**Para salvar os logs**</span><span class="sxs-lookup"><span data-stu-id="99613-164">**To save the logs**</span></span>

1.  <span data-ttu-id="99613-165">Abra o aplicativo Lync da Windows Store no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99613-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="99613-166">Tente entrar.</span><span class="sxs-lookup"><span data-stu-id="99613-166">Try signing in.</span></span>

3.  <span data-ttu-id="99613-167">Passe o dedo do lado direito da tela.</span><span class="sxs-lookup"><span data-stu-id="99613-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="99613-168">Se você estiver usando um mouse, aponte para o canto superior direito da tela e, em seguida, mova o ponteiro do mouse para baixo na tela.</span><span class="sxs-lookup"><span data-stu-id="99613-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="99613-169">Selecione **configurações**, selecionar **sobre**e, em seguida, selecione **salvar logs**.</span><span class="sxs-lookup"><span data-stu-id="99613-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

