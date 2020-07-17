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
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785944"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="74db1-103">Estudo de caso da Contoso: sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="74db1-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="74db1-104">Dependendo da localização geográfica e de outros fatores, a Contoso tinha escritórios usando as seguintes soluções de telefonia:</span><span class="sxs-lookup"><span data-stu-id="74db1-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="74db1-105">Tipo de site A: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="74db1-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="74db1-106">Tipo de site B: sistemas de telefonia herdados tradicionais</span><span class="sxs-lookup"><span data-stu-id="74db1-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="74db1-107">Tipo de site C: uma combinação do Skype for Business Enterprise Voice e dos sistemas de telefonia herdados tradicionais</span><span class="sxs-lookup"><span data-stu-id="74db1-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="74db1-108">Para implementar uma solução de sistema telefônico da Microsoft para toda a sua organização, a Contoso tinha que determinar &mdash; para cada tipo &mdash; de site quais das seguintes opções seriam usadas com o sistema telefônico para se conectar à rede telefônica pública comutada (PSTN):</span><span class="sxs-lookup"><span data-stu-id="74db1-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="74db1-109">Sistema telefônico com plano de chamada</span><span class="sxs-lookup"><span data-stu-id="74db1-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="74db1-110">Sistema telefônico com uma transportabilidade PSTN por meio do roteamento direto</span><span class="sxs-lookup"><span data-stu-id="74db1-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="74db1-111">Combinação de sistema telefônico com plano de chamada e sistema telefônico com a própria transportabilidade PSTN por meio do direcionamento direto</span><span class="sxs-lookup"><span data-stu-id="74db1-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="74db1-112">Para determinar a solução certa para sua organização, a contoso usou [soluções de telefonia da Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) e as chamadas de sessão do Ignite 2019 [no Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="74db1-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="74db1-113">Tipo de site A: Skype for Business Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="74db1-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="74db1-114">O Skype for Business Enterprise Voice da Contoso foi configurado como Hub e spoke.</span><span class="sxs-lookup"><span data-stu-id="74db1-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="74db1-115">Havia um local central que mantinha o gateway PSTN na região que forneceu a conexão com a PSTN para os usuários do Skype for Business Enterprise Voice em país.</span><span class="sxs-lookup"><span data-stu-id="74db1-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="74db1-116">Geralmente, esses telefones de satélite não têm o seu próprio egresso na Internet.</span><span class="sxs-lookup"><span data-stu-id="74db1-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="74db1-117">Os números para esses usuários residem no tronco SIP se conectando a um SBC existente.</span><span class="sxs-lookup"><span data-stu-id="74db1-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="74db1-118">Para determinar se o SBC já implantado é certificado para roteamento direto e bypass de mídia, a contoso verificou a [lista de controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="74db1-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="74db1-119">Os hábitos de discagem do usuário eram discar um usuário no sistema de telefonia herdado usando uma extensão, mesmo quando o usuário tem um cliente Skype for Business disponível para o áudio ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="74db1-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="74db1-120">A contoso baseou suas decisões nas seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="74db1-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="74db1-121">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-121">Q.</span></span> <span data-ttu-id="74db1-122">Precisamos manter a funcionalidade oferecida pela sua implantação local?</span><span class="sxs-lookup"><span data-stu-id="74db1-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="74db1-123">Um.</span><span class="sxs-lookup"><span data-stu-id="74db1-123">A.</span></span> <span data-ttu-id="74db1-124">Não</span><span class="sxs-lookup"><span data-stu-id="74db1-124">No</span></span> 

- <span data-ttu-id="74db1-125">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-125">Q.</span></span> <span data-ttu-id="74db1-126">Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?</span><span class="sxs-lookup"><span data-stu-id="74db1-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="74db1-127">Um.</span><span class="sxs-lookup"><span data-stu-id="74db1-127">A.</span></span> <span data-ttu-id="74db1-128">Não</span><span class="sxs-lookup"><span data-stu-id="74db1-128">No</span></span> 

- <span data-ttu-id="74db1-129">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-129">Q.</span></span> <span data-ttu-id="74db1-130">Precisamos manter o nosso carro de terceiros atual?</span><span class="sxs-lookup"><span data-stu-id="74db1-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="74db1-131">A. Sim (países regulamentados) e não</span><span class="sxs-lookup"><span data-stu-id="74db1-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="74db1-132">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-132">Q.</span></span> <span data-ttu-id="74db1-133">Precisamos ter o ROI implantado no SBCs?</span><span class="sxs-lookup"><span data-stu-id="74db1-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="74db1-134">A. Sim e não</span><span class="sxs-lookup"><span data-stu-id="74db1-134">A. Yes and No</span></span>  

- <span data-ttu-id="74db1-135">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-135">Q.</span></span> <span data-ttu-id="74db1-136">Os planos de chamada PSTN da Microsoft estão disponíveis nesta região?</span><span class="sxs-lookup"><span data-stu-id="74db1-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="74db1-137">A. Sim e não</span><span class="sxs-lookup"><span data-stu-id="74db1-137">A. Yes and No</span></span> 

<span data-ttu-id="74db1-138">Com base nas respostas às suas perguntas, a Contoso decidiu:</span><span class="sxs-lookup"><span data-stu-id="74db1-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="74db1-139">Mova os usuários que estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para o sistema telefônico com planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="74db1-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="74db1-140">Mover os usuários que não estão localizados em uma região em que os planos de chamada PSTN estão disponíveis, os usuários localizados em um site em que o ROI do SBCs ainda devem ser atendidos e os usuários residentes em um país que tenha regulamentos de telefonia para o sistema telefônico com roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="74db1-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="74db1-141">O diagrama a seguir mostra a implantação inicial do Skype for Business Enterprise Voice e como essa implantação foi migrada para os planos de chamada da Microsoft e para o roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="74db1-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![Diagrama mostrando o estado anterior e posterior](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="74db1-143">Tipo de site B: sistemas de telefonia herdados tradicionais</span><span class="sxs-lookup"><span data-stu-id="74db1-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="74db1-144">A Contoso tinha muitos escritórios que aproveitaram os sistemas de telefonia herdados.</span><span class="sxs-lookup"><span data-stu-id="74db1-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="74db1-145">Havia um subconjunto de usuários que tinham um número de telefone E 1.64 enquanto outras pessoas tinham apenas uma extensão.</span><span class="sxs-lookup"><span data-stu-id="74db1-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="74db1-146">Esses números residem no tronco TDM para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="74db1-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="74db1-147">A discagem dentro do site foi configurada aproveitando um código de site na frente da extensão para determinar onde direcionar a chamada.</span><span class="sxs-lookup"><span data-stu-id="74db1-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="74db1-148">Os hábitos de discagem dos usuários eram discados por extensão.</span><span class="sxs-lookup"><span data-stu-id="74db1-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="74db1-149">A contoso baseou suas decisões nas seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="74db1-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="74db1-150">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-150">Q.</span></span> <span data-ttu-id="74db1-151">Precisamos manter a funcionalidade oferecida pela sua implantação local?</span><span class="sxs-lookup"><span data-stu-id="74db1-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="74db1-152">Um.</span><span class="sxs-lookup"><span data-stu-id="74db1-152">A.</span></span> <span data-ttu-id="74db1-153">Não</span><span class="sxs-lookup"><span data-stu-id="74db1-153">No</span></span> 

- <span data-ttu-id="74db1-154">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-154">Q.</span></span> <span data-ttu-id="74db1-155">Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?</span><span class="sxs-lookup"><span data-stu-id="74db1-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="74db1-156">A. Sim</span><span class="sxs-lookup"><span data-stu-id="74db1-156">A. Yes</span></span>

- <span data-ttu-id="74db1-157">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-157">Q.</span></span> <span data-ttu-id="74db1-158">Precisamos manter o nosso carro de terceiros atual?</span><span class="sxs-lookup"><span data-stu-id="74db1-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="74db1-159">R. no</span><span class="sxs-lookup"><span data-stu-id="74db1-159">A. No</span></span> 

- <span data-ttu-id="74db1-160">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-160">Q.</span></span> <span data-ttu-id="74db1-161">O plano de chamadas de PSTN da Microsoft está disponível na nossa região?</span><span class="sxs-lookup"><span data-stu-id="74db1-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="74db1-162">A. Sim e não</span><span class="sxs-lookup"><span data-stu-id="74db1-162">A. Yes and No</span></span> 

<span data-ttu-id="74db1-163">Com base nas respostas às suas perguntas, a Contoso decidiu:</span><span class="sxs-lookup"><span data-stu-id="74db1-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="74db1-164">Mova os usuários que estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para o sistema telefônico com planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="74db1-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="74db1-165">Mova os usuários que não estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para o sistema telefônico com roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="74db1-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="74db1-166">Mantenha uma conexão PSTN com dispositivos analógicos críticos para empresas.</span><span class="sxs-lookup"><span data-stu-id="74db1-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="74db1-167">Os diagramas a seguir mostram a implantação de sistema original herdada com sites remotos e a migração para uma implantação de roteamento direto com a otimização de mídia local:</span><span class="sxs-lookup"><span data-stu-id="74db1-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="74db1-168">**Original legacy deployment**  
 Implantação ![ herdada original Diagrama mostrando o estado anterior e posterior](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="74db1-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="74db1-169">**Implantação com roteamento direto**</span><span class="sxs-lookup"><span data-stu-id="74db1-169">**Deployment with Direct Routing**</span></span>

![Diagrama mostrando o estado anterior e posterior](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="74db1-171">Tipo de site C: combinação do Skype for Business Enterprise Voice e sistemas de telefonia herdados tradicionais</span><span class="sxs-lookup"><span data-stu-id="74db1-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="74db1-172">Os números de usuários do Skype for Business Enterprise Voice do contoso residem no tronco SIP para o SBC da operadora.</span><span class="sxs-lookup"><span data-stu-id="74db1-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="74db1-173">Os números dos sistemas de telefonia tradicionais residem no tronco TDM para o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="74db1-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="74db1-174">A contoso baseou suas decisões nas seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="74db1-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="74db1-175">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-175">Q.</span></span> <span data-ttu-id="74db1-176">Precisamos manter a funcionalidade oferecida pela sua implantação local?</span><span class="sxs-lookup"><span data-stu-id="74db1-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="74db1-177">Um.</span><span class="sxs-lookup"><span data-stu-id="74db1-177">A.</span></span> <span data-ttu-id="74db1-178">Não</span><span class="sxs-lookup"><span data-stu-id="74db1-178">No</span></span> 

- <span data-ttu-id="74db1-179">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-179">Q.</span></span> <span data-ttu-id="74db1-180">Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?</span><span class="sxs-lookup"><span data-stu-id="74db1-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="74db1-181">R. no</span><span class="sxs-lookup"><span data-stu-id="74db1-181">A. No</span></span> 

- <span data-ttu-id="74db1-182">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-182">Q.</span></span> <span data-ttu-id="74db1-183">Precisamos manter o nosso carro de terceiros atual?</span><span class="sxs-lookup"><span data-stu-id="74db1-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="74db1-184">R. no</span><span class="sxs-lookup"><span data-stu-id="74db1-184">A. No</span></span> 

- <span data-ttu-id="74db1-185">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-185">Q.</span></span> <span data-ttu-id="74db1-186">Precisamos ter o ROI implantado no SBCs?</span><span class="sxs-lookup"><span data-stu-id="74db1-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="74db1-187">A. Sim e não</span><span class="sxs-lookup"><span data-stu-id="74db1-187">A. Yes and No</span></span>  

- <span data-ttu-id="74db1-188">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-188">Q.</span></span> <span data-ttu-id="74db1-189">O plano de chamada PSTN da Microsoft está disponível nesta região?</span><span class="sxs-lookup"><span data-stu-id="74db1-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="74db1-190">R. no</span><span class="sxs-lookup"><span data-stu-id="74db1-190">A. No</span></span> 

<span data-ttu-id="74db1-191">Com base nas respostas às suas perguntas, a Contoso decidiu o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74db1-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="74db1-192">Para os usuários de telefonia herdados que serão habilitados para roteamento direto, a contoso portou os números do tronco TDM para o tronco SIP para o SBC, pois o SBC é certificado para roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="74db1-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="74db1-193">Para dar suporte a um subconjunto de usuários que se movem para o sistema telefônico e para permitir roteamento contínuo por meio do sistema herdado, o sistema de telefonia herdado foi configurado como o próximo salto para o SBC.</span><span class="sxs-lookup"><span data-stu-id="74db1-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="74db1-194">Além disso, para incentivar a mudança de comportamento do usuário e remover a dependência na discagem de extensão entre sites, a contoso forneceu orientação para usar o Microsoft Teams para todas as chamadas internas.</span><span class="sxs-lookup"><span data-stu-id="74db1-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="74db1-195">Os diagramas a seguir mostram a implantação original do Skype for Business Enterprise Voice e do sistema de telefonia herdada e a migração para uma implantação mista usando o roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="74db1-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="74db1-196">**Original mixed deployment** 
 Implantação ![ mista original Diagrama mostrando o estado anterior](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="74db1-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="74db1-197">**Implantação mista com roteamento direto** 
 ![ Diagrama mostrando o estado anterior](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="74db1-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="74db1-198">Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="74db1-198">Calling Plans</span></span>

<span data-ttu-id="74db1-199">Para determinar os requisitos de configuração dos planos de chamadas, a contoso revisou as [decisões básicas de implantação do plano de chamadas](calling-plan-landing-page.md#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="74db1-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="74db1-200">As decisões resultantes foram feitas:</span><span class="sxs-lookup"><span data-stu-id="74db1-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="74db1-201">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-201">Q.</span></span> <span data-ttu-id="74db1-202">Meus usuários precisam fazer chamadas internacionais?</span><span class="sxs-lookup"><span data-stu-id="74db1-202">Do my users need international calling?</span></span><br> <span data-ttu-id="74db1-203">A. Sim</span><span class="sxs-lookup"><span data-stu-id="74db1-203">A. Yes</span></span> 

- <span data-ttu-id="74db1-204">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-204">Q.</span></span> <span data-ttu-id="74db1-205">Cada um dos meus usuários tem um número de telefone do Direct Inward?</span><span class="sxs-lookup"><span data-stu-id="74db1-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="74db1-206">A. não está hoje.</span><span class="sxs-lookup"><span data-stu-id="74db1-206">A. Not today.</span></span> <span data-ttu-id="74db1-207">Todos os usuários habilitados receberão um.</span><span class="sxs-lookup"><span data-stu-id="74db1-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="74db1-208">I.</span><span class="sxs-lookup"><span data-stu-id="74db1-208">Q.</span></span> <span data-ttu-id="74db1-209">Desejo mascarar ou desabilitar o recurso de identificação de chamadas?</span><span class="sxs-lookup"><span data-stu-id="74db1-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="74db1-210">R. a identificação de chamadas para um usuário será mascarada para o número local da contoso.</span><span class="sxs-lookup"><span data-stu-id="74db1-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="74db1-211">Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="74db1-211">Direct Routing</span></span>

<span data-ttu-id="74db1-212">A contoso participou Ignite para ficar atualizado sobre os recursos do Office 365, incluindo aqueles disponíveis com o sistema telefônico e o roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="74db1-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="74db1-213">Liderança técnica e arquitetos usaram as diretrizes fornecidas durante a Ignite 2019 para determinar sua direção.</span><span class="sxs-lookup"><span data-stu-id="74db1-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="74db1-214">Principais sessões que foram usadas:</span><span class="sxs-lookup"><span data-stu-id="74db1-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="74db1-215">Plano de sucesso com o Microsoft Teams Direct Routing</span><span class="sxs-lookup"><span data-stu-id="74db1-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="74db1-216">Atualizações para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="74db1-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="74db1-217">Configuração</span><span class="sxs-lookup"><span data-stu-id="74db1-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="74db1-218">Sites de planos de chamada</span><span class="sxs-lookup"><span data-stu-id="74db1-218">Calling Plans sites</span></span>

<span data-ttu-id="74db1-219">Para obter licenças e atribuir números de telefone aos usuários, a contoso seguiu as etapas em [configurar planos de chamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="74db1-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="74db1-220">Devido ao número de usuários que precisavam de números de telefone atribuídos, a Contoso decidiu usar o PowerShell para atribuir os números de telefone.</span><span class="sxs-lookup"><span data-stu-id="74db1-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="74db1-221">Para saber como atribuir números usando o PowerShell, &mdash; além de outras configurações, &mdash; a contoso usou a [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="74db1-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="74db1-222">Sites de roteamento direto</span><span class="sxs-lookup"><span data-stu-id="74db1-222">Direct Routing sites</span></span>

<span data-ttu-id="74db1-223">Para conectar a infraestrutura de telefonia local da Contoso ao Microsoft Teams, o administrador da Contoso seguiu as etapas em [Configurar o roteamento direto](direct-routing-configure.md) e analisou o [Roteamento direto de vídeo no Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obter diretrizes.</span><span class="sxs-lookup"><span data-stu-id="74db1-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="74db1-224">A contoso também se referiu à documentação de implantação de roteamento direto pelo fornecedor SBC certificado.</span><span class="sxs-lookup"><span data-stu-id="74db1-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="74db1-225">Após o roteamento direto ter sido configurado entre o SBC e o sistema telefônico da Microsoft, era necessário que a contoso teste a configuração.</span><span class="sxs-lookup"><span data-stu-id="74db1-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="74db1-226">Para isso, os administradores da Contoso usaram o cliente testador SIP que foi discutido na [sessão atualizações para roteamento direto no Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="74db1-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="74db1-227">O script de cliente de teste SIP e a documentação foram baixados do script do PowerShell para testar conexões de controlador de borda de sessão de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="74db1-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="74db1-228">Otimização de mídia local</span><span class="sxs-lookup"><span data-stu-id="74db1-228">Local Media Optimization</span></span>

<span data-ttu-id="74db1-229">A contoso viu a oportunidade de aproveitar a otimização de mídia local nas diferentes regiões do mundo todo.</span><span class="sxs-lookup"><span data-stu-id="74db1-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="74db1-230">Os cenários com suporte para contoso estão descritos em [otimização de mídia local para roteamento direto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="74db1-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="74db1-231">A configuração da otimização de mídia local foi concluída seguindo diretrizes do fornecedor do SBC e da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74db1-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="74db1-232">As etapas de configuração para a otimização de mídia local incluem:</span><span class="sxs-lookup"><span data-stu-id="74db1-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="74db1-233">Configurar os sites usuário e SBC</span><span class="sxs-lookup"><span data-stu-id="74db1-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="74db1-234">Configurar o SBC de acordo com a especificação do fornecedor do SBC,</span><span class="sxs-lookup"><span data-stu-id="74db1-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="74db1-235">Adicionar endereços IP externos confiáveis a cada site usado para otimização de mídia local</span><span class="sxs-lookup"><span data-stu-id="74db1-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="74db1-236">Definir a topologia de rede</span><span class="sxs-lookup"><span data-stu-id="74db1-236">Define the network topology</span></span> 

- <span data-ttu-id="74db1-237">Definir a topologia de rede virtual</span><span class="sxs-lookup"><span data-stu-id="74db1-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="74db1-238">Determine o modo: sempre ignorar ou somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="74db1-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="74db1-239">Considerações de rede</span><span class="sxs-lookup"><span data-stu-id="74db1-239">Networking considerations</span></span>

<span data-ttu-id="74db1-240">A Contoso tinha vários usuários que precisavam trabalhar remotamente por um período de tempo prolongado depois que foram habilitados para o sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="74db1-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="74db1-241">Os usuários usavam a VPN para acessar certos aplicativos de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="74db1-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="74db1-242">Durante a VPN, os usuários do sistema telefônico sofreram uma degradação da qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="74db1-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="74db1-243">Para resolver o problema de qualidade, a contoso implementou o tunelamento de VPN, que permitia que o tráfego do Office 365 atravessasse a Internet enquanto a conexão com os aplicativos internos permaneceram na VPN.</span><span class="sxs-lookup"><span data-stu-id="74db1-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="74db1-244">Para implementar o tunelamento de VPN, a contoso seguiu a orientação em [implementando o tunelamento de divisão VPN para o Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="74db1-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





