---
title: Implantar o bypass de mídia no Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leia este tópico para saber mais sobre as etapas de implantação do bypass de mídia com o Cloud Connector Edition versão 2,0 e posterior.
ms.openlocfilehash: 6f3ad140d25d5f1d03196e576ac57dc56e905d44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287542"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="89250-103">Implantar o bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="89250-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="89250-104">Leia este tópico para saber mais sobre as etapas de implantação do bypass de mídia com o Cloud Connector Edition versão 2,0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="89250-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="89250-105">O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da rede telefônica pública comutada (PSTN), um gateway ou um controlador de borda de sessão (SBC), e elimine o componente da edição do conector de nuvem do caminho de mídia.</span><span class="sxs-lookup"><span data-stu-id="89250-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="89250-106">Consulte também [planejar a bypass de mídia na edição do Cloud Connector](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="89250-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="89250-107">Habilitar bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="89250-107">Enable media bypass</span></span>

<span data-ttu-id="89250-108">Para habilitar o bypass de mídia, você deve configurar o nome DNS do serviço Web do bypass de mídia e ativar o bypass de mídia na configuração do locatário.</span><span class="sxs-lookup"><span data-stu-id="89250-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="89250-109">O serviço Web de bypass de mídia é implantado automaticamente em cada Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="89250-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="89250-110">Um administrador de locatário precisa escolher um nome para um serviço de voz híbrido (site), e esse nome deve ser de um domínio SIP registrado para voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="89250-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="89250-111">O nome do serviço deve ser o mesmo em todos os dispositivos de conector de nuvem e em todos os sites PSTN, independentemente do local do cliente.</span><span class="sxs-lookup"><span data-stu-id="89250-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="89250-112">O serviço Web só deve estar disponível internamente na rede.</span><span class="sxs-lookup"><span data-stu-id="89250-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="89250-113">O administrador do locatário deve configurar um registro A DNS no Active Directory da produção interna.</span><span class="sxs-lookup"><span data-stu-id="89250-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="89250-114">Se você tiver um ambiente de vários sites complexo, consulte o exemplo no exemplo [: ignorar o site do Web site registros DNS em ambientes com vários sites complexos](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="89250-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="89250-115">O registro DNS deve resolver apenas clientes da rede interna; ele não deve resolver clientes da rede externa.</span><span class="sxs-lookup"><span data-stu-id="89250-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="89250-116">Depois de configurar o DNS, conecte-se ao Skype for Business Online usando o PowerShell remoto com as credenciais de administrador do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="89250-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="89250-117">Para obter mais informações, consulte [configurar seu computador para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="89250-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="89250-118">Na sessão do PowerShell, insira os seguintes comandos para habilitar o bypass de mídia:</span><span class="sxs-lookup"><span data-stu-id="89250-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="89250-119">Habilitando o bypass de mídia em um processo de duas etapas.</span><span class="sxs-lookup"><span data-stu-id="89250-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="89250-120">O cmdlet New-CsNetworkMedia não salva imediatamente a nova configuração; ele só cria as configurações na memória.</span><span class="sxs-lookup"><span data-stu-id="89250-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="89250-121">O objeto criado por este cmdlet deve ser salvo como uma variável, e então atribuído à propriedade MediaBypassSettings da configuração da rede.</span><span class="sxs-lookup"><span data-stu-id="89250-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="89250-122">Para obter mais informações, consulte [exemplo: ignorar a mídia de registros DNS de sites em ambientes complexos de vários locais](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="89250-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="89250-123">A replicação entre os componentes locais e online pode demorar até 24 horas, portanto a Microsoft recomenda que você execute os comandos necessários antes de habilitar os usuários.</span><span class="sxs-lookup"><span data-stu-id="89250-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="89250-124">Confirmar as configurações de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="89250-124">Confirm media bypass settings</span></span>

<span data-ttu-id="89250-125">Você pode verificar as configurações de bypass de mídia da seguinte maneira. </span><span class="sxs-lookup"><span data-stu-id="89250-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="89250-126">Para verificar a replicação online para o pool do locatário, execute o seguinte comando no PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="89250-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="89250-127">Para verificar a replicação local, conecte-se aos servidores de remediação do conector de nuvem, execute o seguinte comando no PowerShell e confirme se Enabled = true e AlwaysBypass = true</span><span class="sxs-lookup"><span data-stu-id="89250-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="89250-128">Para verificar as configurações do cliente, desconecte-se do cliente Skype for Business, entre novamente e confirme se o cliente recebeu a URL do serviço da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="89250-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="89250-129">Abra %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="89250-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="89250-130">Procure por hybridconfigserviceinternalurl e confirme se a URL corresponde à que você definiu.</span><span class="sxs-lookup"><span data-stu-id="89250-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="89250-131">Alterar parâmetros de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="89250-131">Change media bypass parameters</span></span>

<span data-ttu-id="89250-132">Os administradores de locatários podem alterar o nome DNS do serviço Web executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="89250-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="89250-133">Os clientes precisam sair e entrar novamente para obter o novo nome do serviço e reconhecer a mudança. </span><span class="sxs-lookup"><span data-stu-id="89250-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="89250-134">Desabilitar o bypass de mídia temporariamente</span><span class="sxs-lookup"><span data-stu-id="89250-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="89250-p106">Esse cenário pode ser útil para a solução de problemas ou para a manutenção. Para desabilitar o serviço, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="89250-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="89250-137">Depois de fazer a alteração, pode levar algum tempo até que as alterações sejam replicadas em todos os Cloud Connectors.</span><span class="sxs-lookup"><span data-stu-id="89250-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="89250-138">Para verificar o status da replicação, execute o seguinte cmdlet no PowerShell em servidores de Media Connector:</span><span class="sxs-lookup"><span data-stu-id="89250-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="89250-139">Depois de replicadas as alterações, o serviço Web no Servidor de Mediação começará a rejeitar solicitações de cliente para o serviço de bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="89250-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="89250-140">Desabilitar o bypass de mídia permanentemente</span><span class="sxs-lookup"><span data-stu-id="89250-140">Disable media bypass permanently</span></span>

<span data-ttu-id="89250-141">Para a desabilitação permanente do bypass de mídia, um administrador de locatários precisa executar os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="89250-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="89250-142">O administrador também precisará remover os endereços da web para o bypass de mídia dos servidores DNS internos.</span><span class="sxs-lookup"><span data-stu-id="89250-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="89250-143">Depois de fazer a alteração, pode levar algum tempo para que as alterações sejam replicadas para todos os aparelhos de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="89250-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="89250-144">Exemplo: registros DNS do site de bypass de mídia em ambientes complexos multissites.</span><span class="sxs-lookup"><span data-stu-id="89250-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="89250-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="89250-145"></span></span>

<span data-ttu-id="89250-146">Os clientes receberão o endereço web do serviço de bypass de mídia de um servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="89250-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="89250-147">O nome do serviço Web será o mesmo em todos os dispositivos de conector de nuvem e sites PSTN do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="89250-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="89250-148">Em um ambiente complexo multissites, recomendamos usar a política de DNS do Windows 2016 para localização geográfica com base em gerenciamento de tráfego para que os clientes possam ser redirecionados para o serviço Web que seja local para a sua rede.</span><span class="sxs-lookup"><span data-stu-id="89250-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="89250-149">Para saber mais sobre as políticas de DNS do Windows 2016, consulte [usar a política DNS para gerenciamento de tráfego baseado em localização geográfica com servidores primários](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="89250-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="89250-150">Veja a seguir um exemplo de configuração para uma empresa com vários sites usando a Política DNS do Windows 2016 para Localização geográfica com base em gerenciamento de tráfego.</span><span class="sxs-lookup"><span data-stu-id="89250-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="89250-151">O nome do serviço de bypass é ' hybridvoice.adatum.biz '.</span><span class="sxs-lookup"><span data-stu-id="89250-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="89250-152">O site em Amsterdã tem quatro dispositivos de conector de nuvem implantados com os seguintes endereços IP do servidor de mediação:</span><span class="sxs-lookup"><span data-stu-id="89250-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="89250-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="89250-153">192.168.1.45</span></span>
    
- <span data-ttu-id="89250-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="89250-154">192.168.1.46</span></span>
    
- <span data-ttu-id="89250-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="89250-155">192.168.1.47</span></span>
    
- <span data-ttu-id="89250-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="89250-156">192.168.1.48</span></span>
    
<span data-ttu-id="89250-157">O site em Seattle tem três dispositivos de conector de nuvem implantados com os seguintes endereços IP do servidor de mediação:</span><span class="sxs-lookup"><span data-stu-id="89250-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="89250-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="89250-158">10.10.1.8</span></span>
    
- <span data-ttu-id="89250-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="89250-159">10.10.1.9</span></span>
    
- <span data-ttu-id="89250-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="89250-160">10.10.1.10</span></span>
    
<span data-ttu-id="89250-161">Usando-se a Localização geográfica com base em gerenciamento de tráfego, os servidores DNS seriam configurados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="89250-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="89250-162">Crie sub-redes de cliente DNS para ambas as sub-redes de Amsterdã e de Seattle.</span><span class="sxs-lookup"><span data-stu-id="89250-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="89250-163">Crie escopos de zona DNS para adatum.biz tanto para Amsterdã quanto para Seattle.</span><span class="sxs-lookup"><span data-stu-id="89250-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="89250-164">Crie registros DNS em cada escopo de zona DNS.</span><span class="sxs-lookup"><span data-stu-id="89250-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="89250-165">Amsterdã</span><span class="sxs-lookup"><span data-stu-id="89250-165">Amsterdam</span></span>
    
   - <span data-ttu-id="89250-166">Tipo A;</span><span class="sxs-lookup"><span data-stu-id="89250-166">Type A;</span></span>
    
   - <span data-ttu-id="89250-167">Nome : hybridvoice na zona DNS de adatum.biz</span><span class="sxs-lookup"><span data-stu-id="89250-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="89250-168">Destino: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="89250-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="89250-169">Crie registros adicionais para servidores de mediação adicionais</span><span class="sxs-lookup"><span data-stu-id="89250-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="89250-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="89250-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="89250-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="89250-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="89250-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="89250-172">192.168.1.48</span></span>
    
     <span data-ttu-id="89250-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="89250-173">Seattle</span></span>
    
   - <span data-ttu-id="89250-174">Tipo A</span><span class="sxs-lookup"><span data-stu-id="89250-174">Type A</span></span>
    
   - <span data-ttu-id="89250-175">Nome : hybridvoice na zona DNS de adatum.biz</span><span class="sxs-lookup"><span data-stu-id="89250-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="89250-176">Destino: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="89250-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="89250-177">Crie registros adicionais para servidores de mediação adicionais</span><span class="sxs-lookup"><span data-stu-id="89250-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="89250-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="89250-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="89250-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="89250-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="89250-180">Crie a política DNS que conecta as sub-redes do cliente aos escopos de zona apropriados para garantir a resolução de DNS desejada.</span><span class="sxs-lookup"><span data-stu-id="89250-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="89250-181">Neste ponto, os clientes que fizerem consultas DNS da sub-rede de Amsterdã para hybridvoice.adatum.biz retornarão os endereços 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, enquanto os clientes que fizerem a mesma consulta de Seattle retornarão 10.10.1.8, 10.10.1.9 e 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="89250-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="89250-182">Se o dispositivo CCE parece não ter as configurações atualizadas, verifique se o dispositivo consegue entrar em contato com o locatário via PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="89250-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="89250-183">Você pode usar o PowerShell remoto para verificar o status do aplicativo com Get-CsHybridPSTNAppliance ou usar o PowerShell no host CCE para verificar o status com Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="89250-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="89250-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="89250-184">See also</span></span>
<span data-ttu-id="89250-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="89250-185"></span></span>

[<span data-ttu-id="89250-186">Plano para bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="89250-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
