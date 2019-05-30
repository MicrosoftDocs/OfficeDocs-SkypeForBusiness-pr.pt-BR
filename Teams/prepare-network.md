---
title: Preparo da rede da sua organização para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Saiba como preparar e gerenciar sua rede para o Microsoft Teams. As informações incluem requisitos de rede, requisitos de largura de banda e considerações adicionais.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 330b62bc98d4a45d8d6902707dd2ebb9fd031913
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548274"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="cc95b-104">Preparo da rede da sua organização para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc95b-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="cc95b-105">O Microsoft Teams combina três formas de tráfego:</span><span class="sxs-lookup"><span data-stu-id="cc95b-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="cc95b-106">O tráfego de dados entre o ambiente online do Office 365 e o cliente Microsoft Teams (sinalização, presença, chat, upload e download de arquivos, sincronização do OneNote).</span><span class="sxs-lookup"><span data-stu-id="cc95b-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="cc95b-107">Tráfego de comunicação ponto a ponto em tempo real (compartilhamento de áudio, vídeo e área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="cc95b-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="cc95b-108">Tráfego de comunicação de conferências em tempo real (compartilhamento de áudio, vídeo e área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="cc95b-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="cc95b-109">Isso impacta a rede em dois níveis: o tráfego fluirá entre os clientes Microsoft Teams diretamente para cenários ponto a ponto, e o tráfego fluirá entre o ambiente do Office 365 e os clientes Microsoft Teams para os cenários de reunião.</span><span class="sxs-lookup"><span data-stu-id="cc95b-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="cc95b-110">Para garantir um fluxo de tráfego ideal, o tráfego deve ser permitido entre os segmentos internos da rede (por exemplo, entre sites da WAN), bem como entre os sites da rede e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc95b-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="cc95b-111">Deixar de abrir as portas corretas ou bloquear ativamente as portas especificadas prejudicará a experiência.</span><span class="sxs-lookup"><span data-stu-id="cc95b-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="cc95b-112">As reuniões têm suporte em dispositivos móveis iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="cc95b-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="cc95b-113">Para ter uma experiência ideal com mídia em tempo real no Microsoft Teams, sua rede deve atender aos requisitos de rede do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc95b-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="cc95b-114">Para obter mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="cc95b-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="cc95b-115">Os dois segmentos de rede a ser definidos (Cliente para o Microsoft Edge e Edge do cliente para o Microsoft Edge), considere os seguintes requisitos.</span><span class="sxs-lookup"><span data-stu-id="cc95b-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="cc95b-116">Valor</span><span class="sxs-lookup"><span data-stu-id="cc95b-116">Value</span></span>  |<span data-ttu-id="cc95b-117">Cliente para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cc95b-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="cc95b-118">Edge do cliente para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cc95b-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="cc95b-119">**Latência (de uma maneira)**\*</span><span class="sxs-lookup"><span data-stu-id="cc95b-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="cc95b-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="cc95b-120">< 50ms</span></span>          |<span data-ttu-id="cc95b-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="cc95b-121">< 30ms</span></span>         |
|<span data-ttu-id="cc95b-122">**Latência (RTT ou tempo de viagem de ida e volta)**\*</span><span class="sxs-lookup"><span data-stu-id="cc95b-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="cc95b-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="cc95b-123">< 100ms</span></span>   |<span data-ttu-id="cc95b-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="cc95b-124">< 60ms</span></span> |
|<span data-ttu-id="cc95b-125">**Perda de pacote de intermitência**</span><span class="sxs-lookup"><span data-stu-id="cc95b-125">**Burst packet loss**</span></span>    |<span data-ttu-id="cc95b-126"><10% durante qualquer intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="cc95b-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="cc95b-127"><1% durante qualquer intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="cc95b-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="cc95b-128">**Perda de pacote**</span><span class="sxs-lookup"><span data-stu-id="cc95b-128">**Packet loss**</span></span>     |<span data-ttu-id="cc95b-129"><1% durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="cc95b-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="cc95b-130"><0,1% durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="cc95b-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="cc95b-131">**Tremulação entre chegadas de pacote**</span><span class="sxs-lookup"><span data-stu-id="cc95b-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="cc95b-132"><30 ms durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="cc95b-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="cc95b-133"><15 ms durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="cc95b-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="cc95b-134">**Novo pedido de pacotes**</span><span class="sxs-lookup"><span data-stu-id="cc95b-134">**Packet reorder**</span></span>    |<span data-ttu-id="cc95b-135"><0,05% de pacotes com problemas</span><span class="sxs-lookup"><span data-stu-id="cc95b-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="cc95b-136"><0,01% de pacotes com problemas</span><span class="sxs-lookup"><span data-stu-id="cc95b-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="cc95b-137">\*Os destinos de métrica de latência assumem que o site ou os sites da empresa e as bordas da Microsoft estão no mesmo continente.</span><span class="sxs-lookup"><span data-stu-id="cc95b-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="cc95b-138">A conexão do site da sua empresa com o Microsoft Network Edge inclui o acesso de rede de primeiro salto, que pode ser WiFi ou outra tecnologia sem fio.</span><span class="sxs-lookup"><span data-stu-id="cc95b-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="cc95b-139">Os destinos de desempenho de rede pressupõem largura de banda e/ou [planejamento de QoS](QoS-in-Teams.md)adequado.</span><span class="sxs-lookup"><span data-stu-id="cc95b-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="cc95b-140">Em outras palavras, os requisitos se aplicam diretamente ao tráfego de mídia em tempo real do teams quando a conexão de rede está com carga de pico.</span><span class="sxs-lookup"><span data-stu-id="cc95b-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="cc95b-141">Para testar ambos os segmentos de rede, você pode usar a [ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="cc95b-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="cc95b-142">Essa ferramenta pode ser implantada diretamente no PC cliente e em um PC conectado à borda de rede do cliente.</span><span class="sxs-lookup"><span data-stu-id="cc95b-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="cc95b-143">A ferramenta inclui documentação limitada, mas uma documentação mais profunda sobre o uso da ferramenta pode ser encontrada aqui: [avaliação de prontidão de rede](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="cc95b-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="cc95b-144">Ao executar esta avaliação de preparação de rede, você pode validar a preparação da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cc95b-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="cc95b-145">Esta é a mesma avaliação de preparação de rede que é recomendada para os clientes que pretendem implantar o Skype for Business com êxito.</span><span class="sxs-lookup"><span data-stu-id="cc95b-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="cc95b-146">Requisitos de largura de banda</span><span class="sxs-lookup"><span data-stu-id="cc95b-146">Bandwidth requirements</span></span>
<span data-ttu-id="cc95b-147">O Microsoft Teams oferece a melhor experiência de áudio, vídeo e compartilhamento de conteúdo, independentemente das condições da rede.</span><span class="sxs-lookup"><span data-stu-id="cc95b-147">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="cc95b-148">Com os codecs variáveis, a mídia pode ser negociada em ambientes limitados de largura de banda com impacto mínimo.</span><span class="sxs-lookup"><span data-stu-id="cc95b-148">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="cc95b-149">Mas onde a largura de banda não é uma preocupação, as experiências podem ser otimizadas para qualidade, incluindo até 1080p de resolução de vídeo, até 30 qps para vídeo e 15fps para conteúdo e áudio de alta fidelidade.</span><span class="sxs-lookup"><span data-stu-id="cc95b-149">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


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

<a name="additional-network-considerations"></a><span data-ttu-id="cc95b-150">Considerações de rede adicionais</span><span class="sxs-lookup"><span data-stu-id="cc95b-150">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="cc95b-151">Resolução de nomes externos</span><span class="sxs-lookup"><span data-stu-id="cc95b-151">External Name Resolution</span></span>

<span data-ttu-id="cc95b-152">Verifique se todos os computadores cliente que executam o cliente do teams podem resolver consultas DNS externas para descobrir os serviços fornecidos pelo Office 365 e se seus firewalls não impedem o acesso.</span><span class="sxs-lookup"><span data-stu-id="cc95b-152">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="cc95b-153">Para obter informações sobre como configurar portas de firewall, vá para [URLs e intervalos de IP do Office 365](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="cc95b-153">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="cc95b-154">Tamanho do pool NAT</span><span class="sxs-lookup"><span data-stu-id="cc95b-154">NAT Pool Size</span></span>

<span data-ttu-id="cc95b-155">Quando vários usuários/dispositivos acessam o Office 365 usando a NAT (conversão de endereços de rede) ou PAT (conversão de endereço de porta), você precisa garantir que os dispositivos ocultos atrás de cada endereço IP roteável publicamente não exceda o número compatível.</span><span class="sxs-lookup"><span data-stu-id="cc95b-155">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="cc95b-156">Para reduzir esse risco, certifique-se de que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para evitar a exaustão de portabilidade.</span><span class="sxs-lookup"><span data-stu-id="cc95b-156">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="cc95b-157">A exaustão da porta fará com que usuários finais e dispositivos internos tenham problemas quando se conectar aos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc95b-157">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="cc95b-158">Para obter mais informações, consulte [suporte a NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="cc95b-158">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="cc95b-159">**Orientação de detecção e prevenção de invasões**</span><span class="sxs-lookup"><span data-stu-id="cc95b-159">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="cc95b-160">Se seu ambiente tem um sistema de prevenção de intrusão e/ou prevenção (IDS/IPS) implantado para obter uma camada adicional de segurança para conexões de saída, certifique-se de que qualquer tráfego com o destino para URLs do Office 365 seja da lista branca.</span><span class="sxs-lookup"><span data-stu-id="cc95b-160">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="cc95b-161">Determinação da integridade da rede</span><span class="sxs-lookup"><span data-stu-id="cc95b-161">Network health determination</span></span>
-----------------

<span data-ttu-id="cc95b-162">Ao planejar a implementação do Microsoft Teams em sua rede, você deve certificar-se de que tem a largura de banda necessária, ter acesso a todos os endereços IP necessários, às portas corretas abertas e a atender aos requisitos de desempenho de mídia em tempo real .</span><span class="sxs-lookup"><span data-stu-id="cc95b-162">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="cc95b-163">Se você sabe que não atenderá a esses critérios, seus usuários finais não receberão uma experiência ideal do teams devido à qualidade ruim durante chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="cc95b-163">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="cc95b-164">Se você não atender a esses critérios, essa é a hora de considerar a pausa do projeto para garantir que você atenda aos critérios antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="cc95b-164">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="cc95b-166">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="cc95b-166">Decision Point</span></span>         |<span data-ttu-id="cc95b-167">Você avaliou seus recursos de rede para oferecer suporte à mídia em tempo real?</span><span class="sxs-lookup"><span data-stu-id="cc95b-167">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="cc95b-168">Se a sua rede não tiver sido corretamente avaliada ou você souber que ela não será compatível com a mídia em tempo real, você desabilitará os recursos de vídeo e compartilhamento de tela para reduzir o impacto na rede e as experiências de equipes deficientes?</span><span class="sxs-lookup"><span data-stu-id="cc95b-168">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Um ícone que representa as próximas etapas](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="cc95b-170">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="cc95b-170">Next Steps</span></span>         |<span data-ttu-id="cc95b-171">Qualidade de rede desconhecida: siga as diretrizes de [avaliação de preparação de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) para determinar se a sua rede está pronta para mídia em tempo real.</span><span class="sxs-lookup"><span data-stu-id="cc95b-171">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="cc95b-172">Qualidade da rede ruim: realize as etapas de correção de rede para fornecer um ambiente adequado para mídia de alta qualidade em tempo real.</span><span class="sxs-lookup"><span data-stu-id="cc95b-172">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="cc95b-173">Rede satisfatória: Assegure-se de que todos os endereços IP e portas estejam acessíveis corretamente.</span><span class="sxs-lookup"><span data-stu-id="cc95b-173">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="cc95b-174">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="cc95b-174">Related Topics</span></span>

[<span data-ttu-id="cc95b-175">Vídeo: planejamento de rede</span><span class="sxs-lookup"><span data-stu-id="cc95b-175">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
