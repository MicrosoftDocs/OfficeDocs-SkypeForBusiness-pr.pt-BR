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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Você define um novo servidor de borda ou um novo pool de bordas e é apresentado à oportunidade de definir recursos para o novo servidor ou pool. As opções que você pode escolher são:'
ms.openlocfilehash: 953aa6c0bcb5d5bf65f0ba649545aef909d3b647
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698356"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="24eb4-104">Adicionar Opções de Servidor de Borda para o Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="24eb4-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="24eb4-105">Você define um novo servidor de borda ou um novo pool de bordas e é apresentado à oportunidade de definir recursos para o novo servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="24eb4-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="24eb4-106">As opções que você pode escolher são:</span><span class="sxs-lookup"><span data-stu-id="24eb4-106">The options that you can choose are:</span></span>

- <span data-ttu-id="24eb4-107">**Use um único FQDN e endereço IP**: marque a caixa de seleção para usar um único IPv4 ou IPv6 (se optar por usar IPv4 e IPv6, você precisará definir um endereço de cada tipo de endereço IP) e um FQDN (nome de domínio totalmente qualificado) para as interfaces de borda externa.</span><span class="sxs-lookup"><span data-stu-id="24eb4-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="24eb4-108">Se você escolher essa opção, usará apenas um endereço IP ou um IPv4 e um IPv6, mas deverá atribuir números de porta diferentes para cada interface de borda.</span><span class="sxs-lookup"><span data-stu-id="24eb4-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="24eb4-109">**Habilitar Federação (porta 5061)**: Marque esta caixa de seleção se você fizer a Federação com outras federações, provedores ou ofertas hospedadas do SIP que usam o protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="24eb4-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="24eb4-110">**O endereço IP externo deste pool de bordas é traduzido por Nat**: Marque esta caixa de seleção se você usar endereços IP particulares para as interfaces externas de borda e fornecerá um dispositivo NAT (conversão de endereços de rede) para colocar o servidor de borda ou o pool de bordas logicamente atrás.</span><span class="sxs-lookup"><span data-stu-id="24eb4-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="24eb4-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="24eb4-111">See also</span></span>

[<span data-ttu-id="24eb4-112">Planejando o acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="24eb4-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="24eb4-113">Implantando o acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="24eb4-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
