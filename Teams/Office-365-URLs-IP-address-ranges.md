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
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23889540"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="a2398-103">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="a2398-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="a2398-104">Vá para o [Office 365 URLs e intervalos de endereços IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) para uma lista detalhada e atualizada de URLs, endereços IP, portas e protocolos que devem estar corretamente configurados para equipes.</span><span class="sxs-lookup"><span data-stu-id="a2398-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="a2398-105">A Microsoft está continuamente aperfeiçoando o serviço Office 365 e adicionar a nova funcionalidade, que significa que as portas necessárias, URLs, e endereços IP podem mudar ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="a2398-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="a2398-106">Recomendamos que você [Inscreva-se via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando esta informação é atualizada ou alterada.</span><span class="sxs-lookup"><span data-stu-id="a2398-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="a2398-107">As equipes a experiência de chamada e reuniões é baseada da próxima geração baseado em nuvem de infra-estrutura que também é usada pelo Skype e Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="a2398-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="a2398-108">Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="a2398-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="a2398-109">Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a2398-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="a2398-110">Para todas as cargas de trabalho do Office 365, o método recomendado de conexão aos serviços de equipes é ignorando o proxy de encaminhamento onde for possível.</span><span class="sxs-lookup"><span data-stu-id="a2398-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="a2398-111">Quando um servidor proxy fica entre um cliente e os centros de dados do Office 365, mídia será forçada sobre TCP em vez de UDP, que afetaria qualidade de mídia.</span><span class="sxs-lookup"><span data-stu-id="a2398-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="a2398-112">Baixe arquivos de PAC de proxy de amostra que podem ser usados para configurar o bypass de tráfego de [pontos de extremidade de gerenciamento do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="a2398-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="a2398-113">Se suas políticas de segurança e rede exigem o tráfego do Office 365 para fluem através de um servidor proxy, certifique-se de que os requisitos acima já sejam atendidos antes de implantar equipes em produção (revise [Servidores Proxy para Skype para Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) para orientação).</span><span class="sxs-lookup"><span data-stu-id="a2398-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) for guidance).</span></span>
