---
title: Suporte a hardware de dispositivo do Lync Server 2013
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
ms.openlocfilehash: e0b4b0f24523044169ae3274ae4d0ff16ae9ff67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="e8adb-102">Suporte a hardware de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8adb-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8adb-103">_**Última modificação do tópico:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="e8adb-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="e8adb-104">Configurações de hardware específicas devem ser feitas antes de você implantar telefones IP e dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="e8adb-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="e8adb-105">Telefones IP que executam o protocolo de descoberta de camada de link do Lync Phone Edition – descoberta de ponto de extremidade de mídia (LLDP-MED) e PoE (Power over Ethernet).</span><span class="sxs-lookup"><span data-stu-id="e8adb-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="e8adb-106">Para aproveitar o LLDP-MED, o comutador deve suportar IEEE802.1AB e ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="e8adb-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="e8adb-107">Para aproveitar o PoE, o comutador deve oferecer suporte a PoE802.3AF ou 802.3at.</span><span class="sxs-lookup"><span data-stu-id="e8adb-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="e8adb-108">Para habilitar o LLDP-MED, o administrador precisa habilitar o LLDP usando a janela do console do comutador e definir a política de rede do LLDP-MED com a ID de VLAN de voz correta.</span><span class="sxs-lookup"><span data-stu-id="e8adb-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="e8adb-109">Além disso, se sua implantação incluir dispositivos analógicos, você deve configurar o gateway analógico para usar o Lync Server e o gateway deve ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="e8adb-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="e8adb-110">Um adaptador de telefone analógico (ATA)</span><span class="sxs-lookup"><span data-stu-id="e8adb-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="e8adb-111">Um gateway analógico PSTN</span><span class="sxs-lookup"><span data-stu-id="e8adb-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="e8adb-112">Um Aparelho de Filial Persistente que inclua um gateway PSTN analógico</span><span class="sxs-lookup"><span data-stu-id="e8adb-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="e8adb-113">Um Aparelho de Filial Persistente que inclui um gateway PSTN que se comunica com um ATA</span><span class="sxs-lookup"><span data-stu-id="e8adb-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="e8adb-114">Para saber como configurar um gateway analógico, consulte "planejando a implantação de dispositivos analógicos" [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) na biblioteca do TechNet do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e8adb-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="e8adb-115">(Os dispositivos analógicos funcionam da mesma maneira que no Lync Server 2013, como no Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="e8adb-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e8adb-116">É possível configurar o comutador para o Enhanced 9-1-1 (E9-1-1), se o comutador suportar isso.</span><span class="sxs-lookup"><span data-stu-id="e8adb-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

