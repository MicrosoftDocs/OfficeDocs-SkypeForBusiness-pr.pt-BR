---
title: Mover os usuários do Skype para Business Online no local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Resumo: Saiba como mover as contas de usuário de online para no local no Skype para Business Server.'
ms.openlocfilehash: 655c037fc2299044aa3799d06e0d231784248d7e
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260143"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a><span data-ttu-id="d5d5f-103">Mover os usuários do Skype para Business Online no local</span><span class="sxs-lookup"><span data-stu-id="d5d5f-103">Move users from Skype for Business Online to on premises</span></span>

<span data-ttu-id="d5d5f-104">**Resumo:** Aprenda a mover as contas de usuário de online para no local no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-104">**Summary:** Learn how to move user accounts from online to on premises in Skype for Business Server.</span></span>

<span data-ttu-id="d5d5f-105">Você pode precisar mover as contas de usuário de online para no local para garantir que os usuários hospedagem online e no local são detectáveis uns aos outros.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-105">You might need to move user accounts from online to on premises to ensure that users homed online and on premises are discoverable to one another.</span></span> <span data-ttu-id="d5d5f-106">Para ser descoberto uns aos outros, todos os usuários devem ter uma presença no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-106">To be discoverable to one another, all users must have a presence in the on-premises Active Directory.</span></span> <span data-ttu-id="d5d5f-107">Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="d5d5f-107">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span> <span data-ttu-id="d5d5f-108">Talvez você queira mover usuários online no local, por exemplo, se:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-108">You might want to move online users to on premises, for example, if:</span></span>

- <span data-ttu-id="d5d5f-109">Você tem a novos usuários que precisam ser criadas no local e depois movido para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-109">You have new users who need to be created on premises and then moved to the cloud.</span></span>

- <span data-ttu-id="d5d5f-110">Sua organização implantou o Skype para Business Online antes que ele implantado Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-110">Your organization deployed Skype for Business Online before it deployed Skype for Business Server.</span></span> <span data-ttu-id="d5d5f-111">Portanto, você tiver usuários que foram criados pela primeira vez na nuvem e agora precisa ser movido para no local antes de serem: mover para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-111">Therefore, you have users who were created in the cloud first, and now need to be moved to on premises before they are move to Skype for Business Online.</span></span>

<span data-ttu-id="d5d5f-112">Este tópico descreve os dois cenários:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-112">This topic describes two scenarios:</span></span>

