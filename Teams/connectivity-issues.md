---
title: Solucionar problemas de conectividade do cliente Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Solucione problemas de conectividade do cliente Microsoft Teams causados principalmente pelo firewall ou pela conexão do proxy, e saiba como corrigi-los.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5204c745da00535b0838d06a00709ffa31146a3e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461656"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="aec7e-103">Solucionar problemas de conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aec7e-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="aec7e-104">A maioria dos problemas descobertos com o cliente Microsoft Teams pode ser remetida para o firewall ou para a conectividade do proxy.</span><span class="sxs-lookup"><span data-stu-id="aec7e-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="aec7e-105">Verificar se as URLs, os endereços IP e as portas necessárias estão abertas no seu firewall ou no seu proxy minimizará uma resolução de problemas desnecessária.</span><span class="sxs-lookup"><span data-stu-id="aec7e-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="aec7e-106">Para obter informações específicas sobre URLs e IPs necessário for Microsoft Teams, consulte as [URLs do Office 365 e o endereço IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) artigo de suporte.</span><span class="sxs-lookup"><span data-stu-id="aec7e-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="aec7e-107">Os cenários a seguir exigem que portas e URLs específicas sejam abertas no firewall.</span><span class="sxs-lookup"><span data-stu-id="aec7e-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="aec7e-108">Autenticação</span><span class="sxs-lookup"><span data-stu-id="aec7e-108">Authentication</span></span>

-   <span data-ttu-id="aec7e-109">Conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aec7e-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="aec7e-110">Colaboração</span><span class="sxs-lookup"><span data-stu-id="aec7e-110">Collaboration</span></span>

-   <span data-ttu-id="aec7e-111">Mídia</span><span class="sxs-lookup"><span data-stu-id="aec7e-111">Media</span></span>

-   <span data-ttu-id="aec7e-112">Serviços compartilhados</span><span class="sxs-lookup"><span data-stu-id="aec7e-112">Shared Services</span></span>

-   <span data-ttu-id="aec7e-113">Integração de terceiros</span><span class="sxs-lookup"><span data-stu-id="aec7e-113">Third Party Integration</span></span>

-   <span data-ttu-id="aec7e-114">Interoperabilidade do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aec7e-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="aec7e-115">Interoperabilidade do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aec7e-115">Skype for Business Client Interoperability</span></span>
