---
title: 'URLs e intervalos de endereço IP do Office 365 '
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Saiba como configurar corretamente URLs do Office 365 e intervalos de endereços IP, desviar o proxy direto quando estiver disponível para conexões com o serviço Microsoft Teams e as exigências das políticas de rede e segurança.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5fc8d5bc41f7cf7a28140b30dd4a488c05b9b876
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "37563867"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="01ab1-103">URLs e intervalos de endereço IP do Office 365 </span><span class="sxs-lookup"><span data-stu-id="01ab1-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="01ab1-104">Vá para [ URLs do Office 365 e intervalos de endereço IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)para obter uma lista detalhada e atualizada das URLs, dos endereços IP, das portas e dos protocolos que precisam ser configurados corretamente para o Teams.</span><span class="sxs-lookup"><span data-stu-id="01ab1-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="01ab1-105">A Microsoft está aprimorando continuamente o serviço do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="01ab1-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="01ab1-106">Recomendamos que você [se inscreva via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando essas informações forem atualizadas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="01ab1-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="01ab1-107">O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="01ab1-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="01ab1-108">Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="01ab1-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="01ab1-109">Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="01ab1-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="01ab1-110">Para todas as cargas de trabalho do Office 365, o método de conexão recomendado para os serviços do Teams é o desvio do proxy direto sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="01ab1-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="01ab1-111">Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia.</span><span class="sxs-lookup"><span data-stu-id="01ab1-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="01ab1-112">Baixe um exemplo de arquivos PAC do proxy que podem ser utilizados para configurar o desvio de tráfego em [Gerenciamento dos pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="01ab1-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="01ab1-113">Se suas políticas de rede e segurança exigirem que o tráfego do Office 365 flua através de um servidor proxy, certifique-se de que as exigências acima estejam cumpridas antes de colocar o Teams em produção (confira [Servidores Proxy para o Skype for Business Online](proxy-servers-for-skype-for-business-online.md) para obter orientações.)</span><span class="sxs-lookup"><span data-stu-id="01ab1-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md) for guidance).</span></span>
