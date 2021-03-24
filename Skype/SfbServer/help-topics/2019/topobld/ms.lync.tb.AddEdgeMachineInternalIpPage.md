---
title: Adicionar IP Interno de Máquina de Borda
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.
ms.openlocfilehash: ff6c965c6256e26ebe905ce25e15c9e18a2cd0d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095815"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="bfcbd-103">Adicionar IP Interno de Máquina de Borda</span><span class="sxs-lookup"><span data-stu-id="bfcbd-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="bfcbd-104">Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="bfcbd-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="bfcbd-105">O FQDN especificado precisa ser idêntico ao nome do computador configurado no servidor.</span><span class="sxs-lookup"><span data-stu-id="bfcbd-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="bfcbd-106">Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN.</span><span class="sxs-lookup"><span data-stu-id="bfcbd-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="bfcbd-107">O Construtor de Topologia utiliza FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="bfcbd-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="bfcbd-108">Portanto, é necessário configurar um sufixo DNS (Domain Name System) no nome do computador a ser implantado como um Servidor de Borda que não faz parte de um domínio.</span><span class="sxs-lookup"><span data-stu-id="bfcbd-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="bfcbd-109">Para obter detalhes sobre como adicionar um sufixo DNS ao nome de um computador, consulte [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).</span><span class="sxs-lookup"><span data-stu-id="bfcbd-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span></span>