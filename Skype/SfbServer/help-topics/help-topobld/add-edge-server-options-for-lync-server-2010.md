---
title: Adicionar Opções de Servidor de Borda para o Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Você define um novo pool de Borda ou Servidor de Borda e tem a oportunidade de definir recursos para o novo servidor ou pool. As opções possíveis são:'
ms.openlocfilehash: dfc8238bbbe4899f9819118a11fc11ba47fe21f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119800"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="05819-104">Adicionar Opções de Servidor de Borda para o Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="05819-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="05819-105">Você define um novo pool de Borda ou Servidor de Borda e tem a oportunidade de definir recursos para o novo servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="05819-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="05819-106">As opções possíveis são:</span><span class="sxs-lookup"><span data-stu-id="05819-106">The options that you can choose are:</span></span>

- <span data-ttu-id="05819-107">**Usar um único FQDN e endereço IP**: marque a caixa de seleção para usar um único endereço IPv4 ou IPv6 (se você escolher usar IPv4 e IPv6, será necessário definir um de cada tipo de endereço IP) e nome de domínio totalmente qualificado (FQDN) para as interfaces de Borda externas.</span><span class="sxs-lookup"><span data-stu-id="05819-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="05819-108">Se você escolher essa opção, usará somente um endereço IP ou um IPv4 e um IPv6, mas deverá atribuir números de porta diferentes a cada interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="05819-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="05819-109">**Habilitar federação (porta 5061)**: marque essa caixa de seleção se for federar com outras federações SIP, provedores ou ofertas hospedadas que usam o protocolo de início de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="05819-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="05819-110">O endereço IP externo deste pool de Borda é convertido por **NAT**: marque essa caixa de seleção se você usar endereços IP privados para as interfaces externas de Borda e fornecerá um dispositivo NAT (conversão de endereço de rede) para colocar o Servidor de Borda ou pool de Borda logicamente para trás.</span><span class="sxs-lookup"><span data-stu-id="05819-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="05819-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="05819-111">See also</span></span>

[<span data-ttu-id="05819-112">Planejando o acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="05819-112">Planning for External User Access</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[<span data-ttu-id="05819-113">Implantação de acesso de usuários externos</span><span class="sxs-lookup"><span data-stu-id="05819-113">Deploying External User Access</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)