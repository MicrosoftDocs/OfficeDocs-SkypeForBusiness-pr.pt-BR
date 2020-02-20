---
title: 'Lync Server 2013: Habilitando a QoS para dispositivos que não são baseados no Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad830b2cf15e3f34c443feaa5ea21e19279804cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Habilitando a QoS no Lync Server 2013 para dispositivos que não são baseados no Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Quando você instala o Microsoft Lync Server 2013, a qualidade de serviço (QoS) não será habilitada para os dispositivos usados em sua organização que usam um sistema operacional diferente do Windows. Você pode verificar isso executando o seguinte comando no Shell de gerenciamento do Lync Server 2013:

    Get-CsMediaConfiguration

Assumindo que você não realizou qualquer mudança em suas definições de configuração de mídia, você deve obter informação semelhante ao seguinte:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se a propriedade EnableQoS estiver definida como false (como na saída anterior), significa que a qualidade do serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows. A QoS é habilitada por padrão para os dispositivos do Lync Phone Edition; no entanto, é possível desabilitar a qualidade do serviço para o Lync Phone Edition.

Para habilitar a qualidade de serviço no escopo global, execute o seguinte comando no Shell de gerenciamento do Lync Server:

    Set-CsMediaConfiguration -EnableQoS $True

O comando anterior habilita o QoS no escopo global; no entanto, é importante observar que as definições de configuração de mídia também podem ser aplicadas ao escopo local. Se você precisa habilitar a Qualidade do Serviço para um site, você deve incluir a Identidade das definições de configuração ao chamar o Set-CsMediaConfiguration. Por exemplo, este comando habilita o QoS para o site Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Você não precisa habilitar o QoS no escopo local? Isto depende. As configurações atribuídas ao escopo local têm precedência sobre as configurações atribuídas para o escopo global. Suponha que você habilitou o QoS no escopo global, mas desabilitou no escopo local (para o local Redmond). Neste caso, a Qualidade do Serviço será desabilitada para o local Redmond. isto ocorre porque as configurações locais têm precedência. Para habilitar o QoS para o local Redmond, você precisará fazer isso usando as definições de configuração de mídia aplicada a este site.



</div>

Se você deseja habilitar simultaneamente a QoS para todas as suas definições de configuração de mídia (independentemente do escopo), execute este comando no Shell de gerenciamento do Lync Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows definindo o valor da propriedade EnableQoS como false. Por exemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Isto oferece a habilidade de implementar o QoS em algumas partes da sua rede (por exemplo, no local Redmond) enquanto deixa a Qualidade do Serviço desabilitada em outras partes da sua rede.

A QoS só pode ser habilitada e desabilitada usando o Windows PowerShell essas opções não estão disponíveis no painel de controle do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

