---
title: Preparo da rede da sua organização para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
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
ms.openlocfilehash: f8b3105889021408983c8e3ae249c74833e65ced
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800069"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="1d089-104">Preparo da rede da sua organização para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d089-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="1d089-105">O Microsoft Teams combina três formas de tráfego:</span><span class="sxs-lookup"><span data-stu-id="1d089-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="1d089-106">O tráfego de dados entre o ambiente online do Office 365 e o cliente Microsoft Teams (sinalização, presença, chat, upload e download de arquivos, sincronização do OneNote).</span><span class="sxs-lookup"><span data-stu-id="1d089-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="1d089-107">Tráfego de comunicação ponto a ponto em tempo real (compartilhamento de áudio, vídeo e área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="1d089-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="1d089-108">Tráfego de comunicação de conferências em tempo real (compartilhamento de áudio, vídeo e área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="1d089-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="1d089-109">Isso impacta a rede em dois níveis: o tráfego fluirá entre os clientes Microsoft Teams diretamente para cenários ponto a ponto, e o tráfego fluirá entre o ambiente do Office 365 e os clientes Microsoft Teams para os cenários de reunião.</span><span class="sxs-lookup"><span data-stu-id="1d089-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="1d089-110">Para garantir um fluxo de tráfego ideal, o tráfego deve ser permitido entre os segmentos internos da rede (por exemplo, entre sites da WAN), bem como entre os sites da rede e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1d089-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="1d089-111">Deixar de abrir as portas corretas ou bloquear ativamente as portas especificadas prejudicará a experiência.</span><span class="sxs-lookup"><span data-stu-id="1d089-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="1d089-112">Reuniões são suportados no iOS e dispositivos móveis Android.</span><span class="sxs-lookup"><span data-stu-id="1d089-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="1d089-113">Para obter uma experiência ideal com mídia de tempo real dentro Teams da Microsoft, a sua rede deve atender os requisitos de rede para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="1d089-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="1d089-114">Para obter mais informações, consulte [Qualidade de mídia e desempenho de conectividade de rede para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span><span class="sxs-lookup"><span data-stu-id="1d089-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="1d089-115">Os dois segmentos de rede a ser definidos (Cliente para o Microsoft Edge e Edge do cliente para o Microsoft Edge), considere os seguintes requisitos.</span><span class="sxs-lookup"><span data-stu-id="1d089-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="1d089-116">Valor</span><span class="sxs-lookup"><span data-stu-id="1d089-116">Value</span></span>  |<span data-ttu-id="1d089-117">Cliente para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d089-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="1d089-118">Edge do cliente para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d089-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="1d089-119">**Latência (uma maneira)**\*</span><span class="sxs-lookup"><span data-stu-id="1d089-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="1d089-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="1d089-120">< 50ms</span></span>          |<span data-ttu-id="1d089-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="1d089-121">< 30ms</span></span>         |
|<span data-ttu-id="1d089-122">**Latência (tempo de resposta ou tempo de ida e volta)**\*</span><span class="sxs-lookup"><span data-stu-id="1d089-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="1d089-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="1d089-123">< 100ms</span></span>   |<span data-ttu-id="1d089-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="1d089-124">< 60ms</span></span> |
|<span data-ttu-id="1d089-125">**Perda de pacote de intermitência**</span><span class="sxs-lookup"><span data-stu-id="1d089-125">**Burst packet loss**</span></span>    |<span data-ttu-id="1d089-126"><10% durante qualquer intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="1d089-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="1d089-127"><1% durante qualquer intervalo de 200 ms</span><span class="sxs-lookup"><span data-stu-id="1d089-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="1d089-128">**Perda de pacote**</span><span class="sxs-lookup"><span data-stu-id="1d089-128">**Packet loss**</span></span>     |<span data-ttu-id="1d089-129"><1% durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="1d089-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="1d089-130"><0,1% durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="1d089-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="1d089-131">**Tremulação entre chegadas de pacote**</span><span class="sxs-lookup"><span data-stu-id="1d089-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="1d089-132"><30 ms durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="1d089-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="1d089-133"><15 ms durante qualquer intervalo de 15 s</span><span class="sxs-lookup"><span data-stu-id="1d089-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="1d089-134">**Novo pedido de pacotes**</span><span class="sxs-lookup"><span data-stu-id="1d089-134">**Packet reorder**</span></span>    |<span data-ttu-id="1d089-135"><0,05% de pacotes com problemas</span><span class="sxs-lookup"><span data-stu-id="1d089-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="1d089-136"><0,01% de pacotes com problemas</span><span class="sxs-lookup"><span data-stu-id="1d089-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="1d089-137">\*As metas de latência métrico pressupõem que seu site da empresa ou sites e as bordas da Microsoft estão em continente o mesmo.</span><span class="sxs-lookup"><span data-stu-id="1d089-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="1d089-138">Sua conexão de site da empresa até a borda da rede Microsoft inclui primeiro salto acesso à rede, que pode ser WiFi ou outra tecnologia sem fio.</span><span class="sxs-lookup"><span data-stu-id="1d089-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="1d089-139">As metas de desempenho de rede pressupõem que a largura de banda adequada e/ou o [planejamento de QoS](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="1d089-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="1d089-140">Em outras palavras, os requisitos se aplicam diretamente para o tráfego de mídia em tempo real de equipes quando a conexão de rede está sob uma carga de pico.</span><span class="sxs-lookup"><span data-stu-id="1d089-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="1d089-141">Para testar os dois segmentos de rede, você pode usar a [Ferramenta de avaliação de rede](https://go.microsoft.com/fwlink/?linkid=855799).</span><span class="sxs-lookup"><span data-stu-id="1d089-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="1d089-142">Essa ferramenta pode ser implantada em ambos o cliente PC diretamente e em um PC conectado a borda da rede do cliente.</span><span class="sxs-lookup"><span data-stu-id="1d089-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="1d089-143">A ferramenta inclui documentação limitada, mas uma documentação mais aprofundada alternativa para o uso da ferramenta pode ser encontrada aqui: [Avaliação de prontidão de rede](https://go.microsoft.com/fwlink/?linkid=855800).</span><span class="sxs-lookup"><span data-stu-id="1d089-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="1d089-144">Executando esta avaliação de prontidão de rede, é possível validar a preparação da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1d089-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="1d089-145">Esta é a avaliação de prontidão de rede mesmo recomendado para ser executado para os clientes que desejam para implantar com êxito o Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="1d089-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="1d089-146">Requisitos de largura de banda</span><span class="sxs-lookup"><span data-stu-id="1d089-146">Bandwidth requirements</span></span>


<span data-ttu-id="1d089-147">Este artigo descreve uma versão concisa de como a largura de banda é utilizada por áudio de tempo real do Microsoft Teams, vídeo e compartilhamento modalidades em vários casos de uso.</span><span class="sxs-lookup"><span data-stu-id="1d089-147">This article describes a concise version of how bandwidth is utilized by Microsoft Teams real time audio, video, and desktop sharing modalities in various use cases.</span></span> <span data-ttu-id="1d089-148">As equipes é sempre conservadoras na utilização de largura de banda e pode fornecer a qualidade de vídeo HD em 1.2Mbps.</span><span class="sxs-lookup"><span data-stu-id="1d089-148">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.2Mbps.</span></span>  <span data-ttu-id="1d089-149">O consumo de largura de banda real em cada chamada de áudio/vídeo ou reunião irá variar, com base em vários fatores, como vídeo layout, resolução de vídeo e vídeos quadros por segundo.</span><span class="sxs-lookup"><span data-stu-id="1d089-149">The actual bandwidth consumption in each audio/video call or meeting will vary, based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="1d089-150">Quando houver mais largura de banda qualidade e uso aumentará para oferecer a melhor experiência.</span><span class="sxs-lookup"><span data-stu-id="1d089-150">When more bandwidth is available quality and usage will increase to deliver the best experience.</span></span>


|<span data-ttu-id="1d089-151">Bandwidth(up/down)</span><span class="sxs-lookup"><span data-stu-id="1d089-151">Bandwidth(up/down)</span></span> |<span data-ttu-id="1d089-152">Cenários</span><span class="sxs-lookup"><span data-stu-id="1d089-152">Scenarios</span></span> |
|---|---|
|<span data-ttu-id="1d089-153">30 kbps</span><span class="sxs-lookup"><span data-stu-id="1d089-153">30 kbps</span></span> |<span data-ttu-id="1d089-154">Chamadas de áudio ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="1d089-154">Peer-to-peer audio calling</span></span> |
|<span data-ttu-id="1d089-155">130 kbps</span><span class="sxs-lookup"><span data-stu-id="1d089-155">130 kbps</span></span> |<span data-ttu-id="1d089-156">As chamadas de áudio ponto a ponto e compartilhamento de tela</span><span class="sxs-lookup"><span data-stu-id="1d089-156">Peer-to-peer audio calling and screen sharing</span></span> |
|<span data-ttu-id="1d089-157">500 kbps</span><span class="sxs-lookup"><span data-stu-id="1d089-157">500 kbps</span></span> |<span data-ttu-id="1d089-158">Vídeo de chamar 360p a 30fps de qualidade de ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="1d089-158">Peer-to-peer quality video calling 360p at 30fps</span></span> |
|<span data-ttu-id="1d089-159">1.2 Mbps</span><span class="sxs-lookup"><span data-stu-id="1d089-159">1.2 Mbps</span></span> |<span data-ttu-id="1d089-160">Vídeo com qualidade chamar com resolução de HD 720 pixels a 30fps HD-a-ponto</span><span class="sxs-lookup"><span data-stu-id="1d089-160">Peer-to-peer HD quality video calling with resolution of HD 720p at 30fps</span></span> |
|<span data-ttu-id="1d089-161">1,5 Mbps</span><span class="sxs-lookup"><span data-stu-id="1d089-161">1.5 Mbps</span></span> |<span data-ttu-id="1d089-162">Vídeo com qualidade de chamada com resolução de HD 1080p em 30fps HD-a-ponto</span><span class="sxs-lookup"><span data-stu-id="1d089-162">Peer-to-peer HD quality video calling with resolution of HD 1080p at 30fps</span></span> |
|<span data-ttu-id="1d089-163">500kbps/1Mbps</span><span class="sxs-lookup"><span data-stu-id="1d089-163">500kbps/1Mbps</span></span> |<span data-ttu-id="1d089-164">Grupo de chamada de vídeo</span><span class="sxs-lookup"><span data-stu-id="1d089-164">Group Video calling</span></span> |
|<span data-ttu-id="1d089-165">1Mbps/2Mbps</span><span class="sxs-lookup"><span data-stu-id="1d089-165">1Mbps/2Mbps</span></span> |<span data-ttu-id="1d089-166">Grupo de HD vídeo chamar (vídeos de 540p na tela 1080p)</span><span class="sxs-lookup"><span data-stu-id="1d089-166">HD Group video calling (540p videos on 1080p screen)</span></span> |

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

<a name="additional-network-considerations"></a><span data-ttu-id="1d089-167">Considerações de rede adicionais</span><span class="sxs-lookup"><span data-stu-id="1d089-167">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="1d089-168">Resolução de nome externo</span><span class="sxs-lookup"><span data-stu-id="1d089-168">External Name Resolution</span></span>

<span data-ttu-id="1d089-169">Certifique-se de que todos os computadores cliente executando o cliente de equipes podem resolver consultas DNS externas para descobrir os serviços fornecidos pelo Office 365 e que seus firewalls não estão impedindo o acesso.</span><span class="sxs-lookup"><span data-stu-id="1d089-169">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="1d089-170">Para obter informações sobre como configurar portas de firewall, vá para o [Office 365 URLs e intervalos IP](office-365-urls-ip-address-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="1d089-170">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="1d089-171">Tamanho do Pool NAT</span><span class="sxs-lookup"><span data-stu-id="1d089-171">NAT Pool Size</span></span>

<span data-ttu-id="1d089-172">Quando vários dispositivos/usuários acessam o Office 365 usando a conversão de endereço de rede (NAT) ou Port Address Translation (PAT), você precisará garantir que os dispositivos ocultos por trás de cada endereço IP roteável publicamente exceder o número com suporte.</span><span class="sxs-lookup"><span data-stu-id="1d089-172">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="1d089-173">Para atenuar esse risco, certifique-se de adequada endereços de IP públicos são atribuídos para os pools NAT para evitar o esgotamento de porta.</span><span class="sxs-lookup"><span data-stu-id="1d089-173">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="1d089-174">Esgotamento de porta fará com que os usuários finais internos e dispositivos enfrentando problemas ao conectar-se aos serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1d089-174">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="1d089-175">Para obter mais informações, consulte [suporte a NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span><span class="sxs-lookup"><span data-stu-id="1d089-175">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="1d089-176">**Orientações de prevenção e detecção de invasão**</span><span class="sxs-lookup"><span data-stu-id="1d089-176">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="1d089-177">Se seu ambiente tiver um sistema de prevenção contra (IDS/IPS) implantados para uma camada adicional de segurança para conexões de saída e/ou detecção de invasão, certifique-se de que nenhum tráfego com destino para URLs do Office 365 está na lista branca.</span><span class="sxs-lookup"><span data-stu-id="1d089-177">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="1d089-178">Determinação de integridade da rede</span><span class="sxs-lookup"><span data-stu-id="1d089-178">Network health determination</span></span>
-----------------

<span data-ttu-id="1d089-179">Quando planejar na implementação do Microsoft Teams dentro de sua rede, você deverá garantir você tem a largura de banda necessária, você tem acesso a todos os endereços IP necessários, as portas corretas estão abertas, e você está cumprindo os requisitos de desempenho para a mídia em tempo real .</span><span class="sxs-lookup"><span data-stu-id="1d089-179">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="1d089-180">Se você souber que você não atenderá a esses critérios, os usuários finais não obterá uma experiência ideal de equipes devido à qualidade ruim durante as reuniões e chamadas.</span><span class="sxs-lookup"><span data-stu-id="1d089-180">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="1d089-181">Deve você não atender a esses critérios, este é um tempo para considerar pausando o projeto para garantir que atendam aos critérios antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1d089-181">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="1d089-183">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="1d089-183">Decision Point</span></span>         |<span data-ttu-id="1d089-184">Você avaliou os recursos de rede para dar suporte a mídia de tempo real?</span><span class="sxs-lookup"><span data-stu-id="1d089-184">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="1d089-185">Se sua rede não foi avaliada corretamente ou se você sabe que ele não dará suporte a mídia de tempo real, você desativará vídeo e recursos para reduzir o impacto na rede e baixa experiências de equipes de compartilhamento de tela?</span><span class="sxs-lookup"><span data-stu-id="1d089-185">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![Ícone de próximos passos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="1d089-187">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="1d089-187">Next Steps</span></span>         |<span data-ttu-id="1d089-188">Qualidade de rede desconhecido: siga as orientações de [Avaliação de prontidão de rede](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) para determinar se a sua rede está pronta para a mídia de Tempo Real.</span><span class="sxs-lookup"><span data-stu-id="1d089-188">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="1d089-189">Baixa qualidade de rede: Execute etapas de atualização de rede para fornecer um ambiente adequado para alta qualidade de mídia de Tempo Real.</span><span class="sxs-lookup"><span data-stu-id="1d089-189">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="1d089-190">Satisfatório de rede: Verifique se todas as portas e endereços IP estão adequadamente acessíveis.</span><span class="sxs-lookup"><span data-stu-id="1d089-190">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="1d089-191">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="1d089-191">Related Topics</span></span>

[<span data-ttu-id="1d089-192">Vídeo: Planejamento de rede</span><span class="sxs-lookup"><span data-stu-id="1d089-192">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
