---
title: Testar as configurações do tronco SIP no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumo: Saiba como testar configurações de tronco SIP usando o Skype do Shell de gerenciamento do servidor de negócios.'
ms.openlocfilehash: 4e4c0c7ce117143f743dd40536bc49bfce92d978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a>Testar as configurações do tronco SIP no Skype for Business Server 2015
 
**Resumo:** Saiba como testar configurações de tronco SIP usando o Skype do Shell de gerenciamento do servidor de negócios.
  
As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:
  
- Se o desvio de mídia deve ser ativado nos troncos.
    
- As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.
    
- Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.
    
Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar se um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.
  
Definições de configuração de tronco só podem ser testadas usando o Windows PowerShell e o cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) . Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Testar as definições da configuração do Tronco SIP

- Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


