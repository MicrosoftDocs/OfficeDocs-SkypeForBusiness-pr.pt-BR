---
title: Implantar o bypass de mídia no Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leia este tópico para saber sobre etapas para implantar o bypass de mídia com o conector de nuvem Edition versão 2.0 e posteriores.
ms.openlocfilehash: ec6647c5d95701ea18a6d403132d50ae8e8ad8dc
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890639"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="73bfb-103">Implantar o bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="73bfb-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="73bfb-104">Leia este tópico para saber sobre etapas para implantar o bypass de mídia com o conector de nuvem Edition versão 2.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="73bfb-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="73bfb-105">Bypass de mídia permite que um cliente enviar mídia diretamente para o próximo salto de rede de telefônica pública comutada (PSTN) — um gateway ou controlador de borda de sessão (SBC) — e eliminar o componente de edição do conector de nuvem do caminho de mídia.</span><span class="sxs-lookup"><span data-stu-id="73bfb-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="73bfb-106">Consulte também [Planejar media bypass na nuvem conector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="73bfb-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="73bfb-107">Habilitar bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="73bfb-107">Enable media bypass</span></span>

<span data-ttu-id="73bfb-108">Para habilitar o bypass de mídia, você deve configurar o nome DNS do serviço Web do bypass de mídia e ativar o bypass de mídia na configuração do locatário.</span><span class="sxs-lookup"><span data-stu-id="73bfb-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="73bfb-109">O serviço Web de bypass de mídia é implantado automaticamente em cada Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="73bfb-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="73bfb-110">Um administrador de locatário precisa escolher um nome para um serviço de voz híbrido (site), e esse nome deve ser de um domínio SIP registrado para voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="73bfb-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="73bfb-111">O nome do serviço deve ser o mesmo em todos os aparelhos de conector de nuvem e todos os sites PSTN, independentemente da localização do cliente.</span><span class="sxs-lookup"><span data-stu-id="73bfb-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="73bfb-112">O serviço Web só deve estar disponível internamente na rede.</span><span class="sxs-lookup"><span data-stu-id="73bfb-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="73bfb-113">O administrador do locatário deve configurar um registro A DNS no Active Directory da produção interna.</span><span class="sxs-lookup"><span data-stu-id="73bfb-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="73bfb-114">Se você tiver um ambiente complexo de vários local, consulte o exemplo [exemplo: registros DNS do site da web em ambientes de vários locais complexos de bypass de mídia](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="73bfb-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="73bfb-115">O registro DNS deve resolver apenas clientes da rede interna; ele não deve resolver clientes da rede externa.</span><span class="sxs-lookup"><span data-stu-id="73bfb-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="73bfb-116">Depois de configurar o DNS, conecte-se ao Skype for Business Online usando o PowerShell remoto com as credenciais de administrador do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="73bfb-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="73bfb-117">Para obter mais informações, consulte [Connecting to Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="73bfb-117">For more information, see [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="73bfb-118">Na sessão do PowerShell, insira os seguintes comandos para habilitar o bypass de mídia:</span><span class="sxs-lookup"><span data-stu-id="73bfb-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="73bfb-119">Habilitando o bypass de mídia em um processo de duas etapas.</span><span class="sxs-lookup"><span data-stu-id="73bfb-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="73bfb-120">O cmdlet New-CsNetworkMedia não salva imediatamente a nova configuração; ele só cria as configurações na memória.</span><span class="sxs-lookup"><span data-stu-id="73bfb-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="73bfb-121">O objeto criado por este cmdlet deve ser salvo como uma variável, e então atribuído à propriedade MediaBypassSettings da configuração da rede.</span><span class="sxs-lookup"><span data-stu-id="73bfb-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="73bfb-122">Para obter mais informações, consulte [exemplo: registros DNS do site da web em ambientes de vários locais complexos de bypass de mídia](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="73bfb-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="73bfb-123">A replicação entre os componentes locais e online pode demorar até 24 horas, portanto a Microsoft recomenda que você execute os comandos necessários antes de habilitar os usuários. </span><span class="sxs-lookup"><span data-stu-id="73bfb-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="73bfb-124">Confirmar as configurações de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="73bfb-124">Confirm media bypass settings</span></span>

<span data-ttu-id="73bfb-125">Você pode verificar as configurações de bypass de mídia da seguinte maneira. </span><span class="sxs-lookup"><span data-stu-id="73bfb-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="73bfb-126">Para verificar a replicação on-line para seu pool de locatário, execute o seguinte comando no PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="73bfb-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="73bfb-127">Para verificar a replicação do local, conecte-se para os servidores de mediação do conector de nuvem, execute o seguinte comando no PowerShell e confirme que Enabled = True e AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="73bfb-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="73bfb-128">Para verificar as configurações do cliente, sair do Skype para o cliente de negócios, entrar novamente e confirme se o cliente recebeu a URL do serviço da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="73bfb-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="73bfb-129">Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. </span><span class="sxs-lookup"><span data-stu-id="73bfb-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="73bfb-130">Procure por hybridconfigserviceinternalurl e confirme se a URL corresponde à que você definiu. </span><span class="sxs-lookup"><span data-stu-id="73bfb-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="73bfb-131">Alterar parâmetros de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="73bfb-131">Change media bypass parameters</span></span>

<span data-ttu-id="73bfb-132">Os administradores de locatários podem alterar o nome DNS do serviço Web executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="73bfb-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="73bfb-133">Os clientes precisam sair e entrar novamente para obter o novo nome do serviço e reconhecer a mudança. </span><span class="sxs-lookup"><span data-stu-id="73bfb-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="73bfb-134">Desabilitar o bypass de mídia temporariamente</span><span class="sxs-lookup"><span data-stu-id="73bfb-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="73bfb-p106">Esse cenário pode ser útil para a solução de problemas ou para a manutenção. Para desabilitar o serviço, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="73bfb-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="73bfb-137">Depois de fazer a alteração, pode levar algum tempo até que as alterações sejam replicadas em todos os Cloud Connectors.</span><span class="sxs-lookup"><span data-stu-id="73bfb-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="73bfb-138">Para verificar o status da replicação, execute o seguinte cmdlet do PowerShell nos servidores de mediação do conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="73bfb-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="73bfb-139">Depois de replicadas as alterações, o serviço Web no Servidor de Mediação começará a rejeitar solicitações de cliente para o serviço de bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="73bfb-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="73bfb-140">Desabilitar o bypass de mídia permanentemente</span><span class="sxs-lookup"><span data-stu-id="73bfb-140">Disable media bypass permanently</span></span>

<span data-ttu-id="73bfb-141">Para a desabilitação permanente do bypass de mídia, um administrador de locatários precisa executar os seguintes comandos: </span><span class="sxs-lookup"><span data-stu-id="73bfb-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="73bfb-142">O administrador também precisará remover os endereços da web para o bypass de mídia dos servidores DNS internos.</span><span class="sxs-lookup"><span data-stu-id="73bfb-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="73bfb-143">Após a alteração, ele pode levar algum tempo para que as alterações replicar para todos os aparelhos de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="73bfb-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="73bfb-144">Exemplo: registros DNS do site de bypass de mídia em ambientes complexos multissites.</span><span class="sxs-lookup"><span data-stu-id="73bfb-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="73bfb-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="73bfb-145"></span></span>

<span data-ttu-id="73bfb-146">Os clientes receberão o endereço web do serviço de bypass de mídia de um servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="73bfb-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="73bfb-147">O nome do serviço da web será o mesmo em todos os aparelhos de conector de nuvem e sites de PSTN do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="73bfb-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="73bfb-148">Em um ambiente complexo multissites, recomendamos usar a política de DNS do Windows 2016 para localização geográfica com base em gerenciamento de tráfego para que os clientes possam ser redirecionados para o serviço Web que seja local para a sua rede.</span><span class="sxs-lookup"><span data-stu-id="73bfb-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="73bfb-149">Para obter mais informações sobre políticas de DNS do Windows 2016, consulte [Usar diretivas de DNS para o gerenciamento de tráfego com base em localização geográfica com servidores primários](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="73bfb-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="73bfb-150">Veja a seguir um exemplo de configuração para uma empresa com vários sites usando a Política DNS do Windows 2016 para Localização geográfica com base em gerenciamento de tráfego.</span><span class="sxs-lookup"><span data-stu-id="73bfb-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="73bfb-151">O nome para o serviço de desvio é 'hybridvoice.adatum.biz'.</span><span class="sxs-lookup"><span data-stu-id="73bfb-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="73bfb-152">O site no Amsterdã tem quatro aparelhos de nuvem conector implantados com os seguintes endereços IP do servidor de mediação:</span><span class="sxs-lookup"><span data-stu-id="73bfb-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="73bfb-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="73bfb-153">192.168.1.45</span></span>
    
- <span data-ttu-id="73bfb-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="73bfb-154">192.168.1.46</span></span>
    
- <span data-ttu-id="73bfb-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="73bfb-155">192.168.1.47</span></span>
    
- <span data-ttu-id="73bfb-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="73bfb-156">192.168.1.48</span></span>
    
<span data-ttu-id="73bfb-157">O site em Seattle tem três aparelhos de nuvem conector implantados com os seguintes endereços IP do servidor de mediação:</span><span class="sxs-lookup"><span data-stu-id="73bfb-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="73bfb-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="73bfb-158">10.10.1.8</span></span>
    
- <span data-ttu-id="73bfb-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="73bfb-159">10.10.1.9</span></span>
    
- <span data-ttu-id="73bfb-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="73bfb-160">10.10.1.10</span></span>
    
<span data-ttu-id="73bfb-161">Usando-se a Localização geográfica com base em gerenciamento de tráfego, os servidores DNS seriam configurados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="73bfb-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="73bfb-162">Crie sub-redes de cliente DNS para ambas as sub-redes de Amsterdã e de Seattle.</span><span class="sxs-lookup"><span data-stu-id="73bfb-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="73bfb-163">Crie escopos de zona DNS para adatum.biz tanto para Amsterdã quanto para Seattle.</span><span class="sxs-lookup"><span data-stu-id="73bfb-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="73bfb-164">Crie registros DNS em cada escopo de zona DNS.</span><span class="sxs-lookup"><span data-stu-id="73bfb-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="73bfb-165">Amsterdã</span><span class="sxs-lookup"><span data-stu-id="73bfb-165">Amsterdam</span></span>
    
  - <span data-ttu-id="73bfb-166">Tipo A;</span><span class="sxs-lookup"><span data-stu-id="73bfb-166">Type A;</span></span>
    
  - <span data-ttu-id="73bfb-167">Nome : hybridvoice na zona DNS de adatum.biz</span><span class="sxs-lookup"><span data-stu-id="73bfb-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="73bfb-168">Destino: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="73bfb-168">Target: 192.168.1.45</span></span>
    
    <span data-ttu-id="73bfb-169">Crie registros adicionais para servidores de mediação adicionais</span><span class="sxs-lookup"><span data-stu-id="73bfb-169">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="73bfb-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="73bfb-170">192.168.1.46</span></span>
    
  - <span data-ttu-id="73bfb-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="73bfb-171">192.168.1.47</span></span>
    
  - <span data-ttu-id="73bfb-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="73bfb-172">192.168.1.48</span></span>
    
    <span data-ttu-id="73bfb-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="73bfb-173">Seattle</span></span>
    
  - <span data-ttu-id="73bfb-174">Tipo A</span><span class="sxs-lookup"><span data-stu-id="73bfb-174">Type A</span></span>
    
  - <span data-ttu-id="73bfb-175">Nome : hybridvoice na zona DNS de adatum.biz</span><span class="sxs-lookup"><span data-stu-id="73bfb-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="73bfb-176">Destino: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="73bfb-176">Target: 10.10.1.8</span></span>
    
    <span data-ttu-id="73bfb-177">Crie registros adicionais para servidores de mediação adicionais</span><span class="sxs-lookup"><span data-stu-id="73bfb-177">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="73bfb-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="73bfb-178">10.10.1.9</span></span>
    
  - <span data-ttu-id="73bfb-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="73bfb-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="73bfb-180">Crie a política DNS que conecta as sub-redes do cliente aos escopos de zona apropriados para garantir a resolução de DNS desejada.</span><span class="sxs-lookup"><span data-stu-id="73bfb-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="73bfb-181">Neste ponto, os clientes que fizerem consultas DNS da sub-rede de Amsterdã para hybridvoice.adatum.biz retornarão os endereços 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, enquanto os clientes que fizerem a mesma consulta de Seattle retornarão 10.10.1.8, 10.10.1.9 e 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="73bfb-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="73bfb-182">Se o aparelho de CCE não parece estar recebendo as configurações atualizadas, verifique se o aparelho é capaz de contatar o locatário via o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="73bfb-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="73bfb-183">Você pode usar o PowerShell remoto para verificar o status de aparelho com Get-CsHybridPSTNAppliance ou usar o PowerShell para verificar o status com o Get-CcApplianceStatus no host CCE.</span><span class="sxs-lookup"><span data-stu-id="73bfb-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="73bfb-184">Ver também</span><span class="sxs-lookup"><span data-stu-id="73bfb-184">See also</span></span>
<span data-ttu-id="73bfb-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="73bfb-185"></span></span>

[<span data-ttu-id="73bfb-186">Planejar o bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="73bfb-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
