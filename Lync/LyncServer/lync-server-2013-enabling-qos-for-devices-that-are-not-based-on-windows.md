---
title: 'Lync Server 2013: Habilitando a QoS para dispositivos que não são baseados no Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Habilitando a QoS no Lync Server 2013 para dispositivos que não são baseados no Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Quando você instala o Microsoft Lync Server 2013, a qualidade do serviço (QoS) não será habilitada para nenhum dispositivo usado em sua organização que use um sistema operacional diferente do Windows. Você pode verificar isso executando o seguinte comando no Shell de gerenciamento do Lync Server 2013:

    Get-CsMediaConfiguration

Presumindo que você não fez alterações nas configurações de sua configuração de mídia, você deve obter informações semelhantes a esta:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se a propriedade EnableQoS estiver definida como false (como na saída anterior), isso significa que a qualidade do serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows. A QoS é habilitada por padrão para os dispositivos do Lync Phone Edition; no entanto, é possível desabilitar a qualidade do serviço para o Lync Phone Edition.

Para habilitar a qualidade de serviço no escopo global, execute o seguinte comando no Shell de gerenciamento do Lync Server:

    Set-CsMediaConfiguration -EnableQoS $True

O comando anterior permite QoS no escopo global; no entanto, é importante observar que as configurações de configuração de mídia também podem ser aplicadas ao escopo do site. Se você precisar habilitar a qualidade do serviço para um site, deve incluir a identidade das configurações ao chamar Set-CsMediaConfiguration. Por exemplo, esse comando habilita a QoS para o site Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Você precisa habilitar a QoS no escopo do site? Isso depende. As configurações atribuídas ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global. Suponha que você tenha o QoS habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond.) Nesse caso, a qualidade do serviço será desabilitada para o site de Redmond; Isso porque as configurações do site têm precedência. Para habilitar a QoS para o site Redmond, você precisará fazer isso usando as definições de configuração de mídia aplicadas a esse site.



</div>

Se você quiser habilitar simultaneamente a QoS para todas as suas configurações de mídia (independentemente do escopo), execute esse comando dentro do Shell de gerenciamento do Lync Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows definindo o valor da propriedade EnableQoS como false. Por exemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Isso oferece a capacidade de implementar a QoS em algumas partes da rede (por exemplo, no site Redmond), deixando a qualidade do serviço desabilitada em outras partes da sua rede.

A QoS só pode ser habilitada e desabilitada usando o Windows PowerShell essas opções não estão disponíveis no painel de controle do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

