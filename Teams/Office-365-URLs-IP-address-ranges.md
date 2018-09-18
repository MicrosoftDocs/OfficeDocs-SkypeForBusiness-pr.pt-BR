---
title: URLs e intervalos de endereços IP do Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Saiba como configurar corretamente URLs do Office 365 e intervalos de endereços IP, desviar o proxy direto quando estiver disponível para conexões com o serviço Microsoft Teams e as exigências das políticas de rede e segurança.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fddcd7a43b6296172b3bac0a7aad31032a585618
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23889540"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="ef8ec-103">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="ef8ec-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="ef8ec-104">Vá para [ URLs do Office 365 e intervalos de endereço IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)para obter uma lista detalhada e atualizada das URLs, dos endereços IP, das portas e dos protocolos que precisam ser configurados corretamente para o Teams.</span><span class="sxs-lookup"><span data-stu-id="ef8ec-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="ef8ec-105">A Microsoft está aprimorando continuamente o serviço do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="ef8ec-105">Microsoft is continuously improving the Office 365 service and adding new functionalities, therefore the required ports, URLs and IP addresses may change over time.</span></span> <span data-ttu-id="ef8ec-106">Recomendamos que você [se inscreva via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando essas informações forem atualizadas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="ef8ec-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="ef8ec-107">O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ef8ec-107">Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="ef8ec-108">Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="ef8ec-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="ef8ec-109">Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ef8ec-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="ef8ec-110">Para todas as cargas de trabalho do Office 365, o método de conexão recomendado para os serviços do Teams é o desvio do proxy direto sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="ef8ec-110">For all Office 365 workloads, the recommended connection method to Microsoft Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="ef8ec-111">Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia.</span><span class="sxs-lookup"><span data-stu-id="ef8ec-111">When a proxy server sits between a client and the Office 365 datacenters, media might be forced over TCP instead of UDP, that would impact media quality.</span></span> <span data-ttu-id="ef8ec-112">Baixe um exemplo de arquivos PAC do proxy que podem ser utilizados para configurar o desvio de tráfego em [Gerenciamento dos pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="ef8ec-112">A sample proxy PAC files that can be used to configure traffic bypass can be downloaded from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) guide.</span></span>

<span data-ttu-id="ef8ec-113">Se suas políticas de rede e segurança exigirem que o tráfego do Office 365 flua através de um servidor proxy, certifique-se de que as exigências acima estejam cumpridas antes de colocar o Teams em produção (veja [Servidores Proxy para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) para obter orientações.)</span><span class="sxs-lookup"><span data-stu-id="ef8ec-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, then make sure that the above requirements are already met before deploying Microsoft Teams into production (review [Proxy Servers for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) for guidance.)</span></span>
