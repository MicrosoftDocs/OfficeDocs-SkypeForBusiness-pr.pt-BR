---
title: Exibir informações sobre troncos SIP individuais no Skype for Business Server
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
description: 'Resumo: saiba como exibir informações sobre troncos SIP no Skype for Business Server.'
ms.openlocfilehash: 29a5a025589f4df7d99b8bf708bf8bd67d0f138f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830521"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Exibir informações sobre troncos SIP individuais no Skype for Business Server
 
**Resumo:** Saiba como exibir informações sobre troncos SIP no Skype for Business Server.
  
Os troncos SIP são usados para conectar a rede telefônica IP do Skype for Business Server Voice com a Rede Telefônica Pública Comuada (PSTN). Na versão anterior do produto, os troncos eram usados para rotear chamadas de saída de um Servidor de Mediação para um gateway PSTN e cada gateway estava limitado a um único tronco. Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos. Para os administradores, isso significa que eles poderiam exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.
  
No Skype for Business Server, no entanto, vários troncos agora podem ser atribuídos a um único gateway PSTN; Isso significa que gateways e troncos não são mais os mesmos. Por sua vez, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) para exibir informações sobre um tronco SIP individual.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Para exibir informações de todos os troncos SIP

- O comando a seguir retorna informações sobre todos os troncos SIP em uso na organização:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Para exibir informações de um tronco SIP específico

- Este comando retorna informações apenas para o tronco SIP com a Identidade PstnGateway:192.168.0.240:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Exibir informações de todos os troncos SIP atribuídos a um pool

- Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
