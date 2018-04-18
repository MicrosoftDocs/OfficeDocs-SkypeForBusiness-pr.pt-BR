---
title: Gerenciar a Unificação de mensagens do Exchange e hospedadas de caixa postal
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use o PowerShell para gerenciar recursos de Unificação de mensagens do Exchange, como o atendedor automático e acesso ao assinante e caixa postal hospedada no Skype para negócios Online.
ms.openlocfilehash: 33fe3c7a3c19916a8a70008f467035c832e5ecb3
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a><span data-ttu-id="f7360-103">Gerenciar a Unificação de mensagens do Exchange e hospedadas de caixa postal</span><span class="sxs-lookup"><span data-stu-id="f7360-103">Manage Exchange Unified Messaging and hosted voicemail</span></span>

<span data-ttu-id="f7360-104">Você pode gerenciar a Unificação de mensagens do Exchange e hospedado de caixa postal na Skype para Business Online por meio de um conjunto de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f7360-104">You can manage Exchange Unified Messaging and hosted voicemail in Skype for Business Online by using a set of cmdlets.</span></span>
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a><span data-ttu-id="f7360-105">Gerenciar o Exchange unificada messaging e hospedadas de caixa postal</span><span class="sxs-lookup"><span data-stu-id="f7360-105">Manage Exchange unified messaging and hosted voice mail</span></span>

<span data-ttu-id="f7360-106">Os cmdlets a seguir podem ser usados para gerenciar o Exchange Unified Messaging (UM) e diretivas de caixa postal hospedada:</span><span class="sxs-lookup"><span data-stu-id="f7360-106">The following cmdlets can be used to manage Exchange Unified Messaging (UM) and hosted voicemail policies:</span></span>
  
|<span data-ttu-id="f7360-107">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="f7360-107">**Cmdlet**</span></span>|<span data-ttu-id="f7360-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f7360-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="f7360-109">Get-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="f7360-109">Get-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [<span data-ttu-id="f7360-110">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="f7360-110">New-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[<span data-ttu-id="f7360-111">Remove-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="f7360-111">Remove-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[<span data-ttu-id="f7360-112">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="f7360-112">Set-CsExUmContact</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> |<span data-ttu-id="f7360-113">Cria e gerencia os objetos de contato usados para serviços de atendedor automático e acesso do assinante, quando o UM do Exchange é um serviço hospedado.</span><span class="sxs-lookup"><span data-stu-id="f7360-113">Creates and manages contact objects used for Auto Attendant and Subscriber Access services, when Exchange UM is a hosted service.</span></span>  <br/><br/> <span data-ttu-id="f7360-114">Skype para Business Online funciona com UM do Exchange para fornecer várias capacidades relacionadas à voz, incluindo o atendedor automático e acesso ao assinante.</span><span class="sxs-lookup"><span data-stu-id="f7360-114">Skype for Business Online works with Exchange UM to provide several voice-related capabilities, including Auto Attendant and Subscriber Access.</span></span> <span data-ttu-id="f7360-115">Atendedor automático oferece uma maneira para chamadas automaticamente ser atendida e roteadas para a pessoa correta.</span><span class="sxs-lookup"><span data-stu-id="f7360-115">Auto Attendant provides a way for calls to automatically be answered and routed to the correct person.</span></span> <span data-ttu-id="f7360-116">Acesso ao assinante permite aos usuários se conectar a UM do Exchange e recuperar mensagens de voz, email, contatos e informações de calendário.</span><span class="sxs-lookup"><span data-stu-id="f7360-116">Subscriber Access enables users to connect to Exchange UM and retrieve email, voice messages, contacts, and calendar information.</span></span>  <br/><br/> <span data-ttu-id="f7360-117">Quando UM do Exchange é fornecido como um serviço hospedado, usados para os serviços de atendedor automático e acesso ao assinante de objetos de contato devem ser criados usando o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7360-117">When Exchange UM is provided as a hosted service, contact objects used for the Auto Attendant and Subscriber Access services must be created by using Microsoft PowerShell.</span></span> <span data-ttu-id="f7360-118">Esses objetos são criados e gerenciados usando os cmdlets **CsExUmContact** .</span><span class="sxs-lookup"><span data-stu-id="f7360-118">These objects are created and managed by using the **CsExUmContact** cmdlets.</span></span> <br/> |
|[<span data-ttu-id="f7360-119">Get-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f7360-119">Get-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[<span data-ttu-id="f7360-120">Grant-CSHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f7360-120">Grant-CSHostedVoicemailPolicy</span></span>](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/> |<span data-ttu-id="f7360-121">Gerencia políticas de caixa postal hospedada usadas na organização.</span><span class="sxs-lookup"><span data-stu-id="f7360-121">Manages hosted voicemail policies used in the organization.</span></span> <span data-ttu-id="f7360-122">As políticas de caixa postal hospedada especificam como respondidas são roteadas para o serviço UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f7360-122">Hosted voicemail policies specify how unanswered calls are routed to the Exchange UM service.</span></span> <span data-ttu-id="f7360-123">Essas diretivas afetam somente os usuários que tiverem sido habilitados para UM do Exchange hospedado de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="f7360-123">These policies affect only users who have been enabled for Exchange UM hosted voicemail.</span></span>  <br/><br/> <span data-ttu-id="f7360-124">Para verificar se um usuário está habilitado para caixa postal hospedada, execute um comando semelhante ao seguinte prompt do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7360-124">To verify whether a user is enabled for hosted voicemail, run a command similar to the following from the PowerShell prompt.</span></span>  <br/> <span data-ttu-id="f7360-125">' Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="f7360-125">\`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"</span></span> | <span data-ttu-id="f7360-126">Select-Object HostedVoiceMail'</span><span class="sxs-lookup"><span data-stu-id="f7360-126">Select-Object HostedVoiceMail\`</span></span>|
   

## <a name="related-topics"></a><span data-ttu-id="f7360-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f7360-127">Related topics</span></span>
[<span data-ttu-id="f7360-128">Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7360-128">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 