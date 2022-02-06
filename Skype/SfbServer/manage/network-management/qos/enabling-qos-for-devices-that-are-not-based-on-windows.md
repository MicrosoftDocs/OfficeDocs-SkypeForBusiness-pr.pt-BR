---
title: Habilitando QoS para dispositivos não baseado no Windows
ms.reviewer: null
'ms:assetid': 26f793df-aef8-4028-9e3b-6c2c37ea61b9
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)'
'ms:contentKeyID': 48183661
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: Saiba como habilitar a QoS para dispositivos usados em sua organização que usam um sistema operacional diferente do Windows.
---

# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Habilitando a QoS Skype for Business Server dispositivos que não se baseiam em Windows


Ao instalar o Skype for Business Server, a Qualidade do Serviço (QoS) não será habilitada para quaisquer dispositivos usados em sua organização que usem um sistema operacional diferente do Windows. Você pode verificar isso executando o seguinte comando no shell Skype for Business ServerManagement:

**Get-CsMediaConfiguration**

Supondo que você não tenha feito alterações nas configurações de mídia, você deve obter informações semelhantes a esta:

Identidade : Global<br/>
EnableQoS : False<br/>
EncryptionLevel : RequireEncryption<br/>
EnableSiren : False<br/>
MaxVideoRateAllowed : VGA600K<br/>
EnableG722StereoCodec : True<br/>
EnableH264Codec : True<br/>
EnableAdaptiveBandwidthEstimation : True<br/>

Se a propriedade EnableQoS estiver definida como False (como na saída anterior), isso significa que a Qualidade do Serviço não está habilitada para computadores e dispositivos que usam um sistema operacional diferente do Windows.

Para habilitar a Qualidade do Serviço no escopo global, execute o seguinte comando de dentro do Shell de Gerenciamento Skype for Business Server gerenciamento:

**Set-CsMediaConfiguration -EnableQoS $True**

O comando anterior habilita o QoS no escopo global; no entanto, é importante observar que as definições de configuração de mídia também podem ser aplicadas ao escopo local. Se você precisar habilitar a Qualidade do Serviço para um site, inclua a Identidade das configurações ao chamar Set-CsMediaConfiguration. Por exemplo, este comando habilita o QoS para o site Redmond:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True**


> [!NOTE]
> Você precisa habilitar a QoS no escopo do site? Isso depende. Configurações atribuído ao escopo do site têm precedência sobre as configurações atribuídas ao escopo global. Suponha que você tenha a QoS habilitada no escopo global, mas desabilitada no escopo do site (para o site redmond). Nesse caso, a Qualidade do Serviço seria desabilitada para o site redmond; isso porque as configurações do site têm precedência. Para habilitar a QoS para o site redmond, você teria que fazer isso usando as configurações de mídia aplicadas a esse site.


Se você quiser habilitar simultaneamente a QoS para todas as configurações de mídia (independentemente do escopo), execute este comando de dentro do Shell de Gerenciamento do LSkype for Business Server:

**Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True**

Você pode desabilitar a QoS para dispositivos que usam um sistema operacional diferente Windows definindo o valor da propriedade EnableQoS como False. Por exemplo:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False**

Isto oferece a habilidade de implementar o QoS em algumas partes da sua rede (por exemplo, no local Redmond) enquanto deixa a Qualidade do Serviço desabilitada em outras partes da sua rede.

A QoS só pode ser habilitada e desabilitada usando Windows PowerShell. Essas opções não estão disponíveis no Painel Skype for Business Server Controle.

> [!NOTE]
> Skype for Business clientes para iOS Versão 6.17 e posterior agora suportam QoS.  Esse recurso QoS só é aplicável Skype for Business clientes e dispositivos de telefone IP que são registrados diretamente em um servidor de pool interno Skype for Business ou Lync em redes gerenciadas. A QoS não é aplicável ao tráfego roteado pela Internet.
