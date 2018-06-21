---
title: Adicionar opções de IP do servidor de borda
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 permite que você configure endereços IPv4 e IPv6 para cada interface para o servidor de borda e o pool de borda. Para fazer isso, faça o seguinte:'
ms.openlocfilehash: a303c4dc3d6fe82617449795507ef87017676a4a
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19974954"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="26f3b-104">Adicionar opções de IP do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="26f3b-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="26f3b-105">Microsoft Lync Server 2013 permite que você configure endereços IPv4 e IPv6 para cada interface para o servidor de borda e o pool de borda.</span><span class="sxs-lookup"><span data-stu-id="26f3b-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="26f3b-106">Para fazer isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="26f3b-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="26f3b-107">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv4 para o servidor de borda ou a interface interna do pool de borda</span><span class="sxs-lookup"><span data-stu-id="26f3b-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="26f3b-108">**Habilitar IPv6 na interface interna**: marque a caixa de seleção se quiser aplicar um endereço IPv6 para o servidor de borda ou a interface interna do pool de borda</span><span class="sxs-lookup"><span data-stu-id="26f3b-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="26f3b-109">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv4 para o servidor de borda ou a interface externa do pool de borda</span><span class="sxs-lookup"><span data-stu-id="26f3b-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="26f3b-110">**Habilitar IPv6 na interface externa**: marque a caixa de seleção se quiser aplicar um endereço IPv6 para o servidor de borda ou a interface externa do pool de borda</span><span class="sxs-lookup"><span data-stu-id="26f3b-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="26f3b-111">Você também pode configurar o servidor de borda ou pool de borda para usar um endereço de conversão de endereço de rede para os endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="26f3b-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="26f3b-112">Você pode fazer isso marcando a caixa de seleção, **o endereço IP externo deste pool de borda é convertido por NAT**.</span><span class="sxs-lookup"><span data-stu-id="26f3b-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="26f3b-113">Suporte NAT.</span><span class="sxs-lookup"><span data-stu-id="26f3b-113">NAT support.</span></span> <span data-ttu-id="26f3b-114">Conversão de endereço de rede (NAT) não é suportado quando você estiver usando hardware balanceamento de carga, portanto, não marque a opção NAT se você estiver implantando um pool do servidor de borda com balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="26f3b-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

