---
title: Parceiros federados do Sistema de Salas do Skype e Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leia este tópico para saber como configurar o Sistema de Salas do Skype para parceiros federados do Skype for Business.
ms.openlocfilehash: 040af495217217b3bfd10fb577b7194df354e027
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="3c976-103">Parceiros federados do Sistema de Salas do Skype e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3c976-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="3c976-104">Leia este tópico para saber como configurar o Sistema de Salas do Skype para parceiros federados do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3c976-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="3c976-105">Parceiros federados do Sistema de Salas do Skype e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3c976-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="3c976-106">Sistema de sala Skype depende do Skype ingressar para o link da reunião de negócios na solicitação de reunião de calendário.</span><span class="sxs-lookup"><span data-stu-id="3c976-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="3c976-107">O link de ingresso normalmente é encontrado no corpo de uma solicitação de reunião.</span><span class="sxs-lookup"><span data-stu-id="3c976-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="3c976-108">No entanto, o sistema de sala de Skype depende neste link estar presentes nas propriedades da mensagem MAPI.</span><span class="sxs-lookup"><span data-stu-id="3c976-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="3c976-109">Quando esta reunião solicitação é enviada ao organizações remotas (Skype para parceiros de negócios federado), por padrão será de sistema de sala Skype remoto da organização não mostrar link de participação da reunião no calendário.</span><span class="sxs-lookup"><span data-stu-id="3c976-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="3c976-110">Na verdade, nenhum usuário do Outlook na organização remota poderão ingressar o Skype para reunião de negócios com o botão direito do mouse do calendário, item ou de dentro do lembrete da reunião.</span><span class="sxs-lookup"><span data-stu-id="3c976-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="3c976-111">Eles devem abrir o convite de reunião e clique em ingressar Skype para negócios de reunião no corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="3c976-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="3c976-112">O motivo para esta limitação é que o Outlook e o Microsoft Exchange não usam um método especial para organizar informações para enviar mensagens pela Internet.</span><span class="sxs-lookup"><span data-stu-id="3c976-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="3c976-113">Esse método, conhecido como Formato de Encapsulamento Neutro de Transporte (TNEF), está desabilitado por padrão para mensagens enviadas externamente de uma organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="3c976-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="3c976-114">Para uma reunião link de ingresso apareça em um sistema de sala Skype remoto, a organização de envio deve habilitar o TNEF usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3c976-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="3c976-115">Depois que o TNEF estiver habilitado para a organização remota, qualquer mensagem enviada através da Internet para a organização será enviada como um anexo no formato TNEF.</span><span class="sxs-lookup"><span data-stu-id="3c976-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="3c976-116">Com o TNEF habilitada, quando um Skype para solicitação de reunião de negócios é enviado para o Skype para parceiro federado de negócios, Skype sala sistema será capaz de renderizar Skype a participação de reunião de negócios e usuários remotos poderão ingressar Skype para reuniões de negócios.</span><span class="sxs-lookup"><span data-stu-id="3c976-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 