- [<span data-ttu-id="d5d5f-113">Mover usuários online — que estavam originalmente online — como local</span><span class="sxs-lookup"><span data-stu-id="d5d5f-113">Move online users—who were originally online—to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [<span data-ttu-id="d5d5f-114">Mover usuários on-line (que estavam originalmente no local) no local</span><span class="sxs-lookup"><span data-stu-id="d5d5f-114">Move online users (who were originally on premises) to on premises</span></span>](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a><span data-ttu-id="d5d5f-115">Mover usuários online — que estavam originalmente online — como local</span><span class="sxs-lookup"><span data-stu-id="d5d5f-115">Move online users—who were originally online—to on premises</span></span>
<span data-ttu-id="d5d5f-116"><a name="BKMK_originallyonline"> </a></span><span class="sxs-lookup"><span data-stu-id="d5d5f-116"></span></span>

<span data-ttu-id="d5d5f-117">Esta seção se aplica somente aos usuários que foram criados e habilitados online, mas que não têm uma conta do local no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-117">This section applies only to users who were created and enabled online, but who do not have an account in the on premises Active Directory.</span></span>

<span data-ttu-id="d5d5f-118">Antes de iniciar a migração dos usuários online para seu ambiente local, verifique se as opções a seguir são todas verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-118">Before you start moving online users to your on-premises environment, check that all of the following are true:</span></span>

- <span data-ttu-id="d5d5f-119">Seu ambiente local deve estar completamente implantado e validado.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-119">Your on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="d5d5f-120">Para obter mais informações, consulte [Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) ou [Implantar Skype para Business Server 2015](../../deploy/deploy.md), dependendo da versão que você esteja usando no local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-120">For more information, see [Deploying Lync Server 2013](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) or [Deploy Skype for Business Server 2015](../../deploy/deploy.md), depending on which version you are using on premises.</span></span>

- <span data-ttu-id="d5d5f-121">Seu locatário online deve ser configurado para acesso remoto do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-121">Your online tenant must be configured for remote PowerShell access.</span></span>

    <span data-ttu-id="d5d5f-122">Para fazer isso, primeiro instale o Skype para o módulo de conector Business Online para o Windows PowerShell, que você pode obter aqui: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="d5d5f-122">To do this, first install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>

    <span data-ttu-id="d5d5f-123">Após instalar o módulo, você pode estabelecer uma sessão remota digitando os seguintes cmdlets no Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-123">After you install the module, you can establish a remote session by typing the following cmdlets in the Skype for Business Server Management Shell:</span></span>

  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    <span data-ttu-id="d5d5f-124">Para obter mais informações sobre como usar o PowerShell com Skype para Business Online, consulte [Configurar o computador para o Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d5d5f-124">For more information about using PowerShell with Skype for Business Online, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>

- <span data-ttu-id="d5d5f-125">Seu locatário online deve ser configurado para um espaço de endereçamento SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-125">Your online tenant must be configured for a shared SIP address space.</span></span> <span data-ttu-id="d5d5f-126">Para fazer isso, primeiro inicie uma sessão Powershell remota com Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-126">To do this, first start a remote Powershell session with Skype for Business Online.</span></span> <span data-ttu-id="d5d5f-127">Em seguida, execute este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-127">Then run the following cmdlet:</span></span>

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > <span data-ttu-id="d5d5f-128">As necessidades de atributo SharedSipAddressSpace permaneça "True", até que a mudança para online é final e nenhum usuário permanecerão no local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-128">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on premises.</span></span>

<span data-ttu-id="d5d5f-129">Depois que terminar estas etapas, você pode migrar contas de usuário, conforme descrito no procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-129">After you've finished these steps, you can migrate user accounts as described in the following procedure:</span></span>

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a><span data-ttu-id="d5d5f-130">Mover as contas de usuário habilitadas originalmente online em uma implantação local</span><span class="sxs-lookup"><span data-stu-id="d5d5f-130">Move user accounts originally enabled online to an on-premises deployment</span></span>

1. <span data-ttu-id="d5d5f-131">Primeiro, certifique-se de que sua organização está configurada para implantação híbrida, incluindo ferramentas de conexão do Azure Active Directory e de sincronização.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-131">First, make sure that your organization is configured for hybrid, including Azure Active Directory Connect and sync tools.</span></span> <span data-ttu-id="d5d5f-132">Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="d5d5f-132">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>

  - <span data-ttu-id="d5d5f-133">Na sua implantação no local, no Skype do Shell de gerenciamento do servidor de negócios, digite os seguintes cmdlets para criar o provedor de hospedagem para Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-133">On your on-premises deployment, in the Skype for Business Server Management Shell, type the following cmdlets to create the hosting provider for Skype for Business Online.</span></span> <span data-ttu-id="d5d5f-134">Você pode usar o valor que desejar para os parâmetros Identity e Name.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-134">You can use whatever value you want for the Identity and Name parameters.</span></span>

  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. <span data-ttu-id="d5d5f-135">Confirme se em seus servidores de borda de local, você tem a cadeia de certificados que permite a conexão para Skype para negócios Online, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-135">Confirm that on your on-premises Edge Servers, you have the certificate chain that enables connection to Skype for Business Online, as shown in the following table.</span></span> <span data-ttu-id="d5d5f-136">Você pode baixar essa cadeia aqui: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span><span class="sxs-lookup"><span data-stu-id="d5d5f-136">You can download this chain here: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).</span></span>

|<span data-ttu-id="d5d5f-137">**Certificado**</span><span class="sxs-lookup"><span data-stu-id="d5d5f-137">**Certificate**</span></span>|<span data-ttu-id="d5d5f-138">**Repositório de Certificado**</span><span class="sxs-lookup"><span data-stu-id="d5d5f-138">**Certificate Store**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d5d5f-139">Raiz do Baltimore CyberTrust</span><span class="sxs-lookup"><span data-stu-id="d5d5f-139">Baltimore CyberTrust Root</span></span>  <br/> |<span data-ttu-id="d5d5f-140">AC Raiz Confiável</span><span class="sxs-lookup"><span data-stu-id="d5d5f-140">Trusted Root CA</span></span>  <br/> |
|<span data-ttu-id="d5d5f-141">Microsoft Internet Authority (novo certificado CA)</span><span class="sxs-lookup"><span data-stu-id="d5d5f-141">Microsoft Internet Authority (New CA certificate)</span></span>  <br/> |<span data-ttu-id="d5d5f-142">CA intermediário</span><span class="sxs-lookup"><span data-stu-id="d5d5f-142">Intermediate CA</span></span>  <br/> |
|<span data-ttu-id="d5d5f-143">MSIT Machine Auth CA2 (nova emissão de CA2)</span><span class="sxs-lookup"><span data-stu-id="d5d5f-143">MSIT Machine Auth CA2 (New Issuing CA2)</span></span>  <br/> |<span data-ttu-id="d5d5f-144">CA intermediário</span><span class="sxs-lookup"><span data-stu-id="d5d5f-144">Intermediate CA</span></span>  <br/> |

3. <span data-ttu-id="d5d5f-145">Em seu local no Active Directory, habilite as contas de usuário afetado para Skype para negócios 2015 de servidor no local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-145">In your on-premises Active Directory, enable the affected user accounts for Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="d5d5f-146">Essa ação é possível para usuários individuais digitando o cmdlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-146">You can do this for an individual user by typing the following cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity "username "
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    <span data-ttu-id="d5d5f-147">Você também pode criar um script que lê os nomes de usuário a partir de um arquivo e os oferece como input ao cmdlet Enable-CsUser:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-147">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>

  ```
  Enable-CsUser
-Identity $Identity
-SipAddress $SipAddress
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. <span data-ttu-id="d5d5f-148">Sincronize os usuários online com os usuários atualizados no local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-148">Synchronize the online users with the updated on-premises users.</span></span> <span data-ttu-id="d5d5f-149">Para obter mais informações, consulte [Ferramentas de integração de diretório](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span><span class="sxs-lookup"><span data-stu-id="d5d5f-149">For more information, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).</span></span>

5. <span data-ttu-id="d5d5f-150">Atualize os seguintes registros DNS para direcionar todo o tráfego SIP para sua implantação no local:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-150">Update the following DNS records to direct all SIP traffic to your on-premises deployment:</span></span>

  - <span data-ttu-id="d5d5f-151">Atualize o **lyncdiscover.contoso.com** Um registro para apontar ao FQDN do servidor de proxy reverso do local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-151">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>

  - <span data-ttu-id="d5d5f-152">Atualização do \*\* *SIP* . _tls.contoso.com\*\* registro SRV para resolver para o endereço IP ou o VIP público do serviço de borda de acesso do Lync local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-152">Update the ***_sip*  ._tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>

  - <span data-ttu-id="d5d5f-153">Atualização do \*\* *sipfederationtls* . _tcp.contoso.com\*\* registro SRV para resolver para o endereço IP ou o VIP público do serviço de borda de acesso do Skype para Business Server 2015 local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-153">Update the ***_sipfederationtls*  ._tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Skype for Business Server 2015 on-premises.</span></span>

  - <span data-ttu-id="d5d5f-154">Se sua organização utiliza dividido (às vezes chamado de "Split-Brain DNS") de DNS, certifique-se de que os usuários a resolução de nomes por meio da zona DNS interno são direcionados para o Pool Front-End.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-154">If your organization uses split DNS (sometimes called "split-brain DNS"), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6. <span data-ttu-id="d5d5f-155">Tipo de `Get-CsUser` cmdlet para verificar algumas propriedades sobre os usuários que estiver movendo.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-155">Type the  `Get-CsUser` cmdlet to check some properties about the users you'll be moving.</span></span> <span data-ttu-id="d5d5f-156">Certifique-se de que o HostingProviderProxyFQDN esteja definido como `"sipfed.online.lync.com"` e que os endereços SIP estejam definidos corretamente.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-156">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7. <span data-ttu-id="d5d5f-157">Mova usuários online no local.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-157">Move online users to on premises.</span></span>

    <span data-ttu-id="d5d5f-158">Para mover um único usuário, digite:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-158">To move a single user, type this:</span></span>

  ```
  $cred = Get-Credential
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="d5d5f-159">Você pode mover vários usuários usando o cmdlet **Get-CsUSer** com o parâmetro - Filter para selecionar os usuários com uma propriedade específica.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-159">You can move multiple users by using the **Get-CsUSer** cmdlet with the -Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="d5d5f-160">Por exemplo, você pode selecionar todos os usuários Online pela filtragem de {provedor de hospedagem - eq "sipfed.online.lync.om"}.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-160">For example, you could select all Online users by filtering for {Hosting Provider -eq "sipfed.online.lync.om"}.</span></span> <span data-ttu-id="d5d5f-161">Em seguida, você pode direcionar os usuários retornados para o cmdlet **Move-CsUSer** , conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-161">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>

  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    <span data-ttu-id="d5d5f-162">O formato da URL especificado para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool de onde o serviço de migração hospedado estiver em execução, no seguinte formato: _Https://\<FQDN do Pool\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-162">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>

    <span data-ttu-id="d5d5f-163">Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-163">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="d5d5f-164">Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="d5d5f-164">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="d5d5f-165">Faça logon no seu inquilino do Office 365 como um administrador.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-165">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="d5d5f-166">Abra o **Centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-166">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="d5d5f-p112">Com o **Centro de administração do Skype for Business** exibido, selecione e copie a URL na barra de endereço no **lync.com**. Uma URL de exemplo seria parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-p112">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="d5d5f-169">Substitua **webdir** na URL por **admin**, o que resulta no seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-169">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="d5d5f-170">Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-170">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="d5d5f-171">A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-171">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > <span data-ttu-id="d5d5f-172">O tamanho máximo padrão para arquivos de registro de transação do banco de dados rtcxds é 16 GB.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-172">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="d5d5f-173">Isso pode não ser grande o suficiente para se você estiver movendo um grande número de usuários ao mesmo tempo, especialmente se você tiver habilitado o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-173">This might not be big enough if you're moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="d5d5f-174">Para contornar a situação, aumente o tamanho de arquivo ou faça backup dos arquivos de registro regularmente.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-174">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="d5d5f-175">Para obter mais informações, consulte [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span><span class="sxs-lookup"><span data-stu-id="d5d5f-175">For more information, see [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725).</span></span>

8. <span data-ttu-id="d5d5f-176">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-176">This is an optional step.</span></span> <span data-ttu-id="d5d5f-177">Caso precise fazer a integração com o Exchange 2013 Online, será necessário utilizar um provedor de hospedagem adicional.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-177">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="d5d5f-178">Para obter detalhes, consulte [Configure de integração entre o local Skype para Business Server 2015 e Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="d5d5f-178">For details, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).</span></span>

9. <span data-ttu-id="d5d5f-p115">Os usuários foram movidos. Para verificar se um usuário possui os valores corretos dos atributos exibidos na tabela a seguir, digite este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-p115">The users are now moved. To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>

  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|<span data-ttu-id="d5d5f-181">**Atributo do Active Directory**</span><span class="sxs-lookup"><span data-stu-id="d5d5f-181">**Active Directory attribute**</span></span>|<span data-ttu-id="d5d5f-182">**Nome do atributo**</span><span class="sxs-lookup"><span data-stu-id="d5d5f-182">**Attribute name**</span></span>|<span data-ttu-id="d5d5f-183">**Valor correto para usuário Online**</span><span class="sxs-lookup"><span data-stu-id="d5d5f-183">**Correct value for Online user**</span></span>|<span data-ttu-id="d5d5f-184">**Valor correto para usuários locais**</span><span class="sxs-lookup"><span data-stu-id="d5d5f-184">**Correct value for on-premises users**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5d5f-185">msRTCSIP-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="d5d5f-185">msRTCSIP-DeploymentLocator</span></span>  <br/> |<span data-ttu-id="d5d5f-186">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="d5d5f-186">HostingProvider</span></span>  <br/> |<span data-ttu-id="d5d5f-187">sipfed</span><span class="sxs-lookup"><span data-stu-id="d5d5f-187">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="d5d5f-188">SRV:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-188">SRV:</span></span>  <br/> |
|<span data-ttu-id="d5d5f-189">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="d5d5f-189">msRTCSIP-PrimaryUserAddress</span></span>  <br/> |<span data-ttu-id="d5d5f-190">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="d5d5f-190">SIPAddress</span></span>  <br/> |<span data-ttu-id="d5d5f-191">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5d5f-191">sip:userName@contoso.com</span></span>  <br/> |<span data-ttu-id="d5d5f-192">SIP:username@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5d5f-192">sip:userName@contoso.com</span></span>  <br/> |
|<span data-ttu-id="d5d5f-193">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="d5d5f-193">msRTCSIP-UserEnabled</span></span>  <br/> |<span data-ttu-id="d5d5f-194">Habilitado</span><span class="sxs-lookup"><span data-stu-id="d5d5f-194">Enabled</span></span>  <br/> |<span data-ttu-id="d5d5f-195">True</span><span class="sxs-lookup"><span data-stu-id="d5d5f-195">True</span></span>  <br/> |<span data-ttu-id="d5d5f-196">True</span><span class="sxs-lookup"><span data-stu-id="d5d5f-196">True</span></span>  <br/> |

10. <span data-ttu-id="d5d5f-p116">Cada usuário movido precisará fazer logout e fazer login novamente. Ao fazer login, deverão verificar a lista de contatos e adicionar, caso seja necessário.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-p116">Each user who has been moved will need to log out, then log back in. When they log in they should verify their contact lists, and add contacts if needed.</span></span>

    <span data-ttu-id="d5d5f-p117">Observe que as reuniões agendadas não são migradas de online para local. Os usuários precisarão reagendar as reuniões depois de serem movidos.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-p117">Note that scheduled meetings are not migrated from online to on-premises. Users will need to reschedule these meetings after being moved.</span></span>

    <span data-ttu-id="d5d5f-201">Depois que os registros DNS estão atualizados e todos os usuários são direcionados para o local, o atributo HostingProvider direciona o usuário use registros SRV ou direcioná-los para o provedor Online "sipfed."</span><span class="sxs-lookup"><span data-stu-id="d5d5f-201">After the DNS records are updated and all users are directed to On-premises, the HostingProvider attribute directs the user to either use SRV records or direct them to the Online provider "sipfed.online.lync.com."</span></span>

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a><span data-ttu-id="d5d5f-202">Mover usuários on-line (que estavam originalmente no local) no local</span><span class="sxs-lookup"><span data-stu-id="d5d5f-202">Move online users (who were originally on premises) to on premises</span></span>
<span data-ttu-id="d5d5f-203"><a name="BKMK_originallyonprem"> </a></span><span class="sxs-lookup"><span data-stu-id="d5d5f-203"></span></span>

<span data-ttu-id="d5d5f-204">Esta seção se aplica somente aos usuários que foram criados e habilitados para uma implantação local e depois movidos de uma implantação local para online.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-204">This section applies only to users who were created and enabled for an on-premises deployment and then moved from an on-premises deployment to online.</span></span>

- <span data-ttu-id="d5d5f-205">Execute os seguintes cmdlets para mover um usuário do Skype para Business Online para no local, substituindo o valor para os parâmetros **identidade** e de **destino** corrigir os valores para o seu ambiente:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-205">Run the following cmdlets to move a user from Skype for Business Online back to on-premises, replacing the value for the **Identity** and **Target** parameters to correct values for your environment:</span></span>

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

<span data-ttu-id="d5d5f-206">O formato da URL especificado para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool de onde o serviço de migração hospedado estiver em execução, no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-206">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

 <span data-ttu-id="d5d5f-207">_Https://\<FQDN do Pool\>/HostedMigration/hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-207">_Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span> <span data-ttu-id="d5d5f-208">Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-208">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="d5d5f-209">Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="d5d5f-209">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="d5d5f-210">Faça logon no seu inquilino do Office 365 como um administrador.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-210">Login to your Office 365 tenant as an administrator.</span></span>

2. <span data-ttu-id="d5d5f-211">Abra o **Centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-211">Open the **Skype for Business admin center**.</span></span>

3. <span data-ttu-id="d5d5f-p119">Com o **Centro de administração do Skype for Business** exibido, selecione e copie a URL na barra de endereço no **lync.com**. Uma URL de exemplo seria parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-p119">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. <span data-ttu-id="d5d5f-214">Substitua **webdir** na URL por **admin**, o que resulta no seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-214">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>

     `https://admin0a.online.lync.com`

5. <span data-ttu-id="d5d5f-215">Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="d5d5f-215">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>

    <span data-ttu-id="d5d5f-216">A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5d5f-216">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


