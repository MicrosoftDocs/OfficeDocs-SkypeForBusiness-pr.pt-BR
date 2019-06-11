---
title: 'Lync Server 2013: verificar ambiente físico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07335046dc4b37d0e5327ded0a12293657f5fe43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="ae734-102">Realização de verificações ambientais físicas</span><span class="sxs-lookup"><span data-stu-id="ae734-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae734-103">_**Tópico da última modificação:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="ae734-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="ae734-104">Antes de verificar o desempenho, a disponibilidade e a funcionalidade da implantação do Lync Server 2013, você deve verificar o ambiente físico.</span><span class="sxs-lookup"><span data-stu-id="ae734-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="ae734-105">Por exemplo, a temperatura da sala do servidor pode precisar ser diminuída ou pode ser necessário substituir um cabo de rede.</span><span class="sxs-lookup"><span data-stu-id="ae734-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="ae734-106">Para obter melhores resultados, realize as seguintes inspeções ambientais físicas:</span><span class="sxs-lookup"><span data-stu-id="ae734-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="ae734-107">**Segurança física medidas**   a proteção de segurança física, como bloqueios, portas e salas de acesso restrito, deve ser protegida.</span><span class="sxs-lookup"><span data-stu-id="ae734-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="ae734-108">Verifique se há entradas não autorizadas e forçadas e sinais de danos no equipamento.</span><span class="sxs-lookup"><span data-stu-id="ae734-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="ae734-109">**Temperatura e umidade**   de alta temperatura, fluxo de ar fraco e umidade podem causar sobreaquecimento a componentes de hardware.</span><span class="sxs-lookup"><span data-stu-id="ae734-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="ae734-110">Verifique a temperatura e a umidade para ajudar a garantir que os sistemas ambientais, como aquecimento e ar condicionado, mantenham condições e funções aceitáveis nas especificações do fabricante do hardware.</span><span class="sxs-lookup"><span data-stu-id="ae734-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="ae734-111">Quando um novo equipamento tiver sido instalado recentemente, verifique se o fluxo de ar de e para os servidores não é impedido e atende às especificações do fabricante.</span><span class="sxs-lookup"><span data-stu-id="ae734-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="ae734-112">**Dispositivos e componentes**   a organização do Lync Server 2013 depende de uma rede física em funcionamento e de um hardware relacionado.</span><span class="sxs-lookup"><span data-stu-id="ae734-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="ae734-113">Certifique-se de que roteadores, switches, hubs, cabos físicos e conectores estão operacionais.</span><span class="sxs-lookup"><span data-stu-id="ae734-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="ae734-114">As especificações sobre como realizar essas verificações dependerão muito do seu site de instalação e do hardware do servidor escolhido.</span><span class="sxs-lookup"><span data-stu-id="ae734-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="ae734-115">Na primeira vez que você executar essa verificação, consulte a documentação do hardware e anote os parâmetros desejados para referência futura.</span><span class="sxs-lookup"><span data-stu-id="ae734-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="ae734-116">Ambiente de espaço do servidor desejado</span><span class="sxs-lookup"><span data-stu-id="ae734-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae734-117">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="ae734-117">Parameter</span></span></th>
<th><span data-ttu-id="ae734-118">Valor desejado ou intervalo</span><span class="sxs-lookup"><span data-stu-id="ae734-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae734-119">Aquecimento</span><span class="sxs-lookup"><span data-stu-id="ae734-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae734-120">Relativa</span><span class="sxs-lookup"><span data-stu-id="ae734-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae734-121">Frente das faces do servidor</span><span class="sxs-lookup"><span data-stu-id="ae734-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="ae734-122">Corredor quente/corredor frio</span><span class="sxs-lookup"><span data-stu-id="ae734-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae734-123">Percurso de exaustão não impedida</span><span class="sxs-lookup"><span data-stu-id="ae734-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

