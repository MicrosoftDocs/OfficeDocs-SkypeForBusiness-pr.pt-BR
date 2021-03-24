---
title: Estudo de caso de voz do Teams Contoso
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
description: Estudo de caso de voz do Teams para corporação multi-nacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101027"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="f15a6-103">Estudo de caso contoso: Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="f15a6-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="f15a6-104">Dependendo da localização geográfica e de outros fatores, a Contoso tinha escritórios usando as seguintes soluções de telefonia:</span><span class="sxs-lookup"><span data-stu-id="f15a6-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="f15a6-105">Tipo de site A: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="f15a6-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="f15a6-106">Tipo de site B: Sistemas de telefonia herdados tradicionais</span><span class="sxs-lookup"><span data-stu-id="f15a6-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="f15a6-107">Tipo de site C: uma combinação de sistemas de telefonia Enterprise Voice skype for Business e tradicionais herdados</span><span class="sxs-lookup"><span data-stu-id="f15a6-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="f15a6-108">Para implementar uma solução do Microsoft Phone System para toda a organização, a Contoso precisava determinar para cada tipo de site qual das seguintes opções seria usada com o Sistema de Telefonia para se conectar à &mdash; PSTN (Rede Telefônica Pública Comucionária): &mdash;</span><span class="sxs-lookup"><span data-stu-id="f15a6-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="f15a6-109">Sistema de Telefonia com Plano de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f15a6-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="f15a6-110">Sistema de Telefonia com própria operadora PSTN por meio de Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="f15a6-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="f15a6-111">Combinação do Sistema de Telefonia com o Plano de Chamadas e o Sistema de Telefonia com a própria operadora PSTN por meio do Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="f15a6-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="f15a6-112">Para determinar a solução certa para sua organização, a Contoso usou soluções de telefonia [da Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) e a Sessão de Chamada do Ignite 2019 no [Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="f15a6-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="f15a6-113">Tipo de site A: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="f15a6-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="f15a6-114">A contoso Skype for Business Enterprise Voice foi configurada como hub e falada.</span><span class="sxs-lookup"><span data-stu-id="f15a6-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="f15a6-115">Havia um local central que mantinha o gateway PSTN na região que forneceu a conexão com o PSTN para os usuários do Skype for Business Enterprise Voice no país.</span><span class="sxs-lookup"><span data-stu-id="f15a6-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="f15a6-116">Muitas vezes, esses escritórios via satélite não têm sua própria saída da Internet.</span><span class="sxs-lookup"><span data-stu-id="f15a6-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="f15a6-117">Os números desses usuários residiam no tronco SIP que se conecta a um SBC existente.</span><span class="sxs-lookup"><span data-stu-id="f15a6-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="f15a6-118">Para determinar se o SBC já implantado está certificado para Roteamento Direto e Desvio de Mídia, a Contoso verificou a Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="f15a6-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="f15a6-119">Os hábitos de discagem do usuário eram discar um usuário no sistema de telefonia herdado usando uma extensão, mesmo quando o usuário tem um cliente skype for Business disponível para áudio ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="f15a6-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="f15a6-120">A Contoso baseou sua decisão nas seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="f15a6-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="f15a6-121">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-121">Q.</span></span> <span data-ttu-id="f15a6-122">Precisamos manter a funcionalidade fornecida pela implantação local?</span><span class="sxs-lookup"><span data-stu-id="f15a6-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="f15a6-123">A.</span><span class="sxs-lookup"><span data-stu-id="f15a6-123">A.</span></span> <span data-ttu-id="f15a6-124">Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-124">No</span></span> 

- <span data-ttu-id="f15a6-125">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-125">Q.</span></span> <span data-ttu-id="f15a6-126">Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?</span><span class="sxs-lookup"><span data-stu-id="f15a6-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="f15a6-127">A.</span><span class="sxs-lookup"><span data-stu-id="f15a6-127">A.</span></span> <span data-ttu-id="f15a6-128">Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-128">No</span></span> 

