---
title: Testar as definições de configuração do tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumo: Saiba como testar as definições de configuração do tronco SIP usando o Shell de Gerenciamento do Skype for Business Server.'
ms.openlocfilehash: 8b3a98d54fd0d2dc8bb69e553e0c0a3a7b98b1ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830631"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testar as definições de configuração do tronco SIP no Skype for Business Server
 
**Resumo:** Saiba como testar as definições de configuração do tronco SIP usando o Shell de Gerenciamento do Skype for Business Server.
  
As definições de configuração do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway PSTN (Rede Telefônica Pública Comutado), um PBX (Branch eXchange) da IP-Public ou um Controlador de Borda de Sessão (SBC) no provedor de serviços. Estas configurações fazem coisas como especificar:
  
- Se o bypass de mídia deve ser habilitado nos troncos.
    
- As condições sob as quais pacotes RTCP (Protocolo de Controle de Transporte em Tempo Real) são enviados.
    
- Se a criptografia SRTP (Secure Realtime Transport Protocol) é necessária ou não em cada tronco.
    
Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar que um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.
  
As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Shell de Gerenciamento do Skype for Business Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Para testar as definições de configuração do tronco SIP

- Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


