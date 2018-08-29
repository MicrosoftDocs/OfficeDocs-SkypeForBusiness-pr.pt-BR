---
title: Adicionar IP interno de máquina de borda 2010
ms.author: heidip
author: microsoftheidi
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
ms.openlocfilehash: 6106f225dbdda1f7e1300606b9cc77299482d020
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23251268"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="01065-103">Adicionar IP interno de máquina de borda 2010</span><span class="sxs-lookup"><span data-stu-id="01065-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="01065-104">Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="01065-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="01065-105">Em **endereço IPv4 interno**, digite o endereço IP do servidor de borda que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="01065-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="01065-106">Em **FQDN interno**, digite o nome de domínio totalmente qualificado (FQDN) do servidor de borda que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="01065-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="01065-107">O FQDN que você especificar deve ser idêntico ao nome do computador que está configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="01065-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="01065-108">Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="01065-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="01065-109">O Construtor de Topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="01065-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="01065-110">Portanto, você deve configurar um sufixo de sistema de nome de domínio (DNS) no nome do computador para ser implantado como um servidor de borda que não está unido a um domínio.</span><span class="sxs-lookup"><span data-stu-id="01065-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="01065-111">Para obter detalhes sobre como adicionar um sufixo DNS para um nome de computador, consulte [Configurar o DNS para suporte de borda](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="01065-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


