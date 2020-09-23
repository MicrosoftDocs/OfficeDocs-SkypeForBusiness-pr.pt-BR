---
title: Adicionar Opções de Servidor de Borda para o Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Você define um novo servidor de borda ou um pool de borda e é apresentado à oportunidade de definir recursos para o novo servidor ou pool. As opções possíveis são:'
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216592"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="2537e-104">Adicionar Opções de Servidor de Borda para o Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2537e-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="2537e-105">Você define um novo servidor de borda ou um pool de borda e é apresentado à oportunidade de definir recursos para o novo servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="2537e-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="2537e-106">As opções possíveis são:</span><span class="sxs-lookup"><span data-stu-id="2537e-106">The options that you can choose are:</span></span>

- <span data-ttu-id="2537e-107">**Usar um único FQDN e endereço IP**: marque a caixa de seleção para usar um único endereço IPv4 ou IPv6 (se você escolher usar IPv4 e IPv6, será necessário definir um de cada tipo de endereço IP) e nome de domínio totalmente qualificado (FQDN) para as interfaces de Borda externas.</span><span class="sxs-lookup"><span data-stu-id="2537e-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2537e-108">Se você escolher essa opção, usará somente um endereço IP ou um IPv4 e um IPv6, mas deverá atribuir números de porta diferentes a cada interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="2537e-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="2537e-109">**Habilitar federação (porta 5061)**: marque essa caixa de seleção se for federar com outras federações SIP, provedores ou ofertas hospedadas que usam o protocolo de início de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="2537e-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="2537e-110">**O endereço IP externo deste pool de borda é convertido pelo NAT**: Marque essa caixa de seleção se você usar endereços IP privados para as interfaces externas de borda e fornecerá um dispositivo NAT (conversão de endereço de rede) para colocar o servidor de borda ou o pool de borda logicamente atrás.</span><span class="sxs-lookup"><span data-stu-id="2537e-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="2537e-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="2537e-111">See also</span></span>

[<span data-ttu-id="2537e-112">Planejando o acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="2537e-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="2537e-113">Implantação de acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="2537e-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
