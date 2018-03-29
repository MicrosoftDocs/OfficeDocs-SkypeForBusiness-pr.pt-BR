---
title: Exibir informações sobre troncos SIP individuais no Skype for Business Server 2015
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumo: Saiba como exibir informações sobre troncos SIP no Skype para Business Server 2015.'
ms.openlocfilehash: c307d4e9b18b7ff5fda8d8d0deaa4eb88ba5b6b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a>Exibir informações sobre troncos SIP individuais no Skype for Business Server 2015
 
**Resumo:** Saiba como exibir informações sobre troncos SIP no Skype para Business Server 2015.
  
Troncos SIP são usados para conectar o Skype para Business Server voz pela rede de telefone IP com a comutação telefônica PSTN (rede pública). Na versão anterior do produto, os troncos foram usados para rotear chamadas de saída de um Servidor de Mediação para um gateway PSTN e cada gateway estava limitado a um único tronco. Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos. Para os administradores, isso significava que seria possível exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.
  
Em Skype para Business Server, no entanto, vários troncos podem agora ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não estão mais o mesmo. Por sua vez, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) para exibir informações sobre um tronco SIP individual.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Para visualizar as informações de todos os seus troncos SIP

- O seguinte comando retorna informações sobre todos os troncos SIP usados em sua organização:
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Para visualizar as informações de um tronco SIP específico

- Este comando retorna informações somente para o tronco SIP com a Identidade PstnGateway:192.168.0.240:
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Exibir informações de todos os troncos SIP atribuídos a um pool

- Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```


