---
title: Configurar chamadas de emergência dinâmicas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: Configurar chamadas de emergência dinâmicas
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516928"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="59990-103">Planejar e configurar chamadas de emergência dinâmicas para planos de chamada</span><span class="sxs-lookup"><span data-stu-id="59990-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="59990-104">Chamadas de emergência dinâmicas para planos de chamada da Microsoft fornecem a funcionalidade de configurar e rotear chamadas de emergência com base na localização atual do cliente da equipe.</span><span class="sxs-lookup"><span data-stu-id="59990-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="59990-105">A capacidade de direcionar o roteamento automático para o ponto de resposta de segurança pública adequado (PSAP) ou notificar a equipe de suporte técnico varia de acordo com o país de uso do usuário do teams.</span><span class="sxs-lookup"><span data-stu-id="59990-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="59990-106">Atualmente, o recurso de chamadas de emergência dinâmicos está disponível somente nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="59990-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="59990-107">No entanto, a notificação de segurança técnica tem suporte entre os limites do país.</span><span class="sxs-lookup"><span data-stu-id="59990-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="59990-108">**Nos Estados Unidos**, você pode configurar o roteamento de chamada de emergência dinâmico da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="59990-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="59990-109">Se um cliente do teams estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão roteadas automaticamente para o PSAP que está servindo essa localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="59990-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="59990-110">Se um cliente do Teams não estiver localizado em um local de emergência dinâmico definido pelo locatário, as chamadas de emergência desse cliente serão filtradas por um centro de chamadas nacionais para determinar a localização do chamador antes de transferir a chamada para o PSAP que está servindo dessa localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="59990-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="59990-111">Você pode configurar a notificação do Security Desk da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="59990-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="59990-112">Se um cliente do teams estiver localizado em um site de rede definido pelo locatário, os membros do grupo de segurança configurados para esse site serão notificados.</span><span class="sxs-lookup"><span data-stu-id="59990-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="59990-113">Se um cliente do Teams não estiver localizado em um site de rede definido pelo locatário, os membros do grupo de segurança configurados para o usuário serão notificados.</span><span class="sxs-lookup"><span data-stu-id="59990-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="59990-114">**Fora dos Estados Unidos**, as chamadas de emergência são roteadas para o PSAP que está mapeado para o número de telefone atribuído ao usuário.</span><span class="sxs-lookup"><span data-stu-id="59990-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="59990-115">Em alguns países, como a Grã-Bretanha e o Canadá, as chamadas são as chamadas nacionais antes de transferir o chamador para o PSAP apropriado, enquanto outras roteiam diretamente para o PSAP, independentemente de onde o usuário está localizado no momento.</span><span class="sxs-lookup"><span data-stu-id="59990-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="59990-116">Observe que você pode configurar a notificação do Dynamic Security Desk para todos os usuários do plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="59990-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="59990-117">Clientes com suporte</span><span class="sxs-lookup"><span data-stu-id="59990-117">Supported clients</span></span>

<span data-ttu-id="59990-118">Os clientes a seguir têm suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="59990-118">The following clients are currently supported.</span></span>  <span data-ttu-id="59990-119">Verifique com frequência para ver as atualizações desta lista.</span><span class="sxs-lookup"><span data-stu-id="59990-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="59990-120">Cliente de área de trabalho do teams para Windows</span><span class="sxs-lookup"><span data-stu-id="59990-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="59990-121">Cliente de área de trabalho do teams para Mac</span><span class="sxs-lookup"><span data-stu-id="59990-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="59990-122">Configurar chamadas de emergência dinâmicas</span><span class="sxs-lookup"><span data-stu-id="59990-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="59990-123">Para configurar a chamada de emergência dinâmica, você precisa executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="59990-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="59990-124">Configurar endereços de emergência</span><span class="sxs-lookup"><span data-stu-id="59990-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="59990-125">Definir configurações de rede</span><span class="sxs-lookup"><span data-stu-id="59990-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="59990-126">Configurar o serviço de informações de localização</span><span class="sxs-lookup"><span data-stu-id="59990-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="59990-127">Configurar políticas de emergência</span><span class="sxs-lookup"><span data-stu-id="59990-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="59990-128">Habilitar usuários e sites</span><span class="sxs-lookup"><span data-stu-id="59990-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="59990-129">Testar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="59990-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="59990-130">Configurar endereços de emergência</span><span class="sxs-lookup"><span data-stu-id="59990-130">Configure emergency addresses</span></span>

