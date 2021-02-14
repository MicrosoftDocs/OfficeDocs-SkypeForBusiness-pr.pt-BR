---
title: Adicionar Opções de IP de Servidor de Borda
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'O Skype for Business Server permite configurar endereços IPv4 e IPv6 para cada interface para o Servidor de Borda e o pool de Borda. Para fazer isso, faça o seguinte:'
ms.openlocfilehash: f940e0480c51b1a2541386401a71f0d7d9818566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801071"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="69268-104">Adicionar Opções de IP de Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="69268-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="69268-105">O Skype for Business Server permite configurar endereços IPv4 e IPv6 para cada interface para o Servidor de Borda e o pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="69268-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="69268-106">Para fazer isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="69268-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="69268-107">**Habilitar IPv4 na interface** interna: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface interna do Servidor de Borda ou do pool de Borda</span><span class="sxs-lookup"><span data-stu-id="69268-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="69268-108">**Habilitar IPv6 na interface** interna: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface interna do Servidor de Borda ou do pool de Borda</span><span class="sxs-lookup"><span data-stu-id="69268-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="69268-109">**Habilitar IPv4 na interface** externa: marque a caixa de seleção se quiser aplicar um endereço IPv4 à interface externa do Servidor de Borda ou do pool de Borda</span><span class="sxs-lookup"><span data-stu-id="69268-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="69268-110">**Habilitar IPv6 na interface** externa: marque a caixa de seleção se quiser aplicar um endereço IPv6 à interface externa do Servidor de Borda ou do pool de Borda</span><span class="sxs-lookup"><span data-stu-id="69268-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="69268-111">Você também pode configurar o Servidor de Borda ou pool de Borda para usar um endereço de conversão de endereço de rede para os endereços IP externos.</span><span class="sxs-lookup"><span data-stu-id="69268-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="69268-112">Faça isso marcando a caixa de seleção **O endereço IP externo deste pool de Borda é convertido pelo NAT**.</span><span class="sxs-lookup"><span data-stu-id="69268-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="69268-p104">Suporte a NAT. NAT (Conversão de endereço de rede) não é suportado quando você está usando balanceamento de carga de hardware. Portanto, não selecione a opção NAT se estiver implantando um pool de Servidor de Borda com balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="69268-p104">NAT support. Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

