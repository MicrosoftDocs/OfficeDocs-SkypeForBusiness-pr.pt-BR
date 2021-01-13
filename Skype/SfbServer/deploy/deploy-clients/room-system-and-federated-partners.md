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
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Parceiros federados do Skype Room System e Skype for Business
 
Leia este tópico para saber como configurar o Sistema de Sala do Skype para parceiros federados do Skype for Business.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Parceiros federados do Skype Room System e Skype for Business

O Sistema de Sala do Skype depende do link Ingressar na Reunião do Skype for Business na solicitação de reunião do calendário. O link de junção geralmente é encontrado no corpo de uma solicitação de reunião. No entanto, o Sistema de Sala do Skype depende desse link para estar presente nas propriedades MAPI da mensagem. Quando essa solicitação de reunião é enviada a organizações remotas (parceiros federados do Skype for Business), por padrão, o Sistema de Sala do Skype da organização remota não mostrará o link de ingressar na reunião no calendário. Na verdade, os usuários do Outlook na organização remota não poderão participar da reunião do Skype for Business com um clique direito do item de calendário ou no lembrete da reunião. Eles devem abrir o convite da reunião e clicar em Ingressar na Reunião do Skype for Business no corpo da mensagem. 
  
O motivo para essa limitação é que o Outlook e o Microsoft Exchange não usam um método especial para empacotar informações para enviar mensagens pela Internet. Esse método, conhecido como TNEF (Transport Neutral Encapsulation Format), é desabilitado por padrão para mensagens enviadas externamente de uma organização do Exchange. Para que um link de ingressar em uma reunião apareça em um Sistema de Sala skype remoto, a organização de envio deve habilitar o TNEF usando o seguinte comando:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Depois que o TNEF é habilitado para a organização remota, qualquer mensagem enviada pela Internet para a organização é enviada como um anexo no formato TNEF. Com o TNEF habilitado, quando uma solicitação de reunião do Skype for Business for enviada para o parceiro federado do Skype for Business, o Sistema de Sala do Skype poderá renderizar a Reunião do Skype for Business e os usuários remotos poderão ingressar em reuniões do Skype for Business. 
