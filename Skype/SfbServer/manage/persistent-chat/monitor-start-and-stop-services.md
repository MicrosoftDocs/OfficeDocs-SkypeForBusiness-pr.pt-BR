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
ms.openlocfilehash: 272ea0f4270b1109ff77b5d809472051705b6f10
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20991586"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="9b4c9-103">Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9b4c9-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9b4c9-104">**Resumo:** Saiba como iniciar, interromper e monitorar os serviços de Chat persistente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9b4c9-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9b4c9-105">Os serviços de Chat persistente e conformidade de Chat persistente fazem parte do Skype para a topologia de servidor de negócios e pode, portanto, ser monitorados, interrompido e iniciados usando os cmdlets a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b4c9-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9b4c9-106">Get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="9b4c9-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="9b4c9-107">Retorna informações detalhadas sobre Skype para componentes de negócios Server 2015 que são executados como serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="9b4c9-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="9b4c9-108">Start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="9b4c9-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="9b4c9-109">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="9b4c9-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="9b4c9-110">Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="9b4c9-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="9b4c9-111">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="9b4c9-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="9b4c9-112">Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9b4c9-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9b4c9-113">A mesma funcionalidade está disponível em equipes.</span><span class="sxs-lookup"><span data-stu-id="9b4c9-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="9b4c9-114">Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="9b4c9-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="9b4c9-115">Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9b4c9-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="9b4c9-116">Para obter informações detalhadas sobre como usar os cmdlets, consulte [Skype do Shell de gerenciamento do Business Server 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="9b4c9-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

