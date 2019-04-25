---
title: Testar configurações de tronco SIP no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumo: Saiba como testar configurações de tronco SIP usando o Skype do Shell de gerenciamento do servidor de negócios.'
ms.openlocfilehash: d602f24c3342e6c8460cab41d5f14e68ba17188b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222846"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testar configurações de tronco SIP no Skype para Business Server
 
**Resumo:** Saiba como testar configurações de tronco SIP usando o Skype do Shell de gerenciamento do servidor de negócios.
  
As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:
  
- Se o desvio de mídia deve ser ativado nos troncos.
    
- As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.
    
- Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.
    
Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar se um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.
  
As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet  [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Testar as definições da configuração do Tronco SIP

- Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


