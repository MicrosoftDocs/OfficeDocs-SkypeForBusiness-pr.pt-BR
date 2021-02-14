---
title: Monitorar, iniciar e interromper os serviços de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Resumo: Saiba como iniciar, parar e monitorar os serviços de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 31285fe5f7eefaa6579f2891a4b29111324de22d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814131"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a><span data-ttu-id="6574d-103">Monitorar, iniciar e interromper os serviços de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6574d-103">Monitor, start, and stop the Persistent Chat services in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6574d-104">**Resumo:** Saiba como iniciar, parar e monitorar os serviços de Chat Persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6574d-104">**Summary:** Learn how to start, stop, and monitor the Persistent Chat services in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6574d-105">Os serviços de Chat Persistente e Conformidade de Chat Persistente fazem parte da topologia do Skype for Business Server e, portanto, podem ser monitorados, interrompidos e iniciados usando os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6574d-105">The Persistent Chat services and Persistent Chat Compliance services are part of the Skype for Business Server topology and can therefore be monitored, stopped, and started by using the following cmdlets:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6574d-106">get-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="6574d-106">get-CsWindowsService</span></span>  <br/> |<span data-ttu-id="6574d-107">Retorna informações detalhadas sobre os componentes do Skype for Business Server 2015 que são executados como serviços do Windows.</span><span class="sxs-lookup"><span data-stu-id="6574d-107">Returns detailed information about Skype for Business Server 2015 components that run as Windows services.</span></span>  <br/> |
|<span data-ttu-id="6574d-108">start-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="6574d-108">start-CsWindowsService</span></span>  <br/> |<span data-ttu-id="6574d-109">Inicia o serviço.</span><span class="sxs-lookup"><span data-stu-id="6574d-109">Starts the service.</span></span>  <br/> |
|<span data-ttu-id="6574d-110">stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="6574d-110">stop-CsWindowsService</span></span>  <br/> |<span data-ttu-id="6574d-111">Interrompe o serviço.</span><span class="sxs-lookup"><span data-stu-id="6574d-111">Stops the service.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="6574d-112">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6574d-112">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6574d-113">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="6574d-113">The same functionality is available in Teams.</span></span> <span data-ttu-id="6574d-114">Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="6574d-114">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="6574d-115">Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6574d-115">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="6574d-116">Para obter informações detalhadas sobre como usar os cmdlets, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="6574d-116">For detailed information about how to use the cmdlets, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

