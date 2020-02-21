---
title: 'Lync Server 2013: validar configurações do sistema de nomes de domínio para balanceamento de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9e45a007fd617ebefc6702a9be7da2e7d0a368f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="f27b3-102">Validar configurações do sistema de nomes de domínio para balanceamento de carga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f27b3-102">Validate Domain Name System settings for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f27b3-103">_**Última modificação do tópico:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="f27b3-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="f27b3-p101">Para suportar o FQDN usado pelo balanceamento de carga DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão atualmente implantados.</span><span class="sxs-lookup"><span data-stu-id="f27b3-p101">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>

<span data-ttu-id="f27b3-106">Além disso, se você estiver usando o balanceamento de carga DNS para os pools de borda, serão necessárias as seguintes entradas DNS:</span><span class="sxs-lookup"><span data-stu-id="f27b3-106">Additionally if you are using DNS load balancing for the Edge pools the following DNS entries are required:</span></span>

  - <span data-ttu-id="f27b3-107">Para o serviço de borda de acesso do Lync Server, você deve ter uma entrada para cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="f27b3-107">For the Lync Server Access Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f27b3-108">Cada entrada deve resolver o FQDN do serviço de borda de acesso do Lync Server (por exemplo, sip.contoso.com) para o endereço IP do serviço de borda de acesso do Lync Server em um dos servidores de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="f27b3-108">Each entry must resolve the FQDN of the Lync Server Access Edge service (for example, sip.contoso.com) to the IP address of the Lync Server Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f27b3-109">Para o serviço de borda de Webconferência do Lync Server, você deve ter uma entrada para cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="f27b3-109">For the Lync Server Web Conferencing Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f27b3-110">Cada entrada deve resolver o FQDN do serviço de borda de Webconferência do Lync Server (por exemplo, webconf.contoso.com) para o endereço IP do serviço de borda de Webconferência do Lync Server em um dos servidores de borda do pool.</span><span class="sxs-lookup"><span data-stu-id="f27b3-110">Each entry must resolve the FQDN of the Lync Server Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Lync Server Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f27b3-111">Para o serviço de borda de áudio/vídeo do Lync Server, você deve ter uma entrada para cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="f27b3-111">For the Lync Server Audio/Video Edge service, you must have one entry for each server in the pool.</span></span> <span data-ttu-id="f27b3-112">Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo do Lync Server (por exemplo, av.contoso.com) para o endereço IP do serviço de borda de áudio/vídeo do Lync Server em um dos servidores de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="f27b3-112">Each entry must resolve the FQDN of the Lync Server Audio/Video Edge service (for example, av.contoso.com) to the IP address of the Lync Server Audio/Video Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f27b3-113">Se quiser usar o balanceamento de carga DNS na interface interna do pool de borda, você deve adicionar um registro DNS que resolva o FQDN interno do pool de borda para o endereço IP de cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="f27b3-113">If you want to use DNS load balancing on the internal interface of the Edge pool, you must add one DNS record, which resolves the internal FQDN of the Edge pool to the IP address of each server in the pool.</span></span>

<span data-ttu-id="f27b3-114">Para verificar se o DNS está retornando os valores corretos para o balanceamento de carga DNS, você deve usar a ferramenta nslookup.</span><span class="sxs-lookup"><span data-stu-id="f27b3-114">To verify that DNS is returning the correct values for DNS load balancing you should use the nslookup tool.</span></span> <span data-ttu-id="f27b3-115">Para retornar todos os valores de um registro DNS com Nslookup, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="f27b3-115">To return all values for a DNS record with nslookup you should run the command:</span></span>

`nslookup <FQDN >`

<span data-ttu-id="f27b3-116">Você deve executar esse comando para cada FQDN usado na configuração de balanceamento de carga DNS para verificar se cada conjunto de registros para balanceamento de carga DNS retornou todas as entradas corretas.</span><span class="sxs-lookup"><span data-stu-id="f27b3-116">You would run this command for every FQDN used in DNS load balancing configuration to verify that every record set for DNS load balancing returned all of the correct entries.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

