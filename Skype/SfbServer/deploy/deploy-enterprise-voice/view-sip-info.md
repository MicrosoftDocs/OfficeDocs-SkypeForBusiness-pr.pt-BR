---
title: Exibir informações de tronco SIP em Skype for Business Server
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumo: saiba como exibir informações sobre troncos SIP em Skype for Business Server.'
ms.openlocfilehash: bbb1a08252240341ceb6e27181dce999753924c897d470a182341be4178ae2a4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304463"
---
# <a name="skype-for-business-server-view-information-about-individual-sip-trunks"></a>Skype for Business Server: Exibir informações sobre troncos SIP individuais 
 
**Resumo:** Saiba como exibir informações sobre troncos SIP em Skype for Business Server.
  
Troncos SIP são usados para conectar Skype for Business Server rede telefônica De Voz sobre IP com a PSTN (Rede Telefônica Pública Comugada). Na versão anterior do produto, os troncos eram usados para rotear chamadas de saída de um Servidor de Mediação para um gateway PSTN e cada gateway era limitado a um único tronco. Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos. Para administradores, isso significava que eles podiam exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.
  
No Skype for Business Server, no entanto, vários troncos agora podem ser atribuídos a um único gateway PSTN; isso significa que gateways e troncos não são mais um e o mesmo. Por sua vez, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](/powershell/module/skype/get-cstrunk) para exibir informações sobre um tronco SIP individual.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Para exibir informações de todos os troncos SIP

- O comando a seguir retorna informações sobre todos os troncos SIP em uso em sua organização:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Para exibir informações de um tronco SIP específico

- Este comando retorna informações apenas para o tronco SIP com Identity PstnGateway:192.168.0.240:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Exibir informações de todos os troncos SIP atribuídos a um pool

- Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
