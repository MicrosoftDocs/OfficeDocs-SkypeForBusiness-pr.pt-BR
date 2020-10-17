---
title: 'Lync Server 2013: planejando e Configurando o IPv6'
description: 'Lync Server 2013: planejando e Configurando o IPv6.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c63268bd92fc9d3b683cfa05ab49f01ea56d6ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554357"
---
# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="efeb4-103">Planejando e Configurando o IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efeb4-103">Planning for and configuring IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efeb4-104">_**Última modificação do tópico:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="efeb4-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="efeb4-105">O Lync Server 2013 inclui suporte para endereços IP versão 6 (IPv6), juntamente com o suporte contínuo dos endereços IP versão 4 (IPv4).</span><span class="sxs-lookup"><span data-stu-id="efeb4-105">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="efeb4-106">Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet.</span><span class="sxs-lookup"><span data-stu-id="efeb4-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="efeb4-107">Devido ao aumento do número de dispositivos em todo o mundo, os endereços IPv4 disponíveis estão em execução. Por causa disso, muitos dispositivos novos estão migrando para o uso de endereços IPv6.</span><span class="sxs-lookup"><span data-stu-id="efeb4-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="efeb4-108">Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32-bits, os endereços IPv6 usam 128 bits.</span><span class="sxs-lookup"><span data-stu-id="efeb4-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="efeb4-109">Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles.</span><span class="sxs-lookup"><span data-stu-id="efeb4-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="efeb4-110">Um endereço IPv4 típico parece com o seguinte: 192.0.2.235, enquanto um endereço IPv6 parece com o seguinte: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span><span class="sxs-lookup"><span data-stu-id="efeb4-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="efeb4-111">A alteração na formatação e funcionalidade para dispositivos que usam endereços IPv6 requer várias considerações de implantação e configuração na sua instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efeb4-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="efeb4-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="efeb4-112">In This Section</span></span>

  - [<span data-ttu-id="efeb4-113">Visão geral dos tipos de endereço IP para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efeb4-113">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="efeb4-114">Requisitos técnicos para IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efeb4-114">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="efeb4-115">Considerações de migração e de coexistência para IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efeb4-115">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="efeb4-116">Configurar tipos de endereço IP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efeb4-116">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

