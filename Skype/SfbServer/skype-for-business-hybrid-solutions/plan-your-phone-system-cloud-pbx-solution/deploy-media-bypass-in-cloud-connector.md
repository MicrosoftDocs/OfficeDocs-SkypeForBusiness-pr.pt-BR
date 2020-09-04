---
title: Implantar bypass de mídia no Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Leia este tópico para saber mais sobre as etapas para implantar o bypass de mídia com o Cloud Connector Edition versão 2,0 e posterior.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359307"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="de645-103">Implantar bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="de645-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="de645-104">O Cloud Connector Edition vai retirar 31 de julho de 2021 junto com o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="de645-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="de645-105">Depois que sua organização tiver atualizado para o Microsoft Teams, saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="de645-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="de645-106">Leia este tópico para saber mais sobre as etapas para implantar o bypass de mídia com o Cloud Connector Edition versão 2,0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="de645-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="de645-107">O bypass de mídia permite que um cliente envie mídia diretamente para o próximo salto da PSTN (rede telefônica pública comutada), um gateway ou um SBC (controlador de borda da sessão), e elimine o componente do Cloud Connector Edition do caminho da mídia.</span><span class="sxs-lookup"><span data-stu-id="de645-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="de645-108">Consulte também [Plan for Media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="de645-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="de645-109">Habilitar bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="de645-109">Enable media bypass</span></span>

<span data-ttu-id="de645-110">Para habilitar o bypass de mídia, você deve configurar o nome DNS do serviço Web de bypass de mídia e ativar o bypass de mídia na configuração do locatário.</span><span class="sxs-lookup"><span data-stu-id="de645-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="de645-111">O serviço Web de bypass de mídia é implantado automaticamente em todos os servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="de645-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="de645-112">Um administrador de locatários deve escolher um nome para um serviço de voz híbrido (site) e esse nome deve ser de um domínio SIP registrado para voz híbrida.</span><span class="sxs-lookup"><span data-stu-id="de645-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="de645-113">O nome do serviço deve ser o mesmo em todos os dispositivos do Cloud Connector e todos os sites PSTN, independentemente do local do cliente.</span><span class="sxs-lookup"><span data-stu-id="de645-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="de645-114">O serviço Web só deve estar disponível internamente na rede.</span><span class="sxs-lookup"><span data-stu-id="de645-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="de645-115">Um administrador de locatários deve configurar um registro A de DNS no Active Directory de produção interna.</span><span class="sxs-lookup"><span data-stu-id="de645-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="de645-116">Se você tiver um ambiente complexo de vários sites, consulte o exemplo, no exemplo [: o bypass de mídia de sites DNS em ambientes de vários sites complexos](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="de645-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="de645-117">O registro DNS só deve ser resolvido para clientes de rede interna; Ela não deve ser resolvida para clientes de rede externa.</span><span class="sxs-lookup"><span data-stu-id="de645-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="de645-118">Após configurar o DNS, conecte-se ao Skype for Business online usando o PowerShell remoto com as credenciais de administrador do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="de645-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="de645-119">Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="de645-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="de645-120">Na sessão do PowerShell, insira os seguintes comandos para habilitar o bypass de mídia:</span><span class="sxs-lookup"><span data-stu-id="de645-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="de645-121">Habilitar o bypass de mídia é um processo de duas etapas.</span><span class="sxs-lookup"><span data-stu-id="de645-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="de645-122">O cmdlet New-CsNetworkMedia não salva imediatamente a nova configuração; Ele apenas cria as configurações na memória.</span><span class="sxs-lookup"><span data-stu-id="de645-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="de645-123">O objeto criado por esse cmdlet deve ser salvo em uma variável e, em seguida, atribuído à propriedade MediaBypassSettings da configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="de645-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="de645-124">Para saber mais, confira o [exemplo: os registros DNS do site de bypass de mídia em ambientes de vários sites complexos](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="de645-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="de645-125">A replicação entre os componentes locais e online pode demorar até 24 horas, portanto a Microsoft recomenda que você execute os comandos necessários antes de habilitar os usuários.</span><span class="sxs-lookup"><span data-stu-id="de645-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="de645-126">Confirmar configurações de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="de645-126">Confirm media bypass settings</span></span>

<span data-ttu-id="de645-127">Você pode verificar as configurações de bypass de mídia da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="de645-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="de645-128">Para verificar a replicação online para seu pool de locatários, execute o seguinte comando no PowerShell remoto:</span><span class="sxs-lookup"><span data-stu-id="de645-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="de645-129">Para verificar a replicação local, conecte-se aos servidores de mediação do Cloud Connector, execute o seguinte comando no PowerShell e confirme que Enabled = true e AlwaysBypass = true</span><span class="sxs-lookup"><span data-stu-id="de645-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="de645-130">Para verificar as configurações do cliente, saia do cliente do Skype for Business, entre novamente e confirme que o cliente recebeu a URL do serviço da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="de645-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="de645-131">Abrir%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="de645-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="de645-132">Procure por hybridconfigserviceinternalurl e confirme se a URL corresponde à que você definiu.</span><span class="sxs-lookup"><span data-stu-id="de645-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="de645-133">Alterar parâmetros de bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="de645-133">Change media bypass parameters</span></span>

<span data-ttu-id="de645-134">Os administradores de locatários podem alterar o nome DNS do serviço Web executando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="de645-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="de645-135">Os clientes precisam sair e entrar para obter o novo nome do serviço e reconhecer a alteração.</span><span class="sxs-lookup"><span data-stu-id="de645-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="de645-136">Desabilitar temporariamente o bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="de645-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="de645-137">Este cenário pode ser útil para solução de problemas ou manutenção.</span><span class="sxs-lookup"><span data-stu-id="de645-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="de645-138">Para desabilitar o serviço, execute os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="de645-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="de645-139">Depois de fazer a alteração, pode levar algum tempo para que as alterações sejam replicadas para todos os conectores de nuvem.</span><span class="sxs-lookup"><span data-stu-id="de645-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="de645-140">Para verificar o status da replicação, execute o seguinte cmdlet no PowerShell nos servidores de mediação do Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="de645-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="de645-141">Após as alterações serem replicadas, o serviço Web no servidor de mediação começará a rejeitar solicitações de cliente para o serviço de bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="de645-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="de645-142">Desabilitar o bypass de mídia permanentemente</span><span class="sxs-lookup"><span data-stu-id="de645-142">Disable media bypass permanently</span></span>

<span data-ttu-id="de645-143">Para desabilitar permanentemente o bypass de mídia, um administrador de locatários precisa executar os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="de645-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="de645-144">Um administrador também precisará remover os endereços Web para bypass de mídia de servidores DNS internos.</span><span class="sxs-lookup"><span data-stu-id="de645-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="de645-145">Depois de fazer a alteração, pode levar algum tempo para que as alterações sejam replicadas para todos os dispositivos do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="de645-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="de645-146">Exemplo: os registros DNS do site de bypass de mídia em ambientes de vários sites complexos</span><span class="sxs-lookup"><span data-stu-id="de645-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="de645-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="de645-147"><a name="Example"> </a></span></span>

<span data-ttu-id="de645-148">Os clientes receberão o endereço Web do serviço Web de bypass de mídia de um servidor DNS interno.</span><span class="sxs-lookup"><span data-stu-id="de645-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="de645-149">O nome do serviço Web será o mesmo em todos os dispositivos do Cloud Connector e sites PSTN do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="de645-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="de645-150">Em um ambiente complexo de vários sites, recomendamos o uso da política DNS do Windows 2016 para o gerenciamento de tráfego baseado em localização geográfica, para que os clientes possam ser redirecionados para o serviço Web que é local para sua rede.</span><span class="sxs-lookup"><span data-stu-id="de645-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="de645-151">Confira mais informações sobre as políticas de DNS 2016 [do Windows em usar a política DNS para gerenciamento de tráfego baseado em localização geográfica com servidores primários](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="de645-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="de645-152">Veja a seguir um exemplo de configuração para uma empresa com vários sites usando a política DNS do Windows 2016 para o gerenciamento de tráfego baseado em localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="de645-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="de645-153">O nome do serviço de bypass é ' hybridvoice.adatum.biz '.</span><span class="sxs-lookup"><span data-stu-id="de645-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="de645-154">O site em Amsterdã tem quatro dispositivos do Cloud Connector implantados com os seguintes endereços IP do servidor de mediação:</span><span class="sxs-lookup"><span data-stu-id="de645-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="de645-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="de645-155">192.168.1.45</span></span>
    
- <span data-ttu-id="de645-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="de645-156">192.168.1.46</span></span>
    
- <span data-ttu-id="de645-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="de645-157">192.168.1.47</span></span>
    
- <span data-ttu-id="de645-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="de645-158">192.168.1.48</span></span>
    
<span data-ttu-id="de645-159">O site em Seattle tem três dispositivos do Cloud Connector implantados com os seguintes endereços IP do servidor de mediação:</span><span class="sxs-lookup"><span data-stu-id="de645-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="de645-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="de645-160">10.10.1.8</span></span>
    
- <span data-ttu-id="de645-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="de645-161">10.10.1.9</span></span>
    
- <span data-ttu-id="de645-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="de645-162">10.10.1.10</span></span>
    
<span data-ttu-id="de645-163">Usando o gerenciamento de tráfego baseado em localização geográfica, os servidores DNS seriam configurados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="de645-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="de645-164">Criar sub-redes de cliente DNS para as sub-redes Amsterdã e Seattle.</span><span class="sxs-lookup"><span data-stu-id="de645-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="de645-165">Criar escopos de zona DNS para o adatum.biz para Amsterdã e Seattle.</span><span class="sxs-lookup"><span data-stu-id="de645-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="de645-166">Criar registros DNS em cada escopo de zona DNS.</span><span class="sxs-lookup"><span data-stu-id="de645-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="de645-167">Amsterdã</span><span class="sxs-lookup"><span data-stu-id="de645-167">Amsterdam</span></span>
    
   - <span data-ttu-id="de645-168">Tipo A;</span><span class="sxs-lookup"><span data-stu-id="de645-168">Type A;</span></span>
    
   - <span data-ttu-id="de645-169">Nome: hybridvoice na zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="de645-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="de645-170">Destino: 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="de645-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="de645-171">Criar registros adicionais para servidores de mediação adicionais</span><span class="sxs-lookup"><span data-stu-id="de645-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="de645-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="de645-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="de645-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="de645-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="de645-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="de645-174">192.168.1.48</span></span>
    
     <span data-ttu-id="de645-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="de645-175">Seattle</span></span>
    
   - <span data-ttu-id="de645-176">Digite um</span><span class="sxs-lookup"><span data-stu-id="de645-176">Type A</span></span>
    
   - <span data-ttu-id="de645-177">Nome: hybridvoice na zona DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="de645-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="de645-178">Destino: 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="de645-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="de645-179">Criar registros adicionais para servidores de mediação adicionais</span><span class="sxs-lookup"><span data-stu-id="de645-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="de645-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="de645-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="de645-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="de645-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="de645-182">Crie a política DNS que conecta as sub-redes do cliente aos escopos de zona apropriados para garantir a resolução DNS desejada.</span><span class="sxs-lookup"><span data-stu-id="de645-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="de645-183">Neste ponto, os clientes que fazem consultas de DNS da sub-rede Amsterdã para hybridvoice.adatum.biz retornarão os endereços 192.168.1.45, 192.168.1.46, 192.168.1.47 e 192.168.1.48, enquanto os clientes que fazem a mesma consulta Seattle retornará 10.10.1.8, 10.10.1.9 e 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="de645-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="de645-184">Se o dispositivo CCE não parece estar obtendo as configurações atualizadas, verifique se o dispositivo consegue entrar em contato com o locatário via PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="de645-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="de645-185">Você pode usar o PowerShell remoto para verificar o status do dispositivo com o Get-CsHybridPSTNAppliance ou usar o PowerShell no host do CCE para verificar o status com o Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="de645-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="de645-186">Confira também</span><span class="sxs-lookup"><span data-stu-id="de645-186">See also</span></span>
<span data-ttu-id="de645-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="de645-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="de645-188">Plano para bypass de mídia no Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="de645-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
