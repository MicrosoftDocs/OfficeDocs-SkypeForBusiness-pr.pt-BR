---
title: Exibir informações sobre individuais troncos SIP no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Resumo: Saiba como exibir informações sobre troncos SIP no Skype para Business Server.'
ms.openlocfilehash: 10f45def1727c083f89afcdba43fb9c1c4e7e45e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968695"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="3e529-103">Exibir informações sobre individuais troncos SIP no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3e529-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="3e529-104">**Resumo:** Saiba como exibir informações sobre troncos SIP no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3e529-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="3e529-105">Troncos SIP são usados para conectar o Skype para Business Server voz pela rede de telefone IP com a comutação telefônica PSTN (rede pública).</span><span class="sxs-lookup"><span data-stu-id="3e529-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="3e529-106">Na versão anterior do produto, os troncos foram usados para rotear chamadas de saída de um Servidor de Mediação para um gateway PSTN e cada gateway estava limitado a um único tronco.</span><span class="sxs-lookup"><span data-stu-id="3e529-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="3e529-107">Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos.</span><span class="sxs-lookup"><span data-stu-id="3e529-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="3e529-108">Para os administradores, isso significava que seria possível exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.</span><span class="sxs-lookup"><span data-stu-id="3e529-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="3e529-109">Em Skype para Business Server, no entanto, vários troncos podem agora ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não estão mais o mesmo.</span><span class="sxs-lookup"><span data-stu-id="3e529-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="3e529-110">Por sua vez, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) para exibir informações sobre um tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="3e529-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="3e529-111">Para visualizar as informações de todos os seus troncos SIP</span><span class="sxs-lookup"><span data-stu-id="3e529-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="3e529-112">O seguinte comando retorna informações sobre todos os troncos SIP usados em sua organização:</span><span class="sxs-lookup"><span data-stu-id="3e529-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="3e529-113">Para visualizar as informações de um tronco SIP específico</span><span class="sxs-lookup"><span data-stu-id="3e529-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="3e529-114">Este comando retorna informações somente para o tronco SIP com a Identidade PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="3e529-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="3e529-115">Exibir informações de todos os troncos SIP atribuídos a um pool</span><span class="sxs-lookup"><span data-stu-id="3e529-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="3e529-116">Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="3e529-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```