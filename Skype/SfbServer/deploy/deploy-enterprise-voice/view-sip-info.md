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
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="f63b8-103">Exibir informações sobre troncos SIP individuais no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f63b8-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="f63b8-104">**Resumo:** Saiba como exibir informações sobre troncos SIP no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f63b8-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="f63b8-105">Os troncos SIP são usados para conectar a rede telefônica IP do Skype for Business Server Voice com a Rede Telefônica Pública Comuada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="f63b8-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="f63b8-106">Na versão anterior do produto, os troncos eram usados para rotear chamadas de saída de um Servidor de Mediação para um gateway PSTN e cada gateway estava limitado a um único tronco.</span><span class="sxs-lookup"><span data-stu-id="f63b8-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="f63b8-107">Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos.</span><span class="sxs-lookup"><span data-stu-id="f63b8-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="f63b8-108">Para os administradores, isso significa que eles poderiam exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.</span><span class="sxs-lookup"><span data-stu-id="f63b8-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="f63b8-109">No Skype for Business Server, no entanto, vários troncos agora podem ser atribuídos a um único gateway PSTN; Isso significa que gateways e troncos não são mais os mesmos.</span><span class="sxs-lookup"><span data-stu-id="f63b8-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="f63b8-110">Por sua vez, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) para exibir informações sobre um tronco SIP individual.</span><span class="sxs-lookup"><span data-stu-id="f63b8-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="f63b8-111">Para exibir informações de todos os troncos SIP</span><span class="sxs-lookup"><span data-stu-id="f63b8-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="f63b8-112">O comando a seguir retorna informações sobre todos os troncos SIP em uso na organização:</span><span class="sxs-lookup"><span data-stu-id="f63b8-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="f63b8-113">Para exibir informações de um tronco SIP específico</span><span class="sxs-lookup"><span data-stu-id="f63b8-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="f63b8-114">Este comando retorna informações apenas para o tronco SIP com a Identidade PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="f63b8-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="f63b8-115">Exibir informações de todos os troncos SIP atribuídos a um pool</span><span class="sxs-lookup"><span data-stu-id="f63b8-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="f63b8-116">Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="f63b8-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
