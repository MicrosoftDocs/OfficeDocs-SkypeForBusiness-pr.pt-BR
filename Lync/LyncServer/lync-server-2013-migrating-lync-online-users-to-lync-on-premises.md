---
title: 'Lync Server 2013: migrando os usuários do Lync Online para o Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8806610d8ede0932a9e1f6048d892a48f104d3
ms.sourcegitcommit: e487637fc122727b41b37961f208ddc0d20a3fce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34845060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="fef9b-102">Migrando usuários do Lync Online para o Lync local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef9b-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef9b-103">_**Tópico da última modificação:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="fef9b-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="fef9b-104">Essas etapas são necessárias somente para migrar contas de usuário originalmente habilitadas para o Lync no Lync Online antes de você implantar o Lync local.</span><span class="sxs-lookup"><span data-stu-id="fef9b-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="fef9b-105">Para mover os usuários que foram originalmente habilitados para o Lync local e depois foram movidos para o Lync Online, consulte <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">administrando usuários em uma implantação híbrida do Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fef9b-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="fef9b-106">Além disso, todos os usuários que migrarem devem ter contas no Diretório Ativo local.</span><span class="sxs-lookup"><span data-stu-id="fef9b-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="fef9b-107">Migrando contas de usuário originalmente habilitadas no Lync Online para o Lync local</span><span class="sxs-lookup"><span data-stu-id="fef9b-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="fef9b-108">Primeiro, verifique se a sua organização está configurada para híbrido.</span><span class="sxs-lookup"><span data-stu-id="fef9b-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="fef9b-109">Instale a ferramenta de sincronização do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fef9b-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="fef9b-110">Para obter mais informações, <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>consulte.</span><span class="sxs-lookup"><span data-stu-id="fef9b-110">For more information, see <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="fef9b-111">Para permitir que seus usuários usem o logon único para o Lync Online, instale os serviços <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>de Federação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fef9b-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="fef9b-112">Na sua implantação local, no Shell de gerenciamento do Lync Server, digite os seguintes cmdlets para criar o provedor de hospedagem para o Lync Online:</span><span class="sxs-lookup"><span data-stu-id="fef9b-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="fef9b-113">Confirme que, em seus servidores de borda local, você tem a cadeia de certificados que permite a conexão com o Lync Online, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fef9b-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="fef9b-114">Você pode baixar esta cadeia aqui:https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="fef9b-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="fef9b-115">Certificado</span><span class="sxs-lookup"><span data-stu-id="fef9b-115">Certificate</span></span></th>
    <th><span data-ttu-id="fef9b-116">Repositório de Certificado</span><span class="sxs-lookup"><span data-stu-id="fef9b-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="fef9b-117">Raiz do Baltimore CyberTrust</span><span class="sxs-lookup"><span data-stu-id="fef9b-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-118">AC Raiz Confiável</span><span class="sxs-lookup"><span data-stu-id="fef9b-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fef9b-119">Microsoft Internet Authority (novo certificado CA)</span><span class="sxs-lookup"><span data-stu-id="fef9b-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-120">CA intermediário</span><span class="sxs-lookup"><span data-stu-id="fef9b-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fef9b-121">MSIT Machine Auth CA2 (nova emissão de CA2)</span><span class="sxs-lookup"><span data-stu-id="fef9b-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-122">CA intermediário</span><span class="sxs-lookup"><span data-stu-id="fef9b-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="fef9b-123">Em seu Active Directory local, habilite as contas de usuário afetadas no Lync local.</span><span class="sxs-lookup"><span data-stu-id="fef9b-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="fef9b-124">Essa ação é possível para usuários individuais digitando o cmdlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="fef9b-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="fef9b-125">Você também pode criar um script que lê os nomes de usuário a partir de um arquivo e os oferece como input ao cmdlet Enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="fef9b-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="fef9b-126">Execute o DirSync para sincronizar os usuários do Lync Online com os usuários do Lync local atualizados.</span><span class="sxs-lookup"><span data-stu-id="fef9b-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="fef9b-127">Atualize alguns registros DNS para direcionar todo o tráfego SIP para o Lync local:</span><span class="sxs-lookup"><span data-stu-id="fef9b-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="fef9b-128">Atualize o **lyncdiscover.contoso.com** Um registro para apontar ao FQDN do servidor de proxy reverso do local.</span><span class="sxs-lookup"><span data-stu-id="fef9b-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="fef9b-129">Atualize o \*\*\*\_SIP \*.\_ \*\*registro SRV TLS.contoso.com para resolver para o endereço IP público ou VIP do serviço de borda de acesso do Lync local.</span><span class="sxs-lookup"><span data-stu-id="fef9b-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="fef9b-130">Atualize o \*\*\*\_sipfederationtls \*.\_ \*\*registro SRV TCP.contoso.com para resolver para o endereço IP público ou VIP do serviço de borda de acesso do Lync local.</span><span class="sxs-lookup"><span data-stu-id="fef9b-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="fef9b-131">Se sua organização usa DNS divididos (conhecidos como “split-brain DNS”), certifique-se de que os usuários que solucionam nomes por meio da zona DNS interna sejam direcionados ao Pool de Front-ends.</span><span class="sxs-lookup"><span data-stu-id="fef9b-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="fef9b-132">Digite o `Get-CsUser` cmdlet para verificar algumas propriedades sobre os usuários que você moverá.</span><span class="sxs-lookup"><span data-stu-id="fef9b-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="fef9b-133">Você deseja certificar-se de que o HostingProviderProxyFQDN está definido `"sipfed.online.lync.com"` e que os endereços SIP estão definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="fef9b-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="fef9b-134">Mover os usuários do Lync Online para o Lync local.</span><span class="sxs-lookup"><span data-stu-id="fef9b-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="fef9b-135">Para mover um único usuário, digite:</span><span class="sxs-lookup"><span data-stu-id="fef9b-135">To move a single user, type this:</span></span>
    
       ```
       $cred = Get-Credential
       ```
    
       ```
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="fef9b-136">Você pode mover usuários únicos por meio do cmdlet **Get-CsUSer** com o parâmetro –Filtro para selecionar os usuários com determinada propriedade.</span><span class="sxs-lookup"><span data-stu-id="fef9b-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="fef9b-137">Por exemplo, você pode selecionar todos os usuários do Lync Online filtrando para {host Provider – EQ "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="fef9b-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="fef9b-138">Em seguida, poderá canalizar os usuários retornados para o cmdlet **Move-CsUSer**, como mostra abaixo.</span><span class="sxs-lookup"><span data-stu-id="fef9b-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="fef9b-139">O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL do pool em que o serviço de migração hospedada está em execução, no seguinte formato *:\<https://pool\>FQDN/HostedMigration/ hostedmigrationService. svc*.</span><span class="sxs-lookup"><span data-stu-id="fef9b-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="fef9b-140">Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="fef9b-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="fef9b-141">Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="fef9b-141">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>
    
    1.  <span data-ttu-id="fef9b-142">Faça logon no seu inquilino do Office 365 como um administrador.</span><span class="sxs-lookup"><span data-stu-id="fef9b-142">Login to your Office 365 tenant as an administrator.</span></span>
    
    2.  <span data-ttu-id="fef9b-143">Abra o **centro de administração do Lync**.</span><span class="sxs-lookup"><span data-stu-id="fef9b-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="fef9b-144">Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="fef9b-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="fef9b-145">Uma URL de exemplo seria parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="fef9b-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="fef9b-146">Substitua **webdir** na URL por **admin**, o que resulta no seguinte:</span><span class="sxs-lookup"><span data-stu-id="fef9b-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="fef9b-147">Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="fef9b-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="fef9b-148">A URL resultante, que tem o valor de **HostedMigrationOverrideUrl**, deverá ser parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="fef9b-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="fef9b-149">O tamanho máximo padrão para arquivos de registro de transação do banco de dados rtcxds é 16 GB.</span><span class="sxs-lookup"><span data-stu-id="fef9b-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="fef9b-150">Este tamanho pode não ser suficiente caso você esteja movendo uma grande quantidade de usuários de uma só vez, especialmente se o espelhamento estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="fef9b-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="fef9b-151">Para contornar a situação, aumente o tamanho de arquivo ou faça backup dos arquivos de registro regularmente.</span><span class="sxs-lookup"><span data-stu-id="fef9b-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="fef9b-152">Para obter mais informações, <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>consulte.</span><span class="sxs-lookup"><span data-stu-id="fef9b-152">For more information, see <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="fef9b-153">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="fef9b-153">This is an optional step.</span></span> <span data-ttu-id="fef9b-154">Caso precise fazer a integração com o Exchange 2013 Online, será necessário utilizar um provedor de hospedagem adicional.</span><span class="sxs-lookup"><span data-stu-id="fef9b-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="fef9b-155">Para obter detalhes, consulte Configurando [a integração do Lync Server 2013 no Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="fef9b-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="fef9b-p110">Os usuários foram movidos. Para verificar se um usuário possui os valores corretos dos atributos exibidos na tabela a seguir, digite este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fef9b-p110">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
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
    <th><span data-ttu-id="fef9b-158">Atributo do Active Directory</span><span class="sxs-lookup"><span data-stu-id="fef9b-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="fef9b-159">Nome do atributo</span><span class="sxs-lookup"><span data-stu-id="fef9b-159">Attribute name</span></span></th>
    <th><span data-ttu-id="fef9b-160">Valor correto para o usuário do Lync Online</span><span class="sxs-lookup"><span data-stu-id="fef9b-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="fef9b-161">Valor correto para usuários do Lync on-premises</span><span class="sxs-lookup"><span data-stu-id="fef9b-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="fef9b-162">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="fef9b-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-163">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="fef9b-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fef9b-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-165">SRV:</span><span class="sxs-lookup"><span data-stu-id="fef9b-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fef9b-166">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="fef9b-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-167">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="fef9b-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef9b-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef9b-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fef9b-170">sRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="fef9b-170">sRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-171">Habilitado</span><span class="sxs-lookup"><span data-stu-id="fef9b-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-172">True</span><span class="sxs-lookup"><span data-stu-id="fef9b-172">True</span></span></p></td>
    <td><p><span data-ttu-id="fef9b-173">True</span><span class="sxs-lookup"><span data-stu-id="fef9b-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="fef9b-174">Cada usuário que tiver sido movido precisará fazer logoff do Lync e, em seguida, conectar-se novamente.</span><span class="sxs-lookup"><span data-stu-id="fef9b-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="fef9b-175">Ao fazer login, deverão verificar a lista de contatos e adicionar, caso seja necessário.</span><span class="sxs-lookup"><span data-stu-id="fef9b-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="fef9b-176">Observe que as reuniões agendadas não são migradas do Lync Online para o Lync local.</span><span class="sxs-lookup"><span data-stu-id="fef9b-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="fef9b-177">Os usuários precisarão reagendar as reuniões depois de serem movidos.</span><span class="sxs-lookup"><span data-stu-id="fef9b-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="fef9b-178">Depois que os registros DNS são atualizados e todos os usuários são direcionados para o local, o atributo Hostingprovider direciona o usuário do Lync para usar registros SRV ou direcioná-los para o provedor online "sipfed.online.lync.com".</span><span class="sxs-lookup"><span data-stu-id="fef9b-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

