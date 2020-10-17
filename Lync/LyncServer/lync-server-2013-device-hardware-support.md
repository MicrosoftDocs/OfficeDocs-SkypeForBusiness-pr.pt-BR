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
ms.openlocfilehash: 8c802141adfecf53b70709ad90cc098004eacda1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522458"
---
# <a name="device-hardware-support-in-lync-server-2013"></a>Suporte a hardware de dispositivo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-14_

Configurações de hardware específicas devem ser feitas antes de você implantar telefones IP e dispositivos analógicos.

Os telefones IP executando o Lync Phone Edition dão suporte à descoberta de camada de link Protocol-Media Endpoint Discovery (LLDP-MED) e à Power over Ethernet (PoE).Para aproveitar o LLDP-MED, o comutador deve suportar IEEE802.1AB e ANSI/TIA-1057. Para aproveitar o PoE, o comutador deve oferecer suporte a PoE802.3AF ou 802.3at.

Para habilitar o LLDP-MED, o administrador precisa habilitar o LLDP usando a janela do console do comutador e definir a política de rede do LLDP-MED com a ID de VLAN de voz correta.

Além disso, se sua implantação incluir dispositivos analógicos, você deve configurar o gateway analógico para usar o Lync Server e o gateway deve ser um dos seguintes:

  - Um adaptador de telefone analógico (ATA)

  - Um gateway analógico PSTN

  - Um Aparelho de Filial Persistente que inclua um gateway PSTN analógico

  - Um Aparelho de Filial Persistente que inclui um gateway PSTN que se comunica com um ATA

Para saber como configurar um gateway analógico, consulte "planejando a implantação de dispositivos analógicos" na [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) biblioteca do TechNet do Lync Server 2010. (Os dispositivos analógicos funcionam da mesma maneira que no Lync Server 2013, como no Lync Server 2010.)

<div>


> [!IMPORTANT]  
> É possível configurar o comutador para o Enhanced 9-1-1 (E9-1-1), se o comutador suportar isso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

