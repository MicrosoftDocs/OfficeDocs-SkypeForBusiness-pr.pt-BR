---
title: Skype for Business Server - Testar configurações de tronco SIP
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PST), um PBX ou um SBC no provedor de serviços. '
ms.openlocfilehash: e0d8a5807f97924c0b733d75065f0ce3d512255e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765359"
---
# <a name="skype-for-business-server---test-sip-trunk-configuration-settings"></a>Skype for Business Server - Testar configurações de tronco SIP

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:

- Se o bypass de mídia deve ser habilitado nos troncos.
- As condições nas quais os pacotes RTCP são enviados.
- Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) para verificar se um tronco pode converter um número conforme discado por um usuário em um número que pode ser manipulado pelo gateway.

As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet Test-CsTrunkConfiguration. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 

**Para testar as configurações do tronco SIP**

Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
