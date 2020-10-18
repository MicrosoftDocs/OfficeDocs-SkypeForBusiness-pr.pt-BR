---
title: Suporte a hardware de dispositivo do Lync Server 2013
description: Suporte a hardware de dispositivo do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd03936d35fbc3a639a3ba4596a4357e8e379719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575657"
---
# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="8efc8-103">Suporte a hardware de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8efc8-103">Device hardware support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8efc8-104">_**Última modificação do tópico:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="8efc8-104">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="8efc8-105">Configurações de hardware específicas devem ser feitas antes de você implantar telefones IP e dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="8efc8-105">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="8efc8-106">Os telefones IP executando o Lync Phone Edition dão suporte à descoberta de camada de link Protocol-Media Endpoint Discovery (LLDP-MED) e à Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="8efc8-106">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="8efc8-107">Para aproveitar o LLDP-MED, o comutador deve suportar IEEE802.1AB e ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="8efc8-107"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="8efc8-108">Para aproveitar o PoE, o comutador deve oferecer suporte a PoE802.3AF ou 802.3at.</span><span class="sxs-lookup"><span data-stu-id="8efc8-108">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="8efc8-109">Para habilitar o LLDP-MED, o administrador precisa habilitar o LLDP usando a janela do console do comutador e definir a política de rede do LLDP-MED com a ID de VLAN de voz correta.</span><span class="sxs-lookup"><span data-stu-id="8efc8-109">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="8efc8-110">Além disso, se sua implantação incluir dispositivos analógicos, você deve configurar o gateway analógico para usar o Lync Server e o gateway deve ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="8efc8-110">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="8efc8-111">Um adaptador de telefone analógico (ATA)</span><span class="sxs-lookup"><span data-stu-id="8efc8-111">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="8efc8-112">Um gateway analógico PSTN</span><span class="sxs-lookup"><span data-stu-id="8efc8-112">A PSTN analog gateway</span></span>

  - <span data-ttu-id="8efc8-113">Um Aparelho de Filial Persistente que inclua um gateway PSTN analógico</span><span class="sxs-lookup"><span data-stu-id="8efc8-113">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="8efc8-114">Um Aparelho de Filial Persistente que inclui um gateway PSTN que se comunica com um ATA</span><span class="sxs-lookup"><span data-stu-id="8efc8-114">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="8efc8-115">Para saber como configurar um gateway analógico, consulte "planejando a implantação de dispositivos analógicos" na [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) biblioteca do TechNet do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8efc8-115">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="8efc8-116">(Os dispositivos analógicos funcionam da mesma maneira que no Lync Server 2013, como no Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="8efc8-116">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8efc8-117">É possível configurar o comutador para o Enhanced 9-1-1 (E9-1-1), se o comutador suportar isso.</span><span class="sxs-lookup"><span data-stu-id="8efc8-117">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

