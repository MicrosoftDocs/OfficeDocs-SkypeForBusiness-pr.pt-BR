---
title: Adicionar Opções de IP de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'O Skype for Business Server permite configurar endereços IPv4 e IPv6 para cada interface do servidor de borda e do pool de bordas. Para fazer isso, faça o seguinte:'
ms.openlocfilehash: 8352826fff371e4d59a4cf915d034465ac1aee7f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703046"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="69990-104">Adicionar Opções de IP de Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="69990-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="69990-105">O Skype for Business Server permite configurar endereços IPv4 e IPv6 para cada interface do servidor de borda e do pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="69990-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="69990-106">Para fazer isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="69990-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="69990-107">**Habilitar IPv4 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface interna do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="69990-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="69990-108">**Habilitar o IPv6 na interface interna**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface interna do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="69990-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="69990-109">**Habilitar IPv4 na interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv4 à interface externa do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="69990-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="69990-110">**Habilitar o IPv6 em uma interface externa**: marque a caixa de seleção se desejar aplicar um endereço IPv6 à interface externa do servidor de borda ou do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="69990-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="69990-111">Você também pode configurar o servidor de borda ou o pool de bordas para usar um endereço de conversão de endereços de rede para os endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="69990-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="69990-112">Para fazer isso, marque a caixa de seleção **o endereço IP externo deste pool de bordas é convertido pela NAT**.</span><span class="sxs-lookup"><span data-stu-id="69990-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="69990-113">Suporte a NAT.</span><span class="sxs-lookup"><span data-stu-id="69990-113">NAT support.</span></span> <span data-ttu-id="69990-114">Não há suporte para a conversão de endereços de rede (NAT) quando você está usando o balanceamento de carga de hardware, portanto, não selecione a opção NAT se você estiver implantando um pool do servidor de borda com balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="69990-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