<span data-ttu-id="59990-131">Para dar suporte ao roteamento automatizado nos Estados Unidos, você deve configurar completamente o endereço cívico que faz parte dos locais de emergência atribuídos a identificadores de rede--e incluir os códigos geográficos associados.</span><span class="sxs-lookup"><span data-stu-id="59990-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="59990-132">(Endereços de emergência sem códigos geográficos não podem ser atribuídos aos identificadores de rede necessários para locais dinâmicos.)</span><span class="sxs-lookup"><span data-stu-id="59990-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="59990-133">Se você inserir um endereço de emergência por meio do centro de administração do Microsoft Teams, os códigos geográficos serão automaticamente incluídos se uma correspondência for encontrada.</span><span class="sxs-lookup"><span data-stu-id="59990-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="59990-134">Se uma coincidência não for encontrada automaticamente, você terá a oportunidade de criar um endereço de emergência manualmente.</span><span class="sxs-lookup"><span data-stu-id="59990-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="59990-135">Isso significa que, se um endereço de emergência existente for configurado para fazer chamadas de emergência, o mesmo endereço precisa ser recriado para incluir os códigos geográficos.</span><span class="sxs-lookup"><span data-stu-id="59990-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="59990-136">Para distinguir entre os dois endereços, você deve incluir uma descrição diferente.</span><span class="sxs-lookup"><span data-stu-id="59990-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="59990-137">O novo endereço de emergência pode ser atribuído aos usuários que têm o endereço antigo.</span><span class="sxs-lookup"><span data-stu-id="59990-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="59990-138">Quando migrado completamente, o endereço antigo pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="59990-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="59990-139">Para obter mais informações sobre como configurar endereços de emergência, consulte [o que são locais de emergência, locais e encaminhamento de chamadas?](what-are-emergency-locations-addresses-and-call-routing.md).</span><span class="sxs-lookup"><span data-stu-id="59990-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="59990-140">Definir configurações de rede</span><span class="sxs-lookup"><span data-stu-id="59990-140">Configure network settings</span></span>

<span data-ttu-id="59990-141">Você precisa definir as configurações de rede para obter dinamicamente um local de emergência usado para roteamento de chamadas de emergência e, opcionalmente, fornecer a configuração dinâmica de notificações de segurança de mesa.</span><span class="sxs-lookup"><span data-stu-id="59990-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="59990-142">A experiência de chamadas de emergência desejada determinará quais configurações de rede precisam ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="59990-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="59990-143">Tenha em mente as seguintes definições:</span><span class="sxs-lookup"><span data-stu-id="59990-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="59990-144">Os IPs confiáveis contêm uma coleção dos IPs externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="59990-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="59990-145">Locais dinâmicos só serão habilitados se o IP externo do usuário corresponder a um IP na coleção de IPs confiáveis.</span><span class="sxs-lookup"><span data-stu-id="59990-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="59990-146">Uma coincidência pode ser feita em endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="59990-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="59990-147">Uma região de rede contém uma coleção de locais de rede.</span><span class="sxs-lookup"><span data-stu-id="59990-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="59990-148">Um site de rede representa um local onde a sua organização tem um valor físico, como um escritório, um conjunto de edifícios ou um campus.</span><span class="sxs-lookup"><span data-stu-id="59990-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="59990-149">Esses sites são definidos como uma coleção de sub-redes IP.</span><span class="sxs-lookup"><span data-stu-id="59990-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="59990-150">Uma sub-rede de rede deve estar associada a um site de rede específico.</span><span class="sxs-lookup"><span data-stu-id="59990-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="59990-151">A localização de um cliente é determinada com base na sub-rede da rede e no site de rede associado.</span><span class="sxs-lookup"><span data-stu-id="59990-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="59990-152">Para usuários do plano de chamada:</span><span class="sxs-lookup"><span data-stu-id="59990-152">For Calling Plan users:</span></span>

