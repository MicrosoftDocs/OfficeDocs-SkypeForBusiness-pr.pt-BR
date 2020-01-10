---
title: Exibir informações sobre troncos SIP individuais no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumo: saiba como exibir informações sobre troncos SIP no Skype for Business Server.'
ms.openlocfilehash: 366e03c1a3ceef345a52bca6e038c9311fcc3003
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001121"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Exibir informações sobre troncos SIP individuais no Skype for Business Server
 
**Resumo:** Saiba como exibir informações sobre troncos SIP no Skype for Business Server.
  
Os troncos SIP são usados para conectar a rede de telefone de voz do Skype for Business Server à rede telefônica pública comutada (PSTN). Na versão anterior do produto, os troncos foram usados para rotear chamadas de saída de um Servidor de Mediação para um gateway PSTN e cada gateway estava limitado a um único tronco. Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos. Para os administradores, isso significava que seria possível exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.
  
No entanto, no Skype for Business Server, vários troncos agora podem ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não são mais um e iguais. Por outro lado, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) para exibir informações sobre um tronco SIP individual.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Para visualizar as informações de todos os seus troncos SIP

- O seguinte comando retorna informações sobre todos os troncos SIP usados em sua organização:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Para visualizar as informações de um tronco SIP específico

- Este comando retorna informações somente para o tronco SIP com a Identidade PstnGateway:192.168.0.240:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Exibir informações de todos os troncos SIP atribuídos a um pool

- Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
