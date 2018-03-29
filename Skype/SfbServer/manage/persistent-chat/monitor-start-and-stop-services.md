---
title: Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumo: Saiba como iniciar, interromper e monitorar os serviços de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 47cd6daeca664f7775455818a5690232e92d4c36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="ecdfb-103">Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ecdfb-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ecdfb-104">**Resumo:** Saiba como iniciar, interromper e monitorar os serviços de Chat persistente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ecdfb-105">Os serviços de Chat persistente e conformidade de Chat persistente fazem parte do Skype para a topologia de servidor de negócios e pode, portanto, ser monitorados, interrompido e iniciados usando os cmdlets a seguir:</span><span class="sxs-lookup"><span data-stu-id="ecdfb-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ecdfb-106">Get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="ecdfb-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="ecdfb-107">Retorna informações detalhadas sobre Skype para componentes de negócios Server 2015 que são executados como serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="ecdfb-108">Start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="ecdfb-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="ecdfb-109">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="ecdfb-110">Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="ecdfb-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="ecdfb-111">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="ecdfb-111">Stops the service.</span></span>  <br/> |
   
<span data-ttu-id="ecdfb-112">Para obter informações detalhadas sobre como usar os cmdlets, consulte [Skype do Shell de gerenciamento do Business Server 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ecdfb-112">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

