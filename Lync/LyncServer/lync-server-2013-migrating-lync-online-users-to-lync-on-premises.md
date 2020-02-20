---
title: 'Lync Server 2013: Migrando usuários do Lync Online para o Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07a333eeb794a27ca78b1f6d8c9bf71c386c8a92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="baff0-102">Migração de usuários do Lync Online para o Lync no local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="baff0-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baff0-103">_**Última modificação do tópico:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="baff0-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="baff0-104">Essas etapas são necessárias somente para migrar contas de usuário que foram originalmente habilitadas para Lync no Lync Online, antes de implantar o Lync local.</span><span class="sxs-lookup"><span data-stu-id="baff0-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="baff0-105">Para mover os usuários que foram originalmente habilitados para o Lync local e depois movidos para o Lync Online, consulte <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administração de usuários em uma implantação híbrida do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="baff0-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="baff0-106">Além disso, todos os usuários que estão sendo movidos devem ter contas no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="baff0-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="baff0-107">Migrando contas de usuário originalmente habilitadas no Lync Online para o Lync local</span><span class="sxs-lookup"><span data-stu-id="baff0-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="baff0-108">Primeiro, certifique-se de que sua organização está configurada para híbrido.</span><span class="sxs-lookup"><span data-stu-id="baff0-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="baff0-109">Instale a ferramenta de sincronização do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="baff0-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="baff0-110">Para obter mais informações, confira <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span><span class="sxs-lookup"><span data-stu-id="baff0-110">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="baff0-111">Para permitir que os usuários usem o single sign-on para o Lync Online, instale os serviços <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>de Federação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="baff0-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="baff0-112">Em sua implantação local, no Shell de gerenciamento do Lync Server, digite os cmdlets a seguir para criar o provedor de hospedagem para o Lync Online:</span><span class="sxs-lookup"><span data-stu-id="baff0-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="baff0-113">Confirme que, em seus servidores de borda no local, você tem a cadeia de certificados que permite a conexão com o Lync Online, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="baff0-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="baff0-114">Você pode baixar essa cadeia aqui:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="baff0-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="baff0-115">Certificado</span><span class="sxs-lookup"><span data-stu-id="baff0-115">Certificate</span></span></th>
    <th><span data-ttu-id="baff0-116">Repositório de Certificados</span><span class="sxs-lookup"><span data-stu-id="baff0-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="baff0-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="baff0-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="baff0-118">AC raiz confiável</span><span class="sxs-lookup"><span data-stu-id="baff0-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="baff0-119">Autoridade da Internet da Microsoft (novo certificado de autoridade de certificação)</span><span class="sxs-lookup"><span data-stu-id="baff0-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="baff0-120">Autoridade de certificação intermediária</span><span class="sxs-lookup"><span data-stu-id="baff0-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="baff0-121">MSIT de autenticação de máquina CA2 (nova CA2 de emissão)</span><span class="sxs-lookup"><span data-stu-id="baff0-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="baff0-122">Autoridade de certificação intermediária</span><span class="sxs-lookup"><span data-stu-id="baff0-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="baff0-123">No Active Directory local, habilite as contas de usuário afetadas para o Lync local.</span><span class="sxs-lookup"><span data-stu-id="baff0-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="baff0-124">Você pode fazer isso para um usuário individual digitando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="baff0-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="baff0-125">Ou você pode criar um script que lê os nomes de usuário de um arquivo e os fornece como entrada para o cmdlet Enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="baff0-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="baff0-126">Execute DirSync para sincronizar os usuários do Lync Online com os usuários locais do Lync atualizados.</span><span class="sxs-lookup"><span data-stu-id="baff0-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="baff0-127">Atualize alguns registros DNS para direcionar todo o tráfego SIP para o Lync local:</span><span class="sxs-lookup"><span data-stu-id="baff0-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="baff0-128">Atualize o **Lyncdiscover.contoso.com** um registro para apontar para o FQDN do servidor de proxy reverso local.</span><span class="sxs-lookup"><span data-stu-id="baff0-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="baff0-129">Atualize o \*\**\_SIP *.\_ tls.contoso.com** registro SRV para resolver para o endereço IP público ou VIP do serviço de borda de acesso do Lync local.</span><span class="sxs-lookup"><span data-stu-id="baff0-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="baff0-130">Atualize o \*\**\_sipfederationtls *.\_ tcp.contoso.com** registro SRV para resolver para o endereço IP público ou VIP do serviço de borda de acesso do Lync local.</span><span class="sxs-lookup"><span data-stu-id="baff0-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="baff0-131">Se sua organização usa DNS dividido (às vezes chamado de "DNS de divisões"), certifique-se de que os usuários que resolvem nomes através da zona DNS interna sejam direcionados para o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="baff0-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="baff0-132">Digite o `Get-CsUser` cmdlet para verificar algumas propriedades sobre os usuários que serão movidos.</span><span class="sxs-lookup"><span data-stu-id="baff0-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="baff0-133">Você deseja certificar-se de que o HostingProviderProxyFQDN está definido `"sipfed.online.lync.com"` como e que os endereços SIP estão definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="baff0-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="baff0-134">Mover os usuários do Lync Online para o Lync no local.</span><span class="sxs-lookup"><span data-stu-id="baff0-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="baff0-135">Para mover um único usuário, digite:</span><span class="sxs-lookup"><span data-stu-id="baff0-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="baff0-136">Você pode mover vários usuários usando o cmdlet **Get-CsUSer** com o parâmetro – Filter para selecionar os usuários com uma propriedade específica.</span><span class="sxs-lookup"><span data-stu-id="baff0-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="baff0-137">Por exemplo, você pode selecionar todos os usuários do Lync Online filtrando para {Hosting Provider – EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="baff0-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="baff0-138">Você pode canalizar os usuários retornados para o cmdlet **move-CsUSer** , como mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="baff0-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="baff0-139">O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool em que o serviço de migração hospedado está sendo executado, no seguinte formato *:\</HostedMigration/hostedmigrationService.svc do\>pool https://FQDN*.</span><span class="sxs-lookup"><span data-stu-id="baff0-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="baff0-140">Você pode determinar a URL para o serviço de migração hospedado visualizando a URL do painel de controle do Lync Online para sua conta de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="baff0-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="baff0-141">Para determinar a URL do serviço de migração hospedado para seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="baff0-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="baff0-142">Faça logon no seu locatário do Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="baff0-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="baff0-143">Abra o **centro de administração do Lync**.</span><span class="sxs-lookup"><span data-stu-id="baff0-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="baff0-144">Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="baff0-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="baff0-145">Uma URL de exemplo é semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="baff0-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="baff0-146">Substitua **Webdir** na URL por **admin**, resultando no seguinte:</span><span class="sxs-lookup"><span data-stu-id="baff0-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="baff0-147">Acrescente a seguinte cadeia de caracteres à URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="baff0-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="baff0-148">A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="baff0-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="baff0-149">O tamanho máximo padrão para os arquivos de log de transações do banco de dados do rtcxds é de 16 GB.</span><span class="sxs-lookup"><span data-stu-id="baff0-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="baff0-150">Isso pode não ser grande o suficiente se você estiver movendo um grande número de usuários de uma só vez, especialmente se você tiver o espelhamento habilitado.</span><span class="sxs-lookup"><span data-stu-id="baff0-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="baff0-151">Para contornar isso, você pode aumentar o tamanho do arquivo ou fazer o backup dos arquivos de log regularmente.</span><span class="sxs-lookup"><span data-stu-id="baff0-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="baff0-152">Para obter mais informações, <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>consulte.</span><span class="sxs-lookup"><span data-stu-id="baff0-152">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="baff0-153">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="baff0-153">This is an optional step.</span></span> <span data-ttu-id="baff0-154">Se for necessário integrar com o Exchange 2013 online, você precisará usar um provedor de hospedagem adicional.</span><span class="sxs-lookup"><span data-stu-id="baff0-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="baff0-155">Para obter detalhes, consulte [Configuring on-premises Lync Server 2013 Integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="baff0-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="baff0-156">Os usuários agora serão movidos.</span><span class="sxs-lookup"><span data-stu-id="baff0-156">The users are now moved.</span></span> <span data-ttu-id="baff0-157">Para verificar se um usuário tem valores corretos para os atributos mostrados na tabela a seguir, digite este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="baff0-157">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="baff0-158">Atributo do Active Directory</span><span class="sxs-lookup"><span data-stu-id="baff0-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="baff0-159">Nome do atributo</span><span class="sxs-lookup"><span data-stu-id="baff0-159">Attribute name</span></span></th>
    <th><span data-ttu-id="baff0-160">Valor correto para o usuário do Lync Online</span><span class="sxs-lookup"><span data-stu-id="baff0-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="baff0-161">Valor correto para usuários do Lync on-premises</span><span class="sxs-lookup"><span data-stu-id="baff0-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="baff0-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="baff0-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="baff0-163">Hostingprovider</span><span class="sxs-lookup"><span data-stu-id="baff0-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="baff0-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="baff0-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="baff0-165">SRV</span><span class="sxs-lookup"><span data-stu-id="baff0-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="baff0-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="baff0-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="baff0-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="baff0-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="baff0-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="baff0-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="baff0-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="baff0-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="baff0-170">msRTCSIP-userhabilitado</span><span class="sxs-lookup"><span data-stu-id="baff0-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="baff0-171">Habilitado</span><span class="sxs-lookup"><span data-stu-id="baff0-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="baff0-172">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="baff0-172">True</span></span></p></td>
    <td><p><span data-ttu-id="baff0-173">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="baff0-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="baff0-174">Cada usuário que tiver sido movido precisará fazer logout do Lync e, em seguida, fazer logon novamente.</span><span class="sxs-lookup"><span data-stu-id="baff0-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="baff0-175">Quando eles fazem logon, eles devem verificar suas listas de contatos e adicionar contatos, se necessário.</span><span class="sxs-lookup"><span data-stu-id="baff0-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="baff0-176">Observe que as reuniões agendadas não são migradas do Lync Online para o Lync local.</span><span class="sxs-lookup"><span data-stu-id="baff0-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="baff0-177">Os usuários precisarão reagendar essas reuniões após serem movidas.</span><span class="sxs-lookup"><span data-stu-id="baff0-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="baff0-178">Depois que os registros DNS são atualizados e todos os usuários são direcionados para o local, o atributo Hostingprovider orienta o usuário do Lync a usar registros SRV ou direcioná-los ao provedor online "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="baff0-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

