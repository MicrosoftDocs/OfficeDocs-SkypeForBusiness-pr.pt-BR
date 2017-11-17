---
title: Solucionar problemas de conectividade do cliente Microsoft Teams | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Solucione problemas de conectividade do cliente Microsoft Teams causados principalmente pelo firewall ou pela conexão do proxy, e saiba como corrigi-los."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: fdba24620fca80b12b4e86780b19203436e7c9f4
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2017
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="b2ce3-103">Solucionar problemas de conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2ce3-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="b2ce3-104">A maioria dos problemas descobertos com o cliente Microsoft Teams pode ser remetida para o firewall ou para a conectividade do proxy.</span><span class="sxs-lookup"><span data-stu-id="b2ce3-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="b2ce3-105">Verificar se as URLs, os endereços IP e as portas necessárias estão abertas no seu firewall ou no seu proxy minimizará uma resolução de problemas desnecessária.</span><span class="sxs-lookup"><span data-stu-id="b2ce3-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="b2ce3-106">Para obter informações específicas das URLs e dos Ips exigidos pelo Microsoft Teams, consulte [o artigo de suporte URLs e Endereços IP
do Office 365 ](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams).</span><span class="sxs-lookup"><span data-stu-id="b2ce3-106">For specific information on URLs and IPs required for Microsoft Teams, please reference the [Office 365 URLs and IP Address](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams) support article.</span></span> <span data-ttu-id="b2ce3-107">Os cenários a seguir exigem que portas e URLs específicas sejam abertas no firewall.</span><span class="sxs-lookup"><span data-stu-id="b2ce3-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="b2ce3-108">Autenticação</span><span class="sxs-lookup"><span data-stu-id="b2ce3-108">Authentication</span></span>

-   <span data-ttu-id="b2ce3-109">Conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2ce3-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="b2ce3-110">Colaboração</span><span class="sxs-lookup"><span data-stu-id="b2ce3-110">collaboration</span></span>

-   <span data-ttu-id="b2ce3-111">Mídia</span><span class="sxs-lookup"><span data-stu-id="b2ce3-111">Media</span></span>

-   <span data-ttu-id="b2ce3-112">Serviços compartilhados</span><span class="sxs-lookup"><span data-stu-id="b2ce3-112">Shared Services</span></span>

-   <span data-ttu-id="b2ce3-113">Integração de terceiros</span><span class="sxs-lookup"><span data-stu-id="b2ce3-113">Third Party Integration</span></span>

-   <span data-ttu-id="b2ce3-114">Interoperabilidade do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2ce3-114">Skype for Business</span></span>

-   <span data-ttu-id="b2ce3-115">Interoperabilidade do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b2ce3-115">Skype for Business Client Interoperability</span></span>
