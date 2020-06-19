---
title: Estudo de caso da Contoso Voice Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785945"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="4a14d-103">Estudo de caso da Contoso: chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="4a14d-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="4a14d-104">Para entender a disponibilidade de chamadas de emergência e terminologia relacionada ao endereço de emergência de chamada de emergência &mdash; , lugar, local de emergência e endereço cadastrado, a &mdash; contoso revisou [gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md) e [planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="4a14d-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="4a14d-105">No Office 365, um usuário do plano de chamada é habilitado automaticamente para chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="4a14d-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="4a14d-106">Mas somente os usuários de plano de chamada nos Estados Unidos podem usar locais dinâmicos para direcionar as chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="4a14d-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="4a14d-107">Para direcionamento direto, a contoso aprendeu que uma configuração adicional é necessária para roteamento de chamadas de emergência e possivelmente para conectividade de parceiros.</span><span class="sxs-lookup"><span data-stu-id="4a14d-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="4a14d-108">O administrador deve configurar a conexão para um provedor de serviços de roteamento de emergência (ERSP) (Estados Unidos) ou configurar o controlador de borda de sessão (SBC) para um aplicativo de número de identificação de localização de emergência (ELIN).</span><span class="sxs-lookup"><span data-stu-id="4a14d-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="4a14d-109">A contoso tem escritórios nos Estados Unidos e fora dos Estados Unidos:</span><span class="sxs-lookup"><span data-stu-id="4a14d-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="4a14d-110">Nos Estados Unidos, os usuários do plano de chamadas da Contoso podem usar locais dinâmicos para direcionar as chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="4a14d-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="4a14d-111">Fora dos Estados Unidos, a contoso tem alguns sites que usam planos de chamadas e alguns sites conectados ao sistema telefônico por meio de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="4a14d-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="4a14d-112">Casos de uso de chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="4a14d-112">Emergency calling use cases</span></span>

<span data-ttu-id="4a14d-113">Depois de decidir como a contoso se conectará ao sistema telefônico, a contoso identificou os seguintes casos de uso de chamadas de emergência:</span><span class="sxs-lookup"><span data-stu-id="4a14d-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="4a14d-114">Usuário do plano de chamada nos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="4a14d-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="4a14d-115">Plano de chamada usuário fora dos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="4a14d-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="4a14d-116">Usuário que se conecta ao sistema telefônico por meio do roteamento direto</span><span class="sxs-lookup"><span data-stu-id="4a14d-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="4a14d-117">Usuário do plano de chamada nos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="4a14d-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="4a14d-118">Há requisitos para quando o número de telefone precisa estar associado a um local de emergência.</span><span class="sxs-lookup"><span data-stu-id="4a14d-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="4a14d-119">Para compreender esses requisitos, a contoso revisou as [considerações para planos de chamada](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="4a14d-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="4a14d-120">Com base nesses requisitos, a Contoso decidiu associar o local ao número de telefone quando um número é atribuído a um usuário nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="4a14d-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="4a14d-121">Plano de chamada usuário fora dos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="4a14d-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="4a14d-122">Para entender quando um número de telefone precisa estar associado a um local de emergência, a contoso revisou as [considerações para planos de chamada](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="4a14d-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="4a14d-123">Com base nos requisitos, a Contoso decidiu o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4a14d-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="4a14d-124">A contoso associará o local ao número de telefone quando um número for atribuído a um usuário no Canadá.</span><span class="sxs-lookup"><span data-stu-id="4a14d-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="4a14d-125">A contoso atribuirá um local de emergência quando o número de telefone for adquirido do Office 365 ou quando um número for transferido de outro provedor de serviços ou operadora.</span><span class="sxs-lookup"><span data-stu-id="4a14d-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="4a14d-126">Usuário que se conecta ao sistema telefônico por meio do roteamento direto</span><span class="sxs-lookup"><span data-stu-id="4a14d-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="4a14d-127">Para planejar o roteamento de emergência para esse caso de uso, a contoso revisou as [considerações para roteamento direto](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="4a14d-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="4a14d-128">Como os usuários de roteamento direto não recebem chamadas de emergência da mesma maneira que os usuários do plano de chamadas, a Contoso tinha que decidir como fazer chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="4a14d-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="4a14d-129">O roteamento direto pode ser conectado a um provedor de serviços de roteamento de emergência (ERSP).</span><span class="sxs-lookup"><span data-stu-id="4a14d-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="4a14d-130">O roteamento direto também pode ter um SBC que inclui um número de identificação de localização de emergência (ELIN).</span><span class="sxs-lookup"><span data-stu-id="4a14d-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="4a14d-131">Considerações sobre o provedor de serviços de roteamento de emergência (ERSP)</span><span class="sxs-lookup"><span data-stu-id="4a14d-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="4a14d-132">Os provedores de serviços de roteamento de emergência (ERSPs) podem rotear automaticamente as chamadas de emergência com base na localização do chamador.</span><span class="sxs-lookup"><span data-stu-id="4a14d-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="4a14d-133">Se um provedor de serviços de roteamento de emergência estiver integrado a uma implantação de roteamento direto, as chamadas de emergência com um local adquirido dinamicamente serão automaticamente roteadas para o ponto de resposta de segurança pública (PSAP) que está servindo essa localização.</span><span class="sxs-lookup"><span data-stu-id="4a14d-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="4a14d-134">As chamadas de emergência sem um local adquirido dinamicamente são organizadas em primeiro lugar para determinar a localização atual do usuário antes de conectar a chamada ao centro de expedição apropriado com base no local atualizado.</span><span class="sxs-lookup"><span data-stu-id="4a14d-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="4a14d-135">Considerações sobre o ELIN</span><span class="sxs-lookup"><span data-stu-id="4a14d-135">ELIN considerations</span></span>

<span data-ttu-id="4a14d-136">Se um aplicativo ELIN do SBC estiver integrado a uma implantação de roteamento direto, etapas de configuração adicionais precisarão ocorrer para associar os endereços de emergência a números de telefone.</span><span class="sxs-lookup"><span data-stu-id="4a14d-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="4a14d-137">A Contoso decidiu usar os controladores de borda de sessão que incluem aplicativos de número de identificação de local de emergência (ELIN).</span><span class="sxs-lookup"><span data-stu-id="4a14d-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="4a14d-138">Notificação de segurança técnica</span><span class="sxs-lookup"><span data-stu-id="4a14d-138">Security desk notification</span></span>

<span data-ttu-id="4a14d-139">A capacidade de notificar a mesa de segurança quando uma chamada de emergência é feita está disponível para planos de chamadas da Microsoft e roteamento direto do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="4a14d-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="4a14d-140">A contoso revisou os detalhes na notificação de segurança para determinar se isso deve ser configurado em seus escritórios</span><span class="sxs-lookup"><span data-stu-id="4a14d-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="4a14d-141">A Contoso decidiu usar a notificação de segurança técnica.</span><span class="sxs-lookup"><span data-stu-id="4a14d-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="4a14d-142">Configuração</span><span class="sxs-lookup"><span data-stu-id="4a14d-142">Configuration</span></span> 

<span data-ttu-id="4a14d-143">A contoso seguiu as etapas em [Configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md) para:</span><span class="sxs-lookup"><span data-stu-id="4a14d-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="4a14d-144">Atribuir endereços de emergência</span><span class="sxs-lookup"><span data-stu-id="4a14d-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="4a14d-145">Definir configurações de rede</span><span class="sxs-lookup"><span data-stu-id="4a14d-145">Configure network settings</span></span> 

- <span data-ttu-id="4a14d-146">Configurar o serviço de informações de localização</span><span class="sxs-lookup"><span data-stu-id="4a14d-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="4a14d-147">Configurar políticas de emergência</span><span class="sxs-lookup"><span data-stu-id="4a14d-147">Configure emergency policies</span></span> 

- <span data-ttu-id="4a14d-148">Habilitar usuários e sites</span><span class="sxs-lookup"><span data-stu-id="4a14d-148">Enable users and sites</span></span> 

- <span data-ttu-id="4a14d-149">Testar chamadas de emergência</span><span class="sxs-lookup"><span data-stu-id="4a14d-149">Test emergency calling</span></span> 

<span data-ttu-id="4a14d-150">Após a configuração da chamada de emergência dinâmica, a contoso precisava atribuir o local ao usuário adequado.</span><span class="sxs-lookup"><span data-stu-id="4a14d-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="4a14d-151">Para adicionar, alterar ou remover um local de emergência de sua organização, a contoso seguiu as etapas em [Adicionar, alterar ou remover um local de emergência para sua organização](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="4a14d-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="4a14d-152">Para criar locais para edifícios, andares e escritórios, a contoso seguiu as etapas em [Adicionar, alterar ou remover um local para um local de emergência](add-change-remove-emergency-place-organization.md) .</span><span class="sxs-lookup"><span data-stu-id="4a14d-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="4a14d-153">Para atribuir um local de emergência, a contoso seguiu as etapas em [atribuir ou alterar um local de emergência para um usuário](assign-change-emergency-location-user.md).</span><span class="sxs-lookup"><span data-stu-id="4a14d-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 