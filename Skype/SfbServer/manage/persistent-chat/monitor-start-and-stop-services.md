---
title: Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumo: saiba como iniciar, parar e monitorar os serviços de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418687"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="96ae8-103">Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96ae8-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="96ae8-104">**Resumo:** Saiba como iniciar, parar e monitorar os serviços de chat persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96ae8-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="96ae8-105">Os serviços de chat persistente e os serviços de conformidade de chat persistente fazem parte da topologia do Skype for Business Server e, portanto, podem ser monitorados, interrompidos e iniciados usando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="96ae8-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="96ae8-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="96ae8-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="96ae8-107">Retorna informações detalhadas sobre os componentes do Skype for Business Server 2015 executados como serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="96ae8-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="96ae8-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="96ae8-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="96ae8-109">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="96ae8-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="96ae8-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="96ae8-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="96ae8-111">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="96ae8-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="96ae8-112">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="96ae8-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="96ae8-113">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="96ae8-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="96ae8-114">Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="96ae8-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="96ae8-115">Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96ae8-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="96ae8-116">Para obter informações detalhadas sobre como usar os cmdlets, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="96ae8-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

