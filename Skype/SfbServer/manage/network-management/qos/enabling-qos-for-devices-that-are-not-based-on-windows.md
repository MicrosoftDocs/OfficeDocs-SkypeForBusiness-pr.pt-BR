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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba como habilitar a QoS para dispositivos usados em sua organização que usam um sistema operacional diferente do Windows.
ms.openlocfilehash: 74f964f6156c8b2f2d7a7359193b5dbffe95a011
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817410"
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

> [!NOTE]
> Os clientes do Skype for Business para iOS versão 6,17 e posterior agora dão suporte a QoS.  Esta funcionalidade de QoS só se aplica a clientes do Skype for Business e dispositivos de telefone IP que são registrados diretamente em um servidor de pool interno do Skype for Business ou do Lync em redes gerenciadas. A QoS não se aplica ao tráfego roteado pela Internet.



