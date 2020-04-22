---
title: URLs e intervalos de endereços IP do Microsoft 365 e do Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Saiba como configurar corretamente as URLs e os intervalos de endereços IP do Office 365 e ignorar o proxy de encaminhamento quando possível para conexões com o Microsoft Teams Service.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 635ec9007e4cb4742b9076b15b89d32ad77a135f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778617"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="f1d7f-103">URLs e intervalos de endereços IP do Microsoft 365 e do Office 365</span><span class="sxs-lookup"><span data-stu-id="f1d7f-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="f1d7f-104">Acesse o [Microsoft 365 e os intervalos de endereços IP e URLs do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para obter uma lista detalhada e atualizada das URLs, endereços IP, portas e protocolos que devem ser configurados corretamente para o Teams.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="f1d7f-105">A Microsoft está aprimorando continuamente o serviço do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="f1d7f-106">Recomendamos que você [se inscreva via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando essas informações forem atualizadas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="f1d7f-107">O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="f1d7f-108">Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="f1d7f-109">Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="f1d7f-110">Para todas as cargas de trabalho do Office 365, o método de conexão recomendado para os serviços do Teams é o desvio do proxy direto sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="f1d7f-111">Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="f1d7f-112">Baixe os exemplos de arquivos PAC de proxy que podem ser usados para configurar [o bypass do gerenciamento de pontos de extremidade do Microsoft 365 e do Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span><span class="sxs-lookup"><span data-stu-id="f1d7f-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="f1d7f-113">Se as suas políticas de rede e segurança exigirem o tráfego do Office 365 fluir por meio de um servidor proxy, verifique se os requisitos acima já foram atendidos antes de implantar equipes em produção.</span><span class="sxs-lookup"><span data-stu-id="f1d7f-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="f1d7f-114">Para obter mais informações, leia [servidores proxy para Teams ou Skype for Business online](proxy-servers-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="f1d7f-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
