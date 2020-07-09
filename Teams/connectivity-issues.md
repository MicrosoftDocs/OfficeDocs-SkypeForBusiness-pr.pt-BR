---
title: Solucionar problemas de conectividade com o cliente do teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Solucione problemas de conectividade do cliente Microsoft Teams causados principalmente pelo firewall ou pela conexão do proxy, e saiba como corrigi-los.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 116ce1afef08a6f1639ed011b799f9ca43ea57f5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085227"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="23325-103">Solucionar problemas de conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23325-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="23325-104">A maioria dos problemas descobertos com o cliente Microsoft Teams pode ser remetida para o firewall ou para a conectividade do proxy.</span><span class="sxs-lookup"><span data-stu-id="23325-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="23325-105">Verificar se as URLs, os endereços IP e as portas necessárias estão abertas no seu firewall ou no seu proxy minimizará uma resolução de problemas desnecessária.</span><span class="sxs-lookup"><span data-stu-id="23325-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="23325-106">Para obter informações específicas sobre URLs e IPs necessários para o Microsoft Teams, consulte o artigo [microsoft 365 and Office 365 URLs and IP address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support.</span><span class="sxs-lookup"><span data-stu-id="23325-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="23325-107">Os cenários a seguir exigem que portas e URLs específicas sejam abertas no firewall.</span><span class="sxs-lookup"><span data-stu-id="23325-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="23325-108">Autenticação</span><span class="sxs-lookup"><span data-stu-id="23325-108">Authentication</span></span>

-   <span data-ttu-id="23325-109">Conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="23325-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="23325-110">Colaboração</span><span class="sxs-lookup"><span data-stu-id="23325-110">Collaboration</span></span>

-   <span data-ttu-id="23325-111">Mídia</span><span class="sxs-lookup"><span data-stu-id="23325-111">Media</span></span>

-   <span data-ttu-id="23325-112">Serviços Compartilhados</span><span class="sxs-lookup"><span data-stu-id="23325-112">Shared Services</span></span>

-   <span data-ttu-id="23325-113">Integração de terceiros</span><span class="sxs-lookup"><span data-stu-id="23325-113">Third Party Integration</span></span>

-   <span data-ttu-id="23325-114">Interoperabilidade do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="23325-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="23325-115">Interoperabilidade do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="23325-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="23325-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="23325-116">Related topics</span></span>

[<span data-ttu-id="23325-117">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="23325-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)