---
title: Adicionar IP NAT de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: O endereço IP público é o endereço IP usado pela NAT (conversão de endereços de rede). O endereço IP deve ser roteável publicamente. Isso é necessário porque você selecionou o endereço IP externo desse pool de bordas é convertido pela opção NAT na página Selecionar recursos deste assistente.
ms.openlocfilehash: 988b585145b6607002b6de0aafffbdc95b9c54c6
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798168"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="55a4b-105">Adicionar IP NAT de Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="55a4b-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="55a4b-106">O endereço IP público é o endereço IP usado pela NAT (conversão de endereços de rede).</span><span class="sxs-lookup"><span data-stu-id="55a4b-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="55a4b-107">O endereço IP deve ser roteável publicamente.</span><span class="sxs-lookup"><span data-stu-id="55a4b-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="55a4b-108">Isso é necessário porque você selecionou **o endereço IP externo desse pool de bordas é convertido pela opção NAT** na página **selecionar recursos** deste assistente.</span><span class="sxs-lookup"><span data-stu-id="55a4b-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="55a4b-109">A NAT (conversão de endereços de rede) permite que clientes ou servidores em uma rede privada (por exemplo, o intervalo 192.168.0.0) se comuniquem com sistemas em redes remotas por meio das redes públicas da Internet.</span><span class="sxs-lookup"><span data-stu-id="55a4b-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="55a4b-110">O NAT funciona usando um único endereço IP público em uma interface externa e associando endereços IP internos a um endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="55a4b-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="55a4b-111">O mapeamento NAT mapeia um endereço interno para o endereço IP público externo.</span><span class="sxs-lookup"><span data-stu-id="55a4b-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="55a4b-112">O sistema remoto vê apenas o endereço público da fonte.</span><span class="sxs-lookup"><span data-stu-id="55a4b-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="55a4b-113">O sistema remoto responde à fonte, e a origem se refere ao mapa NAT para determinar a qual endereço IP interno a resposta deve ser retornada.</span><span class="sxs-lookup"><span data-stu-id="55a4b-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="55a4b-p104">É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior. Para obter detalhes sobre como incluir Servidores de Borda na topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação de Implantação do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="55a4b-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