- <span data-ttu-id="59990-153">Se a configuração dinâmica da notificação de segurança for necessária, você deverá configurar endereços IP confiáveis e sites de rede.</span><span class="sxs-lookup"><span data-stu-id="59990-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="59990-154">Se forem necessários apenas locais dinâmicos, você deverá configurar apenas endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="59990-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="59990-155">Se nenhuma delas for necessária, a configuração das configurações de rede não será necessária.</span><span class="sxs-lookup"><span data-stu-id="59990-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="59990-156">Para obter mais informações, consulte [definir configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md), que descreve como definir as configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="59990-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="59990-157">(As informações neste artigo se aplicam aos planos de chamada e ao encaminhamento direto.)</span><span class="sxs-lookup"><span data-stu-id="59990-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="59990-158">Configurar o serviço de informações de localização</span><span class="sxs-lookup"><span data-stu-id="59990-158">Configure Location Information Service</span></span>

<span data-ttu-id="59990-159">Um cliente do teams Obtém endereços de emergência dos locais de emergência associados a diferentes identificadores de rede.</span><span class="sxs-lookup"><span data-stu-id="59990-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="59990-160">As sub-redes e pontos de acesso sem fio têm suporte.</span><span class="sxs-lookup"><span data-stu-id="59990-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="59990-161">(O suporte para switch/porta Ethernet está pendente.)</span><span class="sxs-lookup"><span data-stu-id="59990-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="59990-162">Para configurar o LIS (serviço de informações de localização) com identificadores de rede e locais de emergência, use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="59990-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="59990-163">Obter, definir, remover-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="59990-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="59990-164">Obter, definir, remover-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="59990-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="59990-165">Obter, definir, remover-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="59990-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="59990-166">Obter, definir, remover-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="59990-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="59990-167">Se as sub-redes estiverem sendo usadas como parte dos sites de rede, elas deverão ser redefinidas no serviço de informações de localização para renderizar locais dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="59990-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="59990-168">Configurar políticas de emergência</span><span class="sxs-lookup"><span data-stu-id="59990-168">Configure emergency policies</span></span>

<span data-ttu-id="59990-169">As políticas de emergência determinam o que acontece quando um usuário em sua organização faz uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="59990-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="59990-170">Você pode definir quem deseja notificar e como eles são notificados quando um usuário chama serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="59990-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="59990-171">Por exemplo, você pode definir as configurações de política para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="59990-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="59990-172">Para gerenciar as políticas de emergência, use os cmdlets de política New-, Set-CsTeamsEmergencyCalling.</span><span class="sxs-lookup"><span data-stu-id="59990-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="59990-173">Para obter mais informações, consulte [gerenciar políticas de chamadas de emergência no Microsoft Teams](manage-emergency-calling-policies.md).</span><span class="sxs-lookup"><span data-stu-id="59990-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="59990-174">Habilitar usuários e sites</span><span class="sxs-lookup"><span data-stu-id="59990-174">Enable users and sites</span></span>

<span data-ttu-id="59990-175">Enquanto os usuários do plano de chamada são habilitados automaticamente para chamadas de emergência, você deve habilitar os usuários para a notificação de segurança, configurando a política de chamadas de emergência, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="59990-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="59990-176">Você também pode atribuir a política de chamadas de emergência a um site de rede, conforme mostrado no exemplo a seguir, que atribui uma política chamada "política de chamadas de emergência da Contoso 1" ao site 1:</span><span class="sxs-lookup"><span data-stu-id="59990-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="59990-177">Se você atribuiu uma política de chamadas de emergência a um site de rede e a um usuário, e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="59990-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="59990-178">Testar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="59990-178">Test emergency calling</span></span>

<span data-ttu-id="59990-179">Para testar as chamadas de emergência nos Estados Unidos, use o número de emergência de teste predefinido 933.</span><span class="sxs-lookup"><span data-stu-id="59990-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="59990-180">Esse número é roteado para um bot, que então ecoa novamente o número de telefone do chamador (ID da linha de chamada), o endereço de emergência ou o local e se a chamada é automaticamente roteada para o PSAP ou com a tela em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="59990-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  