---
title: Solucionar problemas de conectividade do cliente Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Solucione problemas de conectividade do cliente Microsoft Teams causados principalmente pelo firewall ou pela conexão do proxy, e saiba como corrigi-los.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d208671415e44ca5ec83313d0d8af666534f2b20
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30872698"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="29f89-103">Solucionar problemas de conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29f89-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="29f89-104">A maioria dos problemas descobertos com o cliente Microsoft Teams pode ser remetida para o firewall ou para a conectividade do proxy.</span><span class="sxs-lookup"><span data-stu-id="29f89-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="29f89-105">Verificar se as URLs, os endereços IP e as portas necessárias estão abertas no seu firewall ou no seu proxy minimizará uma resolução de problemas desnecessária.</span><span class="sxs-lookup"><span data-stu-id="29f89-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="29f89-106">Para obter informações específicas sobre URLs e IPs necessário for Microsoft Teams, consulte as [URLs do Office 365 e o endereço IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) artigo de suporte.</span><span class="sxs-lookup"><span data-stu-id="29f89-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="29f89-107">Os cenários a seguir exigem que portas e URLs específicas sejam abertas no firewall.</span><span class="sxs-lookup"><span data-stu-id="29f89-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="29f89-108">Autenticação</span><span class="sxs-lookup"><span data-stu-id="29f89-108">Authentication</span></span>

-   <span data-ttu-id="29f89-109">Conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29f89-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="29f89-110">Colaboração</span><span class="sxs-lookup"><span data-stu-id="29f89-110">Collaboration</span></span>

-   <span data-ttu-id="29f89-111">Mídia</span><span class="sxs-lookup"><span data-stu-id="29f89-111">Media</span></span>

-   <span data-ttu-id="29f89-112">Serviços compartilhados</span><span class="sxs-lookup"><span data-stu-id="29f89-112">Shared Services</span></span>

-   <span data-ttu-id="29f89-113">Integração de terceiros</span><span class="sxs-lookup"><span data-stu-id="29f89-113">Third Party Integration</span></span>

-   <span data-ttu-id="29f89-114">Interoperabilidade do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="29f89-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="29f89-115">Interoperabilidade do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="29f89-115">Skype for Business Client Interoperability</span></span>
