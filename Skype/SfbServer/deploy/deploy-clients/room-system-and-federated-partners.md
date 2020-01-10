---
title: Parceiros federados do Sistema de Salas do Skype e Skype for Business
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leia este tópico para saber como configurar o Sistema de Salas do Skype para parceiros federados do Skype for Business.
ms.openlocfilehash: 8ded7ba9be24cf1ac700be0ead1c7e0c3637becd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002991"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Parceiros federados do Sistema de Salas do Skype e Skype for Business
 
Leia este tópico para saber como configurar o Sistema de Salas do Skype para parceiros federados do Skype for Business.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Parceiros federados do Sistema de Salas do Skype e Skype for Business

O sistema de sala do Skype depende do link ingressar na reunião do Skype for Business na solicitação de reunião do calendário. O link de ingresso normalmente é encontrado no corpo de uma solicitação de reunião. No entanto, o sistema de sala do Skype depende desse link para estar presente nas propriedades MAPI da mensagem. Quando esta solicitação de reunião for enviada a organizações remotas (parceiros federados do Skype for Business), por padrão, o sistema de salas da organização remota não mostrará o link de ingresso na reunião no calendário. Na verdade, os usuários do Outlook na organização remota não poderão participar da reunião do Skype for Business com um clique com o botão direito do mouse no item do calendário ou no lembrete da reunião. Eles devem abrir o convite de reunião e clicar em ingressar na reunião do Skype for Business no corpo da mensagem. 
  
O motivo para esta limitação é que o Outlook e o Microsoft Exchange não usam um método especial para organizar informações para enviar mensagens pela Internet. Esse método, conhecido como Formato de Encapsulamento Neutro de Transporte (TNEF), está desabilitado por padrão para mensagens enviadas externamente de uma organização do Exchange. Para que o link de ingresso na reunião apareça em um sistema de sala remoto do Skype, a organização de envio deve habilitar o TNEF usando o seguinte comando:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Depois que o TNEF estiver habilitado para a organização remota, qualquer mensagem enviada através da Internet para a organização será enviada como um anexo no formato TNEF. Com o TNEF habilitado, quando uma solicitação de reunião do Skype for Business for enviada para o parceiro federado do Skype for Business, o sistema de salas da Skype poderá renderizar a reunião do Skype for Business e os usuários remotos poderão participar de reuniões do Skype for Business. 
