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
ms.openlocfilehash: 8056758fc707c53b780843f2fc25123b92f6e252
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136481"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="19964-103">URLs e intervalos de endereço IP do Office 365 </span><span class="sxs-lookup"><span data-stu-id="19964-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="19964-104">Vá para [ URLs do Office 365 e intervalos de endereço IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)para obter uma lista detalhada e atualizada das URLs, dos endereços IP, das portas e dos protocolos que precisam ser configurados corretamente para o Teams.</span><span class="sxs-lookup"><span data-stu-id="19964-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="19964-105">A Microsoft está aprimorando continuamente o serviço do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo.</span><span class="sxs-lookup"><span data-stu-id="19964-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="19964-106">Recomendamos que você [se inscreva via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando essas informações forem atualizadas ou alteradas.</span><span class="sxs-lookup"><span data-stu-id="19964-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="19964-107">O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="19964-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="19964-108">Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="19964-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="19964-109">Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="19964-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="19964-110">Para todas as cargas de trabalho do Office 365, o método de conexão recomendado para os serviços do Teams é o desvio do proxy direto sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="19964-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="19964-111">Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia.</span><span class="sxs-lookup"><span data-stu-id="19964-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="19964-112">Baixe um exemplo de arquivos PAC do proxy que podem ser utilizados para configurar o desvio de tráfego em [Gerenciamento dos pontos de extremidade do Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span><span class="sxs-lookup"><span data-stu-id="19964-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="19964-113">Se as suas políticas de rede e segurança exigirem o tráfego do Office 365 fluir por meio de um servidor proxy, verifique se os requisitos acima já foram atendidos antes de implantar equipes em produção.</span><span class="sxs-lookup"><span data-stu-id="19964-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="19964-114">Para obter mais informações, leia [servidores proxy para Teams ou Skype for Business online](proxy-servers-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="19964-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
