---
title: Adicionar Opções de IP de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 permite que você configure endereços IPv4 e IPv6 para cada interface para o servidor de borda e o pool de borda. Para fazer isso, faça o seguinte:'
ms.openlocfilehash: 3a9f11686d27d8b289de52df8541fa686f11d3af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886329"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="80156-104">Adicionar Opções de IP de Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="80156-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="80156-105">Microsoft Lync Server 2013 permite que você configure endereços IPv4 e IPv6 para cada interface para o servidor de borda e o pool de borda.</span><span class="sxs-lookup"><span data-stu-id="80156-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="80156-106">Para fazer isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="80156-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="80156-107">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 para o servidor de borda ou a interface interna do pool de borda</span><span class="sxs-lookup"><span data-stu-id="80156-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="80156-108">**Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 para o servidor de borda ou a interface interna do pool de borda</span><span class="sxs-lookup"><span data-stu-id="80156-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="80156-109">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 para o servidor de borda ou a interface externa do pool de borda</span><span class="sxs-lookup"><span data-stu-id="80156-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="80156-110">**Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 para o servidor de borda ou a interface externa do pool de borda</span><span class="sxs-lookup"><span data-stu-id="80156-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="80156-111">Você também pode configurar o servidor de borda ou pool de borda para usar um endereço de conversão de endereço de rede para os endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="80156-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="80156-112">Você pode fazer isso marcando a caixa de seleção, **o endereço IP externo deste pool de borda é convertido por NAT**.</span><span class="sxs-lookup"><span data-stu-id="80156-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="80156-113">Suporte NAT.</span><span class="sxs-lookup"><span data-stu-id="80156-113">NAT support.</span></span> <span data-ttu-id="80156-114">Conversão de endereço de rede (NAT) não é suportado quando você estiver usando hardware balanceamento de carga, portanto, não marque a opção NAT se você estiver implantando um pool do servidor de borda com balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="80156-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

