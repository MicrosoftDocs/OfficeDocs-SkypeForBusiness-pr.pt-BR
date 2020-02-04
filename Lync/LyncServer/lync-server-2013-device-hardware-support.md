---
title: 'Lync Server 2013: Suporte a hardware de dispositivo'
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
ms.openlocfilehash: ea720eda982ab20333e56de268085a706ab2cdc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="13f5e-102">Suporte a hardware de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13f5e-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13f5e-103">_**Tópico da última modificação:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="13f5e-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="13f5e-104">Configurações de hardware específicas devem estar no lugar antes de você implantar telefones IP e dispositivos analógicos.</span><span class="sxs-lookup"><span data-stu-id="13f5e-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="13f5e-105">Telefones IP executando o Lync Phone Edition dão suporte ao protocolo de descoberta de camada de link-descoberta de ponto de extremidade de mídia (LLDP-MED) e Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="13f5e-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="13f5e-106">Para tirar proveito do LLDP-MED, o switch deve dar suporte a IEEE 802.1 AB e ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="13f5e-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="13f5e-107">Para tirar proveito da PoE, o switch deve oferecer suporte a PoE 802.3 AF ou 802.3 em.</span><span class="sxs-lookup"><span data-stu-id="13f5e-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="13f5e-108">Para habilitar o LLDP-MED, o administrador deve habilitar o LLDP usando a janela de console do switch e definir a política de rede LLDP-MED com a ID de VLAN de voz correta.</span><span class="sxs-lookup"><span data-stu-id="13f5e-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="13f5e-109">Além disso, se a sua implantação inclui dispositivos analógicos, você deve configurar o gateway analógico para usar o Lync Server, e o gateway deve ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="13f5e-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="13f5e-110">Um adaptador de telefonia analógica (ATA)</span><span class="sxs-lookup"><span data-stu-id="13f5e-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="13f5e-111">Um gateway analógico PSTN</span><span class="sxs-lookup"><span data-stu-id="13f5e-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="13f5e-112">Um aparelho de ramificação sobreviventes que inclui um gateway analógico PSTN</span><span class="sxs-lookup"><span data-stu-id="13f5e-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="13f5e-113">Um aparelho de ramificação sobreviventes que inclui um gateway PSTN que se comunica com um ATA</span><span class="sxs-lookup"><span data-stu-id="13f5e-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="13f5e-114">Para saber como configurar um gateway analógico, consulte "planejando implantar dispositivos analógicos" [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) na biblioteca do Lync Server 2010 TechNet.</span><span class="sxs-lookup"><span data-stu-id="13f5e-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="13f5e-115">(Dispositivos analógicos funcionam da mesma maneira no Lync Server 2013 como no Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="13f5e-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="13f5e-116">Você pode configurar a opção para Enhanced 9-1-1 (E9-1-1), se o switch der suporte a isso.</span><span class="sxs-lookup"><span data-stu-id="13f5e-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

