---
title: Adicionar Pool de Aplicativo Confiável
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir um nome de domínio totalmente qualificado do pool de aplicativos confiáveis (FQDN), especifique o seguinte:'
ms.openlocfilehash: 11331569e7db06fba6d7dc99529fe83ad3fe2ddd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888965"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="3c957-103">Adicionar Pool de Aplicativo Confiável</span><span class="sxs-lookup"><span data-stu-id="3c957-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="3c957-104">Para definir um nome de domínio totalmente qualificado do pool de aplicativos confiáveis (FQDN), especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3c957-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="3c957-105">Um FQDN do servidor ou pool de servidores que hospedará os aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="3c957-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="3c957-106">Se você estiver implantando um pool de servidores para os aplicativos confiáveis do balanceamento de carga e alta disponibilidade, ou selecione o **pool de computador único** se você não precisa carga balanceamento ou alta disponibilidade, selecione **pool de vários computadores** .</span><span class="sxs-lookup"><span data-stu-id="3c957-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3c957-107">Um único servidor de aplicativos confiáveis não puder ser convertido para um pool de servidores mais tarde.</span><span class="sxs-lookup"><span data-stu-id="3c957-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="3c957-108">Se você acha que talvez seja necessário um pool no futuro, você pode implantar um pool de servidores múltiplos que contém um único computador agora e adicionar servidores quando necessário.</span><span class="sxs-lookup"><span data-stu-id="3c957-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="3c957-109">Para obter detalhes sobre pools de aplicativos confiáveis, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3c957-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

