---
title: 'Lync Server 2013: configuração do roteamento de Location-Based para conferência'
description: 'Lync Server 2013: configuração do roteamento Location-Based para conferência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a87f9c799e565f64b0dd30ce025a4e7a3174625
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552157"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuração do roteamento de Location-Based para conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-09-11_

O aplicativo de conferência de roteamento de Location-Based depende da configuração do Lync Server 2013 Location-Based Routing. As principais configurações são as seguintes:

  - O local dos participantes que ingressam em uma reunião é determinado com base no seu site de rede. Um site de rede e suas sub-redes de rede associadas devem ser definidos no Lync Server para impor o roteamento Location-Based.

  - Para impor Location-Based roteamento de reuniões, os participantes do Lync devem estar habilitados para roteamento de Location-Based.

  - Para impor Location-Based roteamento de pontos de extremidade PSTN que participam de reuniões, o tronco SIP usado para conectar os pontos de extremidade PSTN deve ser configurado para roteamento Location-Based.

Para obter informações adicionais sobre como implantar e configurar o roteamento de Location-Based do Lync Server 2013, consulte Configurando o [roteamento baseado em local](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Habilitando o aplicativo de conferência de roteamento de Location-Based

O aplicativo de conferência de roteamento Location-Based está desabilitado por padrão. Antes de habilitar esse aplicativo, você precisa determinar a prioridade correta a ser atribuída ao aplicativo. Para determinar essa prioridade, execute o seguinte cmdlet no Shell de gerenciamento do Lync Server:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

Neste cmdlet, \<Pool FQDN\> é o pool no qual o aplicativo de conferência de roteamento do Location-Based deve ser habilitado.

Este cmdlet retornará a lista de aplicativos hospedados pelo Lync Server e o valor de prioridade para cada um deles. O aplicativo de conferência de roteamento Location-Based precisa ter um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "defaultrouting", "ExumRouting" e "OutboundRouting". Recomendamos que você atribua o Location-Based aplicativo de conferência de roteamento um valor de prioridade que seja um ponto maior do que o valor de prioridade do aplicativo "UdcAgent".

Por exemplo, se o aplicativo "UdcAgent" tiver um valor de prioridade de "2", o aplicativo "defaultrouting" tem um valor de prioridade "8", o aplicativo "ExumRouting" tem um valor de prioridade "9" e o aplicativo "OutboundRouting" tem um valor de prioridade "10", então você deve atribuir Location-Based o aplicativo de conferência de roteamento a um valor "3". Isso colocaria a prioridade dos aplicativos na seguinte ordem: outros aplicativos (prioridades: 0 a 1), "UdcAgent" (prioridade: 2), Location-Based aplicativo de conferência de roteamento (prioridade: 3), outros aplicativos (prioridades: 4 a 8), "roteamento default" (prioridade: 9), "ExumRouting" (prioridade: 10) e "OutboundRouting" (prioridade: 11).

Depois de encontrar o valor de prioridade correto para o aplicativo de conferência de roteamento Location-Based, digite o seguinte cmdlet para cada pool de Front-End ou servidor Standard Edition que hospeda os usuários habilitados para Location-Based roteamento:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Por exemplo:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Após usar esse cmdlet, reinicie todos os servidores front-end no pool ou os servidores Standard Edition nos quais o aplicativo de conferência de roteamento Location-Based foi habilitado.

<div>


> [!IMPORTANT]  
> Location-Based os enforcementos de roteamento para conferências ou transferências de consultoria não serão impostos até que todos os servidores front-end nos pools aplicáveis ou servidores Standard Edition sejam reiniciados.



</div>

Depois que o aplicativo de conferência de roteamento Location-Based tiver sido habilitado com êxito e todos os servidores do Lync aplicáveis forem reiniciados, todas as conferências organizadas por usuários do Lync habilitados para Location-Based roteamento serão monitoradas para evitar o bypass de chamadas PSTN

</div>

</div>

<span> </span>

</div>

</div>

</div>

