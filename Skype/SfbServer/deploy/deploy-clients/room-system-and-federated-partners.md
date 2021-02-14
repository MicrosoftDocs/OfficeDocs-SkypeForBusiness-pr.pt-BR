---
title: Parceiros federados do Skype Room System e Skype for Business
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leia este tópico para saber como configurar o Sistema de Sala do Skype para parceiros federados do Skype for Business.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820801"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="35d56-103">Parceiros federados do Skype Room System e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="35d56-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="35d56-104">Leia este tópico para saber como configurar o Sistema de Sala do Skype para parceiros federados do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="35d56-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="35d56-105">Parceiros federados do Skype Room System e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="35d56-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="35d56-106">O Sistema de Sala do Skype depende do link Ingressar na Reunião do Skype for Business na solicitação de reunião do calendário.</span><span class="sxs-lookup"><span data-stu-id="35d56-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="35d56-107">O link de junção geralmente é encontrado no corpo de uma solicitação de reunião.</span><span class="sxs-lookup"><span data-stu-id="35d56-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="35d56-108">No entanto, o Sistema de Sala do Skype depende desse link para estar presente nas propriedades MAPI da mensagem.</span><span class="sxs-lookup"><span data-stu-id="35d56-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="35d56-109">Quando essa solicitação de reunião é enviada a organizações remotas (parceiros federados do Skype for Business), por padrão, o Sistema de Sala do Skype da organização remota não mostrará o link de ingressar na reunião no calendário.</span><span class="sxs-lookup"><span data-stu-id="35d56-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="35d56-110">Na verdade, os usuários do Outlook na organização remota não poderão participar da reunião do Skype for Business com um clique direito do item de calendário ou no lembrete da reunião.</span><span class="sxs-lookup"><span data-stu-id="35d56-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="35d56-111">Eles devem abrir o convite da reunião e clicar em Ingressar na Reunião do Skype for Business no corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="35d56-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="35d56-112">O motivo para essa limitação é que o Outlook e o Microsoft Exchange não usam um método especial para empacotar informações para enviar mensagens pela Internet.</span><span class="sxs-lookup"><span data-stu-id="35d56-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="35d56-113">Esse método, conhecido como TNEF (Transport Neutral Encapsulation Format), é desabilitado por padrão para mensagens enviadas externamente de uma organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="35d56-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="35d56-114">Para que um link de ingressar em uma reunião apareça em um Sistema de Sala skype remoto, a organização de envio deve habilitar o TNEF usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="35d56-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="35d56-115">Depois que o TNEF é habilitado para a organização remota, qualquer mensagem enviada pela Internet para a organização é enviada como um anexo no formato TNEF.</span><span class="sxs-lookup"><span data-stu-id="35d56-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="35d56-116">Com o TNEF habilitado, quando uma solicitação de reunião do Skype for Business for enviada para o parceiro federado do Skype for Business, o Sistema de Sala do Skype poderá renderizar a Reunião do Skype for Business e os usuários remotos poderão ingressar em reuniões do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="35d56-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
