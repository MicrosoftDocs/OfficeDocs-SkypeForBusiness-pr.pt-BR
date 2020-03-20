---
title: Solucionar problemas de conectividade do cliente Microsoft Teams
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
ms.openlocfilehash: a12be097d0609f3631b6761f31350603b283faa2
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825349"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="d6cab-103">Solucionar problemas de conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6cab-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="d6cab-104">A maioria dos problemas descobertos com o cliente Microsoft Teams pode ser remetida para o firewall ou para a conectividade do proxy.</span><span class="sxs-lookup"><span data-stu-id="d6cab-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="d6cab-105">Verificar se as URLs, os endereços IP e as portas necessárias estão abertas no seu firewall ou no seu proxy minimizará uma resolução de problemas desnecessária.</span><span class="sxs-lookup"><span data-stu-id="d6cab-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="d6cab-106">Para obter informações específicas das URLs e dos Ips exigidos pelo Microsoft Teams, confira o artigo de suporte [URLs e Endereços IP do Office 365 ](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="d6cab-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="d6cab-107">Os cenários a seguir exigem que portas e URLs específicas sejam abertas no firewall.</span><span class="sxs-lookup"><span data-stu-id="d6cab-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="d6cab-108">Autenticação</span><span class="sxs-lookup"><span data-stu-id="d6cab-108">Authentication</span></span>

-   <span data-ttu-id="d6cab-109">Conectividade do cliente Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6cab-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="d6cab-110">Colaboração</span><span class="sxs-lookup"><span data-stu-id="d6cab-110">Collaboration</span></span>

-   <span data-ttu-id="d6cab-111">Mídia</span><span class="sxs-lookup"><span data-stu-id="d6cab-111">Media</span></span>

-   <span data-ttu-id="d6cab-112">Serviços Compartilhados</span><span class="sxs-lookup"><span data-stu-id="d6cab-112">Shared Services</span></span>

-   <span data-ttu-id="d6cab-113">Integração de terceiros</span><span class="sxs-lookup"><span data-stu-id="d6cab-113">Third Party Integration</span></span>

-   <span data-ttu-id="d6cab-114">Interoperabilidade do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d6cab-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="d6cab-115">Interoperabilidade do cliente Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d6cab-115">Skype for Business Client Interoperability</span></span>
