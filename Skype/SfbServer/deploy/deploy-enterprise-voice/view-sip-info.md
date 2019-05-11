---
title: Exibir informações sobre individuais troncos SIP no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumo: Saiba como exibir informações sobre troncos SIP no Skype para Business Server.'
ms.openlocfilehash: a7cf290bf245092e08babcaa86c642dd0f0a4265
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892234"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Exibir informações sobre individuais troncos SIP no Skype para Business Server
 
**Resumo:** Saiba como exibir informações sobre troncos SIP no Skype para Business Server.
  
Troncos SIP são usados para conectar o Skype para Business Server voz pela rede de telefone IP com a comutação telefônica PSTN (rede pública). Na versão anterior do produto, os troncos foram usados para rotear chamadas de saída de um Servidor de Mediação para um gateway PSTN e cada gateway estava limitado a um único tronco. Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos. Para os administradores, isso significava que seria possível exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.
  
Em Skype para Business Server, no entanto, vários troncos podem agora ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não estão mais o mesmo. Por outro lado, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) para exibir informações sobre um tronco SIP individual.
  
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
