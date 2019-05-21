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
ms.openlocfilehash: 161bda3cb02bf6208b4db9f1c6825d3fe433eeca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279288"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="f2412-103">Monitorar, iniciar e parar serviços de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f2412-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f2412-104">**Resumo:** Saiba como iniciar, parar e monitorar os serviços de chat persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f2412-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f2412-105">Os serviços de chat persistente e os serviços de conformidade de chat persistente fazem parte da topologia do Skype for Business Server e, portanto, podem ser monitorados, interrompidos e iniciados usando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f2412-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f2412-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="f2412-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="f2412-107">Retorna informações detalhadas sobre os componentes do Skype for Business Server 2015 executados como serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="f2412-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="f2412-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="f2412-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="f2412-109">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="f2412-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="f2412-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="f2412-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="f2412-111">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="f2412-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="f2412-112">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f2412-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f2412-113">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2412-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="f2412-114">Para obter mais informações, consulte [jornada do Skype for Business para o Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="f2412-114">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="f2412-115">Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f2412-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="f2412-116">Para obter informações detalhadas sobre como usar os cmdlets, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="f2412-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

