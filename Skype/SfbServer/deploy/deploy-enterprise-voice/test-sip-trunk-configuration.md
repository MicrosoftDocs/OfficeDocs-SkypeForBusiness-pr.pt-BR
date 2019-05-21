---
title: Testar as configurações de tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumo: saiba como testar as configurações de configuração de tronco SIP usando o Shell de gerenciamento do Skype for Business Server.'
ms.openlocfilehash: aec88300341f42d5f228c3c13f1a0925b71ce855
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300957"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testar as configurações de tronco SIP no Skype for Business Server
 
**Resumo:** Saiba como testar as definições de configuração de tronco SIP usando o Shell de gerenciamento do Skype for Business Server.
  
As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:
  
- Se o desvio de mídia deve ser ativado nos troncos.
    
- As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.
    
- Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.
    
Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar se um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.
  
As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet  [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Shell de gerenciamento do Skype for Business Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Testar as definições da configuração do Tronco SIP

- Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


