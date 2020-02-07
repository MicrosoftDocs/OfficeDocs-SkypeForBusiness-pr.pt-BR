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
f1.keywords:
- NOCSH
description: Configurar chamadas de emergência dinâmicas
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cd5f3320896c823eb81a9147a1b1b1adb36dbac
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825509"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="08ae2-103">Planejar e configurar chamadas de emergência dinâmicas</span><span class="sxs-lookup"><span data-stu-id="08ae2-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="08ae2-104">Chamadas de emergência dinâmicas para planos de chamadas e roteamento direto do sistema telefônico fornecem a funcionalidade de configurar e direcionar chamadas de emergência e notificar o pessoal de segurança com base na localização atual do cliente da equipe.</span><span class="sxs-lookup"><span data-stu-id="08ae2-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="08ae2-105">Com base na topologia de rede que o administrador do locatário define, o cliente do teams fornece informações de conectividade de rede em uma solicitação para o serviço de informações de localização (LIS).</span><span class="sxs-lookup"><span data-stu-id="08ae2-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span>  <span data-ttu-id="08ae2-106">Se houver uma correspondência, o LIS retornará um local para o cliente.</span><span class="sxs-lookup"><span data-stu-id="08ae2-106">If there is a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="08ae2-107">Esses dados de localização são transmitidos de volta para o cliente.</span><span class="sxs-lookup"><span data-stu-id="08ae2-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="08ae2-108">O cliente do teams inclui dados de localização como parte de uma chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="08ae2-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="08ae2-109">Esses dados são usados pelo provedor de serviços de emergência para determinar o ponto de resposta de segurança pública apropriado (PSAP) e para direcionar a chamada para esse PSAP, que permite que o PSAP Dispatcher obtenha a localização do chamador.</span><span class="sxs-lookup"><span data-stu-id="08ae2-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="08ae2-110">Para fazer chamadas de emergência dinâmicas, o seguinte deve ocorrer:</span><span class="sxs-lookup"><span data-stu-id="08ae2-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="08ae2-111">O administrador de rede define as configurações de rede e o LIS para criar um mapa de local de emergência/rede.</span><span class="sxs-lookup"><span data-stu-id="08ae2-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="08ae2-112">Para roteamento direto, a configuração adicional é necessária para roteamento de chamadas de emergência e possivelmente para conectividade de parceiro.</span><span class="sxs-lookup"><span data-stu-id="08ae2-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="08ae2-113">O administrador deve configurar a conexão para um provedor de serviços de roteamento de emergência (ERS) **ou** configurar o controlador de borda de sessão (SBC) para um aplicativo de número de identificação de localização (Elin) de emergência.</span><span class="sxs-lookup"><span data-stu-id="08ae2-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="08ae2-114">Durante a inicialização e depois, periodicamente, ou quando uma conexão de rede é alterada, o cliente das equipes envia uma solicitação de localização que contém suas informações de conectividade de rede para as configurações de rede e o LIS.</span><span class="sxs-lookup"><span data-stu-id="08ae2-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="08ae2-115">Se houver uma correspondência de site de configurações de rede – as políticas de chamadas de emergência serão retornadas ao cliente do teams desse site.</span><span class="sxs-lookup"><span data-stu-id="08ae2-115">If there is a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="08ae2-116">(Para obter mais informações sobre políticas, consulte [Configurar políticas de emergência](#configure-emergency-policies)).</span><span class="sxs-lookup"><span data-stu-id="08ae2-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="08ae2-117">Se houver uma combinação de LIS – um local de emergência do elemento de rede ao qual o cliente do teams está conectado será retornado ao cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="08ae2-117">If there is an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span>

3. <span data-ttu-id="08ae2-118">Quando o cliente do teams faz uma chamada de emergência, o local de emergência é transmitido para a rede PSTN.</span><span class="sxs-lookup"><span data-stu-id="08ae2-118">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="08ae2-119">Para roteamento direto, o administrador deve configurar o SBC para enviar chamadas de emergência para o provedor de ERS ou configurar o aplicativo SBC ELIN.</span><span class="sxs-lookup"><span data-stu-id="08ae2-119">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="08ae2-120">Este artigo contém as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="08ae2-120">This article contains the following sections.</span></span>

- [<span data-ttu-id="08ae2-121">Configurar endereços de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-121">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="08ae2-122">Definir configurações de rede</span><span class="sxs-lookup"><span data-stu-id="08ae2-122">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="08ae2-123">Configurar o serviço de informações de localização</span><span class="sxs-lookup"><span data-stu-id="08ae2-123">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="08ae2-124">Configurar políticas de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-124">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="08ae2-125">Habilitar usuários e sites</span><span class="sxs-lookup"><span data-stu-id="08ae2-125">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="08ae2-126">Testar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-126">Test emergency calling</span></span>](#test-emergency-calling)


<span data-ttu-id="08ae2-127">A capacidade de fazer o roteamento automático para o ponto de resposta de segurança pública apropriado (PSAP) varia de acordo com o país de uso do usuário do teams.</span><span class="sxs-lookup"><span data-stu-id="08ae2-127">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span> 

<span data-ttu-id="08ae2-128">Para obter mais informações sobre chamadas de emergência, incluindo informações sobre endereços de emergência e roteamento de chamadas de emergência, informações específicas para países e informações sobre configurações de rede e topologia de rede, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08ae2-128">For more information about emergency calling--including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology--see the following:</span></span>

- [<span data-ttu-id="08ae2-129">Gerenciar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-129">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="08ae2-130">Gerenciar configurações de rede para recursos de voz na nuvem</span><span class="sxs-lookup"><span data-stu-id="08ae2-130">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="08ae2-131">Gerenciar a topologia de rede para os recursos de voz na nuvem</span><span class="sxs-lookup"><span data-stu-id="08ae2-131">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)


## <a name="supported-clients"></a><span data-ttu-id="08ae2-132">Clientes com suporte</span><span class="sxs-lookup"><span data-stu-id="08ae2-132">Supported clients</span></span>

<span data-ttu-id="08ae2-133">Os clientes a seguir têm suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="08ae2-133">The following clients are currently supported.</span></span>  <span data-ttu-id="08ae2-134">Verifique com frequência para ver as atualizações desta lista.</span><span class="sxs-lookup"><span data-stu-id="08ae2-134">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="08ae2-135">Cliente de área de trabalho do teams para Windows</span><span class="sxs-lookup"><span data-stu-id="08ae2-135">Teams desktop client for Windows</span></span>
- <span data-ttu-id="08ae2-136">Cliente de área de trabalho do teams para Mac</span><span class="sxs-lookup"><span data-stu-id="08ae2-136">Teams desktop client for Mac</span></span>
- <span data-ttu-id="08ae2-137">Cliente do teams Mobile para IOS versão 1.0.92.2019121004 e versão 1.0.92 do App Store versão e posterior</span><span class="sxs-lookup"><span data-stu-id="08ae2-137">Teams mobile client for IOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="08ae2-138">Cliente do teams Mobile para cliente Android e para a loja versão 1416/1.0.0.2019121201 e posterior</span><span class="sxs-lookup"><span data-stu-id="08ae2-138">Teams mobile client for Android client and store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="08ae2-139">Teams Phone versão 1449/1.0.94.2019110802 e maior</span><span class="sxs-lookup"><span data-stu-id="08ae2-139">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="08ae2-140">Atribuir endereços de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-140">Assign emergency addresses</span></span>

<span data-ttu-id="08ae2-141">Você pode atribuir endereços de emergência a usuários do plano de chamada e aos identificadores de rede necessários para obter um local dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="08ae2-141">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="08ae2-142">(A sub-rede e o AP WiFi têm suporte; o suporte para switch/porta Ethernet está pendente).</span><span class="sxs-lookup"><span data-stu-id="08ae2-142">(Subnet and WiFi AP are supported; support for Ethernet switch/port is pending).</span></span>

<span data-ttu-id="08ae2-143">Para dar suporte ao roteamento automatizado de chamadas de emergência nos Estados Unidos, você deve garantir que os locais de emergência atribuídos a identificadores de rede incluam os códigos geográficos associados.</span><span class="sxs-lookup"><span data-stu-id="08ae2-143">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="08ae2-144">(Os endereços de emergência sem códigos geográficos não podem ser atribuídos aos identificadores de rede necessários para locais dinâmicos.)</span><span class="sxs-lookup"><span data-stu-id="08ae2-144">(Emergency addresses without geo codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="08ae2-145">O Azure Maps é usado para serviços baseados em localização.</span><span class="sxs-lookup"><span data-stu-id="08ae2-145">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="08ae2-146">Quando você insere um endereço de emergência usando o centro de administração do Microsoft Teams, o Teams verifica o Azure Maps para o endereço:</span><span class="sxs-lookup"><span data-stu-id="08ae2-146">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="08ae2-147">Se for encontrada uma correspondência, os códigos geográficos serão incluídos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="08ae2-147">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="08ae2-148">Se não for encontrada uma correspondência, você terá a oportunidade de criar manualmente um endereço de emergência.</span><span class="sxs-lookup"><span data-stu-id="08ae2-148">If a match is not found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="08ae2-149">Você pode usar o recurso soltar de PIN para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="08ae2-149">You can use the PIN drop feature to do this.</span></span>   

<span data-ttu-id="08ae2-150">Isso significa que, se um local de emergência existente criado para a atribuição a usuários do plano de chamada for destinado a um local dinâmico, o mesmo endereço precisa ser recriado para incluir os códigos geográficos.</span><span class="sxs-lookup"><span data-stu-id="08ae2-150">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="08ae2-151">Para distinguir entre os dois locais, você deve incluir uma descrição diferente.</span><span class="sxs-lookup"><span data-stu-id="08ae2-151">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="08ae2-152">O novo local de emergência pode ser atribuído aos usuários que têm o local antigo.</span><span class="sxs-lookup"><span data-stu-id="08ae2-152">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="08ae2-153">Quando migrado completamente, o local antigo pode ser excluído.</span><span class="sxs-lookup"><span data-stu-id="08ae2-153">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="08ae2-154">Para obter mais informações sobre como configurar endereços de emergência, consulte [Adicionar um local de emergência para sua organização](add-change-remove-emergency-location-organization.md) e [atribuir um local de emergência para o usuário](assign-change-emergency-location-user.md).</span><span class="sxs-lookup"><span data-stu-id="08ae2-154">For more information about configuring emergency addresses, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for your user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="08ae2-155">Definir configurações de rede</span><span class="sxs-lookup"><span data-stu-id="08ae2-155">Configure network settings</span></span>

<span data-ttu-id="08ae2-156">As configurações de rede são usadas para determinar a localização de um cliente do Teams e para obter dinamicamente as políticas de chamadas de emergência e um local de emergência.</span><span class="sxs-lookup"><span data-stu-id="08ae2-156">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="08ae2-157">Você pode definir as configurações de rede de acordo com a forma como a sua organização quer que a chamada de emergência funcione.</span><span class="sxs-lookup"><span data-stu-id="08ae2-157">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="08ae2-158">As configurações de rede incluem sites que incluem uma coleção de sub-redes--elas são usadas exclusivamente para atribuição de política dinâmica a usuários.</span><span class="sxs-lookup"><span data-stu-id="08ae2-158">Network settings include sites that include a collection of subnets--these are used exclusively for dynamic policy assignment to users.</span></span>  <span data-ttu-id="08ae2-159">Por exemplo, uma política TeamsEmergencyCalling e uma política TeamsEmergencyCallRouting podem ser atribuídas ao "site Redmond" para que todos os usuários que estiverem em roaming ou em outro local da Microsoft sejam configurados com números de emergência, roteamento e escrivaninha de segurança específico para Redmond.</span><span class="sxs-lookup"><span data-stu-id="08ae2-159">For example, a TeamsEmergencyCalling Policy and TeamsEmergencyCallRouting Policy might be assigned to the “Redmond site” so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="08ae2-160">As sub-redes também podem ser definidas no LIS e podem ser associadas a um local de emergência.</span><span class="sxs-lookup"><span data-stu-id="08ae2-160">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="08ae2-161">Tenha em mente as seguintes definições:</span><span class="sxs-lookup"><span data-stu-id="08ae2-161">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="08ae2-162">Os IPs confiáveis contêm uma coleção dos IPs externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="08ae2-162">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="08ae2-163">Uma tentativa de obter uma política dinâmica ou local será feita apenas se o IP externo do usuário corresponder a um IP no endereço IP confiável.</span><span class="sxs-lookup"><span data-stu-id="08ae2-163">An attempt to obtain a dynamic policy or location will only be made if the user’s external IP matches an IP in the Trusted IP address.</span></span> <span data-ttu-id="08ae2-164">Uma coincidência pode ser feita em endereços IP IPv4 ou IPv6 e depende do formato do pacote IP enviado para as configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="08ae2-164">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="08ae2-165">(Se um endereço IP público tiver IPv4 e IPv6, você precisará adicionar ambos como endereços IP confiáveis.)</span><span class="sxs-lookup"><span data-stu-id="08ae2-165">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="08ae2-166">Uma região de rede contém uma coleção de locais de rede.</span><span class="sxs-lookup"><span data-stu-id="08ae2-166">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="08ae2-167">Um site de rede representa um local onde a sua organização tem um valor físico, como um escritório, um conjunto de edifícios ou um campus.</span><span class="sxs-lookup"><span data-stu-id="08ae2-167">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="08ae2-168">Esses sites são definidos como uma coleção de sub-redes IP.</span><span class="sxs-lookup"><span data-stu-id="08ae2-168">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="08ae2-169">Uma sub-rede de rede deve estar associada a um site de rede específico.</span><span class="sxs-lookup"><span data-stu-id="08ae2-169">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="08ae2-170">A localização de um cliente é determinada com base na sub-rede da rede e no site de rede associado.</span><span class="sxs-lookup"><span data-stu-id="08ae2-170">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="08ae2-171">Para obter mais informações, consulte [configurações de rede para recursos de voz em nuvem](cloud-voice-network-settings.md) e [gerenciar a topologia de rede para recursos de voz na nuvem](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="08ae2-171">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md) and [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="08ae2-172">Observe que pode demorar algum tempo (até algumas horas) para algumas alterações nas configurações de rede (como um novo endereço, identificador de rede e assim por diante) para propagar e estar disponível para clientes do teams.</span><span class="sxs-lookup"><span data-stu-id="08ae2-172">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="08ae2-173">**Para usuários do plano de chamada:**</span><span class="sxs-lookup"><span data-stu-id="08ae2-173">**For Calling Plan users:**</span></span>

- <span data-ttu-id="08ae2-174">Se a configuração dinâmica da notificação de segurança for necessária, você deverá configurar endereços IP confiáveis e sites de rede.</span><span class="sxs-lookup"><span data-stu-id="08ae2-174">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="08ae2-175">Se forem necessários apenas locais dinâmicos, você deverá configurar apenas endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="08ae2-175">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="08ae2-176">Se nenhuma delas for necessária, a configuração das configurações de rede não será necessária.</span><span class="sxs-lookup"><span data-stu-id="08ae2-176">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="08ae2-177">**Para usuários de roteamento direto:**</span><span class="sxs-lookup"><span data-stu-id="08ae2-177">**For Direct Routing users:**</span></span>

- <span data-ttu-id="08ae2-178">Se a habilitação dinâmica de configuração de emergência ou a configuração dinâmica da notificação de segurança for necessária, você deverá configurar endereços IP confiáveis e sites de rede.</span><span class="sxs-lookup"><span data-stu-id="08ae2-178">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="08ae2-179">Se forem necessários apenas locais dinâmicos, você deverá configurar apenas endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="08ae2-179">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span>

- <span data-ttu-id="08ae2-180">Se nenhuma delas for necessária, a configuração das configurações de rede não será necessária.</span><span class="sxs-lookup"><span data-stu-id="08ae2-180">If neither are required, then configuration of network settings is not required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="08ae2-181">Configurar o serviço de informações de localização</span><span class="sxs-lookup"><span data-stu-id="08ae2-181">Configure Location Information Service</span></span>

<span data-ttu-id="08ae2-182">Um cliente do teams Obtém endereços de emergência dos locais associados a diferentes identificadores de rede.</span><span class="sxs-lookup"><span data-stu-id="08ae2-182">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="08ae2-183">As duas sub-redes e pontos de acesso sem fio (WAPs) são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="08ae2-183">Both subnets and Wireless Access Points (WAPs) are supported.</span></span> <span data-ttu-id="08ae2-184">(O suporte para switch/porta Ethernet está pendente.)</span><span class="sxs-lookup"><span data-stu-id="08ae2-184">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="08ae2-185">Para que um cliente obtenha um local, você deve preencher o LIS (serviço de informações de localização) com identificadores de rede e locais de emergência usando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="08ae2-185">For a client to obtain a location, you must populate the Location Information Service (LIS) with network identifiers and emergency locations by using the following cmdlets:</span></span>  


- <span data-ttu-id="08ae2-186">[Obter](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [definir](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="08ae2-186">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="08ae2-187">[Obter](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [definir](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="08ae2-187">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="08ae2-188">[Obter](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [definir](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="08ae2-188">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="08ae2-189">[Obter](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [definir](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [remover](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="08ae2-189">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps
) -CsOnlineLisWirelessAccessPoint</span></span> 


>[!Important] 
><span data-ttu-id="08ae2-190">Se as sub-redes estiverem sendo usadas como parte dos sites de rede, elas deverão ser redefinidas no serviço de informações de localização para renderizar locais dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="08ae2-190">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


## <a name="configure-emergency-policies"></a><span data-ttu-id="08ae2-191">Configurar políticas de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-191">Configure emergency policies</span></span>

<span data-ttu-id="08ae2-192">Use as políticas a seguir para configurar as chamadas de emergência:</span><span class="sxs-lookup"><span data-stu-id="08ae2-192">You use the following policies to configure emergency calling:</span></span>

- <span data-ttu-id="08ae2-193">**TeamsEmergencyCallRoutingPolicy** – aplica-se somente ao roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="08ae2-193">**TeamsEmergencyCallRoutingPolicy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="08ae2-194">Essa política configura os números de emergência, máscaras por número, se desejado, e a rota PSTN por número.</span><span class="sxs-lookup"><span data-stu-id="08ae2-194">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="08ae2-195">Você pode atribuir essa política a usuários, a sites de rede ou a ambos.</span><span class="sxs-lookup"><span data-stu-id="08ae2-195">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="08ae2-196">(Planos de chamada os clientes da equipe são habilitados automaticamente para fazer chamadas de emergência com os números de emergência do país com base no local de uso do Office 365.)  Você gerencia essa política usando os cmdlets New-, set-e Grant-CsTeamsEmergencyCallRouting.</span><span class="sxs-lookup"><span data-stu-id="08ae2-196">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Office 365 usage location.)  You manage this policy by using the New-, Set-, and Grant-CsTeamsEmergencyCallRouting cmdlets.</span></span> 

- <span data-ttu-id="08ae2-197">**TeamsEmergencyCallingPolicy** -aplica-se ao plano de chamada e ao encaminhamento direto.</span><span class="sxs-lookup"><span data-stu-id="08ae2-197">**TeamsEmergencyCallingPolicy** - Applies to Calling Plan and Direct Routing.</span></span> <span data-ttu-id="08ae2-198">Essa política configura a experiência de notificação de segurança técnica quando uma chamada de emergência é feita.</span><span class="sxs-lookup"><span data-stu-id="08ae2-198">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="08ae2-199">Você pode definir quem deseja notificar e como eles são notificados.</span><span class="sxs-lookup"><span data-stu-id="08ae2-199">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="08ae2-200">Por exemplo, para notificar automaticamente a equipe de segurança da sua organização e fazer com que elas escutem em chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="08ae2-200">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="08ae2-201">Essa política pode ser atribuída a usuários ou sites de rede ou ambos.</span><span class="sxs-lookup"><span data-stu-id="08ae2-201">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="08ae2-202">Você gerencia essa política usando os cmdlets New-, set-e Grant-CsTeamsEmergencyCallingPolicy.</span><span class="sxs-lookup"><span data-stu-id="08ae2-202">You manage this policy by using the New-, Set- and Grant-CsTeamsEmergencyCallingPolicy  cmdlets.</span></span> 

<span data-ttu-id="08ae2-203">Para obter mais informações, consulte [gerenciar políticas de chamadas de emergência no Teams](manage-emergency-calling-policies.md) e [gerenciar políticas de roteamento de chamadas de emergência para roteamento direto](manage-emergency-call-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="08ae2-203">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md) and [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>


## <a name="enable-users-and-sites"></a><span data-ttu-id="08ae2-204">Habilitar usuários e sites</span><span class="sxs-lookup"><span data-stu-id="08ae2-204">Enable users and sites</span></span>

<span data-ttu-id="08ae2-205">Você pode atribuir políticas **TeamsEmergencyCalling** e **TeamsEmergencyCallROuting** para usuários e para sites.</span><span class="sxs-lookup"><span data-stu-id="08ae2-205">You can assign **TeamsEmergencyCalling** and **TeamsEmergencyCallROuting** policies to users and to sites.</span></span>  

<span data-ttu-id="08ae2-206">A política TeamsEmergencyCallRouting se aplica apenas ao roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="08ae2-206">The TeamsEmergencyCallRouting policy applies to Direct Routing only.</span></span> <span data-ttu-id="08ae2-207">(Embora seja possível atribuir essa política a um usuário de plano de chamada, a política não terá efeito.)</span><span class="sxs-lookup"><span data-stu-id="08ae2-207">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="08ae2-208">Por exemplo, para habilitar um usuário específico para a notificação do Security Desk, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="08ae2-208">For example, to enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="08ae2-209">Para atribuir uma política chamada "política de chamadas de emergência da Contoso 1" ao site 1, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="08ae2-209">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="08ae2-210">Para habilitar um usuário de roteamento direto específico para fazer chamadas de emergência, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="08ae2-210">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="08ae2-211">Para atribuir uma política chamada "roteamento de chamada de emergência do contoso New York" ao site 1, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="08ae2-211">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="08ae2-212">Se você atribuiu uma política de chamadas de emergência a um site de rede e a um usuário, e se esse usuário estiver nesse site de rede, a política que é atribuída ao site da rede substituirá a política atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="08ae2-212">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


## <a name="test-emergency-calling"></a><span data-ttu-id="08ae2-213">Testar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-213">Test emergency calling</span></span>

<span data-ttu-id="08ae2-214">Alguns provedores de serviços de roteamento de emergência (ERSPs) nos Estados Unidos oferecem um bot de teste de chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="08ae2-214">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="08ae2-215">**Plano de chamada os usuários nos Estados Unidos** podem usar o número de emergência de teste predefinido 933 para validar a configuração de chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="08ae2-215">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="08ae2-216">Esse número é roteado para um bot, que então ecoa novamente o número de telefone do chamador (ID da linha de chamada), o endereço de emergência ou o local e se a chamada seria automaticamente roteada para o PSAP ou em uma tela em primeiro lugar.</span><span class="sxs-lookup"><span data-stu-id="08ae2-216">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="08ae2-217">**Os clientes de roteamento direto nos Estados Unidos** devem coordenar com o ERSP para um serviço de teste.</span><span class="sxs-lookup"><span data-stu-id="08ae2-217">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="08ae2-218">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="08ae2-218">Related topics</span></span>

- [<span data-ttu-id="08ae2-219">Gerenciar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-219">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="08ae2-220">Gerenciar políticas de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-220">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="08ae2-221">Gerenciar políticas de roteamento de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="08ae2-221">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="08ae2-222">Adicionar, alterar ou remover um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="08ae2-222">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="08ae2-223">Atribuir ou alterar um local de emergência para o usuário</span><span class="sxs-lookup"><span data-stu-id="08ae2-223">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="08ae2-224">Configurações de rede para recursos de voz na nuvem</span><span class="sxs-lookup"><span data-stu-id="08ae2-224">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="08ae2-225">Gerenciar a topologia de rede para os recursos de voz na nuvem</span><span class="sxs-lookup"><span data-stu-id="08ae2-225">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
