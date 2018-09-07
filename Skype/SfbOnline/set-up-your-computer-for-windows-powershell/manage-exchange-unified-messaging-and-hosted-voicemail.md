---
title: Gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use o PowerShell para gerenciar recursos de Unificação de mensagens do Exchange, como o atendedor automático e acesso ao assinante e caixa postal hospedada no Skype para negócios Online.
ms.openlocfilehash: 10c1891272a81731c94e5f0f459bb91e532e8387
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849789"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="59b1b-103">Gerenciar a Unificação de Mensagens do Exchange e a caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="59b1b-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="59b1b-104">Você pode gerenciar a Unificação de mensagens do Exchange e hospedado de caixa postal na Skype para Business Online por meio de um conjunto de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="59b1b-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="59b1b-105">Gerenciar o Exchange unificada messaging e hospedadas de caixa postal</span><span class="sxs-lookup"><span data-stu-id="59b1b-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="59b1b-106">Os cmdlets a seguir podem ser usados para gerenciar o Exchange Unified Messaging (UM) e diretivas de caixa postal hospedada:</span><span class="sxs-lookup"><span data-stu-id="59b1b-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="59b1b-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="59b1b-107">**Cmdlet**</span></span>|<span data-ttu-id="59b1b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="59b1b-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="59b1b-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="59b1b-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="59b1b-110">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="59b1b-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="59b1b-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="59b1b-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="59b1b-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="59b1b-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="59b1b-113">Cria e gerencia os objetos de contato usados para serviços de atendedor automático e acesso do assinante, quando o UM do Exchange é um serviço hospedado.</span><span class="sxs-lookup"><span data-stu-id="59b1b-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="59b1b-114">Skype para Business Online funciona com UM do Exchange para fornecer várias capacidades relacionadas à voz, incluindo o atendedor automático e acesso ao assinante.</span><span class="sxs-lookup"><span data-stu-id="59b1b-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="59b1b-115">Atendedor automático oferece uma maneira para chamadas automaticamente ser atendida e roteadas para a pessoa correta.</span><span class="sxs-lookup"><span data-stu-id="59b1b-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="59b1b-116">Acesso ao assinante permite aos usuários se conectar a UM do Exchange e recuperar mensagens de voz, email, contatos e informações de calendário.</span><span class="sxs-lookup"><span data-stu-id="59b1b-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="59b1b-117">Quando UM do Exchange é fornecido como um serviço hospedado, usados para os serviços de atendedor automático e acesso ao assinante de objetos de contato devem ser criados usando o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59b1b-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="59b1b-118">Esses objetos são criados e gerenciados usando os cmdlets **CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="59b1b-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
|[<span data-ttu-id="59b1b-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="59b1b-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="59b1b-120">Grant-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="59b1b-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="59b1b-121">Gerencia políticas de caixa postal hospedada usadas na organização.</span><span class="sxs-lookup"><span data-stu-id="59b1b-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="59b1b-122">As políticas de caixa postal hospedada especificam como respondidas são roteadas para o serviço UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="59b1b-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="59b1b-123">Essas diretivas afetam somente os usuários que tiverem sido habilitados para UM do Exchange hospedado de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="59b1b-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="59b1b-124">Para verificar se um usuário está habilitado para caixa postal hospedada, execute um comando semelhante ao seguinte prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59b1b-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="59b1b-125">' Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="59b1b-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="59b1b-126">Select-Object HostedVoiceMail'</span><span class="sxs-lookup"><span data-stu-id="59b1b-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="59b1b-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="59b1b-127">Related topics</span></span>
[<span data-ttu-id="59b1b-128">Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59b1b-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 