---
title: Adicionar IP de NAT de servidor de borda
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: O endereço IP público é o endereço IP que é usado pelo conversão de endereço de rede (NAT). O endereço IP deverá ser roteável publicamente. Isso é necessário porque você selecionou o endereço IP externo desse pool é convertido em + pela opção de NAT na página Selecionar recursos deste assistente de borda.
ms.openlocfilehash: 034367d42d4ef698315f128e840123295e8fd694
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23257476"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="ed079-105">Adicionar IP de NAT de servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ed079-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="ed079-106">O endereço IP público é o endereço IP que é usado pelo conversão de endereço de rede (NAT).</span><span class="sxs-lookup"><span data-stu-id="ed079-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="ed079-107">O endereço IP deverá ser roteável publicamente.</span><span class="sxs-lookup"><span data-stu-id="ed079-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="ed079-108">Isso é necessário porque você selecionou a opção **o endereço IP externo deste pool de borda é convertido por NAT** na página **Selecionar recursos** deste assistente.</span><span class="sxs-lookup"><span data-stu-id="ed079-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="ed079-109">Conversão de endereço de rede (NAT) permite que os clientes ou servidores em uma rede privada (por exemplo, 192.168.0.0 intervalo) para se comunicar com sistemas em redes remotas através de redes públicas de Internet.</span><span class="sxs-lookup"><span data-stu-id="ed079-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="ed079-110">NAT funciona usando um único endereço IP público em uma interface externa e endereços IP internos como associar o um endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="ed079-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="ed079-111">Mapeamento de NAT mapeia um endereço interno para o endereço IP público externo.</span><span class="sxs-lookup"><span data-stu-id="ed079-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="ed079-112">O sistema remoto vê apenas o endereço público da fonte.</span><span class="sxs-lookup"><span data-stu-id="ed079-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="ed079-113">O sistema remoto responde à fonte e a fonte refere-se para o mapa NAT para determinar qual endereço IP interno, que a resposta deve ser retornada ao.</span><span class="sxs-lookup"><span data-stu-id="ed079-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="ed079-114">É possível incluir suporte ao acesso de usuários externos durante a implantação da sua topologia inicial ou em uma fase posterior.</span><span class="sxs-lookup"><span data-stu-id="ed079-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="ed079-115">Para obter detalhes sobre como adicionar servidores de borda a uma topologia existente, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) na documentação de implantação de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ed079-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