- <span data-ttu-id="f15a6-129">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-129">Q.</span></span> <span data-ttu-id="f15a6-130">Precisamos manter nossa operadora de terceiros atual?</span><span class="sxs-lookup"><span data-stu-id="f15a6-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="f15a6-131">A. Sim (países regulamentados) e Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="f15a6-132">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-132">Q.</span></span> <span data-ttu-id="f15a6-133">Precisamos implantar o ROI em SBCs?</span><span class="sxs-lookup"><span data-stu-id="f15a6-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="f15a6-134">A. Sim e Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-134">A. Yes and No</span></span>  

- <span data-ttu-id="f15a6-135">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-135">Q.</span></span> <span data-ttu-id="f15a6-136">Os Planos de Chamada PSTN da Microsoft estão disponíveis nesta região?</span><span class="sxs-lookup"><span data-stu-id="f15a6-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="f15a6-137">A. Sim e Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-137">A. Yes and No</span></span> 

<span data-ttu-id="f15a6-138">Com base nas respostas às suas perguntas, a Contoso decidiu:</span><span class="sxs-lookup"><span data-stu-id="f15a6-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="f15a6-139">Mova os usuários que estão localizados em uma região onde os planos de chamadas PSTN estão disponíveis para o Sistema de Telefonia com Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="f15a6-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="f15a6-140">Mova os usuários que não estão localizados em uma região onde os planos de chamadas PSTN estão disponíveis, os usuários localizados em um site onde o ROI nos SBCs ainda não foram atendidos e os usuários que residiram em um país que tenha regulamentações de telefonia para o Sistema de Telefonia com Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="f15a6-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="f15a6-141">O diagrama a seguir mostra a implantação inicial do Skype for Business Enterprise Voice e como essa implantação foi migrada para planos de chamadas da Microsoft e roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="f15a6-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagrama mostrando estados antes e depois](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="f15a6-143">Tipo de site B: Sistemas de telefonia herdados tradicionais</span><span class="sxs-lookup"><span data-stu-id="f15a6-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="f15a6-144">A Contoso tinha muitos escritórios que utilizava sistemas de telefonia herdados.</span><span class="sxs-lookup"><span data-stu-id="f15a6-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="f15a6-145">Havia um subconjunto de usuários que tinham um número de telefone E1.64 enquanto outros tinham apenas uma extensão.</span><span class="sxs-lookup"><span data-stu-id="f15a6-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="f15a6-146">Esses números residiam no tronco TDM para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f15a6-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="f15a6-147">A discagem intra-site foi configurada aproveitando um código de site em frente à extensão para determinar para onde encaminhar a chamada.</span><span class="sxs-lookup"><span data-stu-id="f15a6-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="f15a6-148">Os hábitos de discagem dos usuários eram discar por extensão.</span><span class="sxs-lookup"><span data-stu-id="f15a6-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="f15a6-149">A Contoso baseou sua decisão nas seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="f15a6-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="f15a6-150">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-150">Q.</span></span> <span data-ttu-id="f15a6-151">Precisamos manter a funcionalidade fornecida pela implantação local?</span><span class="sxs-lookup"><span data-stu-id="f15a6-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="f15a6-152">A.</span><span class="sxs-lookup"><span data-stu-id="f15a6-152">A.</span></span> <span data-ttu-id="f15a6-153">Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-153">No</span></span> 

- <span data-ttu-id="f15a6-154">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-154">Q.</span></span> <span data-ttu-id="f15a6-155">Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?</span><span class="sxs-lookup"><span data-stu-id="f15a6-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="f15a6-156">A. Sim</span><span class="sxs-lookup"><span data-stu-id="f15a6-156">A. Yes</span></span>

- <span data-ttu-id="f15a6-157">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-157">Q.</span></span> <span data-ttu-id="f15a6-158">Precisamos manter nossa operadora de terceiros atual?</span><span class="sxs-lookup"><span data-stu-id="f15a6-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="f15a6-159">A. Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-159">A. No</span></span> 

- <span data-ttu-id="f15a6-160">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-160">Q.</span></span> <span data-ttu-id="f15a6-161">O Plano de Chamada da Microsoft PSTN está disponível em nossa região?</span><span class="sxs-lookup"><span data-stu-id="f15a6-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="f15a6-162">A. Sim e Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-162">A. Yes and No</span></span> 

<span data-ttu-id="f15a6-163">Com base nas respostas às suas perguntas, a Contoso decidiu:</span><span class="sxs-lookup"><span data-stu-id="f15a6-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="f15a6-164">Mova os usuários que estão localizados em uma região onde os planos de chamadas PSTN estão disponíveis para o Sistema de Telefonia com Planos de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="f15a6-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="f15a6-165">Mova os usuários que não estão localizados em uma região onde os planos de chamadas PSTN estão disponíveis para o Sistema de Telefonia com Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="f15a6-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="f15a6-166">Mantenha uma conexão PSTN com dispositivos analógicos críticos de negócios.</span><span class="sxs-lookup"><span data-stu-id="f15a6-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="f15a6-167">Os diagramas a seguir mostram a implantação do sistema herdados original com sites remotos e a migração para uma implantação de Roteamento Direto com Otimização de Mídia Local:</span><span class="sxs-lookup"><span data-stu-id="f15a6-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="f15a6-168">**Implantação herdda original**  
 ![ Diagrama mostrando estados antes e depois](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="f15a6-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="f15a6-169">**Implantação com Roteamento Direto**</span><span class="sxs-lookup"><span data-stu-id="f15a6-169">**Deployment with Direct Routing**</span></span>

![Diagrama mostrando estados antes e depois](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="f15a6-171">Tipo de site C: combinação do Skype for Business Enterprise Voice e sistemas de telefonia herdados tradicionais</span><span class="sxs-lookup"><span data-stu-id="f15a6-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="f15a6-172">A Contoso Skype for Business Enterprise Voice os números dos usuários residem no tronco SIP para o SBC da operadora.</span><span class="sxs-lookup"><span data-stu-id="f15a6-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="f15a6-173">Os números dos sistemas de telefonia tradicionais residiam no tronco TDM para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f15a6-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="f15a6-174">A Contoso baseou sua decisão nas seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="f15a6-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="f15a6-175">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-175">Q.</span></span> <span data-ttu-id="f15a6-176">Precisamos manter a funcionalidade fornecida pela implantação local?</span><span class="sxs-lookup"><span data-stu-id="f15a6-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="f15a6-177">A.</span><span class="sxs-lookup"><span data-stu-id="f15a6-177">A.</span></span> <span data-ttu-id="f15a6-178">Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-178">No</span></span> 

- <span data-ttu-id="f15a6-179">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-179">Q.</span></span> <span data-ttu-id="f15a6-180">Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?</span><span class="sxs-lookup"><span data-stu-id="f15a6-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="f15a6-181">A. Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-181">A. No</span></span> 

- <span data-ttu-id="f15a6-182">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-182">Q.</span></span> <span data-ttu-id="f15a6-183">Precisamos manter nossa operadora de terceiros atual?</span><span class="sxs-lookup"><span data-stu-id="f15a6-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="f15a6-184">A. Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-184">A. No</span></span> 

- <span data-ttu-id="f15a6-185">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-185">Q.</span></span> <span data-ttu-id="f15a6-186">Precisamos implantar o ROI em SBCs?</span><span class="sxs-lookup"><span data-stu-id="f15a6-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="f15a6-187">A. Sim e Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-187">A. Yes and No</span></span>  

- <span data-ttu-id="f15a6-188">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-188">Q.</span></span> <span data-ttu-id="f15a6-189">O Plano de Chamada PSTN da Microsoft está disponível nesta região?</span><span class="sxs-lookup"><span data-stu-id="f15a6-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="f15a6-190">A. Não</span><span class="sxs-lookup"><span data-stu-id="f15a6-190">A. No</span></span> 

<span data-ttu-id="f15a6-191">Com base nas respostas às suas perguntas, a Contoso decidiu o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f15a6-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="f15a6-192">Para os usuários de telefonia herdados que serão habilitados para Roteamento Direto, a Contoso portava os números do tronco TDM para o Tronco SIP do SBC, já que o SBC é certificado para Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="f15a6-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="f15a6-193">Para dar suporte a um subconjunto de usuários que se movem para o Sistema de Telefonia e para permitir o roteamento contínuo pelo sistema herdado, o sistema de telefonia herdado foi definido como o próximo salto para o SBC.</span><span class="sxs-lookup"><span data-stu-id="f15a6-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="f15a6-194">Além disso, para incentivar a alteração de comportamento do usuário e remover a dependência da discagem de extensão entre e dentro do site, a Contoso forneceu orientações para usar o Teams para todas as chamadas internas.</span><span class="sxs-lookup"><span data-stu-id="f15a6-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="f15a6-195">Os diagramas a seguir mostram a implantação original do sistema de telefonia Enterprise Voice Skype for Business e a migração para uma implantação mista usando Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="f15a6-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="f15a6-196">**Implantação mista original** 
 ![ Diagrama mostrando antes do estado](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="f15a6-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="f15a6-197">**Implantação mista com Roteamento Direto** 
 ![ Diagrama mostrando antes do estado](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="f15a6-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="f15a6-198">Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f15a6-198">Calling Plans</span></span>

<span data-ttu-id="f15a6-199">Para determinar os requisitos de configuração para Planos de Chamada, a Contoso analisou as decisões principais de [implantação do Plano de Chamada.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="f15a6-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="f15a6-200">As decisões resultantes foram tomadas:</span><span class="sxs-lookup"><span data-stu-id="f15a6-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="f15a6-201">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-201">Q.</span></span> <span data-ttu-id="f15a6-202">Meus usuários precisam de chamada internacional?</span><span class="sxs-lookup"><span data-stu-id="f15a6-202">Do my users need international calling?</span></span><br> <span data-ttu-id="f15a6-203">A. Sim</span><span class="sxs-lookup"><span data-stu-id="f15a6-203">A. Yes</span></span> 

- <span data-ttu-id="f15a6-204">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-204">Q.</span></span> <span data-ttu-id="f15a6-205">Cada um dos meus usuários tem um número de telefone DID direto para dentro?</span><span class="sxs-lookup"><span data-stu-id="f15a6-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="f15a6-206">R. Não hoje.</span><span class="sxs-lookup"><span data-stu-id="f15a6-206">A. Not today.</span></span> <span data-ttu-id="f15a6-207">Todos os usuários habilitados receberão um DID.</span><span class="sxs-lookup"><span data-stu-id="f15a6-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="f15a6-208">P.</span><span class="sxs-lookup"><span data-stu-id="f15a6-208">Q.</span></span> <span data-ttu-id="f15a6-209">Quero mascarar ou desabilitar a ID do chamador?</span><span class="sxs-lookup"><span data-stu-id="f15a6-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="f15a6-210">A. A ID do chamador de um usuário será mascarada para o número local da Contoso.</span><span class="sxs-lookup"><span data-stu-id="f15a6-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="f15a6-211">Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="f15a6-211">Direct Routing</span></span>

<span data-ttu-id="f15a6-212">A Contoso participou do Ignite para se manter atual nos recursos do Office 365, incluindo aqueles disponíveis com o sistema de telefonia e o Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="f15a6-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="f15a6-213">Líderes técnicos e arquitetos usaram as diretrizes fornecidas durante o Ignite 2019 para determinar sua direção.</span><span class="sxs-lookup"><span data-stu-id="f15a6-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="f15a6-214">Principais sessões que foram usadas:</span><span class="sxs-lookup"><span data-stu-id="f15a6-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="f15a6-215">Planejar o sucesso com o Roteamento Direto do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f15a6-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="f15a6-216">Atualizações para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="f15a6-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="f15a6-217">Configuração</span><span class="sxs-lookup"><span data-stu-id="f15a6-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="f15a6-218">Sites de Planos de Chamada</span><span class="sxs-lookup"><span data-stu-id="f15a6-218">Calling Plans sites</span></span>

<span data-ttu-id="f15a6-219">Para obter licenças e atribuir números de telefone aos usuários, a Contoso seguiu as etapas em [Configurar Planos de Chamadas.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="f15a6-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="f15a6-220">Devido ao número de usuários que precisavam ser atribuídos números de telefone, a Contoso decidiu usar o PowerShell para atribuir os números de telefone.</span><span class="sxs-lookup"><span data-stu-id="f15a6-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="f15a6-221">Para saber como atribuir números usando o PowerShell, além de outras configurações, a Contoso usou a Visão Geral do &mdash; &mdash; [PowerShell do Teams.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f15a6-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="f15a6-222">Sites de Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="f15a6-222">Direct Routing sites</span></span>

<span data-ttu-id="f15a6-223">Para conectar a infraestrutura de telefonia local da Contoso ao Microsoft Teams, o administrador da Contoso seguiu as etapas em [Configurar](direct-routing-configure.md) Roteamento Direto e reviu o vídeo Roteamento Direto no [Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obter orientações.</span><span class="sxs-lookup"><span data-stu-id="f15a6-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="f15a6-224">A Contoso também se referiu à documentação de implantação de roteamento direto pelo fornecedor SBC certificado.</span><span class="sxs-lookup"><span data-stu-id="f15a6-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="f15a6-225">Depois que o Roteamento Direto foi configurado entre o SBC e o Microsoft Phone System, foi necessário que a Contoso testa a configuração.</span><span class="sxs-lookup"><span data-stu-id="f15a6-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="f15a6-226">Para fazer isso, os administradores da Contoso usaram o cliente testador SIP que foi discutido na sessão Atualizações para Roteamento Direto no [Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="f15a6-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="f15a6-227">O script e a documentação do cliente do Testador SIP foram baixados do script do PowerShell para testar conexões do Controlador de Borda de Sessão de Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="f15a6-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="f15a6-228">Otimização de mídia local</span><span class="sxs-lookup"><span data-stu-id="f15a6-228">Local Media Optimization</span></span>

<span data-ttu-id="f15a6-229">A Contoso viu a oportunidade de aproveitar a Otimização de Mídia Local nas diferentes regiões do mundo.</span><span class="sxs-lookup"><span data-stu-id="f15a6-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="f15a6-230">Os cenários com suporte para Contoso são descritos em [Otimização de Mídia Local para Roteamento Direto.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="f15a6-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="f15a6-231">A configuração da otimização de mídia local foi concluída seguindo as diretrizes do fornecedor SBC e da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f15a6-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="f15a6-232">As etapas de configuração para Otimização de Mídia Local incluem:</span><span class="sxs-lookup"><span data-stu-id="f15a6-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="f15a6-233">Configurar o usuário e os sites SBC</span><span class="sxs-lookup"><span data-stu-id="f15a6-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="f15a6-234">Configurar o SBC de acordo com a especificação do fornecedor SBC,</span><span class="sxs-lookup"><span data-stu-id="f15a6-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="f15a6-235">Adicionar endereços IP confiáveis externos a cada site usado para Otimização de Mídia Local</span><span class="sxs-lookup"><span data-stu-id="f15a6-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="f15a6-236">Definir a topologia de rede</span><span class="sxs-lookup"><span data-stu-id="f15a6-236">Define the network topology</span></span> 

- <span data-ttu-id="f15a6-237">Definir a topologia de rede virtual</span><span class="sxs-lookup"><span data-stu-id="f15a6-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="f15a6-238">Determinar o modo: Sempre Ignorar ou Somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="f15a6-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="f15a6-239">Considerações sobre rede</span><span class="sxs-lookup"><span data-stu-id="f15a6-239">Networking considerations</span></span>

<span data-ttu-id="f15a6-240">A Contoso tinha vários usuários que precisavam trabalhar remotamente por um longo período de tempo após a habilitação para o Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="f15a6-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="f15a6-241">Os usuários usavam VPN para acessar determinados aplicativos de Linha de Negócios.</span><span class="sxs-lookup"><span data-stu-id="f15a6-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="f15a6-242">Durante a VPN, os usuários do Sistema de Telefonia experimentaram uma degradação da qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="f15a6-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="f15a6-243">Para resolver o problema de qualidade, a Contoso implementou o túnel dividido de VPN, permitindo que o tráfego do Office 365 atravessasse a Internet enquanto a conexão com os aplicativos internos permanecesse na VPN.</span><span class="sxs-lookup"><span data-stu-id="f15a6-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="f15a6-244">Para implementar o túnel dividido de VPN, a Contoso seguiu as diretrizes em Implementar o túnel [dividido de VPN para o Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="f15a6-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

