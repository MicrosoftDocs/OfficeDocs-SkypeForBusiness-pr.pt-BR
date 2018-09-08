---
title: Preparo da rede da sua organização para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: Saiba como preparar e gerenciar sua rede para o Microsoft Teams. As informações incluem requisitos de rede, requisitos de largura de banda e considerações adicionais.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470ddec93526fe5ea3aa5a24a835d37d971426c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892686"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="f5144-104">Preparo da rede da sua organização para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5144-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

<span data-ttu-id="f5144-105">O Microsoft Teams combina três formas de tráfego:</span><span class="sxs-lookup"><span data-stu-id="f5144-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="f5144-106">O tráfego de dados entre o ambiente online do Office 365 e o cliente Microsoft Teams (sinalização, presença, chat, upload e download de arquivos, sincronização do OneNote).</span><span class="sxs-lookup"><span data-stu-id="f5144-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="f5144-107">Tráfego de comunicação ponto a ponto em tempo real (compartilhamento de áudio, vídeo e área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="f5144-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="f5144-108">Tráfego de comunicação de conferências em tempo real (compartilhamento de áudio, vídeo e área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="f5144-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="f5144-109">Isso impacta a rede em dois níveis: o tráfego fluirá entre os clientes Microsoft Teams diretamente para cenários ponto a ponto, e o tráfego fluirá entre o ambiente do Office 365 e os clientes Microsoft Teams para os cenários de reunião.</span><span class="sxs-lookup"><span data-stu-id="f5144-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="f5144-110">Para garantir um fluxo de tráfego ideal, o tráfego deve ser permitido entre os segmentos internos da rede (por exemplo, entre sites da WAN), bem como entre os sites da rede e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5144-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="f5144-111">Deixar de abrir as portas corretas ou bloquear ativamente as portas especificadas prejudicará a experiência.</span><span class="sxs-lookup"><span data-stu-id="f5144-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5144-112">No momento, as reuniões têm suporte em dispositivos móveis iOS e Android, mas não no Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="f5144-112">Currently, meetings are supported on iOS and Android mobile devices, but not on Windows Phone.</span></span>

<span data-ttu-id="f5144-113">Para ter uma experiência ideal com mídia em tempo real no Microsoft Teams, é necessário atender aos requisitos de rede do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5144-113">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="f5144-114">Para mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="f5144-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="f5144-115">Para os dois determinantes segmentos de rede (cliente para Microsoft Edge) e a extremidade do cliente para o Microsoft Edge, considere as seguintes recomendações.</span><span class="sxs-lookup"><span data-stu-id="f5144-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="f5144-116">Valor</span><span class="sxs-lookup"><span data-stu-id="f5144-116">Value</span></span>  |<span data-ttu-id="f5144-117">Cliente para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f5144-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="f5144-118">Edge do cliente para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f5144-118">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f5144-119">**Latência (unidirecional)**</span><span class="sxs-lookup"><span data-stu-id="f5144-119">**Latency (one way)**</span></span>     |<span data-ttu-id="f5144-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="f5144-120">< 50ms</span></span>          |<span data-ttu-id="f5144-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="f5144-121">< 30ms</span></span>          |
|<span data-ttu-id="f5144-122">**Latência (RTT ou tempo-resposta)**</span><span class="sxs-lookup"><span data-stu-id="f5144-122">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="f5144-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="f5144-123">< 100ms</span></span>         |<span data-ttu-id="f5144-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="f5144-124">< 60ms</span></span>         |
|<span data-ttu-id="f5144-125">**Perda de pacote de intermitência**</span><span class="sxs-lookup"><span data-stu-id="f5144-125">**Burst packet loss**</span></span>    |<span data-ttu-id="f5144-126"><10% durante qualquer intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="f5144-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="f5144-127"><1% durante qualquer intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="f5144-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="f5144-128">**Perda de pacote**</span><span class="sxs-lookup"><span data-stu-id="f5144-128">**Packet loss**</span></span>     |<span data-ttu-id="f5144-129"><1% durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="f5144-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="f5144-130"><0,1% durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="f5144-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="f5144-131">**Tremulação entre chegadas de pacote**</span><span class="sxs-lookup"><span data-stu-id="f5144-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="f5144-132"><30 ms durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="f5144-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="f5144-133"><15 ms durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="f5144-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="f5144-134">**Novo pedido de pacotes**</span><span class="sxs-lookup"><span data-stu-id="f5144-134">**Packet reorder**</span></span>    |<span data-ttu-id="f5144-135"><0,05% de pacotes com problemas</span><span class="sxs-lookup"><span data-stu-id="f5144-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="f5144-136"><0,01% de pacotes com problemas</span><span class="sxs-lookup"><span data-stu-id="f5144-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="f5144-137">Para testar os dois segmentos de rede, use a [ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="f5144-137">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="f5144-138">Essa ferramenta pode ser implantada diretamente no computador cliente e em um computador conectado ao Customer Network Edge.</span><span class="sxs-lookup"><span data-stu-id="f5144-138">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="f5144-139">Essa ferramenta contém uma documentação limitada, mas uma documentação mais profunda do uso da ferramenta pode ser encontrada aqui: [Avaliação da prontidão da rede](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="f5144-139">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="f5144-140">Ao executar essa Avaliação da prontidão da rede, você pode validar a prontidão da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f5144-140">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="f5144-141">Essa é a mesma Avaliação da prontidão da rede recomendada para clientes que estão buscando implantar o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f5144-141">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="f5144-142">Requisitos de largura de banda</span><span class="sxs-lookup"><span data-stu-id="f5144-142">Bandwidth requirements</span></span>
----------

<span data-ttu-id="f5144-143">Os cálculos de largura de banda do Microsoft Teams são complexos e, para ajudar, foi criada uma calculadora.</span><span class="sxs-lookup"><span data-stu-id="f5144-143">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="f5144-144">Para acessar a calculadora, vá para [Planejador de Rede no MyAdvisor](https://aka.ms/bwcalc/).</span><span class="sxs-lookup"><span data-stu-id="f5144-144">To access the calculator, go to [Network Planner in MyAdvisor](https://aka.ms/bwcalc/).</span></span>

<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="f5144-145">Considerações de rede adicionais</span><span class="sxs-lookup"><span data-stu-id="f5144-145">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="f5144-146">**Resolução do nome externo**</span><span class="sxs-lookup"><span data-stu-id="f5144-146">**External Name Resolution**</span></span>

<span data-ttu-id="f5144-147">Certifique-se de que todos os computadores cliente que executam o cliente Microsoft Teams possam resolver consultas externas de DNS para descobrir os serviços fornecidos pelo Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5144-147">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="f5144-148">**Tamanho do pool de NAT**</span><span class="sxs-lookup"><span data-stu-id="f5144-148">**NAT Pool Size**</span></span>

<span data-ttu-id="f5144-149">Quando vários usuários/dispositivos acessam o Office 365 usando Conversão de Endereços de Rede (NAT) ou Conversão de Endereços de Porta (PAT), você precisa assegurar que os dispositivos ocultos em cada um dos endereços IP publicamente roteáveis não excedam o número suportado.</span><span class="sxs-lookup"><span data-stu-id="f5144-149">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="f5144-150">Para reduzir esse risco, garanta que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para prevenir o esgotamento de portas.</span><span class="sxs-lookup"><span data-stu-id="f5144-150">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="f5144-151">O esgotamento de portas fará com que dispositivos e usuários finais internos enfrentem problemas ao se conectarem aos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f5144-151">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="f5144-152">Para mais informações, consulte o [guia Suporte de NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="f5144-152">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="f5144-153">**Detecção de intrusões e guia de prevenção**</span><span class="sxs-lookup"><span data-stu-id="f5144-153">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="f5144-154">Se o seu ambiente tiver um Sistema de Detecção e/u Prevenção de Intrusões (IDS / IPS) implantado para uma camada extra de segurança para conexões de saída, certifique-se de que qualquer tráfego com destino para URLs do Office 365 esteja na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="f5144-154">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="f5144-155">Determinação da integridade de rede</span><span class="sxs-lookup"><span data-stu-id="f5144-155">Network health determination</span></span>
-----------------

<span data-ttu-id="f5144-156">Ao planejar a implementação do Microsoft Teams na sua rede, você precisa garantir ter a largura de banda necessária, ter acesso a todos os endereços IP necessários, ter as portas corretas abertas e atender aos requisitos de desempenho para mídias em tempo real.</span><span class="sxs-lookup"><span data-stu-id="f5144-156">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="f5144-157">Caso saiba da impossibilidade de atender a esses critérios, seus usuários finais não terão a experiência ideal no Microsoft Teams devido à má qualidade das chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="f5144-157">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="f5144-158">Caso não atenda a esses critérios, essa é a hora de considerar pausar o projeto para garantir que você esteja atendendo ao critérios antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="f5144-158">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="f5144-160">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="f5144-160">Decision Point</span></span>         |<span data-ttu-id="f5144-161">Você avaliou seus recursos de rede para suporte a mídia em tempo real?</span><span class="sxs-lookup"><span data-stu-id="f5144-161">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="f5144-162">Caso sua rede não tenha sido devidamente avaliada ou caso saiba que ela não consegue suportar mídia em tempo real, você vai desativar os recursos de vídeo e compartilhamento de tela para reduzir o impacto de rede e as experiências deficientes do Teams?</span><span class="sxs-lookup"><span data-stu-id="f5144-162">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Ícone de próximos passos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="f5144-164">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="f5144-164">Next Steps</span></span>         |<span data-ttu-id="f5144-165">Qualidade de rede desconhecida: siga as orientações da [Avaliação da prontidão da rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) em para determinar se a sua rede está preparada para reproduzir mídia em tempo real.</span><span class="sxs-lookup"><span data-stu-id="f5144-165">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="f5144-166">Qualidade de rede deficiente: Execute as etapas de remediação de rede para proporcionar um ambiente adequado e de alta qualidade para mídia em tempo real.</span><span class="sxs-lookup"><span data-stu-id="f5144-166">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="f5144-167">Satisfatoriedade de rede: Garanta que todas as portas e endereços IP possam ser acessados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="f5144-167">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

