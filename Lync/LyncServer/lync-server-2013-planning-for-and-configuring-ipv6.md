---
title: 'Lync Server 2013: planejando e Configurando o IPv6'
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
ms.openlocfilehash: 193c0db95b88a5436043bd06d63b62bc8e45a3f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="f749f-102">Planejando e Configurando o IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f749f-102">Planning for and configuring IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f749f-103">_**Última modificação do tópico:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="f749f-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="f749f-104">O Lync Server 2013 inclui suporte para endereços IP versão 6 (IPv6), juntamente com o suporte contínuo dos endereços IP versão 4 (IPv4).</span><span class="sxs-lookup"><span data-stu-id="f749f-104">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="f749f-105">Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet.</span><span class="sxs-lookup"><span data-stu-id="f749f-105">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="f749f-106">Devido ao aumento do número de dispositivos em todo o mundo, os endereços IPv4 disponíveis estão em execução. Por causa disso, muitos dispositivos novos estão migrando para o uso de endereços IPv6.</span><span class="sxs-lookup"><span data-stu-id="f749f-106">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="f749f-107">Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32-bits, os endereços IPv6 usam 128 bits.</span><span class="sxs-lookup"><span data-stu-id="f749f-107">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="f749f-108">Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles.</span><span class="sxs-lookup"><span data-stu-id="f749f-108">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="f749f-109">Um endereço IPv4 típico parece com o seguinte: 192.0.2.235, enquanto um endereço IPv6 parece com o seguinte: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span><span class="sxs-lookup"><span data-stu-id="f749f-109">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="f749f-110">A alteração na formatação e funcionalidade para dispositivos que usam endereços IPv6 requer várias considerações de implantação e configuração na sua instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f749f-110">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f749f-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f749f-111">In This Section</span></span>

  - [<span data-ttu-id="f749f-112">Visão geral dos tipos de endereço IP para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f749f-112">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="f749f-113">Requisitos técnicos para IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f749f-113">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="f749f-114">Considerações de migração e de coexistência para IPv6 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f749f-114">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="f749f-115">Configurar tipos de endereço IP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f749f-115">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

