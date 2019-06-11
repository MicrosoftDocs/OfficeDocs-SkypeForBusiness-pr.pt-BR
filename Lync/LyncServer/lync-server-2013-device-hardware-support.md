---
title: 'Lync Server 2013: Suporte a hardware de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da92e5f8d37ae5112ccea2d2b33f7f2b0186dfcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Suporte a hardware de dispositivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-14_

Configurações de hardware específicas devem estar no lugar antes de você implantar telefones IP e dispositivos analógicos.

Telefones IP executando o Lync Phone Edition dão suporte ao protocolo de descoberta de camada de link-descoberta de ponto de extremidade de mídia (LLDP-MED) e Power over Ethernet (PoE).Para tirar proveito do LLDP-MED, o switch deve dar suporte a IEEE 802.1 AB e ANSI/TIA-1057. Para tirar proveito da PoE, o switch deve oferecer suporte a PoE 802.3 AF ou 802.3 em.

Para habilitar o LLDP-MED, o administrador deve habilitar o LLDP usando a janela de console do switch e definir a política de rede LLDP-MED com a ID de VLAN de voz correta.

Além disso, se a sua implantação inclui dispositivos analógicos, você deve configurar o gateway analógico para usar o Lync Server, e o gateway deve ser um dos seguintes:

  - Um adaptador de telefonia analógica (ATA)

  - Um gateway analógico PSTN

  - Um aparelho de ramificação sobreviventes que inclui um gateway analógico PSTN

  - Um aparelho de ramificação sobreviventes que inclui um gateway PSTN que se comunica com um ATA

Para saber como configurar um gateway analógico, consulte "planejando implantar dispositivos analógicos" [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) na biblioteca do Lync Server 2010 TechNet. (Dispositivos analógicos funcionam da mesma maneira no Lync Server 2013 como no Lync Server 2010.)

<div>


> [!IMPORTANT]  
> Você pode configurar a opção para Enhanced 9-1-1 (E9-1-1), se o switch der suporte a isso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

