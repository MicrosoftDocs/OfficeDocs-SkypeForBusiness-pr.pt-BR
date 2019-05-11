---
title: Adicionar IP Interno de Máquina de Borda 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) do servidor de borda.
ms.openlocfilehash: 1ec24b1c85b429cf5308eb7e521c7ca4d7d295dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886519"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="19279-103">Adicionar IP Interno de Máquina de Borda 2010</span><span class="sxs-lookup"><span data-stu-id="19279-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="19279-104">Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="19279-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="19279-105">Em **endereço IPv4 interno**, digite o endereço IP do servidor de borda que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="19279-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="19279-106">Em **FQDN interno**, digite o nome de domínio totalmente qualificado (FQDN) do servidor de borda que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="19279-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="19279-107">O FQDN que você especificar deve ser idêntico ao nome do computador que está configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="19279-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="19279-108">Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="19279-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="19279-109">O Construtor de Topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="19279-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="19279-110">Portanto, você deve configurar um sufixo de sistema de nome de domínio (DNS) no nome do computador para ser implantado como um servidor de borda que não está unido a um domínio.</span><span class="sxs-lookup"><span data-stu-id="19279-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="19279-111">Para obter detalhes sobre como adicionar um sufixo DNS para um nome de computador, consulte [Configurar o DNS para suporte de borda](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="19279-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


