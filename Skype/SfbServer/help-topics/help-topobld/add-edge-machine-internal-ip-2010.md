---
title: Adicionar IP Interno de Máquina de Borda 2010
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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.
ms.openlocfilehash: 51ab7e117892efbbbd7fd16a27b3f06b599297b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120943"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="693d5-103">Adicionar IP Interno de Máquina de Borda 2010</span><span class="sxs-lookup"><span data-stu-id="693d5-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="693d5-104">Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="693d5-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="693d5-105">No **endereço IPv4** interno, digite o endereço IP do Servidor de Borda que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="693d5-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="693d5-106">Em **FQDN** Interno, digite o FQDN (nome de domínio totalmente qualificado) do Servidor de Borda que você deseja adicionar ao pool.</span><span class="sxs-lookup"><span data-stu-id="693d5-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="693d5-107">O FQDN especificado precisa ser idêntico ao nome do computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="693d5-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="693d5-108">Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="693d5-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="693d5-109">O Construtor de Topologia utiliza FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="693d5-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="693d5-110">Portanto, é necessário configurar um sufixo DNS (Domain Name System) no nome do computador a ser implantado como um Servidor de Borda que não faz parte de um domínio.</span><span class="sxs-lookup"><span data-stu-id="693d5-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="693d5-111">Para obter detalhes sobre como adicionar um sufixo DNS ao nome de um computador, consulte [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).</span><span class="sxs-lookup"><span data-stu-id="693d5-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span></span>