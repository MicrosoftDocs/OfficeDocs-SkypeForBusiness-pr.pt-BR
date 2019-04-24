---
title: Testar configurações de tronco SIP no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços. '
ms.openlocfilehash: 3f251ea720ab220ccda0cfe9882d4a8396085aa0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214621"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testar configurações de tronco SIP no Skype para Business Server

Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços. Essas configurações realizam atividades como especificar:

- Se o desvio de mídia deve ser ativado nos troncos.
- As condições nas quais os pacotes RTCP (protocolo) de controle de transporte em tempo real são enviados.
- Ou não a criptografia do protocolo em tempo real seguro (SRTP) é necessário em cada tronco.

Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) para verificar se um tronco pode converter um número como discado por um usuário para um número que pode ser manipulado pelo gateway.

As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet  Test-CsTrunkConfiguration. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

**Testar as definições da configuração do Tronco SIP**

Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
