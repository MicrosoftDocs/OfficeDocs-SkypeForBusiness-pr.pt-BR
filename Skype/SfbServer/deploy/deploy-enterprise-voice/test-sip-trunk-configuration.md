---
title: 'Skype for Business Server: Testar configurações de tronco SIP'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumo: saiba como testar as configurações de tronco SIP usando o Shell de Gerenciamento Skype for Business Server.'
ms.openlocfilehash: 59f246abfc4ef27ad75ab45cccaedc6f5236c98e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829505"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype for Business Server: Testar configurações de tronco SIP
 
**Resumo:** Saiba como testar as configurações de tronco SIP usando o Shell de Gerenciamento Skype for Business Server.
  
As configurações de tronco SIP definem a relação e os recursos entre um Servidor de Mediação e o gateway PSTN (Rede Telefônica Pública Comutado), um PBX (Branch eXchange) do IP-Public ou um Controlador de Borda de Sessão (SBC) no provedor de serviços. Estas configurações fazem coisas como especificar:
  
- Se o bypass de mídia deve ser habilitado nos troncos
    
- As condições sob as quais pacotes RTCP (Protocolo de Controle de Transporte em Tempo Real) são enviados
    
- Se a criptografia SRTP (Protocolo de Transporte de Tempo Real Seguro) é necessária em cada tronco
    
Quando você instala Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar se um tronco pode converter um número conforme discado por um usuário em um número que o gateway pode manipular.
  
As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration). Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota do Shell de Gerenciamento Skype for Business Server Gerenciamento.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Para testar as configurações do tronco SIP

- Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
