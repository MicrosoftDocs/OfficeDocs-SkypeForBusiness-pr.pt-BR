---
title: Habilitando QoS para dispositivos não baseado no Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Saiba como habilitar a QoS para dispositivos usados em sua organização que usam um sistema operacional diferente do Windows.
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279407"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Habilitando a QoS no Skype for Business Server para dispositivos que não são baseados no Windows


Quando você instala o Skype for Business Server, a qualidade do serviço (QoS) não será habilitada para nenhum dispositivo usado em sua organização que use um sistema operacional diferente do Windows. Você pode verificar isso executando o seguinte comando no Shell do Skype for Business ServerManagement:

    Get-CsMediaConfiguration

Presumindo que você não fez alterações em suas configurações de configuração de mídia, você deve obter informações semelhantes a esta:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se a propriedade EnableQoS estiver definida como false (como na saída anterior), isso significa que a qualidade do serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows.

Para habilitar a qualidade de serviço no escopo global, execute o seguinte comando no Shell de gerenciamento do Skype for Business Server:

    Set-CsMediaConfiguration -EnableQoS $True

O comando anterior permite QoS no escopo global; no entanto, é importante observar que as configurações de configuração de mídia também podem ser aplicadas ao escopo do site. Se precisar habilitar a qualidade do serviço para um site, você deve incluir a identidade das configurações ao chamar Set-CsMediaConfiguration. Por exemplo, esse comando habilita a QoS para o site Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Você precisa habilitar a QoS no escopo do site? Isso depende. As configurações atribuídas ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global. Suponha que você tenha o QoS habilitado no escopo global, mas desabilitado no escopo do site (para o site de Redmond). Nesse caso, a qualidade do serviço seria desabilitada para o site de Redmond; Isso porque as configurações do site têm precedência. Para habilitar a QoS para o site Redmond, você precisaria fazê-lo usando as definições de configuração de mídia aplicadas a esse site.


Se você quiser habilitar simultaneamente a QoS para todas as suas configurações de mídia (independentemente do escopo), execute esse comando dentro do Shell de gerenciamento do LSkype for Business Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows definindo o valor da propriedade EnableQoS como false. Por exemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Isso oferece a capacidade de implementar a QoS em algumas partes da rede (por exemplo, no site Redmond), deixando a qualidade do serviço desabilitada em outras partes da sua rede.

A QoS só pode ser habilitada e desabilitada usando o Windows PowerShell. Essas opções não estão disponíveis no painel de controle do Skype for Business Server.


