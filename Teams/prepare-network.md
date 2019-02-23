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
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3af825b28f1c6c4abc202bb343c80b50176de16e
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205671"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="901e0-104">Preparo da rede da sua organização para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="901e0-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="901e0-105">Assista a sessão de seguir para saber como equipes aproveita sua rede e como planejar melhor conectividade de rede ideal: [Planejamento da rede de equipes](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="901e0-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="901e0-106">O Microsoft Teams combina três formas de tráfego:</span><span class="sxs-lookup"><span data-stu-id="901e0-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="901e0-107">O tráfego de dados entre o ambiente online do Office 365 e o cliente Microsoft Teams (sinalização, presença, chat, upload e download de arquivos, sincronização do OneNote).</span><span class="sxs-lookup"><span data-stu-id="901e0-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="901e0-108">Tráfego de comunicação ponto a ponto em tempo real (compartilhamento de áudio, vídeo e área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="901e0-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="901e0-109">Tráfego de comunicação de conferências em tempo real (compartilhamento de áudio, vídeo e área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="901e0-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="901e0-110">Isso impacta a rede em dois níveis: o tráfego fluirá entre os clientes Microsoft Teams diretamente para cenários ponto a ponto, e o tráfego fluirá entre o ambiente do Office 365 e os clientes Microsoft Teams para os cenários de reunião.</span><span class="sxs-lookup"><span data-stu-id="901e0-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="901e0-111">Para garantir um fluxo de tráfego ideal, o tráfego deve ser permitido entre os segmentos internos da rede (por exemplo, entre sites da WAN), bem como entre os sites da rede e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="901e0-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="901e0-112">Deixar de abrir as portas corretas ou bloquear ativamente as portas especificadas prejudicará a experiência.</span><span class="sxs-lookup"><span data-stu-id="901e0-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="901e0-113">Reuniões são suportados no iOS e dispositivos móveis Android.</span><span class="sxs-lookup"><span data-stu-id="901e0-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="901e0-114">Para ter uma experiência ideal com mídia em tempo real no Microsoft Teams, é necessário atender aos requisitos de rede do Office 365.</span><span class="sxs-lookup"><span data-stu-id="901e0-114">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="901e0-115">Para mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="901e0-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="901e0-116">Para os dois determinantes segmentos de rede (cliente para Microsoft Edge) e a extremidade do cliente para o Microsoft Edge, considere as seguintes recomendações.</span><span class="sxs-lookup"><span data-stu-id="901e0-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="901e0-117">Valor</span><span class="sxs-lookup"><span data-stu-id="901e0-117">Value</span></span>  |<span data-ttu-id="901e0-118">Cliente para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="901e0-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="901e0-119">Edge do cliente para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="901e0-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="901e0-120">**Latência (unidirecional)** \*</span><span class="sxs-lookup"><span data-stu-id="901e0-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="901e0-121">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="901e0-121">< 50ms</span></span>          |<span data-ttu-id="901e0-122">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="901e0-122">< 30ms</span></span>         |
|<span data-ttu-id="901e0-123">**Latência (RTT ou tempo-resposta)** \*</span><span class="sxs-lookup"><span data-stu-id="901e0-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="901e0-124">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="901e0-124">< 100ms</span></span>   |<span data-ttu-id="901e0-125">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="901e0-125">< 60ms</span></span> |
|<span data-ttu-id="901e0-126">**Perda de pacote de intermitência**</span><span class="sxs-lookup"><span data-stu-id="901e0-126">**Burst packet loss**</span></span>    |<span data-ttu-id="901e0-127"><10% durante qualquer intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="901e0-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="901e0-128"><1% durante qualquer intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="901e0-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="901e0-129">**Perda de pacote**</span><span class="sxs-lookup"><span data-stu-id="901e0-129">**Packet loss**</span></span>     |<span data-ttu-id="901e0-130"><1% durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="901e0-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="901e0-131"><0,1% durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="901e0-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="901e0-132">**Tremulação entre chegadas de pacote**</span><span class="sxs-lookup"><span data-stu-id="901e0-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="901e0-133"><30 ms durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="901e0-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="901e0-134"><15 ms durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="901e0-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="901e0-135">**Novo pedido de pacotes**</span><span class="sxs-lookup"><span data-stu-id="901e0-135">**Packet reorder**</span></span>    |<span data-ttu-id="901e0-136"><0,05% de pacotes com problemas</span><span class="sxs-lookup"><span data-stu-id="901e0-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="901e0-137"><0,01% de pacotes com problemas</span><span class="sxs-lookup"><span data-stu-id="901e0-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="901e0-138">\*As metas de latência métrico pressupõem que seu site da empresa ou sites e as bordas da Microsoft estão em continente o mesmo.</span><span class="sxs-lookup"><span data-stu-id="901e0-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="901e0-139">Sua conexão de site da empresa até a borda da rede Microsoft inclui primeiro salto acesso à rede, que pode ser WiFi ou outra tecnologia sem fio.</span><span class="sxs-lookup"><span data-stu-id="901e0-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="901e0-140">As metas de desempenho de rede pressupõem que a largura de banda adequada e/ou o [planejamento de QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="901e0-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="901e0-141">Em outras palavras, os requisitos se aplicam diretamente para o tráfego de mídia em tempo real de equipes quando a conexão de rede está sob uma carga de pico.</span><span class="sxs-lookup"><span data-stu-id="901e0-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="901e0-142">Para testar os dois segmentos de rede, use a [ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="901e0-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="901e0-143">Essa ferramenta pode ser implantada diretamente no computador cliente e em um computador conectado ao Customer Network Edge.</span><span class="sxs-lookup"><span data-stu-id="901e0-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="901e0-144">Essa ferramenta contém uma documentação limitada, mas uma documentação mais profunda do uso da ferramenta pode ser encontrada aqui: [Avaliação da prontidão da rede](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="901e0-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="901e0-145">Ao executar essa Avaliação da prontidão da rede, você pode validar a prontidão da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="901e0-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="901e0-146">Essa é a mesma Avaliação da prontidão da rede recomendada para clientes que estão buscando implantar o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="901e0-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="901e0-147">Requisitos de largura de banda</span><span class="sxs-lookup"><span data-stu-id="901e0-147">Bandwidth requirements</span></span>

<span data-ttu-id="901e0-148">Os cálculos de largura de banda do Microsoft Teams são complexos e, para ajudar, foi criada uma calculadora.</span><span class="sxs-lookup"><span data-stu-id="901e0-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="901e0-149">Para acessar a Calculadora, vá para [Planejador de rede](https://aka.ms/bwcalc/) em MyAdvisor.</span><span class="sxs-lookup"><span data-stu-id="901e0-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="901e0-150">Tratamento de largura de banda de equipes aprimorou Skype para Business Online: para obter uma qualidade alta chamando ou experiência (com áudio, vídeo e compartilhamento) de reunião, equipes requer apenas 1.2 Mbps.</span><span class="sxs-lookup"><span data-stu-id="901e0-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="901e0-151">Ele também pode ser dimensionado ainda mais para super alta qualidade se não houver largura de banda suficiente disponível.</span><span class="sxs-lookup"><span data-stu-id="901e0-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="901e0-152">Quando uma solicitação de equipes encontra uma condição de baixa largura de banda, as equipes podem rapidamente reajustar o uso de largura de banda para adaptar-se a largura de banda disponível.</span><span class="sxs-lookup"><span data-stu-id="901e0-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="901e0-153">Considerações de rede adicionais</span><span class="sxs-lookup"><span data-stu-id="901e0-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="901e0-154">Resolução do nome externo</span><span class="sxs-lookup"><span data-stu-id="901e0-154">External Name Resolution</span></span>

<span data-ttu-id="901e0-155">Certifique-se de que todos os computadores cliente executando o cliente de equipes podem resolver consultas DNS externas para descobrir os serviços fornecidos pelo Office 365 e que seus firewalls não estão impedindo o acesso.</span><span class="sxs-lookup"><span data-stu-id="901e0-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="901e0-156">Para obter informações sobre como configurar portas de firewall, vá para o [Office 365 URLs e intervalos IP](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="901e0-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="901e0-157">Tamanho do pool de NAT</span><span class="sxs-lookup"><span data-stu-id="901e0-157">NAT Pool Size</span></span>

<span data-ttu-id="901e0-158">Quando vários usuários/dispositivos acessam o Office 365 usando Conversão de Endereços de Rede (NAT) ou Conversão de Endereços de Porta (PAT), você precisa assegurar que os dispositivos ocultos em cada um dos endereços IP publicamente roteáveis não excedam o número suportado.</span><span class="sxs-lookup"><span data-stu-id="901e0-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="901e0-159">Para reduzir esse risco, garanta que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para prevenir o esgotamento de portas.</span><span class="sxs-lookup"><span data-stu-id="901e0-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="901e0-160">O esgotamento de portas fará com que dispositivos e usuários finais internos enfrentem problemas ao se conectarem aos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="901e0-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="901e0-161">Para mais informações, consulte o [guia Suporte de NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="901e0-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="901e0-162">**Detecção de intrusões e guia de prevenção**</span><span class="sxs-lookup"><span data-stu-id="901e0-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="901e0-163">Se o seu ambiente tiver um Sistema de Detecção e/u Prevenção de Intrusões (IDS / IPS) implantado para uma camada extra de segurança para conexões de saída, certifique-se de que qualquer tráfego com destino para URLs do Office 365 esteja na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="901e0-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="901e0-164">Determinação da integridade de rede</span><span class="sxs-lookup"><span data-stu-id="901e0-164">Network health determination</span></span>
-----------------

<span data-ttu-id="901e0-165">Ao planejar a implementação do Microsoft Teams na sua rede, você precisa garantir ter a largura de banda necessária, ter acesso a todos os endereços IP necessários, ter as portas corretas abertas e atender aos requisitos de desempenho para mídias em tempo real.</span><span class="sxs-lookup"><span data-stu-id="901e0-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="901e0-166">Caso saiba da impossibilidade de atender a esses critérios, seus usuários finais não terão a experiência ideal no Microsoft Teams devido à má qualidade das chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="901e0-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="901e0-167">Caso não atenda a esses critérios, essa é a hora de considerar pausar o projeto para garantir que você esteja atendendo ao critérios antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="901e0-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="901e0-169">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="901e0-169">Decision Point</span></span>         |<span data-ttu-id="901e0-170">Você avaliou seus recursos de rede para suporte a mídia em tempo real?</span><span class="sxs-lookup"><span data-stu-id="901e0-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="901e0-171">Caso sua rede não tenha sido devidamente avaliada ou caso saiba que ela não consegue suportar mídia em tempo real, você vai desativar os recursos de vídeo e compartilhamento de tela para reduzir o impacto de rede e as experiências deficientes do Teams?</span><span class="sxs-lookup"><span data-stu-id="901e0-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Ícone de próximos passos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="901e0-173">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="901e0-173">Next Steps</span></span>         |<span data-ttu-id="901e0-174">Qualidade de rede desconhecida: siga as orientações da [Avaliação da prontidão da rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) em para determinar se a sua rede está preparada para reproduzir mídia em tempo real.</span><span class="sxs-lookup"><span data-stu-id="901e0-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="901e0-175">Qualidade de rede deficiente: Execute as etapas de remediação de rede para proporcionar um ambiente adequado e de alta qualidade para mídia em tempo real.</span><span class="sxs-lookup"><span data-stu-id="901e0-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="901e0-176">Satisfatoriedade de rede: Garanta que todas as portas e endereços IP possam ser acessados adequadamente.</span><span class="sxs-lookup"><span data-stu-id="901e0-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="901e0-177">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="901e0-177">Related Topics</span></span>

[<span data-ttu-id="901e0-178">Vídeo: Planejamento de rede</span><span class="sxs-lookup"><span data-stu-id="901e0-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)