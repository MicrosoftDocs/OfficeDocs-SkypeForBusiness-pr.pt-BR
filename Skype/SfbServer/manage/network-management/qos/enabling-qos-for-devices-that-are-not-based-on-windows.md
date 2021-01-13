---
title: Habilitando QoS para dispositivos não baseado no Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Saiba como habilitar a QoS para dispositivos usados em sua organização que usam um sistema operacional diferente do Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814171"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Habilitando a QoS no Skype for Business Server para dispositivos que não são baseados no Windows


Quando você instala o Skype for Business Server, a QoS (Qualidade de Serviço) não será habilitada para dispositivos usados em sua organização que usem um sistema operacional diferente do Windows. Você pode verificar isso executando o seguinte comando no Shell do Skype for Business ServerManagement:

    Get-CsMediaConfiguration

Supondo que você não tenha feito alterações em suas definições de configuração de mídia, você deve obter informações semelhantes a esta:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se a propriedade EnableQoS estiver definida como False (como na saída anterior), isso significa que a Qualidade de Serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows.

Para habilitar a Qualidade de Serviço no escopo global, execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server:

    Set-CsMediaConfiguration -EnableQoS $True

O comando anterior habilita o QoS no escopo global; no entanto, é importante observar que as definições de configuração de mídia também podem ser aplicadas ao escopo local. Se for necessário habilitar a Qualidade de Serviço para um site, inclua a Identidade das definições de configuração ao chamar Set-CsMediaConfiguration. Por exemplo, este comando habilita o QoS para o site Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Você precisa habilitar a QoS no escopo do site? Isso depende. As configurações atribuídas ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global. Suponha que você tenha a QoS habilitada no escopo global, mas desabilitada no escopo do site (para o site Redmond). Nesse caso, a Qualidade de Serviço seria desabilitada para o site Redmond; isso porque as configurações do site têm precedência. Para habilitar a QoS para o site redmond, você teria que fazer isso usando as definições de configuração de mídia aplicadas a esse site.


Se você quiser habilitar simultaneamente a QoS para todas as definições de configuração de mídia (independentemente do escopo), execute este comando no Shell de Gerenciamento do LSkype for Business Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente do Windows definindo o valor da propriedade EnableQoS como False. Por exemplo:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Isto oferece a habilidade de implementar o QoS em algumas partes da sua rede (por exemplo, no local Redmond) enquanto deixa a Qualidade do Serviço desabilitada em outras partes da sua rede.

A QoS só pode ser habilitada e desabilitada usando o Windows PowerShell. Essas opções não estão disponíveis no Painel de Controle do Skype for Business Server.

> [!NOTE]
> Os clientes do Skype for Business para iOS versão 6.17 e posterior agora são suportados para QoS.  Esse recurso de QoS só é aplicável aos clientes do Skype for Business e dispositivos de telefone IP que são registrados diretamente em um Skype for Business interno ou servidor de pool do Lync em redes gerenciadas. A QoS não é aplicável ao tráfego roteado pela Internet.



