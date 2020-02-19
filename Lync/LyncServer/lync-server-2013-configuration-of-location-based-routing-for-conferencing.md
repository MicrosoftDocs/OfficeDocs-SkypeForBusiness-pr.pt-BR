---
title: 'Lync Server 2013: configuração do roteamento baseado em local para conferência'
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
ms.openlocfilehash: 237799a84d0230bf55737779921dd66b23c27130
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuração do roteamento baseado em local para conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-09-11_

O aplicativo de conferência de roteamento baseado em local depende da configuração do roteamento baseado em local do Lync Server 2013. As principais configurações são as seguintes:

  - O local dos participantes que ingressam em uma reunião é determinado com base no seu site de rede. Um site de rede e suas sub-redes de rede associadas devem ser definidos no Lync Server para impor o roteamento baseado em local.

  - Para impor o roteamento baseado em local de reuniões, os participantes do Lync devem estar habilitados para roteamento baseado em local.

  - Para impor o roteamento baseado em local de pontos de extremidade PSTN que participam de reuniões, o tronco SIP usado para conectar os pontos de extremidade PSTN deve ser configurado para roteamento baseado em local.

Para obter informações adicionais sobre como implantar e configurar o roteamento baseado em local do Lync Server 2013, consulte Configurando o [roteamento baseado em local](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Habilitando o aplicativo de conferência de roteamento baseado em local

O aplicativo de conferência de roteamento baseado em local está desabilitado por padrão. Antes de habilitar esse aplicativo, você precisa determinar a prioridade correta a ser atribuída ao aplicativo. Para determinar essa prioridade, execute o seguinte cmdlet no Shell de gerenciamento do Lync Server:

Get-CsServerApplication-Identity Service: registrar:\<FQDN do pool\>

Neste cmdlet, \<o FQDN\> do pool é o pool no qual o aplicativo de conferência de roteamento baseado em local deve ser habilitado.

Este cmdlet retornará a lista de aplicativos hospedados pelo Lync Server e o valor de prioridade para cada um deles. O aplicativo de conferência de roteamento baseado em local precisa ser atribuído a um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "defaultrouting", "ExumRouting" e "OutboundRouting". Recomendamos que você atribua o aplicativo de conferência de roteamento baseado em local um valor de prioridade que seja um ponto maior do que o valor de prioridade do aplicativo "UdcAgent".

Por exemplo, se o aplicativo "UdcAgent" tiver um valor de prioridade "2", o aplicativo "defaultrouting" tem um valor de prioridade "8", o aplicativo "ExumRouting" tem um valor de prioridade "9" e o aplicativo "OutboundRouting" tem um valor de prioridade "10" e, em seguida, Você deve atribuir o aplicativo de conferência de roteamento baseado em local com um valor de prioridade "3". Isso colocaria a prioridade dos aplicativos na seguinte ordem: outros aplicativos (prioridades: 0 a 1), "UdcAgent" (prioridade: 2), aplicativo de conferência de roteamento baseado em local (prioridade: 3), outros aplicativos (prioridades: 4 a 8), " Defaultrouting "(prioridade: 9)," ExumRouting "(prioridade: 10) e" OutboundRouting "(prioridade: 11).

Depois de encontrar o valor de prioridade correto para o aplicativo de conferência de roteamento baseado em local, digite o cmdlet a seguir para cada pool de front-end ou servidor Standard Edition que hospeda os usuários habilitados para roteamento baseado em local:

New-CsServerApplication-Identity Service: registrar:\<pool FQDN\>/LBRouting-priority \<Application Priority\> Enabled $true-Critical $true-URIhttps://www.microsoft.com/LCS/LBRouting

Por exemplo:

New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3 Enabled $true-Critical $true-URIhttps://www.microsoft.com/LCS/LBRouting

Após usar esse cmdlet, reinicie todos os servidores front-end no pool ou os servidores Standard Edition onde o aplicativo de conferência de roteamento baseado na localização tenha sido habilitado.

<div>


> [!IMPORTANT]  
> Os enforces de roteamento baseado em local para conferências ou transferências de consultoria não serão impostos até que todos os servidores front-end nos pools aplicáveis ou servidores Standard Edition sejam reiniciados.



</div>

Depois que o aplicativo de conferência de roteamento baseado no local tiver sido habilitado com êxito e todos os servidores do Lync aplicáveis forem reiniciados, todas as conferências organizadas por usuários do Lync habilitados para roteamento baseado em local serão monitoradas para evitar o bypass de PSTN

</div>

</div>

<span> </span>

</div>

</div>

</div>

