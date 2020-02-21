---
title: 'Lync Server 2013: verificar ambiente físico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e85f99250161433ba895f287521367d1b76cec1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="420d6-102">Executando verificações ambientais físicas</span><span class="sxs-lookup"><span data-stu-id="420d6-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="420d6-103">_**Última modificação do tópico:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="420d6-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="420d6-104">Antes de verificar o desempenho, a disponibilidade e a funcionalidade da implantação do Lync Server 2013, você deve verificar o ambiente físico.</span><span class="sxs-lookup"><span data-stu-id="420d6-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="420d6-105">Por exemplo, a temperatura da sala do servidor pode ter que ser diminuída ou um cabo de rede pode ter que ser substituído.</span><span class="sxs-lookup"><span data-stu-id="420d6-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="420d6-106">Para obter melhores resultados, execute as seguintes inspeções de ambiente físico:</span><span class="sxs-lookup"><span data-stu-id="420d6-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="420d6-107">**A segurança física mede**   a proteção de segurança física, como bloqueios, portas e salas de acesso restrito devem ser protegidas.</span><span class="sxs-lookup"><span data-stu-id="420d6-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="420d6-108">Verifique se há entradas não autorizadas e forçadas e sinais de danos a equipamentos.</span><span class="sxs-lookup"><span data-stu-id="420d6-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="420d6-109">**Temperatura e umidade**   alta temperatura, fluxo de ar ruim e umidade podem causar o superaquecimento dos componentes de hardware.</span><span class="sxs-lookup"><span data-stu-id="420d6-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="420d6-110">Verifique a temperatura e a umidade para ajudar a garantir que os sistemas ambientais, como calefação e ar condicionado, possam manter as condições e funções aceitáveis nas especificações do fabricante do hardware.</span><span class="sxs-lookup"><span data-stu-id="420d6-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="420d6-111">Quando um novo equipamento tiver sido instalado recentemente, verifique também se o fluxo de ar de e para os servidores está impedida e atende à especificação do fabricante.</span><span class="sxs-lookup"><span data-stu-id="420d6-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="420d6-112">**Dispositivos e componentes**   a organização do Lync Server 2013 depende de uma rede física em funcionamento e de um hardware relacionado.</span><span class="sxs-lookup"><span data-stu-id="420d6-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="420d6-113">Certifique-se de que roteadores, comutadores, hubs, cabos físicos e conectores estão operacionais.</span><span class="sxs-lookup"><span data-stu-id="420d6-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="420d6-114">As informações específicas sobre como realizar essas verificações dependerão muito do seu site de instalação e do hardware do servidor escolhido.</span><span class="sxs-lookup"><span data-stu-id="420d6-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="420d6-115">Na primeira vez que você executar essa verificação, consulte a documentação do hardware e observe os parâmetros desejados para referência futura.</span><span class="sxs-lookup"><span data-stu-id="420d6-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="420d6-116">Ambiente de espaço do servidor desejado</span><span class="sxs-lookup"><span data-stu-id="420d6-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="420d6-117">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="420d6-117">Parameter</span></span></th>
<th><span data-ttu-id="420d6-118">Valor ou intervalo desejado</span><span class="sxs-lookup"><span data-stu-id="420d6-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="420d6-119">Temperatura</span><span class="sxs-lookup"><span data-stu-id="420d6-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="420d6-120">Umidade</span><span class="sxs-lookup"><span data-stu-id="420d6-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="420d6-121">Frente do servidor</span><span class="sxs-lookup"><span data-stu-id="420d6-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="420d6-122">Corredor quente/corredor frio</span><span class="sxs-lookup"><span data-stu-id="420d6-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="420d6-123">Percurso de exaustão não impedida</span><span class="sxs-lookup"><span data-stu-id="420d6-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

