---
title: Teams de caso contoso de voz
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
description: Teams de caso de voz para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785945"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="c605e-103">Estudo de caso contoso: Chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="c605e-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="c605e-104">Para entender a disponibilidade de chamada de emergência e terminologia relacionadas à chamada de emergência Endereço de Emergência, Local, Local de Emergência e Endereço Registrado A Contoso analisou Gerenciar chamada de emergência e Planejar e configurar a chamada de emergência &mdash; &mdash; [dinâmica.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="c605e-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="c605e-105">No Office 365, um usuário do Plano de Chamada é habilitado automaticamente para chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="c605e-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="c605e-106">Mas somente os usuários do Plano de Chamadas nos Estados Unidos podem usar locais dinâmicos para rotear chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="c605e-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="c605e-107">Para Roteamento Direto, a Contoso aprendeu que a configuração adicional é necessária para roteamento de chamadas de emergência e, possivelmente, para conectividade de parceiros.</span><span class="sxs-lookup"><span data-stu-id="c605e-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="c605e-108">O administrador deve configurar a conexão com um Provedor de Serviços de Roteamento de Emergência (ERSP) (Estados Unidos) OU configurar o Controlador de Borda de Sessão (SBC) para um aplicativo ELIN (Número de Identificação de Local de Emergência).</span><span class="sxs-lookup"><span data-stu-id="c605e-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="c605e-109">A Contoso tem escritórios nos Estados Unidos e fora dos Estados Unidos:</span><span class="sxs-lookup"><span data-stu-id="c605e-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="c605e-110">Nos Estados Unidos, os usuários do Plano de Chamadas contoso podem usar locais dinâmicos para rotear chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="c605e-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="c605e-111">Fora dos Estados Unidos, a Contoso tem alguns sites que usam Planos de Chamadas e alguns sites conectados Sistema de Telefonia roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="c605e-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="c605e-112">Casos de uso de chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="c605e-112">Emergency calling use cases</span></span>

<span data-ttu-id="c605e-113">Depois de decidir como a Contoso se conectará Telefone sistema, a Contoso identificou os seguintes casos de uso de chamada de emergência:</span><span class="sxs-lookup"><span data-stu-id="c605e-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="c605e-114">Usuário do Plano de Chamada nos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="c605e-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="c605e-115">Chamando o usuário do Plano fora dos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="c605e-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="c605e-116">Usuário que se conecta Sistema de Telefonia roteamento direto</span><span class="sxs-lookup"><span data-stu-id="c605e-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="c605e-117">Usuário do Plano de Chamada nos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="c605e-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="c605e-118">Há requisitos para quando o número de telefone precisa ser associado a um local de emergência.</span><span class="sxs-lookup"><span data-stu-id="c605e-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="c605e-119">Para entender esses requisitos, a Contoso [reviu Considerações sobre planos de chamada.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="c605e-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="c605e-120">Com base nesses requisitos, a Contoso decidiu associar o local ao número de telefone quando um número é atribuído a um usuário nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c605e-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="c605e-121">Chamando o usuário do Plano fora dos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="c605e-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="c605e-122">Para entender quando um número de telefone precisa ser associado a um local de emergência, a Contoso [reviu Considerações para Planos de Chamadas.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="c605e-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="c605e-123">Com base nos requisitos, a Contoso decidiu o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c605e-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="c605e-124">A Contoso associará o local ao número de telefone quando um número for atribuído a um usuário no Canadá.</span><span class="sxs-lookup"><span data-stu-id="c605e-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="c605e-125">A Contoso atribuirá um local de emergência quando o número de telefone for adquirido do Office 365 ou quando um número for transferido de outro provedor de serviços ou operadora.</span><span class="sxs-lookup"><span data-stu-id="c605e-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="c605e-126">Usuário que se conecta Sistema de Telefonia roteamento direto</span><span class="sxs-lookup"><span data-stu-id="c605e-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="c605e-127">Para planejar o roteamento de emergência para esse caso de uso, a Contoso [reviu Considerações para Roteamento Direto.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="c605e-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="c605e-128">Como os usuários do Roteamento Direto não recebem chamadas de emergência da mesma maneira que os usuários do Plano de Chamadas, a Contoso teve que decidir como fornecer chamadas de emergência.</span><span class="sxs-lookup"><span data-stu-id="c605e-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="c605e-129">O Roteamento Direto pode ser conectado a um Provedor de Serviços de Roteamento de Emergência (ERSP).</span><span class="sxs-lookup"><span data-stu-id="c605e-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="c605e-130">O Roteamento Direto também pode ter um SBC que inclui um ELIN (Número de Identificação de Local de Emergência).</span><span class="sxs-lookup"><span data-stu-id="c605e-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="c605e-131">Considerações do Provedor de Serviços de Roteamento de Emergência (ERSP)</span><span class="sxs-lookup"><span data-stu-id="c605e-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="c605e-132">Os Provedores de Serviços de Roteamento de Emergência (ERSPs) podem rotear automaticamente chamadas de emergência com base no local do chamador.</span><span class="sxs-lookup"><span data-stu-id="c605e-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="c605e-133">Se um Provedor de Serviços de Roteamento de Emergência estiver integrado a uma implantação de Roteamento Direto, as chamadas de emergência com um local adquirido dinamicamente serão roteados automaticamente para o PSAP (Ponto de Atendimento de Segurança Pública) que atende a esse local.</span><span class="sxs-lookup"><span data-stu-id="c605e-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="c605e-134">Chamadas de emergência sem um local adquirido dinamicamente são primeiramente triadas para determinar o local atual do usuário antes de conectar a chamada ao centro de expedição apropriado com base no local atualizado.</span><span class="sxs-lookup"><span data-stu-id="c605e-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="c605e-135">Considerações sobre ELIN</span><span class="sxs-lookup"><span data-stu-id="c605e-135">ELIN considerations</span></span>

<span data-ttu-id="c605e-136">Se um aplicativo ELIN SBC estiver integrado a uma implantação de Roteamento Direto, etapas adicionais de configuração precisam ocorrer para associar os endereços de emergência aos números de telefone.</span><span class="sxs-lookup"><span data-stu-id="c605e-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="c605e-137">A Contoso decidiu usar controladores de borda de sessão que incluem aplicativos ELIN (Número de Identificação de Local de Emergência).</span><span class="sxs-lookup"><span data-stu-id="c605e-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="c605e-138">Notificação de segurança</span><span class="sxs-lookup"><span data-stu-id="c605e-138">Security desk notification</span></span>

<span data-ttu-id="c605e-139">A capacidade de notificar o suporte de segurança quando uma chamada de emergência é feita está disponível para planos de chamadas da Microsoft e Sistema de Telefonia Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="c605e-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="c605e-140">A Contoso analisou os detalhes na notificação de segurança para determinar se isso deve ser configurado em seus escritórios</span><span class="sxs-lookup"><span data-stu-id="c605e-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="c605e-141">A Contoso decidiu usar a notificação de segurança.</span><span class="sxs-lookup"><span data-stu-id="c605e-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="c605e-142">Configuração</span><span class="sxs-lookup"><span data-stu-id="c605e-142">Configuration</span></span> 

<span data-ttu-id="c605e-143">A Contoso seguiu as etapas em [Configurar chamada de emergência dinâmica](configure-dynamic-emergency-calling.md) para:</span><span class="sxs-lookup"><span data-stu-id="c605e-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="c605e-144">Atribuir endereços de emergência</span><span class="sxs-lookup"><span data-stu-id="c605e-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="c605e-145">Configurar configurações de rede</span><span class="sxs-lookup"><span data-stu-id="c605e-145">Configure network settings</span></span> 

- <span data-ttu-id="c605e-146">Configurar o Serviço de Informações de Local</span><span class="sxs-lookup"><span data-stu-id="c605e-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="c605e-147">Configurar políticas de emergência</span><span class="sxs-lookup"><span data-stu-id="c605e-147">Configure emergency policies</span></span> 

- <span data-ttu-id="c605e-148">Habilitar usuários e sites</span><span class="sxs-lookup"><span data-stu-id="c605e-148">Enable users and sites</span></span> 

- <span data-ttu-id="c605e-149">Testar chamada de emergência</span><span class="sxs-lookup"><span data-stu-id="c605e-149">Test emergency calling</span></span> 

<span data-ttu-id="c605e-150">Após a configuração da chamada de emergência dinâmica, a Contoso precisou atribuir o local ao usuário apropriado.</span><span class="sxs-lookup"><span data-stu-id="c605e-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="c605e-151">Para adicionar, alterar ou remover um local de emergência para sua organização, a Contoso seguiu as etapas em [Adicionar,](add-change-remove-emergency-location-organization.md) alterar ou remover um local de emergência para sua organização</span><span class="sxs-lookup"><span data-stu-id="c605e-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="c605e-152">Para criar locais para edifícios, pisos e escritórios, a Contoso seguiu as etapas em Adicionar, alterar ou remover um local para um local [de emergência.](add-change-remove-emergency-place-organization.md)</span><span class="sxs-lookup"><span data-stu-id="c605e-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="c605e-153">Para atribuir um local de emergência, a Contoso seguiu as etapas em [Atribuir ou alterar um local](assign-change-emergency-location-user.md)de emergência para um usuário .</span><span class="sxs-lookup"><span data-stu-id="c605e-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 