---
title: Testar configurações de tronco SIP no Skype for Business Server
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
description: 'Resumo: saiba como testar as configurações de tronco SIP usando o Shell de Gerenciamento do Skype for Business Server.'
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103367"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testar configurações de tronco SIP no Skype for Business Server
 
**Resumo:** Saiba como testar as configurações de tronco SIP usando o Shell de Gerenciamento do Skype for Business Server.
  
As configurações de tronco SIP definem a relação e os recursos entre um Servidor de Mediação e o gateway PSTN (Rede Telefônica Pública Comutado), um PBX (Branch eXchange) do IP-Public ou um Controlador de Borda de Sessão (SBC) no provedor de serviços. Estas configurações fazem coisas como especificar:
  
- Se o bypass de mídia deve ser habilitado nos troncos.
    
- As condições em que pacotes RTCP (Protocolo de Controle de Transporte em Tempo Real) são enviados.
    
- Se a criptografia SRTP (Protocolo de Transporte de Tempo Real Seguro) é necessária ou não em cada tronco.
    
Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Os administradores também podem usar o cmdlet Test-CsTrunkConfiguration para verificar que um tronco pode converter um número conforme discado por um usuário para um número que pode ser tratado pelo gateway.
  
As definições de configuração de tronco podem ser testadas apenas usando o Windows PowerShell e o cmdlet [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Shell de Gerenciamento do Skype for Business Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Para testar as configurações do tronco SIP

- Este comando verifica se as definições de configuração para o local Redmond podem converter corretamente o número discado 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```