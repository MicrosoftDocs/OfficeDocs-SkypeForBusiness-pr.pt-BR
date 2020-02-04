---
title: 'Lync Server 2013: Configuração do Roteamento Baseado em Local para conferência'
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
ms.openlocfilehash: d9ea90f30dcd9ec9fdde2e6f4db25e7d27ad12cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Configuração do Roteamento Baseado em Local para conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-09-11_

O aplicativo de conferência de roteamento baseado em localização depende da configuração do roteamento baseado em localização do Lync Server 2013. Estas são as principais configurações:

  - O local dos participantes que ingressam em uma reunião é determinado com base em seus locais de rede. Um site de rede e suas sub-redes de rede associadas devem ser definidos no Lync Server para impor o roteamento baseado em localização.

  - Para impor o roteamento baseado em localização de reuniões, os participantes do Lync devem estar habilitados para roteamento baseado em local.

  - Para impor o roteamento baseado em localização de pontos de extremidade PSTN ingressando em reuniões, o tronco SIP usado para conexão dos pontos de extremidade PSTN devem ser configurados para roteamento baseado em local.

Para obter informações adicionais sobre como implantar e configurar o roteamento baseado em localização do Lync Server 2013, consulte Configurando o [roteamento baseado em local](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Habilitando o aplicativo de conferência de roteamento baseado em localização

O aplicativo de conferência de roteamento baseado em localização é desabilitado por padrão. Antes de habilitá-lo, determine a prioridade certa para atribuir a ele. Para determinar essa prioridade, execute o seguinte cmdlet no Shell de gerenciamento do Lync Server:

Get-CsServerApplication-serviço de identidade: registrador:\<FQDN de pool\>

Nesse cmdlet, \<o FQDN\> do pool é o pool no qual o aplicativo de conferência de roteamento baseado em localização deve ser habilitado.

Esse cmdlet retornará a lista dos aplicativos hospedados pelo Lync Server e o valor de prioridade para cada um deles. O aplicativo de conferência de roteamento baseado em localização precisa ser atribuído um valor de prioridade maior do que o aplicativo "UdcAgent" e menor do que os aplicativos "defaultrouting", "ExumRouting" e "OutboundRouting". Recomendamos que você atribua o aplicativo de conferência de roteamento baseado em localização um valor de prioridade que seja um ponto maior do que o valor de prioridade do aplicativo "UdcAgent".

Por exemplo, se o aplicativo "UdcAgent" tem um valor de prioridade "2", o aplicativo "defaultrouting" tem um valor de prioridade de "8", o aplicativo "ExumRouting" tem um valor de prioridade de "9" e o aplicativo "OutboundRouting" tem um valor de prioridade de "10" e, em seguida, Você deve atribuir o aplicativo de conferência de roteamento baseado em localização um valor de prioridade de "3". Isso colocaria a prioridade dos aplicativos na seguinte ordem: outros aplicativos (prioridades: de 0 a 1), "UdcAgent" (prioridade: 2), aplicativo de conferência de roteamento baseado em local (prioridade: 3), outros aplicativos (prioridades: 4 a 8), " Defaultrouting "(prioridade: 9)," ExumRouting "(prioridade: 10) e" OutboundRouting "(prioridade: 11).

Depois de encontrar o valor de prioridade correto para o aplicativo de videoconferência baseado em localização, digite o cmdlet a seguir para cada pool Front-end ou servidor Standard Edition que os usuários habilitaram para o roteamento baseado em localização:

Novo-CsServerApplication-serviço de identidade: registrador\<:\>pool FQDN/LBRouting \<-Priority\> Application Priority-Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting

Por exemplo:

New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting

Depois de usar esse cmdlet, reinicie todos os servidores front-end no pool ou os servidores Standard Edition nos quais o aplicativo de conferência de roteamento baseado em localização esteja habilitado.

<div>


> [!IMPORTANT]  
> Os roteamentos baseados em local para conferências ou transferências de consultoria não serão impostos até que todos os servidores de front-end nos pools aplicáveis ou servidores padrão da edição sejam reiniciados.



</div>

Depois que o aplicativo de conferência de roteamento baseado em local tiver sido habilitado com êxito e todos os servidores do Lync aplicáveis forem reiniciados, todas as conferências organizadas pelos usuários do Lync habilitados para roteamento baseado em local serão monitoradas para impedir o bypass de chamada PSTN

</div>

</div>

<span> </span>

</div>

</div>

</div>

