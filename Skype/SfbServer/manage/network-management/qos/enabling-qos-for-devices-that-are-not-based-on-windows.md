---
title: Habilitando QoS para dispositivos não baseado no Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Aprenda a habilitar o QoS para dispositivos usados em sua organização que usam um sistema operacional diferente do Windows.
ms.openlocfilehash: b1f3dae2d2b499b334995d7754282c56872ce111
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887117"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Habilitando QoS no Skype para Business Server para dispositivos que não são baseados no Windows


Quando você instala o Skype para Business Server, Quality of Service (QoS) não será habilitado para todos os dispositivos usados na sua organização que usam um sistema operacional diferente do Windows. Você pode verificar isso executando o seguinte comando dentro do Skype para negócios ServerManagement Shell:

    Get-CsMediaConfiguration

Supondo que você não tenha feito qualquer alteração para suas definições de configuração de mídia, você deve obter informação semelhante a esta:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se a propriedade EnableQoS estiver definida como False (como a saída anterior) significa que a qualidade do serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows.

Para habilitar o Quality of Service no escopo global, execute o seguinte comando dentro do Skype do Shell de gerenciamento do servidor de negócios:

    Set-CsMediaConfiguration -EnableQoS $True

O comando anterior habilita o QoS no escopo global; No entanto, é importante observar que as definições de configuração de mídia também podem ser aplicadas ao escopo do site. Se você precisar habilitar o Quality of Service para um site, você deve incluir a identidade das definições de configuração ao chamar Set-CsMediaConfiguration. Por exemplo, este comando habilita o QoS para o site Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Você precisa habilitar o QoS no escopo do site? Que depende. Configurações atribuídas ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global. Suponha que você tenha QoS habilitado no escopo global, mas desativada no escopo do site (para o site de Redmond). Nesse caso, Quality of Service seria desativado para o site de Redmond; Isso ocorre porque as definições do site têm precedência. Para habilitar o QoS para o site Redmond, você precisará fazê-lo usando as definições de configuração de mídia aplicada ao site.


Se você deseja habilitar simultaneamente o QoS para todas as suas definições de configuração de mídia (independente do escopo), execute este comando a partir do LSkype do Shell de gerenciamento do servidor de negócios:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows, definindo o valor da propriedade EnableQoS como False. Por exemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Isso oferece a capacidade para implementar o QoS em algumas partes da sua rede (por exemplo, no site de Redmond), deixando Quality of Service desabilitada em outras partes da sua rede.

QoS só possam ser habilitados e desabilitados pelo uso do Windows PowerShell. Essas opções não estão disponíveis no Skype para painel de controle do servidor de negócios.


