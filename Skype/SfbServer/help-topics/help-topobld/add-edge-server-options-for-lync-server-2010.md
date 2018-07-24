---
title: Adicionar opções de servidor de borda do Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Você pode define um novo servidor de borda ou pool de borda e é apresentados a oportunidade de definir os recursos para o novo servidor ou pool. As opções que você pode escolher são:'
ms.openlocfilehash: 7cd5af525e87f23bc07245f5fed139bc2c9c7356
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967618"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="f7569-104">Adicionar opções de servidor de borda do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f7569-104">Add Edge Server Options for Lync Server 2010</span></span>
 
<span data-ttu-id="f7569-105">Você pode define um novo servidor de borda ou pool de borda e é apresentados a oportunidade de definir os recursos para o novo servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="f7569-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="f7569-106">As opções que você pode escolher são:</span><span class="sxs-lookup"><span data-stu-id="f7569-106">The options that you can choose are:</span></span>
  
- <span data-ttu-id="f7569-107">**Use um único endereço IP e FQDN**: marque a caixa de seleção usar um único IPv4 ou IPv6 (se você optar por usar o IPv4 e IPv6, e em seguida, você precisará defini-la de cada tipo de endereço IP) endereço e o nome domínio totalmente qualificado (FQDN) do External interfaces de borda.</span><span class="sxs-lookup"><span data-stu-id="f7569-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f7569-108">Se você escolher essa opção, você usará somente um endereço IP, ou um IPv4 e um IPv6, mas você deve atribuir números de porta diferentes para cada interface de borda.</span><span class="sxs-lookup"><span data-stu-id="f7569-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span> 
  
- <span data-ttu-id="f7569-109">**Habilitar federação (porta 5061)**: marque essa caixa de seleção se for federar com outras federações SIP, provedores ou ofertas hospedadas que usam o protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="f7569-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>
    
- <span data-ttu-id="f7569-110">**O endereço IP externo deste pool de borda é convertido por NAT**: marque essa caixa de seleção se você usar endereços IP privados das interfaces externas de borda e fornecerá um dispositivo NAT (conversão) de endereço de rede para colocar o servidor de borda ou pool de borda logicamente atrás.</span><span class="sxs-lookup"><span data-stu-id="f7569-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f7569-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f7569-111">See also</span></span>

[<span data-ttu-id="f7569-112">Planejando o acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="f7569-112">Planning for External User Access</span></span>](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)
  
[<span data-ttu-id="f7569-113">Implantando o acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="f7569-113">Deploying External User Access</span></span>](http://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)